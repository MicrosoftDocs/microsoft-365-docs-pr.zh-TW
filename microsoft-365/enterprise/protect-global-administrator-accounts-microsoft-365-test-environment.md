---
title: 保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用下列步驟來保護 Microsoft 365 企業版測試環境中的全域系統管理員帳戶。
ms.openlocfilehash: 32e5983532c89c6ada106ed32d8ef3eabd5dc569
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801388"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9ef9a-103">保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="9ef9a-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9ef9a-104">*這個測試實驗室指南只能用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="9ef9a-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9ef9a-105">您可以防止數位攻擊您的組織藉由確保您的系統管理員帳戶會盡可能的安全。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="9ef9a-106">本文說明如何使用 Azure Active Directory (Azure AD) 條件式存取原則來保護全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="9ef9a-107">有兩個階段，以保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="9ef9a-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="9ef9a-108">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="9ef9a-109">保護您專用的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-109">Protect your dedicated global administrator account.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="9ef9a-111">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9ef9a-112">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="9ef9a-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9ef9a-113">如果您只想以具有最小需求的輕量型方式測試全域系統管理員帳戶保護，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9ef9a-114">如果您想要在模擬的企業中測試全域系統管理員帳戶保護，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ef9a-115">測試保護不需要模擬的企業測試環境，其中包含的模擬內部網路的全域系統管理員帳戶連線至網際網路和 Active Directory 網域服務 (AD DS) 的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="9ef9a-116">它提供了此選項，讓您可以測試全域系統管理員帳戶保護與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="9ef9a-117">階段 2： 設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="9ef9a-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="9ef9a-118">首先，建立新的使用者帳戶為專用的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="9ef9a-119">個別索引標籤上，開啟[Microsoft 365 系統管理中心](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="9ef9a-120">按一下 [**使用者 > 作用中使用者**]，然後按一下 [**新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="9ef9a-121">在 [**新增使用者**] 窗格中，輸入**DedicatedAdmin**中**第一個名稱**、**顯示名稱**和**使用者名稱**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="9ef9a-122">按一下 [**密碼**] 和 [**讓我建立密碼**，然後輸入 [強式密碼。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="9ef9a-123">此新帳戶的密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="9ef9a-124">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-124">Click **Next**.</span></span>
6. <span data-ttu-id="9ef9a-125">在 [**指派產品授權**] 窗格中，選取 [ **Microsoft 365 E5**或**Office 365 E5**，，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="9ef9a-126">在 [**選擇性設定**] 窗格中，按一下 [**角色**]，然後選取**系統管理中心存取**並**全域系統管理員**。按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="9ef9a-127">在上**幾乎大功告成**] 窗格中，按一下 [**完成 [新增**]，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="9ef9a-128">接下來，建立名為 GlobalAdmins 的新群組，並將 DedicatedAdmin 帳戶新增至它。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="9ef9a-129">在**Microsoft 365 系統管理中心**] 索引標籤上，按一下 [**群組**]，請在左側導覽中，，，然後按一下 [**群組**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="9ef9a-130">按一下 [**新增群組**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="9ef9a-131">在 [**選擇群組類型**] 窗格中，選取 [**安全性**]，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="9ef9a-132">在 [**設定 [基本**] 窗格中，按一下 [**建立群組**]，然後按一下 [**關閉**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="9ef9a-133">在 [**檢閱並完成新增群組**] 窗格中，輸入**GlobalAdmins**，，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="9ef9a-134">在群組清單中，按一下 [ **GlobalAdmins**群組]。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="9ef9a-135">在**GlobalAdmins** ] 窗格中，按一下 [**成員**]，然後按一下 [**檢視所有及管理成員**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="9ef9a-136">在**GlobalAdmins** ] 窗格中，按一下 [**新增成員**、 選取**DedicatedAdmin**帳戶與您的全域系統管理員帳戶，，然後按一下 [**儲存 > Close > 關閉**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="9ef9a-137">接下來，建立需要的全域系統管理員帳戶的多重要素驗證，並拒絕驗證登入風險中或高時的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="9ef9a-138">此第一個原則需要所有的全域系統管理員帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="9ef9a-139">在瀏覽器的新索引標籤，移至 [ [https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="9ef9a-140">按一下 [ **Azure Active Directory > 安全性 > 條件式存取**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="9ef9a-141">在 [**條件式存取 – 原則**] 窗格中，按一下 [**基準線原則： 系統管理員 （預覽） 需要 MFA**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="9ef9a-142">在 [**比較基準原則**] 窗格中，按一下 [**立即 > 儲存使用原則**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="9ef9a-143">以全域系統管理員帳戶驗證登入風險中或高時此第二個原則封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="9ef9a-144">在 [**條件式存取 – 原則**] 窗格中，按一下 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="9ef9a-145">在 [**新增**] 窗格中，輸入**名稱**的**全域系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="9ef9a-146">在 [**指派**] 區段中，按一下 [**使用者和群組**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="9ef9a-147">在 [**使用者和群組**] 窗格的 [**包含**] 索引標籤中，按一下 [**選取使用者及群組 > 使用者和群組 >，請選取**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="9ef9a-148">在 [**選取**] 窗格中，按一下 [ **GlobalAdmins** ] 群組中，然後按一下 [**選取 > 完成**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="9ef9a-149">在 [**指派**] 區段中，按一下 [**條件**]。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="9ef9a-150">在 [**條件**] 窗格中，按一下 [**登入風險**、 按一下 [**是]** 的**設定**，按一下 [**高**] 和 [**中等**，，然後按一下**選取**並**完成**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="9ef9a-151">在 [**新增**] 窗格中的 [**存取控制**] 區段中，按一下 [**授與**]。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="9ef9a-152">在 [**授與**] 窗格中，按一下 [**封鎖存取**]，然後按一下 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="9ef9a-153">在 [**新增**] 窗格中，**啟用原則**，請按一下 [ \*\*\*\* ，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="9ef9a-154">關閉 [ **Azure 入口網站**和**Microsoft 365 系統管理中心**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="9ef9a-155">若要測試的第一個原則，請登出，並使用 DedicatedAdmin 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="9ef9a-156">應該會提示您設定 MFA。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="9ef9a-157">此示範，將第一個會被套用原則。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="9ef9a-158">在身分識別階段中的資訊，以及保護您的全域系統管理員帳戶，在生產環境中的連結，請參閱[保護全域系統管理員帳戶](identity-create-protect-global-admins.md#identity-global-admin)的步驟。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="9ef9a-159">下一步</span><span class="sxs-lookup"><span data-stu-id="9ef9a-159">Next step</span></span>

<span data-ttu-id="9ef9a-160">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="9ef9a-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ef9a-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9ef9a-161">See also</span></span>

[<span data-ttu-id="9ef9a-162">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="9ef9a-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="9ef9a-163">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="9ef9a-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9ef9a-164">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="9ef9a-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9ef9a-165">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="9ef9a-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
