---
title: 設定電子郵件轉寄
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 使用 Office365 設定電子郵件轉寄至一或多個電子郵件帳戶。
ms.openlocfilehash: b5612a915fce21e9e9865fca6cb2275d8af17bd2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242405"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="2cdad-103">設定 Microsoft 365 中的電子郵件轉寄功能</span><span class="sxs-lookup"><span data-stu-id="2cdad-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="2cdad-104">做為組織的系統管理員，您可能需要設定使用者信箱的電子郵件轉寄功能的公司需求。</span><span class="sxs-lookup"><span data-stu-id="2cdad-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="2cdad-105">電子郵件轉寄功能可讓您將傳送至使用者信箱的電子郵件轉寄至組織內部或外部的其他使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="2cdad-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cdad-106">您可以使用輸出垃圾郵件篩選原則來控制自動轉寄給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="2cdad-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="2cdad-107">如需詳細資訊，請參閱[在 Microsoft 365 中控制自動外部電子郵件轉接](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)。</span><span class="sxs-lookup"><span data-stu-id="2cdad-107">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="2cdad-108">設定電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="2cdad-108">Configure email forwarding</span></span>

<span data-ttu-id="2cdad-109">在您設定電子郵件轉發之前，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="2cdad-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="2cdad-110">一旦您設定了電子郵件轉寄功能，就只會轉寄傳送給 *寄件者* 信箱的 **新** 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2cdad-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="2cdad-111">電子郵件轉寄要求 [  *寄件者*  ] 帳戶具有授權。</span><span class="sxs-lookup"><span data-stu-id="2cdad-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="2cdad-112">如果您正在設定電子郵件轉寄功能，因為使用者已離開您的組織，另一個選項是 [將其信箱轉換成共用信箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="2cdad-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="2cdad-113">這樣可以讓數個人員存取它。</span><span class="sxs-lookup"><span data-stu-id="2cdad-113">This way several people can access it.</span></span> <span data-ttu-id="2cdad-114">不過，共用信箱不能超過50GB。</span><span class="sxs-lookup"><span data-stu-id="2cdad-114">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="2cdad-115">您必須是 Microsoft 365 的 Exchange 管理員或全域系統管理員，才可執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="2cdad-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="2cdad-116">如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md)的主題。</span><span class="sxs-lookup"><span data-stu-id="2cdad-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="2cdad-117">在系統管理中心中，移至 [ **使用者** 作用中 \> **[使用者](https://go.microsoft.com/fwlink/p/?linkid=834822)** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2cdad-117">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="2cdad-118">選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2cdad-118">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="2cdad-119">在 [ **郵件** ] 索引標籤上，選取 [ **管理電子郵件轉發**]。</span><span class="sxs-lookup"><span data-stu-id="2cdad-119">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="2cdad-120">在 [電子郵件轉寄] 頁面上，選取 [ **轉寄所有傳送至此信箱的電子郵件**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="2cdad-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="2cdad-121">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2cdad-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="2cdad-122">選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="2cdad-122">Select **Save changes**.</span></span>

    <span data-ttu-id="2cdad-123">**若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="2cdad-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="2cdad-124">若要深入瞭解，請參閱 [使用規則來自動轉寄郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="2cdad-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="2cdad-125">或者，在系統管理中心 [建立通訊群組](../setup/create-distribution-lists.md)， [新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="2cdad-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="2cdad-126">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="2cdad-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="2cdad-127">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="2cdad-127">If you do, email forwarding will stop.</span></span>