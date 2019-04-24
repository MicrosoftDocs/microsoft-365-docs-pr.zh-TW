---
title: 使用逐步指南新增 Autopilot 裝置和設定檔
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 了解如何使用 Windows AutoPilot 為貴公司的新 Windows 10 裝置上設定。
ms.openlocfilehash: e0802ddcc0964d0b8d102f7dbdb9116b33cdcf58
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277073"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="e69c1-103">使用逐步指南新增 Autopilot 裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="e69c1-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="e69c1-104">您可以使用 Windows AutoPilot 為貴公司設定新的 Windows 10 裝置，在員工獲得您提供的裝置時，就能立即使用並發揮生產力。</span><span class="sxs-lookup"><span data-stu-id="e69c1-104">You can use Windows AutoPilot to set up new Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="e69c1-105">裝置需求</span><span class="sxs-lookup"><span data-stu-id="e69c1-105">Device requirements</span></span>

<span data-ttu-id="e69c1-106">裝置必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="e69c1-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="e69c1-107">Windows 10 版本 1703 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="e69c1-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="e69c1-108">新裝置尚未執行過 Windows 全新體驗設定。</span><span class="sxs-lookup"><span data-stu-id="e69c1-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="e69c1-109">使用設定指南建立裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="e69c1-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="e69c1-110">如果您尚未建立裝置群組或設定檔，最佳的開始使用方式是使用逐步指南，但您也可以[新增裝置](create-and-edit-autopilot-devices.md)及[指派設定檔](create-and-edit-autopilot-profiles.md)給裝置，而不使用指南。</span><span class="sxs-lookup"><span data-stu-id="e69c1-110">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="e69c1-111">在 Microsoft 365 商務版系統管理中心中，找出 [**裝置動作**] 卡片，然後選擇 [**透過 Autopilot 部署 Windows**。</span><span class="sxs-lookup"><span data-stu-id="e69c1-111">In the Microsoft 365 Business admin center, locate the **Device actions** card, and choose **Deploy Windows with Autopilot**.</span></span>
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="e69c1-113">在 [**準備 Windows** ] 頁面上，按一下或點選 [**開始指南**。</span><span class="sxs-lookup"><span data-stu-id="e69c1-113">On the **Prepare Windows** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="e69c1-115">在 [**上傳裝置清單的.csv 檔案**] 頁面上，瀏覽到您已準備好位置。CSV 檔案，然後**開啟** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="e69c1-115">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="e69c1-116">檔案應該會有三個標題：</span><span class="sxs-lookup"><span data-stu-id="e69c1-116">The file should have three headers:</span></span>
    
  - <span data-ttu-id="e69c1-117">欄 A：裝置序號</span><span class="sxs-lookup"><span data-stu-id="e69c1-117">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="e69c1-118">欄 B：Windows 產品識別碼</span><span class="sxs-lookup"><span data-stu-id="e69c1-118">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="e69c1-119">欄 C：硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="e69c1-119">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="e69c1-120">您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。</span><span class="sxs-lookup"><span data-stu-id="e69c1-120">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="e69c1-121">如需詳細資訊，請參閱[裝置清單 CSV 檔案](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。</span><span class="sxs-lookup"><span data-stu-id="e69c1-121">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e).</span></span> <span data-ttu-id="e69c1-122">您也可以下載範例檔案**上傳裝置清單的.csv 檔案**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="e69c1-122">You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="e69c1-123">在**指派設定檔**] 頁面中，您可以挑選現有設定檔，或建立一個新。</span><span class="sxs-lookup"><span data-stu-id="e69c1-123">On the **Assign a profile** page, you can either pick an existing profile, or create a new one.</span></span> <span data-ttu-id="e69c1-124">如果您還沒有設定檔，您將看到建立設定檔的提示。</span><span class="sxs-lookup"><span data-stu-id="e69c1-124">If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="e69c1-125">設定檔是可套用到單一裝置或一組裝置的設定集合。</span><span class="sxs-lookup"><span data-stu-id="e69c1-125">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="e69c1-p104">預設功能是必要的，而且會自動設定。預設功能包括：</span><span class="sxs-lookup"><span data-stu-id="e69c1-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="e69c1-128">略過 Cortana、OneDrive 及 OEM 註冊。</span><span class="sxs-lookup"><span data-stu-id="e69c1-128">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="e69c1-129">使用公司品牌建立登入體驗。</span><span class="sxs-lookup"><span data-stu-id="e69c1-129">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="e69c1-130">裝置即將連線到 Azure Active Directory 帳戶，而且會自動註冊為受 Microsoft 365 商務版管理。</span><span class="sxs-lookup"><span data-stu-id="e69c1-130">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="e69c1-131">如需詳細資訊，請參閱</span><span class="sxs-lookup"><span data-stu-id="e69c1-131">For more information, see</span></span>
    
    <span data-ttu-id="e69c1-132">[關於 AutoPilot 設定檔的設定](autopilot-profile-settings.md) 。</span><span class="sxs-lookup"><span data-stu-id="e69c1-132">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="e69c1-133">其他設定，而**略過的隱私權設定\*\*\*\*不會讓使用者成為本機系統管理員**。這些都設定為**Off**預設。</span><span class="sxs-lookup"><span data-stu-id="e69c1-133">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="e69c1-134">選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e69c1-134">Choose **Next**.</span></span>
    
6. <span data-ttu-id="e69c1-135">**大功告成**] 頁面會指出您建立 （或選擇） 的設定檔將會套用至您建立所上傳裝置清單的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="e69c1-135">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="e69c1-136">這些設定會在裝置使用者下次登入時生效。</span><span class="sxs-lookup"><span data-stu-id="e69c1-136">These settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="e69c1-137">選擇 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e69c1-137">Choose **Close**.</span></span>
    