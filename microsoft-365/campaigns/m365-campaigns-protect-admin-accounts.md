---
title: 保護您的系統管理員帳戶
f1.keywords:
- NOCSH
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
description: 瞭解如何設定和保護您的系統管理員帳戶。
ms.openlocfilehash: 2104697320308b329f9fde1b6984c15f9814f9ef
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633650"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="3f33b-103">保護您的系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="3f33b-103">Protect your administrator accounts</span></span>

<span data-ttu-id="3f33b-104">因為系統管理員帳戶具有較高的許可權，所以它們是駭客和網路罪犯的重要目標。</span><span class="sxs-lookup"><span data-stu-id="3f33b-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="3f33b-105">本文說明：</span><span class="sxs-lookup"><span data-stu-id="3f33b-105">This article describes:</span></span>

- <span data-ttu-id="3f33b-106">如何為緊急情況設定額外的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="3f33b-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="3f33b-107">如何保護這些帳戶。</span><span class="sxs-lookup"><span data-stu-id="3f33b-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="3f33b-108">當您註冊 Microsoft 365 並輸入您的資訊時，您會自動成為全域系統管理員。全域管理員在 Microsoft 系統管理中心內具有使用者帳戶和所有其他設定的最終控制權，但不同類型的系統管理員帳戶具有不同的存取程度。</span><span class="sxs-lookup"><span data-stu-id="3f33b-108">When you sign up for Microsoft 365 and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="3f33b-109">如需每種系統管理員角色之不同存取層級的詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="3f33b-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="3f33b-110">建立其他系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="3f33b-110">Create additional admin accounts</span></span>

<span data-ttu-id="3f33b-111">僅使用系統管理帳戶進行管理。</span><span class="sxs-lookup"><span data-stu-id="3f33b-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="3f33b-112">系統管理員應該要有個別的使用者帳戶，以便定期使用 Office 應用程式，且只有在需要管理帳戶和裝置時，以及在處理其他系統管理功能時，才使用其管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="3f33b-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="3f33b-113">最好從系統管理員帳戶中移除 Microsoft 365 授權，這樣您就不需要付費。</span><span class="sxs-lookup"><span data-stu-id="3f33b-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="3f33b-114">您必須設定至少一個額外的全域系統管理員帳戶，以授與其他受信任員工的系統管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="3f33b-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="3f33b-115">您也可以為使用者管理建立個別的系統管理員帳戶（此角色稱為「**使用者管理管理員**」）。</span><span class="sxs-lookup"><span data-stu-id="3f33b-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="3f33b-116">如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="3f33b-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="3f33b-117">若要建立其他系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="3f33b-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="3f33b-118">移至 [系統<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a>]，然後選擇左側導覽中的 [**使用者** \> ] [作用中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="3f33b-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![選擇左側流覽中的 [使用者] 和 [作用中使用者]](../media/Activeusers.png)

2. <span data-ttu-id="3f33b-120">在 [作用中**使用者**] 頁面上，選取頁面頂端的 [**新增使用者**]，然後在 [**新增使用者**] 面板上，輸入名稱及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="3f33b-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="3f33b-121">展開 [**角色**] 區段，然後選擇 [**全域管理員**]，以授予此使用者全域管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="3f33b-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="3f33b-122">您也可以選擇**自訂的系統管理員**，並選擇任何顯示的角色。</span><span class="sxs-lookup"><span data-stu-id="3f33b-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="3f33b-123">在 [**其他電子郵件地址**] 文字方塊中輸入備選電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3f33b-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="3f33b-124">您可以使用此位址，當您鎖定時，復原您的密碼資訊。若為全域系統管理員，則也會傳送帳單報表至此位址。</span><span class="sxs-lookup"><span data-stu-id="3f33b-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![選擇系統管理員角色](../media/adminroles.png)
    
4. <span data-ttu-id="3f33b-126">在 [**產品授權**] 區段中，將**Microsoft 365 商務**版的選取器移至 [**關閉**]，然後將 [**建立沒有產品許可證的使用者**]**開啟**為 [</span><span class="sxs-lookup"><span data-stu-id="3f33b-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![選擇產品授權](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="3f33b-128">建立緊急管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="3f33b-128">Create an emergency admin account</span></span>

<span data-ttu-id="3f33b-129">您也應該使用多重要素驗證（MFA）來建立未設定的備份帳戶，這樣您就不會不慎鎖定自己，例如，當您因第二種形式的驗證而遺失您的電話時。</span><span class="sxs-lookup"><span data-stu-id="3f33b-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="3f33b-130">請確定此帳戶的密碼為片語或至少16個字元的長度。</span><span class="sxs-lookup"><span data-stu-id="3f33b-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="3f33b-131">這通常稱為「斷玻璃帳戶」。</span><span class="sxs-lookup"><span data-stu-id="3f33b-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="3f33b-132">為自己建立使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="3f33b-132">Create a user account for yourself</span></span>

<span data-ttu-id="3f33b-133">使用您的使用者帳戶參與組織的共同作業，包括檢查郵件。</span><span class="sxs-lookup"><span data-stu-id="3f33b-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="3f33b-134">這表示您的系統管理員認證可能類似于*小紅 Chavez<span></span>@Contoso. org*和一般使用者帳戶可能類似*alice<span></span>@Contoso .com*。</span><span class="sxs-lookup"><span data-stu-id="3f33b-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="3f33b-135">若要建立新的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="3f33b-135">To create a new user account:</span></span>
1. <span data-ttu-id="3f33b-136">移至 [系統<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a>]，然後選擇左側導覽中的 [**使用者** \> ] [作用中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="3f33b-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="3f33b-137">在 [作用中**使用者**] 頁面上，選取頁面頂端的 [**新增使用者**]，然後在 [**新增使用者**] 面板上，輸入名稱及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="3f33b-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="3f33b-138">展開 [**角色**] 區段，然後選擇 [**使用者] （無管理存取）**。</span><span class="sxs-lookup"><span data-stu-id="3f33b-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="3f33b-139">在 [**產品授權**] 區段中，將**Microsoft 365 商務**版的選取器移至 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="3f33b-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="3f33b-140">針對多重要素驗證註冊這些帳戶</span><span class="sxs-lookup"><span data-stu-id="3f33b-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="3f33b-141">其他建議</span><span class="sxs-lookup"><span data-stu-id="3f33b-141">Additional recommendations</span></span>

- <span data-ttu-id="3f33b-142">請確定系統管理員帳戶也設定為進行多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="3f33b-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="3f33b-143">我們將在[設定條件式存取原則](m365-campaigns-conditional-access.md)中示範如何執行此動作。</span><span class="sxs-lookup"><span data-stu-id="3f33b-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="3f33b-144">使用系統管理員帳戶之前，請先關閉所有不相關的瀏覽器會話和應用程式（包括個人電子郵件帳戶）。</span><span class="sxs-lookup"><span data-stu-id="3f33b-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="3f33b-145">您也可以在私人或 incognito 瀏覽器視窗中使用。</span><span class="sxs-lookup"><span data-stu-id="3f33b-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="3f33b-146">完成系統管理工作之後，請務必登出瀏覽器會話。</span><span class="sxs-lookup"><span data-stu-id="3f33b-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>
