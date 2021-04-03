---
title: 可下載的整備評估檢查程式
description: 檢查裝置和網路設定（包括必要的端點）
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581031"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="2f3cd-104">可下載的整備評估檢查程式</span><span class="sxs-lookup"><span data-stu-id="2f3cd-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="2f3cd-105">若要搭配 Microsoft 受管理的桌上型電腦運作，裝置必須符合硬體和設定的特定需求。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="2f3cd-106">此外，每個裝置都必須能夠到達機碼端點。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="2f3cd-107">下載並執行此工具以取得 HTML 報告、查看結果，然後採取動作。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="2f3cd-108">您必須下載工具和支援檔案，然後在您要在 Microsoft 受管理的電腦上登錄的每一個裝置上手動執行。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="2f3cd-109">針對每個檢查，該工具會報告三個可能結果中的其中一項：</span><span class="sxs-lookup"><span data-stu-id="2f3cd-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="2f3cd-110">結果</span><span class="sxs-lookup"><span data-stu-id="2f3cd-110">Result</span></span>  |<span data-ttu-id="2f3cd-111">意義</span><span class="sxs-lookup"><span data-stu-id="2f3cd-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="2f3cd-112">就緒</span><span class="sxs-lookup"><span data-stu-id="2f3cd-112">Ready</span></span>     | <span data-ttu-id="2f3cd-113">完成註冊之前，不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="2f3cd-114">公告</span><span class="sxs-lookup"><span data-stu-id="2f3cd-114">Advisory</span></span>    | <span data-ttu-id="2f3cd-115">請遵循工具中的步驟，以取得註冊和使用者的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="2f3cd-116">您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="2f3cd-117">未就緒</span><span class="sxs-lookup"><span data-stu-id="2f3cd-117">Not ready</span></span> | <span data-ttu-id="2f3cd-118">如果您未修正這些問題，*註冊將會失敗*。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="2f3cd-119">請遵循工具中的步驟加以解決。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="2f3cd-120">取得檢查</span><span class="sxs-lookup"><span data-stu-id="2f3cd-120">Obtain the checker</span></span>

<span data-ttu-id="2f3cd-121">從下載 .zip 檔案 https://aka.ms/mmddratoolv0 。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="2f3cd-122">執行工具的使用者必須具有其所執行之裝置上的本機系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="2f3cd-123">請遵循下列步驟來執行工具：</span><span class="sxs-lookup"><span data-stu-id="2f3cd-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="2f3cd-124">將下載的 .zip 檔案複製到您想要檢查的每一個裝置。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="2f3cd-125">解壓縮壓縮下載中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="2f3cd-126">執行 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="2f3cd-127">顯示使用者存取控制提示時，請選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="2f3cd-128">工具會在您的預設瀏覽器中執行並開啟報表。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="2f3cd-129">您也可以下載並解壓縮 .zip 封存至共用位置，從每個裝置存取 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** ，然後在本機執行。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="2f3cd-130">檢查</span><span class="sxs-lookup"><span data-stu-id="2f3cd-130">Checks</span></span>

<span data-ttu-id="2f3cd-131">可下載的工具會檢查這些裝置和網路相關專案：</span><span class="sxs-lookup"><span data-stu-id="2f3cd-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="2f3cd-132">硬體</span><span class="sxs-lookup"><span data-stu-id="2f3cd-132">Hardware</span></span>

<span data-ttu-id="2f3cd-133">裝置必須符合特定硬體需求，才能與 Microsoft 受管理的電腦搭配使用。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="2f3cd-134">目前，只允許特定 [已核准的裝置](../service-description/device-list.md) 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="2f3cd-135">如果您的裝置失敗任何檢查，它就不會與 Microsoft 受管理的桌上型電腦相容。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="2f3cd-136">網路端點</span><span class="sxs-lookup"><span data-stu-id="2f3cd-136">Network endpoints</span></span>

<span data-ttu-id="2f3cd-137">裝置很大可以到達數個 [金鑰端點](network.md) ，以與 Microsoft Managed Desktop 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="2f3cd-138">若工具報告 **未就緒** 的結果，請參閱詳細報告以找出無法到達的端點。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="2f3cd-139">然後調整您的防火牆或其他網路設定，以確保可以到達這些端點。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="2f3cd-140">其他設定</span><span class="sxs-lookup"><span data-stu-id="2f3cd-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="2f3cd-141">企業 wi-fi 設定檔</span><span class="sxs-lookup"><span data-stu-id="2f3cd-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="2f3cd-142">**建議** 結果表示您使用的某些 wi-fi 設定檔需要憑證和設定檔才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="2f3cd-143">如需詳細資訊，請參閱 [部署憑證和 Wi-Fi/VPN 設定檔](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="2f3cd-144">LAN 設定檔</span><span class="sxs-lookup"><span data-stu-id="2f3cd-144">LAN profiles</span></span>

<span data-ttu-id="2f3cd-145">**建議** 的結果表示您有需要憑證和設定檔才能正常運作的局域網。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="2f3cd-146">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="2f3cd-147">VPN 設定檔</span><span class="sxs-lookup"><span data-stu-id="2f3cd-147">VPN profiles</span></span>

<span data-ttu-id="2f3cd-148">**建議** 的結果表示您使用的是虛擬私人網路 (VPN) 。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="2f3cd-149">建立 VPN 設定檔，以部署與 Microsoft Intune 整合的憑證。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="2f3cd-150">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="2f3cd-151">對應磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="2f3cd-151">Mapped drives</span></span>

<span data-ttu-id="2f3cd-152">**建議** 結果表示您有一些對應的磁片磁碟機，不建議使用。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="2f3cd-153">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備對應的磁片磁碟機](mapped-drives.md)。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="2f3cd-154">列印佇列</span><span class="sxs-lookup"><span data-stu-id="2f3cd-154">Print queues</span></span>

<span data-ttu-id="2f3cd-155">**建議** 的結果表示您有一些尚未處理的列印佇列，不建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="2f3cd-156">一個解決方案是使用雲端列印。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="2f3cd-157">如需詳細資訊，請參閱 [準備列印 Microsoft Managed Desktop 的資源](printing.md)。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="2f3cd-158">代理</span><span class="sxs-lookup"><span data-stu-id="2f3cd-158">Proxies</span></span>

<span data-ttu-id="2f3cd-159">**建議** 的結果表示您有使用 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="2f3cd-160">如需詳細資訊，請參閱 [Microsoft Managed Desktop 的網路](network.md)設定。</span><span class="sxs-lookup"><span data-stu-id="2f3cd-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

