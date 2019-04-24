---
title: 多重要素驗證您的 Microsoft 365 企業版測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 設定使用文字訊息傳送至 Microsoft 365 企業版測試環境中的智慧型手機的多重要素驗證。
ms.openlocfilehash: 8e202936451030718c0c86601c2c621c50f78e1a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291138"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a2936-103">多重要素驗證您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="a2936-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a2936-104">針對其他安全性層級的登入 Office 365 或任何服務或應用程式，為您的組織會使用 Azure AD 租用戶，您可以啟用 Azure 多重要素驗證，需要不只是使用者名稱和密碼，可驗證帳戶。</span><span class="sxs-lookup"><span data-stu-id="a2936-104">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="a2936-105">以多重要素驗證使用者，才能確認電話、 輸入傳送文字郵件驗證碼或其智慧型手機上指定應用程式密碼之後正確輸入其密碼。</span><span class="sxs-lookup"><span data-stu-id="a2936-105">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="a2936-106">只有在滿足這個第二次驗證要素之後，他們才可以登入。</span><span class="sxs-lookup"><span data-stu-id="a2936-106">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="a2936-107">本文說明如何啟用及測試文字郵件的驗證為特定帳戶。</span><span class="sxs-lookup"><span data-stu-id="a2936-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="a2936-108">有兩個主要階段設定多重要素驗證 Microsoft 365 企業版測試環境中的帳戶：</span><span class="sxs-lookup"><span data-stu-id="a2936-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="a2936-109">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="a2936-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="a2936-110">啟用並測試 「 使用者 2 」 帳戶的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="a2936-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a2936-112">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="a2936-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a2936-113">階段 1： 建置 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="a2936-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a2936-114">如果您只想以具有最小需求的輕量型方式測試多重要素驗證，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="a2936-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a2936-115">如果您想要在模擬的企業中測試多重要素驗證，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="a2936-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2936-116">測試多重要素驗證不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理 Active Directory 網域服務 (AD DS) 樹系中。</span><span class="sxs-lookup"><span data-stu-id="a2936-116">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a2936-117">它提供了此選項，讓您可以測試多重要素驗證與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="a2936-117">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="a2936-118">階段 2： 啟用並測試 「 使用者 2 」 帳戶的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="a2936-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="a2936-119">啟用多重要素驗證的 「 使用者 2 」 帳戶使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a2936-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="a2936-120">開啟瀏覽器的個別的私用執行個體，請移至 Office 入口網站 ([https://office.com](https://office.com))，然後使用全域管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="a2936-120">Open a separate, private instance of your browser, go to the Office portal ([https://office.com](https://office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="a2936-121">從主要的入口網站頁面中，按一下 [管理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2936-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="a2936-122">在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2936-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="a2936-123">在 [作用中使用者] 窗格中，按一下 [**更多 > 多重要素驗證設定**]。</span><span class="sxs-lookup"><span data-stu-id="a2936-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="a2936-124">在清單中，選取 「**使用者 2** 」 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a2936-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="a2936-125">在 [**使用者 2** ] 區段中，[**快速步驟**，按一下 [**啟用**。</span><span class="sxs-lookup"><span data-stu-id="a2936-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="a2936-126">在 [**關於啟用多重要素驗證**] 對話方塊中，按一下 [**啟用多重要素驗證**]。</span><span class="sxs-lookup"><span data-stu-id="a2936-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="a2936-127">在**更新成功**] 對話方塊中，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a2936-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="a2936-128">在 [ **Microsoft Office 的首頁**] 索引標籤中，按一下右上方，使用者帳戶圖示，然後按一下 [**登出]**。</span><span class="sxs-lookup"><span data-stu-id="a2936-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="a2936-129">關閉瀏覽器執行個體。</span><span class="sxs-lookup"><span data-stu-id="a2936-129">Close your browser instance.</span></span>
   
<span data-ttu-id="a2936-130">完成文字郵件驗證和測試這些步驟的 「 使用者 2 」 帳戶的設定：</span><span class="sxs-lookup"><span data-stu-id="a2936-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="a2936-131">開啟瀏覽器的新的私用執行個體。</span><span class="sxs-lookup"><span data-stu-id="a2936-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="a2936-132">移至 Office 入口網站 ([https://office.com](https://office.com)) 並以 「 使用者 2 」 帳戶登入 (user2 @\<組織 name>.onmicrosoft.com) 和密碼。</span><span class="sxs-lookup"><span data-stu-id="a2936-132">Go to the Office portal ([https://office.com](https://office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="a2936-133">登入後，系統會提示您若要設定之帳戶的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a2936-133">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="a2936-134">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2936-134">Click **Next**.</span></span>
    
4. <span data-ttu-id="a2936-135">在**其他安全性驗證**] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="a2936-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="a2936-136">選取您的國家/地區或區域。</span><span class="sxs-lookup"><span data-stu-id="a2936-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="a2936-137">輸入將接收文字訊息智慧型手機的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="a2936-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="a2936-138">在**方法**中，按一下 [**傳送我透過文字訊息的程式碼**。</span><span class="sxs-lookup"><span data-stu-id="a2936-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="a2936-139">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2936-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="a2936-140">從智慧型手機上接收簡訊輸入驗證碼，然後按一下 [**驗證**。</span><span class="sxs-lookup"><span data-stu-id="a2936-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="a2936-141">在**步驟 3： 保留您現有的應用程式**頁面、 使用者 2 」 帳戶的顯示的應用程式密碼記錄於安全的位置，然後再按一下 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="a2936-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="a2936-142">如果這是第一次您登入的使用者 2 帳戶後，系統會提示您要變更密碼。</span><span class="sxs-lookup"><span data-stu-id="a2936-142">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="a2936-143">按兩次，輸入原始密碼] 和 [新密碼，然後按一下 [**更新密碼並登入**。</span><span class="sxs-lookup"><span data-stu-id="a2936-143">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="a2936-144">新的密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="a2936-144">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="a2936-145">在瀏覽器的 [ **Microsoft Office 的首頁**] 索引標籤上，您應該針對使用者 2 看到 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="a2936-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="a2936-146">在身分識別階段中的資訊，以及部署在生產環境中的多重要素驗證的連結，請參閱[設定多重要素驗證](identity-multi-factor-authentication.md#identity-mfa)的步驟。</span><span class="sxs-lookup"><span data-stu-id="a2936-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="a2936-147">下一步</span><span class="sxs-lookup"><span data-stu-id="a2936-147">Next step</span></span>

<span data-ttu-id="a2936-148">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="a2936-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2936-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a2936-149">See also</span></span>

[<span data-ttu-id="a2936-150">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="a2936-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="a2936-151">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="a2936-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a2936-152">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="a2936-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a2936-153">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="a2936-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
