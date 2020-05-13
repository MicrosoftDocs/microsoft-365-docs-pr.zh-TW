---
title: 在獨立 EOP 中查看系統管理員審核記錄
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 系統管理員可以瞭解如何在獨立 Exchange Online Protection （EOP）中查看及搜尋管理審核記錄。
ms.openlocfilehash: 3aedebc97ccd32c1641510017a276ddbe4770633
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208473"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="69d7d-103">在獨立 EOP 中查看系統管理員審核記錄</span><span class="sxs-lookup"><span data-stu-id="69d7d-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="69d7d-104">在沒有 Exchange Online 信箱的獨立 Exchange Online Protection （EOP）組織中，您可以使用 Exchange 系統管理中心（EAC）或獨立的 EOP PowerShell，在系統管理員審核記錄中搜尋並查看專案。</span><span class="sxs-lookup"><span data-stu-id="69d7d-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="69d7d-105">系統管理員審核記錄會根據獨立 EOP PowerShell Cmdlet，記錄由系統管理員及已獲指派系統管理許可權之使用者所執行的特定動作。</span><span class="sxs-lookup"><span data-stu-id="69d7d-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="69d7d-106">系統管理員審核記錄中的專案會提供您執行的指令程式、所使用的參數、使用 Cmdlet 的執行者，以及受影響物件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="69d7d-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
> <ul><li><span data-ttu-id="69d7d-107">系統管理員審核記錄預設為啟用，您無法停用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span></li><li><span data-ttu-id="69d7d-108">系統管理員審核記錄不會根據以**Get**、 **Search**或**Test**動詞開頭的指令程式，記錄動作。</span><span class="sxs-lookup"><span data-stu-id="69d7d-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span></li><li><span data-ttu-id="69d7d-109">稽核記錄項目會保留 90 天的時間。</span><span class="sxs-lookup"><span data-stu-id="69d7d-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="69d7d-110">當專案超過90天時，它會被刪除</span><span class="sxs-lookup"><span data-stu-id="69d7d-110">When an entry is older than 90 days, it's deleted</span></span></li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="69d7d-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="69d7d-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="69d7d-112">若要開啟 Exchange 系統管理中心，請參閱[exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="69d7d-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="69d7d-113">若要連線至獨立 EOP PowerShell，請參閱[connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="69d7d-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="69d7d-114">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="69d7d-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="69d7d-115">具體說來，您需要 ComplianceManagement 審核記錄檔或 View-Only 的「審核記錄」角色，其預設會指派給、OrganizationManagement （全域管理員）和 SecurityAdministrator 角色群組。</span><span class="sxs-lookup"><span data-stu-id="69d7d-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="69d7d-116">如需詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)和[使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="69d7d-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="69d7d-117">如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="69d7d-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="69d7d-118">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="69d7d-118">Having problems?</span></span> <span data-ttu-id="69d7d-119">在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="69d7d-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="69d7d-120">使用 EAC 來查看系統管理員審核記錄檔</span><span class="sxs-lookup"><span data-stu-id="69d7d-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="69d7d-121">在 EAC 中，移至 [**規範管理**] [ \> **審計**]，然後選擇 [**執行系統管理員審計記錄報告**]。</span><span class="sxs-lookup"><span data-stu-id="69d7d-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="69d7d-122">在開啟的 [**搜尋系統管理員角色群組變更**] 頁面上，選擇 [**開始日期**] 和 [**結束日期**] （預設範圍是過去兩周），然後選擇 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="69d7d-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="69d7d-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span><span class="sxs-lookup"><span data-stu-id="69d7d-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="69d7d-124">**日期**：設定變更的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="69d7d-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="69d7d-125">日期和時間會以格林威治標準時間 (UTC) 格式儲存。</span><span class="sxs-lookup"><span data-stu-id="69d7d-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="69d7d-126">**Cmdlet**：用來變更設定之 Cmdlet 的名稱。</span><span class="sxs-lookup"><span data-stu-id="69d7d-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="69d7d-127">**User**：變更設定之使用者的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="69d7d-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="69d7d-p107">可在多個頁面上顯示最多 5000 個項目。如果需要縮小搜尋結果，請指定較小的日期範圍。如果您選取個別的搜尋結果，下列其他資訊會顯示在詳細資料窗格中：</span><span class="sxs-lookup"><span data-stu-id="69d7d-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="69d7d-131">**已修改物件**： Cmdlet 所修改的物件。</span><span class="sxs-lookup"><span data-stu-id="69d7d-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="69d7d-132">**Parameters （參數： Value）**：使用的 Cmdlet 參數，以及使用參數指定的任何值。</span><span class="sxs-lookup"><span data-stu-id="69d7d-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="69d7d-133">如果您要列印特定的稽核記錄項目，請選擇詳細資料窗格中的 [ **列印**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="69d7d-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="69d7d-134">使用獨立 EOP PowerShell 來查看系統管理員審核記錄檔</span><span class="sxs-lookup"><span data-stu-id="69d7d-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="69d7d-135">您可以使用獨立 EOP PowerShell 來搜尋符合您指定之準則的審計記錄專案。</span><span class="sxs-lookup"><span data-stu-id="69d7d-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="69d7d-136">請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="69d7d-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="69d7d-137">**附註**：</span><span class="sxs-lookup"><span data-stu-id="69d7d-137">**Notes**:</span></span>

