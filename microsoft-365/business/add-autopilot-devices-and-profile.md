---
title: 使用逐步指南新增 Autopilot 裝置和設定檔
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 瞭解如何使用 Windows AutoPilot 為您的公司設定新的 Windows 10 裝置，以供員工使用。
ms.openlocfilehash: cd8777e6ae2e395506d2bf308c99309de1e24805
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578520"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="68585-103">使用逐步指南新增 Autopilot 裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="68585-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="68585-104">您可以使用 Windows AutoPilot 為您的公司設定 **新** 的 Windows 10 裝置，以便在您將其提供給員工時可供使用。</span><span class="sxs-lookup"><span data-stu-id="68585-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="68585-105">裝置需求</span><span class="sxs-lookup"><span data-stu-id="68585-105">Device requirements</span></span>

<span data-ttu-id="68585-106">裝置必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="68585-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="68585-107">Windows 10，版本1703或更新版本</span><span class="sxs-lookup"><span data-stu-id="68585-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="68585-108">尚未透過 Windows 現成體驗的新裝置</span><span class="sxs-lookup"><span data-stu-id="68585-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="68585-109">使用設定指南建立裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="68585-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="68585-110">[![[標籤] 可讓您知道系統管理中心正在變更，您可以在 aka.ms/aboutM365preview 取得更多詳細資料。](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="68585-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="68585-111">若尚未建立裝置群組或設定檔，最好的入門方式是使用逐步指南。</span><span class="sxs-lookup"><span data-stu-id="68585-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="68585-112">您也可以 [新增裝置](create-and-edit-autopilot-devices.md) ，並 [將設定檔指派](create-and-edit-autopilot-profiles.md) 給它們，而不需使用輔助線。</span><span class="sxs-lookup"><span data-stu-id="68585-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="68585-113">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="68585-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="68585-114">在左功能窗格中，選擇 [ **裝置**] \> **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="68585-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![在系統管理中心中，選擇 [裝置]，然後 AutoPilot]。](../media/AutoPilot.png)
  
2. <span data-ttu-id="68585-116">在 [ **AutoPilot** ] 頁面上，按一下或點擊 [ **開始指南**]。</span><span class="sxs-lookup"><span data-stu-id="68585-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="68585-118">在 [ **上傳含裝置清單的 .csv** 檔案] 頁面上，流覽至您準備好的位置。CSV 檔案，然後 **開啟** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="68585-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="68585-119">檔案必須有三個標頭：</span><span class="sxs-lookup"><span data-stu-id="68585-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="68585-120">欄 A：裝置序號</span><span class="sxs-lookup"><span data-stu-id="68585-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="68585-121">欄 B：Windows 產品識別碼</span><span class="sxs-lookup"><span data-stu-id="68585-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="68585-122">欄 C：硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="68585-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="68585-123">您可以從硬體廠商取得此資訊，也可以使用 [Get-WindowsAutoPilotInfo PowerShell 腳本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 來產生 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="68585-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="68585-124">如需詳細資訊，請參閱[裝置清單 CSV 檔案](../admin/misc/device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="68585-124">For more information, see [Device list CSV-file](../admin/misc/device-list.md).</span></span> <span data-ttu-id="68585-125">您也可以在 [ **上傳含裝置清單的 .csv** 檔案] 頁面上，下載範例檔案。</span><span class="sxs-lookup"><span data-stu-id="68585-125">You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="68585-126">此腳本會使用 WMI 來取得客戶使用 Windows Autopilot 註冊裝置所需的屬性。</span><span class="sxs-lookup"><span data-stu-id="68585-126">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="68585-127">請注意，產生的 CSV 檔案不會收集 Windows 產品識別碼 (PKID) 值，因為不需要在輸出 CSV 中註冊裝置和 PKID 是完全正常的方式。</span><span class="sxs-lookup"><span data-stu-id="68585-127">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="68585-128">只會填入序號碼和硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="68585-128">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="68585-129">在 [ **指派設定檔** ] 頁面上，您可以挑選現有的設定檔或建立新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="68585-129">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="68585-130">如果您還沒有，系統會提示您建立一個。</span><span class="sxs-lookup"><span data-stu-id="68585-130">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="68585-131">設定檔是可套用到單一裝置或一組裝置的設定集合。</span><span class="sxs-lookup"><span data-stu-id="68585-131">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="68585-132">預設功能是必要的，且會自動設定。</span><span class="sxs-lookup"><span data-stu-id="68585-132">The default features are required and are set automatically.</span></span> <span data-ttu-id="68585-133">預設功能包括：</span><span class="sxs-lookup"><span data-stu-id="68585-133">The default features are:</span></span>
    
    - <span data-ttu-id="68585-134">略過 Cortana、OneDrive 及 OEM 註冊。</span><span class="sxs-lookup"><span data-stu-id="68585-134">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="68585-135">使用公司品牌建立登入體驗。</span><span class="sxs-lookup"><span data-stu-id="68585-135">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="68585-136">將裝置連線到 Azure Active Directory 帳戶，並自動將其註冊為由 Microsoft 365 商務版 Premium 管理。</span><span class="sxs-lookup"><span data-stu-id="68585-136">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="68585-137">如需詳細資訊，請參閱 [關於 AutoPilot 設定檔設定](autopilot-profile-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="68585-137">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="68585-138">其他設定則 **略過隱私權設定** ，而 **不允許使用者成為本機系統管理員**。這些皆預設會設為 **Off** 。</span><span class="sxs-lookup"><span data-stu-id="68585-138">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="68585-139">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="68585-139">Choose **Next**.</span></span>
    
6. <span data-ttu-id="68585-140">**您已完成** 表示您已建立的設定檔 (或選擇) 會套用到您透過上載裝置清單所建立的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="68585-140">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="68585-141">當裝置使用者下一次登入時，設定就會生效。</span><span class="sxs-lookup"><span data-stu-id="68585-141">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="68585-142">選擇 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="68585-142">Choose **Close**.</span></span>
