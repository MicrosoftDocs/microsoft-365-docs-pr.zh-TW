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
description: 了解如何上傳 Microsoft 365 商務版中使用 AutoPilot 裝置。 您可以將設定檔指派到單一裝置或一組裝置。
ms.openlocfilehash: 640e4af7cccde83c87d90a875c1d44dead7255ca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065968"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="6a295-104">建立及編輯 AutoPilot 裝置</span><span class="sxs-lookup"><span data-stu-id="6a295-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="6a295-105">上傳裝置清單</span><span class="sxs-lookup"><span data-stu-id="6a295-105">Upload a list of devices</span></span>

<span data-ttu-id="6a295-106">您可以使用[逐步指南](add-autopilot-devices-and-profile.md)來上傳裝置，但您也可以上傳**裝置**] 索引標籤中的裝置。</span><span class="sxs-lookup"><span data-stu-id="6a295-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="6a295-107">裝置必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="6a295-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="6a295-108">Windows 10 版本 1703 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6a295-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="6a295-109">新裝置尚未透過 Windows 現成可用的經驗</span><span class="sxs-lookup"><span data-stu-id="6a295-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="6a295-110">在 Microsoft 365 商務版系統管理中心中，選擇 [**裝置**] \> **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="6a295-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="6a295-111">在**自動駕駛**頁面上，選擇 [**裝置**] 索引標籤\>**新增裝置**。</span><span class="sxs-lookup"><span data-stu-id="6a295-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="6a295-113">在 [**新增裝置**] 面板中，瀏覽至您備妥的[裝置清單 CSV 檔案](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) \> **儲存** \> **關閉**。</span><span class="sxs-lookup"><span data-stu-id="6a295-113">On the **Add devices** panel, browse to a [Device list CSV file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="6a295-114">您可以從您的硬體廠商取得這項資訊，或您可以使用[Get-windowsautopilotinfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)來產生 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="6a295-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="6a295-115">針對裝置或裝置群組指派設定檔</span><span class="sxs-lookup"><span data-stu-id="6a295-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="6a295-116">在 [**準備 Windows** ] 頁面上選擇 [**裝置**] 索引標籤，並選取一個或多個裝置旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6a295-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="6a295-117">在 [**裝置**] 面板中，選取 [設定檔從**指派的設定檔**下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="6a295-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="6a295-118">如果您沒有任何設定檔，請參閱[建立及編輯 AutoPilot 設定檔](create-and-edit-autopilot-profiles.md)以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="6a295-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
