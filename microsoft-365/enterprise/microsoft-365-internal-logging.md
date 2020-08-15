---
title: Microsoft 365 工程的 microsoft 365 內部記錄
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，將尋找 Microsoft 365 工程小組內部記錄運作方式的說明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b4c4b1db876a6b68ec852adbbd51afe7386a1855
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695625"
---
# <a name="internal-logging-for-microsoft-365-engineering"></a><span data-ttu-id="59124-103">Microsoft 365 工程的內部記錄</span><span class="sxs-lookup"><span data-stu-id="59124-103">Internal logging for Microsoft 365 engineering</span></span>

<span data-ttu-id="59124-104">除了可供客戶使用的事件和記錄資料之外，microsoft 的 Microsoft 365 工程師也可使用內部記錄資料收集系統。</span><span class="sxs-lookup"><span data-stu-id="59124-104">In addition to the events and log data available for customers, there is also an internal log data collection system that is available to Microsoft 365 engineers at Microsoft.</span></span> <span data-ttu-id="59124-105">許多不同類型的記錄資料會從 Microsoft 365 伺服器上傳至內部的大型資料計算服務，稱為 Cosmos。</span><span class="sxs-lookup"><span data-stu-id="59124-105">Many different types of log data are uploaded from Microsoft 365 servers to an internal, big data computing service called Cosmos.</span></span> <span data-ttu-id="59124-106">每個服務小組都會將審核記錄從各自的伺服器上傳至 Cosmos 資料庫，以進行匯總和分析。</span><span class="sxs-lookup"><span data-stu-id="59124-106">Each service team uploads audit logs from their respective servers into the Cosmos database for aggregation and analysis.</span></span> <span data-ttu-id="59124-107">使用稱為 Office Data Loader (ODL) 的專屬自動化工具，在特別認可的埠和通訊協定上，會透過 FIPS 140-2 驗證的 TLS 連線進行此資料傳輸。</span><span class="sxs-lookup"><span data-stu-id="59124-107">This data transfer occurs over a FIPS 140-2-validated TLS connection on specifically approved ports and protocols using a proprietary automation tool called the Office Data Loader (ODL).</span></span> <span data-ttu-id="59124-108">Microsoft 365 中用來收集和處理審計記錄的工具不允許對原始的審計記錄內容或時間順序進行永久或不可逆的變更。</span><span class="sxs-lookup"><span data-stu-id="59124-108">The tools used in Microsoft 365 to collect and process audit records do not allow permanent or irreversible changes to the original audit record content or time ordering.</span></span>

<span data-ttu-id="59124-109">服務小組使用 Cosmos 做為集中式存放庫，進行應用程式使用方式的分析，以測量系統和操作效能，並尋找可能表示問題或安全性問題的 abnormalities 和模式。</span><span class="sxs-lookup"><span data-stu-id="59124-109">Service teams use Cosmos as a centralized repository to conduct an analysis of application usage, to measure system and operational performance, and to look for abnormalities and patterns that may indicate problems or security issues.</span></span> <span data-ttu-id="59124-110">每個服務小組會根據要分析的內容，將記錄的基準上傳至 Cosmos，這通常包括：</span><span class="sxs-lookup"><span data-stu-id="59124-110">Each service team uploads a baseline of logs into Cosmos, depending on what they are looking to analyze, that often include:</span></span>

- <span data-ttu-id="59124-111">事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="59124-111">Event logs</span></span>
- <span data-ttu-id="59124-112">AppLocker 記錄</span><span class="sxs-lookup"><span data-stu-id="59124-112">AppLocker logs</span></span>
- <span data-ttu-id="59124-113">效能資料</span><span class="sxs-lookup"><span data-stu-id="59124-113">Performance data</span></span>
- <span data-ttu-id="59124-114">System Center 資料</span><span class="sxs-lookup"><span data-stu-id="59124-114">System Center data</span></span>
- <span data-ttu-id="59124-115">詳細通話記錄</span><span class="sxs-lookup"><span data-stu-id="59124-115">Call detail records</span></span>
- <span data-ttu-id="59124-116">經驗品質資料</span><span class="sxs-lookup"><span data-stu-id="59124-116">Quality of experience data</span></span>
- <span data-ttu-id="59124-117">IIS 網頁伺服器記錄檔</span><span class="sxs-lookup"><span data-stu-id="59124-117">IIS Web Server logs</span></span>
- <span data-ttu-id="59124-118">SQL Server 記錄檔</span><span class="sxs-lookup"><span data-stu-id="59124-118">SQL Server logs</span></span>
- <span data-ttu-id="59124-119">Syslog 資料</span><span class="sxs-lookup"><span data-stu-id="59124-119">Syslog data</span></span>
- <span data-ttu-id="59124-120">安全性審核記錄檔</span><span class="sxs-lookup"><span data-stu-id="59124-120">Security audit logs</span></span>

