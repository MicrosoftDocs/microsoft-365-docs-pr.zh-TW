---
title: 針對 Office 365、構造、建立及設計框架，檢查 Microsoft Defender 的架構需求和規劃概念
description: Microsoft 365 Defender 中的 Microsoft Defender Office 365 的技術圖表可協助您在建立試用實驗室或試驗環境之前，先瞭解 Microsoft 365 中的身分識別。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 15c84921dcfb4644241cf83ce4ffb6403180b9d4
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457877"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a><span data-ttu-id="e69ab-103">查看 Microsoft Defender 以取得 Office 365 架構需求和重要概念</span><span class="sxs-lookup"><span data-stu-id="e69ab-103">Review Microsoft Defender for Office 365 architecture requirements and key concepts</span></span>


<span data-ttu-id="e69ab-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e69ab-104">**Applies to:**</span></span>
- <span data-ttu-id="e69ab-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e69ab-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="e69ab-106">本文是為 Office 365 的 Microsoft Defender 設定評估環境過程中的[步驟1之 3](eval-defender-office-365-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="e69ab-106">This article is [Step 1 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e69ab-107">如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-office-365-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e69ab-107">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="e69ab-108">在啟用 Office 365 的 Defender 之前，請確定您瞭解架構並可滿足需求。</span><span class="sxs-lookup"><span data-stu-id="e69ab-108">Before enabling Defender for Office 365, be sure you understand the architecture and can meet the requirements.</span></span> <span data-ttu-id="e69ab-109">本文說明架構、重要概念，以及您的 Exchange Online 環境必須符合的必要條件。</span><span class="sxs-lookup"><span data-stu-id="e69ab-109">This article describes the architecture, key concepts, and the prerequisites that your Exchange Online environment must meet.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="e69ab-110">了解架構</span><span class="sxs-lookup"><span data-stu-id="e69ab-110">Understand the architecture</span></span>

<span data-ttu-id="e69ab-111">下圖說明 Microsoft Defender for Office 的基準架構，其中可以包含協力廠商 SMTP 閘道或內部部署整合。</span><span class="sxs-lookup"><span data-stu-id="e69ab-111">The following diagram illustrates baseline architecture for Microsoft Defender for Office which can include a third-party SMTP gateway or on-premises integration.</span></span> <span data-ttu-id="e69ab-112">混合共存案例 (亦即，實際執行和線上) 都需要更複雜的設定，而且不會包含在本文或評估指導中。</span><span class="sxs-lookup"><span data-stu-id="e69ab-112">Hybrid coexistence scenarios (i.e. production mailboxes are both on-premise and online) require more complex configurations and are not covered in this article or evaluation guidance.</span></span>

![適用于 Office 365 的 Microsoft Defender 架構](../../media/defender/m365-defender-office-architecture.png)

<span data-ttu-id="e69ab-114">下表說明此圖例。</span><span class="sxs-lookup"><span data-stu-id="e69ab-114">The following table describes this illustration.</span></span>

