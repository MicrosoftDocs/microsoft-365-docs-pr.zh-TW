---
title: 驗證 Windows 10 PC 上的 App 保護設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何驗證 Windows 10 裝置中的 Microsoft 365 商務應用程式保護設定。
ms.openlocfilehash: f00dd380103ad9498d77b0e8814bace3de168df4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866526"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="147e8-103">驗證 Windows 10 PC 上的 App 保護設定</span><span class="sxs-lookup"><span data-stu-id="147e8-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="147e8-104">確認使用者無法在公司裝置上將公司資料複製到個人檔案</span><span class="sxs-lookup"><span data-stu-id="147e8-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="147e8-p101">之後您[設定應用程式保護原則](protection-settings-for-windows-10-devices.md)，它可能需要幾個小時才會影響使用者的裝置原則。如果**您開啟**防止使用者將複製的個人檔案的公司資料與強制其儲存至 OneDrive for Business 的工時檔案**設定擁有裝置的公司，** 您可以檢查此使用者的裝置後他們已連線至 Azure AD並已登入。</span><span class="sxs-lookup"><span data-stu-id="147e8-p101">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices. If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they have connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="147e8-107">**驗證連線設定**</span><span class="sxs-lookup"><span data-stu-id="147e8-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="147e8-p102">使用 Microsoft 365 商務認證登入並連線至 Azure AD 如所述[設定 Microsoft 365 商務使用者的 Windows 裝置](set-up-windows-devices.md)之後，移至 [ **Windows 設定** \> **帳戶** \> **存取工作或學校**.選擇 [**連接至\<租用戶名稱\>Azure AD**，然後選擇 [**資訊**。</span><span class="sxs-lookup"><span data-stu-id="147e8-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="147e8-111">在**受管理的**\<租用戶名稱\>頁面您可以看到包含類似如下圖所示的其中一個**管理伺服器位址\*\*\*\*連線資訊**。</span><span class="sxs-lookup"><span data-stu-id="147e8-111">On the **Managed by** \<tenant name\> page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="147e8-113">**確認您無法將公司資料貼到未受管理的 App**</span><span class="sxs-lookup"><span data-stu-id="147e8-113">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="147e8-114">開啟由 Microsoft 365 商務版 安裝的 Outlook 2016。</span><span class="sxs-lookup"><span data-stu-id="147e8-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="147e8-115">開啟一封電子郵件，並從中複製部分內容。</span><span class="sxs-lookup"><span data-stu-id="147e8-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="147e8-116">開啟記事本，嘗試將內容貼上。</span><span class="sxs-lookup"><span data-stu-id="147e8-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="147e8-117">您會收到一則錯誤，其中指出 App 無法存取內容。</span><span class="sxs-lookup"><span data-stu-id="147e8-117">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="147e8-119">不過，您可以將同樣的內容貼入 Word 2016。</span><span class="sxs-lookup"><span data-stu-id="147e8-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="147e8-120">確認使用者無法在個人裝置上將公司資料複製到個人檔案</span><span class="sxs-lookup"><span data-stu-id="147e8-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="147e8-121">**驗證連線設定**</span><span class="sxs-lookup"><span data-stu-id="147e8-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="147e8-122">在 Windows 10 個人在裝置上出您要以登入本機使用者移至 [ **Windows 設定**並按一下或點選**帳戶** \> **存取工作或學校**。</span><span class="sxs-lookup"><span data-stu-id="147e8-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="147e8-123">**存取工作或學校**] 下選擇 [**連接**]。</span><span class="sxs-lookup"><span data-stu-id="147e8-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="147e8-124">輸入到您 Microsoft 365 商務認證**設定工作或學校帳戶] 對話方塊** \> **登入**。</span><span class="sxs-lookup"><span data-stu-id="147e8-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="147e8-125">在 [**存取工作或學校**] 頁面上選擇 [**工作或學校帳戶**，然後選擇 [**資訊**。</span><span class="sxs-lookup"><span data-stu-id="147e8-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="147e8-127">在 [**存取工作或學校**頁面您可以看到**連線資訊**包括顯示於下圖、 種方式在**管理伺服器位址**並包含單字*wip*和*mam*內。</span><span class="sxs-lookup"><span data-stu-id="147e8-127">On the **Access work or school** page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="147e8-129">**確認您無法將公司資料貼到未受管理的 App**</span><span class="sxs-lookup"><span data-stu-id="147e8-129">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="147e8-130">開啟 Outlook 2016，若有需要的話請新增您的 Microsoft 365 商務版 帳戶，並以您的 Microsoft 365 商務版 認證登入。</span><span class="sxs-lookup"><span data-stu-id="147e8-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="147e8-131">開啟一封電子郵件，並從中複製部分內容。</span><span class="sxs-lookup"><span data-stu-id="147e8-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="147e8-132">開啟記事本，嘗試將內容貼上。</span><span class="sxs-lookup"><span data-stu-id="147e8-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="147e8-133">您會收到一則錯誤，其中指出 App 無法存取內容。</span><span class="sxs-lookup"><span data-stu-id="147e8-133">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="147e8-135">不過，您可以將同樣的內容貼入 Word 2016。</span><span class="sxs-lookup"><span data-stu-id="147e8-135">You can, however, paste the same content into Word 2016.</span></span>
    

