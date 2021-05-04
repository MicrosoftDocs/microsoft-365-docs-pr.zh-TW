---
title: 開始使用預設的 DLP 原則
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何使用此報告來精煉組織的預設資料遺失防護 (DLP) 原則。
ms.openlocfilehash: 4530e570f0ce593a7d2cb62acc28dfa4e1658df0
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114081"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="2315e-103">開始使用預設的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="2315e-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="2315e-104">在您甚至建立第一個資料遺失防護 (DLP) 原則之前，DLP 都有助您使用預設原則來保護您的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="2315e-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="2315e-105">此預設原則及其建議 (如下所示) 協助您在組織外的人員共用包含信用卡號碼的電子郵件或檔時通知您，以保障機密內容的安全。</span><span class="sxs-lookup"><span data-stu-id="2315e-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="2315e-106">您會在安全性與合規性中心 **的首頁上** 看到此建議 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="2315e-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="2315e-107">您可以使用此小工具快速查看共用的敏感資訊的時間和程度，然後只需按一下一次或兩次，以精煉預設 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="2315e-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="2315e-108">您也可以隨時編輯預設 DLP 原則，因為它完全可自訂。</span><span class="sxs-lookup"><span data-stu-id="2315e-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="2315e-109">請注意，如果您第一次沒有看到建議，請嘗試按一下 [**建議**] 區段底部的 [**其他**]。</span><span class="sxs-lookup"><span data-stu-id="2315e-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![名為進一步的小工具保護共用內容](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="2315e-111">查看報告並調整預設 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="2315e-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="2315e-112">當小工具顯示使用者與組織外部人員共用機密資訊時，請選擇底部的 [ **優化 DLP 原則** ]。</span><span class="sxs-lookup"><span data-stu-id="2315e-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="2315e-113">詳細報告會向您顯示過去30天內，包含信用卡號碼共用的內容數量和數目。</span><span class="sxs-lookup"><span data-stu-id="2315e-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="2315e-114">請注意，規則相符可能需要長達48小時才能顯示在構件中。</span><span class="sxs-lookup"><span data-stu-id="2315e-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="2315e-115">為了協助保護機密資訊，預設 DLP 原則為：</span><span class="sxs-lookup"><span data-stu-id="2315e-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="2315e-116">在包含至少一張信用卡號碼的 Exchange、SharePoint 和 OneDrive 中，偵測到組織外部人員共用的內容。</span><span class="sxs-lookup"><span data-stu-id="2315e-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="2315e-117">顯示原則提示，當使用者嘗試與組織外部的人員共用此機密資訊時，將電子郵件通知傳送給他們。</span><span class="sxs-lookup"><span data-stu-id="2315e-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="2315e-118">如需這些選項的詳細資訊，請參閱 [傳送電子郵件通知及顯示 DLP 原則的原則秘訣](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="2315e-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="2315e-119">產生詳細的活動報告，使您可以追蹤與組織外部的人員共用內容的人員，以及他們的情況。</span><span class="sxs-lookup"><span data-stu-id="2315e-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="2315e-120">您可以使用 [DLP 報告](view-the-dlp-reports.md)和 [審核記錄資料](search-the-audit-log-in-security-and-compliance.md) (其中的 **活動**  =  **DLP**) 來查看此資訊。</span><span class="sxs-lookup"><span data-stu-id="2315e-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="2315e-121">若要快速提煉預設 DLP 原則，您可以選擇讓它具有下列專案：</span><span class="sxs-lookup"><span data-stu-id="2315e-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="2315e-122">當使用者與組織外部的人員共用此機密資訊時，向您傳送附隨報告電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2315e-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="2315e-123">將其他使用者新增至電子郵件附隨報告。</span><span class="sxs-lookup"><span data-stu-id="2315e-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="2315e-124">封鎖存取包含機密資訊的內容，但是允許使用者在需要時覆寫和共用或傳送。</span><span class="sxs-lookup"><span data-stu-id="2315e-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="2315e-125">如需有關附隨報告或限制存取的詳細資訊，請參閱 [資料遺失防護參考](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2315e-125">For more information on incident reports or restricting access, see [Data loss prevention reference](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="2315e-126">如果您想要稍後變更這些選項，您可以隨時編輯預設 DLP 原則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="2315e-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![名為進一步保護共用內容的小工具設定](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="2315e-128">編輯預設 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="2315e-128">Edit the default DLP policy</span></span>

<span data-ttu-id="2315e-129">這個原則命名為「**預設 DLP 原則**」，而且會出現在安全性與規範中心的 [**原則**] 頁面的 [**資料遺失防護**] 底下 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="2315e-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="2315e-130">這個原則可以完全自訂，與您從頭建立的任何 DLP 原則相同。</span><span class="sxs-lookup"><span data-stu-id="2315e-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="2315e-131">您也可以關閉或刪除原則，如此一來，您的使用者就不會再收到原則提示或電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="2315e-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![名為預設 DLP 原則的 DLP 原則](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="2315e-133">構件的功能及未出現時</span><span class="sxs-lookup"><span data-stu-id="2315e-133">When the widget does and does not appear</span></span>

<span data-ttu-id="2315e-134">在安全性與合規性中心 **首頁的 [** **建議**] 區段中，會顯示名為「**進一步保護共用內容**」的小工具 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="2315e-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="2315e-135">只有在下列情況時才會顯示此小工具：</span><span class="sxs-lookup"><span data-stu-id="2315e-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="2315e-136">在安全性與 &amp; 合規性中心或 Exchange 系統管理中心中，沒有資料遺失防護原則。</span><span class="sxs-lookup"><span data-stu-id="2315e-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="2315e-137">此小工具的目的是協助您開始使用 DLP，所以如果您已有 DLP 原則，就不會顯示。</span><span class="sxs-lookup"><span data-stu-id="2315e-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="2315e-138">在過去30天內，包含至少一張信用卡的內容已與組織外部的人員共用。</span><span class="sxs-lookup"><span data-stu-id="2315e-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="2315e-139">請注意，可供小工具使用的規則比對可長達48個小時，所以在偵測到外部共用的敏感資訊之後，可能需要長達兩天的時間，建議才會顯示。</span><span class="sxs-lookup"><span data-stu-id="2315e-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="2315e-140">最後，在您使用小工具來提煉預設的 DLP 原則之後，該構件會從 **首頁** 消失。</span><span class="sxs-lookup"><span data-stu-id="2315e-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

