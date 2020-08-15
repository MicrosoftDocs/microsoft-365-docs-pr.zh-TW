---
title: 在 Microsoft 365 for enterprise test 環境中保護全域系統管理員帳戶
f1.keywords:
- NOCSH
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
description: 使用這些步驟來保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶。
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695179"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f5934-103">在 Microsoft 365 for enterprise test 環境中保護全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="f5934-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f5934-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="f5934-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="f5934-105">您可以確保您的系統管理員帳戶盡可能安全，以防止組織的數位攻擊。</span><span class="sxs-lookup"><span data-stu-id="f5934-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="f5934-106">本文說明如何使用 Azure Active Directory (Azure AD) 條件式存取原則來保護全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="f5934-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="f5934-107">在 Microsoft 365 企業版測試環境中，保護全域系統管理員帳戶有兩個階段：</span><span class="sxs-lookup"><span data-stu-id="f5934-107">There are two phases to protecting global administrator accounts in your Microsoft 365 for enterprise test environment:</span></span>

1.  <span data-ttu-id="f5934-108">建立適用于企業測試環境的 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f5934-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2.  <span data-ttu-id="f5934-109">保護您的專屬全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="f5934-109">Protect your dedicated global administrator account.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f5934-111">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="f5934-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f5934-112">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="f5934-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f5934-113">如果您只想以輕量的方式測試全域管理員帳戶保護，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="f5934-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f5934-114">如果您想要在模擬的企業中測試全域管理員帳戶保護，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="f5934-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f5934-115">測試全域管理員帳戶保護並不需要模擬的企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="f5934-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="f5934-116">這裡是以選項形式提供，可讓您測試全域管理員帳戶保護，並在代表一般組織的環境中進行試驗。</span><span class="sxs-lookup"><span data-stu-id="f5934-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="f5934-117">階段2：設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f5934-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="f5934-118">首先，建立新的使用者帳戶做為專屬全域管理員。</span><span class="sxs-lookup"><span data-stu-id="f5934-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="f5934-119">在個別的索引標籤上，開啟 [ [Microsoft 365 系統管理中心](https://admin.microsoft.com/)]。</span><span class="sxs-lookup"><span data-stu-id="f5934-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="f5934-120">按一下 [ **使用者 > Active 使用者**]，然後按一下 [ **新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="f5934-121">在 [**新增使用者**] 窗格中，在 **[名字**]、[**顯示名稱**] 和 [使用者**名稱]** 中輸入**DedicatedAdmin** 。</span><span class="sxs-lookup"><span data-stu-id="f5934-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="f5934-122">按一下 [ **密碼**]，然後按一下 **[讓我建立密碼**]，然後輸入強式密碼。</span><span class="sxs-lookup"><span data-stu-id="f5934-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="f5934-123">在安全的位置記錄此新帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="f5934-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="f5934-124">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5934-124">Click **Next**.</span></span>
6. <span data-ttu-id="f5934-125">在 [ **指派產品授權** ] 窗格中，選取 [ **Microsoft 365 E5**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f5934-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="f5934-126">在 [ **選用的設定** ] 窗格中，按一下 [ **角色**]，然後選取 [管理中心] [ **存取** 和 **全域管理員**]。按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f5934-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="f5934-127">在 [ **即將完成** ] 窗格中，按一下 **[完成新增**]，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="f5934-128">接下來，建立名為 GlobalAdmins 的新群組，並將 DedicatedAdmin 帳戶新增至該群組。</span><span class="sxs-lookup"><span data-stu-id="f5934-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="f5934-129">在 [ **Microsoft 365 系統管理中心** ] 索引標籤上，按一下左側導覽窗格中的 [ **群組** ]，然後按一下 [ **群組**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="f5934-130">按一下 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="f5934-131">在 [ **選擇群組類型** ] 窗格中，選取 [ **安全性**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f5934-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="f5934-132">在 [ **設定基礎** ] 窗格中，按一下 [ **建立群組**]，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="f5934-133">在 [ **複查並完成新增群組** ] 窗格中，輸入 **GlobalAdmins**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f5934-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="f5934-134">在群組清單中，按一下 [ **GlobalAdmins** ] 群組。</span><span class="sxs-lookup"><span data-stu-id="f5934-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="f5934-135">在 [ **GlobalAdmins** ] 窗格中，按一下 [ **成員**]，然後按一下 [ **全部查看] 和 [管理成員**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="f5934-136">在 [ **GlobalAdmins** ] 窗格中，按一下 [ **新增成員**]，選取 **DedicatedAdmin** 帳戶和全域系統管理員帳戶，然後按一下 [ **儲存] > 關閉 > 關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="f5934-137">接下來，建立條件式存取原則以要求全域管理員帳戶的多重要素驗證，以及在登入風險為中低或高時拒絕驗證。</span><span class="sxs-lookup"><span data-stu-id="f5934-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="f5934-138">此第一個原則要求所有全域管理員帳戶都使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="f5934-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="f5934-139">在瀏覽器的新索引標籤上，移至 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="f5934-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f5934-140">按一下 [ **Azure Active Directory > Security > 條件式存取**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="f5934-141">在 [ **條件式存取-原則** ] 窗格中，按一下 [ \*\*基準原則：需要 MFA 進行系統管理員 (預覽]) \*\*。</span><span class="sxs-lookup"><span data-stu-id="f5934-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="f5934-142">在 [ **基線原則** ] 窗格中，按一下 [ **立即使用原則 > 儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="f5934-143">第二個原則會封鎖存取全域管理員帳戶時，當登入風險為「中」或「高」時。</span><span class="sxs-lookup"><span data-stu-id="f5934-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="f5934-144">在 [ **條件式存取-原則** ] 窗格中，按一下 [ **新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="f5934-145">在 [**新增**] 窗格中，輸入 [**名稱**] 中的 [**全域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="f5934-146">在 [ **工作分派** ] 區段中，按一下 [ **使用者和群組**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="f5934-147">在 [**使用者和群組**] 窗格的 [**包含**] 索引標籤上，按一下 [**選取使用者和群組 > 使用者和群組] > 選取**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="f5934-148">在 [ **選取** ] 窗格中，按一下 [ **GlobalAdmins** ] 群組，然後按一下 [ **選取 > 完成**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="f5934-149">在 [ **工作分派** ] 區段中，按一下 [ **條件**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="f5934-150">在 [**條件**] 窗格中，按一下 [登**入風險**]，針對 [**設定** **] 按一下 [是]** ，按一下 [**高**] 和 [**中**]，然後按一下 [**選取**並**完成**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="f5934-151">在 [**新增**] 窗格的 [**存取控制**] 區段中，按一下 **[授**與]。</span><span class="sxs-lookup"><span data-stu-id="f5934-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="f5934-152">在 [ **授** 與] 窗格中，按一下 [ **封鎖存取**]，然後按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="f5934-153">在 [**新增**] 窗格中，按一下 [**啟用原則**] 的 [**開啟**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="f5934-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="f5934-154">關閉 [ **Azure 入口網站** ] 和 [ **Microsoft 365 管理中心** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f5934-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="f5934-155">若要測試第一個原則，請以 DedicatedAdmin 帳戶登出並登入。</span><span class="sxs-lookup"><span data-stu-id="f5934-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="f5934-156">您應該會收到設定 MFA 的提示。</span><span class="sxs-lookup"><span data-stu-id="f5934-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="f5934-157">這會示範正在套用第一個原則。</span><span class="sxs-lookup"><span data-stu-id="f5934-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5934-158">下一步</span><span class="sxs-lookup"><span data-stu-id="f5934-158">Next step</span></span>

<span data-ttu-id="f5934-159">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="f5934-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5934-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f5934-160">See also</span></span>

[<span data-ttu-id="f5934-161">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="f5934-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="f5934-162">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="f5934-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f5934-163">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="f5934-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f5934-164">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="f5934-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
