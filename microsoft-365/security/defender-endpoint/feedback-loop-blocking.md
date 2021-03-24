---
title: 意見反應-環路封鎖
description: 意見反應-環路封鎖（也稱為快速保護）是 Microsoft Defender for Endpoint 中行為封鎖和包容功能的一部分
keywords: 行為封鎖，快速保護，回應封鎖，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: b1ec879a2f05a0354b1a49cf94fccacb4a382193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060548"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="7c72b-104">意見反應-環路封鎖</span><span class="sxs-lookup"><span data-stu-id="7c72b-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7c72b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7c72b-105">**Applies to:**</span></span>
- [<span data-ttu-id="7c72b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7c72b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="7c72b-107">概觀</span><span class="sxs-lookup"><span data-stu-id="7c72b-107">Overview</span></span>

<span data-ttu-id="7c72b-108">意見反應-環路封鎖（也稱為快速保護）是[Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)中的[行為封鎖和包容功能](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)的元件。</span><span class="sxs-lookup"><span data-stu-id="7c72b-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/).</span></span> <span data-ttu-id="7c72b-109">透過反應反應封鎖，您組織中的裝置會更好地受到攻擊。</span><span class="sxs-lookup"><span data-stu-id="7c72b-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="7c72b-110">反應反應-環路封鎖的運作方式</span><span class="sxs-lookup"><span data-stu-id="7c72b-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="7c72b-111">偵測到可疑行為或檔案（例如 [Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)程式）時，就會將該專案的相關資訊傳送至多個分類程式。</span><span class="sxs-lookup"><span data-stu-id="7c72b-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="7c72b-112">「快速保護環路引擎」會檢查資訊，並將資訊與其他信號關聯，以判斷是否封鎖檔。</span><span class="sxs-lookup"><span data-stu-id="7c72b-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="7c72b-113">檢查和分類偽像會很快進行。</span><span class="sxs-lookup"><span data-stu-id="7c72b-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="7c72b-114">這會導致快速封鎖已確認的惡意程式碼，並推動整個生態系統的保護。</span><span class="sxs-lookup"><span data-stu-id="7c72b-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="7c72b-115">使用快速保護時，攻擊可以在裝置、組織中的其他裝置和其他組織中的裝置上停止，因為攻擊會嘗試拓寬其 foothold。</span><span class="sxs-lookup"><span data-stu-id="7c72b-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="7c72b-116">設定反應反應-環路封鎖</span><span class="sxs-lookup"><span data-stu-id="7c72b-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="7c72b-117">如果您的組織使用的是用於端點的 Defender，則預設會啟用反應反應封鎖。</span><span class="sxs-lookup"><span data-stu-id="7c72b-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="7c72b-118">不過，透過 Microsoft 安全服務的 Endpoint 功能、機器學習保護功能和信號共用的組合，便會進行快速保護。</span><span class="sxs-lookup"><span data-stu-id="7c72b-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="7c72b-119">請確定已啟用並設定 Defender for Endpoint 的下列功能和功能：</span><span class="sxs-lookup"><span data-stu-id="7c72b-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="7c72b-120">Microsoft Defender for Endpoint 基準</span><span class="sxs-lookup"><span data-stu-id="7c72b-120">Microsoft Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="7c72b-121">裝置架至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7c72b-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="7c72b-122">組塊模式中的 EDR</span><span class="sxs-lookup"><span data-stu-id="7c72b-122">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="7c72b-123">受攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="7c72b-123">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="7c72b-124">[下一代保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (防病毒) </span><span class="sxs-lookup"><span data-stu-id="7c72b-124">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="7c72b-125">相關文章</span><span class="sxs-lookup"><span data-stu-id="7c72b-125">Related articles</span></span>

- [<span data-ttu-id="7c72b-126">行為封鎖和包容</span><span class="sxs-lookup"><span data-stu-id="7c72b-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="7c72b-127"> (博客) 行為封鎖與包容：將光學器件轉換成保護</span><span class="sxs-lookup"><span data-stu-id="7c72b-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="7c72b-128">有用的 Microsoft Defender for Endpoint resources</span><span class="sxs-lookup"><span data-stu-id="7c72b-128">Helpful Microsoft Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
