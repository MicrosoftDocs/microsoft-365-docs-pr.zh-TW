---
title: 保護您的 Microsoft 365 Enterprise 的測試環境中的全域管理員帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: 使用下列步驟來保護 Microsoft 365 企業版測試環境中的全域管理員帳戶。
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866142"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="eaba5-103">保護您的 Microsoft 365 Enterprise 的測試環境中的全域管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="eaba5-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="eaba5-p101">若要防止對貴組織的數位攻擊，您可以確保您的系統管理員帳戶會盡可能的安全。本文說明如何使用 Office 365 雲端應用程式安全性和 Azure AD 的設定格式化的條件存取原則來保護全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="eaba5-p101">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="eaba5-106">有兩個階段來保護 Microsoft 365 企業版測試環境中的全域管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="eaba5-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="eaba5-107">建立 Microsoft 365 企業版的測試環境。</span><span class="sxs-lookup"><span data-stu-id="eaba5-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="eaba5-108">保護您專用的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="eaba5-108">Protect your dedicated global administrator account.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="eaba5-110">按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="eaba5-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="eaba5-111">階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境</span><span class="sxs-lookup"><span data-stu-id="eaba5-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="eaba5-112">如果您只想要測試全域管理員帳戶保護的基本需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="eaba5-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="eaba5-113">如果您想要測試全域管理員帳戶保護模擬 enterprise 中，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="eaba5-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eaba5-p102">測試全域管理員帳戶保護不需要模擬的企業測試環境中，其中包含模擬內部網路連線至網際網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試全域管理員帳戶保護和代表的典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="eaba5-p102">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="eaba5-116">階段 2： 設定雲端應用程式安全性和設定格式化的條件存取原則</span><span class="sxs-lookup"><span data-stu-id="eaba5-116">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="eaba5-117">首先，建立 Office 365 雲端應用程式安全性原則監視全域管理員帳戶活動並將通知傳送給您的全域管理員帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="eaba5-117">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="eaba5-118">登入 Office 365 入口網站[http://portal.office.com](http://portal.office.com)使用全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="eaba5-118">Sign in to the Office 365 portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.</span></span>
2. <span data-ttu-id="eaba5-p103">按一下 [**系統**] 磚。在 [ **Office 系統管理中心**] 索引標籤上按一下 [**系統中心 > 安全性與規範**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-p103">Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.</span></span>
3. <span data-ttu-id="eaba5-121">在左側的導覽窗格中，按一下 [**提醒 > 管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
4. <span data-ttu-id="eaba5-122">**進階提醒的管理**] 頁面上按一下 [**開啟 Office 365 雲端應用程式安全性**] 和 [**移至 Office 365 雲端應用程式安全性**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
5. <span data-ttu-id="eaba5-123">在 [新的**儀表板**] 索引標籤，按一下 [**控制項 > 原則**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
6. <span data-ttu-id="eaba5-124">在 [**原則**] 頁面上按一下 [**建立原則**] 和 [**活動原則**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
7. <span data-ttu-id="eaba5-125">在 [**原則名稱**輸入**系統管理的活動**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-125">In **Policy name**, type **Administrative activity**.</span></span>
8. <span data-ttu-id="eaba5-126">在**原則嚴重性**，按一下 [**高**]。</span><span class="sxs-lookup"><span data-stu-id="eaba5-126">In **Policy severity**, click **High**.</span></span>
9. <span data-ttu-id="eaba5-127">在 [**類別**] 中，按一下 [**權限的帳戶**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-127">In **Category**, click **Privileged accounts**.</span></span>
10. <span data-ttu-id="eaba5-128">在**建立篩選器原則**中**符合下列所有的活動**，按一下 [**系統管理的活動**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
11. <span data-ttu-id="eaba5-p104">在**警告**中，按一下 [**傳送做為電子郵件通知**。在 [**至**] 輸入您的全域管理員帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="eaba5-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
12. <span data-ttu-id="eaba5-131">在頁面的底端，按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="eaba5-131">At the bottom of the page, click **Create**.</span></span>
13. <span data-ttu-id="eaba5-132">關閉 [**儀表板**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="eaba5-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="eaba5-133">下一步] 建立新的使用者帳戶為專用的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="eaba5-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="eaba5-134">在 [ **Office 系統管理中心**] 索引標籤上**作用中使用者**] 底下按一下 [**新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="eaba5-134">On the **Office Admin center** tab, under **Active users**, click **Add a user**.</span></span>
2. <span data-ttu-id="eaba5-135">在 [**新增使用者**] 頁面上輸入**DedicatedAdmin**的**名字**、**顯示名稱**和**使用者名稱**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-135">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
3. <span data-ttu-id="eaba5-p105">按一下 [**密碼**] 和 [**讓我建立密碼**，然後輸入 [強式密碼。安全的位置記錄此新帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="eaba5-p105">Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.</span></span>
4. <span data-ttu-id="eaba5-138">清除 [**讓此變更其密碼時第一次登入的使用者**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-138">Clear **Make this user change their password when they first sign in**.</span></span>
5. <span data-ttu-id="eaba5-139">按一下 [**角色**]，然後按一下 [**全域管理員**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-139">Click **Roles**, and then click **Global administrator**.</span></span>
6. <span data-ttu-id="eaba5-140">按一下 [**產品授權**，然後再開啟**企業行動性 + 安全性 E5**和**Office 365 企業版 E5 授權**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-140">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
7. <span data-ttu-id="eaba5-141">按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eaba5-141">Click **Add**.</span></span>
8. <span data-ttu-id="eaba5-142">在**已新增使用者] 頁面上**，清除**傳送電子郵件中的密碼**，然後再按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="eaba5-142">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="eaba5-143">接下來，建立名為 GlobalAdmins 的新群組並將 DedicatedAdmin 帳戶新增至其。</span><span class="sxs-lookup"><span data-stu-id="eaba5-143">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="eaba5-144">在**Office 系統管理中心**] 索引標籤按一下 [群組] 圖示的左方導覽，和 [**群組**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-144">On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="eaba5-145">按一下 [**新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="eaba5-145">Click **Add a group**.</span></span>
3. <span data-ttu-id="eaba5-146">在 [**新增群組**] 頁面上輸入**GlobalAdmins**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-146">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="eaba5-147">按一下 [**選取擁有者**按一下您的全域管理員帳戶] 和 [**新增 > 關閉**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-147">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="eaba5-148">在群組清單中，按一下 [ **GlobalAdmins**群組]。</span><span class="sxs-lookup"><span data-stu-id="eaba5-148">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="eaba5-149">在**GlobalAdmins** ] 頁面上，按一下 [**編輯成員**] 及 [**新增成員**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-149">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="eaba5-150">在清單中，按一下 [ **DedicatedAdmin**帳戶] 和 [**儲存 > Close > Close > 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-150">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="eaba5-151">接下來，建立條件式存取原則以全域管理員帳戶需要多重要素驗證和拒絕驗證登入風險時中型或高。</span><span class="sxs-lookup"><span data-stu-id="eaba5-151">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="eaba5-152">此第一個原則要求所有全域管理員帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="eaba5-152">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="eaba5-153">在 [新增] 索引標籤的瀏覽器中移至[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="eaba5-153">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="eaba5-154">按一下 [ **Azure Active Directory > 條件式存取**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-154">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="eaba5-155">在 [**設定格式化的條件存取 – 原則**blade 中，按一下 [**基準原則： 的系統管理員 （預覽） 需要 MFA**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-155">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="eaba5-p106">在**基準原則...** blade 中，按一下 [**立即使用原則 > 儲存**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-p106">On the **Baseline policies…** blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="eaba5-158">此第二個原則封鎖存取權全域管理員帳戶驗證登入風險時中型或高。</span><span class="sxs-lookup"><span data-stu-id="eaba5-158">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="eaba5-159">在**設定格式化的條件存取 – 原則**blade 中，按一下 [**新的原則**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-159">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="eaba5-160">在**新增**blade 中，輸入**全域管理員**的**名稱**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-160">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="eaba5-161">在 [**工作分派**] 區段中，按一下 [**使用者與群組**]。</span><span class="sxs-lookup"><span data-stu-id="eaba5-161">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="eaba5-162">按一下 [**加入**] 索引標籤的**使用者和群組**blade**選取的使用者和群組 > 使用者和群組 > 選取**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-162">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="eaba5-163">在 [**選取**blade，按一下 [ **GlobalAdmins > 選取 > 完成**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-163">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="eaba5-164">在 [**工作分派**] 區段中，按一下 [**條件**]。</span><span class="sxs-lookup"><span data-stu-id="eaba5-164">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="eaba5-165">上**條件**blade 中，按一下 [**登入風險**、 按一下 [**是]** 的**設定**、 [**高**] 和 [**中等**和 [**選取**並**完成**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-165">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="eaba5-166">**新增**blade 的 [**存取控制**] 區段中的 [**授與**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-166">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="eaba5-167">在**授與**blade 中，按一下 [**封鎖存取**] 和 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-167">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="eaba5-168">在**新增**blade、**啟用原則**，請按一下 [\*\*\*\* 然後再按一下 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="eaba5-168">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="eaba5-169">關閉 [ **Azure 入口網站**與**Office 系統管理中心**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="eaba5-169">Close the **Azure portal** and **Office Admin center** tabs.</span></span>

<span data-ttu-id="eaba5-p107">若要測試的第一個原則，請登出並使用 DedicatedAdmin 帳戶登入。您應提示使用者帳戶上設定 MFA。這將示範如何套用的第一個原則。</span><span class="sxs-lookup"><span data-stu-id="eaba5-p107">To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="eaba5-173">請參閱 「 身分識別 」 階段的資訊及連結來保護您的全域管理員帳戶在生產環境中[保護全域管理員帳戶](identity-designate-protect-admin-accounts.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="eaba5-173">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="eaba5-174">下一步</span><span class="sxs-lookup"><span data-stu-id="eaba5-174">Next step</span></span>

<span data-ttu-id="eaba5-175">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="eaba5-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="eaba5-176">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eaba5-176">See also</span></span>

[<span data-ttu-id="eaba5-177">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="eaba5-177">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="eaba5-178">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="eaba5-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="eaba5-179">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="eaba5-179">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="eaba5-180">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="eaba5-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
