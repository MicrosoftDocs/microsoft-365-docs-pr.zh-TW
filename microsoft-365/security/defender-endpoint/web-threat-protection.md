---
title: 保護您的組織免受網頁威脅
description: 深入瞭解 Microsoft Defender ATP 中的 web 保護，以及它如何保護您的組織。
keywords: 網頁防護，網頁威脅防護，網頁流覽，安全性，網路釣魚，惡意程式碼，exploit，網站，網路保護，Edge，Internet Explorer，Chrome，Firefox，網頁瀏覽器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: aeeea02ca1ef2d37623e9ab434b162237c2f4946
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499902"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="b53f8-104">保護您的組織免受網頁威脅</span><span class="sxs-lookup"><span data-stu-id="b53f8-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b53f8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b53f8-105">**Applies to:**</span></span>
- [<span data-ttu-id="b53f8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b53f8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b53f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b53f8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b53f8-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b53f8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b53f8-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b53f8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="b53f8-110">Web 威脅防護是用於端點之 [web 保護](web-protection-overview.md) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b53f8-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="b53f8-111">它會使用 [網路保護](network-protection.md) 來保護您的裝置免受網頁威脅。</span><span class="sxs-lookup"><span data-stu-id="b53f8-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="b53f8-112">透過與 Microsoft Edge 和流行的協力廠商瀏覽器（如 Chrome 和 Firefox）整合，網頁威脅防護會停止網頁 proxy 以外的網頁威脅，並在離開或內部部署時保護裝置。</span><span class="sxs-lookup"><span data-stu-id="b53f8-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="b53f8-113">Web 威脅防護會停止存取網路釣魚網站、惡意程式碼向量、exploit 網站、不信任或低信譽網站，以及您在 [自訂指示器清單](manage-indicators.md)中封鎖的網站。</span><span class="sxs-lookup"><span data-stu-id="b53f8-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="b53f8-114">裝置接收新的自訂指示器時，最多可能需要一小時。</span><span class="sxs-lookup"><span data-stu-id="b53f8-114">It can take up to an hour for devices to receive new custom indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b53f8-115">先決條件</span><span class="sxs-lookup"><span data-stu-id="b53f8-115">Prerequisites</span></span>
<span data-ttu-id="b53f8-116">Web 保護使用網路保護，在 Microsoft Edge 和協力廠商網頁瀏覽器上提供 web 流覽安全性。</span><span class="sxs-lookup"><span data-stu-id="b53f8-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="b53f8-117">開啟裝置上的網路保護：</span><span class="sxs-lookup"><span data-stu-id="b53f8-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="b53f8-118">在 [ **Web & 網路保護** ] 底下編輯端點的「安全性基準」，以在部署或重新部署之前啟用網路保護。</span><span class="sxs-lookup"><span data-stu-id="b53f8-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="b53f8-119">瞭解如何檢查和指派用於端點安全性基準的 Defender</span><span class="sxs-lookup"><span data-stu-id="b53f8-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="b53f8-120">使用 Intune 裝置設定、SCCM、群組原則或 MDM 解決方案開啟網路保護。</span><span class="sxs-lookup"><span data-stu-id="b53f8-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="b53f8-121">進一步閱讀啟用網路保護的資訊</span><span class="sxs-lookup"><span data-stu-id="b53f8-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="b53f8-122">若您將網路保護設定為 **僅供審核**，封鎖將無法使用。</span><span class="sxs-lookup"><span data-stu-id="b53f8-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="b53f8-123">此外，您也可以偵測和記錄嘗試只在 Microsoft Edge 上存取惡意和有害網站的嘗試。</span><span class="sxs-lookup"><span data-stu-id="b53f8-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b53f8-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="b53f8-124">Related topics</span></span>

- [<span data-ttu-id="b53f8-125">Web 保護概觀</span><span class="sxs-lookup"><span data-stu-id="b53f8-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="b53f8-126">網頁威脅防護</span><span class="sxs-lookup"><span data-stu-id="b53f8-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="b53f8-127">監視 Web 安全性</span><span class="sxs-lookup"><span data-stu-id="b53f8-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="b53f8-128">回應 Web 威脅</span><span class="sxs-lookup"><span data-stu-id="b53f8-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="b53f8-129">網路保護</span><span class="sxs-lookup"><span data-stu-id="b53f8-129">Network protection</span></span>](network-protection.md)
