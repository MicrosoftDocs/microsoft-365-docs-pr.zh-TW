---
title: Microsoft 365 for enterprise test 環境多重要素驗證
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
description: 使用 Microsoft 365 for enterprise test 環境中傳送至 smart phone 的文字訊息，設定多重要素驗證。
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558439"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b79c1-103">適用于 Microsoft 365 企業版測試環境的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="b79c1-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b79c1-104">*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="b79c1-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b79c1-105">若要取得其他安全性，以供登入 Microsoft 365 或任何服務或應用程式使用您訂閱的 Azure AD 租使用者，您可以啟用 Azure AD 多重要素驗證，而不只需要使用使用者名稱和密碼來驗證帳戶。</span><span class="sxs-lookup"><span data-stu-id="b79c1-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="b79c1-106">使用多重要素驗證時，使用者必須認可電話、輸入短信中所傳送的驗證碼，或在正確輸入密碼後，使用智慧型電話上的應用程式驗證驗證。</span><span class="sxs-lookup"><span data-stu-id="b79c1-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="b79c1-107">只有在滿足第二個驗證因素之後，才可登入。</span><span class="sxs-lookup"><span data-stu-id="b79c1-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="b79c1-108">本文說明如何為特定使用者帳戶啟用並測試以郵件為基礎的驗證。</span><span class="sxs-lookup"><span data-stu-id="b79c1-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="b79c1-109">在 Microsoft 365 for enterprise test 環境中為帳戶設定多重要素驗證時，包含兩個階段和第三個選用階段：</span><span class="sxs-lookup"><span data-stu-id="b79c1-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="b79c1-110">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="b79c1-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="b79c1-111">階段2：針對使用者2帳戶啟用並測試多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="b79c1-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="b79c1-112">階段3：使用條件式存取原則來啟用及測試多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="b79c1-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b79c1-114">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b79c1-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b79c1-115">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="b79c1-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b79c1-116">如果您只想以輕量的方式測試多重要素驗證，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="b79c1-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b79c1-117">如果您想要在模擬的企業中測試多重要素驗證，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="b79c1-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b79c1-118">測試多重要素驗證並不需要模擬的企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="b79c1-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b79c1-119">這裡是以選項形式提供，可讓您測試多重要素驗證，並在代表一般組織的環境中進行嘗試。</span><span class="sxs-lookup"><span data-stu-id="b79c1-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="b79c1-120">階段2：針對使用者2帳戶啟用並測試多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="b79c1-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="b79c1-121">使用下列步驟為使用者2帳戶啟用多重要素驗證：</span><span class="sxs-lookup"><span data-stu-id="b79c1-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="b79c1-122">開啟瀏覽器的個別私人實例，移至 Microsoft 365 管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com)) ，然後使用全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b79c1-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="b79c1-123">在左側導覽中，選取 [**使用者** 作用中  >  **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="b79c1-124">在 [作用中的使用者] 窗格中，選取 [ **多重要素驗證**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="b79c1-125">在清單中，選取 [ **使用者 2** ] 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b79c1-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="b79c1-126">在 [ **使用者 2** ] 區段的 [ **快速步驟**] 底下，選取 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="b79c1-127">在 [ **相關啟用多重要素驗證** ] 對話方塊中，選取 [ **啟用多重要素驗證**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="b79c1-128">在 [ **更新成功** ] 對話方塊中，選取 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="b79c1-129">在 [ **Microsoft 365 系統管理中心** ] 索引標籤上，選取右上方的使用者帳戶圖示，然後選取 [ **登出**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="b79c1-130">關閉瀏覽器實例。</span><span class="sxs-lookup"><span data-stu-id="b79c1-130">Close your browser instance.</span></span>
   
