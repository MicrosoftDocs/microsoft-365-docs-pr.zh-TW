---
title: 外洩通知
description: Microsoft 服務如何防止個人資料外洩，以及若發生外洩 Microsoft 會如何回應和通知您。
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: ffd5bd81542e2d39a928789c8575178c1b9a7633
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594423"
---
# <a name="gdpr-breach-notification"></a><span data-ttu-id="fcff0-104">GDPR 外洩通知</span><span class="sxs-lookup"><span data-stu-id="fcff0-104">GDPR Breach Notification</span></span>

<span data-ttu-id="fcff0-105">針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處。</span><span class="sxs-lookup"><span data-stu-id="fcff0-105">The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located.</span></span> <span data-ttu-id="fcff0-106">您可以在 [GDPR 摘要主題](gdpr.md)中找到其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="fcff0-106">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrZgG] 

<span data-ttu-id="fcff0-107">本文件會引導您了解依據 GDPR 使用 Microsoft 產品和服務時，完成外洩通知的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fcff0-107">This document leads you to information on the completion of Breach Notifications under the GDPR using Microsoft products and services.</span></span>

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a><span data-ttu-id="fcff0-108">GDPR 規定的個人資料是由什麼所構成？</span><span class="sxs-lookup"><span data-stu-id="fcff0-108">What constitute a breach of personal data under the GDPR?</span></span>

<span data-ttu-id="fcff0-109">個人資料表示與個人相關的任何資訊，可用來直接或間接識別他們。</span><span class="sxs-lookup"><span data-stu-id="fcff0-109">Personal data means any information related to an individual that can be used to identify them directly or indirectly.</span></span> <span data-ttu-id="fcff0-110">個人資料外洩是「導致意外或非法損毀、遺失、變更、未經授權洩漏或存取所傳輸、儲存或處理的個人資料之安全性缺口。</span><span class="sxs-lookup"><span data-stu-id="fcff0-110">A personal data breach is “a breach of security leading to the accidental or unlawful destruction, loss, alteration, unauthorized disclosure of, or access to, personal data transmitted, stored, or otherwise processed.</span></span>

## <a name="terminology"></a><span data-ttu-id="fcff0-111">術語</span><span class="sxs-lookup"><span data-stu-id="fcff0-111">Terminology</span></span>

<span data-ttu-id="fcff0-112">本文件中使用的 GDPR 術語的實用定義：</span><span class="sxs-lookup"><span data-stu-id="fcff0-112">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="fcff0-113">資料控制者 (控制者)\*\*：法律人員、公開授權單位、公司或其他實體，不論單獨或聯合其他單位，會決定個人資料處理方式的用途及方式。</span><span class="sxs-lookup"><span data-stu-id="fcff0-113">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="fcff0-114">個人資料\*\* 和資料主體\*\*：與已識別或可識別的自然人 (資料主體) 相關的任何資訊；可識別的自然人為可直接或間接識別的個人。</span><span class="sxs-lookup"><span data-stu-id="fcff0-114">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="fcff0-115">處理者：\*\* 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。</span><span class="sxs-lookup"><span data-stu-id="fcff0-115">*Processor*: A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="fcff0-116">客戶資料：\*\* 在公司運作的日常作業中產生並儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="fcff0-116">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="microsoft-and-breach-notification"></a><span data-ttu-id="fcff0-117">Microsoft 與外洩通知</span><span class="sxs-lookup"><span data-stu-id="fcff0-117">Microsoft and Breach Notification</span></span>

<span data-ttu-id="fcff0-118">Microsoft 很認真看待其在一般資料保護規定 (GDPR) 下所需承擔的責任。</span><span class="sxs-lookup"><span data-stu-id="fcff0-118">Microsoft takes its obligations under the General Data Protection Regulation (GDPR) seriously.</span></span> <span data-ttu-id="fcff0-119">安全性事件/資料外洩是指例如非法存取客戶儲存在 Microsoft 設備上或 Microsoft 設施中資料的事件，或未經授權存取而可能導致客戶資料遺失、揭露或變更的事件。</span><span class="sxs-lookup"><span data-stu-id="fcff0-119">A security incident/data breach refers to events such as unlawful access to customer’s data stored on Microsoft equipment or in Microsoft facilities, or unauthorized access to such that has the potential to result in the loss, disclosure, or alteration of customer data.</span></span>

