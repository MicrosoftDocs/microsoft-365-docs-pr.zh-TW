---
title: 建立及編輯 AutoPilot 設定檔
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: '了解如何建立、 編輯、 刪除或移除自動駕駛儀上設定檔。 '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866423"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="189ff-103">建立及編輯 AutoPilot 設定檔</span><span class="sxs-lookup"><span data-stu-id="189ff-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="189ff-104">建立設定檔</span><span class="sxs-lookup"><span data-stu-id="189ff-104">Create a profile</span></span>

<span data-ttu-id="189ff-105">設定檔適用於單一裝置或一組裝置。</span><span class="sxs-lookup"><span data-stu-id="189ff-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="189ff-106">在 Microsoft 365 商務系統管理中心中，選擇 [**使用自動駕駛儀上部署 Windows** **裝置動作**卡片上。</span><span class="sxs-lookup"><span data-stu-id="189ff-106">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="189ff-108">在 [**準備 Windows** ] 頁面上選擇 [**設定檔**] 索引標籤\>**建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="189ff-108">On the **Prepare Windows** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="189ff-109">在 [**建立設定檔**] 頁面上輸入有助於您識別，例如行銷、 開啟您想 （請參閱[關於自動駕駛儀上設定檔設定](autopilot-profile-settings.md)如需詳細資訊，） 的設定和選擇 [**儲存**設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="189ff-109">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="189ff-111">將設定檔套用到裝置</span><span class="sxs-lookup"><span data-stu-id="189ff-111">Apply profile to a device</span></span>

<span data-ttu-id="189ff-p101">建立設定檔之後，您可以將它套用到單一裝置或一組裝置。您可以在[逐步指南](add-autopilot-devices-and-profile.md)中挑選現有設定檔、可以將設定檔套用到新裝置，或者也可以取代單一裝置或一組裝置的現有設定檔。</span><span class="sxs-lookup"><span data-stu-id="189ff-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="189ff-114">在 [**準備 Windows** ] 頁面上選擇 [**裝置**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="189ff-114">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="189ff-115">按一下 [核取方塊旁的裝置名稱及 [**裝置**] 面板中，從**已指派] 設定檔**] 下拉式清單中選擇一個設定檔\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="189ff-115">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="189ff-117">編輯、刪除或移除設定檔</span><span class="sxs-lookup"><span data-stu-id="189ff-117">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="189ff-p102">一旦為裝置指派設定檔後，即使您已將裝置提供給使用者，您仍可更新設定檔。當裝置連線到網際網路時，它會在設定程序期間下載您的最新版設定檔。如果使用者將其裝置還原為其原廠預設設定，裝置會將最新更新再次下載到您的設定檔。</span><span class="sxs-lookup"><span data-stu-id="189ff-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="189ff-121">編輯設定檔</span><span class="sxs-lookup"><span data-stu-id="189ff-121">Edit a profile</span></span>

1. <span data-ttu-id="189ff-122">在 [**準備 Windows** ] 頁面上選擇 [**設定檔**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="189ff-122">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="189ff-123">按一下 [裝置名稱旁核取方塊並**設定檔**中面板更新任何可用的設定\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="189ff-123">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="189ff-124">如果您在使用者將裝置連線到網際網路之前這麼做，設定檔則會套用到設定程序。</span><span class="sxs-lookup"><span data-stu-id="189ff-124">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="189ff-125">刪除設定檔</span><span class="sxs-lookup"><span data-stu-id="189ff-125">Delete a profile</span></span>

1. <span data-ttu-id="189ff-126">在 [**準備 Windows** ] 頁面上選擇 [**設定檔**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="189ff-126">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="189ff-127">按一下 [裝置名稱旁核取方塊並在 [**設定檔**] 面板中按一下 [**刪除設定檔** \> **儲存**。</span><span class="sxs-lookup"><span data-stu-id="189ff-127">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="189ff-128">當您刪除設定檔時，會移除單一裝置或一組裝置中的獲派設定檔。</span><span class="sxs-lookup"><span data-stu-id="189ff-128">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="189ff-129">移除設定檔</span><span class="sxs-lookup"><span data-stu-id="189ff-129">Remove a profile</span></span>

1. <span data-ttu-id="189ff-130">在 [**準備 Windows** ] 頁面上選擇 [**裝置**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="189ff-130">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="189ff-131">按一下 [核取方塊旁的裝置名稱及 [**裝置**] 面板中，選擇 [**無**從**已指派 profile**下拉式\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="189ff-131">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
