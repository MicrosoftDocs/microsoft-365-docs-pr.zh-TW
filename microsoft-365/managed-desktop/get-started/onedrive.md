---
title: Microsoft OneDrive
description: Microsoft 受管理的電腦如何為已註冊的裝置設定 OneDrive
keywords: Microsoft 受管理的電腦、Microsoft 365、服務、檔、應用程式、商務營運應用程式、LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904837"
---
# <a name="microsoft-onedrive"></a><span data-ttu-id="7799e-104">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="7799e-104">Microsoft OneDrive</span></span>

<span data-ttu-id="7799e-105">Microsoft 受管理的電腦會使用[商務用 OneDrive](/onedrive/plan-onedrive-enterprise)作為所有 Microsoft 受管理的電腦裝置的雲端儲存體服務，以確保裝置盡可能具有無狀態。</span><span class="sxs-lookup"><span data-stu-id="7799e-105">Microsoft Managed Desktop uses [OneDrive for Business](/onedrive/plan-onedrive-enterprise) as a cloud storage service for all Microsoft Managed Desktop devices to ensure that the devices are as stateless as possible.</span></span> <span data-ttu-id="7799e-106">不管使用者登入的裝置為何，使用者都能找到他們的檔案。</span><span class="sxs-lookup"><span data-stu-id="7799e-106">User will be able to find their files no matter which device they sign into.</span></span> <span data-ttu-id="7799e-107">例如，如果您將 Microsoft 受管理的電腦裝置更換為新的裝置，則檔案會自動同步至新裝置。</span><span class="sxs-lookup"><span data-stu-id="7799e-107">For example, if you replace a Microsoft Managed Desktop device with a new one, files will automatically sync to the new device.</span></span>

<span data-ttu-id="7799e-108">在 Microsoft 受管理的裝置上，預設會自動設定這些設定：</span><span class="sxs-lookup"><span data-stu-id="7799e-108">We automatically configure these settings by default on Microsoft Managed Devices:</span></span>

- <span data-ttu-id="7799e-109">OneDrive 會以無訊息方式設定使用者帳戶，並自動登入 (，但不) 使用者互動至用來登入 Windows 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7799e-109">OneDrive is silently configured with the user account and automatically signed in (without user interaction) to the user account that was used to sign into Windows.</span></span> <span data-ttu-id="7799e-110">如需詳細資訊，請參閱以[無訊息方式設定使用者帳戶-OneDrive](/onedrive/use-silent-account-configuration)</span><span class="sxs-lookup"><span data-stu-id="7799e-110">For more information, see [Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)</span></span>

- <span data-ttu-id="7799e-111">已啟用檔隨選功能，讓使用者可以在 OneDrive 存取其雲端儲存中的檔案，而不需要不必要地使用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="7799e-111">The Files-On-Demand feature is enabled so that users can access files from their cloud storage in OneDrive without having to use disk space unnecessarily.</span></span> <span data-ttu-id="7799e-112">如需詳細資訊，請參閱[使用 Windows 10 的 OneDrive 檔案儲存磁碟空間](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)。</span><span class="sxs-lookup"><span data-stu-id="7799e-112">For more information, see [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).</span></span>

- <span data-ttu-id="7799e-113">已知的資料夾移動功能會以無訊息方式啟用，以在雲端中備份使用者的資料，讓他們可以從任何裝置存取其檔案。</span><span class="sxs-lookup"><span data-stu-id="7799e-113">The Known Folder Move feature is enabled silently to back up users’ data in the cloud, which gives them access to their files from any device.</span></span> <span data-ttu-id="7799e-114">如需詳細資訊，請參閱[備份您的檔、圖片和桌面資料夾與 OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)。</span><span class="sxs-lookup"><span data-stu-id="7799e-114">For more information, see [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).</span></span>

- <span data-ttu-id="7799e-115">使用者無法停用已知的資料夾移動功能或變更已知資料夾的位置，以確保跨 Microsoft 受管理的電腦裝置的一致體驗。</span><span class="sxs-lookup"><span data-stu-id="7799e-115">Users cannot disable the Known Folder Move feature or change the location of known folders to ensure a consistent experience across Microsoft Managed Desktop devices.</span></span>

## <a name="user-experience"></a><span data-ttu-id="7799e-116">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7799e-116">User experience</span></span>

<span data-ttu-id="7799e-117">當 Microsoft 受管理的電腦使用者收到新的裝置時，他們會在設定裝置時輸入其 Azure 認證，以經歷初次執行的體驗。</span><span class="sxs-lookup"><span data-stu-id="7799e-117">When Microsoft Managed Desktop users receive a new device, they go through a first-run experience by entering their Azure credentials while setting up the device.</span></span> <span data-ttu-id="7799e-118">完成此程式之後，即可存取其桌面並獲得 OneDrive 體驗。</span><span class="sxs-lookup"><span data-stu-id="7799e-118">After this process is completed, they can access their desktop and have the OneDrive experience.</span></span>

