---
title: 整合 Microsoft Defender for Endpoint with 其他 Microsoft 解決方案
description: 瞭解 Microsoft Defender for Endpoint 如何與其他 Microsoft 解決方案（包括 Microsoft Defender 身分識別和 Azure Defender）整合。
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender，條件式存取，office，Microsoft Defender for Endpoint，microsoft defender for identity，microsoft defender for office，Azure Defender，microsoft cloud app security，azure sentinel
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
ms.openlocfilehash: 8973a78787345532055161507e2d30f75b3b2cf1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844967"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="ddad3-104">Microsoft Defender for Endpoint 和其他 Microsoft 解決方案</span><span class="sxs-lookup"><span data-stu-id="ddad3-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ddad3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ddad3-105">**Applies to:**</span></span>
- [<span data-ttu-id="ddad3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ddad3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ddad3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ddad3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ddad3-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="ddad3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ddad3-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ddad3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="ddad3-110">與其他 Microsoft 解決方案整合</span><span class="sxs-lookup"><span data-stu-id="ddad3-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="ddad3-111">Microsoft Defender for Endpoint 直接與各種 Microsoft 解決方案整合。</span><span class="sxs-lookup"><span data-stu-id="ddad3-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="ddad3-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="ddad3-112">Azure Defender</span></span>
<span data-ttu-id="ddad3-113">Microsoft Defender for Endpoint 提供綜合的伺服器保護解決方案，包括 (Windows 伺服器 EDR) 功能的端點偵測和回應。</span><span class="sxs-lookup"><span data-stu-id="ddad3-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="ddad3-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="ddad3-114">Azure Sentinel</span></span>
<span data-ttu-id="ddad3-115">Microsoft Defender for Endpoint connector 可讓您將來自 Microsoft Defender for Endpoint 的警示資料流程成 Azure Sentinel。</span><span class="sxs-lookup"><span data-stu-id="ddad3-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="ddad3-116">這可讓您更深入地分析整個組織的安全性事件，並建立行動行動以取得有效且立即的回應。</span><span class="sxs-lookup"><span data-stu-id="ddad3-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="ddad3-117">Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="ddad3-117">Azure Information Protection</span></span>
<span data-ttu-id="ddad3-118">近來，我們最近取代 Azure 資訊保護整合，因為在端點 DLP 功能中，會針對儲存在端點裝置上的機密資料，結合使用已改善的探索和保護解決方案，以更深入的方式與解決方案之間的整合。</span><span class="sxs-lookup"><span data-stu-id="ddad3-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="ddad3-119">這已于下列 [博客](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)宣告。</span><span class="sxs-lookup"><span data-stu-id="ddad3-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="ddad3-120">我們建議客戶移至使用端點 DLP。</span><span class="sxs-lookup"><span data-stu-id="ddad3-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="ddad3-121">條件式存取</span><span class="sxs-lookup"><span data-stu-id="ddad3-121">Conditional Access</span></span>
<span data-ttu-id="ddad3-122">Microsoft Defender for Endpoint 的動態裝置風險分數已整合到條件式存取評估中，以確保只有安全裝置能夠存取資源。</span><span class="sxs-lookup"><span data-stu-id="ddad3-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="ddad3-123">Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="ddad3-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="ddad3-124">Microsoft Cloud App Security 利用 Microsoft Defender for endpoint 端點信號，允許直接查看 cloud 應用程式使用方式，包括使用不受支援的雲端服務 (陰影 IT) 從所有 Microsoft Defender for Endpoint 受監視裝置。</span><span class="sxs-lookup"><span data-stu-id="ddad3-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="ddad3-125">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ddad3-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="ddad3-126">可疑活動是指在使用者內容下執行的進程。</span><span class="sxs-lookup"><span data-stu-id="ddad3-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="ddad3-127">Microsoft Defender for Endpoint 和 Microsoft Defender 身分識別之間的整合，可讓您靈活地進行跨活動和身分識別的網路安全性調查。</span><span class="sxs-lookup"><span data-stu-id="ddad3-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="ddad3-128">Microsoft Defender Office</span><span class="sxs-lookup"><span data-stu-id="ddad3-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="ddad3-129">[Office 365 的 Defender](/office365/securitycompliance/office-365-atp) ，可透過安全連結、安全附件、高級反網路釣魚和欺騙智慧功能，協助您的組織避免電子郵件中的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="ddad3-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="ddad3-130">microsoft defender for Office 365 和 microsoft defender for Endpoint 之間的整合，可讓安全性分析者深入查看攻擊的進入點。</span><span class="sxs-lookup"><span data-stu-id="ddad3-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="ddad3-131">透過威脅智慧共用，攻擊可以包含並封鎖。</span><span class="sxs-lookup"><span data-stu-id="ddad3-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="ddad3-132">在過去30天內顯示事件的 Office 365 資料的 Defender。</span><span class="sxs-lookup"><span data-stu-id="ddad3-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="ddad3-133">針對警示，Office 365 資料的 Defender 會根據第一個啟用時間來顯示。</span><span class="sxs-lookup"><span data-stu-id="ddad3-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="ddad3-134">之後，Office 365 中便無法再使用資料。</span><span class="sxs-lookup"><span data-stu-id="ddad3-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="ddad3-135">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="ddad3-135">Skype for Business</span></span>
<span data-ttu-id="ddad3-136">商務用 Skype 整合提供一種方法，讓分析員透過來自入口網站的簡單按鈕，與可能已遭破壞的使用者或裝置擁有者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="ddad3-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="ddad3-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ddad3-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="ddad3-138">使用 Microsoft 365 defender 時，microsoft defender for Endpoint 和各種 Microsoft security 解決方案組成的整合發佈前防護套件，可內部整合在端點、身分識別、電子郵件和應用程式中，以偵測、避免、調查和自動回應複雜的攻擊。</span><span class="sxs-lookup"><span data-stu-id="ddad3-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="ddad3-139">深入瞭解 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ddad3-139">Learn more about Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="ddad3-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="ddad3-140">Related topics</span></span>
- [<span data-ttu-id="ddad3-141">設定整合及其他高級功能</span><span class="sxs-lookup"><span data-stu-id="ddad3-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="ddad3-142">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="ddad3-142">Microsoft 365 Defender overview</span></span>](/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="ddad3-143">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ddad3-143">Turn on Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="ddad3-144">使用條件式存取來保護使用者、資料和裝置</span><span class="sxs-lookup"><span data-stu-id="ddad3-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