<span data-ttu-id="fcff0-120">身為資料處理者，Microsoft 確保服務客戶能夠符合與資料控制者一樣的 GDPR 外洩通知需求。</span><span class="sxs-lookup"><span data-stu-id="fcff0-120">As a data processor, Microsoft ensures that service customers are able to meet the GDPR’s breach notification requirements as data controllers.</span></span> <span data-ttu-id="fcff0-121">我們的通知提供進行該評估所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="fcff0-121">Our notification provides the information needed to make that assessment.</span></span> <span data-ttu-id="fcff0-122">Microsoft 會在有任何個人資料外洩時通知客戶，除了個人資料經確認為無法辨識的情況 (例如，已確認其金鑰完整性的強式加密資料)。</span><span class="sxs-lookup"><span data-stu-id="fcff0-122">Microsoft notifies customers of any personal data breach, except for those cases where personal data is confirmed to be unintelligible (for example, strongly encrypted data where integrity of the keys is confirmed).</span></span>

<span data-ttu-id="fcff0-123">資料控制者負責評估資料隱私權的風險，並且決定外洩時是否需要客戶 DPA 的通知。</span><span class="sxs-lookup"><span data-stu-id="fcff0-123">Data controllers are responsible for assessing risks to data privacy and determining whether a breach requires notification of a customer’s DPA.</span></span> <span data-ttu-id="fcff0-124">Microsoft 伴隨您的 GDPR 合規性原則提供需要的通知，以進行該評估。</span><span class="sxs-lookup"><span data-stu-id="fcff0-124">Microsoft provides the information needed, along with your GDPR compliance policy, to make that assessment.</span></span>

<span data-ttu-id="fcff0-125">初始通知包含外洩本質、大致使用者影響及風險降低步驟 (如果有的話) 的描述。</span><span class="sxs-lookup"><span data-stu-id="fcff0-125">Initial notification includes a description of the nature of the breach, approximate user impact, and mitigation steps (if applicable).</span></span> <span data-ttu-id="fcff0-126">如果我們的調查在初始通知時不完整，我們會指出後續通訊的後續步驟和時間表。</span><span class="sxs-lookup"><span data-stu-id="fcff0-126">If our investigation is not complete at the time of initial notification, we will indicate next steps and timelines for subsequent communication.</span></span> <span data-ttu-id="fcff0-127">如需 Microsoft 如何偵測及回應個人資料外洩的詳細資訊，請參閱服務信任入口網站中的 [GDPR 規定的資料外泄通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)。</span><span class="sxs-lookup"><span data-stu-id="fcff0-127">For more information about how Microsoft detects and responds to a breach of personal data, see [Data Breach Notification Under the GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) in the Service Trust Portal.</span></span>

<span data-ttu-id="fcff0-128">特定 Microsoft 產品和服務外洩通知相關的詳細資料如下所示。</span><span class="sxs-lookup"><span data-stu-id="fcff0-128">Details regarding breach notification for specific Microsoft products and services is given below.</span></span>
  
