---
title: 在獨立版 EOP 中執行系統管理員角色群組報告
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
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 管理員可以瞭解如何在獨立 Exchange Online Protection （EOP）中執行系統管理員角色群組報告。 當系統管理員在系統管理員角色群組中新增或移除成員時，此報告會登入，EOP 記錄每次出現一次。
ms.openlocfilehash: 39022892075b295a26645157941195b97897c690
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350936"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="de7bf-104">在獨立版 EOP 中執行系統管理員角色群組報告</span><span class="sxs-lookup"><span data-stu-id="de7bf-104">Run an administrator role group report in standalone EOP</span></span>

<span data-ttu-id="de7bf-105">在沒有 Exchange Online 信箱的獨立 Exchange Online Protection （EOP）組織中，當系統管理員新增成員至或移除系統管理角色群組中的成員時，服務會記錄每個事件。</span><span class="sxs-lookup"><span data-stu-id="de7bf-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="de7bf-106">如需獨立 EOP 中角色群組的詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="de7bf-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="de7bf-107">當您在 Exchange 系統管理中心（EAC）中執行系統管理員角色群組報告時，專案會顯示為搜尋結果，並包含受影響的角色群組、變更角色群組成員資格的人員，以及進行的成員資格更新。</span><span class="sxs-lookup"><span data-stu-id="de7bf-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="de7bf-108">使用此報告可監視指派給組織使用者的系統管理權限變更。</span><span class="sxs-lookup"><span data-stu-id="de7bf-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de7bf-109">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="de7bf-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de7bf-110">若要開啟 Exchange 系統管理中心，請參閱[exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="de7bf-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="de7bf-111">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="de7bf-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="de7bf-112">具體說來，您需要 ComplianceManagement 審核記錄檔或 View-Only 的「審核記錄」角色，其預設會指派給、OrganizationManagement （全域管理員）和 SecurityAdministrator 角色群組。</span><span class="sxs-lookup"><span data-stu-id="de7bf-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="de7bf-113">如需詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)和[使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="de7bf-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="de7bf-114">如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="de7bf-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="de7bf-115">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="de7bf-115">Having problems?</span></span> <span data-ttu-id="de7bf-116">在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="de7bf-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="de7bf-117">使用 EAC 執行系統管理員角色群組報告</span><span class="sxs-lookup"><span data-stu-id="de7bf-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="de7bf-118">執行系統管理員角色群組報告，以在特定時間範圍內尋找組織中管理角色群組的變更。</span><span class="sxs-lookup"><span data-stu-id="de7bf-118">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="de7bf-119">在 EAC 中，移至 [**規範管理**] [ \> **審計**]，然後選擇 [**執行系統管理員角色群組報告**]。</span><span class="sxs-lookup"><span data-stu-id="de7bf-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="de7bf-120">在開啟的 [**搜尋系統管理員角色群組變更**] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="de7bf-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="de7bf-121">**開始日期**和**結束日期**：輸入日期範圍。</span><span class="sxs-lookup"><span data-stu-id="de7bf-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="de7bf-122">依預設，報告會搜尋過去兩週以來對系統管理員角色群組所做的變更。</span><span class="sxs-lookup"><span data-stu-id="de7bf-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="de7bf-123">**選取角色群組**：根據預設，會搜尋所有角色群組。</span><span class="sxs-lookup"><span data-stu-id="de7bf-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="de7bf-124">若要依特定角色群組篩選結果，請按一下 [**選取角色群組**]。</span><span class="sxs-lookup"><span data-stu-id="de7bf-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="de7bf-125">在出現的對話方塊中，選取角色群組，然後按一下 [**載入 >**]。</span><span class="sxs-lookup"><span data-stu-id="de7bf-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="de7bf-126">視需要重複此步驟，然後在完成時按一下 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="de7bf-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="de7bf-127">完成後，請按一下 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="de7bf-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="de7bf-p108">如果使用您指定的準則找到任何變更，它們會出現在結果窗格中。按一下搜尋結果中的角色群組，即可在詳細資料窗格中查看變更。</span><span class="sxs-lookup"><span data-stu-id="de7bf-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="de7bf-130">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="de7bf-130">How do you know this worked?</span></span>

<span data-ttu-id="de7bf-p109">如果您已經成功執行系統管理員角色群組報告，已在日期範圍內變更的角色群組會顯示在搜尋結果窗格中。如果沒有任何結果，則表示在指定的日期範圍內，沒有對角色群組進行任何變更。如果您認為應該有結果，請變更日期範圍，然後重新執行報告。</span><span class="sxs-lookup"><span data-stu-id="de7bf-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="de7bf-134">監視角色群組成員資格的變更</span><span class="sxs-lookup"><span data-stu-id="de7bf-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="de7bf-p110">在角色群組中新增或移除成員時，搜尋結果會顯示在詳細資料窗格中，指出角色群組成員資格已經更新，並列出目前的成員。結果不會明確表示已新增或移除哪一位使用者。</span><span class="sxs-lookup"><span data-stu-id="de7bf-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="de7bf-p111">若要判斷是否已新增或移除某位使用者，您必須比較報告中的兩個個別項目。例如，以下是 **HelpDesk** 角色群組的記錄項目：</span><span class="sxs-lookup"><span data-stu-id="de7bf-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="de7bf-139">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="de7bf-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="de7bf-140">系統管理員</span><span class="sxs-lookup"><span data-stu-id="de7bf-140">Administrator</span></span> <br> <span data-ttu-id="de7bf-141">Updated members:Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="de7bf-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="de7bf-142">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="de7bf-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="de7bf-143">系統管理員</span><span class="sxs-lookup"><span data-stu-id="de7bf-143">Administrator</span></span> <br> <span data-ttu-id="de7bf-144">Updated members:Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="de7bf-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="de7bf-145">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="de7bf-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="de7bf-146">系統管理員</span><span class="sxs-lookup"><span data-stu-id="de7bf-146">Administrator</span></span> <br> <span data-ttu-id="de7bf-147">Updated members:Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="de7bf-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="de7bf-148">在此範例中，系統管理員使用者帳戶做了以下變更：</span><span class="sxs-lookup"><span data-stu-id="de7bf-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="de7bf-149">在2/06/2018 上，他們新增了使用者 tonip。</span><span class="sxs-lookup"><span data-stu-id="de7bf-149">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="de7bf-150">在2/19/2018 上，他們移除使用者 pilarp。</span><span class="sxs-lookup"><span data-stu-id="de7bf-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="de7bf-151">使用獨立 Exchange Online PowerShell 來搜尋審計記錄專案</span><span class="sxs-lookup"><span data-stu-id="de7bf-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="de7bf-152">您可以使用 Exchange Online PowerShell 來搜尋符合您指定之準則的審計記錄專案。</span><span class="sxs-lookup"><span data-stu-id="de7bf-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="de7bf-153">如需搜尋準則的清單，請參閱[系統管理員稽核記錄](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx)。</span><span class="sxs-lookup"><span data-stu-id="de7bf-153">For a list of search criteria, see [Administrator audit logging](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx).</span></span> <span data-ttu-id="de7bf-154">此程式會使用**Search-AdminAuditLog** Cmdlet，並以 Exchange Online PowerShell 顯示搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="de7bf-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="de7bf-155">當您需要傳回的一組結果超過 **New-AdminAuditLogSearch** Cmdlet 或 EAC「稽核報告」報告中所定義的限制時，就可以使用這個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="de7bf-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="de7bf-156">若要搜尋指定準則的稽核記錄，請使用下列語法。</span><span class="sxs-lookup"><span data-stu-id="de7bf-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="de7bf-157">根據預設， **Search-AdminAuditLog** 指令程式最多會傳回 1,000 個記錄項目。</span><span class="sxs-lookup"><span data-stu-id="de7bf-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="de7bf-158">使用_ResultSize_參數可指定最多250000個記錄專案。</span><span class="sxs-lookup"><span data-stu-id="de7bf-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="de7bf-159">或者，使用值傳回 `Unlimited` 所有專案。</span><span class="sxs-lookup"><span data-stu-id="de7bf-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="de7bf-160">此範例使用下列準則，執行所有稽核記錄項目的搜尋：</span><span class="sxs-lookup"><span data-stu-id="de7bf-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="de7bf-161">**開始日期**：08/04/2018</span><span class="sxs-lookup"><span data-stu-id="de7bf-161">**Start date**: 08/04/2018</span></span>

- <span data-ttu-id="de7bf-162">**結束日期**：10/03/2018</span><span class="sxs-lookup"><span data-stu-id="de7bf-162">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="de7bf-163">**使用者 IDs**： davids、chrisd、kima</span><span class="sxs-lookup"><span data-stu-id="de7bf-163">**User IDs**: davids, chrisd, kima</span></span>

- <span data-ttu-id="de7bf-164">**Cmdlet**： **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="de7bf-164">**Cmdlets**: **Set-Mailbox**</span></span>

- <span data-ttu-id="de7bf-165">**Parameters**： _ProhibitSendQuota_、 _ProhibitSendReceiveQuota_、 _IssueWarningQuota_、 _MaxSendSize_、 _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="de7bf-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="de7bf-p114">此範例搜尋特定信箱的變更。如果您在進行疑難排解或需要提供調查的資訊，這會很有用。使用下列準則：</span><span class="sxs-lookup"><span data-stu-id="de7bf-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="de7bf-169">**開始日期**：05/01/2018</span><span class="sxs-lookup"><span data-stu-id="de7bf-169">**Start date**: 05/01/2018</span></span>

- <span data-ttu-id="de7bf-170">**結束日期**：10/03/2018</span><span class="sxs-lookup"><span data-stu-id="de7bf-170">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="de7bf-171">**物件識別碼**： contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="de7bf-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="de7bf-172">如果您的搜尋傳回許多記錄專案，建議您使用使用 Exchange Online PowerShell 中提供的程式，**來搜尋審計記錄專案，並將結果傳送給**本主題稍後的收件者。</span><span class="sxs-lookup"><span data-stu-id="de7bf-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic.</span></span> <span data-ttu-id="de7bf-173">該章節中的程序會以電子郵件附件形式將 XML 檔案傳送給您指定的收件者，讓您更輕鬆擷取感興趣的資料。</span><span class="sxs-lookup"><span data-stu-id="de7bf-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="de7bf-174">如需詳細的語法及參數資訊，請參閱 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)。</span><span class="sxs-lookup"><span data-stu-id="de7bf-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="de7bf-175">檢視稽核記錄項目的詳細資料</span><span class="sxs-lookup"><span data-stu-id="de7bf-175">View details of audit log entries</span></span>

<span data-ttu-id="de7bf-p116">**Search-AdminAuditLog** Cmdlet 會傳回 [系統管理員稽核記錄](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx)的「稽核記錄內容」一節所描述的欄位。在此指令程式傳回的欄位中， **CmdletParameters** 和 **ModifiedProperties** 兩個欄位包含依預設無法檢視的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="de7bf-p116">The **Search-AdminAuditLog** cmdlet returns the fields described in the "Audit log contents section of [Administrator audit logging](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx). Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="de7bf-178">若要檢視 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="de7bf-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="de7bf-179">或者，您可以使用**Exchange Online PowerShell 中的程式來搜尋審計記錄專案，並將結果傳送到**本主題稍後的收件者，以建立 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="de7bf-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic to create an XML file.</span></span>

<span data-ttu-id="de7bf-180">此程序採用下列概念：</span><span class="sxs-lookup"><span data-stu-id="de7bf-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="de7bf-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="de7bf-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="de7bf-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="de7bf-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="de7bf-183">決定您要搜尋的準則、執行 **Search-AdminAuditLog** 指令程式，然後使用下列命令將結果儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="de7bf-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="de7bf-184">每個審計記錄專案都是以陣列元素形式儲存在變數中 `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="de7bf-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="de7bf-185">您可以指定陣列項目索引來選取陣列元素。</span><span class="sxs-lookup"><span data-stu-id="de7bf-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="de7bf-186">陣列元素索引從零 (0) 開始，表示第一個陣列元素。</span><span class="sxs-lookup"><span data-stu-id="de7bf-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="de7bf-187">例如，若要擷取第 5 個陣列元素，其索引為 4，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="de7bf-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="de7bf-p119">上一個命令會傳回儲存在陣列元素 4 中的記錄項目。若要查看此記錄項目的 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="de7bf-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="de7bf-190">若要檢視另一個記錄項目的 **CmdletParameters** 或 **ModifiedParameters** 欄位，請變更陣列元素索引。</span><span class="sxs-lookup"><span data-stu-id="de7bf-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>