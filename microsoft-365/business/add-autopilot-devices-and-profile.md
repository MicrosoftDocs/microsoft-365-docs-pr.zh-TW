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
description: 瞭解如何使用 Windows AutoPilot 為您的公司設定新的 Windows 10 裝置，使其可供員工使用。
ms.openlocfilehash: e178e7df220e89605502d9ed400265bcd963e57e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636099"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="bbd92-103">使用逐步指南新增 Autopilot 裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="bbd92-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="bbd92-104">您可以使用 Windows AutoPilot 為您的公司設定 **新** 的 Windows 10 裝置，以便在您將其授與員工時使用。</span><span class="sxs-lookup"><span data-stu-id="bbd92-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="bbd92-105">裝置需求</span><span class="sxs-lookup"><span data-stu-id="bbd92-105">Device requirements</span></span>

<span data-ttu-id="bbd92-106">裝置必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="bbd92-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="bbd92-107">Windows 10，版本1703或更新版本</span><span class="sxs-lookup"><span data-stu-id="bbd92-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="bbd92-108">尚未透過 Windows 全新體驗的新裝置</span><span class="sxs-lookup"><span data-stu-id="bbd92-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="bbd92-109">使用設定指南建立裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="bbd92-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="bbd92-110">若尚未建立裝置群組或設定檔，最好的入門方式是使用逐步指南。</span><span class="sxs-lookup"><span data-stu-id="bbd92-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="bbd92-111">您也可以 [新增裝置](create-and-edit-autopilot-devices.md) ，並 [將設定檔指派](create-and-edit-autopilot-profiles.md) 給它們，而不需使用輔助線。</span><span class="sxs-lookup"><span data-stu-id="bbd92-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="bbd92-112">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="bbd92-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="bbd92-113">在左功能窗格中，選擇 [ **裝置**] \> **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="bbd92-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![在系統管理中心中，選擇 [裝置]，然後 AutoPilot]。](../media/AutoPilot.png)
  
2. <span data-ttu-id="bbd92-115">在 [ **AutoPilot** ] 頁面上，按一下或點擊 [ **開始指南**]。</span><span class="sxs-lookup"><span data-stu-id="bbd92-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="bbd92-117">在 [ **Upload .csv 具有裝置清單的** 檔案] 頁面上，流覽至您已準備好 .CSV 檔案的位置，然後 **開啟** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bbd92-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="bbd92-118">檔案必須有三個標頭：</span><span class="sxs-lookup"><span data-stu-id="bbd92-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="bbd92-119">欄 A：裝置序號</span><span class="sxs-lookup"><span data-stu-id="bbd92-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="bbd92-120">欄 B：Windows 產品識別碼</span><span class="sxs-lookup"><span data-stu-id="bbd92-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="bbd92-121">欄 C：硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="bbd92-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="bbd92-122">您可以從硬體廠商取得此資訊，也可以使用 [Get-WindowsAutoPilotInfo PowerShell 腳本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 來產生 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="bbd92-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="bbd92-123">如需詳細資訊，請參閱[裝置清單 CSV 檔案](../admin/misc/device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="bbd92-123">For more information, see [Device list CSV-file](../admin/misc/device-list.md).</span></span> <span data-ttu-id="bbd92-124">您也可以 **使用 [裝置清單**] 頁面，在 [Upload .csv 檔案] 頁面上下載範例檔案。</span><span class="sxs-lookup"><span data-stu-id="bbd92-124">You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="bbd92-125">此腳本會使用 WMI 來取得客戶使用 Windows Autopilot 註冊裝置所需的屬性。</span><span class="sxs-lookup"><span data-stu-id="bbd92-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="bbd92-126">請注意，產生的 CSV 檔案不會收集 Windows 產品識別碼 (PKID) 值，因為不需要在輸出 CSV 中註冊裝置及 PKID 為 Null，就完全正確。</span><span class="sxs-lookup"><span data-stu-id="bbd92-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="bbd92-127">只會填入序號碼和硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="bbd92-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="bbd92-128">在 [ **指派設定檔** ] 頁面上，您可以挑選現有的設定檔或建立新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="bbd92-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="bbd92-129">如果您還沒有，系統會提示您建立一個。</span><span class="sxs-lookup"><span data-stu-id="bbd92-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="bbd92-130">設定檔是可套用到單一裝置或一組裝置的設定集合。</span><span class="sxs-lookup"><span data-stu-id="bbd92-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="bbd92-131">預設功能是必要的，且會自動設定。</span><span class="sxs-lookup"><span data-stu-id="bbd92-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="bbd92-132">預設功能包括：</span><span class="sxs-lookup"><span data-stu-id="bbd92-132">The default features are:</span></span>
    
    - <span data-ttu-id="bbd92-133">略過 Cortana、OneDrive 及 OEM 註冊。</span><span class="sxs-lookup"><span data-stu-id="bbd92-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="bbd92-134">使用公司品牌建立登入體驗。</span><span class="sxs-lookup"><span data-stu-id="bbd92-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="bbd92-135">連線您的裝置以 Azure Active Directory 帳戶，並自動將其註冊為由 Microsoft 365 商務進階版進行管理。</span><span class="sxs-lookup"><span data-stu-id="bbd92-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="bbd92-136">如需詳細資訊，請參閱 [關於 AutoPilot 設定檔設定](autopilot-profile-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="bbd92-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="bbd92-137">其他設定則 **略過隱私權設定** ，而 **不允許使用者成為本機系統管理員**。這些皆預設會設為 **Off** 。</span><span class="sxs-lookup"><span data-stu-id="bbd92-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="bbd92-138">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bbd92-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="bbd92-139">**您已完成** 表示您已建立的設定檔 (或選擇) 會套用到您透過上載裝置清單所建立的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="bbd92-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="bbd92-140">當裝置使用者下一次登入時，設定就會生效。</span><span class="sxs-lookup"><span data-stu-id="bbd92-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="bbd92-141">選擇 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="bbd92-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="bbd92-142">相關內容</span><span class="sxs-lookup"><span data-stu-id="bbd92-142">Related content</span></span>

<span data-ttu-id="bbd92-143">[關於 AutoPilot 設定檔設定](autopilot-profile-settings.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="bbd92-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="bbd92-144">[保護裝置及應用程式資料的選項](../admin/devices/choose-device-security.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="bbd92-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
