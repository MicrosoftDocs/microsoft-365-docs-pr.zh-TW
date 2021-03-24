---
title: 瞭解 Microsoft Defender for Endpoint 中的威脅智慧概念
description: 為您的組織建立自訂威脅警示，並瞭解 Microsoft Defender for Endpoint 中威脅情報的概念。
keywords: 威脅情報、警示定義、損等標記、ioc
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
ms.technology: mde
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059303"
---
# <a name="understand-threat-intelligence-concepts"></a><span data-ttu-id="d893f-104">瞭解威脅智慧概念</span><span class="sxs-lookup"><span data-stu-id="d893f-104">Understand threat intelligence concepts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d893f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d893f-105">**Applies to:**</span></span>
- [<span data-ttu-id="d893f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d893f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d893f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d893f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="d893f-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d893f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d893f-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d893f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

<span data-ttu-id="d893f-110">Advanced cybersecurity 攻擊是由多個複雜的惡意事件、屬性和內容資訊所組成。</span><span class="sxs-lookup"><span data-stu-id="d893f-110">Advanced cybersecurity attacks comprise of multiple complex malicious events, attributes, and contextual information.</span></span> <span data-ttu-id="d893f-111">識別和決定哪些活動符合可疑的工作可能是一項挑戰性的工作。</span><span class="sxs-lookup"><span data-stu-id="d893f-111">Identifying and deciding which of these activities qualify as suspicious can be a challenging task.</span></span> <span data-ttu-id="d893f-112">您對您的行業所知之已知屬性和反常活動的知識，都是知道何時將觀測行為視為可疑的情況的基礎。</span><span class="sxs-lookup"><span data-stu-id="d893f-112">Your knowledge of known attributes and abnormal activities specific to your industry is fundamental in knowing when to call an observed behavior as suspicious.</span></span>

<span data-ttu-id="d893f-113">透過 Microsoft Defender for Endpoint，您可以建立自訂威脅警示，可協助您追蹤組織中可能的攻擊活動。</span><span class="sxs-lookup"><span data-stu-id="d893f-113">With Microsoft Defender for Endpoint, you can create custom threat alerts that can help you keep track of possible attack activities in your organization.</span></span> <span data-ttu-id="d893f-114">您可以標示可疑的事件，將線索放在一起，並可能停止攻擊鏈。</span><span class="sxs-lookup"><span data-stu-id="d893f-114">You can flag suspicious events to piece together clues and possibly stop an attack chain.</span></span> <span data-ttu-id="d893f-115">這些自訂威脅警示只會出現在您的組織中，並會標示您設定它追蹤的事件。</span><span class="sxs-lookup"><span data-stu-id="d893f-115">These custom threat alerts will only appear in your organization and will flag events that you set it to track.</span></span>

<span data-ttu-id="d893f-116">在建立自訂威脅警示之前，請務必瞭解警示定義及威脅 (IOCs) 及其之間的關聯性的概念。</span><span class="sxs-lookup"><span data-stu-id="d893f-116">Before creating custom threat alerts, it's important to know the concepts behind alert definitions and indicators of compromise (IOCs) and the relationship between them.</span></span>

## <a name="alert-definitions"></a><span data-ttu-id="d893f-117">警示定義</span><span class="sxs-lookup"><span data-stu-id="d893f-117">Alert definitions</span></span>
<span data-ttu-id="d893f-118">警示定義是可共同用於識別可能的 cybersecurity 攻擊的早期線索的內容屬性。</span><span class="sxs-lookup"><span data-stu-id="d893f-118">Alert definitions are contextual attributes that can be used collectively to identify early clues on a possible cybersecurity attack.</span></span> <span data-ttu-id="d893f-119">這些指示器通常是攻擊者採取的動作和動作組合，以順利達成攻擊的目標。</span><span class="sxs-lookup"><span data-stu-id="d893f-119">These indicators are typically a combination of activities, characteristics, and actions taken by an attacker to successfully achieve the objective of an attack.</span></span> <span data-ttu-id="d893f-120">監視這些屬性的組合對於在攻擊者的目標達到 vantage 點，並可能影響事件鏈之前很重要。</span><span class="sxs-lookup"><span data-stu-id="d893f-120">Monitoring these combinations of attributes is critical in gaining a vantage point against attacks and possibly interfering with the chain of events before an attacker's objective is reached.</span></span>

## <a name="indicators-of-compromise-ioc"></a><span data-ttu-id="d893f-121"> (IOC 的折衷標記) </span><span class="sxs-lookup"><span data-stu-id="d893f-121">Indicators of compromise (IOC)</span></span>
<span data-ttu-id="d893f-122">IOCs 是個別已知的惡意事件，表示網路或裝置已遭破壞。</span><span class="sxs-lookup"><span data-stu-id="d893f-122">IOCs are individually-known malicious events that indicate that a network or device has already been breached.</span></span> <span data-ttu-id="d893f-123">與警示定義不同的是，這些指示器會被視為遭到破壞的證據。</span><span class="sxs-lookup"><span data-stu-id="d893f-123">Unlike alert definitions, these indicators are considered as evidence of a breach.</span></span> <span data-ttu-id="d893f-124">在攻擊已執行並已到達目標時（例如 exfiltration），通常會出現這種情況。</span><span class="sxs-lookup"><span data-stu-id="d893f-124">They are often seen after an attack has already been carried out and the objective has been reached, such as exfiltration.</span></span> <span data-ttu-id="d893f-125">在取證調查期間，追蹤 IOCs 也很重要。</span><span class="sxs-lookup"><span data-stu-id="d893f-125">Keeping track of IOCs is also important during forensic investigations.</span></span> <span data-ttu-id="d893f-126">雖然它可能無法提供干預攻擊鏈的能力，但收集這些指示器可以在建立更好的防禦，以進行未來的潛在攻擊。</span><span class="sxs-lookup"><span data-stu-id="d893f-126">Although it might not provide the ability to intervene with an attack chain, gathering these indicators can be useful in creating better defenses for possible future attacks.</span></span>

## <a name="relationship-between-alert-definitions-and-iocs"></a><span data-ttu-id="d893f-127">警示定義與 IOCs 之間的關係</span><span class="sxs-lookup"><span data-stu-id="d893f-127">Relationship between alert definitions and IOCs</span></span>
<span data-ttu-id="d893f-128">在 Microsoft Defender for Endpoint 中，警示定義是 IOCs 的容器，它會定義警示，包括在特定 IOC 相符時引發的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="d893f-128">In the context of Microsoft Defender for Endpoint, alert definitions are containers for IOCs and defines the alert, including the metadata that is raised in case of a specific IOC match.</span></span> <span data-ttu-id="d893f-129">各種中繼資料都是以警示定義的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="d893f-129">Various metadata is provided as part of the alert definitions.</span></span> <span data-ttu-id="d893f-130">與其他選項一起提供的中繼資料，例如攻擊、嚴重性和描述的警示定義名稱。</span><span class="sxs-lookup"><span data-stu-id="d893f-130">Metadata such as alert definition name of attack, severity, and description is provided along with other options.</span></span>

<span data-ttu-id="d893f-131">每個 IOC 會根據其類型和值來定義具體偵測邏輯，以及其動作，以判斷其的相符方式。</span><span class="sxs-lookup"><span data-stu-id="d893f-131">Each IOC defines the concrete detection logic based on its type and value as well as its action, which determines how it is matched.</span></span> <span data-ttu-id="d893f-132">它會系結至特定的警示定義，以定義如何在 Microsoft Defender for Endpoint 主控台上顯示偵測通知。</span><span class="sxs-lookup"><span data-stu-id="d893f-132">It is bound to a specific alert definition that defines how a detection is displayed as an alert on the Microsoft Defender for Endpoint console.</span></span>

<span data-ttu-id="d893f-133">以下是 IOC 的範例：</span><span class="sxs-lookup"><span data-stu-id="d893f-133">Here is an example of an IOC:</span></span>
- <span data-ttu-id="d893f-134">類型： Sha1</span><span class="sxs-lookup"><span data-stu-id="d893f-134">Type: Sha1</span></span>
- <span data-ttu-id="d893f-135">值：92cfceb39d57d914ed8b14d0e37643de0797ae56</span><span class="sxs-lookup"><span data-stu-id="d893f-135">Value:  92cfceb39d57d914ed8b14d0e37643de0797ae56</span></span>
- <span data-ttu-id="d893f-136">動作：等於</span><span class="sxs-lookup"><span data-stu-id="d893f-136">Action: Equals</span></span>

<span data-ttu-id="d893f-137">IOCs 具有與警示定義的多對一關聯，讓警示定義可以有許多對應的 IOCs。</span><span class="sxs-lookup"><span data-stu-id="d893f-137">IOCs have a many-to-one relationship with alert definitions such that an alert definition can have many IOCs that correspond to it.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d893f-138">本節內容</span><span class="sxs-lookup"><span data-stu-id="d893f-138">In this section</span></span>

<span data-ttu-id="d893f-139">主題</span><span class="sxs-lookup"><span data-stu-id="d893f-139">Topic</span></span> | <span data-ttu-id="d893f-140">描述</span><span class="sxs-lookup"><span data-stu-id="d893f-140">Description</span></span>
:---|:---
[<span data-ttu-id="d893f-141">向 SIEM 工具提取偵測</span><span class="sxs-lookup"><span data-stu-id="d893f-141">Pull detections to your SIEM tools</span></span>](configure-siem.md)| <span data-ttu-id="d893f-142">深入瞭解提取偵測的不同方式。</span><span class="sxs-lookup"><span data-stu-id="d893f-142">Learn about different ways to pull detections.</span></span>
[<span data-ttu-id="d893f-143">在 Microsoft Defender for Endpoint 中啟用 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="d893f-143">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)| <span data-ttu-id="d893f-144">瞭解如何在入口網站的 [ **設定** ] 頁面中啟用 SIEM 整合功能，讓您可以使用及產生必要的資訊來設定支援的 SIEM 工具。</span><span class="sxs-lookup"><span data-stu-id="d893f-144">Learn about enabling the SIEM integration feature in the **Settings** page in the portal so that you can use and generate the required information to configure supported SIEM tools.</span></span>
[<span data-ttu-id="d893f-145">設定 Splunk 以拉入 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="d893f-145">Configure Splunk to pull Microsoft Defender for Endpoint detections</span></span>](configure-siem.md)| <span data-ttu-id="d893f-146">瞭解如何安裝 REST API 模組化輸入應用程式和其他設定設定，以讓 Splunk 提取 Microsoft Defender for Endpoint 偵測。</span><span class="sxs-lookup"><span data-stu-id="d893f-146">Learn about installing the REST API Modular Input App and other configuration settings to enable Splunk to pull Microsoft Defender for Endpoint detections.</span></span>
[<span data-ttu-id="d893f-147">設定 HP ArcSight 以拉入 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="d893f-147">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)| <span data-ttu-id="d893f-148">瞭解如何安裝 HP ArcSight REST FlexConnector 套件，以及您需要設定 ArcSight 以提取 Microsoft Defender for Endpoint 偵測的檔案。</span><span class="sxs-lookup"><span data-stu-id="d893f-148">Learn about installing the HP ArcSight REST FlexConnector package and the files you need to configure ArcSight to pull Microsoft Defender for Endpoint detections.</span></span>
[<span data-ttu-id="d893f-149">Microsoft Defender for Endpoint 偵測欄位</span><span class="sxs-lookup"><span data-stu-id="d893f-149">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md) | <span data-ttu-id="d893f-150">瞭解哪些資料欄位會公開成為警示 API 的一部分，以及這些欄位如何對應至 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="d893f-150">Understand what data fields are exposed as part of the alerts API and how they map to Microsoft Defender Security Center.</span></span>
[<span data-ttu-id="d893f-151">使用 REST API 提取 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="d893f-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md) | <span data-ttu-id="d893f-152">使用用戶端認證 OAuth 2.0 流程，從使用 REST API 的 Microsoft Defender for Endpoint 提取偵測。</span><span class="sxs-lookup"><span data-stu-id="d893f-152">Use the Client credentials OAuth 2.0 flow to pull detections from Microsoft Defender for Endpoint using REST API.</span></span>
[<span data-ttu-id="d893f-153">疑難排解 SIEM 工具整合問題</span><span class="sxs-lookup"><span data-stu-id="d893f-153">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md) | <span data-ttu-id="d893f-154">解決使用 SIEM 整合功能時可能遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="d893f-154">Address issues you might encounter when using the SIEM integration feature.</span></span>



## <a name="related-topics"></a><span data-ttu-id="d893f-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="d893f-155">Related topics</span></span>
- [<span data-ttu-id="d893f-156">管理指示器</span><span class="sxs-lookup"><span data-stu-id="d893f-156">Manage indicators</span></span>](manage-indicators.md)