<span data-ttu-id="59124-121">在將資料上傳至 Cosmos 之前，ODL 應用程式會使用清理服務，以模糊顯示任何包含客戶資料的欄位（如租使用者資訊和使用者身分識別資訊），並以雜湊值取代這些欄位。</span><span class="sxs-lookup"><span data-stu-id="59124-121">Prior to uploading data into Cosmos, the ODL application uses a scrubbing service to obfuscate any fields that contain customer data, such as tenant information and end-user identifiable information, and replace those fields with a hash value.</span></span> <span data-ttu-id="59124-122">匿名和雜湊記錄會重新寫入並上傳至 Cosmos。</span><span class="sxs-lookup"><span data-stu-id="59124-122">The anonymized and hashed logs are rewritten and then uploaded into Cosmos.</span></span> <span data-ttu-id="59124-123">服務小組對 Cosmos 中的資料執行關聯、警示及報告等範圍的查詢。</span><span class="sxs-lookup"><span data-stu-id="59124-123">Service teams run scoped queries against their data in Cosmos for correlation, alerting, and reporting.</span></span> <span data-ttu-id="59124-124">Cosmos 中的審計記錄資料保留期間是由服務小組決定。大多數的審計記錄資料會保留90天或更長的時間，以支援安全性事件調查，並符合法規保留要求。</span><span class="sxs-lookup"><span data-stu-id="59124-124">The period of audit log data retention in Cosmos is determined by the service teams; most audit log data is retained for 90 days or longer to support security incident investigations and to meet regulatory retention requirements.</span></span>

<span data-ttu-id="59124-125">存取儲存在 Cosmos 中的 Microsoft 365 資料會限制在授權的人員。</span><span class="sxs-lookup"><span data-stu-id="59124-125">Access to Microsoft 365 data stored in Cosmos is restricted to authorized personnel.</span></span> <span data-ttu-id="59124-126">Microsoft 會將審計功能的管理限制于負責審計功能的服務小組成員的有限子集。</span><span class="sxs-lookup"><span data-stu-id="59124-126">Microsoft restricts the management of audit functionality to the limited subset of service team members that are responsible for audit functionality.</span></span> <span data-ttu-id="59124-127">這些小組成員無法修改或刪除 Cosmos 中的資料，而且會記錄及審核 Cosmos 之記錄機制的所有變更。</span><span class="sxs-lookup"><span data-stu-id="59124-127">These team members do not have the ability to modify or delete data from Cosmos, and all changes to logging mechanisms for Cosmos are recorded and audited.</span></span>

<span data-ttu-id="59124-128">每個服務小組會透過授權某些應用程式來執行特定分析，存取其記錄資料以進行分析。</span><span class="sxs-lookup"><span data-stu-id="59124-128">Each service team accesses its log data for analysis by authorizing certain applications to conduct specific analysis.</span></span> <span data-ttu-id="59124-129">例如，Microsoft 365 安全小組會透過專有的事件記錄分析程式使用來自 Cosmos 的資料，以在 Microsoft 365 實際執行環境中關聯、警示及產生可操作的報告，以進行可能的可疑活動。</span><span class="sxs-lookup"><span data-stu-id="59124-129">For example, the Microsoft 365 Security team uses data from Cosmos through a proprietary event log parser to correlate, alert, and generate actionable reports on possible suspicious activity in the Microsoft 365 production environment.</span></span> <span data-ttu-id="59124-130">這些資料中的報告是用來修正漏洞，以及改善服務的整體效能。</span><span class="sxs-lookup"><span data-stu-id="59124-130">The reports from this data are used to correct vulnerabilities, and to improve the overall performance of the service.</span></span> <span data-ttu-id="59124-131">如果特定警示或報告需要進一步調查，服務人員可以要求將資料匯入回 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="59124-131">If a specific alert or report requires further investigation, service personnel can request that data be imported back into the Microsoft 365 service.</span></span> <span data-ttu-id="59124-132">因為從 Cosmos 匯入的特定記錄是在加密的，而服務人員卻沒有解密金鑰的存取權，所以目標記錄會以程式設計方式傳遞，該解密服務會將範圍的結果傳回至授權服務人員。</span><span class="sxs-lookup"><span data-stu-id="59124-132">Since the specific log being imported from Cosmos is in encrypted and service personnel do not have access to decryption keys, the target log is programmatically passed through a decryption service that returns scoped results to the authorized service personnel.</span></span> <span data-ttu-id="59124-133">在此練習中找到的任何弱點，都是透過 Microsoft 的標準安全性事件管理通道來報告及上報。</span><span class="sxs-lookup"><span data-stu-id="59124-133">Any vulnerabilities found from this exercise are reported and escalated using Microsoft's standard security incident management channels.</span></span>
