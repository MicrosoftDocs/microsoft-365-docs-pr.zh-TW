---
title: 資料保護影響評估
description: 這些文件提供資料控制者資訊，協助他們判斷是否需要 DPIA，以及若需要，應包含哪些詳細資料。
keywords: 資料保護影響評估, DPIA, Dynamics 365, Microsoft Professional Services, Microsoft 365, Microsoft 365 文件, GDPR
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
ms.openlocfilehash: 21bda86075b2ab1e542e482e8c0a1edee640035e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558073"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a><span data-ttu-id="98eba-104">GDPR 資料保護影響評估</span><span class="sxs-lookup"><span data-stu-id="98eba-104">Data Protection Impact Assessment for the GDPR</span></span>

<span data-ttu-id="98eba-105">針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處都必須遵守。</span><span class="sxs-lookup"><span data-stu-id="98eba-105">The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located.</span></span> <span data-ttu-id="98eba-106">您可以在 [GDPR 摘要主題](gdpr.md)中找到其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="98eba-106">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span> <span data-ttu-id="98eba-107">這份文件將引導您在使用 Microsoft 產品和服務時，取得 GDPR 規定下之資料保護影響評估 (DPIAS) 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="98eba-107">This document guides you to information regarding Data Protection Impact Assessments (DPIAs) under the GDPR when using Microsoft products and services.</span></span>

## <a name="terminology"></a><span data-ttu-id="98eba-108">術語</span><span class="sxs-lookup"><span data-stu-id="98eba-108">Terminology</span></span>

<span data-ttu-id="98eba-109">本文件中使用的 GDPR 術語的實用定義：</span><span class="sxs-lookup"><span data-stu-id="98eba-109">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="98eba-110">資料控制者 (控制者)\*\*：法律人員、公開授權單位、公司或其他實體，不論單獨或聯合其他單位，會決定個人資料處理方式的用途及方式。</span><span class="sxs-lookup"><span data-stu-id="98eba-110">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="98eba-111">個人資料\*\* 和資料主體\*\*：與已識別或可識別的自然人 (資料主體) 相關的任何資訊；可識別的自然人為可直接或間接識別的個人。</span><span class="sxs-lookup"><span data-stu-id="98eba-111">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="98eba-112">處理者：\*\* 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。</span><span class="sxs-lookup"><span data-stu-id="98eba-112">*Processor*: A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="98eba-113">*客戶資料*：在公司運作的日常作業中產生並儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="98eba-113">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dpia"></a><span data-ttu-id="98eba-114">什麼是 DPIA？</span><span class="sxs-lookup"><span data-stu-id="98eba-114">What is a DPIA?</span></span>

<span data-ttu-id="98eba-115">GDPR 需要控制者為「可能導致自然人之權利和自由高風險」的作業準備資料保護影響評估 (DPIA)。</span><span class="sxs-lookup"><span data-stu-id="98eba-115">The GDPR requires controllers to prepare a Data Protection Impact Assessment (DPIA) for operations that are 'likely to result in a high risk to the rights and freedoms of natural persons.'</span></span> <span data-ttu-id="98eba-116">Microsoft 產品和服務中沒有需要 DPIA 建立的項目。</span><span class="sxs-lookup"><span data-stu-id="98eba-116">There is nothing inherent in Microsoft products and services that need the creation of a DPIA.</span></span> <span data-ttu-id="98eba-117">不過由於 Microsoft 產品和服務的高度可自訂性，根據您的 Microsoft 設定之詳細資料可能因此會需要 DPIA。</span><span class="sxs-lookup"><span data-stu-id="98eba-117">However, because Microsoft products and services are highly customizable, a DPIA may be needed depending on the details of your Microsoft configuration.</span></span> <span data-ttu-id="98eba-118">Microsoft 無法控制，並對這些資訊沒有任何了解。</span><span class="sxs-lookup"><span data-stu-id="98eba-118">Microsoft has no control over, and little or no insight into such information.</span></span> <span data-ttu-id="98eba-119">身為資料控制者的您必須決定資料的正確使用。</span><span class="sxs-lookup"><span data-stu-id="98eba-119">You, as a data controller must determine appropriate uses of their data.</span></span>

## <a name="dpia-in-action"></a><span data-ttu-id="98eba-120">DPIA 實際運作方式</span><span class="sxs-lookup"><span data-stu-id="98eba-120">DPIA in Action</span></span>

<span data-ttu-id="98eba-121">DPIA 指導方針適用於 Office 365、Azure、Dynamics 365，和 Microsoft 支援服務及專業服務。</span><span class="sxs-lookup"><span data-stu-id="98eba-121">The DPIA guidance applies to Office 365, Azure, Dynamics 365, and Microsoft Support and Professional Services.</span></span> <span data-ttu-id="98eba-122">指導方針包含考量：</span><span class="sxs-lookup"><span data-stu-id="98eba-122">That guidance includes consideration of:</span></span>

