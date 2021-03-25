---
title: 從 Microsoft Defender for Endpoint 向您的 SIEM 工具提取偵測
description: 瞭解如何使用 REST API 及設定支援的安全性資訊和事件管理工具來接收及提取偵測。
keywords: 設定 siem、安全性資訊和事件管理工具、splunk、arcsight、自訂指示器、rest api、警示定義、損等指示器
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
ms.openlocfilehash: 0b9ce376736e5f00ee0f6a4f308d783e75052357
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163291"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="600dd-104">向 SIEM 工具提取偵測</span><span class="sxs-lookup"><span data-stu-id="600dd-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="600dd-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="600dd-105">**Applies to:**</span></span>
- [<span data-ttu-id="600dd-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="600dd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="600dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="600dd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="600dd-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="600dd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="600dd-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="600dd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="600dd-110">使用安全性資訊和事件管理 (SIEM) 工具提取偵測</span><span class="sxs-lookup"><span data-stu-id="600dd-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="600dd-111">[Microsoft Defender For Endpoint Alert](alerts.md) 是由一或多個偵測所組成。</span><span class="sxs-lookup"><span data-stu-id="600dd-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="600dd-112">[Microsoft Defender For Endpoint 偵測](api-portal-mapping.md) 是由裝置上發生的可疑事件及其相關警示詳細資料所組成。</span><span class="sxs-lookup"><span data-stu-id="600dd-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="600dd-113">-Microsoft Defender for Endpoint Alert API 是最新的警示消耗 API，且包含每個警示的相關證據的詳細清單。</span><span class="sxs-lookup"><span data-stu-id="600dd-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="600dd-114">如需詳細資訊，請參閱 [Alert 方法和屬性](alerts.md) 和 [清單警示](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="600dd-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="600dd-115">Defender for Endpoint 支援安全性資訊和事件管理 (SIEM) 工具來提取偵測。</span><span class="sxs-lookup"><span data-stu-id="600dd-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="600dd-116">端點會透過 Azure 所主控的 HTTPS 端點公開警示。</span><span class="sxs-lookup"><span data-stu-id="600dd-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="600dd-117">端點可以設定為在 Azure Active Directory (AAD) 中使用 OAuth 2.0 驗證通訊協定來拉入您環境中所安裝之特定 SIEM 連接器的 AAD 應用程式的偵測。</span><span class="sxs-lookup"><span data-stu-id="600dd-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="600dd-118">SIEM 的 Defender 目前是透過專用的 SIEM 整合模型，支援下列特定的解決方案工具：</span><span class="sxs-lookup"><span data-stu-id="600dd-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="600dd-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="600dd-119">IBM QRadar</span></span>
- <span data-ttu-id="600dd-120">微焦點 ArcSight</span><span class="sxs-lookup"><span data-stu-id="600dd-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="600dd-121">其他 SIEM 解決方案 (例如 Splunk、RSA NetWitness) ，都是透過以新的警示 API 為基礎的不同整合模型所支援。</span><span class="sxs-lookup"><span data-stu-id="600dd-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="600dd-122">如需詳細資訊，請查看 [ [夥伴應用程式](https://securitycenter.microsoft.com/interoperability/partners) ] 頁面，然後選取 [安全性資訊與分析] 區段以取得完整詳細資料。</span><span class="sxs-lookup"><span data-stu-id="600dd-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="600dd-123">若要使用其中一種支援的 SIEM 工具，您必須：</span><span class="sxs-lookup"><span data-stu-id="600dd-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="600dd-124">在 Defender for Endpoint 中啟用 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="600dd-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="600dd-125">設定支援的 SIEM 工具：</span><span class="sxs-lookup"><span data-stu-id="600dd-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="600dd-126">設定 HP ArcSight 以拉入 Defender 以進行端點偵測</span><span class="sxs-lookup"><span data-stu-id="600dd-126">Configure HP ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="600dd-127">設定 IBM QRadar 若要深入瞭解端點偵測以取得資訊，請參閱 [Ibm 知識中心](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。</span><span class="sxs-lookup"><span data-stu-id="600dd-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="600dd-128">如需在偵測 API 中公開的欄位清單的詳細資訊，請參閱， [Defender For Endpoint 偵測欄位](api-portal-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="600dd-128">For more information on the list of fields exposed in the Detection API see, [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