1. <span data-ttu-id="fcff0-129">**[Office 365](gdpr-breach-Office365.md)**</span><span class="sxs-lookup"><span data-stu-id="fcff0-129">**[Office 365](gdpr-breach-Office365.md)**</span></span>  
    <span data-ttu-id="fcff0-130">Microsoft 在系統、處理程序及人員上花費許多心思，為求降低個人資料外洩的可能性，以及在資料外洩發生時進行快速偵測，並降低其造成的傷害。</span><span class="sxs-lookup"><span data-stu-id="fcff0-130">Microsoft invests extensively in systems, processes, and personnel to reduce the likelihood of personal data breach and to quickly detect and mitigate consequence of breach if it does occur.</span></span> <span data-ttu-id="fcff0-131">其他詳細資料請參閱 [Office 365 在資料安全性中的投資](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security)。</span><span class="sxs-lookup"><span data-stu-id="fcff0-131">Additional details can be read at [Office 365 Investments in Data Security](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security).</span></span>

    <span data-ttu-id="fcff0-132">客戶可能發現外洩，而且想要連絡 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="fcff0-132">A customer may become aware of a breach and wish to contact Microsoft.</span></span> <span data-ttu-id="fcff0-133">在此情況下，請通知 Microsoft 支援服務，然後與工程小組接洽以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fcff0-133">In this case, notify Microsoft Support, which will then interface with engineering teams for more information.</span></span>

