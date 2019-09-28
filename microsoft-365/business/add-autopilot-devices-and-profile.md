---
title: 使用逐步指南新增 Autopilot 裝置和設定檔
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 了解如何使用 Windows AutoPilot 為貴公司的新 Windows 10 裝置上設定。
ms.openlocfilehash: 563c3bbbc9f69996778417b35cfaa64d089770ef
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287588"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="3bc22-103">使用逐步指南新增 Autopilot 裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="3bc22-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="3bc22-104">您可以使用 Windows AutoPilot 來讓裝置備妥用於工作生產，為您提供給您的員工貴公司設定**新**的 Windows 10 裝置上。</span><span class="sxs-lookup"><span data-stu-id="3bc22-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="3bc22-105">裝置需求</span><span class="sxs-lookup"><span data-stu-id="3bc22-105">Device requirements</span></span>

<span data-ttu-id="3bc22-106">裝置必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="3bc22-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="3bc22-107">Windows 10 版本 1703 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="3bc22-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="3bc22-108">新裝置尚未執行過 Windows 全新體驗設定。</span><span class="sxs-lookup"><span data-stu-id="3bc22-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="3bc22-109">使用設定指南建立裝置和設定檔</span><span class="sxs-lookup"><span data-stu-id="3bc22-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="3bc22-110">[![標籤，讓您知道變更在系統管理中心，然後您可以在 aka.ms/aboutM365preview 尋找更多詳細資料。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="3bc22-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="3bc22-111">如果您尚未建立裝置群組或設定檔，最佳的開始使用方式是使用逐步指南，但您也可以[新增裝置](create-and-edit-autopilot-devices.md)及[指派設定檔](create-and-edit-autopilot-profiles.md)給裝置，而不使用指南。</span><span class="sxs-lookup"><span data-stu-id="3bc22-111">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="3bc22-112">移至系統管理中心， <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。</span><span class="sxs-lookup"><span data-stu-id="3bc22-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="3bc22-113">在左側導覽中選擇 [**裝置** \> **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="3bc22-113">On the left nav choose **Devices** \> **AutoPilot**.</span></span>

    ![在系統管理中心選擇 [裝置，然後自動駕駛。](media/AutoPilot.png)
  
2. <span data-ttu-id="3bc22-115">在**自動駕駛**頁面上，按一下或點選 [**開始指南**。</span><span class="sxs-lookup"><span data-stu-id="3bc22-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="3bc22-117">在 [**上傳裝置清單的.csv 檔案**] 頁面上，瀏覽到您已準備好位置。CSV 檔案，然後**開啟** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="3bc22-117">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="3bc22-118">檔案應該會有三個標題：</span><span class="sxs-lookup"><span data-stu-id="3bc22-118">The file should have three headers:</span></span>
    
  - <span data-ttu-id="3bc22-119">欄 A：裝置序號</span><span class="sxs-lookup"><span data-stu-id="3bc22-119">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="3bc22-120">欄 B：Windows 產品識別碼</span><span class="sxs-lookup"><span data-stu-id="3bc22-120">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="3bc22-121">欄 C：硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="3bc22-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="3bc22-122">您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。</span><span class="sxs-lookup"><span data-stu-id="3bc22-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="3bc22-123">如需詳細資訊，請參閱[裝置清單 CSV 檔案](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。</span><span class="sxs-lookup"><span data-stu-id="3bc22-123">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e).</span></span> <span data-ttu-id="3bc22-124">您也可以下載範例檔案**上傳裝置清單的.csv 檔案**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="3bc22-124">You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="3bc22-125">在**指派設定檔**] 頁面中，您可以挑選現有設定檔，或建立一個新。</span><span class="sxs-lookup"><span data-stu-id="3bc22-125">On the **Assign a profile** page, you can either pick an existing profile, or create a new one.</span></span> <span data-ttu-id="3bc22-126">如果您還沒有設定檔，您將看到建立設定檔的提示。</span><span class="sxs-lookup"><span data-stu-id="3bc22-126">If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="3bc22-127">設定檔是可套用到單一裝置或一組裝置的設定集合。</span><span class="sxs-lookup"><span data-stu-id="3bc22-127">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="3bc22-p104">預設功能是必要的，而且會自動設定。預設功能包括：</span><span class="sxs-lookup"><span data-stu-id="3bc22-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="3bc22-130">略過 Cortana、OneDrive 及 OEM 註冊。</span><span class="sxs-lookup"><span data-stu-id="3bc22-130">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="3bc22-131">使用公司品牌建立登入體驗。</span><span class="sxs-lookup"><span data-stu-id="3bc22-131">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="3bc22-132">裝置即將連線到 Azure Active Directory 帳戶，而且會自動註冊為受 Microsoft 365 商務版管理。</span><span class="sxs-lookup"><span data-stu-id="3bc22-132">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="3bc22-133">如需詳細資訊，請參閱</span><span class="sxs-lookup"><span data-stu-id="3bc22-133">For more information, see</span></span>
    
    <span data-ttu-id="3bc22-134">[關於 AutoPilot 設定檔的設定](autopilot-profile-settings.md) 。</span><span class="sxs-lookup"><span data-stu-id="3bc22-134">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="3bc22-135">其他設定，而**略過的隱私權設定\*\*\*\*不會讓使用者成為本機系統管理員**。這些都設定為**Off**預設。</span><span class="sxs-lookup"><span data-stu-id="3bc22-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="3bc22-136">選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3bc22-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="3bc22-137">**大功告成**] 頁面會指出您建立 （或選擇） 的設定檔將會套用至您建立所上傳裝置清單的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="3bc22-137">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="3bc22-138">這些設定會在裝置使用者下次登入時生效。</span><span class="sxs-lookup"><span data-stu-id="3bc22-138">These settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="3bc22-139">選擇 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3bc22-139">Choose **Close**.</span></span>
    