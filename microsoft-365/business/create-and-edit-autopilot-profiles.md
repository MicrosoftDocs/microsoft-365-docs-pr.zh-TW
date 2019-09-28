---
title: 建立及編輯 AutoPilot 設定檔
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: '了解如何建立、 編輯、 刪除或移除 AutoPilot 設定檔。 '
ms.openlocfilehash: 8fae8af5e7aa7b866745d0b34a4fe11862de6e9d
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287768"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="2f6ab-103">建立及編輯 AutoPilot 設定檔</span><span class="sxs-lookup"><span data-stu-id="2f6ab-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="2f6ab-104">建立設定檔</span><span class="sxs-lookup"><span data-stu-id="2f6ab-104">Create a profile</span></span>

<span data-ttu-id="2f6ab-105">設定檔適用於單一裝置或一組裝置。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="2f6ab-106">在 Microsoft 365 商務版系統管理中心中，選擇 [**裝置**] \> **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="2f6ab-107">在**自動駕駛**頁面上，選擇 [**設定檔**] 索引標籤\>**建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="2f6ab-108">在 [**建立設定檔**] 頁面上，輸入可協助您識別，例如行銷，開啟您想要 （如需詳細資訊，請參閱[關於 AutoPilot 設定檔設定](autopilot-profile-settings.md)，） 的設定，然後選擇 [**儲存**設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="2f6ab-110">將設定檔套用到裝置</span><span class="sxs-lookup"><span data-stu-id="2f6ab-110">Apply profile to a device</span></span>

<span data-ttu-id="2f6ab-p101">建立設定檔之後，您可以將它套用到單一裝置或一組裝置。您可以在[逐步指南](add-autopilot-devices-and-profile.md)中挑選現有設定檔、可以將設定檔套用到新裝置，或者也可以取代單一裝置或一組裝置的現有設定檔。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="2f6ab-113">在 [**準備 Windows** ] 頁面上，選擇 [**裝置**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-113">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="2f6ab-114">按一下核取方塊，裝置名稱旁邊，然後在 [**裝置**] 面板中，從**指派的設定檔**下拉式清單中選擇設定檔\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="2f6ab-116">編輯、刪除或移除設定檔</span><span class="sxs-lookup"><span data-stu-id="2f6ab-116">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="2f6ab-p102">一旦為裝置指派設定檔後，即使您已將裝置提供給使用者，您仍可更新設定檔。當裝置連線到網際網路時，它會在設定程序期間下載您的最新版設定檔。如果使用者將其裝置還原為其原廠預設設定，裝置會將最新更新再次下載到您的設定檔。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="2f6ab-120">編輯設定檔</span><span class="sxs-lookup"><span data-stu-id="2f6ab-120">Edit a profile</span></span>

1. <span data-ttu-id="2f6ab-121">在 [**準備 Windows** ] 頁面上，選擇 [**設定檔**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-121">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="2f6ab-122">按一下裝置名稱旁邊的核取方塊，並在 [**設定檔**] 面板更新任何可用設定\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="2f6ab-123">如果您在使用者將裝置連線到網際網路之前這麼做，設定檔則會套用到設定程序。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-123">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="2f6ab-124">刪除設定檔</span><span class="sxs-lookup"><span data-stu-id="2f6ab-124">Delete a profile</span></span>

1. <span data-ttu-id="2f6ab-125">在 [**準備 Windows** ] 頁面上，選擇 [**設定檔**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-125">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="2f6ab-126">按一下裝置名稱旁邊的核取方塊，然後在 [**設定檔**] 面板中按一下 [**刪除設定檔** \> **儲存**。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="2f6ab-127">當您刪除設定檔時，會移除單一裝置或一組裝置中的獲派設定檔。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-127">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="2f6ab-128">移除設定檔</span><span class="sxs-lookup"><span data-stu-id="2f6ab-128">Remove a profile</span></span>

1. <span data-ttu-id="2f6ab-129">在 [**準備 Windows** ] 頁面上，選擇 [**裝置**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-129">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="2f6ab-130">按一下核取方塊，裝置名稱旁邊，然後在 [**裝置**] 面板中，從**指派的設定檔**下拉式清單選擇 [**無** \> **儲存**。</span><span class="sxs-lookup"><span data-stu-id="2f6ab-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