2. <span data-ttu-id="fcff0-134">**[Azure 與 Dynamics 365](gdpr-breach-azure-dynamics.md)**</span><span class="sxs-lookup"><span data-stu-id="fcff0-134">**[Azure & Dynamics 365](gdpr-breach-azure-dynamics.md)**</span></span>  
    <span data-ttu-id="fcff0-135">Microsoft 有全球全年無休的事件回應服務，降低對於 Microsoft Azure 與 Dynamics 365 攻擊的風險。</span><span class="sxs-lookup"><span data-stu-id="fcff0-135">Microsoft has a global, 24x7 incident response service that works to mitigate the effects of attacks against Microsoft Azure and Dynamics 365.</span></span>

    - <span data-ttu-id="fcff0-136">*外洩偵測*：因為 Microsoft 和客戶都有維護安全性的義務，因此 Azure 服務使用共用模型來定義安全性與操作的責任。</span><span class="sxs-lookup"><span data-stu-id="fcff0-136">*Detection of Breaches*: Since both Microsoft and the customer have security obligations, Azure services employ a shared responsibility model to define security and operational accountabilities.</span></span> <span data-ttu-id="fcff0-137">Microsoft 不會監視或回應客戶責任範圍內的安全性事件。</span><span class="sxs-lookup"><span data-stu-id="fcff0-137">Microsoft does not monitor or respond to security incidents within the customer’s realm of responsibility.</span></span> <span data-ttu-id="fcff0-138">客戶事件回應可能會牽涉到與 Azure[客戶支援](https://azure.microsoft.com/support/options/)共同作業，前提是有適當的服務合約。</span><span class="sxs-lookup"><span data-stu-id="fcff0-138">Customer incident response may involve collaboration with Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts.</span></span> <span data-ttu-id="fcff0-139">Microsoft Azure 也提供各種不同的服務 (例如，[Azure 資訊安全中心](https://azure.microsoft.com/services/security-center/))，客戶可以用來開發和管理安全性事件回應。</span><span class="sxs-lookup"><span data-stu-id="fcff0-139">Microsoft Azure also offers various services (for example, [Azure Security Center](https://azure.microsoft.com/services/security-center/)) that customers can utilize for developing and managing security incident response.</span></span>

        <span data-ttu-id="fcff0-140">如需 Microsoft Azure 中觸發外洩調查的事件清單，請參閱[偵測潛在缺口](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches)。</span><span class="sxs-lookup"><span data-stu-id="fcff0-140">For a list of events that trigger a breach investigation in Microsoft Azure, see [Detection of Potential Breaches](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches).</span></span> <span data-ttu-id="fcff0-141">[GDPR 規定的 Azure 和外洩通知](gdpr-breach-azure-dynamics.md)進一步詳述 Microsoft 在 Azure 中調查、管理以及回應安全性事件的方式。</span><span class="sxs-lookup"><span data-stu-id="fcff0-141">[Azure and Breach Notification under the GDPR](gdpr-breach-azure-dynamics.md) further details how Microsoft investigates, manages, and responds to security incidents within Azure.</span></span>

    - <span data-ttu-id="fcff0-142">資料外洩回應\*\*：Microsoft 藉由調查事件的功能影響、恢復能力和資訊影響，決定外洩的適當優先順序和嚴重性層級。</span><span class="sxs-lookup"><span data-stu-id="fcff0-142">*Data Breach Response*: Microsoft determines appropriate priority and severity levels of a breach by investigating the functional impact, recoverability, and information impact of the incident.</span></span> <span data-ttu-id="fcff0-143">優先順序和嚴重性可能會隨著調查的進行，根據新的發現結果和結論而變更。</span><span class="sxs-lookup"><span data-stu-id="fcff0-143">Priority and severity may change over the course of the investigation, based on new findings and conclusions.</span></span>
    <span data-ttu-id="fcff0-144">Microsoft 安全性回應小組與全球法律顧問密切合作，以協助確保該鑑識是根據法律義務和對客戶的承諾來執行。</span><span class="sxs-lookup"><span data-stu-id="fcff0-144">Microsoft’s security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers.</span></span> <span data-ttu-id="fcff0-145">這些程序於 [Azure 的資料外洩回應](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response)中詳述。</span><span class="sxs-lookup"><span data-stu-id="fcff0-145">These processes are detailed in [Azure’s Data Breach Response](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response).</span></span>

    - <span data-ttu-id="fcff0-146">客戶通知\*\*：Microsoft Azure 視需要通知客戶和監管單位有資料外洩。</span><span class="sxs-lookup"><span data-stu-id="fcff0-146">*Customer Notification*: Microsoft Azure notifies customers and regulatory authorities of data breaches as required.</span></span> <span data-ttu-id="fcff0-147">客戶通知會在我們宣告外洩的 72 小時內傳遞，除了下列情況：</span><span class="sxs-lookup"><span data-stu-id="fcff0-147">Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances:</span></span>

        - <span data-ttu-id="fcff0-148">Microsoft 相信執行通知的動作會增加其他客戶的風險。</span><span class="sxs-lookup"><span data-stu-id="fcff0-148">Microsoft believes the act of performing a notification increases the risk to other customers.</span></span>
        - <span data-ttu-id="fcff0-149">72 小時的時間表可能會讓某些事件詳細資料可供使用。</span><span class="sxs-lookup"><span data-stu-id="fcff0-149">The 72-hour timeline may leave some incident details available.</span></span> <span data-ttu-id="fcff0-150">這些資訊會隨著調查進行提供給您。</span><span class="sxs-lookup"><span data-stu-id="fcff0-150">These will be provided to you as the investigation proceeds.</span></span>

        <span data-ttu-id="fcff0-151">如需進一步的詳細資料，請參閱[客戶通知](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification)。</span><span class="sxs-lookup"><span data-stu-id="fcff0-151">Further details can be found in [Customer Notification](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification).</span></span>

3. <span data-ttu-id="fcff0-152">**[Microsoft 支援服務與專業服務](gdpr-breach-Microsoft-Support-Professional-Services.md)**</span><span class="sxs-lookup"><span data-stu-id="fcff0-152">**[Microsoft Support and Professional Services](gdpr-breach-Microsoft-Support-Professional-Services.md)**</span></span>  
    <span data-ttu-id="fcff0-153">專業服務的本質表示某些資料保護事件可能會落在客戶的責任範圍。</span><span class="sxs-lookup"><span data-stu-id="fcff0-153">The nature of professional services means that some data protection incidents may fall within the customer’s realm of responsibility.</span></span> <span data-ttu-id="fcff0-154">Microsoft 專業服務發現資料保護事件時，它會遵循如[資料保護事件回應程序的範圍與限制](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process)中所述的記載業界標準回應計劃。</span><span class="sxs-lookup"><span data-stu-id="fcff0-154">When Microsoft Professional Services identifies a data protection incident, it follows documented industry standard response plan as outlined in [Scope & Limits of Data Protection Incident Response Process](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process).</span></span>

## <a name="learn-more"></a><span data-ttu-id="fcff0-155">深入了解</span><span class="sxs-lookup"><span data-stu-id="fcff0-155">Learn more</span></span>

- [<span data-ttu-id="fcff0-156">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="fcff0-156">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
