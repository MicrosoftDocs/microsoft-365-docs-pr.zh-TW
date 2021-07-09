---
title: 在 Microsoft 365 中設定高級審計
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文說明如何設定高級審核，讓您可以在使用者帳戶受損時執行鑒證調查，或調查其他與安全性相關的事件。
ms.openlocfilehash: 825dadee5260a263d005eb3a37f280381f9425a2
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339223"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="85c8a-103">在 Microsoft 365 中設定高級審計</span><span class="sxs-lookup"><span data-stu-id="85c8a-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="85c8a-104">如果您的組織擁有支援高級審計的訂閱和使用者授權，請執行下列步驟，以在高級審計中設定及使用其他功能。</span><span class="sxs-lookup"><span data-stu-id="85c8a-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![設定進階稽核的工作流程](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a><span data-ttu-id="85c8a-106">步驟1：為使用者設定高級審計</span><span class="sxs-lookup"><span data-stu-id="85c8a-106">Step 1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="85c8a-107">進階稽核功能，如記錄重要事件 (如 MailItemsAccessed 和 Send) 功能，需要為使用者指派適當的 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="85c8a-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="85c8a-108">此外，必須為這些使用者啟用 [進階稽核] 應用程式/服務方案。</span><span class="sxs-lookup"><span data-stu-id="85c8a-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="85c8a-109">要驗證 [進階稽核] 應用程式是否已指派給使用者，請對每個使用者執行以下步驟：</span><span class="sxs-lookup"><span data-stu-id="85c8a-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="85c8a-110">在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/Adminportal)中，移至 **[使用者]** > **[作用中的使用者]**，然後選取使用者。</span><span class="sxs-lookup"><span data-stu-id="85c8a-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="85c8a-111">在 [使用者內容] 飛出頁面上，按一下 **[授權和應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="85c8a-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="85c8a-112">在 [ **授權** ] 區段中，確認使用者已獲指派 E5 授權，或已獲指派適當的附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="85c8a-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="85c8a-113">如需支援高級審核的授權清單，請參閱「 [高級審核授權」需求](auditing-solutions-overview.md#advanced-audit-1)。</span><span class="sxs-lookup"><span data-stu-id="85c8a-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="85c8a-114">展開 **[應用程式]** 區段，並驗證是否選中了 **[Microsoft 365 進階稽核]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="85c8a-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="85c8a-115">如果未選取此核取方塊，請選取它，然後按一下 [ **儲存變更]。**</span><span class="sxs-lookup"><span data-stu-id="85c8a-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="85c8a-116">MailItemsAccessed 和 Send 的審計記錄記錄會從24小時內開始。</span><span class="sxs-lookup"><span data-stu-id="85c8a-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="85c8a-117">您必須執行步驟3，以開始記錄其他兩個高級審核重要事件： SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint。</span><span class="sxs-lookup"><span data-stu-id="85c8a-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="85c8a-118">針對使用以群組為基礎授權之指派授權至使用者群組的組織，請務必關閉該群組的 Microsoft 365 進階稽核授權指派。</span><span class="sxs-lookup"><span data-stu-id="85c8a-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="85c8a-119">儲存變更之後，請確認已關閉群組的 Microsoft 365 進階稽核。</span><span class="sxs-lookup"><span data-stu-id="85c8a-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="85c8a-120">然後重新開啟群組的授權指派。</span><span class="sxs-lookup"><span data-stu-id="85c8a-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="85c8a-121">如需以群組為基礎授權的相關指示，請參閱[在 Azure Active Directory 中以群組成員資格指派授權給使用者](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="85c8a-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="85c8a-122">此外，如果您已自訂使用者信箱或共用信箱上所記錄的信箱動作，則 Microsoft 所發行的任何新重要事件都不會自動在這些信箱上進行審核。</span><span class="sxs-lookup"><span data-stu-id="85c8a-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="85c8a-123">有關變更為每個登入類型稽核的郵箱動作之資訊，請參閱[管理郵箱稽核](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)中的 [變更或還原預設記錄的郵箱動作] 一節。</span><span class="sxs-lookup"><span data-stu-id="85c8a-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="85c8a-124">步驟2：啟用重要事件</span><span class="sxs-lookup"><span data-stu-id="85c8a-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="85c8a-125">您必須啟用兩個重要事件 (SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint) 在使用者于 Exchange Online 和 SharePoint 線上執行搜尋時才會登入。</span><span class="sxs-lookup"><span data-stu-id="85c8a-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="85c8a-126">若要為使用者審核這兩個事件，請針對[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中的每個使用者) 執行下列命令 (：</span><span class="sxs-lookup"><span data-stu-id="85c8a-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="85c8a-127">在多地理位置環境中，您必須在使用者信箱所在的樹系中執行先前的 **Set-Mailbox** 命令。</span><span class="sxs-lookup"><span data-stu-id="85c8a-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="85c8a-128">若要識別使用者的信箱位置，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="85c8a-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="85c8a-129">若啟用搜尋查詢審計的命令先前是在與使用者信箱所在的樹系不同的樹系中執行，則必須執行此作業， `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` 然後再將其新增至使用者信箱所在樹系中的使用者信箱，以移除使用者信箱中的 SearchQueryInitiated 值。</span><span class="sxs-lookup"><span data-stu-id="85c8a-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="85c8a-130">步驟3：設定審核保留原則</span><span class="sxs-lookup"><span data-stu-id="85c8a-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="85c8a-131">除了保留 Exchange、SharePoint 和 Azure AD 稽核記錄一年的預設原則之外，您還可以建立其他稽核記錄保留原則以符合組織的安全性作業、IT 和合規性小組的需求。</span><span class="sxs-lookup"><span data-stu-id="85c8a-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="85c8a-132">如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="85c8a-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="85c8a-133">步驟4：搜尋重要事件</span><span class="sxs-lookup"><span data-stu-id="85c8a-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="85c8a-134">現在您已設定好組織的高級審核，您可以在進行鑒證調查時搜尋重要的事件及其他活動。</span><span class="sxs-lookup"><span data-stu-id="85c8a-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="85c8a-135">完成步驟1和步驟2後，您可以在取證調查遭破壞的帳戶和其他類型的安全性或法規遵從性調查期間，搜尋「審核記錄」，以取得重要的事件及其他活動。</span><span class="sxs-lookup"><span data-stu-id="85c8a-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="85c8a-136">如需使用 MailItemsAccessed 重要事件來進行取證調查已遭破壞之使用者帳戶的詳細資訊，請參閱 [使用 Advanced Audit 調查已遭破壞的帳戶](mailitemsaccessed-forensics-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="85c8a-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
