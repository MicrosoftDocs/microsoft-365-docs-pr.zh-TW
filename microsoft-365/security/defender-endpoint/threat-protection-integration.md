---
title: 整合 Microsoft Defender for Endpoint with 其他 Microsoft 解決方案
description: 瞭解 Microsoft Defender for Endpoint 如何與其他 Microsoft 解決方案整合，包括 Microsoft Defender for Identity 和 Azure Security Center。
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender，條件式存取，office，高級威脅防護，microsoft defender 身分識別，microsoft defender for office，azure security center，microsoft cloud app security，azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 287ad9adeccd527b756bdd5304d3c89fc1b2d789
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060488"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="d0735-104">Microsoft Defender for Endpoint 和其他 Microsoft 解決方案</span><span class="sxs-lookup"><span data-stu-id="d0735-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d0735-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d0735-105">**Applies to:**</span></span>
- [<span data-ttu-id="d0735-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d0735-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d0735-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0735-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d0735-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d0735-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d0735-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d0735-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="d0735-110">與其他 Microsoft 解決方案整合</span><span class="sxs-lookup"><span data-stu-id="d0735-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="d0735-111">Microsoft Defender for Endpoint 直接與各種 Microsoft 解決方案整合。</span><span class="sxs-lookup"><span data-stu-id="d0735-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-security-center"></a><span data-ttu-id="d0735-112">Azure 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="d0735-112">Azure Security Center</span></span>
<span data-ttu-id="d0735-113">Microsoft Defender for Endpoint 提供綜合的伺服器保護解決方案，包括 Windows Server 上的端點偵測和回應 (EDR) 功能。</span><span class="sxs-lookup"><span data-stu-id="d0735-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="d0735-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="d0735-114">Azure Sentinel</span></span>
<span data-ttu-id="d0735-115">Microsoft Defender for Endpoint connector 可讓您將來自 Microsoft Defender for Endpoint 的警示資料流程成 Azure Sentinel。</span><span class="sxs-lookup"><span data-stu-id="d0735-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="d0735-116">這可讓您更深入地分析整個組織的安全性事件，並建立行動行動以取得有效且立即的回應。</span><span class="sxs-lookup"><span data-stu-id="d0735-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="d0735-117">Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="d0735-117">Azure Information Protection</span></span>
<span data-ttu-id="d0735-118">將敏感性資料保持安全，同時透過資料探索和資料保護在工作場所中實現生產力。</span><span class="sxs-lookup"><span data-stu-id="d0735-118">Keep sensitive data secure while enabling productivity in the workplace through data discovery and data protection.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="d0735-119">條件式存取</span><span class="sxs-lookup"><span data-stu-id="d0735-119">Conditional Access</span></span>
<span data-ttu-id="d0735-120">Microsoft Defender for Endpoint 的動態裝置風險分數已整合到條件式存取評估中，以確保只有安全裝置能夠存取資源。</span><span class="sxs-lookup"><span data-stu-id="d0735-120">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="d0735-121">Microsoft 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="d0735-121">Microsoft Cloud App Security</span></span>
<span data-ttu-id="d0735-122">Microsoft Cloud App Security 利用 Microsoft Defender for Endpoint endpoint 信號來允許直接查看 cloud 應用程式使用情形，包括使用不受支援的雲端服務 (陰影它) 從所有 Microsoft Defender for Endpoint 受監視裝置。</span><span class="sxs-lookup"><span data-stu-id="d0735-122">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="d0735-123">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d0735-123">Microsoft Defender for Identity</span></span>
<span data-ttu-id="d0735-124">可疑活動是指在使用者內容下執行的進程。</span><span class="sxs-lookup"><span data-stu-id="d0735-124">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="d0735-125">Microsoft Defender for Endpoint 和 Azure ATP 之間的整合，可讓您靈活地進行跨活動和身分識別的網路安全性調查。</span><span class="sxs-lookup"><span data-stu-id="d0735-125">The integration between Microsoft Defender for Endpoint and Azure ATP provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="d0735-126">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="d0735-126">Microsoft Defender for Office</span></span>
<span data-ttu-id="d0735-127">[Office 365 的 Defender](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) 可協助您的組織避免電子郵件中的惡意程式碼或檔案中的 Atp 安全連結、Atp 安全附件、高級反網路釣魚和欺騙智慧功能。</span><span class="sxs-lookup"><span data-stu-id="d0735-127">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through ATP Safe Links, ATP Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="d0735-128">Office 365 ATP 和 Microsoft Defender for Endpoint 之間的整合，可讓安全性分析師進行上游調查，以調查攻擊的進入點。</span><span class="sxs-lookup"><span data-stu-id="d0735-128">The integration between Office 365 ATP and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="d0735-129">透過威脅智慧共用，攻擊可以包含並封鎖。</span><span class="sxs-lookup"><span data-stu-id="d0735-129">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="d0735-130">在過去30天內，會顯示事件的 Defender for Office 365 資料。</span><span class="sxs-lookup"><span data-stu-id="d0735-130">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="d0735-131">針對警示，Office 365 資料的 Defender 會根據第一個啟用時間來顯示。</span><span class="sxs-lookup"><span data-stu-id="d0735-131">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="d0735-132">之後，Office 365 的資料就不再提供。</span><span class="sxs-lookup"><span data-stu-id="d0735-132">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="d0735-133">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="d0735-133">Skype for Business</span></span>
<span data-ttu-id="d0735-134">商務用 Skype 整合提供一種方法，讓分析員透過來自入口網站的簡單按鈕，與可能已遭破壞的使用者或裝置擁有者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="d0735-134">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="d0735-135">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0735-135">Microsoft 365 Defender</span></span>
<span data-ttu-id="d0735-136">使用 Microsoft 365 Defender 時，Microsoft Defender for Endpoint 和各種 Microsoft security 解決方案組成的整合內發佈的後續企業防護套件，可共同整合在端點、身分識別、電子郵件和應用程式中，以偵測、避免、調查和自動回應複雜的攻擊。</span><span class="sxs-lookup"><span data-stu-id="d0735-136">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="d0735-137">深入瞭解 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0735-137">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="d0735-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="d0735-138">Related topics</span></span>
- [<span data-ttu-id="d0735-139">設定整合及其他高級功能</span><span class="sxs-lookup"><span data-stu-id="d0735-139">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="d0735-140">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="d0735-140">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="d0735-141">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0735-141">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="d0735-142">使用條件式存取來保護使用者、資料和裝置</span><span class="sxs-lookup"><span data-stu-id="d0735-142">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
