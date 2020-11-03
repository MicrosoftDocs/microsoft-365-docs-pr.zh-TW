---
title: Microsoft 受管理電腦中的安全性作業
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5698e2a88adf3d2bae84a82e0e001132293e36be
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847713"
---
# <a name="security-operations-in-microsoft-managed-desktop"></a><span data-ttu-id="f1c84-103">Microsoft 受管理電腦中的安全性作業</span><span class="sxs-lookup"><span data-stu-id="f1c84-103">Security operations in Microsoft Managed Desktop</span></span>

<span data-ttu-id="f1c84-104">Microsoft Managed Desktop Security Operations Center (SOC) 合作夥伴與您的資訊安全性人員，讓您的桌面環境保持安全。</span><span class="sxs-lookup"><span data-stu-id="f1c84-104">The Microsoft Managed Desktop Security Operations Center (SOC) partners with your information security staff to keep your desktop environment secure.</span></span> <span data-ttu-id="f1c84-105">我們的小組會透過專家分析接收並回應受管理裝置上的所有安全性警示，而且在需要時，我們會促進安全性事件回應活動。</span><span class="sxs-lookup"><span data-stu-id="f1c84-105">Our team receives and responds to all security alerts on managed devices with expert analysis and, when needed, we drive security incident response activities.</span></span> <span data-ttu-id="f1c84-106">如需使用 SOC 的詳細資訊，請參閱系統管理入口網站的操作檔。</span><span class="sxs-lookup"><span data-stu-id="f1c84-106">For more information about working with the SOC, review operational documentation at your Admin portal.</span></span>

<span data-ttu-id="f1c84-107">SOC 從 Microsoft 全職員工提供24/7/365 的範圍，包含目前和新興威脅形勢的專業知識，包括透過軟體、網路或人力敵人的常見攻擊方法。</span><span class="sxs-lookup"><span data-stu-id="f1c84-107">The SOC offers 24/7/365 coverage from Microsoft full-time employees with expertise in the current and emerging threat landscape, including common attack methods through software, network, or human adversaries.</span></span>

<span data-ttu-id="f1c84-108">SOC 提供下列服務：</span><span class="sxs-lookup"><span data-stu-id="f1c84-108">The SOC provides these services:</span></span>
- <span data-ttu-id="f1c84-109">對偵測到事件的快速且準確的回應，以及資料分析來識別影響，並評估裝置或您環境的整體風險</span><span class="sxs-lookup"><span data-stu-id="f1c84-109">Quick and accurate response to detected events, with analysis of data to identify the impact and assess the overall risk to a device or your environment</span></span>
- <span data-ttu-id="f1c84-110">裝置管理和隔離動作可保護您的環境免受已知或可疑的損害，避免因阻礙傳播而降低風險</span><span class="sxs-lookup"><span data-stu-id="f1c84-110">Device management and isolation actions to protect your environment from known or suspected compromises, reducing risk by preventing spread</span></span>
- <span data-ttu-id="f1c84-111">推動安全性事件回應程式，以確保與安全性小組及時且準確地進行通訊</span><span class="sxs-lookup"><span data-stu-id="f1c84-111">Driving the security incident response process, ensuring timely and accurate communication with your security team</span></span>
- <span data-ttu-id="f1c84-112">以威脅和弱點資料為基礎的分析和建議，可在受到攻擊之前識別並解決風險</span><span class="sxs-lookup"><span data-stu-id="f1c84-112">Analysis and recommendations based on threat and vulnerability data to identify and address risks before they're exploited</span></span>
- <span data-ttu-id="f1c84-113">跨受管理裝置的高級搜尋，以找出已知和潛在威脅的指示器和實體</span><span class="sxs-lookup"><span data-stu-id="f1c84-113">Advanced hunting across the managed devices to identify indicators and entities for both known and potential threats</span></span>

## <a name="processes"></a><span data-ttu-id="f1c84-114">過程</span><span class="sxs-lookup"><span data-stu-id="f1c84-114">Processes</span></span>

