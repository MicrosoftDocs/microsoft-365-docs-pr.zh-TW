---
title: 建立及管理裝置標記
description: 使用裝置標記來群組裝置以捕獲內容，並在事件中啟用動態清單建立
keywords: 標籤，裝置標記，裝置群組，群組，修正，層級，規則，aad 群組，角色，指派，排名
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187586"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="3d2b2-104">建立及管理裝置標記</span><span class="sxs-lookup"><span data-stu-id="3d2b2-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3d2b2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3d2b2-105">**Applies to:**</span></span>
- [<span data-ttu-id="3d2b2-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3d2b2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3d2b2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d2b2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3d2b2-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3d2b2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3d2b2-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3d2b2-110">在裝置上新增標記，以建立邏輯群組從屬關係。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="3d2b2-111">裝置標記支援正確的網路對應，可讓您附加不同的標記以捕獲內容，並在事件中啟用動態清單建立。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="3d2b2-112">標籤可在 **裝置清單** 視圖中做為篩選器，或群組裝置使用。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="3d2b2-113">如需裝置群組的詳細資訊，請參閱 [Create and manage device groups](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="3d2b2-114">您可以使用下列方法，在裝置上新增標籤：</span><span class="sxs-lookup"><span data-stu-id="3d2b2-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="3d2b2-115">使用入口網站</span><span class="sxs-lookup"><span data-stu-id="3d2b2-115">Using the portal</span></span>
- <span data-ttu-id="3d2b2-116">設定登錄機碼值</span><span class="sxs-lookup"><span data-stu-id="3d2b2-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="3d2b2-117">在標籤新增至裝置清單和裝置中的裝置及其可用性時，可能會有一些延遲。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="3d2b2-118">若要使用 API 新增裝置標記，請參閱 [add or remove device TAGS API](add-or-remove-machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="3d2b2-119">使用入口網站新增及管理裝置標記</span><span class="sxs-lookup"><span data-stu-id="3d2b2-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="3d2b2-120">選取您要管理標記的裝置。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="3d2b2-121">您可以從下列任何一種視圖中，選取或搜尋裝置：</span><span class="sxs-lookup"><span data-stu-id="3d2b2-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="3d2b2-122">**安全性作業儀表板** -從 [最上層裝置與使用中警示] 區段選取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="3d2b2-123">**警示佇列** -從警示佇列中，選取裝置圖示旁邊的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="3d2b2-124">**裝置清單** -從裝置清單中選取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="3d2b2-125">**搜尋框** -從下拉式功能表中選取 [裝置]，然後輸入裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="3d2b2-126">您也可以透過 [檔案] 和 [IP 視圖] 進入警示頁面。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="3d2b2-127">從 [回應動作] 列中，選取 [ **管理標記** ]。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![管理標記的影像按鈕](images/manage-tags.png)

3. <span data-ttu-id="3d2b2-129">輸入以尋找或建立標記</span><span class="sxs-lookup"><span data-stu-id="3d2b2-129">Type to find or create tags</span></span>

    ![在 device1 上新增標記的影像](images/new-tags.png)

<span data-ttu-id="3d2b2-131">標記會新增至裝置視圖，也會反映在 [裝置] **清單** 視圖上。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="3d2b2-132">您可以使用 [ **標記** ] 篩選來查看相關的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="3d2b2-133">篩選可能無法處理包含括弧的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="3d2b2-134">當您建立新的標籤時，會顯示一份現有的標記清單。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="3d2b2-135">清單只會顯示透過入口網站建立的標籤。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="3d2b2-136">將不會顯示從用戶端裝置建立的現有標記。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="3d2b2-137">您也可以從此視圖中刪除標記。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-137">You can also delete tags from this view.</span></span>

![在 device2 上新增標記的影像](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="3d2b2-139">設定登錄機碼值以新增裝置標記</span><span class="sxs-lookup"><span data-stu-id="3d2b2-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="3d2b2-140">僅適用于下列裝置：</span><span class="sxs-lookup"><span data-stu-id="3d2b2-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="3d2b2-141">Windows 10，版本1709或更新版本</span><span class="sxs-lookup"><span data-stu-id="3d2b2-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="3d2b2-142">Windows Server，版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="3d2b2-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="3d2b2-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3d2b2-143">Windows Server 2016</span></span>
>- <span data-ttu-id="3d2b2-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3d2b2-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="3d2b2-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="3d2b2-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="3d2b2-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3d2b2-146">Windows 8.1</span></span>
>- <span data-ttu-id="3d2b2-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="3d2b2-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="3d2b2-148">標記中可以設定的最大字元數為200。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="3d2b2-149">當您需要在特定裝置清單上套用內容性動作時，具有類似標記的裝置可能十分方便。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="3d2b2-150">使用下列登錄機碼專案在裝置上新增標籤：</span><span class="sxs-lookup"><span data-stu-id="3d2b2-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="3d2b2-151">登錄機碼： `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="3d2b2-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="3d2b2-152">登錄機碼值 (REG_SZ) ： `Group`</span><span class="sxs-lookup"><span data-stu-id="3d2b2-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="3d2b2-153">登錄機碼資料： `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="3d2b2-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="3d2b2-154">裝置標記是一天產生一次的裝置資訊報告的一部分。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="3d2b2-155">或者，您也可以選擇重新開機會傳輸新裝置資訊報告的端點。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="3d2b2-156">如果您需要移除以上述登錄機碼所新增的標籤，請清除登錄機碼資料的內容，而不是移除 ' 群組」機碼。</span><span class="sxs-lookup"><span data-stu-id="3d2b2-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
