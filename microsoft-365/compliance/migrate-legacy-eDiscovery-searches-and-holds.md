---
title: 將舊版 eDiscovery 搜尋和保留遷移至 Microsoft 365 規範中心
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ef5562aa6f5c7519d19452100b55dd4bc30d4126
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926321"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="1ded2-102">將舊版 eDiscovery 搜尋和保留遷移至 Microsoft 365 規範中心</span><span class="sxs-lookup"><span data-stu-id="1ded2-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="1ded2-103">Microsoft 365 合規性中心提供 eDiscovery 使用的改善體驗，包括：更高的可靠性、更好的效能，以及許多針對 eDiscovery 工作流程量身定做的功能，包括案例以查看內容和分析，以協助挑選資料進行審核，例如接近重複的群組、電子郵件執行緒、主題分析和預測編碼。</span><span class="sxs-lookup"><span data-stu-id="1ded2-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="1ded2-104">為了協助客戶利用新的和改善的功能，本文提供如何將 In-Place eDiscovery 搜尋和保留從 Exchange 系統管理中心遷移至 Microsoft 365 規範中心的基本指導方針。</span><span class="sxs-lookup"><span data-stu-id="1ded2-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="1ded2-105">因為有許多不同的案例，本文提供將搜尋和保留轉換至 Microsoft 365 規範中心中核心 eDiscovery 案例的一般指導方針。</span><span class="sxs-lookup"><span data-stu-id="1ded2-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1ded2-106">使用 eDiscovery 案例不一定是必要的，但是會讓您指派許可權來控制哪些人員可以存取您組織中的 eDiscovery 案例，以增加額外的安全性層級。</span><span class="sxs-lookup"><span data-stu-id="1ded2-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1ded2-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="1ded2-107">Before you begin</span></span>

- <span data-ttu-id="1ded2-108">您必須是 Security & 合規性中心內 eDiscovery 管理員角色群組的成員，才可執行本文所述的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="1ded2-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="1ded2-109">您也必須是 Exchange 系統管理中心內「探索管理」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1ded2-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="1ded2-110">本文提供如何建立 eDiscovery 暫止功能的指導方針。</span><span class="sxs-lookup"><span data-stu-id="1ded2-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="1ded2-111">保留原則會透過非同步處理常式套用至信箱。</span><span class="sxs-lookup"><span data-stu-id="1ded2-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="1ded2-112">建立 eDiscovery 暫止功能時，您必須同時建立 CaseHoldPolicy 和 New-caseholdrule，否則不會建立保留，也不會將內容位置置於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="1ded2-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="1ded2-113">步驟1：連線至 Exchange Online PowerShell 及安全性 & 規範中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ded2-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="1ded2-114">第一步是連線至 Exchange Online PowerShell 及安全性 & 規範中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1ded2-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="1ded2-115">您可以複製下列腳本，將其貼到 PowerShell 視窗，然後執行它。</span><span class="sxs-lookup"><span data-stu-id="1ded2-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="1ded2-116">系統會提示您輸入您要連線之組織的認證。</span><span class="sxs-lookup"><span data-stu-id="1ded2-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="1ded2-117">在此 PowerShell 會話中，您必須執行下列步驟中的命令。</span><span class="sxs-lookup"><span data-stu-id="1ded2-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="1ded2-118">步驟2：使用 Get-MailboxSearch 取得 In-Place eDiscovery 搜尋的清單</span><span class="sxs-lookup"><span data-stu-id="1ded2-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="1ded2-119">驗證之後，您可以執行 **Get-MailboxSearch** Cmdlet，以取得 In-Place eDiscovery 搜尋的清單。</span><span class="sxs-lookup"><span data-stu-id="1ded2-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="1ded2-120">將下列命令複製並貼到 PowerShell，然後執行它。</span><span class="sxs-lookup"><span data-stu-id="1ded2-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="1ded2-121">會列出搜尋的清單，以及其名稱及任何 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="1ded2-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="1ded2-122">Cmdlet 輸出會類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="1ded2-122">The cmdlet output will be similar to the following:</span></span>

