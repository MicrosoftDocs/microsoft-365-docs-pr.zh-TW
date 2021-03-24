---
title: Microsoft Cloud App Security 整合概述
ms.reviewer: ''
description: Microsoft Defender for Endpoint 會透過轉送所有雲端 app 網路活動，與 Cloud App 安全性整合。
keywords: 雲端，應用程式，網路，可視性，使用
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 6ea885c17cf506ef6f9a4a7138630aed671f0ce8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059407"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="1687d-104">Defender for Endpoint 中的 Microsoft Cloud App Security 簡介</span><span class="sxs-lookup"><span data-stu-id="1687d-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1687d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1687d-105">**Applies to:**</span></span>
- [<span data-ttu-id="1687d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1687d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="1687d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1687d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="1687d-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1687d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1687d-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1687d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1687d-110">Microsoft Cloud App Security (Cloud App Security) 是一種全面的解決方案，可讓您控制和限制雲端應用程式的存取，同時也會在雲端儲存的資料上強制執行規范的需求。</span><span class="sxs-lookup"><span data-stu-id="1687d-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="1687d-111">如需詳細資訊，請參閱 [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="1687d-111">For more information, see [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="1687d-112">在執行 Windows 10 版本1809或更新版本的裝置上，使用 [企業行動](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) 裝置和安全性的 E5 授權可取得此功能。</span><span class="sxs-lookup"><span data-stu-id="1687d-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="1687d-113">Microsoft Defender for Endpoint 和 Cloud App Security 整合</span><span class="sxs-lookup"><span data-stu-id="1687d-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="1687d-114">雲端應用程式安全性探索依賴從企業防火牆和 proxy 伺服器轉寄的雲端流量記錄。</span><span class="sxs-lookup"><span data-stu-id="1687d-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="1687d-115">Microsoft Defender for Endpoint 會透過收集和轉寄所有雲端應用程式網路活動，以與雲端 App 安全性整合，以提供 Cloud app 使用狀況的無與倫比的洞察力。</span><span class="sxs-lookup"><span data-stu-id="1687d-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="1687d-116">監視功能是內置於裝置中，可提供完整的網路活動範圍。</span><span class="sxs-lookup"><span data-stu-id="1687d-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="1687d-117">整合針對現有的雲端應用程式安全性探索提供下列重大改進：</span><span class="sxs-lookup"><span data-stu-id="1687d-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="1687d-118">隨處可用-因為網路活動是直接從端點收集，所以不論是在公司網路上，還是在公司網路上，只要該裝置不再是透過企業防火牆或 proxy 伺服器路由傳送的流量，便可使用。</span><span class="sxs-lookup"><span data-stu-id="1687d-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="1687d-119">可在盒外運作，不需要設定將雲端流量記錄送出至 Cloud App 安全性需要防火牆和 proxy 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="1687d-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="1687d-120">使用 Defender for Endpoint 和 Cloud App Security 整合，不需要進行任何設定。</span><span class="sxs-lookup"><span data-stu-id="1687d-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="1687d-121">只要在 Microsoft Defender 安全性中心設定中切換，您就可以繼續。</span><span class="sxs-lookup"><span data-stu-id="1687d-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="1687d-122">裝置內容-Cloud 流量記錄檔缺乏裝置內容。</span><span class="sxs-lookup"><span data-stu-id="1687d-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="1687d-123">Defender for Endpoint network activity 會以裝置內容來報告 (哪些裝置存取雲端 app) ，因此您可以完全瞭解 (裝置) 網路活動的位置，以及 (使用者) 執行它的情況。</span><span class="sxs-lookup"><span data-stu-id="1687d-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="1687d-124">如需雲端探索的詳細資訊，請參閱使用已 [探索的應用程式](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="1687d-124">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="1687d-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="1687d-125">Related topic</span></span>

- [<span data-ttu-id="1687d-126">設定 Microsoft Cloud App Security 整合</span><span class="sxs-lookup"><span data-stu-id="1687d-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
