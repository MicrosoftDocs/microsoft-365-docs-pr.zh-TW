---
title: 多重要素驗證您的 Microsoft 365 企業版測試環境
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
description: 設定使用文字訊息傳送至 Microsoft 365 企業版測試環境中的智慧型手機的多重要素驗證。
ms.openlocfilehash: ea87ab6f169829d74339b64b6edb3978bea9ca9a
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801398"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a6ab0-103">多重要素驗證您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="a6ab0-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a6ab0-104">*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*</span><span class="sxs-lookup"><span data-stu-id="a6ab0-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a6ab0-105">針對其他安全性層級的登入 Microsoft 365，或任何服務或應用程式的訂用帳戶使用 Azure AD 租用戶，您可以啟用 Azure 多重要素驗證，需要不只是使用者名稱和密碼，可驗證帳戶。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="a6ab0-106">以多重要素驗證使用者，才能確認電話、 輸入傳送文字郵件驗證碼或其智慧型手機上指定應用程式密碼之後正確輸入其密碼。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="a6ab0-107">只有在滿足這個第二次驗證要素之後，他們才可以登入。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="a6ab0-108">本文說明如何啟用及測試文字郵件的驗證，為特定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="a6ab0-109">有兩個主要階段設定多重要素驗證 Microsoft 365 企業版測試環境中的帳戶：</span><span class="sxs-lookup"><span data-stu-id="a6ab0-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="a6ab0-110">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="a6ab0-111">啟用並測試 「 使用者 2 」 帳戶的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="a6ab0-112">啟用並測試與條件式存取原則 （選用） 的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a6ab0-114">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-114">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a6ab0-115">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="a6ab0-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a6ab0-116">如果您只想以具有最小需求的輕量型方式測試多重要素驗證，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a6ab0-117">如果您想要在模擬的企業中測試多重要素驗證，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6ab0-118">測試多重要素驗證不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a6ab0-119">它提供了此選項，讓您可以測試多重要素驗證與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="a6ab0-120">階段 2： 啟用並測試 「 使用者 2 」 帳戶的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="a6ab0-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="a6ab0-121">啟用多重要素驗證的 「 使用者 2 」 帳戶使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a6ab0-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="a6ab0-122">開啟瀏覽器的個別的私用執行個體，請移至 Microsoft 365 系統管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com))，然後使用全域管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="a6ab0-123">在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="a6ab0-124">在 [作用中使用者] 窗格中，按一下 [**多重要素驗證**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="a6ab0-125">在清單中，選取 「**使用者 2** 」 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="a6ab0-126">在 [**使用者 2** ] 區段中，[**快速步驟**，按一下 [**啟用**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="a6ab0-127">在 [**關於啟用多重要素驗證**] 對話方塊中，按一下 [**啟用多重要素驗證**]。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="a6ab0-128">在**更新成功**] 對話方塊中，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="a6ab0-129">在**Microsoft 365 系統管理中心**] 索引標籤上，按一下右上方，使用者帳戶圖示，然後按一下 [**登出]**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="a6ab0-130">關閉瀏覽器執行個體。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-130">Close your browser instance.</span></span>
   
<span data-ttu-id="a6ab0-131">完成文字郵件驗證和測試這些步驟的 「 使用者 2 」 帳戶的設定：</span><span class="sxs-lookup"><span data-stu-id="a6ab0-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="a6ab0-132">開啟瀏覽器的新的私用執行個體。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="a6ab0-133">移至 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 並以使用者 2 帳戶名稱和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="a6ab0-134">登入後，系統會提示您若要設定之帳戶的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="a6ab0-135">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="a6ab0-136">在**其他安全性驗證**] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="a6ab0-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="a6ab0-137">選取您的國家/地區或區域。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="a6ab0-138">輸入將接收文字訊息智慧型手機的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="a6ab0-139">在**方法**中，按一下 [**傳送我透過文字訊息的程式碼**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="a6ab0-140">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="a6ab0-141">從智慧型手機上接收簡訊輸入驗證碼，然後按一下 [**驗證**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="a6ab0-142">在**步驟 3： 保留您現有的應用程式**頁面、 使用者 2 」 帳戶的顯示的應用程式密碼記錄於安全的位置，然後再按一下 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-142">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="a6ab0-143">如果這是第一次您登入的使用者 2 帳戶後，系統會提示您要變更密碼。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="a6ab0-144">按兩次，輸入原始密碼] 和 [新密碼，然後按一下 [**更新密碼並登入**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="a6ab0-145">新的密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="a6ab0-146">在瀏覽器的 [ **Microsoft Office 的首頁**] 索引標籤上，您應該針對使用者 2 看到 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="a6ab0-147">階段 3： 啟用並測試與條件式存取原則的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="a6ab0-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="a6ab0-148">*這個階段中只能用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="a6ab0-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="a6ab0-149">在這個階段中，您會啟用使用群組和條件式存取原則的使用者 3 帳戶的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="a6ab0-150">接下來，建立名為 MFAUsers 的新群組和使用者 3 帳戶新增到它。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="a6ab0-151">在**Microsoft 365 系統管理中心**] 索引標籤上，按一下 [**群組**]，請在左側導覽中，，，然後按一下 [**群組**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="a6ab0-152">按一下 [**新增群組**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="a6ab0-153">在 [**選擇群組類型**] 窗格中，選取 [**安全性**]，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="a6ab0-154">在 [**設定 [基本**] 窗格中，按一下 [**建立群組**]，然後按一下 [**關閉**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="a6ab0-155">在 [**檢閱並完成新增群組**] 窗格中，輸入**MFAUsers**，，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="a6ab0-156">在群組清單中，按一下 [ **MFAUsers**群組]。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="a6ab0-157">在**MFAUsers** ] 窗格中，按一下 [**成員**]，然後按一下 [**檢視所有及管理成員**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="a6ab0-158">在**MFAUsers** ] 窗格中，按一下 [**新增成員**、 選取的**使用者 3**帳戶後，，然後按一下 [**儲存 > Close > 關閉**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="a6ab0-159">接下來，建立條件式存取原則以多重要素驗證需要 MFAUsers 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="a6ab0-160">在瀏覽器的新索引標籤，移至 [ [https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a6ab0-161">按一下 [ **Azure Active Directory > 安全性 > 條件式存取**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="a6ab0-162">在 [**條件式存取 – 原則**] 窗格中，按一下 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="a6ab0-163">在 [**新增**] 窗格中，輸入**名稱**中的**使用者帳戶的 MFA** 。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="a6ab0-164">在 [**指派**] 區段中，按一下 [**使用者和群組**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="a6ab0-165">在 [**使用者和群組**] 窗格的 [**包含**] 索引標籤中，按一下 [**選取使用者及群組 > 使用者和群組 >，請選取**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="a6ab0-166">在 [**選取**] 窗格中，按一下 [ **MFAUsers** ] 群組中，然後按一下 [**選取 > 完成**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="a6ab0-167">在 [**新增**] 窗格中的 [**存取控制**] 區段中，按一下 [**授與**]。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="a6ab0-168">在 [**授與**] 窗格中，按一下 [**需要多重要素驗證**，，然後按一下 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="a6ab0-169">在 [**新增**] 窗格中，**啟用原則**，請按一下 [ \*\*\*\* ，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="a6ab0-170">關閉 [ **Azure 入口網站**和**Microsoft 365 系統管理中心**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="a6ab0-171">若要測試此原則，登出並以使用者 3 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="a6ab0-172">應該會提示您設定 MFA。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="a6ab0-173">此示範 MFAUsers 原則會被套用。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="a6ab0-174">在身分識別階段中的資訊，以及部署在生產環境中的多重要素驗證的連結，請參閱[設定多重要素驗證](identity-secure-user-sign-ins.md#identity-mfa)的步驟。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="a6ab0-175">下一步</span><span class="sxs-lookup"><span data-stu-id="a6ab0-175">Next step</span></span>

<span data-ttu-id="a6ab0-176">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="a6ab0-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6ab0-177">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a6ab0-177">See also</span></span>

[<span data-ttu-id="a6ab0-178">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="a6ab0-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="a6ab0-179">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="a6ab0-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a6ab0-180">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="a6ab0-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a6ab0-181">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="a6ab0-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
