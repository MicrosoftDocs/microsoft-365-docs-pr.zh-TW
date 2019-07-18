---
title: 保護您的系統管理員帳戶
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 了解如何設定和保護您的系統管理員帳戶。
ms.openlocfilehash: 33bf7f8a2a1e666a7822be1d52ac2d81fc681230
ms.sourcegitcommit: 75b97d1ff617bc4b1b0ef9135dfe6a8842ea1b52
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "35772470"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="ffaad-103">保護您的系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="ffaad-103">Protect your administrator accounts</span></span>

<span data-ttu-id="ffaad-104">系統管理員帳戶會隨附提升的權限，因為它們是有價值的目標的駭客和網路罪犯。</span><span class="sxs-lookup"><span data-stu-id="ffaad-104">Because the admin accounts come with elevated privileges, they are valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="ffaad-105">本文說明：</span><span class="sxs-lookup"><span data-stu-id="ffaad-105">This article describes:</span></span>

- <span data-ttu-id="ffaad-106">如何設定緊急情況納入考量的其他系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="ffaad-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="ffaad-107">如何保護這些帳戶。</span><span class="sxs-lookup"><span data-stu-id="ffaad-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="ffaad-108">當您註冊 Microsoft 365 商務版，並輸入您的資訊時，會自動成為全域系統管理員。全域系統管理員具有使用者帳戶的最終控制項和其他所有設定在 Microsoft 系統管理中心中，但有許多不同種類的系統管理員帳戶具有不同程度的存取。</span><span class="sxs-lookup"><span data-stu-id="ffaad-108">When you sign up for Microsoft 365 Business and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="ffaad-109">請參閱[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)的系統管理員角色的每一種不同的存取層級的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ffaad-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="ffaad-110">建立其他系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="ffaad-110">Create additional admin accounts</span></span>

