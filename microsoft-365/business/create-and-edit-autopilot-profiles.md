---
title: 建立及編輯 AutoPilot 設定檔
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 瞭解如何建立 AutoPilot 設定檔，並將其套用至裝置，以及編輯或刪除設定檔，或從裝置移除設定檔。
ms.openlocfilehash: e58418813ed0b4d23a5fa7e1d23aae33d8850e7f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400967"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="762d0-103">建立及編輯 AutoPilot 設定檔</span><span class="sxs-lookup"><span data-stu-id="762d0-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="762d0-104">建立設定檔</span><span class="sxs-lookup"><span data-stu-id="762d0-104">Create a profile</span></span>

<span data-ttu-id="762d0-105">設定檔適用於單一裝置或一組裝置。</span><span class="sxs-lookup"><span data-stu-id="762d0-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="762d0-106">在 Microsoft 365 系統管理中心，選擇 [**裝置**] \> **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="762d0-106">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="762d0-107">在 [ **AutoPilot** ] 頁面上，選擇 [**設定檔**] 索引標籤 \> **建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="762d0-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="762d0-108">在 [**建立設定檔**] 頁面上，輸入設定檔的名稱，以協助您識別，例如「行銷」。</span><span class="sxs-lookup"><span data-stu-id="762d0-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="762d0-109">開啟您想要的設定，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="762d0-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="762d0-110">如需 AutoPilot 設定檔設定的詳細資訊，請參閱[關於 AutoPilot 設定檔設定](autopilot-profile-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="762d0-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="762d0-112">將設定檔套用到裝置</span><span class="sxs-lookup"><span data-stu-id="762d0-112">Apply profile to a device</span></span>

<span data-ttu-id="762d0-113">在您建立設定檔之後，您可以將它套用至裝置或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="762d0-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="762d0-114">您可以在[逐步指南](add-autopilot-devices-and-profile.md)中挑選現有的設定檔，並將其套用至新裝置，或取代裝置或裝置群組的現有設定檔。</span><span class="sxs-lookup"><span data-stu-id="762d0-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="762d0-115">在 [**準備 Windows** ] 頁面上，選擇 [**裝置**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="762d0-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="762d0-116">選取裝置名稱旁邊的核取方塊，然後在 [**裝置**] 面板中，從 [**已指派的設定檔**] 下拉式清單中選擇設定檔 \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="762d0-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="762d0-118">編輯、刪除或移除設定檔</span><span class="sxs-lookup"><span data-stu-id="762d0-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="762d0-p103">一旦為裝置指派設定檔後，即使您已將裝置提供給使用者，您仍可更新設定檔。當裝置連線到網際網路時，它會在設定程序期間下載您的最新版設定檔。如果使用者將其裝置還原為其原廠預設設定，裝置會將最新更新再次下載到您的設定檔。</span><span class="sxs-lookup"><span data-stu-id="762d0-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="762d0-122">編輯設定檔</span><span class="sxs-lookup"><span data-stu-id="762d0-122">Edit a profile</span></span>

1. <span data-ttu-id="762d0-123">在 [**準備 Windows** ] 頁面上，選擇 [**設定檔**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="762d0-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="762d0-124">選取裝置名稱旁邊的核取方塊，然後在 [**設定檔**] 面板中，更新任何可用的設定 \> **儲存**。</span><span class="sxs-lookup"><span data-stu-id="762d0-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="762d0-125">如果您在使用者將裝置連線到網際網路之前這麼做，設定檔則會套用到設定程序。</span><span class="sxs-lookup"><span data-stu-id="762d0-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="762d0-126">刪除設定檔</span><span class="sxs-lookup"><span data-stu-id="762d0-126">Delete a profile</span></span>

1. <span data-ttu-id="762d0-127">在 [**準備 Windows** ] 頁面上，選擇 [**設定檔**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="762d0-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="762d0-128">選取裝置名稱旁邊的核取方塊，然後在 [**設定檔**] 面板中，選取 [**刪除設定檔** \> **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="762d0-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="762d0-129">當您刪除設定檔時，會移除單一裝置或一組裝置中的獲派設定檔。</span><span class="sxs-lookup"><span data-stu-id="762d0-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="762d0-130">移除設定檔</span><span class="sxs-lookup"><span data-stu-id="762d0-130">Remove a profile</span></span>

1. <span data-ttu-id="762d0-131">在 [**準備 Windows** ] 頁面上，選擇 [**裝置**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="762d0-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="762d0-132">選取裝置名稱旁邊的核取方塊，然後在 [**裝置**] 面板中，從 [**已指派的設定檔**] 下拉式清單中選擇 [**無**] \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="762d0-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
