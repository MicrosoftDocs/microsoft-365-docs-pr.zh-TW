---
title: Microsoft Defender Office 365 中的威脅瀏覽器和即時偵測基本知識
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用 Explorer 或即時偵測，以有效地調查和回應威脅。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300122"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="0f09f-103">威脅瀏覽器和即時偵測基礎</span><span class="sxs-lookup"><span data-stu-id="0f09f-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="0f09f-104">本文內容：</span><span class="sxs-lookup"><span data-stu-id="0f09f-104">In this article:</span></span>

- [<span data-ttu-id="0f09f-105">威脅瀏覽器與即時偵測的差異</span><span class="sxs-lookup"><span data-stu-id="0f09f-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="0f09f-106">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="0f09f-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="0f09f-107">這是 **威脅 Explorer (Explorer)**、**電子郵件安全性** 及 **Explorer 和即時** 偵測 (基礎的 **3 篇文章** 中的一部分，例如工具間的差異，以及操作) 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="0f09f-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="0f09f-108">此系列中的其他兩篇文章是威脅流覽 [器中的威脅搜尋](threat-hunting-in-threat-explorer.md) ，以及 [使用威脅瀏覽器的電子郵件安全性](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="0f09f-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="0f09f-109">本文說明威脅探索與即時偵測報告的差異，以及所需的授權和許可權。</span><span class="sxs-lookup"><span data-stu-id="0f09f-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="0f09f-110">**適用於**</span><span class="sxs-lookup"><span data-stu-id="0f09f-110">**Applies to**</span></span>
- [<span data-ttu-id="0f09f-111">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="0f09f-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0f09f-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f09f-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0f09f-113">如果您的組織有 [Office 365 的 Microsoft Defender](defender-for-office-365.md)，而且您具有 [許可權](#required-licenses-and-permissions)，則可以使用 **威脅 explorer** (稱為 **Explorer**) 或 **即時** 偵測，以偵測並修正威脅。</span><span class="sxs-lookup"><span data-stu-id="0f09f-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="0f09f-114">在 [ **安全性 & 規範中心**] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時** 偵測]。</span><span class="sxs-lookup"><span data-stu-id="0f09f-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="0f09f-115">使用 Microsoft Defender Office 365 方案2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="0f09f-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="0f09f-116">使用 Microsoft Defender Office 365 方案1，您會看到：</span><span class="sxs-lookup"><span data-stu-id="0f09f-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="0f09f-119">使用這些工具，您可以：</span><span class="sxs-lookup"><span data-stu-id="0f09f-119">With these tools, you can:</span></span>

- <span data-ttu-id="0f09f-120">請參閱 Microsoft 365 安全性功能偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="0f09f-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="0f09f-121">查看網路釣魚 URL，然後按一下 [已判定資料]。</span><span class="sxs-lookup"><span data-stu-id="0f09f-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="0f09f-122">從瀏覽器中的視圖開始自動調查和回應程式。</span><span class="sxs-lookup"><span data-stu-id="0f09f-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="0f09f-123">調查惡意電子郵件及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="0f09f-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="0f09f-124">如需詳細資訊，請參閱 [使用威脅瀏覽器的電子郵件安全性](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="0f09f-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="0f09f-125">威脅瀏覽器與即時偵測的差異</span><span class="sxs-lookup"><span data-stu-id="0f09f-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="0f09f-126">*即時* 偵測是適用于 Office 365 方案1之 Defender 的報表工具。</span><span class="sxs-lookup"><span data-stu-id="0f09f-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="0f09f-127">*威脅瀏覽器* 是適用于 Office 365 方案2之 Defender 的威脅搜尋和修正工具。</span><span class="sxs-lookup"><span data-stu-id="0f09f-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="0f09f-128">即時偵測報告可讓您即時查看偵測。</span><span class="sxs-lookup"><span data-stu-id="0f09f-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="0f09f-129">威脅瀏覽器也會這麼做，但是它會提供特定攻擊的其他詳細資料，例如，反白顯示攻擊活動，並讓安全性運作小組能夠修正威脅 (包括觸發 [自動調查和回應調查](automated-investigation-response-office.md)) 。</span><span class="sxs-lookup"><span data-stu-id="0f09f-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="0f09f-130">*所有的電子郵件* view 都可用於威脅瀏覽器，但不會包含在即時偵測報告中。</span><span class="sxs-lookup"><span data-stu-id="0f09f-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="0f09f-131">威脅瀏覽器中包含豐富型篩選功能和修正動作。</span><span class="sxs-lookup"><span data-stu-id="0f09f-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="0f09f-132">如需詳細資訊，請參閱[Microsoft defender for Office 365 Service Description：每個 defender 的功能可用性以取得 Office 365 計畫](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="0f09f-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="0f09f-133">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="0f09f-133">Required licenses and permissions</span></span>

<span data-ttu-id="0f09f-134">您必須具有[Microsoft Defender Office 365](defender-for-office-365.md) ，才能使用瀏覽器或即時偵測的其中一項：</span><span class="sxs-lookup"><span data-stu-id="0f09f-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="0f09f-135">但是 Explorer 只會包含在 Office 365 方案2的 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="0f09f-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="0f09f-136">在 Office 365 方案1的 Defender 中包含即時偵測報告。</span><span class="sxs-lookup"><span data-stu-id="0f09f-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="0f09f-137">安全性作業小組需要為所有應受 Office 365 的 Defender 保護的使用者指派授權，並請注意，瀏覽器和即時偵測會顯示已授權使用者的偵測資料。</span><span class="sxs-lookup"><span data-stu-id="0f09f-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="0f09f-138">若要查看和使用 Explorer *或* 即時偵測，您必須具備下列各項：</span><span class="sxs-lookup"><span data-stu-id="0f09f-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="0f09f-139">針對安全性 & 規範中心：</span><span class="sxs-lookup"><span data-stu-id="0f09f-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="0f09f-140">組織管理</span><span class="sxs-lookup"><span data-stu-id="0f09f-140">Organization Management</span></span>
  - <span data-ttu-id="0f09f-141">安全性管理員 (可以在 Azure Active Directory 系統管理中心 (中指派 <https://aad.portal.azure.com>) </span><span class="sxs-lookup"><span data-stu-id="0f09f-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="0f09f-142">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="0f09f-142">Security Reader</span></span>

- <span data-ttu-id="0f09f-143">Exchange Online：</span><span class="sxs-lookup"><span data-stu-id="0f09f-143">For Exchange Online:</span></span>

  - <span data-ttu-id="0f09f-144">組織管理</span><span class="sxs-lookup"><span data-stu-id="0f09f-144">Organization Management</span></span>
  - <span data-ttu-id="0f09f-145">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="0f09f-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="0f09f-146">僅限檢視收件者</span><span class="sxs-lookup"><span data-stu-id="0f09f-146">View-Only Recipients</span></span>
  - <span data-ttu-id="0f09f-147">合規性管理</span><span class="sxs-lookup"><span data-stu-id="0f09f-147">Compliance Management</span></span>

<span data-ttu-id="0f09f-148">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="0f09f-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="0f09f-149">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="0f09f-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="0f09f-150">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="0f09f-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="0f09f-151">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f09f-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="0f09f-152">其他資訊</span><span class="sxs-lookup"><span data-stu-id="0f09f-152">More information</span></span>
- [<span data-ttu-id="0f09f-153">威脅瀏覽器收集電子郵件實體頁面上的電子郵件詳細資料</span><span class="sxs-lookup"><span data-stu-id="0f09f-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="0f09f-154">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="0f09f-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="0f09f-155">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="0f09f-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="0f09f-156">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="0f09f-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="0f09f-157">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="0f09f-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)