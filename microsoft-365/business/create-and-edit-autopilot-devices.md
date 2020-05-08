---
title: 建立及編輯 AutoPilot 裝置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 瞭解如何使用 Microsoft 365 商務版 Premium 中的 AutoPilot 上傳裝置。 您可以將設定檔指派給裝置或裝置群組。
ms.openlocfilehash: 83c027cfe019e037518c4ca13eb331e5300fc2c1
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165854"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="1144a-104">建立及編輯 AutoPilot 裝置</span><span class="sxs-lookup"><span data-stu-id="1144a-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="1144a-105">上傳裝置清單</span><span class="sxs-lookup"><span data-stu-id="1144a-105">Upload a list of devices</span></span>

<span data-ttu-id="1144a-106">您可以使用逐步[指南](add-autopilot-devices-and-profile.md)來上傳裝置，但是您也可以在 [**裝置**] 索引標籤中上傳裝置。</span><span class="sxs-lookup"><span data-stu-id="1144a-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="1144a-107">裝置必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="1144a-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="1144a-108">Windows 10，版本1703或更新版本</span><span class="sxs-lookup"><span data-stu-id="1144a-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="1144a-109">尚未透過 Windows 現成體驗的新裝置</span><span class="sxs-lookup"><span data-stu-id="1144a-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="1144a-110">在 Microsoft 365 系統管理中心，選擇 [**裝置** \> ] **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="1144a-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="1144a-111">在 [ **AutoPilot** ] 頁面上，選擇 [**裝置**] 索引標籤 [ \> **新增裝置**]。</span><span class="sxs-lookup"><span data-stu-id="1144a-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="1144a-113">在 [**新增裝置**] 面板上，流覽至您準備\> **儲存** \> **關閉**的[裝置清單 CSV](https://docs.microsoft.com/microsoft-365/admin/misc/device-list)檔案。</span><span class="sxs-lookup"><span data-stu-id="1144a-113">On the **Add devices** panel, browse to a [Device list CSV file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="1144a-114">您可以從硬體廠商取得此資訊，也可以使用[Get-WindowsAutoPilotInfo PowerShell 腳本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)來產生 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="1144a-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="1144a-115">針對裝置或裝置群組指派設定檔</span><span class="sxs-lookup"><span data-stu-id="1144a-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="1144a-116">在 [**準備 Windows** ] 頁面上，選擇 [**裝置**] 索引標籤，然後選取一或多個裝置旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1144a-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="1144a-117">在 [**裝置**] 面板上，從 [**已指派的設定檔**] 下拉式清單中選取設定檔。</span><span class="sxs-lookup"><span data-stu-id="1144a-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="1144a-118">如果您沒有任何設定檔，請參閱[建立及編輯 AutoPilot 設定檔](create-and-edit-autopilot-profiles.md)以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="1144a-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
