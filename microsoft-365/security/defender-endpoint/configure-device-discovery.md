---
title: 設定裝置探索
description: 瞭解如何使用基本或標準探索在 Microsoft 365 Defender 中設定裝置探索
keywords: basic，standard，configure endpoint discovery，裝置探索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 711a3188c49269b2ecedf0cccb6b27986742b048
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698424"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="2f15c-104">設定裝置探索</span><span class="sxs-lookup"><span data-stu-id="2f15c-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f15c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2f15c-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f15c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f15c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2f15c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f15c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2f15c-108">探索可以設定為 on standard 或 basic 模式。</span><span class="sxs-lookup"><span data-stu-id="2f15c-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="2f15c-109">使用標準選項可在您的網路中主動尋找裝置，這樣就能更好地保證端點的探索，並提供更豐富的裝置分類。</span><span class="sxs-lookup"><span data-stu-id="2f15c-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="2f15c-110">您可以自訂用來執行標準探索的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="2f15c-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="2f15c-111">您可以在目前只支援此功能的所有架裝置上啟用標準探索 (目前只有 Windows 10 裝置) 或透過指定裝置的裝置標記來選取一部分裝置或子集。</span><span class="sxs-lookup"><span data-stu-id="2f15c-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="2f15c-112">預覽時，您必須先在 Microsoft Defender 安全中心開啟預覽功能。</span><span class="sxs-lookup"><span data-stu-id="2f15c-112">For preview, you'll first need to turn on the Preview features in Microsoft Defender Security Center.</span></span>
> <span data-ttu-id="2f15c-113">然後，您可以在 Microsoft 365 的安全性中心存取裝置探索設定。</span><span class="sxs-lookup"><span data-stu-id="2f15c-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="2f15c-114">Microsoft Defender Security Center 和 Microsoft 365 security center 中皆提供非管理裝置及安全性建議的清單，而儀表板磚只會在 Microsoft 365 安全性中心提供。</span><span class="sxs-lookup"><span data-stu-id="2f15c-114">The list of unmanaged devices and security recommendations will be available in both Microsoft Defender Security Center and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>


<span data-ttu-id="2f15c-115">在 Microsoft 365 安全中心採取下列設定步驟：</span><span class="sxs-lookup"><span data-stu-id="2f15c-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1.  <span data-ttu-id="2f15c-116">流覽至 [ **設定] > 裝置探索**。</span><span class="sxs-lookup"><span data-stu-id="2f15c-116">Navigate to **Settings > Device discovery**.</span></span>
2.  <span data-ttu-id="2f15c-117">選取要用於架裝置的探索模式。</span><span class="sxs-lookup"><span data-stu-id="2f15c-117">Select the discovery mode to use on your onboarded devices.</span></span> 
3.  <span data-ttu-id="2f15c-118">如果您已選擇使用標準探索，請選取要用於作用中探測的裝置： [所有裝置] 或 [子集]，方法是指定其裝置標記。</span><span class="sxs-lookup"><span data-stu-id="2f15c-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="2f15c-119">按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="2f15c-119">Click **Save**.</span></span>


## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="2f15c-120">排除在標準探索中積極探測裝置</span><span class="sxs-lookup"><span data-stu-id="2f15c-120">Exclude devices from being actively probed in standard discovery</span></span>
<span data-ttu-id="2f15c-121">如果您的網路上有不應該主動掃描的裝置 (例如，使用另一種安全性工具的裝置做為 honeypots) 中，您也可以定義排除清單以避免掃描這些裝置。</span><span class="sxs-lookup"><span data-stu-id="2f15c-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="2f15c-122">請注意，使用基本探索模式仍可探索裝置。</span><span class="sxs-lookup"><span data-stu-id="2f15c-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="2f15c-123">將會被動探索這些裝置，但不會主動加以探測。</span><span class="sxs-lookup"><span data-stu-id="2f15c-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="2f15c-124">選取要監視的網路</span><span class="sxs-lookup"><span data-stu-id="2f15c-124">Select networks to monitor</span></span>
 <span data-ttu-id="2f15c-125">Microsoft Defender for Endpoint 會分析網路，並判斷其是否為需要監控的公司網路，或是可以忽略的非公司網路。</span><span class="sxs-lookup"><span data-stu-id="2f15c-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="2f15c-126">公司網路通常會選擇加以監視。</span><span class="sxs-lookup"><span data-stu-id="2f15c-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="2f15c-127">不過，您可以選擇監視未找到架裝置的非公司網路，以覆寫此決策。</span><span class="sxs-lookup"><span data-stu-id="2f15c-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="2f15c-128">您可以指定要監視的網路，以設定可執行裝置探索的位置。</span><span class="sxs-lookup"><span data-stu-id="2f15c-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="2f15c-129">監視網路時，可對其執行設備探索。</span><span class="sxs-lookup"><span data-stu-id="2f15c-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="2f15c-130">「 **受監視的網路** 」頁面中顯示可執行裝置探索的網路清單。</span><span class="sxs-lookup"><span data-stu-id="2f15c-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 


