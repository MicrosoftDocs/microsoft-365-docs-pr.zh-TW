---
title: 在獨立版 EOP 中檢視系統管理稽核記錄
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 系統管理員可以瞭解如何在獨立 Exchange Online Protection (EOP) 中查看及搜尋管理審核記錄。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286474"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="7641a-103">在獨立版 EOP 中檢視系統管理稽核記錄</span><span class="sxs-lookup"><span data-stu-id="7641a-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="7641a-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="7641a-104">**Applies to**</span></span>
- [<span data-ttu-id="7641a-105">Exchange Online Protection 獨立</span><span class="sxs-lookup"><span data-stu-id="7641a-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7641a-106">在獨立 Exchange Online Protection (EOP 中) 沒有 Exchange Online 信箱的組織，您可以使用 Exchange 系統管理中心 (EAC) 或獨立 EOP PowerShell，以搜尋並查看系統管理員審核記錄檔中的專案。</span><span class="sxs-lookup"><span data-stu-id="7641a-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="7641a-107">系統管理員審核記錄會根據獨立 EOP PowerShell Cmdlet，記錄由系統管理員及已獲指派系統管理許可權之使用者所執行的特定動作。</span><span class="sxs-lookup"><span data-stu-id="7641a-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="7641a-108">系統管理員審核記錄中的專案會提供您執行的指令程式、所使用的參數、使用 Cmdlet 的執行者，以及受影響物件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7641a-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7641a-109">系統管理員審核記錄預設為啟用，您無法停用。</span><span class="sxs-lookup"><span data-stu-id="7641a-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="7641a-110">系統管理員審核記錄不會根據以 **Get**、 **Search** 或 **Test** 動詞開頭的指令程式，記錄動作。</span><span class="sxs-lookup"><span data-stu-id="7641a-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="7641a-111">稽核記錄項目會保留 90 天的時間。</span><span class="sxs-lookup"><span data-stu-id="7641a-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="7641a-112">當專案超過90天時，它會被刪除</span><span class="sxs-lookup"><span data-stu-id="7641a-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7641a-113">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="7641a-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7641a-114">若要開啟 Exchange 系統管理中心，請參閱 [exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="7641a-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="7641a-115">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7641a-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7641a-116">您必須先在 Exchange Online Protection 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="7641a-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="7641a-117">具體說來，您需要「 **審核記錄** 」或「 **View-Only 審核記錄** 」角色，預設會指派給「 **組織管理**」、「 **合規性管理**」及「 **安全性管理員** 」角色群組。</span><span class="sxs-lookup"><span data-stu-id="7641a-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="7641a-118">如需詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="7641a-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="7641a-119">如需適用于本文中程式的鍵盤快速鍵的詳細資訊，請參閱 exchange [Online 中 exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="7641a-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="7641a-120">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="7641a-120">Having problems?</span></span> <span data-ttu-id="7641a-121">在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="7641a-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="7641a-122">使用 EAC 來查看系統管理員審核記錄檔</span><span class="sxs-lookup"><span data-stu-id="7641a-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="7641a-123">在 EAC 中，移至 [ **規範管理**] [ \> **審計**]，然後選擇 [ **執行系統管理員審計記錄報告**]。</span><span class="sxs-lookup"><span data-stu-id="7641a-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="7641a-124">在開啟的 [ **搜尋系統管理員角色群組變更** ] 頁面上，選擇 [ **開始日期** ] 和 [ **結束日期** ] (預設範圍是過去兩周) ，然後選擇 [ **搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="7641a-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="7641a-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span><span class="sxs-lookup"><span data-stu-id="7641a-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="7641a-126">**日期**：設定變更的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="7641a-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="7641a-127">日期和時間會以格林威治標準時間 (UTC) 格式儲存。</span><span class="sxs-lookup"><span data-stu-id="7641a-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="7641a-128">**Cmdlet**：用來變更設定之 Cmdlet 的名稱。</span><span class="sxs-lookup"><span data-stu-id="7641a-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="7641a-129">**User**：變更設定之使用者的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="7641a-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="7641a-p107">可在多個頁面上顯示最多 5000 個項目。如果需要縮小搜尋結果，請指定較小的日期範圍。如果您選取個別的搜尋結果，下列其他資訊會顯示在詳細資料窗格中：</span><span class="sxs-lookup"><span data-stu-id="7641a-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="7641a-133">**已修改物件**： Cmdlet 所修改的物件。</span><span class="sxs-lookup"><span data-stu-id="7641a-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="7641a-134">**Parameters (參數： Value)**：所使用的 Cmdlet 參數，以及使用參數指定的任何值。</span><span class="sxs-lookup"><span data-stu-id="7641a-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="7641a-135">如果您要列印特定的稽核記錄項目，請選擇詳細資料窗格中的 [ **列印**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7641a-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="7641a-136">使用獨立 EOP PowerShell 來查看系統管理員審核記錄檔</span><span class="sxs-lookup"><span data-stu-id="7641a-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="7641a-137">您可以使用獨立 EOP PowerShell 來搜尋符合您指定之準則的審計記錄專案。</span><span class="sxs-lookup"><span data-stu-id="7641a-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="7641a-138">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="7641a-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="7641a-139">**附註**：</span><span class="sxs-lookup"><span data-stu-id="7641a-139">**Notes**:</span></span>

- <span data-ttu-id="7641a-140">您只能將 _Parameters_ 參數與 _Cmdlet_ 參數搭配使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="7641a-141">_ObjectIds_ 參數會依 Cmdlet 所修改的物件來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="7641a-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="7641a-142">有效的值取決於物件在審計記錄中的表示方式。</span><span class="sxs-lookup"><span data-stu-id="7641a-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="7641a-143">例如：</span><span class="sxs-lookup"><span data-stu-id="7641a-143">For example:</span></span>

  - <span data-ttu-id="7641a-144">名稱</span><span class="sxs-lookup"><span data-stu-id="7641a-144">Name</span></span>
  - <span data-ttu-id="7641a-145">正常化辨別名稱 (例如，contoso.com/Users/Akia Al Zuhairi) </span><span class="sxs-lookup"><span data-stu-id="7641a-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="7641a-146">您可能需要在此 Cmdlet 上使用其他篩選參數，以縮小結果，並識別您感興趣的物件類型。</span><span class="sxs-lookup"><span data-stu-id="7641a-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="7641a-147">_UserIds_ 參數會依據執行 Cmdlet) 的變更 (來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="7641a-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="7641a-148">針對 _StartDate_ 和 _EndDate_ 參數，如果您指定的日期/時間值不含時區，則此值會在 [標準時間] (UTC) 。</span><span class="sxs-lookup"><span data-stu-id="7641a-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="7641a-149">若要指定這個參數的日期/時間值，請使用下列其中一個選項︰</span><span class="sxs-lookup"><span data-stu-id="7641a-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="7641a-150">指定 UTC 的日期/時間值：例如，"2016-05-06 14:30:00z"。</span><span class="sxs-lookup"><span data-stu-id="7641a-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="7641a-151">指定 [日期/時間] 值做為公式，以將您的本機時區中的日期/時間轉換成 UTC：例如， `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="7641a-152">如需詳細資訊，請參閱 [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)。</span><span class="sxs-lookup"><span data-stu-id="7641a-152">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="7641a-153">根據預設，Cmdlet 會傳回最多1000個記錄專案。</span><span class="sxs-lookup"><span data-stu-id="7641a-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="7641a-154">使用 _ResultSize_ 參數可指定最多250000個記錄專案。</span><span class="sxs-lookup"><span data-stu-id="7641a-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="7641a-155">或者，使用值傳回 `Unlimited` 所有專案。</span><span class="sxs-lookup"><span data-stu-id="7641a-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="7641a-156">此範例使用下列準則，執行所有稽核記錄項目的搜尋：</span><span class="sxs-lookup"><span data-stu-id="7641a-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="7641a-157">**開始日期**：2019年8月4日</span><span class="sxs-lookup"><span data-stu-id="7641a-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="7641a-158">**結束日期**：2019年10月3日</span><span class="sxs-lookup"><span data-stu-id="7641a-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="7641a-159">**Cmdlet**： Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="7641a-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="7641a-160">如需詳細的語法及參數資訊，請參閱 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)。</span><span class="sxs-lookup"><span data-stu-id="7641a-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="7641a-161">檢視稽核記錄項目的詳細資料</span><span class="sxs-lookup"><span data-stu-id="7641a-161">View details of audit log entries</span></span>

<span data-ttu-id="7641a-162">**Search-AdminAuditLog** Cmdlet 會傳回本文稍後的 [[審計記錄檔內容](#audit-log-contents)] 區段中所述的欄位。</span><span class="sxs-lookup"><span data-stu-id="7641a-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="7641a-163">由指令程式傳回的欄位、兩個欄位 **CmdletParameters** 和 **ModifiedProperties**，包含預設不會傳回的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="7641a-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="7641a-164">若要檢視 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7641a-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="7641a-165">決定您要搜尋的準則、執行 **Search-AdminAuditLog** 指令程式，然後使用下列命令將結果儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="7641a-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="7641a-166">每個審計記錄專案都是以陣列元素形式儲存在變數中 `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="7641a-167">您可以指定陣列項目索引來選取陣列元素。</span><span class="sxs-lookup"><span data-stu-id="7641a-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="7641a-168">陣列元素索引從零 (0) 開始，表示第一個陣列元素。</span><span class="sxs-lookup"><span data-stu-id="7641a-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="7641a-169">例如，若要擷取第 5 個陣列元素，其索引為 4，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="7641a-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="7641a-p115">上一個命令會傳回儲存在陣列元素 4 中的記錄項目。若要查看此記錄項目的 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="7641a-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="7641a-172">若要檢視另一個記錄項目的 **CmdletParameters** 或 **ModifiedParameters** 欄位，請變更陣列元素索引。</span><span class="sxs-lookup"><span data-stu-id="7641a-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="7641a-173">稽核記錄內容</span><span class="sxs-lookup"><span data-stu-id="7641a-173">Audit log contents</span></span>

<span data-ttu-id="7641a-174">每個審計記錄專案都包含下表所述的資訊。</span><span class="sxs-lookup"><span data-stu-id="7641a-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="7641a-175">審核記錄檔包含一或多個審計記錄專案。</span><span class="sxs-lookup"><span data-stu-id="7641a-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="7641a-176">欄位</span><span class="sxs-lookup"><span data-stu-id="7641a-176">Field</span></span>|<span data-ttu-id="7641a-177">描述</span><span class="sxs-lookup"><span data-stu-id="7641a-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="7641a-178">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="7641a-179">此欄位包含的物件是由欄位中指定的 Cmdlet 所修改 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="7641a-180">此欄位包含使用者在欄位中執行的 Cmdlet 名稱 `Caller` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="7641a-181">此欄位包含在執列欄位中的 Cmdlet 時所指定的參數 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="7641a-182">此外，在此欄位中（但在預設輸出中看不到）是以參數指定的值（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="7641a-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="7641a-183">此欄位包含在欄位中的物件上修改的屬性 `ObjectModified` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="7641a-184">此欄位也儲存在此欄位中，但在預設輸出中不會顯示，也就是舊的屬性值及已儲存的新值。</span><span class="sxs-lookup"><span data-stu-id="7641a-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="7641a-185">此欄位包含在欄位中執行 Cmdlet 之使用者的使用者帳戶 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="7641a-186">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="7641a-187">此欄位會指定是否已成功執列欄位中的 Cmdlet `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="7641a-188">其值為 `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="7641a-189">此欄位包含當欄位中的 Cmdlet 未能成功完成時所產生的錯誤訊息 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="7641a-190">此欄位包含執列欄位中的指令程式的日期和時間 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="7641a-191">日期和時間會以格林威治標準時間 (UTC) 格式儲存。</span><span class="sxs-lookup"><span data-stu-id="7641a-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="7641a-192">此欄位會指出執列欄位中所指定之指令程式的伺服器 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="7641a-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="7641a-193">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="7641a-194">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="7641a-195">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="7641a-196">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="7641a-197">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="7641a-198">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="7641a-199">此欄位是由 EOP 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="7641a-199">This field is used internally by EOP.</span></span>|
|
