---
title: 保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用下列步驟來保護 Microsoft 365 企業版測試環境中的全域系統管理員帳戶。
ms.openlocfilehash: 86b2d325fc710fd8b387bc37cad5f8ea60df001d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353055"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="52631-103">保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="52631-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="52631-104">您可以防止數位攻擊您的組織藉由確保您的系統管理員帳戶會盡可能的安全。</span><span class="sxs-lookup"><span data-stu-id="52631-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="52631-105">本文說明如何使用 Azure Active Directory (Azure AD) 條件式存取原則來保護全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="52631-105">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="52631-106">有兩個階段，以保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="52631-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="52631-107">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="52631-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="52631-108">保護您專用的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="52631-108">Protect your dedicated global administrator account.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="52631-110">按一下[這裡](https://aka.ms/m365etlgstack)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中文件的所有視覺對應。</span><span class="sxs-lookup"><span data-stu-id="52631-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="52631-111">階段 1： 建置 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="52631-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="52631-112">如果您只想以具有最小需求的輕量型方式測試全域系統管理員帳戶保護，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="52631-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="52631-113">如果您想要在模擬的企業中測試全域系統管理員帳戶保護，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="52631-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="52631-114">測試保護不需要模擬的企業測試環境，其中包含的模擬內部網路的全域系統管理員帳戶連線至網際網路和 Active Directory 網域服務 (AD DS) 的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="52631-114">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="52631-115">它提供了此選項，讓您可以測試全域系統管理員帳戶保護與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="52631-115">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="52631-116">階段 2： 設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="52631-116">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="52631-117">首先，建立新的使用者帳戶為專用的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="52631-117">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="52631-118">個別索引標籤上，開啟[Microsoft 365 系統管理中心](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="52631-118">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="52631-119">[**作用中使用者**] 下方按一下 [**新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="52631-119">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="52631-120">在 [**新增使用者**] 頁面上，輸入**DedicatedAdmin**中**第一個名稱**、**顯示名稱**和**使用者名稱**。</span><span class="sxs-lookup"><span data-stu-id="52631-120">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="52631-121">按一下 [**密碼**] 和 [**讓我建立密碼**，然後輸入 [強式密碼。</span><span class="sxs-lookup"><span data-stu-id="52631-121">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="52631-122">此新帳戶的密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="52631-122">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="52631-123">清除 [**讓這位使用者變更其密碼，當使用者第一次登入**。</span><span class="sxs-lookup"><span data-stu-id="52631-123">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="52631-124">按一下 [**角色**]，然後按一下 [**全域系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="52631-124">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="52631-125">按一下 [**產品授權**]，然後再開啟的 [ **Enterprise Mobility + Security E5** ] 和 [ **Office 365 企業版 E5 授權**。</span><span class="sxs-lookup"><span data-stu-id="52631-125">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="52631-126">按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52631-126">Click **Add**.</span></span>
9. <span data-ttu-id="52631-127">在**已新增使用者] 頁面上**，清除 [**傳送電子郵件中的密碼**，，然後再按一下 [**關閉**。</span><span class="sxs-lookup"><span data-stu-id="52631-127">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="52631-128">接下來，建立名為 GlobalAdmins 的新群組，並將 DedicatedAdmin 帳戶新增至它。</span><span class="sxs-lookup"><span data-stu-id="52631-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="52631-129">在**Microsoft 365 系統管理中心**] 索引標籤上，按一下左側導覽中，在 [群組] 圖示，然後按一下**群組**。</span><span class="sxs-lookup"><span data-stu-id="52631-129">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="52631-130">按一下 [**新增群組**。</span><span class="sxs-lookup"><span data-stu-id="52631-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="52631-131">在 [**新增群組**] 頁面上，輸入**GlobalAdmins**。</span><span class="sxs-lookup"><span data-stu-id="52631-131">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="52631-132">全域管理員帳戶，按一下 [**選取擁有者**按一下，然後按一下 [**新增 > 關閉**。</span><span class="sxs-lookup"><span data-stu-id="52631-132">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="52631-133">在群組清單中，按一下 [ **GlobalAdmins**群組]。</span><span class="sxs-lookup"><span data-stu-id="52631-133">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="52631-134">在**GlobalAdmins**頁面上，按一下 [**編輯成員**]，然後按一下 [**新增成員**。</span><span class="sxs-lookup"><span data-stu-id="52631-134">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="52631-135">在清單中，按一下 [ **DedicatedAdmin**帳戶]，然後按一下 [**儲存 > Close > Close > 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="52631-135">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="52631-136">接下來，建立需要的全域系統管理員帳戶的多重要素驗證，並拒絕驗證登入風險中或高時的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="52631-136">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="52631-137">此第一個原則需要所有的全域系統管理員帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="52631-137">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="52631-138">在瀏覽器的新索引標籤，移至 [ [https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="52631-138">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="52631-139">按一下 [ **Azure Active Directory > 條件式存取**]。</span><span class="sxs-lookup"><span data-stu-id="52631-139">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="52631-140">在 [**條件式存取 – 原則**] 刀鋒視窗中，按一下 [**基準線原則： 系統管理員 （預覽） 需要 MFA**。</span><span class="sxs-lookup"><span data-stu-id="52631-140">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="52631-141">**[比較基準原則...**</span><span class="sxs-lookup"><span data-stu-id="52631-141">On the **Baseline policies…**</span></span> <span data-ttu-id="52631-142">] 刀鋒視窗上，按一下 [**立即 > 儲存使用原則**。</span><span class="sxs-lookup"><span data-stu-id="52631-142">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="52631-143">以全域系統管理員帳戶驗證登入風險中或高時此第二個原則封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="52631-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="52631-144">在 [**條件式存取 – 原則**] 刀鋒視窗中，按一下 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="52631-144">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="52631-145">在 [**新增**] 刀鋒視窗中，輸入**全域系統管理員**在 [**名稱]**。</span><span class="sxs-lookup"><span data-stu-id="52631-145">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="52631-146">在 [**指派**] 區段中，按一下 [**使用者和群組**。</span><span class="sxs-lookup"><span data-stu-id="52631-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="52631-147">在 [**使用者和群組**] 刀鋒視窗的 [**包含**] 索引標籤中，按一下 [**選取使用者及群組 > 使用者和群組 > 選取**。</span><span class="sxs-lookup"><span data-stu-id="52631-147">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="52631-148">在 [**選取**] 刀鋒視窗中，按一下 [**完成 GlobalAdmins > 選取 >**。</span><span class="sxs-lookup"><span data-stu-id="52631-148">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="52631-149">在 [**指派**] 區段中，按一下 [**條件**]。</span><span class="sxs-lookup"><span data-stu-id="52631-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="52631-150">在 [**條件**] 刀鋒視窗中，按一下 [**登入風險**、 按一下 [**是]** 的**設定**、 按一下 [**高**] 和 [**媒體**，然後按一下**選取**並**完成**。</span><span class="sxs-lookup"><span data-stu-id="52631-150">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="52631-151">在 [**新增**] 刀鋒視窗中的 [**存取控制**] 區段中，按一下 [**授與**]。</span><span class="sxs-lookup"><span data-stu-id="52631-151">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="52631-152">在 [**授與**] 刀鋒視窗中，按一下 [**封鎖存取**]，然後按一下 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="52631-152">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="52631-153">在 [**新增**] 刀鋒視窗上**啟用原則**，請按一下 [ \*\*\*\* ，然後按一下 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="52631-153">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="52631-154">關閉 [ **Azure 入口網站**和**Microsoft 365 系統管理中心**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="52631-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="52631-155">若要測試的第一個原則，請登出，並使用 DedicatedAdmin 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="52631-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="52631-156">應該會提示您的使用者帳戶上設定 MFA。</span><span class="sxs-lookup"><span data-stu-id="52631-156">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="52631-157">此示範，將第一個會被套用原則。</span><span class="sxs-lookup"><span data-stu-id="52631-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="52631-158">在身分識別階段中的資訊，以及保護您的全域系統管理員帳戶，在生產環境中的連結，請參閱[保護全域系統管理員帳戶](identity-designate-protect-admin-accounts.md#identity-global-admin)的步驟。</span><span class="sxs-lookup"><span data-stu-id="52631-158">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="52631-159">下一步</span><span class="sxs-lookup"><span data-stu-id="52631-159">Next step</span></span>

<span data-ttu-id="52631-160">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="52631-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="52631-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="52631-161">See also</span></span>

[<span data-ttu-id="52631-162">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="52631-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="52631-163">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="52631-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="52631-164">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="52631-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="52631-165">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="52631-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
