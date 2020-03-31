---
title: 比較 Office 365 中的群組
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: 了解您可以在 Office 365 中使用的群組類型。
ms.openlocfilehash: 7d0a18606918884381b0bf7863cfac6cafb29c29
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894596"
---
# <a name="compare-groups"></a><span data-ttu-id="e9326-103">比較群組</span><span class="sxs-lookup"><span data-stu-id="e9326-103">Compare groups</span></span>

<span data-ttu-id="e9326-104">在 Microsoft 365 系統管理中心的 [群組]\*\*\*\* 區段中，您可以建立和管理以下類型的群組：</span><span class="sxs-lookup"><span data-stu-id="e9326-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="e9326-105">**Office 365 群組**用來在公司內部和外部的使用者之間共同作業。</span><span class="sxs-lookup"><span data-stu-id="e9326-105">**Office 365 groups** are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="e9326-106">**通訊群組**用來傳送通知給一群人。</span><span class="sxs-lookup"><span data-stu-id="e9326-106">**Distribution groups** are used for sending notifications to a group of people.</span></span>
- <span data-ttu-id="e9326-107">**安全性群組**用來授權存取資源，例如 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="e9326-107">**Security groups** are used for granting access to resources such as SharePoint sites.</span></span>
- <span data-ttu-id="e9326-108">**擁有郵件功能的安全性群組**用來授權存取資源 (如 SharePoint)，以及將通知透過電子郵件傳送給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="e9326-108">**Mail-enabled security groups** are used for granting access to resources such as SharePoint, and emailing notifications to those users.</span></span>
- <span data-ttu-id="e9326-109">如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址)，就會使用**共用信箱**。</span><span class="sxs-lookup"><span data-stu-id="e9326-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="office-365-groups"></a><span data-ttu-id="e9326-110">Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="e9326-110">Office 365 groups</span></span>

<span data-ttu-id="e9326-111">Office 365 群組用來在公司內部和外部的使用者之間共同作業。</span><span class="sxs-lookup"><span data-stu-id="e9326-111">Office 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="e9326-112">透過每個 Office 365 群組，成員可以取得交談、檔案和行事曆活動以及 Planner 的群組電子郵件與共用工作區。</span><span class="sxs-lookup"><span data-stu-id="e9326-112">With each Office 365 group, members get a group email and shared workspace for conversations, files, and calendar events, and a Planner.</span></span>

<span data-ttu-id="e9326-113">只要[系統管理員啟用](manage-guest-access-in-groups.md)這項功能，您就可以將組織外部的人員新增至群組。</span><span class="sxs-lookup"><span data-stu-id="e9326-113">You can add people from outside your organization to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="e9326-114">您也可以允許外部寄件者將電子郵件傳送到群組電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e9326-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="e9326-115">Office 365 群組可以[在 Azure Active Directory 中針對動態成員資格設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)，以便根據使用者屬性 (例如部門、位置、職稱等) 自動新增或移除群組成員。</span><span class="sxs-lookup"><span data-stu-id="e9326-115">Office 365 groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="e9326-116">Office 365 群組可透過行動裝置應用程式存取，例如 iOS 版 Outlook 和 Android 版 Outlook。</span><span class="sxs-lookup"><span data-stu-id="e9326-116">Office 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="e9326-117">如果[系統管理員已啟用](allow-members-to-send-as-or-send-on-behalf-of-group.md)此功能，則群組成員可以以群組電子郵件地址的身分傳送或代表其傳送。</span><span class="sxs-lookup"><span data-stu-id="e9326-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="e9326-118">通訊群組</span><span class="sxs-lookup"><span data-stu-id="e9326-118">Distribution groups</span></span>

