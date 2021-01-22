---
title: 可下載的備應評定檢查程式
description: 檢查裝置和網路設定，包括所需的端點
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921939"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="ac3ad-104">可下載的備應評定檢查程式</span><span class="sxs-lookup"><span data-stu-id="ac3ad-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="ac3ad-105">若要順利使用 Microsoft 受管理的桌面，裝置必須符合硬體和設定的某些需求。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="ac3ad-106">此外，每個裝置必須能夠到達關鍵端點。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="ac3ad-107">下載並執行此工具以取得 HTML 報告、查看結果，然後採取行動。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="ac3ad-108">您必須下載工具和支援檔案，然後在您想要註冊 Microsoft 管理桌面的每個裝置上手動執行。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="ac3ad-109">工具會針對每項檢查報告三種可能的結果之一：</span><span class="sxs-lookup"><span data-stu-id="ac3ad-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="ac3ad-110">結果</span><span class="sxs-lookup"><span data-stu-id="ac3ad-110">Result</span></span>  |<span data-ttu-id="ac3ad-111">意義</span><span class="sxs-lookup"><span data-stu-id="ac3ad-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="ac3ad-112">就緒</span><span class="sxs-lookup"><span data-stu-id="ac3ad-112">Ready</span></span>     | <span data-ttu-id="ac3ad-113">完成註冊之前，無需執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="ac3ad-114">諮詢</span><span class="sxs-lookup"><span data-stu-id="ac3ad-114">Advisory</span></span>    | <span data-ttu-id="ac3ad-115">請遵循工具中的步驟，為註冊和使用者提供最佳使用體驗。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="ac3ad-116">您可以 *完成* 註冊，但必須在部署第一個裝置之前修正這些問題。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="ac3ad-117">未就緒</span><span class="sxs-lookup"><span data-stu-id="ac3ad-117">Not ready</span></span> | <span data-ttu-id="ac3ad-118">*如果您沒有修正這些問題* ，註冊將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="ac3ad-119">請遵循工具中的步驟來解決問題。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="ac3ad-120">取得檢查程式</span><span class="sxs-lookup"><span data-stu-id="ac3ad-120">Obtain the checker</span></span>

<span data-ttu-id="ac3ad-121">下載 .zip 檔案 https://aka.ms/mmddratoolv0 。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="ac3ad-122">執行工具的使用者必須在執行此工具的裝置上擁有當地系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="ac3ad-123">然後按照下列步驟執行工具：</span><span class="sxs-lookup"><span data-stu-id="ac3ad-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="ac3ad-124">將下載的 .zip 檔案複製到每個要檢查的裝置。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="ac3ad-125">解壓縮下載中所有的檔案。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="ac3ad-126">執行 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe。**</span><span class="sxs-lookup"><span data-stu-id="ac3ad-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="ac3ad-127">出現使用者存取控制提示時， **請選取是**。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="ac3ad-128">這項工具會隨即在預設瀏覽器中執行並開啟報表。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="ac3ad-129">您也可以將 .zip 存檔下載並解壓縮到共用位置，Microsoft.MMD.DeviceReadinessAssessmentTool.exe裝置存取檔案，然後在當地執行。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="ac3ad-130">檢查</span><span class="sxs-lookup"><span data-stu-id="ac3ad-130">Checks</span></span>

<span data-ttu-id="ac3ad-131">可下載的工具會檢查這些裝置和網路相關專案：</span><span class="sxs-lookup"><span data-stu-id="ac3ad-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="ac3ad-132">硬體</span><span class="sxs-lookup"><span data-stu-id="ac3ad-132">Hardware</span></span>

<span data-ttu-id="ac3ad-133">裝置必須符合特定硬體需求，以使用 Microsoft Managed Desktop。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="ac3ad-134">目前僅允許特定 [核准的](../service-description/device-list.md) 裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="ac3ad-135">如果您的裝置未通過任何檢查，就與 Microsoft Managed Desktop 不相容。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="ac3ad-136">網路端點</span><span class="sxs-lookup"><span data-stu-id="ac3ad-136">Network endpoints</span></span>

<span data-ttu-id="ac3ad-137">裝置能連接到數 [個金鑰](network.md) 端點，以使用 Microsoft Managed Desktop。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="ac3ad-138">如果工具報告尚未 **就緒** 的結果，請參閱詳細報告，瞭解哪些端點無法連接。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="ac3ad-139">然後調整防火牆或其他網路設定，以確保可以連接到這些端點。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="ac3ad-140">其他設定</span><span class="sxs-lookup"><span data-stu-id="ac3ad-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="ac3ad-141">企業 Wi-Fi 設定檔</span><span class="sxs-lookup"><span data-stu-id="ac3ad-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="ac3ad-142">建議 **結果** 表示您目前使用一些需要憑證及設定檔的 Wi-Fi 設定檔，以正常運作。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="ac3ad-143">有關詳細資訊，請參閱 [部署憑證和 Wi-Fi/VPN 設定檔](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="ac3ad-144">LAN 設定檔</span><span class="sxs-lookup"><span data-stu-id="ac3ad-144">LAN profiles</span></span>

<span data-ttu-id="ac3ad-145">建議 **結果** 表示您擁有需要憑證及設定檔的 LAN，以正常運作。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="ac3ad-146">有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="ac3ad-147">VPN 設定檔</span><span class="sxs-lookup"><span data-stu-id="ac3ad-147">VPN profiles</span></span>

<span data-ttu-id="ac3ad-148">建議 **結果** 表示您目前使用 VPN (私人網路) 。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="ac3ad-149">建立部署與 Microsoft Intune 整合之憑證的 VPN 設定檔。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="ac3ad-150">有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="ac3ad-151">對應磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="ac3ad-151">Mapped drives</span></span>

<span data-ttu-id="ac3ad-152">建議 **結果** 表示您擁有一些對應磁片磁碟機，這是不建議的。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="ac3ad-153">有關詳細資訊，請參閱 [準備適用于 Microsoft Managed Desktop 的對應磁片磁碟機](mapped-drives.md)。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="ac3ad-154">列印佇列</span><span class="sxs-lookup"><span data-stu-id="ac3ad-154">Print queues</span></span>

<span data-ttu-id="ac3ad-155">建議 **結果** 表示您有一些未付的列印佇列，這是不建議的。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="ac3ad-156">其中一個解決方案是使用雲端列印。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="ac3ad-157">有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的列印資源](printing.md)。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="ac3ad-158">代理</span><span class="sxs-lookup"><span data-stu-id="ac3ad-158">Proxies</span></span>

<span data-ttu-id="ac3ad-159">建議 **結果** 表示您擁有使用中的 Proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="ac3ad-160">詳細資訊請參閱 Microsoft [Managed Desktop 的網路組配置](network.md)。</span><span class="sxs-lookup"><span data-stu-id="ac3ad-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

