---
title: 保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用下列步驟來保護 Microsoft 365 企業版測試環境中的全域系統管理員帳戶。
ms.openlocfilehash: 89985f99f5471aab87189e78035062add2c6bad9
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673329"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1d090-103">保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="1d090-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1d090-104">*此測試實驗室指南僅可用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="1d090-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="1d090-105">您可以防止數位攻擊您的組織藉由確保您的系統管理員帳戶會盡可能的安全。</span><span class="sxs-lookup"><span data-stu-id="1d090-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="1d090-106">本文說明如何使用 Azure Active Directory (Azure AD) 條件式存取原則來保護全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="1d090-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="1d090-107">有兩個階段，以保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="1d090-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="1d090-108">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="1d090-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="1d090-109">保護您專用的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="1d090-109">Protect your dedicated global administrator account.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="1d090-111">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="1d090-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1d090-112">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="1d090-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1d090-113">如果您只想以具有最小需求的輕量型方式測試全域系統管理員帳戶保護，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="1d090-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1d090-114">如果您想要在模擬的企業中測試全域系統管理員帳戶保護，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="1d090-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="1d090-115">測試保護不需要模擬的企業測試環境，其中包含的模擬內部網路的全域系統管理員帳戶連線至網際網路和 Active Directory 網域服務 (AD DS) 的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="1d090-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="1d090-116">它提供了此選項，讓您可以測試全域系統管理員帳戶保護與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="1d090-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="1d090-117">階段 2： 設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="1d090-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="1d090-118">首先，建立新的使用者帳戶為專用的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="1d090-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="1d090-119">個別索引標籤上，開啟[Microsoft 365 系統管理中心](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="1d090-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="1d090-120">[**作用中使用者**] 下方按一下 [**新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="1d090-120">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="1d090-121">在 [**新增使用者**] 頁面上，輸入**DedicatedAdmin**中**第一個名稱**、**顯示名稱**和**使用者名稱**。</span><span class="sxs-lookup"><span data-stu-id="1d090-121">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="1d090-122">按一下 [**密碼**] 和 [**讓我建立密碼**，然後輸入 [強式密碼。</span><span class="sxs-lookup"><span data-stu-id="1d090-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="1d090-123">此新帳戶的密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="1d090-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="1d090-124">清除 [**讓這位使用者變更其密碼，當使用者第一次登入**。</span><span class="sxs-lookup"><span data-stu-id="1d090-124">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="1d090-125">按一下 [**角色**]，然後按一下 [**全域系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="1d090-125">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="1d090-126">按一下 [**產品授權**]，然後再開啟的 [ **Enterprise Mobility + Security E5** ] 和 [ **Office 365 企業版 E5 授權**。</span><span class="sxs-lookup"><span data-stu-id="1d090-126">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="1d090-127">按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d090-127">Click **Add**.</span></span>
9. <span data-ttu-id="1d090-128">在**已新增使用者] 頁面上**，清除 [**傳送電子郵件中的密碼**，，然後再按一下 [**關閉**。</span><span class="sxs-lookup"><span data-stu-id="1d090-128">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="1d090-129">接下來，建立名為 GlobalAdmins 的新群組，並將 DedicatedAdmin 帳戶新增至它。</span><span class="sxs-lookup"><span data-stu-id="1d090-129">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="1d090-130">在**Microsoft 365 系統管理中心**] 索引標籤上，按一下左側導覽中，在 [群組] 圖示，然後按一下**群組**。</span><span class="sxs-lookup"><span data-stu-id="1d090-130">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="1d090-131">按一下 [**新增群組**。</span><span class="sxs-lookup"><span data-stu-id="1d090-131">Click **Add a group**.</span></span>
3. <span data-ttu-id="1d090-132">在 [**新增群組**] 頁面上，輸入**GlobalAdmins**。</span><span class="sxs-lookup"><span data-stu-id="1d090-132">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="1d090-133">全域管理員帳戶，按一下 [**選取擁有者**按一下，然後按一下 [**新增 > 關閉**。</span><span class="sxs-lookup"><span data-stu-id="1d090-133">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="1d090-134">在群組清單中，按一下 [ **GlobalAdmins**群組]。</span><span class="sxs-lookup"><span data-stu-id="1d090-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="1d090-135">在**GlobalAdmins**頁面上，按一下 [**編輯成員**]，然後按一下 [**新增成員**。</span><span class="sxs-lookup"><span data-stu-id="1d090-135">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="1d090-136">在清單中，按一下 [ **DedicatedAdmin**帳戶]，然後按一下 [**儲存 > Close > Close > 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="1d090-136">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="1d090-137">接下來，建立需要的全域系統管理員帳戶的多重要素驗證，並拒絕驗證登入風險中或高時的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="1d090-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="1d090-138">此第一個原則需要所有的全域系統管理員帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="1d090-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="1d090-139">在瀏覽器的新索引標籤，移至 [ [https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="1d090-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="1d090-140">按一下 [ **Azure Active Directory > 條件式存取**]。</span><span class="sxs-lookup"><span data-stu-id="1d090-140">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="1d090-141">在 [**條件式存取 – 原則**] 刀鋒視窗中，按一下 [**基準線原則： 系統管理員 （預覽） 需要 MFA**。</span><span class="sxs-lookup"><span data-stu-id="1d090-141">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="1d090-142">**[比較基準原則...**</span><span class="sxs-lookup"><span data-stu-id="1d090-142">On the **Baseline policies…**</span></span> <span data-ttu-id="1d090-143">] 刀鋒視窗上，按一下 [**立即 > 儲存使用原則**。</span><span class="sxs-lookup"><span data-stu-id="1d090-143">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="1d090-144">以全域系統管理員帳戶驗證登入風險中或高時此第二個原則封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="1d090-144">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="1d090-145">在 [**條件式存取 – 原則**] 刀鋒視窗中，按一下 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="1d090-145">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="1d090-146">在 [**新增**] 刀鋒視窗中，輸入**全域系統管理員**在 [**名稱]**。</span><span class="sxs-lookup"><span data-stu-id="1d090-146">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="1d090-147">在 [**指派**] 區段中，按一下 [**使用者和群組**。</span><span class="sxs-lookup"><span data-stu-id="1d090-147">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="1d090-148">在 [**使用者和群組**] 刀鋒視窗的 [**包含**] 索引標籤中，按一下 [**選取使用者及群組 > 使用者和群組 > 選取**。</span><span class="sxs-lookup"><span data-stu-id="1d090-148">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="1d090-149">在 [**選取**] 刀鋒視窗上，按一下 [ **GlobalAdmins > 選取 > 完成**]。</span><span class="sxs-lookup"><span data-stu-id="1d090-149">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="1d090-150">在 [**指派**] 區段中，按一下 [**條件**]。</span><span class="sxs-lookup"><span data-stu-id="1d090-150">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="1d090-151">在 [**條件**] 刀鋒視窗中，按一下 [**登入風險**、 按一下 [**是]** 的**設定**、 按一下 [**高**] 和 [**媒體**，然後按一下**選取**並**完成**。</span><span class="sxs-lookup"><span data-stu-id="1d090-151">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="1d090-152">在 [**新增**] 刀鋒視窗中的 [**存取控制**] 區段中，按一下 [**授與**]。</span><span class="sxs-lookup"><span data-stu-id="1d090-152">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="1d090-153">在 [**授與**] 刀鋒視窗中，按一下 [**封鎖存取**]，然後按一下 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="1d090-153">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="1d090-154">在 [**新增**] 刀鋒視窗上**啟用原則**，請按一下 [ \*\*\*\* ，然後按一下 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="1d090-154">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="1d090-155">關閉 [ **Azure 入口網站**和**Microsoft 365 系統管理中心**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1d090-155">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="1d090-156">若要測試的第一個原則，請登出，並使用 DedicatedAdmin 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="1d090-156">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="1d090-157">應該會提示您的使用者帳戶上設定 MFA。</span><span class="sxs-lookup"><span data-stu-id="1d090-157">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="1d090-158">此示範，將第一個會被套用原則。</span><span class="sxs-lookup"><span data-stu-id="1d090-158">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="1d090-159">在身分識別階段中的資訊，以及保護您的全域系統管理員帳戶，在生產環境中的連結，請參閱[保護全域系統管理員帳戶](identity-create-protect-global-admins.md#identity-global-admin)的步驟。</span><span class="sxs-lookup"><span data-stu-id="1d090-159">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="1d090-160">下一步</span><span class="sxs-lookup"><span data-stu-id="1d090-160">Next step</span></span>

<span data-ttu-id="1d090-161">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="1d090-161">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d090-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1d090-162">See also</span></span>

[<span data-ttu-id="1d090-163">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="1d090-163">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="1d090-164">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="1d090-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1d090-165">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="1d090-165">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1d090-166">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="1d090-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
