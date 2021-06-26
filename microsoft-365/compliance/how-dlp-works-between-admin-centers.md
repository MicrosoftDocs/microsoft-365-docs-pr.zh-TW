---
title: DLP 如何與安全性 & 規範中心 & Exchange 系統管理中心的運作方式
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 瞭解安全性 & 合規性中心中的 dlp 如何使用 dlp 和郵件流程規則 (Exchange 系統管理中心) 的傳輸規則。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d71c45e5483bc73afbe2598415e30b84e97c2539
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149139"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="2e5fb-103">DLP 在 Microsoft 365 規範中心與 Exchange 系統管理中心之間的運作方式</span><span class="sxs-lookup"><span data-stu-id="2e5fb-103">How DLP works between the Microsoft 365 Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="2e5fb-104">在 Microsoft 365 中，您可以在兩個不同的系統管理中心建立「資料遺失防護」 (DLP) 原則：</span><span class="sxs-lookup"><span data-stu-id="2e5fb-104">In Microsoft 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="2e5fb-105">在 **Microsoft 365 規範中心** 中，您可以建立單一 DLP 原則，協助保護 SharePoint、OneDrive、Exchange、Teams 和現在端點裝置中的內容。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-105">In the **Microsoft 365 Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, Teams, and now Endpoint Devices.</span></span> <span data-ttu-id="2e5fb-106">建議您在這裡建立 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-106">We recommend that you create a DLP policy here.</span></span> <span data-ttu-id="2e5fb-107">如需詳細資訊，請參閱 [資料遺失防護參考](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="2e5fb-108">在 **Exchange 系統管理中心**，您可以建立 DLP 原則，以協助只保護 Exchange 中的內容。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="2e5fb-109">這項原則可以使用 Exchange 郵件流程規則 (也稱為傳輸規則) ，因此它具有處理電子郵件時特有的選項。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="2e5fb-110">如需詳細資訊，請參閱[Exchange 系統管理中心的 [DLP](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)]。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="2e5fb-111">在這些系統管理中心建立的 DLP 策略並排運作-本主題說明如何執行。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![安全性與合規性中心及 Exchange 系統管理中心的 DLP 頁面](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="2e5fb-113">安全性 & 規範中心中的 dlp 如何在 Exchange 系統管理中心中使用 dlp 和郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="2e5fb-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="2e5fb-114">在安全性 & 規範中心建立 DLP 原則之後，原則會部署至原則所包含的所有位置。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="2e5fb-115">若原則包括 Exchange Online，該原則會與其同步處理，並以與在 Exchange 系統管理中心中建立的 DLP 原則完全相同的方式執行。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="2e5fb-116">如果您已在 Exchange 系統管理中心建立 DLP 原則，這些原則將繼續與您在安全性 & 規範中心建立之電子郵件的任何原則並排運作。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="2e5fb-117">不過，請注意，在 Exchange 系統管理中心建立的規則具有優先權。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="2e5fb-118">會先處理所有 Exchange 郵件流程規則，然後處理安全性 & 規範中心的 DLP 規則。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="2e5fb-119">這表示：</span><span class="sxs-lookup"><span data-stu-id="2e5fb-119">This means that:</span></span>
  
- <span data-ttu-id="2e5fb-120">Exchange 郵件流程規則封鎖的郵件不會透過安全性 & 規範中心內建立的 DLP 規則進行掃描。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="2e5fb-121">如果 Exchange 郵件流程規則會以一種方式修改郵件，使其符合 Security & 合規性中心的 DLP 原則（例如新增外部使用者），則 DLP 規則會偵測到這種情況，並視需要強制執行原則。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="2e5fb-122">另請注意 Exchange，使用「停止處理」動作的郵件流程規則不會影響在安全性 & 規範中心處理 DLP 規則的處理常式，他們仍會進行處理。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="2e5fb-123">安全性 & 規範中心與 Exchange 系統管理中心的原則提示</span><span class="sxs-lookup"><span data-stu-id="2e5fb-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="2e5fb-124">原則提示可使用 Exchange 系統管理中心中建立的 dlp 原則和郵件流程規則，或是在安全性 & 規範中心內建立的 dlp 原則使用，但不能同時使用這兩者。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="2e5fb-125">這是因為這些原則儲存在不同的位置，但是原則秘訣只能從單一位置進行繪製。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="2e5fb-126">如果您已在 Exchange 系統管理中心中設定原則提示，則在安全性 & 規範中心內設定的任何原則提示，都不會向使用者顯示 Outlook 網頁版和 Outlook 2013 及更新版本，直到您關閉 Exchange 系統管理中心中的秘訣。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="2e5fb-127">這可確保您目前的 Exchange 郵件流程規則將繼續運作，直到您選擇切換到安全性 & 規範中心為止。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="2e5fb-128">請注意，當原則提示只能從單一位置繪製時，系統會永遠傳送電子郵件通知，即使您同時在安全性 & 規範中心和 Exchange 系統管理中心中使用 DLP 原則也是一樣。</span><span class="sxs-lookup"><span data-stu-id="2e5fb-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