- <span data-ttu-id="f1c84-115">Microsoft 受管理的桌面安全性作業是由全職 Microsoft 員工共同作業，以 Microsoft 的 [網路國防作業中心](https://www.microsoft.com/msrc/cdoc)為合作。</span><span class="sxs-lookup"><span data-stu-id="f1c84-115">Microsoft Managed Desktop Security Operations is staffed by full-time Microsoft employees in partnership with  Microsoft’s [Cyber Defense Operations Center](https://www.microsoft.com/msrc/cdoc).</span></span> 
- <span data-ttu-id="f1c84-116">我們的 SOC 使用來自我們公司的綜合信號（包括內部及外部），以保護您的裝置--甚至是 Microsoft 受管理電腦中尚未看到的專案。</span><span class="sxs-lookup"><span data-stu-id="f1c84-116">Our SOC uses collective signals from across our company, both internal and external, to protect your devices--even from things we have not yet seen in Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="f1c84-117">Microsoft 安全性解決方案會對應許多 cybersecurity 保護標準。</span><span class="sxs-lookup"><span data-stu-id="f1c84-117">Microsoft security solutions align to many cybersecurity protection standards.</span></span> <span data-ttu-id="f1c84-118">SOC 作業是以國家安全局的國家標準和技術電腦安全性性事件回應處理指南 (NIST 800-61 r2) 為基礎。</span><span class="sxs-lookup"><span data-stu-id="f1c84-118">SOC operations are based on the National Institute of Standards and Technology Computer Security Incident Response Handling Guide (NIST 800-61 r2).</span></span>
- <span data-ttu-id="f1c84-119">此程式可讓您正確地集合資訊和證據，以供分析和檔和復原深入瞭解，以透過這些階段更好地保護您的環境：</span><span class="sxs-lookup"><span data-stu-id="f1c84-119">The process allows for proper collection of information and evidence, for analysis and documentation and post-recovery insights into ways to better defend your environment through these phases:</span></span>
    - <span data-ttu-id="f1c84-120">準備、偵測和分析</span><span class="sxs-lookup"><span data-stu-id="f1c84-120">Preparation, detection, and analysis</span></span>
    - <span data-ttu-id="f1c84-121">遏制</span><span class="sxs-lookup"><span data-stu-id="f1c84-121">Containment</span></span>
    - <span data-ttu-id="f1c84-122">根除</span><span class="sxs-lookup"><span data-stu-id="f1c84-122">Eradication</span></span>
    - <span data-ttu-id="f1c84-123">恢復</span><span class="sxs-lookup"><span data-stu-id="f1c84-123">Recovery</span></span>
    - <span data-ttu-id="f1c84-124">事件後活動</span><span class="sxs-lookup"><span data-stu-id="f1c84-124">Post-incident activity</span></span>
- <span data-ttu-id="f1c84-125">Microsoft 受管理的桌面客戶可以註冊 Microsoft 威脅專家服務。</span><span class="sxs-lookup"><span data-stu-id="f1c84-125">Microsoft Managed Desktop customers are eligible to enroll in the Microsoft Threat Experts service.</span></span> <span data-ttu-id="f1c84-126">使用此服務的 SOC liaises，可深入瞭解影響組織的複雜威脅，包括警示查詢、可能受損的裝置、可疑網路連線的根本原因，以及有關持續性的高級威脅活動的其他威脅情報。</span><span class="sxs-lookup"><span data-stu-id="f1c84-126">The SOC liaises with this service to understand better the complex threats affecting your organization, including alert inquiries, potentially compromised devices, root cause of a suspicious network connection, and additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="f1c84-127">如需詳細資訊，請參閱 [Microsoft 威脅專家](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。</span><span class="sxs-lookup"><span data-stu-id="f1c84-127">For more information, see [Microsoft Threat Experts](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).</span></span>
- <span data-ttu-id="f1c84-128">SOC 的威脅和弱點管理程式會使用 Microsoft 的部分服務，協助告知組織的建議，以防禦威脅。</span><span class="sxs-lookup"><span data-stu-id="f1c84-128">SOC’s Threat and Vulnerability Management process uses some of Microsoft’s services to help inform recommendations for your organization to protect against threats.</span></span> <span data-ttu-id="f1c84-129">SOC 會使用 Microsoft Defender for Endpoint Security Center 中的資料，以及從 Microsoft 內外的相關弱點資料來源探索安全性漏洞與錯誤配置，並提供可操作的報告。</span><span class="sxs-lookup"><span data-stu-id="f1c84-129">The SOC consumes data from your Microsoft Defender for Endpoint Security Center and from relevant vulnerability data sources within and outside of Microsoft to discover vulnerabilities and misconfigurations and provide actionable reporting.</span></span>