<span data-ttu-id="98eba-123">**何時需要 DPIA？**</span><span class="sxs-lookup"><span data-stu-id="98eba-123">**When is a DPIA needed?**</span></span>

<span data-ttu-id="98eba-124">考慮是否要完成 DPIA 時，應設法解決以下風險因素。</span><span class="sxs-lookup"><span data-stu-id="98eba-124">The risk factors listed below should be addressed when considering whether to complete a DPIA.</span></span> <span data-ttu-id="98eba-125">每個指導方針的第 1 部分可找到其他潛在因素與進一步詳細資料。</span><span class="sxs-lookup"><span data-stu-id="98eba-125">Other potential factors and further details are found in Part 1 of each of the guidelines.</span></span>  

- <span data-ttu-id="98eba-126">基於自動化處理之資料的系統化和廣泛評估。</span><span class="sxs-lookup"><span data-stu-id="98eba-126">A systematic and extensive evaluation of data based on automated processing.</span></span>  
- <span data-ttu-id="98eba-127">處理大規模的特殊類別資料 (顯示唯一識別自然人資訊的資料) 或與刑事定罪和犯罪相關的個人資料。</span><span class="sxs-lookup"><span data-stu-id="98eba-127">Processing on a large scale of special categories of data (data revealing information uniquely identifying a natural person), or of personal data relating to criminal convictions and offenses.</span></span>
- <span data-ttu-id="98eba-128">系統化監視大規模的公開區域。</span><span class="sxs-lookup"><span data-stu-id="98eba-128">Systematic monitoring of a publicly accessible area on a large scale.</span></span>

<span data-ttu-id="98eba-129">GDPR 闡明：「如果處理是有關於個別醫生的病患或其他醫療保健專業人員或律師之客戶的個人資料，則處理個人資料不應視為大規模。</span><span class="sxs-lookup"><span data-stu-id="98eba-129">The GDPR clarifies 'The processing of personal data should not be considered to be on a large scale if the processing concerns personal data from patients or clients by an individual physician, other health care professional, or lawyer.</span></span> <span data-ttu-id="98eba-130">在此類情況下，資料保護影響評估不應強制」。</span><span class="sxs-lookup"><span data-stu-id="98eba-130">In such cases, a data protection impact assessment should not be mandatory.'</span></span>

<span data-ttu-id="98eba-131">**完成 DPIA 的必要項目？**</span><span class="sxs-lookup"><span data-stu-id="98eba-131">**What is required to complete a DPIA?**</span></span>

<span data-ttu-id="98eba-132">根據本指導方針第 2 部分的詳細說明，DPIA 必須提供欲處理作業的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="98eba-132">A DPIA should provide specific information about the intended processing, which is detailed in Part 2 of the guidance.</span></span> <span data-ttu-id="98eba-133">這些資訊包含：</span><span class="sxs-lookup"><span data-stu-id="98eba-133">That information includes:</span></span>

- <span data-ttu-id="98eba-134">評估與 DPIA 目的相關之資料處理的必要性和相稱性。</span><span class="sxs-lookup"><span data-stu-id="98eba-134">Assessment of the necessity, and proportionality of data processing in relation to the purpose of the DPIA.</span></span>  
- <span data-ttu-id="98eba-135">評估自然人的權利和自由風險。</span><span class="sxs-lookup"><span data-stu-id="98eba-135">Assessment of the risks to the rights and freedoms of natural persons.</span></span>
- <span data-ttu-id="98eba-136">意圖解決風險的措施，包含防護措施、安全性措施，和確保個人資料保護並證明遵守 GDPR 的機制。</span><span class="sxs-lookup"><span data-stu-id="98eba-136">Intended measures to address the risks, including safeguards, security measures, and mechanisms to ensure the protection of personal data and demonstrate compliance with the GDPR.</span></span>
- <span data-ttu-id="98eba-137">處理目的</span><span class="sxs-lookup"><span data-stu-id="98eba-137">Purposes of processing</span></span>  
- <span data-ttu-id="98eba-138">處理的個人資料類別</span><span class="sxs-lookup"><span data-stu-id="98eba-138">Categories of personal data processed</span></span>  
- <span data-ttu-id="98eba-139">資料保留</span><span class="sxs-lookup"><span data-stu-id="98eba-139">Data retention</span></span>  
- <span data-ttu-id="98eba-140">個人資料的位置和傳輸</span><span class="sxs-lookup"><span data-stu-id="98eba-140">Location and transfers of personal data</span></span>  
- <span data-ttu-id="98eba-141">與第三方子處理者共用資料</span><span class="sxs-lookup"><span data-stu-id="98eba-141">Data sharing with third-party subprocessors</span></span>  
- <span data-ttu-id="98eba-142">與獨立第三方共用資料</span><span class="sxs-lookup"><span data-stu-id="98eba-142">Data sharing with independent third-parties</span></span>  
- <span data-ttu-id="98eba-143">資料主體權利</span><span class="sxs-lookup"><span data-stu-id="98eba-143">Data subject rights</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="98eba-144">其他考量</span><span class="sxs-lookup"><span data-stu-id="98eba-144">Additional Considerations</span></span>

