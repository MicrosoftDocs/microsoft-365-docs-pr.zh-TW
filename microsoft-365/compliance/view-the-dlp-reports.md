---
title: 檢視資料外洩防護報告
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: 使用 Office 365 中的 DLP 報告，以查看 DLP 原則相符、覆寫或誤報的數目，以及它們是隨時間向上或向下移動。
ms.openlocfilehash: 1ddcd60dc9314779ade2f7ceae02d336f902e483
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818993"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="545de-103">檢視資料外洩防護報告</span><span class="sxs-lookup"><span data-stu-id="545de-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="545de-104">在您建立資料遺失防護（DLP）原則之後，您可能會想要驗證他們的運作是否正常，並協助您保持相容。</span><span class="sxs-lookup"><span data-stu-id="545de-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="545de-105">透過安全性與 &amp; 合規性中心的 DLP 報告，您可以快速查看：</span><span class="sxs-lookup"><span data-stu-id="545de-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="545de-106">**DLP 原則相符**專案此報告顯示一段時間的 DLP 原則相符計數。</span><span class="sxs-lookup"><span data-stu-id="545de-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="545de-107">您可以依日期、位置、原則或動作來篩選報告。</span><span class="sxs-lookup"><span data-stu-id="545de-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="545de-108">您可以使用此報告來：</span><span class="sxs-lookup"><span data-stu-id="545de-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="545de-109">在測試模式中執行時，請調整或提煉您的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="545de-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="545de-110">您可以查看符合內容的特定規則。</span><span class="sxs-lookup"><span data-stu-id="545de-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="545de-111">將重點放在特定時段，以了解尖峰和趨勢的原因。</span><span class="sxs-lookup"><span data-stu-id="545de-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="545de-112">探索違反貴組織 DLP 原則的商務程序。</span><span class="sxs-lookup"><span data-stu-id="545de-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="545de-113">查看內容所套用的動作，以瞭解 DLP 原則的任何業務影響。</span><span class="sxs-lookup"><span data-stu-id="545de-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="545de-114">顯示該原則的任何符合項目來驗證是否符合特定 DLP 原則的規範。</span><span class="sxs-lookup"><span data-stu-id="545de-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="545de-115">查看主要使用者的清單，並重複參與組織中事件的使用者。</span><span class="sxs-lookup"><span data-stu-id="545de-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="545de-116">在您的組織中查看最上層的敏感資訊類型清單。</span><span class="sxs-lookup"><span data-stu-id="545de-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="545de-117">**DLP 事件**此報告也顯示一段時間的原則相符專案，就像原則符合報表。</span><span class="sxs-lookup"><span data-stu-id="545de-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="545de-118">不過，原則符合報表會顯示規則層級的相符專案;例如，如果電子郵件符合三個不同的規則，則原則符合報表會顯示三個不同的行專案。</span><span class="sxs-lookup"><span data-stu-id="545de-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="545de-119">相反地，附隨報告會顯示專案層級的相符專案;例如，如果電子郵件符合三個不同的規則，則附隨報告會顯示該部分內容的單一行專案。</span><span class="sxs-lookup"><span data-stu-id="545de-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="545de-120">由於報告計數的匯總方式不同，因此原則比對報告更適合識別與特定規則的相符專案，以及微調 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="545de-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="545de-121">當您識別 DLP 原則有問題的特定內容片段時，附隨報告會比較好。</span><span class="sxs-lookup"><span data-stu-id="545de-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="545de-122">**DLP 錯誤正值和 overrides**如果您的 DLP 原則允許使用者覆寫它或報告誤報，此報告會顯示一段時間的這類實例計數。</span><span class="sxs-lookup"><span data-stu-id="545de-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="545de-123">您可以依日期、位置或原則篩選報表。</span><span class="sxs-lookup"><span data-stu-id="545de-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="545de-124">您可以使用此報告來：</span><span class="sxs-lookup"><span data-stu-id="545de-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="545de-125">查看哪些原則會產生大量的誤報，以調整或提煉您的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="545de-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="545de-126">透過覆寫原則，查看使用者解析原則提示時所提交的理由。</span><span class="sxs-lookup"><span data-stu-id="545de-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="545de-127">透過產生大量的使用者覆寫，探索 DLP 原則與有效商務程式的衝突。</span><span class="sxs-lookup"><span data-stu-id="545de-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="545de-128">所有 DLP 報告都可顯示最近四個月的時間範圍內的資料。</span><span class="sxs-lookup"><span data-stu-id="545de-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="545de-129">最新的資料可能需要長達24小時才會顯示在報告中。</span><span class="sxs-lookup"><span data-stu-id="545de-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="545de-130">您可以在安全性與 &amp; 合規性中心 \> **報告** \> **儀表板**中找到這些報告。</span><span class="sxs-lookup"><span data-stu-id="545de-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP 原則符合報告](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="545de-132">查看使用者為覆寫而提交的理由</span><span class="sxs-lookup"><span data-stu-id="545de-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="545de-133">如果您的 DLP 原則允許使用者覆寫該原則，您可以使用 [誤報] 和 [覆寫] 報告，以查看原則提示中使用者所提交的文字。</span><span class="sxs-lookup"><span data-stu-id="545de-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![DLP false 肯定和覆寫報告詳細資料中的調整欄位](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="545de-135">對真知灼見和建議採取動作</span><span class="sxs-lookup"><span data-stu-id="545de-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="545de-136">報告可顯示洞察力和建議，您可以在其中按一下紅色的警告圖示，以查看有關潛在問題的詳細資訊，並採取可能的補救措施。</span><span class="sxs-lookup"><span data-stu-id="545de-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![按一下 insights 圖示，以查看要採取的詳細資料和動作](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="545de-138">DLP 報告的許可權</span><span class="sxs-lookup"><span data-stu-id="545de-138">Permissions for DLP reports</span></span>

