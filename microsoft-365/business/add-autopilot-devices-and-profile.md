---
title: 使用逐步指南新增 Autopilot 裝置和設定檔
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
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
description: 了解如何使用 Windows 自動駕駛儀上設定為貴公司的新 Windows 10 裝置。
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866117"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="b8247-103">使用逐步指南新增 Autopilot 裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="b8247-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="b8247-104">您可以使用 Windows AutoPilot 為貴公司設定新的 Windows 10 裝置，在員工獲得您提供的裝置時，就能立即使用並發揮生產力。</span><span class="sxs-lookup"><span data-stu-id="b8247-104">You can use Windows AutoPilot to set up new Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="b8247-105">裝置需求</span><span class="sxs-lookup"><span data-stu-id="b8247-105">Device requirements</span></span>

<span data-ttu-id="b8247-106">裝置必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="b8247-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="b8247-107">Windows 10 版本 1703 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b8247-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="b8247-108">新裝置尚未執行過 Windows 全新體驗設定。</span><span class="sxs-lookup"><span data-stu-id="b8247-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="b8247-109">使用設定指南建立裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="b8247-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="b8247-110">如果您尚未建立裝置群組或設定檔，最佳的開始使用方式是使用逐步指南，但您也可以[新增裝置](create-and-edit-autopilot-devices.md)及[指派設定檔](create-and-edit-autopilot-profiles.md)給裝置，而不使用指南。</span><span class="sxs-lookup"><span data-stu-id="b8247-110">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="b8247-111">在 Microsoft 365 商務系統管理中心中，找到**裝置動作**卡片，然後選擇 [**使用自動駕駛儀上部署 Windows**。</span><span class="sxs-lookup"><span data-stu-id="b8247-111">In the Microsoft 365 Business admin center, locate the **Device actions** card, and choose **Deploy Windows with Autopilot**.</span></span>
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="b8247-113">在 [**準備 Windows** ] 頁面上按一下或點選**啟動指南 》**。</span><span class="sxs-lookup"><span data-stu-id="b8247-113">On the **Prepare Windows** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="b8247-p101">在 [**上傳.csv 檔案的裝置清單**] 頁面上，瀏覽至您已準備好位置。CSV 檔案，然後**開啟** \> **下一步**。檔案應該有三個標頭：</span><span class="sxs-lookup"><span data-stu-id="b8247-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="b8247-117">欄 A：裝置序號</span><span class="sxs-lookup"><span data-stu-id="b8247-117">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="b8247-118">欄 B：Windows 產品識別碼</span><span class="sxs-lookup"><span data-stu-id="b8247-118">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="b8247-119">欄 C：硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="b8247-119">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="b8247-120">您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。</span><span class="sxs-lookup"><span data-stu-id="b8247-120">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="b8247-p102">如需詳細資訊，請參閱[CSV 檔案的裝置清單](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。您也可以下載 [**上傳.csv 檔案的裝置清單**] 頁面上的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="b8247-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="b8247-p103">在 [**指定設定檔**] 頁面上可以選擇現有的設定檔，或建立一個新。如果您沒有一個尚未，系統會提示您建立一個新。</span><span class="sxs-lookup"><span data-stu-id="b8247-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="b8247-125">設定檔是可套用到單一裝置或一組裝置的設定集合。</span><span class="sxs-lookup"><span data-stu-id="b8247-125">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="b8247-p104">預設功能是必要的，而且會自動設定。預設功能包括：</span><span class="sxs-lookup"><span data-stu-id="b8247-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="b8247-128">略過 Cortana、OneDrive 及 OEM 註冊。</span><span class="sxs-lookup"><span data-stu-id="b8247-128">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="b8247-129">使用公司品牌建立登入體驗。</span><span class="sxs-lookup"><span data-stu-id="b8247-129">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="b8247-130">裝置即將連線到 Azure Active Directory 帳戶，而且會自動註冊為受 Microsoft 365 商務版管理。</span><span class="sxs-lookup"><span data-stu-id="b8247-130">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="b8247-131">如需詳細資訊，請參閱</span><span class="sxs-lookup"><span data-stu-id="b8247-131">For more information, see</span></span>
    
    <span data-ttu-id="b8247-132">[關於 AutoPilot 設定檔的設定](autopilot-profile-settings.md) 。</span><span class="sxs-lookup"><span data-stu-id="b8247-132">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="b8247-133">其他設定會**略過隱私權設定**並**不允許使用者可以成為本機管理員**。這些皆被設為**關閉**預設。</span><span class="sxs-lookup"><span data-stu-id="b8247-133">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="b8247-134">選擇 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="b8247-134">Choose **Next**.</span></span>
    
6. <span data-ttu-id="b8247-p105">**完成**] 頁面上會指出建立 （或選擇） 的設定檔將會套用到您所上傳的裝置清單建立裝置群組。這些設定會對時裝置使用者登入下一步]。選擇 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="b8247-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    