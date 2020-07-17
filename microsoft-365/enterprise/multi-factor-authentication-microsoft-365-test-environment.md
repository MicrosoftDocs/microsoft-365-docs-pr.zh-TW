---
title: Microsoft 365 企業版測試環境多重要素驗證
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
- seo-marvel-apr2020
description: 使用在 Microsoft 365 企業版測試環境中傳送至 smart phone 的文字訊息，設定多重要素驗證。
ms.openlocfilehash: e26fb7470e01397266f5f424ee45941a79a2940c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819373"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e370e-103">Microsoft 365 企業版測試環境的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="e370e-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e370e-104">*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*</span><span class="sxs-lookup"><span data-stu-id="e370e-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="e370e-105">若要取得其他安全性，以供登入 Microsoft 365 或任何服務或應用程式使用您訂閱的 Azure AD 租使用者，您可以啟用 Azure 多重要素驗證，它只需要使用者名稱和密碼，即可驗證帳戶。</span><span class="sxs-lookup"><span data-stu-id="e370e-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="e370e-106">使用多重要素驗證時，使用者必須認可電話、輸入短信中所傳送的驗證碼，或在正確輸入密碼後，使用智慧型電話上的應用程式驗證驗證。</span><span class="sxs-lookup"><span data-stu-id="e370e-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="e370e-107">只有在滿足這個第二次驗證要素之後，他們才可以登入。</span><span class="sxs-lookup"><span data-stu-id="e370e-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="e370e-108">本文說明如何為特定使用者帳戶啟用並測試以郵件為基礎的驗證。</span><span class="sxs-lookup"><span data-stu-id="e370e-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="e370e-109">針對 Microsoft 365 企業版測試環境中的帳戶設定多重要素驗證有兩個階段：</span><span class="sxs-lookup"><span data-stu-id="e370e-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="e370e-110">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="e370e-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="e370e-111">為使用者2帳戶啟用並測試多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="e370e-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="e370e-112">使用條件式存取原則（選用）來啟用及測試多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="e370e-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e370e-114">請移至[測試實驗室指南堆疊](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，以取得 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="e370e-114">Go to [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e370e-115">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="e370e-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e370e-116">如果您只想以輕量的方式測試多重要素驗證，請依照[輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="e370e-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e370e-117">如果您想要在模擬的企業中測試多重要素驗證，請依照[傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="e370e-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e370e-118">測試多重要素驗證並不需要模擬的企業測試環境，其中包括連線到網際網路的模擬內部網路和 Active Directory 網域服務（AD DS）樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="e370e-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e370e-119">這裡是以選項形式提供，可讓您測試多重要素驗證，並在代表一般組織的環境中進行嘗試。</span><span class="sxs-lookup"><span data-stu-id="e370e-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="e370e-120">階段2：針對使用者2帳戶啟用並測試多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="e370e-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="e370e-121">使用下列步驟為使用者2帳戶啟用多重要素驗證：</span><span class="sxs-lookup"><span data-stu-id="e370e-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="e370e-122">開啟瀏覽器的個別私人實例，移至 Microsoft 365 系統管理中心（ [https://portal.microsoft.com](https://portal.microsoft.com) ），然後使用全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="e370e-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="e370e-123">在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e370e-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="e370e-124">在 [作用中的使用者] 窗格中，按一下 [**多重要素驗證**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="e370e-125">在清單中，選取 [**使用者 2** ] 帳戶。</span><span class="sxs-lookup"><span data-stu-id="e370e-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="e370e-126">在 [**使用者 2** ] 區段的 [**快速步驟**] 下方，按一下 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="e370e-127">在 [**相關啟用多重要素驗證**] 對話方塊中，按一下 [**啟用多重要素驗證**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="e370e-128">在 [**更新成功**] 對話方塊中，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="e370e-129">在 [ **Microsoft 365 系統管理中心**] 索引標籤上，按一下右上方的使用者帳戶圖示，然後按一下 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="e370e-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="e370e-130">關閉瀏覽器實例。</span><span class="sxs-lookup"><span data-stu-id="e370e-130">Close your browser instance.</span></span>
   
<span data-ttu-id="e370e-131">完成「使用者2」帳戶的設定，以使用文字訊息進行驗證，並使用下列步驟進行測試：</span><span class="sxs-lookup"><span data-stu-id="e370e-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="e370e-132">開啟瀏覽器的新的私人實例。</span><span class="sxs-lookup"><span data-stu-id="e370e-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="e370e-133">移至 Office 365 入口網站（ [https://portal.office.com](https://portal.office.com) ），並使用使用者2帳戶名稱和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="e370e-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="e370e-134">登入後，系統會提示您設定帳戶以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e370e-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="e370e-135">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e370e-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="e370e-136">在 [**其他安全性驗證**] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="e370e-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="e370e-137">選取您的國家或地區。</span><span class="sxs-lookup"><span data-stu-id="e370e-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="e370e-138">輸入將接收文字訊息之智慧型電話的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e370e-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="e370e-139">在**方法**中，按一下 [以**文字訊息傳送程式碼**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="e370e-140">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e370e-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="e370e-141">從 smart phone 上收到的文字訊息中輸入驗證碼，然後按一下 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="e370e-142">在 [**步驟3：保留現有的應用程式**] 頁面上，按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-142">On the **Step 3: Keep your existing applications** page, click **Done**.</span></span>
    
8. <span data-ttu-id="e370e-143">如果這是您第一次使用使用者2帳戶登入，系統會提示您變更密碼。</span><span class="sxs-lookup"><span data-stu-id="e370e-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="e370e-144">輸入原始密碼和新密碼兩次，然後按一下 [**更新密碼並登入**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="e370e-145">將新密碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="e370e-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="e370e-146">您應該會在瀏覽器的 [ **Microsoft Office 首頁**] 索引標籤上，看到使用者2的 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="e370e-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="e370e-147">階段3：使用條件式存取原則來啟用及測試多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="e370e-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="e370e-148">*此階段僅可用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="e370e-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="e370e-149">在此階段中，您會使用群組和條件式存取原則，為使用者3帳戶啟用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="e370e-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="e370e-150">接下來，建立名為 MFAUsers 的新群組，並將使用者3帳戶新增至該群組。</span><span class="sxs-lookup"><span data-stu-id="e370e-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="e370e-151">在 [ **Microsoft 365 系統管理中心**] 索引標籤上，按一下左側導覽窗格中的 [**群組**]，然後按一下 [**群組**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="e370e-152">按一下 [**新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="e370e-153">在 [**選擇群組類型**] 窗格中，選取 [**安全性**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e370e-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="e370e-154">在 [**設定基礎**] 窗格中，按一下 [**建立群組**]，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="e370e-155">在 [**複查並完成新增群組**] 窗格中，輸入**MFAUsers**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e370e-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="e370e-156">在群組清單中，按一下 [ **MFAUsers** ] 群組。</span><span class="sxs-lookup"><span data-stu-id="e370e-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="e370e-157">在 [ **MFAUsers** ] 窗格中，按一下 [**成員**]，然後按一下 [**全部查看] 和 [管理成員**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="e370e-158">在 [ **MFAUsers** ] 窗格中，按一下 [**新增成員**]，選取 [**使用者 3** ] 帳戶，然後按一下 [**儲存] > 關閉 > 關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="e370e-159">接下來，建立條件式存取原則，以要求 MFAUsers 群組成員的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="e370e-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="e370e-160">在瀏覽器的新索引標籤上，移至 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="e370e-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="e370e-161">按一下 [ **Azure Active Directory > Security > 條件式存取**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="e370e-162">在 [**條件式存取-原則**] 窗格中，按一下 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="e370e-163">在 [**新增**] 窗格中，為 [**名稱**] 中的**使用者帳戶輸入 MFA** 。</span><span class="sxs-lookup"><span data-stu-id="e370e-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="e370e-164">在 [**工作分派**] 區段中，按一下 [**使用者和群組**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="e370e-165">在 [**使用者和群組**] 窗格的 [**包含**] 索引標籤上，按一下 [**選取使用者和群組 > 使用者和群組] > 選取**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="e370e-166">在 [**選取**] 窗格中，按一下 [ **MFAUsers** ] 群組，然後按一下 [**選取 > 完成**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="e370e-167">在 [**新增**] 窗格的 [**存取控制**] 區段中，按一下 **[授**與]。</span><span class="sxs-lookup"><span data-stu-id="e370e-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="e370e-168">在 [**授**與] 窗格中，按一下 [**需要多重要素驗證**]，然後按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="e370e-169">在 [**新增**] 窗格中，按一下 [**啟用原則**] 的 [**開啟**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="e370e-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="e370e-170">關閉 [ **Azure 入口網站**] 和 [ **Microsoft 365 管理中心**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e370e-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="e370e-171">若要測試此原則，請使用使用者3帳戶登出並登入。</span><span class="sxs-lookup"><span data-stu-id="e370e-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="e370e-172">您應該會收到設定 MFA 的提示。</span><span class="sxs-lookup"><span data-stu-id="e370e-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="e370e-173">這會示範所套用的 MFAUsers 原則。</span><span class="sxs-lookup"><span data-stu-id="e370e-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="e370e-174">請參閱 Identity 階段中的[設定多重要素驗證](identity-secure-user-sign-ins.md#identity-mfa)步驟，以取得在生產環境中部署多重要素驗證的資訊和連結。</span><span class="sxs-lookup"><span data-stu-id="e370e-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="e370e-175">下一步</span><span class="sxs-lookup"><span data-stu-id="e370e-175">Next step</span></span>

<span data-ttu-id="e370e-176">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="e370e-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e370e-177">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e370e-177">See also</span></span>

[<span data-ttu-id="e370e-178">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="e370e-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="e370e-179">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="e370e-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e370e-180">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="e370e-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e370e-181">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="e370e-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