<span data-ttu-id="ffaad-111">使用系統管理員帳戶僅適用於管理。</span><span class="sxs-lookup"><span data-stu-id="ffaad-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="ffaad-112">系統管理員應該有個別的使用者帳戶的 Office 應用程式的一般用於與僅使用其時管理帳戶，裝置和其他系統函數工作時所需的系統管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="ffaad-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts, devices and while working on other admin functions.</span></span> <span data-ttu-id="ffaad-113">它也是系統管理員帳戶的 Microsoft 365 商務版授權移除，因此您不需要支付它們是個好主意。</span><span class="sxs-lookup"><span data-stu-id="ffaad-113">It is also a good idea to remove the Microsoft 365 Business license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="ffaad-114">想要設定至少一個其他的全域系統管理員帳戶，將系統管理存取權授與另一個受信任的員工。</span><span class="sxs-lookup"><span data-stu-id="ffaad-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="ffaad-115">您也可以建立不同的系統管理員帳戶的使用者管理 （此角色會呼叫**使用者管理系統管理員**）。</span><span class="sxs-lookup"><span data-stu-id="ffaad-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="ffaad-116">請參閱[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ffaad-116">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for more information.</span></span>

<span data-ttu-id="ffaad-117">若要建立其他系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="ffaad-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="ffaad-118">移至<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">系統管理中心</a>，然後選擇 [**使用者**\>左側的 **[作用中使用者**</span><span class="sxs-lookup"><span data-stu-id="ffaad-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![在左側導覽中選擇使用者，然後作用中使用者](media/Activeusers.png)

2. <span data-ttu-id="ffaad-120">在 [**作用中使用者**] 頁面上選取 [**新增使用者**]，在頁面頂端和在 [**新增使用者**] 面板上，輸入名稱，以及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="ffaad-120">On the **Active users** page select **Add a user** on the top of the page and on the **New user** panel,  enter the name and other information.</span></span>
3. <span data-ttu-id="ffaad-121">依序展開 [**角色**] 區段中，並選擇**全域系統管理員**授與此使用者的全域系統管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="ffaad-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="ffaad-122">您也可以選擇**自訂的系統管理員**，然後選擇 [任何會顯示角色。</span><span class="sxs-lookup"><span data-stu-id="ffaad-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="ffaad-123">在 [備用電子郵件地址] 文字方塊中輸入備用電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ffaad-123">Enter an alternate email in the Alternative email address text box.</span></span> <span data-ttu-id="ffaad-124">您可以使用這個地址來復原您的密碼資訊，如果您要取得鎖定。全域系統管理員，帳單會傳送到這個地址。</span><span class="sxs-lookup"><span data-stu-id="ffaad-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![選擇系統管理員角色](media/adminroles.png)
    
4. <span data-ttu-id="ffaad-126">在 [**產品授權**] 區段中，移動選取器**Microsoft 365 商務**版來**關閉**使用中] 及 [**產品授權沒有建立使用者\*\*\*\*上**。</span><span class="sxs-lookup"><span data-stu-id="ffaad-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![選擇 [產品授權](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="ffaad-128">建立緊急系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="ffaad-128">Create an emergency admin account</span></span>

<span data-ttu-id="ffaad-129">您也應該建立未設定，以多重要素驗證 (MFA) 讓您不小心鎖定自行備份帳戶 （例如如果您遺失您使用作為驗證的第二的電話）。</span><span class="sxs-lookup"><span data-stu-id="ffaad-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you are using as a second from of verification).</span></span> <span data-ttu-id="ffaad-130">請確定此帳戶的密碼是片語或，至少有 16 個字元長時間。</span><span class="sxs-lookup"><span data-stu-id="ffaad-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="ffaad-131">這通常稱為 「 中斷玻璃帳戶 」。</span><span class="sxs-lookup"><span data-stu-id="ffaad-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="ffaad-132">建立您自己的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="ffaad-132">Create a user account for yourself</span></span>

<span data-ttu-id="ffaad-133">使用您的使用者帳戶來參與共同作業與您的組織，包括檢查郵件。</span><span class="sxs-lookup"><span data-stu-id="ffaad-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="ffaad-134">這表示您的系統管理員認證可能會類似於*Alice.Chavez<span></span>@Contoso.org*及一般使用者帳戶，您可能會類似於*Alice<span></span>@Contoso.com*。</span><span class="sxs-lookup"><span data-stu-id="ffaad-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="ffaad-135">若要建立新的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="ffaad-135">To create a new user account:</span></span>
1. <span data-ttu-id="ffaad-136">移至<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">系統管理中心</a>，然後選擇 [**使用者**\>左側的 **[作用中使用者**</span><span class="sxs-lookup"><span data-stu-id="ffaad-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="ffaad-137">在 [**作用中使用者**] 頁面上選取 [**新增使用者**]，在頁面頂端和在 [**新增使用者**] 面板上，輸入名稱，以及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="ffaad-137">On the **Active users** page select **Add a user** on the top of the page and on the **New user** panel,  enter the name and other information.</span></span>
3. <span data-ttu-id="ffaad-138">依序展開 [**角色**] 區段中，然後選擇 [**使用者 （沒有管理存取）**。</span><span class="sxs-lookup"><span data-stu-id="ffaad-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="ffaad-139">在 [**產品授權**] 區段中，將選擇器**Microsoft 365 商務**版往**上**。</span><span class="sxs-lookup"><span data-stu-id="ffaad-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="ffaad-140">註冊每個這些帳戶的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="ffaad-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="ffaad-141">其他建議</span><span class="sxs-lookup"><span data-stu-id="ffaad-141">Additional recommendations</span></span>

- <span data-ttu-id="ffaad-142">請務必針對多重要素驗證也設定系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="ffaad-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="ffaad-143">我們將顯示您如何執行這項操作中[設定條件式存取原則](m365-campaigns-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ffaad-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="ffaad-144">使用系統管理員帳戶之前, 關閉所有不相關的瀏覽器工作階段和應用程式，包括個人電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="ffaad-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="ffaad-145">您也可以使用私人，或 incognito 瀏覽器視窗中。</span><span class="sxs-lookup"><span data-stu-id="ffaad-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="ffaad-146">完成之後系統管理工作，請務必先登出瀏覽器工作階段。</span><span class="sxs-lookup"><span data-stu-id="ffaad-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>