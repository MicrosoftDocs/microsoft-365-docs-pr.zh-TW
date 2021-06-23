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
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083185"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="dd987-103">瀏覽器與即時偵測基礎</span><span class="sxs-lookup"><span data-stu-id="dd987-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="dd987-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="dd987-104">**Applies to**</span></span>
- [<span data-ttu-id="dd987-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="dd987-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="dd987-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd987-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="dd987-107">本文內容：</span><span class="sxs-lookup"><span data-stu-id="dd987-107">In this article:</span></span>

- [<span data-ttu-id="dd987-108">瀏覽器與即時偵測之間的差異</span><span class="sxs-lookup"><span data-stu-id="dd987-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="dd987-109">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="dd987-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="dd987-110">這是 Explorer 的 **3 篇文章系列** 的一部分，也就是「 **威脅瀏覽器」)**、 **電子郵件安全性** 及 **瀏覽器和即時偵測基礎** (（如工具間的差異，以及操作) 所需的許可權）等 (。</span><span class="sxs-lookup"><span data-stu-id="dd987-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="dd987-111">本系列中的其他兩篇文章是使用 explorer 中的「 [威脅搜尋](threat-hunting-in-threat-explorer.md) 」和「 [電子郵件安全性](email-security-in-microsoft-defender.md)」。</span><span class="sxs-lookup"><span data-stu-id="dd987-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="dd987-112">本文說明 Explorer 與即時偵測報告之間的差異，以及所需的授權和許可權。</span><span class="sxs-lookup"><span data-stu-id="dd987-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="dd987-113">如果您的組織有 [Microsoft Defender for Office 365](defender-for-office-365.md)，而且您具有 [許可權](#required-licenses-and-permissions)，您可以使用 **Explorer** (也稱為 **威脅瀏覽器**) 或 **即時** 偵測，以偵測和修正威脅。</span><span class="sxs-lookup"><span data-stu-id="dd987-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="dd987-114">在 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 中，移至 [**電子郵件 &** 共同作業]，然後選擇 [ **Explorer** ]_或_[**即時** 偵測]。</span><span class="sxs-lookup"><span data-stu-id="dd987-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="dd987-115">使用這些工具，您可以：</span><span class="sxs-lookup"><span data-stu-id="dd987-115">With these tools, you can:</span></span>

- <span data-ttu-id="dd987-116">請參閱 Microsoft 365 安全性功能偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="dd987-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="dd987-117">查看網路釣魚 URL，然後按一下 [已判定資料]。</span><span class="sxs-lookup"><span data-stu-id="dd987-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="dd987-118">從瀏覽器中的視圖開始自動調查和回應程式。</span><span class="sxs-lookup"><span data-stu-id="dd987-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="dd987-119">調查惡意電子郵件及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="dd987-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="dd987-120">如需詳細資訊，請參閱 [使用 Explorer 的電子郵件安全性](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="dd987-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="dd987-121">瀏覽器與即時偵測之間的差異</span><span class="sxs-lookup"><span data-stu-id="dd987-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="dd987-122">*即時* 偵測是適用于 Office 365 方案1之 Defender 的報表工具。</span><span class="sxs-lookup"><span data-stu-id="dd987-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="dd987-123">*威脅瀏覽器* 是適用于 Office 365 方案2之 Defender 的威脅搜尋和修正工具。</span><span class="sxs-lookup"><span data-stu-id="dd987-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="dd987-124">即時偵測報告可讓您即時查看偵測。</span><span class="sxs-lookup"><span data-stu-id="dd987-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="dd987-125">威脅瀏覽器也會這麼做，但是它會提供特定攻擊的其他詳細資料，例如，反白顯示攻擊活動，並讓安全性運作小組能夠修正威脅 (包括觸發 [自動調查和回應調查](automated-investigation-response-office.md)) 。</span><span class="sxs-lookup"><span data-stu-id="dd987-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="dd987-126">*所有的電子郵件* view 都可用於威脅瀏覽器，但不會包含在即時偵測報告中。</span><span class="sxs-lookup"><span data-stu-id="dd987-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="dd987-127">威脅瀏覽器中包含豐富型篩選功能和修正動作。</span><span class="sxs-lookup"><span data-stu-id="dd987-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="dd987-128">如需詳細資訊，請參閱[Microsoft defender for Office 365 Service Description：每個 defender 的功能可用性以取得 Office 365 計畫](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="dd987-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="dd987-129">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="dd987-129">Required licenses and permissions</span></span>

<span data-ttu-id="dd987-130">您必須具有[Microsoft Defender Office 365](defender-for-office-365.md) ，才能使用瀏覽器或即時偵測的其中一項：</span><span class="sxs-lookup"><span data-stu-id="dd987-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="dd987-131">Explorer 只會包含在 Office 365 方案2的 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="dd987-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="dd987-132">在 Office 365 方案1的 Defender 中包含即時偵測報告。</span><span class="sxs-lookup"><span data-stu-id="dd987-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="dd987-133">安全性作業小組需要為所有應受 Office 365 的 Defender 保護的使用者指派授權，並請注意，瀏覽器和即時偵測會顯示已授權使用者的偵測資料。</span><span class="sxs-lookup"><span data-stu-id="dd987-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="dd987-134">若要查看和使用 Explorer *或* 即時偵測，您必須具備下列許可權：</span><span class="sxs-lookup"><span data-stu-id="dd987-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="dd987-135">在 Office 365 的 Defender 中：</span><span class="sxs-lookup"><span data-stu-id="dd987-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="dd987-136">組織管理</span><span class="sxs-lookup"><span data-stu-id="dd987-136">Organization Management</span></span>
  - <span data-ttu-id="dd987-137">安全性管理員 (可以在 Azure Active Directory 系統管理中心 (中指派 <https://aad.portal.azure.com>) </span><span class="sxs-lookup"><span data-stu-id="dd987-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="dd987-138">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="dd987-138">Security Reader</span></span>
- <span data-ttu-id="dd987-139">在 Exchange Online 中：</span><span class="sxs-lookup"><span data-stu-id="dd987-139">In Exchange Online:</span></span>
  - <span data-ttu-id="dd987-140">組織管理</span><span class="sxs-lookup"><span data-stu-id="dd987-140">Organization Management</span></span>
  - <span data-ttu-id="dd987-141">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="dd987-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="dd987-142">僅限檢視收件者</span><span class="sxs-lookup"><span data-stu-id="dd987-142">View-Only Recipients</span></span>
  - <span data-ttu-id="dd987-143">合規性管理</span><span class="sxs-lookup"><span data-stu-id="dd987-143">Compliance Management</span></span>

<span data-ttu-id="dd987-144">若要深入瞭解角色和許可權，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="dd987-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="dd987-145">Microsoft 365 Defender 入口網站中的權限</span><span class="sxs-lookup"><span data-stu-id="dd987-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="dd987-146">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="dd987-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="dd987-147">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="dd987-147">More information</span></span>

- [<span data-ttu-id="dd987-148">威脅瀏覽器收集電子郵件實體頁面上的電子郵件詳細資料</span><span class="sxs-lookup"><span data-stu-id="dd987-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="dd987-149">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="dd987-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="dd987-150">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="dd987-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="dd987-151">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="dd987-151">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="dd987-152">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="dd987-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
