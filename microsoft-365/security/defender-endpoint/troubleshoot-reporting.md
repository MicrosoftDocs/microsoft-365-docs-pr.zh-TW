---
title: 疑難排解 Microsoft Defender AV 報告工具的問題
description: 在更新規範中嘗試以 Microsoft Defender AV 保護狀態報表時，識別並解決常見問題
keywords: 疑難排解，錯誤，修正，更新規範，oms，監視器，報表，Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ca62db922a13ab2cb3226eaf0efb92bfaf8c572b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274889"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="fcc8f-104">疑難排解更新合規性中的 Microsoft Defender 防毒軟體報告</span><span class="sxs-lookup"><span data-stu-id="fcc8f-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fcc8f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="fcc8f-105">**Applies to:**</span></span>

- [<span data-ttu-id="fcc8f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fcc8f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="fcc8f-107">2020年3月31日，將會移除更新規範的 Microsoft Defender 防毒軟體報告功能。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="fcc8f-108">您可以繼續使用[Microsoft 端點管理員](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)來定義及檢查安全性符合性原則，這可讓您更精細地控制安全性功能和更新。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="fcc8f-109">您可以使用具有更新規範的 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="fcc8f-110">您將會看到 E3、B、F1、VL 和 Pro 授權的狀態。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="fcc8f-111">不過，對於 E5 授權，您必須使用 [Microsoft Defender For Endpoint 入口網站](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="fcc8f-112">若要深入瞭解授權選項，請參閱[Windows 10 產品授權選項](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="fcc8f-113">當您使用 Windows Analytics 更新合規性，以在您的網路中使用 Microsoft Defender 防毒軟體[來取得裝置或端點的保護狀態](/windows/deployment/update/update-compliance-using#wdav-assessment)時，可能會發生問題或問題。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="fcc8f-114">一般來說，問題最常見的指示器如下：</span><span class="sxs-lookup"><span data-stu-id="fcc8f-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="fcc8f-115">您只會看到您期望看到之所有裝置的小數位或子集</span><span class="sxs-lookup"><span data-stu-id="fcc8f-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="fcc8f-116">您沒有看到任何裝置</span><span class="sxs-lookup"><span data-stu-id="fcc8f-116">You do not see any devices at all</span></span>
- <span data-ttu-id="fcc8f-117">您所看到的報告和資訊已過時 (數天內) </span><span class="sxs-lookup"><span data-stu-id="fcc8f-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="fcc8f-118">如需與更新規範不相關之 Microsoft Defender 防毒軟體服務相關的常見錯誤代碼和事件 IDs，請參閱[Microsoft Defender 防毒軟體事件](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="fcc8f-119">針對這些問題進行疑難排解有三個步驟：</span><span class="sxs-lookup"><span data-stu-id="fcc8f-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="fcc8f-120">確認您已符合所有必要條件</span><span class="sxs-lookup"><span data-stu-id="fcc8f-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="fcc8f-121">檢查您與 Windows Defender 雲端架構服務的連線能力</span><span class="sxs-lookup"><span data-stu-id="fcc8f-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="fcc8f-122">提交支援記錄檔</span><span class="sxs-lookup"><span data-stu-id="fcc8f-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="fcc8f-123">裝置開始出現的3天內，會出現更新規範。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="fcc8f-124">確認必要條件</span><span class="sxs-lookup"><span data-stu-id="fcc8f-124">Confirm prerequisites</span></span>

<span data-ttu-id="fcc8f-125">為了讓裝置能夠正確顯示更新規範，您必須符合更新規範服務和 Microsoft Defender 防毒軟體的特定必要條件：</span><span class="sxs-lookup"><span data-stu-id="fcc8f-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="fcc8f-126">端點使用 Microsoft Defender 防毒軟體作為獨立的防防毒保護應用程式。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="fcc8f-127">[使用任何其他防病毒應用程式會使 Microsoft DEFENDER AV 自行停用](microsoft-defender-antivirus-compatibility.md) ，而且不會在更新規範中報告端點。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="fcc8f-128">[已啟用雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)功能。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="fcc8f-129">端點可以 [連接至 Microsoft DEFENDER AV 雲端](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="fcc8f-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="fcc8f-130">如果端點執行 Windows 10 版本1607或更舊版本，則[必須將 Windows 10 診斷資料設定為增強的層級](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="fcc8f-131">由於已符合所有需求，因此已完成3天</span><span class="sxs-lookup"><span data-stu-id="fcc8f-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="fcc8f-132">「您可以搭配更新規範使用 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="fcc8f-133">您將會看到 E3、B、F1、VL 和 Pro 授權的狀態。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="fcc8f-134">不過，對於 E5 授權，您必須使用 Microsoft Defender for Endpoint 入口網站 (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) 。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="fcc8f-135">若要深入瞭解授權選項，請參閱 Windows 10 產品授權選項 "。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="fcc8f-136">若上述必要條件皆已符合，您可能需要繼續進行下一個步驟，以收集診斷資訊並傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fcc8f-137">收集診斷資料以進行更新規範疑難排解</span><span class="sxs-lookup"><span data-stu-id="fcc8f-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="fcc8f-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="fcc8f-138">Related topics</span></span>

- [<span data-ttu-id="fcc8f-139">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="fcc8f-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="fcc8f-140">部署 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="fcc8f-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)