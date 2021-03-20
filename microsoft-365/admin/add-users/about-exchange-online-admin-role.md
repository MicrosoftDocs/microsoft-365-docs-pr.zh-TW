---
title: 關於 Exchange Online 系統管理員角色
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Exchange online 系統管理員會管理您組織的電子郵件和信箱。 例如，他們會在使用者的信箱中復原已刪除的郵件。 '
ms.openlocfilehash: 4db7b55f6bb5bb75149a3b91bd7855565ca1be46
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906345"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="6c410-104">關於 Exchange Online 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="6c410-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="6c410-105">為了協助您管理 Microsoft 365，您可以從[Exchange 系統管理中心](/exchange/exchange-admin-center)[指派](assign-admin-roles.md)使用者管理組織的電子郵件和信箱的許可權。</span><span class="sxs-lookup"><span data-stu-id="6c410-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](/exchange/exchange-admin-center).</span></span> <span data-ttu-id="6c410-106">若要這麼做，您可以將其指派給 Exchange 系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="6c410-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="6c410-107">**提示**：當您將某人指派給 Exchange 系統管理員角色時，也會將其指派給服務系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="6c410-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="6c410-108">如此一來，他們就可以在 Microsoft 365 系統管理中心中看到重要資訊（例如 Exchange Online 服務的健康情況），以及變更和發佈通知。</span><span class="sxs-lookup"><span data-stu-id="6c410-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="6c410-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="6c410-109">Before you begin</span></span>

<span data-ttu-id="6c410-110">以下是在指派給 Exchange 系統管理員角色時，使用者可以執行的一些主要工作：</span><span class="sxs-lookup"><span data-stu-id="6c410-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="6c410-111">復原使用者信箱中刪除的郵件 - 系統管理說明</span><span class="sxs-lookup"><span data-stu-id="6c410-111">Recover deleted items in a user mailbox - Admin Help</span></span>](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- <span data-ttu-id="6c410-112">[設定組織中信箱的封存和刪除原則](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="6c410-112">[Set up an archive and deletion policy for mailboxes in your organization](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>

- <span data-ttu-id="6c410-113">設定信箱功能，例如信箱共用原則：使用者如何與組織外的其他人共用行事曆和連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="6c410-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="6c410-114">為某人的信箱設定「[傳送為](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)」和「[代理傳送](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)者」代理人。</span><span class="sxs-lookup"><span data-stu-id="6c410-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="6c410-115">例如，行政人員可能想要讓其助理能夠代您傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="6c410-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="6c410-116">[建立共用信箱](../email/create-a-shared-mailbox.md) ，讓一群組人員可以從共同的電子郵件地址監視及傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6c410-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="6c410-117">組織的[電子郵件反垃圾郵件保護](../../security/office-365-security/anti-spam-protection.md)和惡意程式碼篩選器。</span><span class="sxs-lookup"><span data-stu-id="6c410-117">[Email anti-spam protection](../../security/office-365-security/anti-spam-protection.md) and malware filters for the organization.</span></span>

- <span data-ttu-id="6c410-118">管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="6c410-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="6c410-119">Exchange Online 角色群組</span><span class="sxs-lookup"><span data-stu-id="6c410-119">Exchange Online role groups</span></span>

<span data-ttu-id="6c410-120">如果您有大型組織，Exchange 系統管理員可能會想要將使用者指派給 Exchange 角色群組。</span><span class="sxs-lookup"><span data-stu-id="6c410-120">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups.</span></span> <span data-ttu-id="6c410-121">當系統管理員將使用者新增至角色群組時，使用者會取得執行特定商務功能的許可權。只有該群組的成員才能執行。</span><span class="sxs-lookup"><span data-stu-id="6c410-121">When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="6c410-122">例如，Exchange 系統管理員可能會將某個人員指派給「探索管理」角色群組，讓他們可以針對符合特定準則的資料執行信箱搜尋。</span><span class="sxs-lookup"><span data-stu-id="6c410-122">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria.</span></span> <span data-ttu-id="6c410-123">若要深入瞭解，請參閱 [Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo) 和 [管理角色群組](/exchange/manage-role-groups-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="6c410-123">To learn more, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="6c410-124">深入瞭解其他系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="6c410-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="6c410-125">關於 Microsoft 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="6c410-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="6c410-126">關於 SharePoint 線上系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="6c410-126">About the SharePoint Online admin role</span></span>](/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="6c410-127">關於商務用 Skype 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="6c410-127">About the Skype for Business admin role</span></span>](/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="6c410-128">使用 Microsoft 團隊系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="6c410-128">Use Microsoft Teams admin role</span></span>](/MicrosoftTeams/using-admin-roles)