<span data-ttu-id="b79c1-131">完成「使用者2」帳戶的設定，以使用文字訊息進行驗證，並使用下列步驟進行測試：</span><span class="sxs-lookup"><span data-stu-id="b79c1-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="b79c1-132">開啟瀏覽器的新的私人實例。</span><span class="sxs-lookup"><span data-stu-id="b79c1-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="b79c1-133">請移至 [Microsoft 365 系統管理中心](https://admin.microsoft.com) ，並使用使用者2帳戶名稱和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="b79c1-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="b79c1-134">登入後，系統會提示您設定帳戶以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b79c1-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="b79c1-135">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b79c1-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="b79c1-136">在 [ **其他安全性驗證** ] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="b79c1-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="b79c1-137">選取您的國家或地區。</span><span class="sxs-lookup"><span data-stu-id="b79c1-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="b79c1-138">輸入將接收文字訊息之智慧型電話的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b79c1-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="b79c1-139">在 **方法** 中，選取 [以 **文字訊息傳送程式碼**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="b79c1-140">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b79c1-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="b79c1-141">從 smart phone 上收到的文字訊息中輸入驗證碼，然後選取 [ **驗證**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="b79c1-142">在 [ **步驟3：保留現有的應用程式** ] 頁面上，選取 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="b79c1-143">如果這是您第一次使用使用者2帳戶登入，系統會提示您變更密碼。</span><span class="sxs-lookup"><span data-stu-id="b79c1-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="b79c1-144">輸入原始密碼和新密碼兩次，然後選取 [ **更新密碼並登入**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="b79c1-145">將新密碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="b79c1-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="b79c1-146">您應該會在瀏覽器的 [ **Microsoft Office 首頁** ] 索引標籤上，看到使用者2的 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="b79c1-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="b79c1-147">階段3：使用條件式存取原則來啟用及測試多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="b79c1-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="b79c1-148">*此階段僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="b79c1-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="b79c1-149">在此階段中，您會使用群組和條件式存取原則為使用者3帳戶啟用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="b79c1-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="b79c1-150">接下來，建立名為 MFAUsers 的新群組，並將使用者3帳戶新增至該群組。</span><span class="sxs-lookup"><span data-stu-id="b79c1-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="b79c1-151">在 [ **Microsoft 365 系統管理中心** ] 索引標籤上，選取左側導覽中的 [ **群組** ]，然後選取 [ **群組**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="b79c1-152">選取 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="b79c1-153">在 [ **選擇群組類型** ] 窗格中，選取 [ **安全性**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b79c1-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="b79c1-154">在 [ **設定基礎** ] 窗格中，選取 [ **建立群組**]，然後選取 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="b79c1-155">在 [ **複查並完成新增群組** ] 窗格中，輸入 **MFAUsers**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b79c1-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="b79c1-156">在群組清單中，選取 [ **MFAUsers** ] 群組。</span><span class="sxs-lookup"><span data-stu-id="b79c1-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="b79c1-157">在 [ **MFAUsers** ] 窗格中，選取 [ **成員**]，然後選取 [ **全部查看] 和 [管理成員**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="b79c1-158">在 [ **MFAUsers** ] 窗格中，選取 [**新增成員**]，選取 [**使用者 3** ] 帳戶，然後選取 [**儲存**  >  **關閉**] [關閉]  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b79c1-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="b79c1-159">接下來，建立條件式存取原則，以要求 MFAUsers 群組成員的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="b79c1-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="b79c1-160">在瀏覽器的新索引標籤上，移至 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="b79c1-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="b79c1-161">選取 [ **Azure Active Directory**  >  **安全性**  >  **條件式存取**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="b79c1-162">在 [ **條件式存取-原則** ] 窗格中，選取 [ **新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="b79c1-163">在 [**新增**] 窗格中，于 [**名稱**] 方塊中輸入 **使用者帳戶** 的 [MFA]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="b79c1-164">在 [ **工作分派** ] 區段中，選取 [ **使用者和群組**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="b79c1-165">在 [**使用者和群組**] 窗格的 [**包含**] 索引標籤上，選取 [**選取使用者及群組**  >  **使用者和群組**]  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b79c1-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="b79c1-166">在 [**選取**] 窗格中，選取 [ **MFAUsers** ] 群組，然後選取 [**選取**  >  **完成**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="b79c1-167">在 [**新增**] 窗格的 [**存取控制**] 區段中，選取 **[授** 與]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="b79c1-168">在 [ **授** 與] 窗格中，選取 [ **需要多重要素驗證**]，然後選取 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="b79c1-169">在 [**新增**] 窗格中，選取 [**開啟\*\*\*\*原則**]，然後選取 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="b79c1-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="b79c1-170">關閉 [ **Azure 入口網站** ] 和 [ **Microsoft 365 管理中心** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b79c1-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="b79c1-171">若要測試此原則，請使用使用者3帳戶登出並登入。</span><span class="sxs-lookup"><span data-stu-id="b79c1-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="b79c1-172">您應該會收到設定 MFA 的提示。</span><span class="sxs-lookup"><span data-stu-id="b79c1-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="b79c1-173">這會示範所套用的 MFAUsers 原則。</span><span class="sxs-lookup"><span data-stu-id="b79c1-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="b79c1-174">下一步</span><span class="sxs-lookup"><span data-stu-id="b79c1-174">Next step</span></span>

<span data-ttu-id="b79c1-175">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="b79c1-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b79c1-176">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b79c1-176">See also</span></span>

[<span data-ttu-id="b79c1-177">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="b79c1-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="b79c1-178">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="b79c1-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b79c1-179">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="b79c1-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b79c1-180">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="b79c1-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
