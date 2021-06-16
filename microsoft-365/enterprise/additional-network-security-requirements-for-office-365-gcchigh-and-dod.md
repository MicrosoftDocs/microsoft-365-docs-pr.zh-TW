---
title: Office 365 GCC 高 DoD 和的額外網路安全性需求
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 摘要： Office 365 GCC 高及 DoD 具有其他網路安全性需求
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926556"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="24dd0-103">Office 365 GCC High 和 DOD 的額外網路安全性需求</span><span class="sxs-lookup"><span data-stu-id="24dd0-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="24dd0-104">*本文適用于 Office 365 GCC 高、Office 365 DOD、Microsoft 365 GCC 高及 Microsoft 365 DOD。*</span><span class="sxs-lookup"><span data-stu-id="24dd0-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="24dd0-105">Office 365 GCC 高和 DOD 為安全的雲端環境，可滿足美國政府和其供應商和承包商的需求。</span><span class="sxs-lookup"><span data-stu-id="24dd0-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="24dd0-106">這些雲端環境對允許服務存取的外部端點有額外的網路限制。</span><span class="sxs-lookup"><span data-stu-id="24dd0-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="24dd0-107">GCC使用同盟身分識別或混合共存的高和 DOD 客戶可能需要 Microsoft 允許對您現有內部部署的輸入和/或輸出存取權。</span><span class="sxs-lookup"><span data-stu-id="24dd0-107">GCC High and DOD customers planning to use federated identities or hybrid coexistence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="24dd0-108">這些活動的範例包括：</span><span class="sxs-lookup"><span data-stu-id="24dd0-108">Examples of these activities include:</span></span>

* <span data-ttu-id="24dd0-109">使用 Active Directory Federation Services 或類似支援的 STS) 的同盟識別碼 (</span><span class="sxs-lookup"><span data-stu-id="24dd0-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="24dd0-110">使用內部部署 Exchange Server 或商務用 Skype 部署的混合共存</span><span class="sxs-lookup"><span data-stu-id="24dd0-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="24dd0-111">從內部部署系統移轉現有的使用者內容</span><span class="sxs-lookup"><span data-stu-id="24dd0-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="24dd0-112">若要允許服務與您的內部部署端點通訊，您 **必須** 傳送電子郵件給 Office 365 工程進行網路變更。</span><span class="sxs-lookup"><span data-stu-id="24dd0-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="24dd0-113">所有要求都有 **三周** 的 SLA，所以由於必要的安全性和合規性控制和部署管線，所以無法加速。</span><span class="sxs-lookup"><span data-stu-id="24dd0-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="24dd0-114">這包括初始上架網路要求，以及遷移至服務之後的任何變更。</span><span class="sxs-lookup"><span data-stu-id="24dd0-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="24dd0-115">確定您的網路小組意識到此時程表，並將其包含在規劃週期中。</span><span class="sxs-lookup"><span data-stu-id="24dd0-115">Make sure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="24dd0-116">使用下列資訊，傳送電子郵件給[Office 365 政府版 Allow-List 要求](mailto:o365gwlt@microsoft.com)：</span><span class="sxs-lookup"><span data-stu-id="24dd0-116">Send an email to [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="24dd0-117">**若要**： [Office 365 政府版 Allow-List 要求](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="24dd0-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="24dd0-118">**來源**：租使用者管理員-傳送電子郵件 **必須** 符合您租使用者中的全域系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="24dd0-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="24dd0-119">**電子郵件主題**： Office 365 GCC 高網路要求-contoso.onmicrosoft.us (以租使用者名稱取代) </span><span class="sxs-lookup"><span data-stu-id="24dd0-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace with your tenant name)</span></span>

<span data-ttu-id="24dd0-120">您的郵件本文應包含下列資料：</span><span class="sxs-lookup"><span data-stu-id="24dd0-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="24dd0-121">您的 Microsoft Online Services 租使用者名稱 (例如，contoso.onmicrosoft.com、fabrikam.onmicrosoft.us) </span><span class="sxs-lookup"><span data-stu-id="24dd0-121">Your Microsoft Online Services tenant name (for example, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="24dd0-122">一個電子郵件通訊群組清單，Microsoft 會與其通訊，以進行與網路變更和/或追蹤無效子網有關的即時通訊</span><span class="sxs-lookup"><span data-stu-id="24dd0-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="24dd0-123">指出您是否計畫使用 Microsoft Teams 與內部部署的混合共存</span><span class="sxs-lookup"><span data-stu-id="24dd0-123">Indicate whether you plan to use Microsoft Teams hybrid coexistence with your on-premises deployments</span></span>
* <span data-ttu-id="24dd0-124">同盟身分識別系統外部可存取的 URL (例如，sts.contoso.com) 和 CIDR 標記法中的 IP 位址範圍 (例如，。</span><span class="sxs-lookup"><span data-stu-id="24dd0-124">Federated identity system externally accessible URL (for example, sts.contoso.com) and IP address range in CIDR notation (for example,.</span></span> <span data-ttu-id="24dd0-125">10.1.1.0/28) </span><span class="sxs-lookup"><span data-stu-id="24dd0-125">10.1.1.0/28)</span></span>
* <span data-ttu-id="24dd0-126">On-Premises PKI 憑證吊銷清單 URL 與 CIDR 標記法中的 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="24dd0-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="24dd0-127">以 CIDR 標記法 Exchange Server 內部部署的外部可存取 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="24dd0-127">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="24dd0-128">以 CIDR 標記法商務用 Skype 內部部署的外部可存取 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="24dd0-128">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="24dd0-129">根據安全性和合規性原因，請記住您要求的下列限制：</span><span class="sxs-lookup"><span data-stu-id="24dd0-129">For security and compliance reasons, keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="24dd0-130">每個租使用者有四個子網限制</span><span class="sxs-lookup"><span data-stu-id="24dd0-130">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="24dd0-131">子網必須是 CIDR 標記法 (例如 10.1.1.0/28) </span><span class="sxs-lookup"><span data-stu-id="24dd0-131">Subnets must be in CIDR Notation (for example, 10.1.1.0/28)</span></span>
* <span data-ttu-id="24dd0-132">子網範圍不能大於/24</span><span class="sxs-lookup"><span data-stu-id="24dd0-132">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="24dd0-133">我們 **無法** 容納允許存取商業性雲端服務 (商業 Office 365、Google G 套件、Amazon Web 服務等的要求 ) </span><span class="sxs-lookup"><span data-stu-id="24dd0-133">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="24dd0-134">當 Microsoft 收到並核准您的要求之後，會有為期三周的 SLA 可供實施，而且無法加速。</span><span class="sxs-lookup"><span data-stu-id="24dd0-134">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="24dd0-135">當我們收到您的要求時，您將會收到初始認可，並在完成後確認最後的確認。</span><span class="sxs-lookup"><span data-stu-id="24dd0-135">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgment once it has been completed.</span></span>
