---
title: 驗證 Windows 10 PC 上的 App 保護設定
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 在 Windows 10 裝置上驗證 Microsoft 365 商務進階版應用程式保護設定，並確認使用者無法將公司資料複製到個人檔案或非受管理的應用程式。
ms.openlocfilehash: e319ffa5149f055b5de45078facc8899acffc223
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579855"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="bc7fe-103">驗證 Windows 10 PC 上的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="bc7fe-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="bc7fe-104">確認使用者無法在公司裝置上將公司資料複製到個人檔案</span><span class="sxs-lookup"><span data-stu-id="bc7fe-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="bc7fe-105">在您[設定 App 保護原則](protection-settings-for-windows-10-devices.md)後，這些原則可能需要幾個小時才會在使用者的裝置上生效。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="bc7fe-106">如果您已 **開啟**[**防止使用者將公司資料複製到個人檔案並強制使用者將工作檔案儲存到** 公司所擁有的裝置商務用 OneDrive] 設定，您可以在使用者的裝置連線至 Azure AD 並登入後，對其進行檢查。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="bc7fe-107">**驗證連線設定**</span><span class="sxs-lookup"><span data-stu-id="bc7fe-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="bc7fe-108">在您以 [Microsoft 365 商務進階版使用者的 Windows 裝置](set-up-windows-devices.md)登入 Microsoft 365 商務進階版認證並連接至 Azure AD 之後，請移至 **Windows 設定** \> **帳戶** \> **存取工作或學校**。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-108">After you sign in with Microsoft 365 Business Premium credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**.</span></span> <span data-ttu-id="bc7fe-109">選擇 [ **連線到 \<tenant name\> Azure AD**]，然後選擇 [ **資訊**]。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="bc7fe-111">在 [**管理者**] \<tenant name\> 頁面上，您可以看到包含 **管理伺服器位址** 的連線 **資訊**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="bc7fe-113">**確認您無法將公司資料貼到非受管理的應用程式中**</span><span class="sxs-lookup"><span data-stu-id="bc7fe-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="bc7fe-114">開啟 Microsoft 365 商務進階版安裝的 Outlook 2016。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-114">Open Outlook 2016 that was installed by Microsoft 365 Business Premium.</span></span>
    
2. <span data-ttu-id="bc7fe-115">開啟一封電子郵件，並從中複製部分內容。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="bc7fe-116">開啟記事本，嘗試將內容貼上。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="bc7fe-117">您會收到錯誤，指出應用程式無法存取內容。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="bc7fe-119">不過，您可以將同樣的內容貼入 Word 2016。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="bc7fe-120">確認使用者無法在個人裝置上將公司資料複製到個人檔案</span><span class="sxs-lookup"><span data-stu-id="bc7fe-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="bc7fe-121">**驗證連線設定**</span><span class="sxs-lookup"><span data-stu-id="bc7fe-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="bc7fe-122">在您以本機使用者登入的 Windows 10 個人裝置上，移至 **Windows 設定**]，然後按一下或點擊 [**帳戶** \> **存取工作或學校**]。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="bc7fe-123">在 [**存取工作或學校**] 底下，選擇 [**連線**]。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="bc7fe-124">在 [**設定公司或學校帳戶] 對話方塊** 的 [登入] 中輸入您的 Microsoft 365 商務進階版認證 \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-124">Enter your Microsoft 365 Business Premium credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="bc7fe-125">在 [ **存取公司或學校** ] 頁面上，選擇 [ **公司或學校帳戶**]，然後選擇 [ **資訊**]。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![在 [工作或學校帳戶] 對話方塊中，按一下或點擊 [資訊]。](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="bc7fe-127">在 [**存取公司或學校**] 頁面上，您可以看到包含 **管理伺服器位址** 的連線 **資訊**，如下圖所示，並包含 *wip* 和 *mam* 中的文字。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="bc7fe-129">**確認您無法將公司資料貼到非受管理的應用程式中**</span><span class="sxs-lookup"><span data-stu-id="bc7fe-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="bc7fe-130">如有必要，請開啟 Outlook 2016 並新增您的 Microsoft 365 商務進階版帳戶，並以您的 Microsoft 365 商務進階版認證登入。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-130">Open Outlook 2016 and add your Microsoft 365 Business Premium account if necessary and sign in with your Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="bc7fe-131">開啟一封電子郵件，並從中複製部分內容。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="bc7fe-132">開啟記事本，嘗試將內容貼上。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="bc7fe-133">您會收到錯誤，指出應用程式無法存取內容。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="bc7fe-135">不過，您可以將同樣的內容貼入 Word 2016。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-135">You can, however, paste the same content into Word 2016.</span></span>
    

