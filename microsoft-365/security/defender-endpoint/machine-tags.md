---
title: 建立及管理裝置標籤
description: 使用裝置標籤將裝置分組以擷取内容，並將動態清單建立作為事件的一部分啟用
keywords: 標籤、裝置標籤、裝置群組、群組、補救、層級、規則、新增群組、角色、指派、順位
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
ms.openlocfilehash: 83dd2483b93b2f4fe520973ce05346f59baf2f28
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453555"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="d7f5e-104">建立及管理裝置標籤</span><span class="sxs-lookup"><span data-stu-id="d7f5e-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d7f5e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d7f5e-105">**Applies to:**</span></span>
- [<span data-ttu-id="d7f5e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d7f5e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d7f5e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7f5e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d7f5e-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d7f5e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d7f5e-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d7f5e-110">在裝置上新增標籤以建立邏輯群組關係。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="d7f5e-111">裝置標籤支援網路的正確對應，使您能够附加不同的標籤以擷取内容，並作為事件的一部分啟用動態清單建立。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="d7f5e-112">標籤可以用作 **裝置清單** 檢視中的篩檢，也可以用於對裝置進行分組。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="d7f5e-113">有關裝置分組的詳細資訊，請參閱[建立和管理裝置群組](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="d7f5e-114">可以使用以下方法在裝置上新增標籤：</span><span class="sxs-lookup"><span data-stu-id="d7f5e-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="d7f5e-115">使用入口網站</span><span class="sxs-lookup"><span data-stu-id="d7f5e-115">Using the portal</span></span>
- <span data-ttu-id="d7f5e-116">設定登錄機碼值</span><span class="sxs-lookup"><span data-stu-id="d7f5e-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="d7f5e-117">從將標籤新增到裝置的時間，到其在裝置清單和裝置頁中的顯示可用的時間，可能會有一些延遲。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="d7f5e-118">要使用 API 新增裝置標籤，請參閲[新增或移除裝置標籤 API](add-or-remove-machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="d7f5e-119">使用入口網站新增和管理裝置標籤</span><span class="sxs-lookup"><span data-stu-id="d7f5e-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="d7f5e-120">選取要在其上管理標籤的裝置。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="d7f5e-121">您可以從以下任何檢視中選取或搜尋裝置：</span><span class="sxs-lookup"><span data-stu-id="d7f5e-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="d7f5e-122">**安全性操作儀表板** - 從具有作用中警示的頂端裝置區段中選取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="d7f5e-123">**警示佇列** - 從警示佇列中選取裝置圖示旁邊的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="d7f5e-124">**裝置清單** - 從裝置清單中選取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="d7f5e-125">**搜尋方塊** - 從下拉式功能表中選取裝置並輸入裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="d7f5e-126">您還可以透過檔案和 IP 檢視存取警示頁。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="d7f5e-127">從回應動作列中選取 **管理標籤**。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-127">Select **Manage Tags** from the row of Response actions.</span></span>

    :::image type="content" alt-text="[管理標記] 按鈕的圖像。" source="images/manage-tags-option.png":::

3. <span data-ttu-id="d7f5e-129">輸入以尋找或建立標籤</span><span class="sxs-lookup"><span data-stu-id="d7f5e-129">Type to find or create tags</span></span>

    :::image type="content" alt-text="在 device1 上新增標記的影像。" source="images/create-new-tag.png":::

<span data-ttu-id="d7f5e-131">標籤被新增至裝置檢視中，也會反映在 **裝置清單** 檢視中。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="d7f5e-132">然後可以使用 **標籤** 篩選查看相關的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="d7f5e-133">篩選對包含括弧的標籤名稱可能無效。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="d7f5e-134">建立新標籤時，將顯示現有標籤的清單。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="d7f5e-135">該清單僅顯示透過入口網站建立的標籤。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="d7f5e-136">將不顯示從用戶端裝置建立的現有標籤。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="d7f5e-137">您也可以從此檢視中删除標籤。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-137">You can also delete tags from this view.</span></span>

:::image type="content" alt-text="在 device2 上新增標記的影像。" source="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="d7f5e-139">透過設定登錄機碼值新增裝置標籤</span><span class="sxs-lookup"><span data-stu-id="d7f5e-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="d7f5e-140">僅適用於以下裝置：</span><span class="sxs-lookup"><span data-stu-id="d7f5e-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="d7f5e-141">Windows 10 版本 1709 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="d7f5e-142">Windows Server 版本 1803 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d7f5e-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="d7f5e-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d7f5e-143">Windows Server 2016</span></span>
>- <span data-ttu-id="d7f5e-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d7f5e-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="d7f5e-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="d7f5e-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="d7f5e-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d7f5e-146">Windows 8.1</span></span>
>- <span data-ttu-id="d7f5e-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="d7f5e-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="d7f5e-148">標籤中最多可以設定 200 個字元。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="d7f5e-149">當您需要對特定裝置清單套用關聯式動作時，具有類似標籤的裝置會很便利。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="d7f5e-150">使用以下登錄機碼項目在裝置上新增標籤：</span><span class="sxs-lookup"><span data-stu-id="d7f5e-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="d7f5e-151">登錄機碼: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="d7f5e-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="d7f5e-152">登錄機碼值 (REG_SZ)：`Group`</span><span class="sxs-lookup"><span data-stu-id="d7f5e-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="d7f5e-153">登錄機碼資料：`Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="d7f5e-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="d7f5e-154">裝置標籤是每天產生一次的裝置資訊報告的一部分。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="d7f5e-155">或者，您可以選擇將傳輸新裝置資訊報告的端點重新啟動。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="d7f5e-156">如果需要移除使用上述登錄機碼新增的標籤，請清除登錄機碼資料的內容，而不是移除「Group」機碼。</span><span class="sxs-lookup"><span data-stu-id="d7f5e-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