>[!NOTE]
> <span data-ttu-id="2f15c-131">根據 [網路] 清單中提供的相關裝置的數目) ，只會 (前50網路。</span><span class="sxs-lookup"><span data-stu-id="2f15c-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 


<span data-ttu-id="2f15c-132">受監視網路的清單是根據在過去7天內網路上看到之裝置的總數排序。</span><span class="sxs-lookup"><span data-stu-id="2f15c-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>


<span data-ttu-id="2f15c-133">您可以套用篩選器以查看下列任何網路探索狀態：</span><span class="sxs-lookup"><span data-stu-id="2f15c-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="2f15c-134">**受監視的網路** -執行設備探索的網路。</span><span class="sxs-lookup"><span data-stu-id="2f15c-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="2f15c-135">已 **忽略的網路**-將會忽略此網路，而且不會在其上執行設備探索。</span><span class="sxs-lookup"><span data-stu-id="2f15c-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="2f15c-136">隨即會顯示 **所有** 受監視和忽略的網路。</span><span class="sxs-lookup"><span data-stu-id="2f15c-136">**All** - Both monitored and ignored networks will be displayed.</span></span> 


### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="2f15c-137">設定網路監視器狀態</span><span class="sxs-lookup"><span data-stu-id="2f15c-137">Configure the network monitor state</span></span>
<span data-ttu-id="2f15c-138">您可以控制裝置探索發生的位置。</span><span class="sxs-lookup"><span data-stu-id="2f15c-138">You control where device discovery takes place.</span></span> <span data-ttu-id="2f15c-139">受監視的網路是指執行設備探索的地方，通常是公司網路。</span><span class="sxs-lookup"><span data-stu-id="2f15c-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="2f15c-140">您也可以選擇略過網路或在修改狀態後選取初始探索分類。</span><span class="sxs-lookup"><span data-stu-id="2f15c-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span> 

<span data-ttu-id="2f15c-141">選擇初始探索分類意味著套用預設的系統建立網路監視器狀態。</span><span class="sxs-lookup"><span data-stu-id="2f15c-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="2f15c-142">選取預設的系統網路監視器狀態，表示系統會自動忽略已識別成公司的網路，並將其識別為非公司的網路。</span><span class="sxs-lookup"><span data-stu-id="2f15c-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>
 
1. <span data-ttu-id="2f15c-143">選取 [ **設定] > 裝置探索**。</span><span class="sxs-lookup"><span data-stu-id="2f15c-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="2f15c-144">選取 [ **受監視的網路**]。</span><span class="sxs-lookup"><span data-stu-id="2f15c-144">Select **Monitored networks**.</span></span> 
3. <span data-ttu-id="2f15c-145">查看網路清單。</span><span class="sxs-lookup"><span data-stu-id="2f15c-145">View the list of networks.</span></span> 
4. <span data-ttu-id="2f15c-146">選取網路名稱旁邊的三個點。</span><span class="sxs-lookup"><span data-stu-id="2f15c-146">Select the three dots next to the network name.</span></span> 
5. <span data-ttu-id="2f15c-147">選擇您是否要監視、忽略或使用初始探索分類。</span><span class="sxs-lookup"><span data-stu-id="2f15c-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span> 
    
    > [!WARNING]
    >- <span data-ttu-id="2f15c-148">選擇監視未由 Microsoft Defender for Endpoint 做為公司網路的網路，可導致公司網路以外的設備探索，因此可能會偵測到家用或其他非公司的裝置。</span><span class="sxs-lookup"><span data-stu-id="2f15c-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span> 
    > - <span data-ttu-id="2f15c-149">選擇 [略過網路] 會停止監控和搜尋該網路中的裝置。</span><span class="sxs-lookup"><span data-stu-id="2f15c-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="2f15c-150">已探索的裝置將不會從清查中移除，但將不再更新，而且將會保留詳細資料，直到 Endpoint for Endpoint 的資料保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="2f15c-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="2f15c-151">在選擇監視非公司網路之前，您必須確定您有許可權執行該動作。</span><span class="sxs-lookup"><span data-stu-id="2f15c-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span> <br>


6. <span data-ttu-id="2f15c-152">確認您要進行變更。</span><span class="sxs-lookup"><span data-stu-id="2f15c-152">Confirm that you want to make the change.</span></span> 




## <a name="see-also"></a><span data-ttu-id="2f15c-153">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2f15c-153">See also</span></span>
- [<span data-ttu-id="2f15c-154">裝置探索概述</span><span class="sxs-lookup"><span data-stu-id="2f15c-154">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="2f15c-155">裝置探索 FAQs</span><span class="sxs-lookup"><span data-stu-id="2f15c-155">Device discovery FAQs</span></span>](device-discovery-faq.md)