1. <span data-ttu-id="7799e-119">系統會告知使用者已設定 OneDrive，且已自動登入 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="7799e-119">The system tells users that OneDrive has been configured and that they have been automatically signed into OneDrive.</span></span>

:::image type="content" source="media/onedrive-sync.png" alt-text="通知讀取您現在正在同步處理 OneDrive，您可以在 OneDrive 中編輯檔案。按一下這裡以查看您的檔案":::

2. <span data-ttu-id="7799e-121">系統會告訴使用者已為使用者設定 OneDrive 已知資料夾移動。</span><span class="sxs-lookup"><span data-stu-id="7799e-121">The system tells users that OneDrive Known Folder Move has been configured for them.</span></span>

:::image type="content" source="media/onedrive-folders.png" alt-text="讀取您的 IT 部門的通知已備份重要的資料夾。現在，資料夾會備份至 OneDrive，並可從其他裝置取得。":::

3. <span data-ttu-id="7799e-123">若要在裝置重設或 reimaged 時避免桌面上的重複圖示，系統會自動移除 OneDrive 同步中 Microsoft Edge 和 Microsoft Teams 圖示，如檔案瀏覽器中的此視圖所示。</span><span class="sxs-lookup"><span data-stu-id="7799e-123">To prevent duplicate icons on the desktop when devices are being reset or reimaged, the system automatically removes Microsoft Edge and Microsoft Teams icons from the OneDrive sync, as shown in this view in File Explorer.</span></span>

:::image type="content" source="media/onedrive-teams.png" alt-text="檔案瀏覽器顯示的 Teams 和 Edge 清單，其中包含已清除的核取方塊及未同步處理的懸停文字讀取。":::


## <a name="onedrive-sync-restrictions"></a><span data-ttu-id="7799e-125">OneDrive 同步處理限制</span><span class="sxs-lookup"><span data-stu-id="7799e-125">OneDrive sync restrictions</span></span>

<span data-ttu-id="7799e-126">如果您需要限制 OneDrive 同步處理，建議您使用 Azure Active Directory 條件式存取原則來控制存取。</span><span class="sxs-lookup"><span data-stu-id="7799e-126">If you need to restrict OneDrive sync, we recommend that you control access with an Azure Active Directory conditional access policy.</span></span> <span data-ttu-id="7799e-127">如需詳細資訊，請參閱[在 OneDrive 同步處理應用程式中啟用條件式存取支援](/onedrive/enable-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="7799e-127">For more information, see [Enable conditional access support in the OneDrive sync app](/onedrive/enable-conditional-access).</span></span>

<span data-ttu-id="7799e-128">如果您的組織中不能使用 Azure AD 條件式存取原則，您的 IT 系統管理員應該遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7799e-128">If you can't use an Azure AD conditional access policy in your organization, your IT Admin should follow these steps:</span></span>

1. <span data-ttu-id="7799e-129">如果您還沒有知道，請查詢您的租使用者識別碼，如[尋找您的 Microsoft 365 租使用者識別碼](/onedrive/find-your-office-365-tenant-id)所述。</span><span class="sxs-lookup"><span data-stu-id="7799e-129">If you don't already know it, look up your tenant ID, as described in [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).</span></span>
2. <span data-ttu-id="7799e-130">登入 OneDrive 系統管理中心，然後在左窗格中選取 [**同步** 處理]。</span><span class="sxs-lookup"><span data-stu-id="7799e-130">Sign in to the OneDrive admin center, and then select **Sync** in the left pane.</span></span> <span data-ttu-id="7799e-131">選取 [ **只允許在加入特定網域的電腦上進行同步** 處理] 核取方塊，然後將租使用者識別碼新增至網域清單。</span><span class="sxs-lookup"><span data-stu-id="7799e-131">Select the **Allow syncing only on PCs joined to specific domains** check box, and then add the tenant ID to the list of domains.</span></span> <span data-ttu-id="7799e-132">如需詳細資訊，請參閱 [僅允許同步處理加入特定網域的電腦](/onedrive/allow-syncing-only-on-specific-domains)。</span><span class="sxs-lookup"><span data-stu-id="7799e-132">For more information, see [Allow syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains).</span></span>

> [!NOTE]
> <span data-ttu-id="7799e-133">此指南只適用于 Microsoft 受管理的電腦中的承租人。</span><span class="sxs-lookup"><span data-stu-id="7799e-133">This guidance applies only to tenants in Microsoft Managed Desktop.</span></span> <span data-ttu-id="7799e-134">其他使用中的設定不在本文中討論。</span><span class="sxs-lookup"><span data-stu-id="7799e-134">There are other settings in use that aren't discussed in this article.</span></span>