---
title: 調查與警示相關聯的 IP 位址
description: 使用調查選項檢查裝置與外部 IP 位址之間可能的通訊。
keywords: 調查、調查、IP 位址、警示、microsoft defender atp、外部 IP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 003abd854e34bb5a9a05f675313ba6c4f6ce1d71
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186038"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="6b1e2-104">調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6b1e2-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6b1e2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6b1e2-105">**Applies to:**</span></span>
- [<span data-ttu-id="6b1e2-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6b1e2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6b1e2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b1e2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="6b1e2-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6b1e2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6b1e2-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6b1e2-110">檢查裝置與外部網際網路通訊協定之間可能的通訊 (IP) 位址。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="6b1e2-111">識別組織中與可疑或已知惡意的 IP 位址（例如 Command 和 Control (C2) 伺服器）通訊的所有裝置，協助判斷遭到破壞的潛在範圍、關聯的檔案和受感染的裝置。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="6b1e2-112">您可以從 [IP 位址] 視圖中的下列區段找到資訊：</span><span class="sxs-lookup"><span data-stu-id="6b1e2-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="6b1e2-113">全球 IP</span><span class="sxs-lookup"><span data-stu-id="6b1e2-113">IP worldwide</span></span>
- <span data-ttu-id="6b1e2-114">反向 DNS 名稱</span><span class="sxs-lookup"><span data-stu-id="6b1e2-114">Reverse DNS names</span></span>
- <span data-ttu-id="6b1e2-115">與此 IP 相關的警示</span><span class="sxs-lookup"><span data-stu-id="6b1e2-115">Alerts related to this IP</span></span>
- <span data-ttu-id="6b1e2-116">組織中的 IP</span><span class="sxs-lookup"><span data-stu-id="6b1e2-116">IP in organization</span></span>
- <span data-ttu-id="6b1e2-117">流行</span><span class="sxs-lookup"><span data-stu-id="6b1e2-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="6b1e2-118">IP 全球和反向 DNS 名稱</span><span class="sxs-lookup"><span data-stu-id="6b1e2-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="6b1e2-119">「IP 位址詳細資料」區段會顯示 IP 位址（如其 ASN 和其反向 DNS 名稱）的屬性。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="6b1e2-120">與此 IP 相關的警示</span><span class="sxs-lookup"><span data-stu-id="6b1e2-120">Alerts related to this IP</span></span>

<span data-ttu-id="6b1e2-121">與 **此 ip 區段相關的警示** ，提供與 ip 相關聯的警示清單。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="6b1e2-122">組織中的 IP</span><span class="sxs-lookup"><span data-stu-id="6b1e2-122">IP in organization</span></span>

<span data-ttu-id="6b1e2-123">[ **組織中的 ip** ] 區段提供組織中 ip 位址的流行詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="6b1e2-124">流行</span><span class="sxs-lookup"><span data-stu-id="6b1e2-124">Prevalence</span></span>

<span data-ttu-id="6b1e2-125">「 **傳播** 」區段會顯示已連接至此 ip 位址的裝置數量，以及第一次及最後一次看到此 ip 位址的時間。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="6b1e2-126">您可以依時段篩選此區段的結果;預設週期為30天。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="6b1e2-127">最近觀測的裝置（含 IP）</span><span class="sxs-lookup"><span data-stu-id="6b1e2-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="6b1e2-128">[使用 IP 的 **最近觀測的裝置** ] 區段提供按時間排序的事件，以及在 IP 位址上觀測到的相關警示。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="6b1e2-129">**調查外部 IP：**</span><span class="sxs-lookup"><span data-stu-id="6b1e2-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="6b1e2-130">從 **搜尋** 列下拉式功能表中選取 [ **IP** ]。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="6b1e2-131">在 [ **搜尋** ] 欄位中輸入 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="6b1e2-132">按一下搜尋圖示或按 **enter** 鍵。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="6b1e2-133">會顯示 IP 位址的詳細資訊，包括：註冊詳細資料 (如果可用) 、反向 IPs (例如，組織中的網域) 、與此 IP 位址通訊的組織內的設備 (，以及組織中透過此 IP 位址進行通訊所觀察到的裝置。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="6b1e2-134">只會傳回與組織中裝置通訊所看到之 IP 位址的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="6b1e2-135">使用搜尋篩選以定義搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="6b1e2-136">您也可以使用 [時程表] 搜尋方塊，篩選組織中所看到之所有裝置的顯示結果，這些裝置會透過 IP 位址、與通訊相關聯的檔案及最後一個日期所看到的方式進行通訊。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="6b1e2-137">按一下任一裝置名稱將會帶您前往該裝置的視圖，您可以在其中繼續調查報告的警示、行為和事件。</span><span class="sxs-lookup"><span data-stu-id="6b1e2-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b1e2-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="6b1e2-138">Related topics</span></span>

- [<span data-ttu-id="6b1e2-139">查看和組織 Microsoft Defender for Endpoint 警示佇列</span><span class="sxs-lookup"><span data-stu-id="6b1e2-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="6b1e2-140">管理 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="6b1e2-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="6b1e2-141">調查 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="6b1e2-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="6b1e2-142">調查與 Microsoft Defender for Endpoint alert 相關聯的檔案</span><span class="sxs-lookup"><span data-stu-id="6b1e2-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="6b1e2-143">調查 Microsoft Defender for Endpoint Devices 清單中的裝置</span><span class="sxs-lookup"><span data-stu-id="6b1e2-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="6b1e2-144">調查與 Microsoft Defender for Endpoint alert 相關聯的網域</span><span class="sxs-lookup"><span data-stu-id="6b1e2-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="6b1e2-145">調查 Microsoft Defender for Endpoint 中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="6b1e2-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