<span data-ttu-id="e9326-119">[通訊群組](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)用來傳送通知給一群人。</span><span class="sxs-lookup"><span data-stu-id="e9326-119">[Distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="e9326-120">如果系統管理員已啟用該功能，他們就能接收外部電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e9326-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="e9326-121">如果您需要將資訊廣播給一群人，例如「大樓 A 的人員」或「Contoso 的每個人」，則最適合使用通訊群組。</span><span class="sxs-lookup"><span data-stu-id="e9326-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

## <a name="security-groups"></a><span data-ttu-id="e9326-122">安全性群組</span><span class="sxs-lookup"><span data-stu-id="e9326-122">Security groups</span></span>

<span data-ttu-id="e9326-123">[安全性群組](../email/create-edit-or-delete-a-security-group.md)用來授權存取 Office 365 資源，例如 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="e9326-123">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Office 365 resources, such as SharePoint.</span></span> <span data-ttu-id="e9326-124">由於您只需要管理群組，而非將使用者個別新增至每個資源，它們能讓系統管理更容易。</span><span class="sxs-lookup"><span data-stu-id="e9326-124">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="e9326-125">安全性群組可以包含使用者或裝置。</span><span class="sxs-lookup"><span data-stu-id="e9326-125">Security groups can contain users or devices.</span></span> <span data-ttu-id="e9326-126">為裝置建立可搭配行動裝置管理服務 (例如 Intune) 使用的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e9326-126">Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="e9326-127">安全性群組可以[在 Azure Active Directory 中針對動態成員資格設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)，以便根據使用者屬性 (例如部門、位置、職稱等) 或裝置屬性 (例如作業系統版本) 自動新增或移除群組成員。</span><span class="sxs-lookup"><span data-stu-id="e9326-127">Security groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="e9326-128">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="e9326-128">Mail-enabled security groups</span></span>

<span data-ttu-id="e9326-129">擁有郵件功能的安全性群組運作方式與一般安全性群組相同，除了無法透過 Azure Active Directory 動態管理且不能包含裝置以外。</span><span class="sxs-lookup"><span data-stu-id="e9326-129">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="e9326-130">其中包括能夠將郵件傳送給群組的所有成員。</span><span class="sxs-lookup"><span data-stu-id="e9326-130">They include the ability to send mail to all the members of the group.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="e9326-131">共用信箱</span><span class="sxs-lookup"><span data-stu-id="e9326-131">Shared mailboxes</span></span>

<span data-ttu-id="e9326-132">如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址、接待處或其他可能由多人共用的功能)，就會使用[共用信箱](../email/create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="e9326-132">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="e9326-133">如果系統管理員已啟用此功能，共用信箱就可以接收外部電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e9326-133">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="e9326-134">擁有群組信箱權限的使用者可以以信箱電子郵件地址的身分傳送或代表其傳送 (如果系統管理員已授與使用者執行該動作的權限)。</span><span class="sxs-lookup"><span data-stu-id="e9326-134">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="e9326-135">這對於說明和支援信箱特別有用，因為使用者可以透過「Contoso 支援」或「大樓 A 接待處」傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e9326-135">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="e9326-136">目前無法將共用信箱移轉至 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="e9326-136">Currently it's not possible to migrate a shared mailbox to an Office 365 group.</span></span> <span data-ttu-id="e9326-137">這是您需要的內容嗎？</span><span class="sxs-lookup"><span data-stu-id="e9326-137">Is this something you want?</span></span> <span data-ttu-id="e9326-138">請告訴我們。</span><span class="sxs-lookup"><span data-stu-id="e9326-138">Let us know.</span></span> <span data-ttu-id="e9326-139">**[在這裡投票](https://go.microsoft.com/fwlink/?linkid=871518)**。</span><span class="sxs-lookup"><span data-stu-id="e9326-139">**[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e9326-140">相關文章</span><span class="sxs-lookup"><span data-stu-id="e9326-140">Related articles</span></span>

[<span data-ttu-id="e9326-141">了解 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="e9326-141">Learn about Office 365 Groups</span></span>](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
