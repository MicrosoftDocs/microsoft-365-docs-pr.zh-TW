---
title: 檢視資料外洩防護報告
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
description: 使用 Office 365 中的 DLP 報告，您可以快速檢視 DLP 原則相符項目、 覆寫或誤判; 的數請參閱是否它們在一段時間; 趨勢向上或向下以不同方式; 篩選報表然後選取圖形上線條上的一點檢視其他詳細資料。
ms.openlocfilehash: 94569ef24814204263820fb5fdb7a8cb72da20e4
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38685447"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="00088-103">檢視資料外洩防護報告</span><span class="sxs-lookup"><span data-stu-id="00088-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="00088-104">您可以建立您的資料遺失防護 (DLP) 原則之後，您會想確認他們正在為您預期，並協助您符合規範。</span><span class="sxs-lookup"><span data-stu-id="00088-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="00088-105">使用 DLP 報告中 Office 365 安全性&amp;合規性中心，您可以快速檢視：</span><span class="sxs-lookup"><span data-stu-id="00088-105">With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="00088-106">**DLP 原則比對**這份報告顯示一段時間的 DLP 原則相符項目計數。</span><span class="sxs-lookup"><span data-stu-id="00088-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="00088-107">您可以依日期、 位置、 原則或動作篩選報告。</span><span class="sxs-lookup"><span data-stu-id="00088-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="00088-108">您可以使用此報告來：</span><span class="sxs-lookup"><span data-stu-id="00088-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="00088-109">調整或調整您的 DLP 原則，當您在測試模式中執行。</span><span class="sxs-lookup"><span data-stu-id="00088-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="00088-110">您可以檢視符合內容的特定規則。</span><span class="sxs-lookup"><span data-stu-id="00088-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="00088-111">將重點放在特定時段，以了解尖峰和趨勢的原因。</span><span class="sxs-lookup"><span data-stu-id="00088-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="00088-112">探索違反貴組織的 DLP 原則的商務程序。</span><span class="sxs-lookup"><span data-stu-id="00088-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="00088-113">藉由查看哪些動作會套用到內容，了解 DLP 原則的任何業務影響。</span><span class="sxs-lookup"><span data-stu-id="00088-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="00088-114">顯示該原則的任何符合項目來驗證是否符合特定 DLP 原則的規範。</span><span class="sxs-lookup"><span data-stu-id="00088-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="00088-115">檢視的主要使用者清單，然後重複使用者參與您組織中的事件。</span><span class="sxs-lookup"><span data-stu-id="00088-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="00088-116">在您的組織中檢視上方的敏感資訊類型清單。</span><span class="sxs-lookup"><span data-stu-id="00088-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="00088-117">**DLP 事件**這份報告也會顯示原則相符項目經過一段時間，如原則相符項目報告。</span><span class="sxs-lookup"><span data-stu-id="00088-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="00088-118">不過，此原則會比對報表顯示相符項目層級規則;例如，若一封電子郵件符合三個不同的規則，原則會比對報表顯示三個不同列項目。</span><span class="sxs-lookup"><span data-stu-id="00088-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="00088-119">相反地，事件報告 」 可顯示相符項目層級項目;例如，若一封電子郵件符合三個不同的規則，事件報告顯示該份內容單一列項目。</span><span class="sxs-lookup"><span data-stu-id="00088-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="00088-120">因為報告計數彙總不同，原則相符項目報告是用來識別與特定規則的相符項目及正常調整 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="00088-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="00088-121">事件報告是內容的較適合用來識別會有問題的 DLP 原則的特定部分。</span><span class="sxs-lookup"><span data-stu-id="00088-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="00088-122">**DLP 誤判和覆寫**如果您的 DLP 原則允許使用者覆寫它，或回報] 誤判，這份報告顯示這類的執行個體計數一段時間。</span><span class="sxs-lookup"><span data-stu-id="00088-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="00088-123">您可以依日期、 位置或原則篩選報告。</span><span class="sxs-lookup"><span data-stu-id="00088-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="00088-124">您可以使用此報告來：</span><span class="sxs-lookup"><span data-stu-id="00088-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="00088-125">調整或調整您的 DLP 原則所看見的原則可能會形成誤判較大數目。</span><span class="sxs-lookup"><span data-stu-id="00088-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="00088-126">檢視他們所覆寫原則以解析原則秘訣時，使用者所提交的理由。</span><span class="sxs-lookup"><span data-stu-id="00088-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="00088-127">探索其中 DLP 原則衝突有效商務程序所產生大量的使用者會覆寫。</span><span class="sxs-lookup"><span data-stu-id="00088-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="00088-128">所有的 DLP 報告可以顯示最近的四個月的時間期間內的資料。</span><span class="sxs-lookup"><span data-stu-id="00088-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="00088-129">最新的資料可能需要最多 24 小時才會出現在報告。</span><span class="sxs-lookup"><span data-stu-id="00088-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="00088-130">您可以在安全性中找到這些報告&amp;合規性中心\>**報表** \> **儀表板**。</span><span class="sxs-lookup"><span data-stu-id="00088-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP 原則相符項目報告](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="00088-132">檢視覆寫使用者所提交的理由</span><span class="sxs-lookup"><span data-stu-id="00088-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="00088-133">如果您的 DLP 原則允許使用者覆寫它，您可以使用誤判和覆寫報告] 來檢視提交的原則提示的文字。</span><span class="sxs-lookup"><span data-stu-id="00088-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![理由欄位中的 DLP 誤判和覆寫報告詳細資料](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="00088-135">採取動作的見解和建議</span><span class="sxs-lookup"><span data-stu-id="00088-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="00088-136">報告可以顯示見解和建議您將可以按一下 [請參閱潛在問題的詳細資料，並採取可能的補救措施的紅色警告圖示。</span><span class="sxs-lookup"><span data-stu-id="00088-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![按一下以查看詳細資料，要採取的動作觀點圖示](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="00088-138">DLP 報告的權限</span><span class="sxs-lookup"><span data-stu-id="00088-138">Permissions for DLP reports</span></span>

<span data-ttu-id="00088-139">若要檢視 DLP 報告中安全性 & 合規性中心，您必須被指派:</span><span class="sxs-lookup"><span data-stu-id="00088-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="00088-140">在 Exchange 系統管理中心中的**安全性讀取者**角色。</span><span class="sxs-lookup"><span data-stu-id="00088-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="00088-141">根據預設，此角色被指派給組織管理和安全性助讀程式在 Exchange 系統管理中心中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="00088-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="00088-142">安全性 & 合規性中心中的**僅限檢視 DLP 符合性管理**角色。</span><span class="sxs-lookup"><span data-stu-id="00088-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="00088-143">根據預設，此角色被指派給安全性 & 合規性中心的符合性系統管理員、 組織管理、 安全性系統管理員和安全性讀取者角色群組。</span><span class="sxs-lookup"><span data-stu-id="00088-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="00088-144">在 Exchange 系統管理中心**僅檢視收件者**角色。</span><span class="sxs-lookup"><span data-stu-id="00088-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="00088-145">根據預設，此角色被指派給在 Exchange 系統管理中心相符性管理、 組織管理和 View-Only Organization Management 角色群組。</span><span class="sxs-lookup"><span data-stu-id="00088-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="00088-146">尋找 DLP 報告的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="00088-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="00088-147">若要使用之 cmdlet 的大部分 security&amp;合規性中心，您需要：</span><span class="sxs-lookup"><span data-stu-id="00088-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="00088-148">使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="00088-148">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="00088-149">使用下列任何一這些[Office 365 安全性&amp;合規性中心 cmdlet](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="00088-149">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="00088-150">不過，DLP 報告需要提取資料從 Office 365，包括 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="00088-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="00088-151">基於這個理由，DLP 報告指令程式可供 Exchange Online Powershell 中，而不是以安全性&amp;合規性中心 Powershell。</span><span class="sxs-lookup"><span data-stu-id="00088-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="00088-152">因此，若要使用 cmdlet 的 DLP 報告，您必須：</span><span class="sxs-lookup"><span data-stu-id="00088-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="00088-153">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="00088-153">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="00088-154">使用這些 cmdlet 的任何 DLP 報告：</span><span class="sxs-lookup"><span data-stu-id="00088-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="00088-155">Get-dlpdetectionsreport</span><span class="sxs-lookup"><span data-stu-id="00088-155">Get-DlpDetectionsReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="00088-156">Get-dlpdetailreport</span><span class="sxs-lookup"><span data-stu-id="00088-156">Get-DlpDetailReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

