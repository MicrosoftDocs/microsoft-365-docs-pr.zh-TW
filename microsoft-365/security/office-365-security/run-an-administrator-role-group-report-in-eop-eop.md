---
title: 在獨立版 EOP 中執行系統管理員角色群組報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何在獨立 Exchange Online Protection (EOP) 中執行系統管理員角色群組報告。 當系統管理員在系統管理員角色群組中新增或移除成員時，此報告會登入。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d778e807a087a5e29b31645457d4a81bd05c5649
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288016"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="579ef-104">在獨立版 EOP 中執行系統管理員角色群組報告</span><span class="sxs-lookup"><span data-stu-id="579ef-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="579ef-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="579ef-105">**Applies to**</span></span>
-  [<span data-ttu-id="579ef-106">Exchange Online Protection 獨立</span><span class="sxs-lookup"><span data-stu-id="579ef-106">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="579ef-107">在獨立 Exchange Online Protection (EOP 中) 沒有 Exchange Online 信箱的組織，當系統管理員新增成員或從系統管理角色群組中移除成員時，該服務會記錄每個事件。</span><span class="sxs-lookup"><span data-stu-id="579ef-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="579ef-108">如需獨立 EOP 中角色群組的詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="579ef-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="579ef-109">當您在 Exchange 系統管理中心中執行系統管理員角色群組報告 (EAC) 時，專案會顯示為搜尋結果，並包含受影響的角色群組、變更角色群組成員資格的人員，以及進行的成員資格更新。</span><span class="sxs-lookup"><span data-stu-id="579ef-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="579ef-110">使用此報告可監視指派給組織使用者的系統管理權限變更。</span><span class="sxs-lookup"><span data-stu-id="579ef-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="579ef-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="579ef-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="579ef-112">若要開啟 Exchange 系統管理中心，請參閱 [exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="579ef-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="579ef-113">您必須先在 Exchange Online Protection 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="579ef-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="579ef-114">具體說來，您需要「 **審核記錄** 」或「 **View-Only 審核記錄** 」角色，預設會指派給「 **組織管理**」、「 **合規性管理**」及「 **安全性管理員** 」角色群組。</span><span class="sxs-lookup"><span data-stu-id="579ef-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="579ef-115">如需詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="579ef-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="579ef-116">如需適用于本文中程式的鍵盤快速鍵的詳細資訊，請參閱 exchange [Online 中 exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="579ef-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="579ef-117">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="579ef-117">Having problems?</span></span> <span data-ttu-id="579ef-118">在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="579ef-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="579ef-119">使用 EAC 執行系統管理員角色群組報告</span><span class="sxs-lookup"><span data-stu-id="579ef-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="579ef-120">執行系統管理員角色群組報告，以尋找在特定時間範圍內對管理角色群組所做的變更。</span><span class="sxs-lookup"><span data-stu-id="579ef-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="579ef-121">在 EAC 中，移至 [ **規範管理**] [ \> **審計**]，然後選擇 [ **執行系統管理員角色群組報告**]。</span><span class="sxs-lookup"><span data-stu-id="579ef-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="579ef-122">在開啟的 [ **搜尋系統管理員角色群組變更** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="579ef-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="579ef-123">**開始日期** 和 **結束日期**：輸入日期範圍。</span><span class="sxs-lookup"><span data-stu-id="579ef-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="579ef-124">依預設，報告會搜尋過去兩週以來對系統管理員角色群組所做的變更。</span><span class="sxs-lookup"><span data-stu-id="579ef-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="579ef-125">**選取角色群組**：根據預設，會搜尋所有角色群組。</span><span class="sxs-lookup"><span data-stu-id="579ef-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="579ef-126">若要依特定角色群組篩選結果，請按一下 [ **選取角色群組**]。</span><span class="sxs-lookup"><span data-stu-id="579ef-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="579ef-127">在出現的對話方塊中，選取角色群組，然後按一下 [ **載入 >**]。</span><span class="sxs-lookup"><span data-stu-id="579ef-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="579ef-128">視需要重複此步驟，然後在完成時按一下 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="579ef-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="579ef-129">完成後，請按一下 [ **搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="579ef-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="579ef-p108">如果使用您指定的準則找到任何變更，它們會出現在結果窗格中。按一下搜尋結果中的角色群組，即可在詳細資料窗格中查看變更。</span><span class="sxs-lookup"><span data-stu-id="579ef-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="579ef-132">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="579ef-132">How do you know this worked?</span></span>

<span data-ttu-id="579ef-p109">如果您已經成功執行系統管理員角色群組報告，已在日期範圍內變更的角色群組會顯示在搜尋結果窗格中。如果沒有任何結果，則表示在指定的日期範圍內，沒有對角色群組進行任何變更。如果您認為應該有結果，請變更日期範圍，然後重新執行報告。</span><span class="sxs-lookup"><span data-stu-id="579ef-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="579ef-136">監視角色群組成員資格的變更</span><span class="sxs-lookup"><span data-stu-id="579ef-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="579ef-p110">在角色群組中新增或移除成員時，搜尋結果會顯示在詳細資料窗格中，指出角色群組成員資格已經更新，並列出目前的成員。結果不會明確表示已新增或移除哪一位使用者。</span><span class="sxs-lookup"><span data-stu-id="579ef-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="579ef-p111">若要判斷是否已新增或移除某位使用者，您必須比較報告中的兩個個別項目。例如，以下是 **HelpDesk** 角色群組的記錄項目：</span><span class="sxs-lookup"><span data-stu-id="579ef-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="579ef-141">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="579ef-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="579ef-142">系統管理員</span><span class="sxs-lookup"><span data-stu-id="579ef-142">Administrator</span></span> <br> <span data-ttu-id="579ef-143">Updated members:Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="579ef-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="579ef-144">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="579ef-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="579ef-145">系統管理員</span><span class="sxs-lookup"><span data-stu-id="579ef-145">Administrator</span></span> <br> <span data-ttu-id="579ef-146">Updated members:Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="579ef-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="579ef-147">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="579ef-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="579ef-148">系統管理員</span><span class="sxs-lookup"><span data-stu-id="579ef-148">Administrator</span></span> <br> <span data-ttu-id="579ef-149">Updated members:Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="579ef-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="579ef-150">在此範例中，系統管理員使用者帳戶做了以下變更：</span><span class="sxs-lookup"><span data-stu-id="579ef-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="579ef-151">在2/06/2018 上，他們新增了使用者 tonip。</span><span class="sxs-lookup"><span data-stu-id="579ef-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="579ef-152">在2/19/2018 上，他們移除使用者 pilarp。</span><span class="sxs-lookup"><span data-stu-id="579ef-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="579ef-153">使用獨立 Exchange Online PowerShell 來搜尋審計記錄專案</span><span class="sxs-lookup"><span data-stu-id="579ef-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="579ef-154">您可以使用 Exchange Online PowerShell 來搜尋符合您指定之準則的審計記錄專案。</span><span class="sxs-lookup"><span data-stu-id="579ef-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="579ef-155">如需搜尋準則的清單，請參閱 [Search-AdminAuditLog 搜尋準則](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="579ef-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="579ef-156">此程式會使用 **Search-AdminAuditLog** Cmdlet，並以 Exchange Online PowerShell 顯示搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="579ef-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="579ef-157">當您需要傳回的一組結果超過 **New-AdminAuditLogSearch** Cmdlet 或 EAC「稽核報告」報告中所定義的限制時，就可以使用這個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="579ef-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="579ef-158">若要搜尋指定準則的稽核記錄，請使用下列語法。</span><span class="sxs-lookup"><span data-stu-id="579ef-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="579ef-159">根據預設， **Search-AdminAuditLog** 指令程式最多會傳回 1,000 個記錄項目。</span><span class="sxs-lookup"><span data-stu-id="579ef-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="579ef-160">使用 _ResultSize_ 參數可指定最多250000個記錄專案。</span><span class="sxs-lookup"><span data-stu-id="579ef-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="579ef-161">或者，使用值傳回 `Unlimited` 所有專案。</span><span class="sxs-lookup"><span data-stu-id="579ef-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="579ef-162">此範例使用下列準則，執行所有稽核記錄項目的搜尋：</span><span class="sxs-lookup"><span data-stu-id="579ef-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="579ef-163">**開始日期**：08/04/2018</span><span class="sxs-lookup"><span data-stu-id="579ef-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="579ef-164">**結束日期**：10/03/2018</span><span class="sxs-lookup"><span data-stu-id="579ef-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="579ef-165">**使用者 IDs**： `davids` 、 `chrisd` 、 `kima`</span><span class="sxs-lookup"><span data-stu-id="579ef-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="579ef-166">**Cmdlet**： **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="579ef-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="579ef-167">**Parameters**： _ProhibitSendQuota_、 _ProhibitSendReceiveQuota_、 _IssueWarningQuota_、 _MaxSendSize_、 _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="579ef-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="579ef-p114">此範例搜尋特定信箱的變更。如果您在進行疑難排解或需要提供調查的資訊，這會很有用。使用下列準則：</span><span class="sxs-lookup"><span data-stu-id="579ef-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="579ef-171">**開始日期**：05/01/2018</span><span class="sxs-lookup"><span data-stu-id="579ef-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="579ef-172">**結束日期**：10/03/2018</span><span class="sxs-lookup"><span data-stu-id="579ef-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="579ef-173">**物件識別碼**： contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="579ef-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="579ef-174">如果您的搜尋傳回許多記錄專案，建議您使用使用 Exchange Online PowerShell 中提供的程式， **來搜尋審計記錄專案，並將結果傳送給** 本文稍後的收件者。</span><span class="sxs-lookup"><span data-stu-id="579ef-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="579ef-175">該章節中的程序會以電子郵件附件形式將 XML 檔案傳送給您指定的收件者，讓您更輕鬆擷取感興趣的資料。</span><span class="sxs-lookup"><span data-stu-id="579ef-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="579ef-176">如需詳細的語法及參數資訊，請參閱 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)。</span><span class="sxs-lookup"><span data-stu-id="579ef-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="579ef-177">檢視稽核記錄項目的詳細資料</span><span class="sxs-lookup"><span data-stu-id="579ef-177">View details of audit log entries</span></span>

<span data-ttu-id="579ef-178">**Search-AdminAuditLog** Cmdlet 會傳回 [審核記錄內容](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)中所述的欄位。</span><span class="sxs-lookup"><span data-stu-id="579ef-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="579ef-179">在此指令程式傳回的欄位中， **CmdletParameters** 和 **ModifiedProperties** 兩個欄位包含依預設無法檢視的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="579ef-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="579ef-180">若要檢視 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="579ef-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="579ef-181">或者，您可以使用 **Exchange Online PowerShell 中的程式來搜尋審計記錄專案，並將結果傳送到** 本文稍後的收件者，以建立 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="579ef-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="579ef-182">此程序採用下列概念：</span><span class="sxs-lookup"><span data-stu-id="579ef-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="579ef-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="579ef-183">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="579ef-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="579ef-184">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="579ef-185">決定您要搜尋的準則、執行 **Search-AdminAuditLog** 指令程式，然後使用下列命令將結果儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="579ef-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="579ef-186">每個審計記錄專案都是以陣列元素形式儲存在變數中 `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="579ef-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="579ef-187">您可以指定陣列項目索引來選取陣列元素。</span><span class="sxs-lookup"><span data-stu-id="579ef-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="579ef-188">陣列元素索引從零 (0) 開始，表示第一個陣列元素。</span><span class="sxs-lookup"><span data-stu-id="579ef-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="579ef-189">例如，若要擷取第 5 個陣列元素，其索引為 4，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="579ef-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="579ef-p119">上一個命令會傳回儲存在陣列元素 4 中的記錄項目。若要查看此記錄項目的 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="579ef-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="579ef-192">若要檢視另一個記錄項目的 **CmdletParameters** 或 **ModifiedParameters** 欄位，請變更陣列元素索引。</span><span class="sxs-lookup"><span data-stu-id="579ef-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