- <span data-ttu-id="69d7d-138">您只能將_Parameters_參數與_Cmdlet_參數搭配使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="69d7d-139">_ObjectIds_參數會依 Cmdlet 所修改的物件來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="69d7d-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="69d7d-140">有效的值取決於物件在審計記錄中的表示方式。</span><span class="sxs-lookup"><span data-stu-id="69d7d-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="69d7d-141">例如：</span><span class="sxs-lookup"><span data-stu-id="69d7d-141">For example:</span></span>

  - <span data-ttu-id="69d7d-142">名稱</span><span class="sxs-lookup"><span data-stu-id="69d7d-142">Name</span></span>
  - <span data-ttu-id="69d7d-143">正常化辨別名稱（例如，contoso.com/Users/Akia Al Zuhairi）</span><span class="sxs-lookup"><span data-stu-id="69d7d-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="69d7d-144">您可能需要在此 Cmdlet 上使用其他篩選參數，以縮小結果，並識別您感興趣的物件類型。</span><span class="sxs-lookup"><span data-stu-id="69d7d-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="69d7d-145">_UserIds_參數會依進行變更的使用者（執行 Cmdlet 的執行者）來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="69d7d-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="69d7d-146">針對_StartDate_和_EndDate_參數，如果您指定的日期/時間值不含時區，則值為 [世界時（UTC）]。</span><span class="sxs-lookup"><span data-stu-id="69d7d-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="69d7d-147">若要指定這個參數的日期/時間值，請使用下列其中一個選項︰</span><span class="sxs-lookup"><span data-stu-id="69d7d-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="69d7d-148">指定 UTC 的日期/時間值：例如，"2016-05-06 14:30:00z"。</span><span class="sxs-lookup"><span data-stu-id="69d7d-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="69d7d-149">指定 [日期/時間] 值做為公式，以將您的本機時區中的日期/時間轉換成 UTC：例如， `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="69d7d-150">如需詳細資訊，請參閱 [Get-Date](https://go.microsoft.com/fwlink/p/?LinkID=113313)。</span><span class="sxs-lookup"><span data-stu-id="69d7d-150">For more information, see [Get-Date](https://go.microsoft.com/fwlink/p/?LinkID=113313).</span></span>

- <span data-ttu-id="69d7d-151">根據預設，Cmdlet 會傳回最多1000個記錄專案。</span><span class="sxs-lookup"><span data-stu-id="69d7d-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="69d7d-152">使用_ResultSize_參數可指定最多250000個記錄專案。</span><span class="sxs-lookup"><span data-stu-id="69d7d-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="69d7d-153">或者，使用值傳回 `Unlimited` 所有專案。</span><span class="sxs-lookup"><span data-stu-id="69d7d-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="69d7d-154">此範例使用下列準則，執行所有稽核記錄項目的搜尋：</span><span class="sxs-lookup"><span data-stu-id="69d7d-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="69d7d-155">**開始日期**：2019年8月4日</span><span class="sxs-lookup"><span data-stu-id="69d7d-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="69d7d-156">**結束日期**：2019年10月3日</span><span class="sxs-lookup"><span data-stu-id="69d7d-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="69d7d-157">**Cmdlet**： Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="69d7d-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="69d7d-158">如需詳細的語法及參數資訊，請參閱 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog)。</span><span class="sxs-lookup"><span data-stu-id="69d7d-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="69d7d-159">檢視稽核記錄項目的詳細資料</span><span class="sxs-lookup"><span data-stu-id="69d7d-159">View details of audit log entries</span></span>

<span data-ttu-id="69d7d-160">**Search-AdminAuditLog** Cmdlet 會傳回本主題稍後的「[審核記錄內容](#audit-log-contents)」區段中所述的欄位。</span><span class="sxs-lookup"><span data-stu-id="69d7d-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="69d7d-161">由指令程式傳回的欄位、兩個欄位**CmdletParameters**和**ModifiedProperties**，包含預設不會傳回的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="69d7d-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="69d7d-162">若要檢視 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="69d7d-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="69d7d-163">決定您要搜尋的準則、執行 **Search-AdminAuditLog** 指令程式，然後使用下列命令將結果儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="69d7d-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="69d7d-164">每個審計記錄專案都是以陣列元素形式儲存在變數中 `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="69d7d-165">您可以指定陣列項目索引來選取陣列元素。</span><span class="sxs-lookup"><span data-stu-id="69d7d-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="69d7d-166">陣列元素索引從零 (0) 開始，表示第一個陣列元素。</span><span class="sxs-lookup"><span data-stu-id="69d7d-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="69d7d-167">例如，若要擷取第 5 個陣列元素，其索引為 4，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="69d7d-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="69d7d-p115">上一個命令會傳回儲存在陣列元素 4 中的記錄項目。若要查看此記錄項目的 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="69d7d-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="69d7d-170">若要檢視另一個記錄項目的 **CmdletParameters** 或 **ModifiedParameters** 欄位，請變更陣列元素索引。</span><span class="sxs-lookup"><span data-stu-id="69d7d-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="69d7d-171">稽核記錄內容</span><span class="sxs-lookup"><span data-stu-id="69d7d-171">Audit log contents</span></span>