|<span data-ttu-id="e69ab-115">撥出</span><span class="sxs-lookup"><span data-stu-id="e69ab-115">Call-out</span></span>  |<span data-ttu-id="e69ab-116">說明</span><span class="sxs-lookup"><span data-stu-id="e69ab-116">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e69ab-117">1</span><span class="sxs-lookup"><span data-stu-id="e69ab-117">1</span></span>     | <span data-ttu-id="e69ab-118">外部寄件者的主機伺服器通常會對 MX 記錄執行公用 DNS 查閱，以提供目標伺服器轉送郵件。</span><span class="sxs-lookup"><span data-stu-id="e69ab-118">The host server for the external sender typically performs a public DNS lookup for an MX record which provides the target server to relay the message.</span></span>  <span data-ttu-id="e69ab-119">這項參考可以直接 Exchange Online (EXO) 或已設定為要轉送 EXO 的 SMTP 閘道。</span><span class="sxs-lookup"><span data-stu-id="e69ab-119">This referral can either be Exchange Online (EXO) directly or an SMTP gateway that has been configured to relay against EXO.</span></span>  |
|<span data-ttu-id="e69ab-120">2 </span><span class="sxs-lookup"><span data-stu-id="e69ab-120">2</span></span>     | <span data-ttu-id="e69ab-121">Exchange Online Protection 會協商及驗證輸入連線，並檢查郵件頭和內容，以決定所需的其他原則、標記或處理。</span><span class="sxs-lookup"><span data-stu-id="e69ab-121">Exchange Online Protection negotiates and validates the inbound connection and inspects the message headers and content to determine what additional policies, tagging, or processing is required.</span></span>  |
|<span data-ttu-id="e69ab-122">3 </span><span class="sxs-lookup"><span data-stu-id="e69ab-122">3</span></span>     | <span data-ttu-id="e69ab-123">Exchange Online 會與 Microsoft Defender Office 365 整合，以提供更高級的威脅防護、減輕和修正。</span><span class="sxs-lookup"><span data-stu-id="e69ab-123">Exchange Online integrates with Microsoft Defender for Office 365 to offer more advanced threat protection, mitigation, and remediation.</span></span> |
|<span data-ttu-id="e69ab-124">4 </span><span class="sxs-lookup"><span data-stu-id="e69ab-124">4</span></span>     | <span data-ttu-id="e69ab-125">會處理不是惡意、封鎖或隔離的郵件，並傳遞至 EXO 中的收件者，而這些收件者與垃圾郵件、信箱規則或其他設定會評估並觸發使用者喜好設定。</span><span class="sxs-lookup"><span data-stu-id="e69ab-125">A message that is not malicious, blocked, or quarantined is processed and delivered to the recipient in EXO where user preferences related to junk mail, mailbox rules, or other settings are evaluated and triggered.</span></span> |
|<span data-ttu-id="e69ab-126">5 </span><span class="sxs-lookup"><span data-stu-id="e69ab-126">5</span></span>     | <span data-ttu-id="e69ab-127">您可以使用 Azure AD 連線來啟用內部部署 Active Directory 的整合，以同步處理及布建具有郵件功能的物件和帳戶，以 Azure Active Directory 並最終 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e69ab-127">Integration with on-premises Active Directory can be enabled using Azure AD Connect to synchronize and provision mail-enabled objects and accounts to Azure Active Directory and ultimately Exchange Online.</span></span> |
|<span data-ttu-id="e69ab-128">6 </span><span class="sxs-lookup"><span data-stu-id="e69ab-128">6</span></span>     | <span data-ttu-id="e69ab-129">整合內部部署環境時，強烈建議使用 Exchange 伺服器來支援管理和管理郵件相關的屬性、設定和設定</span><span class="sxs-lookup"><span data-stu-id="e69ab-129">When integrating an on-premises environment, it is strongly encouraged to use an Exchange server for supported management and administration of mail related attributes, settings, and configurations</span></span> |
|<span data-ttu-id="e69ab-130">7 </span><span class="sxs-lookup"><span data-stu-id="e69ab-130">7</span></span>     | <span data-ttu-id="e69ab-131">Microsoft Defender for Office 365 分享 Microsoft 365 Defender 以進行延伸偵測及回應 (XDR) 的信號。</span><span class="sxs-lookup"><span data-stu-id="e69ab-131">Microsoft Defender for Office 365 shares signals to Microsoft 365 Defender for extended detection and response (XDR).</span></span>|

<span data-ttu-id="e69ab-132">內部部署整合一般但選用。</span><span class="sxs-lookup"><span data-stu-id="e69ab-132">On-premises integration is common but optional.</span></span> <span data-ttu-id="e69ab-133">如果您的環境僅限雲端，此指南也會為您運作。</span><span class="sxs-lookup"><span data-stu-id="e69ab-133">If your environment is cloud-only this guidance will also work for you.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="e69ab-134">瞭解重要概念</span><span class="sxs-lookup"><span data-stu-id="e69ab-134">Understand key concepts</span></span>

<span data-ttu-id="e69ab-135">下表識別重要概念，在評估、設定及部署 MDO 時，請務必瞭解。</span><span class="sxs-lookup"><span data-stu-id="e69ab-135">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying MDO.</span></span>