![PowerShell 範例 Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="1ded2-124">步驟3：取得 In-Place eDiscovery 搜尋的相關資訊，以及您要遷移的 In-Place 封存</span><span class="sxs-lookup"><span data-stu-id="1ded2-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="1ded2-125">同樣，您會使用 **Get-MailboxSearch** Cmdlet，但這次是取得搜尋的屬性。</span><span class="sxs-lookup"><span data-stu-id="1ded2-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="1ded2-126">您可以將這些屬性儲存在變數中供日後使用。</span><span class="sxs-lookup"><span data-stu-id="1ded2-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="1ded2-127">下列範例會將 **Get-MailboxSearch** Cmdlet 的結果儲存在變數中，然後顯示該搜尋的屬性。</span><span class="sxs-lookup"><span data-stu-id="1ded2-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="1ded2-128">這兩個命令的輸出會類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="1ded2-128">The output of these two commands will be similar to the following:</span></span>

![使用 Get-MailboxSearch 個別搜尋 PowerShell 輸出的範例](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="1ded2-130">在此範例中 In-Place 保留期間 (*ItemHoldPeriod：無限制*) 。</span><span class="sxs-lookup"><span data-stu-id="1ded2-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="1ded2-131">這是 eDiscovery 和法律調查案例的常見功能。</span><span class="sxs-lookup"><span data-stu-id="1ded2-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="1ded2-132">如果保留期間的值與無限期不同，原因可能是因為保留是用於保留案例中的內容。</span><span class="sxs-lookup"><span data-stu-id="1ded2-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="1ded2-133">建議您使用 [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) 和 [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) 保留內容，而不是在安全性 & 規範中心中使用 eDiscovery Cmdlet PowerShell 進行保留案例。</span><span class="sxs-lookup"><span data-stu-id="1ded2-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="1ded2-134">使用這些 Cmdlet 的結果會類似使用 **New-CaseHoldPolicy** 和 **New-CaseHoldRule**，但您可以指定保留期間和保留動作，例如在保留期間到期時刪除內容。</span><span class="sxs-lookup"><span data-stu-id="1ded2-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="1ded2-135">此外，使用保留指令程式不需要您將保留封存與 eDiscovery 案例產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1ded2-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="1ded2-136">步驟4：在 Microsoft 365 規範中心建立案例</span><span class="sxs-lookup"><span data-stu-id="1ded2-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="1ded2-137">若要建立 eDiscovery 保留，您必須建立 eDiscovery 案例以關聯保留。</span><span class="sxs-lookup"><span data-stu-id="1ded2-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="1ded2-138">下列範例會使用您選擇的名稱建立 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="1ded2-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="1ded2-139">我們會將新案例的屬性儲存在變數中供日後使用。</span><span class="sxs-lookup"><span data-stu-id="1ded2-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="1ded2-140">`$case | FL`您可以在建立案例後執行命令，以查看這些屬性。</span><span class="sxs-lookup"><span data-stu-id="1ded2-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![執行 New-ComplianceCase 命令的範例](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="1ded2-142">步驟5：建立電子檔保存暫止</span><span class="sxs-lookup"><span data-stu-id="1ded2-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="1ded2-143">在建立案例之後，您可以建立保留，並將它與您在上一個步驟中建立的情況關聯。</span><span class="sxs-lookup"><span data-stu-id="1ded2-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="1ded2-144">請務必記住，您必須建立案例保留原則及案例保留規則。</span><span class="sxs-lookup"><span data-stu-id="1ded2-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="1ded2-145">如果您建立案例保留原則之後未建立案例保留規則，將不會建立 eDiscovery 保留，也不會保留任何內容。</span><span class="sxs-lookup"><span data-stu-id="1ded2-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="1ded2-146">執行下列命令，以重新建立您要遷移的 eDiscovery 保留。</span><span class="sxs-lookup"><span data-stu-id="1ded2-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="1ded2-147">這些範例會使用您要遷移之步驟3中 In-Place 保留的屬性。</span><span class="sxs-lookup"><span data-stu-id="1ded2-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="1ded2-148">第一個命令會建立新的案例保留原則，並將屬性儲存至變數。</span><span class="sxs-lookup"><span data-stu-id="1ded2-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="1ded2-149">第二個命令會建立對應的案例保留規則。</span><span class="sxs-lookup"><span data-stu-id="1ded2-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![使用 NewCaseHoldPolicy 和 NewCaseHoldRule Cmdlet 的範例](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="1ded2-151">步驟6：確認 eDiscovery 暫止</span><span class="sxs-lookup"><span data-stu-id="1ded2-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="1ded2-152">若要確認建立保留沒有問題，請確認已成功保留分配狀態。</span><span class="sxs-lookup"><span data-stu-id="1ded2-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="1ded2-153">「分配」表示已將保留套用至上一個步驟中 *ExchangeLocation* 參數所指定的所有內容位置。</span><span class="sxs-lookup"><span data-stu-id="1ded2-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="1ded2-154">若要這麼做，您可以執行 **Get-CaseHoldPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ded2-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="1ded2-155">因為儲存至您在上一個步驟中建立的 *$policy* 變數的屬性不會在變數中自動更新，所以您需要重新執行 Cmdlet，以確認分配是否成功。</span><span class="sxs-lookup"><span data-stu-id="1ded2-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="1ded2-156">若要成功發佈案例保留原則，可能需要5分鐘到24小時的時間。</span><span class="sxs-lookup"><span data-stu-id="1ded2-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="1ded2-157">執行下列命令，確認已成功發佈 eDiscovery 封存。</span><span class="sxs-lookup"><span data-stu-id="1ded2-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="1ded2-158">*DistributionStatus* 屬性的 **Success** 值表示已成功將保留放在內容位置上。</span><span class="sxs-lookup"><span data-stu-id="1ded2-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="1ded2-159">如果分配尚未完成，則會顯示 [ **未決** ] 的值。</span><span class="sxs-lookup"><span data-stu-id="1ded2-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell Get-CaseHoldPolicy 範例](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="1ded2-161">步驟7：建立搜尋</span><span class="sxs-lookup"><span data-stu-id="1ded2-161">Step 7: Create the search</span></span>

<span data-ttu-id="1ded2-162">最後一個步驟是重新建立您在步驟3中識別的搜尋，並將它與案例建立關聯。</span><span class="sxs-lookup"><span data-stu-id="1ded2-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="1ded2-163">在您建立搜尋之後，您可以使用 **Start-ComplianceSearch** Cmdlet 來執行它，或稍後執行它。</span><span class="sxs-lookup"><span data-stu-id="1ded2-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-ComplianceSearch 範例](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="1ded2-165">步驟8：確認案例、保留及搜尋 Microsoft 365 規範中心</span><span class="sxs-lookup"><span data-stu-id="1ded2-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="1ded2-166">若要確定所有專案設定正確，請移至 Microsoft 365 規範中心 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下 [ **EDiscovery > Core**]。</span><span class="sxs-lookup"><span data-stu-id="1ded2-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 規範中心電子檔探索](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="1ded2-168">您在步驟3中建立的案例會列在 **核心 eDiscovery** 頁面上。</span><span class="sxs-lookup"><span data-stu-id="1ded2-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="1ded2-169">開啟案例，然後注意您在 [ **保留** ] 索引標籤的 [步驟 4] 中所建立的保留。您可以按一下 [保留] 以查看詳細資料，包括保留所用的信箱數目及發行狀態。</span><span class="sxs-lookup"><span data-stu-id="1ded2-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![Microsoft 365 規範中心的 eDiscovery 保留](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="1ded2-171">您在步驟7中建立的搜尋列在 eDiscovery 案例的 [搜尋] 索引標籤上的 [ **搜尋** ] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="1ded2-171">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![Microsoft 365 規範中心的 eDiscovery 案例搜尋](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="1ded2-173">如果您遷移的是 In-Place eDiscovery 搜尋，但沒有將其與 eDiscovery 案例產生關聯，它會列在 Microsoft 365 規範中心的 [內容搜尋] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="1ded2-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="1ded2-174">其他資訊</span><span class="sxs-lookup"><span data-stu-id="1ded2-174">More information</span></span>

- <span data-ttu-id="1ded2-175">如需 Exchange 系統管理中心中 In-Place eDiscovery & 保留的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="1ded2-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="1ded2-176">就地電子文件</span><span class="sxs-lookup"><span data-stu-id="1ded2-176">In-Place eDiscovery</span></span>](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="1ded2-177">就地保留與訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="1ded2-177">In-Place Hold and Litigation Hold</span></span>](/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="1ded2-178">如需本文中所用 PowerShell Cmdlet 的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="1ded2-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="1ded2-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="1ded2-179">Get-MailboxSearch</span></span>](/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="1ded2-180">新 Get-compliancecase</span><span class="sxs-lookup"><span data-stu-id="1ded2-180">New-ComplianceCase</span></span>](/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="1ded2-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="1ded2-181">New-CaseHoldPolicy</span></span>](/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="1ded2-182">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="1ded2-182">New-CaseHoldRule</span></span>](/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="1ded2-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="1ded2-183">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="1ded2-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="1ded2-184">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="1ded2-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="1ded2-185">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="1ded2-186">如需 Microsoft 365 規範中心的詳細資訊，請參閱 [microsoft 365 規範中心概述](microsoft-365-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1ded2-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>