<span data-ttu-id="69d7d-172">每個審計記錄專案都包含下表所述的資訊。</span><span class="sxs-lookup"><span data-stu-id="69d7d-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="69d7d-173">審核記錄檔包含一或多個審計記錄專案。</span><span class="sxs-lookup"><span data-stu-id="69d7d-173">The audit log contains one or more audit log entries.</span></span>

|||
|---|---|
|<span data-ttu-id="69d7d-174">**Field**</span><span class="sxs-lookup"><span data-stu-id="69d7d-174">**Field**</span></span>|<span data-ttu-id="69d7d-175">**描述**</span><span class="sxs-lookup"><span data-stu-id="69d7d-175">**Description**</span></span>|
|`RunspaceId`|<span data-ttu-id="69d7d-176">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="69d7d-177">此欄位包含的物件是由欄位中指定的 Cmdlet 所修改 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="69d7d-178">此欄位包含使用者在欄位中執行的 Cmdlet 名稱 `Caller` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="69d7d-179">此欄位包含在執列欄位中的 Cmdlet 時所指定的參數 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="69d7d-180">此外，在此欄位中（但在預設輸出中看不到）是以參數指定的值（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="69d7d-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="69d7d-181">此欄位包含在欄位中的物件上修改的屬性 `ObjectModified` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="69d7d-182">此欄位也儲存在此欄位中，但在預設輸出中不會顯示，也就是舊的屬性值及已儲存的新值。</span><span class="sxs-lookup"><span data-stu-id="69d7d-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="69d7d-183">此欄位包含在欄位中執行 Cmdlet 之使用者的使用者帳戶 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="69d7d-184">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="69d7d-185">此欄位會指定是否已成功執列欄位中的 Cmdlet `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="69d7d-186">其值為 `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="69d7d-187">此欄位包含當欄位中的 Cmdlet 未能成功完成時所產生的錯誤訊息 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="69d7d-188">此欄位包含執列欄位中的指令程式的日期和時間 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="69d7d-189">日期和時間會以格林威治標準時間 (UTC) 格式儲存。</span><span class="sxs-lookup"><span data-stu-id="69d7d-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="69d7d-190">此欄位會指出執列欄位中所指定之指令程式的伺服器 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="69d7d-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="69d7d-191">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="69d7d-192">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="69d7d-193">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="69d7d-194">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="69d7d-195">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="69d7d-196">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="69d7d-197">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="69d7d-197">This field is used internally by EOP.</span></span>|
|