|<span data-ttu-id="e69ab-136">概念</span><span class="sxs-lookup"><span data-stu-id="e69ab-136">Concept</span></span>  |<span data-ttu-id="e69ab-137">描述</span><span class="sxs-lookup"><span data-stu-id="e69ab-137">Description</span></span> |<span data-ttu-id="e69ab-138">其他資訊</span><span class="sxs-lookup"><span data-stu-id="e69ab-138">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e69ab-139">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e69ab-139">Exchange Online Protection</span></span>      |    <span data-ttu-id="e69ab-140">Exchange Online Protection (EOP) 是雲端架構篩選服務，可協助您的組織抵禦垃圾郵件和惡意程式碼電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e69ab-140">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware emails.</span></span> <span data-ttu-id="e69ab-141">EOP 包含 Exchange Online 中的所有 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="e69ab-141">EOP is included in all Microsoft 365 licenses which include Exchange Online.</span></span>     |   [<span data-ttu-id="e69ab-142">Exchange Online Protection 概觀</span><span class="sxs-lookup"><span data-stu-id="e69ab-142">Exchange Online Protection overview</span></span>](../office-365-security/exchange-online-protection-overview.md)      |
|<span data-ttu-id="e69ab-143">反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="e69ab-143">Anti-malware protection</span></span>     |    <span data-ttu-id="e69ab-144">在 EXO 中擁有信箱的組織，會自動抵禦惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="e69ab-144">Organizations with mailboxes in EXO are automatically protected against malware.</span></span>     |  [<span data-ttu-id="e69ab-145">EOP 中的反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="e69ab-145">Anti-malware protection in EOP</span></span>](../office-365-security/anti-malware-protection.md)       |
|<span data-ttu-id="e69ab-146">反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="e69ab-146">Anti-spam protection</span></span>     |   <span data-ttu-id="e69ab-147">在 EXO 中擁有信箱的組織，會自動抵禦垃圾郵件和垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="e69ab-147">Organizations with mailboxes in EXO are automatically protected against junk mail and spam policies.</span></span>      |  [<span data-ttu-id="e69ab-148">EOP 中的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="e69ab-148">Anti-spam protection in EOP</span></span>](../office-365-security/anti-spam-protection.md)       |
|<span data-ttu-id="e69ab-149">防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="e69ab-149">Anti-phishing protection</span></span> |  <span data-ttu-id="e69ab-150">MDO 提供更多有關 spear 網路釣魚、whaling、勒索軟體和其他惡意活動的高級反網路釣魚防護。</span><span class="sxs-lookup"><span data-stu-id="e69ab-150">MDO offers more advanced anti-phishing  protection related to spear phishing, whaling, ransomware, and other malicious activities.</span></span>   | [<span data-ttu-id="e69ab-151">適用於 Office 365 的 Microsoft Defender 中的防網路釣魚防護</span><span class="sxs-lookup"><span data-stu-id="e69ab-151">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>](../office-365-security/anti-phishing-protection.md)   |
|<span data-ttu-id="e69ab-152">反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="e69ab-152">Anti-spoofing protection</span></span>     |   <span data-ttu-id="e69ab-153">EOP 包含的功能可協助您保護您的組織免受冒牌 (假冒) 寄件者。</span><span class="sxs-lookup"><span data-stu-id="e69ab-153">EOP includes features to help protect your organization from spoofed (forged) senders.</span></span>      |   [<span data-ttu-id="e69ab-154">EOP 中的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="e69ab-154">Anti-spoofing protection in EOP</span></span>](../office-365-security/anti-spoofing-protection.md)      |
|<span data-ttu-id="e69ab-155">安全附件</span><span class="sxs-lookup"><span data-stu-id="e69ab-155">Safe attachments</span></span>     |   <span data-ttu-id="e69ab-156">保管庫附件會在傳送電子郵件之前，使用虛擬環境來檢查和 "引爆" 附件，以提供其他層級的保護。</span><span class="sxs-lookup"><span data-stu-id="e69ab-156">Safe Attachments provides an additional layer of protection by using a virtual environment to check and "detonate" attachments in email messages before they are delivered.</span></span>      |   [<span data-ttu-id="e69ab-157">保管庫Microsoft Defender 中 Office 365 的附件</span><span class="sxs-lookup"><span data-stu-id="e69ab-157">Safe Attachments in Microsoft Defender for Office 365</span></span>](../office-365-security/safe-attachments.md)      |
|<span data-ttu-id="e69ab-158">保管庫 SharePoint、OneDrive 和 Microsoft Teams 的附件</span><span class="sxs-lookup"><span data-stu-id="e69ab-158">Safe attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>     |    <span data-ttu-id="e69ab-159">此外，SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件為已上傳至雲端儲存庫的檔案，提供額外的保護層級。</span><span class="sxs-lookup"><span data-stu-id="e69ab-159">In addition, Safe Attachments for SharePoint, OneDrive, and Microsoft Teams offers an additional layer of protection for files that have been uploaded to cloud storage repositories.</span></span>     |  [<span data-ttu-id="e69ab-160">適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="e69ab-160">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|<span data-ttu-id="e69ab-161">安全連結</span><span class="sxs-lookup"><span data-stu-id="e69ab-161">Safe Links</span></span>     | <span data-ttu-id="e69ab-162">保管庫連結是一種功能，可提供輸入電子郵件訊息中的 URL 掃描和修正，並在傳送或按一下這些連結之前提供驗證。</span><span class="sxs-lookup"><span data-stu-id="e69ab-162">Safe Links is a feature that provides URL scanning and rewriting within inbound email messages and offers verification of those links before they are delivered or clicked.</span></span>        |   [<span data-ttu-id="e69ab-163">保管庫Microsoft Defender 中 Office 365 的連結</span><span class="sxs-lookup"><span data-stu-id="e69ab-163">Safe Links in Microsoft Defender for Office 365</span></span>](../office-365-security/safe-links.md)      |
|    |         |         |

<span data-ttu-id="e69ab-164">如需與 Office 之 microsoft defender 有關之功能的詳細資訊，請參閱[Microsoft defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="e69ab-164">For more detailed information about the capabilities included with Microsoft Defender for Office, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="review-architecture-requirements"></a><span data-ttu-id="e69ab-165">評審架構需求</span><span class="sxs-lookup"><span data-stu-id="e69ab-165">Review architecture requirements</span></span>
<span data-ttu-id="e69ab-166">成功的 MDO 評估或生產試驗假設下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="e69ab-166">A successful MDO evaluation or production pilot assumes the following pre-requisites:</span></span>
- <span data-ttu-id="e69ab-167">您目前在 Exchange Online 中的所有收件者信箱。</span><span class="sxs-lookup"><span data-stu-id="e69ab-167">All your recipient mailboxes are currently in Exchange Online.</span></span>
- <span data-ttu-id="e69ab-168">您的公用 MX 記錄會直接解析為 EOP 或協力廠商 SMTP 閘道，然後將輸入外部電子郵件直接轉送至 EOP。</span><span class="sxs-lookup"><span data-stu-id="e69ab-168">Your public MX record resolves directly to EOP or a third-party SMTP gateway that then relays inbound external email directly to EOP.</span></span>
- <span data-ttu-id="e69ab-169">您的主要電子郵件網域已設定為 Exchange Online 中的 *授權*。</span><span class="sxs-lookup"><span data-stu-id="e69ab-169">Your primary email domain is configured as *authoritative* in Exchange Online.</span></span>
- <span data-ttu-id="e69ab-170">您已成功部署和設定 *目錄架構邊緣封鎖* (DBEB) 適當。</span><span class="sxs-lookup"><span data-stu-id="e69ab-170">You successfully deployed and configured *Directory Based Edge Blocking* (DBEB) as appropriate.</span></span> <span data-ttu-id="e69ab-171">如需詳細資訊，請參閱[使用目錄架構邊緣封鎖拒絕傳送給無效收件者的郵件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="e69ab-171">For more information, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e69ab-172">如果這些需求不適用，或您仍然處於混合共存案例中，則 Microsoft Defender Office 365 評估可能需要更複雜或更高級的設定，這項指南並未完全涵蓋。</span><span class="sxs-lookup"><span data-stu-id="e69ab-172">If these requirements are not applicable or you are still in a hybrid coexistence scenario, then a Microsoft Defender for Office 365 evaluation can require more complex or advanced configurations which are not fully covered in this guidance.</span></span>

## <a name="siem-integration"></a><span data-ttu-id="e69ab-173">SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="e69ab-173">SIEM integration</span></span>

<span data-ttu-id="e69ab-174">您可以整合 Microsoft Defender for with Azure Sentinel Office 365 與 Azure Sentinel 整合，以更全面地分析整個組織的安全性事件，並建立行動行動以取得有效且立即的回應。</span><span class="sxs-lookup"><span data-stu-id="e69ab-174">You can integrate Microsoft Defender for Office 365 with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> <span data-ttu-id="e69ab-175">如需詳細資訊，請參閱[連線來自 Microsoft Defender 的警示 Office 365](/azure/sentinel/connect-office-365-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="e69ab-175">For more information, see [Connect alerts from Microsoft Defender for Office 365](/azure/sentinel/connect-office-365-advanced-threat-protection).</span></span>

<span data-ttu-id="e69ab-176">Microsoft Defender for Office 365 也可以整合至其他安全性資訊和事件管理 (使用[Office 365 活動管理 API](/office/office-365-management-api/office-365-management-activity-api-reference)的 SIEM) 方案。</span><span class="sxs-lookup"><span data-stu-id="e69ab-176">Microsoft Defender for Office 365 can also be integrated into other Security Information and Event Management (SIEM) solutions using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e69ab-177">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e69ab-177">Next steps</span></span>

<span data-ttu-id="e69ab-178">步驟2之3：[啟用評估環境 Microsoft Defender for Office 365](eval-defender-office-365-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="e69ab-178">Step 2 of 3: [Enable the evaluation environment Microsoft Defender for Office 365](eval-defender-office-365-enable-eval.md)</span></span>

<span data-ttu-id="e69ab-179">回到概述，以[評估 Microsoft Defender 的 Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e69ab-179">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="e69ab-180">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="e69ab-180">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span> 

