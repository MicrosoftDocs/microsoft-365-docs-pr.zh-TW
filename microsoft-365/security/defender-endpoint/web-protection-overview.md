---
title: Web 保護
description: 深入瞭解 Microsoft Defender for Endpoint 中的 web 保護，以及它如何保護您的組織
keywords: web 保護、網頁威脅防護、網頁流覽、安全性、網路釣魚、惡意程式碼、利用方式、網站、網路保護、Edge、Internet Explorer、Chrome、Firefox、網頁瀏覽器、惡意網站
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
ms.openlocfilehash: a985719663ec23d41ce4da57aea9aa5e0cf7674c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688966"
---
# <a name="web-protection"></a><span data-ttu-id="12abf-104">Web 保護</span><span class="sxs-lookup"><span data-stu-id="12abf-104">Web protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12abf-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="12abf-105">**Applies to:**</span></span>
- [<span data-ttu-id="12abf-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="12abf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="12abf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12abf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="12abf-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="12abf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="12abf-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="12abf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="12abf-110">Microsoft Defender for Endpoint 中的 Web 保護是由 [web 威脅防護](web-threat-protection.md) 和 [web 內容篩選](web-content-filtering.md)所組成的功能。</span><span class="sxs-lookup"><span data-stu-id="12abf-110">Web protection in Microsoft Defender for Endpoint is a capability made up of [Web threat protection](web-threat-protection.md) and [Web content filtering](web-content-filtering.md).</span></span> <span data-ttu-id="12abf-111">Web 保護功能可讓您保護裝置免受網頁威脅，並協助您控制不想要的內容。</span><span class="sxs-lookup"><span data-stu-id="12abf-111">Web protection lets you secure your devices against web threats and helps you regulate unwanted content.</span></span> <span data-ttu-id="12abf-112">您可以在 Microsoft Defender Security Center 中尋找 Web 保護報告，以 **> web 保護的報表**。</span><span class="sxs-lookup"><span data-stu-id="12abf-112">You can find Web protection reports in the Microsoft Defender Security Center by going to **Reports > Web protection**.</span></span>

![所有 web 保護卡的影像](images/web-protection.png)

## <a name="web-threat-protection"></a><span data-ttu-id="12abf-114">網頁威脅防護</span><span class="sxs-lookup"><span data-stu-id="12abf-114">Web threat protection</span></span>

<span data-ttu-id="12abf-115">組成網頁威脅防護的卡片是一段時間和 **網頁威脅摘要** 中的 **web 威脅** 偵測。</span><span class="sxs-lookup"><span data-stu-id="12abf-115">The cards that make up web threat protection are **Web threat detections over time** and **Web threat summary**.</span></span>

<span data-ttu-id="12abf-116">網頁威脅防護包括：</span><span class="sxs-lookup"><span data-stu-id="12abf-116">Web threat protection includes:</span></span>
- <span data-ttu-id="12abf-117">深入瞭解影響組織的 web 威脅</span><span class="sxs-lookup"><span data-stu-id="12abf-117">Comprehensive visibility into web threats affecting your organization</span></span>
- <span data-ttu-id="12abf-118">透過透過網路相關之威脅活動的功能和 URLs 及可存取這些 URLs 裝置的綜合設定檔，調查功能</span><span class="sxs-lookup"><span data-stu-id="12abf-118">Investigation capabilities over web-related threat activity through alerts and comprehensive profiles of URLs and the devices that access these URLs</span></span>
- <span data-ttu-id="12abf-119">一組完整的安全性功能，可追蹤對惡意及有害網站的一般存取趨勢</span><span class="sxs-lookup"><span data-stu-id="12abf-119">A full set of security features that track general access trends to malicious and unwanted websites</span></span>

## <a name="web-content-filtering"></a><span data-ttu-id="12abf-120">Web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="12abf-120">Web content filtering</span></span>

<span data-ttu-id="12abf-121">組成 web 內容篩選的卡片是依類別、**網頁內容篩選摘要** 及 **網頁活動摘要** 的 **web 活動**。</span><span class="sxs-lookup"><span data-stu-id="12abf-121">The cards that comprise web content filtering are **Web activity by category**, **Web content filtering summary**, and **Web activity summary**.</span></span>

<span data-ttu-id="12abf-122">Web 內容篩選包括：</span><span class="sxs-lookup"><span data-stu-id="12abf-122">Web content filtering includes:</span></span>
- <span data-ttu-id="12abf-123">使用者無法存取封鎖類別中的網站，不論他們流覽內部部署或離開</span><span class="sxs-lookup"><span data-stu-id="12abf-123">Users are prevented from accessing websites in blocked categories, whether they are browsing on-premises or away</span></span>
- <span data-ttu-id="12abf-124">您可以使用[Microsoft Defender For Endpoint role 的存取控制設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)中所定義的裝置群組，輕鬆地將不同的原則部署至不同的使用者群組</span><span class="sxs-lookup"><span data-stu-id="12abf-124">You can conveniently deploy varied policies to various sets of users using the device groups defined in the [Microsoft Defender for Endpoint role-based access control settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="12abf-125">您可以在相同的中央位置存取 web 報表，並透過實際區塊和 web 使用狀況進行查看</span><span class="sxs-lookup"><span data-stu-id="12abf-125">You can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="in-this-section"></a><span data-ttu-id="12abf-126">本節內容</span><span class="sxs-lookup"><span data-stu-id="12abf-126">In this section</span></span>

<span data-ttu-id="12abf-127">主題</span><span class="sxs-lookup"><span data-stu-id="12abf-127">Topic</span></span> | <span data-ttu-id="12abf-128">描述</span><span class="sxs-lookup"><span data-stu-id="12abf-128">Description</span></span>
:---|:---
[<span data-ttu-id="12abf-129">網頁威脅防護</span><span class="sxs-lookup"><span data-stu-id="12abf-129">Web threat protection</span></span>](web-threat-protection.md) | <span data-ttu-id="12abf-130">停止存取網路釣魚網站、惡意程式碼向量、exploit 網站、不信任或低信譽網站，以及您已封鎖的網站。</span><span class="sxs-lookup"><span data-stu-id="12abf-130">Stop access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked.</span></span>
[<span data-ttu-id="12abf-131">Web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="12abf-131">Web content filtering</span></span>](web-content-filtering.md) | <span data-ttu-id="12abf-132">根據網站的內容類別別，追蹤和控制網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="12abf-132">Track and regulate access to websites based on their content categories.</span></span>