<span data-ttu-id="545de-139">若要在安全性 & 規範中心中查看 DLP 報告，您必須被指派下列專案：</span><span class="sxs-lookup"><span data-stu-id="545de-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="545de-140">Exchange 系統管理中心中的**安全性讀取器**角色。</span><span class="sxs-lookup"><span data-stu-id="545de-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="545de-141">根據預設，此角色會指派給 Exchange 系統管理中心內的「組織管理」和「安全性讀者」角色群組。</span><span class="sxs-lookup"><span data-stu-id="545de-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="545de-142">在安全性 & 規範中心**VIEW-ONLY DLP 合規性管理**角色。</span><span class="sxs-lookup"><span data-stu-id="545de-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="545de-143">根據預設，此角色會指派給安全性 & 合規性中心內的合規性管理員、組織管理、安全性管理員及安全性讀者角色群組。</span><span class="sxs-lookup"><span data-stu-id="545de-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="545de-144">在 Exchange 系統管理中心中**View-Only**收件者角色。</span><span class="sxs-lookup"><span data-stu-id="545de-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="545de-145">根據預設，此角色會指派給 Exchange 系統管理中心中的規範管理、組織管理和 View-Only 組織管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="545de-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="545de-146">尋找 DLP 報告的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="545de-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="545de-147">若要對安全性與合規性中心使用大部分 Cmdlet，您必須：</span><span class="sxs-lookup"><span data-stu-id="545de-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="545de-148">&amp;使用遠端 PowerShell 連接至安全規範中心</span><span class="sxs-lookup"><span data-stu-id="545de-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="545de-149">使用這些安全性與[ &amp; 合規性中心 Cmdlet](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)中的任何一個</span><span class="sxs-lookup"><span data-stu-id="545de-149">Use any of these [Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="545de-150">不過，DLP 報告需要從整個 Office 365 擷取資料，包含 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="545de-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="545de-151">基於這個理由，在 Exchange Online Powershell 中可以使用 DLP 報告的 Cmdlet，而不是在安全性與 &amp; 合規性中心 powershell 中。</span><span class="sxs-lookup"><span data-stu-id="545de-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="545de-152">因此，若要為 DLP 報告使用 Cmdlet，您需要︰</span><span class="sxs-lookup"><span data-stu-id="545de-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="545de-153">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="545de-153">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="545de-154">為 DLP 報告使用下列任何 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="545de-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="545de-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="545de-155">Get-DlpDetectionsReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="545de-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="545de-156">Get-DlpDetailReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

