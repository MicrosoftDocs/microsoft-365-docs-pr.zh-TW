---
title: 管理自助註冊訂閱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: 瞭解如何管理組織的免費自助註冊訂閱。
ms.date: 03/17/2021
ms.openlocfilehash: 741c9e0b45f127ffc0753b34982073f90c525d5b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536067"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="54c9b-103">管理自助註冊訂閱</span><span class="sxs-lookup"><span data-stu-id="54c9b-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="54c9b-104">何謂自助註冊訂閱？</span><span class="sxs-lookup"><span data-stu-id="54c9b-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="54c9b-105">您組織中的使用者可以使用有限數目的免費自助註冊訂閱來註冊。</span><span class="sxs-lookup"><span data-stu-id="54c9b-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="54c9b-106">使用者只能為自己註冊和使用自助註冊訂閱服務。</span><span class="sxs-lookup"><span data-stu-id="54c9b-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="54c9b-107">您可以封鎖使用者的註冊，以及刪除使用者已註冊的免費訂閱，以管理自助註冊訂閱。</span><span class="sxs-lookup"><span data-stu-id="54c9b-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="54c9b-108">如需自助註冊和可用訂閱的詳細資訊，請參閱 [在您的組織中使用自助註冊](../../admin/misc/self-service-sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="54c9b-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="54c9b-109">查看自助註冊訂閱清單</span><span class="sxs-lookup"><span data-stu-id="54c9b-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="54c9b-110">在系統管理中心，移至 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">您的產品</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="54c9b-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="54c9b-111">在 [ **產品** ] 索引標籤上，選取 [篩選] 圖示，然後選取 [ **自由**]。</span><span class="sxs-lookup"><span data-stu-id="54c9b-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="54c9b-112">隨即會顯示所有自助註冊訂閱清單。</span><span class="sxs-lookup"><span data-stu-id="54c9b-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="54c9b-113">這些訂閱與自助購買訂閱有何不同？</span><span class="sxs-lookup"><span data-stu-id="54c9b-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="54c9b-114">自助註冊訂閱是免費的，可提供更大的產品清單，而非自助購買訂閱。</span><span class="sxs-lookup"><span data-stu-id="54c9b-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="54c9b-115">當使用者註冊「自助購買」訂閱時，他們會負責支付服務。</span><span class="sxs-lookup"><span data-stu-id="54c9b-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="54c9b-116">自助購買訂閱只適用于電源平台產品 (Power BI、Power Apps 和 Power Automate) 、Project 和 Visio。</span><span class="sxs-lookup"><span data-stu-id="54c9b-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="54c9b-117">如需詳細資訊，請參閱 [自助購買常見問題](self-service-purchase-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="54c9b-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.yml).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="54c9b-118">封鎖使用者進行註冊</span><span class="sxs-lookup"><span data-stu-id="54c9b-118">Block users from signing up</span></span>

<span data-ttu-id="54c9b-119">您可以搭配 **AllowAdHocSubscriptions** 參數使用 [**MsolCompanySettings 指令程式**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0)，控制使用者是否可以註冊自助註冊訂閱。</span><span class="sxs-lookup"><span data-stu-id="54c9b-119">You use the [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="54c9b-120">如需詳細資訊，請參閱 [如何控制自助設定？](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="54c9b-120">For more information, see [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="54c9b-121">刪除自助註冊訂閱</span><span class="sxs-lookup"><span data-stu-id="54c9b-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54c9b-122">當您刪除自助註冊訂閱時，會封鎖所有使用者存取其資料和電子郵件，以及刪除所有的資料和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="54c9b-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="54c9b-123">在系統管理中心，移至 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">您的產品</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="54c9b-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="54c9b-124">在 [ **產品** ] 索引標籤上，選取 [篩選] 圖示，然後選取 [ **自由**]。</span><span class="sxs-lookup"><span data-stu-id="54c9b-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="54c9b-125">選取您要刪除的自我服務註冊訂閱。</span><span class="sxs-lookup"><span data-stu-id="54c9b-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="54c9b-126">在 [訂閱詳細資料] 頁面上，選取 [ **訂閱和付款設定** ] 區段中的 [ **刪除訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="54c9b-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="54c9b-127">在 [ **刪除訂閱** ] 窗格中，選取核取方塊，然後選取 [ **刪除訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="54c9b-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="54c9b-128">我有封鎖目錄刪除的自助註冊訂閱</span><span class="sxs-lookup"><span data-stu-id="54c9b-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="54c9b-129">個別使用者可以註冊的自助註冊產品，也會建立來賓使用者，以便在 Azure AD 目錄中進行驗證。</span><span class="sxs-lookup"><span data-stu-id="54c9b-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="54c9b-130">為了避免資料遺失，這些自助產品會封鎖目錄刪除，直到完全從目錄中刪除。</span><span class="sxs-lookup"><span data-stu-id="54c9b-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="54c9b-131">它們只可由 Azure AD 系統管理員刪除。如需詳細資訊，請參閱[Delete directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto)。</span><span class="sxs-lookup"><span data-stu-id="54c9b-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>