<span data-ttu-id="98eba-145">以下是可能與您的 Microsoft 實作的特定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="98eba-145">Specific details that may be relevant to your Microsoft implementation are below.</span></span>

- <span data-ttu-id="98eba-146">[Office 365](gdpr-dpia-office365.md)：這份文件適用於 Office 365 應用程式和服務，包含但不限於 Exchange Online、SharePoint Online、Yammer、商務用 Skype 和 Power BI。</span><span class="sxs-lookup"><span data-stu-id="98eba-146">[Office 365](gdpr-dpia-office365.md): This document applies to Office 365 applications and services, including but not limited to Exchange Online, SharePoint Online, Yammer, Skype for Business, and Power BI.</span></span> <span data-ttu-id="98eba-147">如需詳細資訊，請參閱表 [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) 與 [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)。</span><span class="sxs-lookup"><span data-stu-id="98eba-147">Refer to Tables [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) and [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) for more details.</span></span>  
- <span data-ttu-id="98eba-148">[Azure](gdpr-dpia-azure.md)：我們鼓勵客戶與其隱私權主管和法律顧問合作，以確定與使用 Microsoft Azure相關之任何 DPIA 的必要性和內容。</span><span class="sxs-lookup"><span data-stu-id="98eba-148">[Azure](gdpr-dpia-azure.md): Customers are encouraged to work with their privacy officers and legal counsel to determine the necessity and content of any DPIAs related to their use of Microsoft Azure.</span></span>  
- <span data-ttu-id="98eba-149">[Dynamics 365](gdpr-dpia-dynamics.md): DPIA 的內容可能根據您採用的 Dynamics 365 工具而有所不同。</span><span class="sxs-lookup"><span data-stu-id="98eba-149">[Dynamics 365](gdpr-dpia-dynamics.md): The contents of a DPIA may vary according to which Dynamics 365 tools you are employing.</span></span> <span data-ttu-id="98eba-150">如需特定詳細資料，請參閱[第 2 部分：DPIA 的內容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia)。</span><span class="sxs-lookup"><span data-stu-id="98eba-150">For specific details refer to [Part 2 Contents of a DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia).</span></span>
- <span data-ttu-id="98eba-151">[Microsoft 支援服務及專業服務](gdpr-dpia-prof-services.md)：專業服務不會進行特定常式或自動的資料處理，也不會試圖處理特殊類別，或執行促進或需要監管公開資料的任務。</span><span class="sxs-lookup"><span data-stu-id="98eba-151">[Microsoft Support and Professional Services](gdpr-dpia-prof-services.md): Professional Services does not conduct certain routine or automated data processing, nor is it intended to process special categories or perform tasks that facilitate or require monitoring of publicly accessible data.</span></span> <span data-ttu-id="98eba-152">如需詳細資料，請參閱[第 1 部分 – 判斷是否需要 DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed)。</span><span class="sxs-lookup"><span data-stu-id="98eba-152">For details see [Part 1 — Determining Whether a DPIA is needed](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed).</span></span> <span data-ttu-id="98eba-153">在控制者的特定實作與專業服務的使用情況下，控制者必須考慮上述的 DPIA 元素以及其他相關因素。</span><span class="sxs-lookup"><span data-stu-id="98eba-153">Controllers must consider the DPIA elements outlined above, along with any other relevant factors, in the context of the controller’s specific implementations and uses of Professional Services.</span></span> <span data-ttu-id="98eba-154">如需專業服務的詳細資訊，請參閱[第 2 部分：DPIA 的內容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia)。</span><span class="sxs-lookup"><span data-stu-id="98eba-154">For Professional Services information, see [Part 2 — Contents of a DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia).</span></span>

## <a name="learn-more"></a><span data-ttu-id="98eba-155">深入了解</span><span class="sxs-lookup"><span data-stu-id="98eba-155">Learn more</span></span>

- [<span data-ttu-id="98eba-156">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="98eba-156">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
