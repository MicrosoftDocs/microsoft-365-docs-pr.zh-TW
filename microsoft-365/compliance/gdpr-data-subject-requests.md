---
title: GDPR 和 CCPA 的資料主體要求
description: ''
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: f5ab5230cae7dcc31c487ecbc6a2bbdcbcaaa0dd
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "39268455"
---
# <a name="data-subject-requests-and-the-gdpr-and-ccpa"></a><span data-ttu-id="d32d1-103">GDPR 與 CCPA 和資料主體要求</span><span class="sxs-lookup"><span data-stu-id="d32d1-103">Data Subject Requests and the GDPR and CCPA</span></span>

<span data-ttu-id="d32d1-104">針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處都必須遵守。</span><span class="sxs-lookup"><span data-stu-id="d32d1-104">The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located.</span></span> <span data-ttu-id="d32d1-105">您可以在 [GDPR 摘要主題](gdpr.md)中找到其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-105">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span>

<span data-ttu-id="d32d1-106">同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。</span><span class="sxs-lookup"><span data-stu-id="d32d1-106">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR’s Data Subject Rights, such as the right to delete, access and receive (portability) their personal information.</span></span>  <span data-ttu-id="d32d1-107">CCPA 也提供特定接露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。</span><span class="sxs-lookup"><span data-stu-id="d32d1-107">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and “opt-out/ opt-in” requirements for certain data transfers classified as “sales".</span></span>  <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWs1SI] 

<span data-ttu-id="d32d1-108">本文件會引導您了解依據 GDPR 和 CCPA 使用 Microsoft 產品和服務時，完成資料主體要求 (DSR) 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d32d1-108">This document guides you to information on the completion of Data Subject Requests (DSRs) under the GDPR and CCPA using Microsoft products and services.</span></span>

- [<span data-ttu-id="d32d1-109">Office 365</span><span class="sxs-lookup"><span data-stu-id="d32d1-109">Office 365</span></span>](gdpr-dsr-Office365.md)
- [<span data-ttu-id="d32d1-110">Azure</span><span class="sxs-lookup"><span data-stu-id="d32d1-110">Azure</span></span>](gdpr-dsr-Azure.md)
- [<span data-ttu-id="d32d1-111">Intune</span><span class="sxs-lookup"><span data-stu-id="d32d1-111">Intune</span></span>](gdpr-dsr-Intune.md)
- [<span data-ttu-id="d32d1-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d32d1-112">Dynamics 365</span></span>](gdpr-dsr-Dynamics365.md)
- [<span data-ttu-id="d32d1-113">Visual Studio 系列</span><span class="sxs-lookup"><span data-stu-id="d32d1-113">Visual Studio Family</span></span>](gdpr-dsr-visual-studio-family.md)
- [<span data-ttu-id="d32d1-114">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="d32d1-114">Azure DevOps Services</span></span>](gdpr-dsr-vsts.md)
- [<span data-ttu-id="d32d1-115">Microsoft 支援服務與專業服務</span><span class="sxs-lookup"><span data-stu-id="d32d1-115">Microsoft Support and Professional Services</span></span>](gdpr-dsr-prof-services.md)

## <a name="terminology"></a><span data-ttu-id="d32d1-116">術語</span><span class="sxs-lookup"><span data-stu-id="d32d1-116">Terminology</span></span>

<span data-ttu-id="d32d1-117">本文件中使用的 GDPR 術語的實用定義：</span><span class="sxs-lookup"><span data-stu-id="d32d1-117">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="d32d1-118">資料控制者 (控制者)\*\*：法律人員、公開授權單位、公司或其他實體，不論單獨或聯合其他單位，會決定個人資料處理方式的用途及方式。</span><span class="sxs-lookup"><span data-stu-id="d32d1-118">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="d32d1-119">個人資料\*\* 和資料主體\*\*：與已識別或可識別的自然人 (資料主體) 相關的任何資訊；可識別的自然人為可直接或間接識別的個人。</span><span class="sxs-lookup"><span data-stu-id="d32d1-119">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="d32d1-120">處理者：\*\* 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。</span><span class="sxs-lookup"><span data-stu-id="d32d1-120">*Processor*: A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="d32d1-121">*客戶資料：* 在公司運作的日常作業中產生並儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-121">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dsr"></a><span data-ttu-id="d32d1-122">什麼是 DSR？</span><span class="sxs-lookup"><span data-stu-id="d32d1-122">What is a MultiPage?</span></span>

<span data-ttu-id="d32d1-123">一般資料保護規定 (GDPR) 賦予人們 (在此法規中稱為資料主體) 權利來管理雇主或其他類型的代理機構或組織 (稱為資料控制者或僅稱為控制者) 所收集的個人資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-123">The European Union General Data Protection Regulation (GDPR) gives rights to people (known in the regulation as data subjects) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the data controller or just controller).</span></span> <span data-ttu-id="d32d1-124">GDPR 為資料主體提供其個人資料的特定權限；這些權限包括取得個人資料副本、要求對該資料的變更、限制對該資料的處理、刪除該資料，或是以電子格式接收該資料以移至另一個控制者。</span><span class="sxs-lookup"><span data-stu-id="d32d1-124">The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller.</span></span>

<span data-ttu-id="d32d1-125">加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。</span><span class="sxs-lookup"><span data-stu-id="d32d1-125">California Consumer Privacy Act (CCPA) provides privacy rights and obligations to California consumers, including rights similar to GDPR’s Data Subject Rights, such as the right to delete, access and receive (portability) their personal information.</span></span>  

<span data-ttu-id="d32d1-126">身為控制者的您，有義務盡快考慮每項 DSR，並採取要求的動作來提供實質回應，或針對控制者無法滿足 DSR 的原因進行說明。</span><span class="sxs-lookup"><span data-stu-id="d32d1-126">As a controller you are obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller.</span></span> <span data-ttu-id="d32d1-127">控制者應向其法律或法務遵循顧問諮詢有關適當處置任何特定 DSR 的方法。</span><span class="sxs-lookup"><span data-stu-id="d32d1-127">A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.</span></span>

<span data-ttu-id="d32d1-128">受限於組織的 GDPR 符合性規則，完成 DSR 可能涉及數個程序。</span><span class="sxs-lookup"><span data-stu-id="d32d1-128">Several processes may be involved completing a DSR, subject to your organization’s GDPR-compliance rules.</span></span>
  
- <span data-ttu-id="d32d1-129">**探索**。</span><span class="sxs-lookup"><span data-stu-id="d32d1-129">**Discovery mailboxes**</span></span> <span data-ttu-id="d32d1-130">決定需要什麼資料才能完成 DSR 的程序。</span><span class="sxs-lookup"><span data-stu-id="d32d1-130">The process of determining what data is needed to complete a DSR.</span></span>
- <span data-ttu-id="d32d1-131">**存取**。</span><span class="sxs-lookup"><span data-stu-id="d32d1-131">Access</span></span> <span data-ttu-id="d32d1-132">擷取並可能傳輸給所發現資訊的資料主體。</span><span class="sxs-lookup"><span data-stu-id="d32d1-132">Retrieval and potential transmission to the data subject of discovered information.</span></span>
- <span data-ttu-id="d32d1-133">**修正**。</span><span class="sxs-lookup"><span data-stu-id="d32d1-133">Rectify</span></span> <span data-ttu-id="d32d1-134">實作變更或其他要求的個人資料變更。</span><span class="sxs-lookup"><span data-stu-id="d32d1-134">Implement changes or other requested personal data changes.</span></span>
- <span data-ttu-id="d32d1-135">**限制**。</span><span class="sxs-lookup"><span data-stu-id="d32d1-135">**Restrict**</span></span> <span data-ttu-id="d32d1-136">利用限制存取或從 Microsoft 雲端中移除資料來變更存取或個人資料的處理。</span><span class="sxs-lookup"><span data-stu-id="d32d1-136">Changing the access or processing of persona data by restricting access, or removing data from the Microsoft cloud.</span></span>
- <span data-ttu-id="d32d1-137">**匯出**。</span><span class="sxs-lookup"><span data-stu-id="d32d1-137">**Export**</span></span> <span data-ttu-id="d32d1-138">對資料主體提供「結構化、常用、機器可讀取格式」的個人資料，如 GDPR 的「資料可攜帶權」所提供。</span><span class="sxs-lookup"><span data-stu-id="d32d1-138">Providing a “structured, commonly used, machine-readable format” of personal data to the data subject, as provided by the GDPR’s “right of data portability.”</span></span>
- <span data-ttu-id="d32d1-139">**刪除**。</span><span class="sxs-lookup"><span data-stu-id="d32d1-139">**Delete**.</span></span> <span data-ttu-id="d32d1-140">從 Microsoft 雲端永久移除個人資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-140">Permanent removal of personal data from the Microsoft cloud.</span></span>

## <a name="specific-dsr-considerations"></a><span data-ttu-id="d32d1-141">指定 DSR 考量</span><span class="sxs-lookup"><span data-stu-id="d32d1-141">Specific DSR Considerations</span></span>

### <a name="insights-generated-by-microsoft-products-or-services"></a><span data-ttu-id="d32d1-142">Microsoft 產品或服務產生的深入資訊</span><span class="sxs-lookup"><span data-stu-id="d32d1-142">Insights generated by Microsoft Products or Services</span></span>

<span data-ttu-id="d32d1-143">[深入資訊](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)可能由服務 (MyAnalytics 等) 產生。Office 365 包含的線上服務可為其使用其服務的使用者和組織提供深入資訊。</span><span class="sxs-lookup"><span data-stu-id="d32d1-143">[Insights](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) may be generated by services (MyAnalytics, etc.) Office 365 includes online services that provide insights to users and organizations that use them.</span></span> <span data-ttu-id="d32d1-144">這些服務所產生的資料可能會產生與 DSR 相關的個人資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-144">Data generated by these services may produce personal data relevant to a DSR.</span></span> <span data-ttu-id="d32d1-145">請遵循下列連結來取得有關特定服務 DSR 程序的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-145">Follow the link in the list below for details regarding service-specific DSR processes.</span></span>  

### <a name="dsrs-for-system-generated-logs"></a><span data-ttu-id="d32d1-146">系統產生的記錄檔的 DSR</span><span class="sxs-lookup"><span data-stu-id="d32d1-146">Part 2: Responding to DSRs for system-generated logs</span></span>

<span data-ttu-id="d32d1-147">Microsoft 產生的記錄檔和相關資料可能包含依據 GDPR 的「個人資料」定義，被視為個人的資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-147">Logs and related data generated by Microsoft may contain data deemed personal under GDPR's definition of "personal data."</span></span> <span data-ttu-id="d32d1-148">不支援限制或修正系統產生的記錄檔中的資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-148">Restricting or rectifying data in system-generated logs is not supported.</span></span> <span data-ttu-id="d32d1-149">系統產生的記錄檔中的資料構成了 Microsoft 雲端內所進行的實際動作和診斷資料，修改會危害動作的歷程記錄，並增加詐騙和安全性風險。</span><span class="sxs-lookup"><span data-stu-id="d32d1-149">Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.</span></span> <span data-ttu-id="d32d1-150">Microsoft 提供存取、匯出和刪除系統產生的記錄檔的功能，這些記錄檔可能是完成 DSR 所需。</span><span class="sxs-lookup"><span data-stu-id="d32d1-150">Microsoft provides the ability to access, export, and delete system-generated logs that may be necessary to complete a DSR.</span></span> <span data-ttu-id="d32d1-151">這類資料的範例可能包括：</span><span class="sxs-lookup"><span data-stu-id="d32d1-151">Examples of such data may include:</span></span>  

- <span data-ttu-id="d32d1-152">產品和服務使用情況資料 (例如使用者活動記錄)</span><span class="sxs-lookup"><span data-stu-id="d32d1-152">Product and service usage data such as user activity logs</span></span>
- <span data-ttu-id="d32d1-153">使用者搜尋要求和查詢資料</span><span class="sxs-lookup"><span data-stu-id="d32d1-153">User search requests and query data</span></span>
- <span data-ttu-id="d32d1-154">產品和服務透過系統功能和使用者或其他系統的互動產生的資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-154">Data generated by product and services as a product of system functionality and interaction by users or other systems</span></span>  

### <a name="yammer-and-kaizala"></a><span data-ttu-id="d32d1-155">Yammer 和 Kaizala</span><span class="sxs-lookup"><span data-stu-id="d32d1-155">Yammer and Kaizala</span></span>

<span data-ttu-id="d32d1-p113">刪除使用者帳戶不會移除系統為 Yammer 和 Kaizala 所產生的記錄。若要從這些應用程式中移除資料，請參閱以下資訊：</span><span class="sxs-lookup"><span data-stu-id="d32d1-p113">Deleting a user’s account will not remove system-generated logs for Yammer and Kaizala. To remove the data from these applications, see one of the following:</span></span>

- [<span data-ttu-id="d32d1-158">管理 Yammer Enterprise 中的 GDPR 資料主體要求</span><span class="sxs-lookup"><span data-stu-id="d32d1-158">Manage GDPR data subject requests in Yammer Enterprise</span></span>](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [<span data-ttu-id="d32d1-159">在 Kaizala 中匯出或刪除使用者的組織資料</span><span class="sxs-lookup"><span data-stu-id="d32d1-159">Export or delete a user's organizational data in Kaizala</span></span>](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a><span data-ttu-id="d32d1-160">國家/地區雲端</span><span class="sxs-lookup"><span data-stu-id="d32d1-160">National clouds</span></span>

<span data-ttu-id="d32d1-161">在某些國家/地區的雲端中，全域 IT 系統管理員必須刪除由系統產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d32d1-161">In some national clouds, a global IT Administrator needs to delete system-generated logs.</span></span>

### <a name="microsoft-services"></a><span data-ttu-id="d32d1-162">Microsoft 服務</span><span class="sxs-lookup"><span data-stu-id="d32d1-162">Microsoft Services</span></span>

<span data-ttu-id="d32d1-163">如果您的組織或使用者與 Microsoft 交涉以接收與 Microsoft 產品和服務相關的支援，則此資料中的一部分可能包含個人資料。</span><span class="sxs-lookup"><span data-stu-id="d32d1-163">If your organization or users engage with Microsoft to receive,  support related to Microsoft products and services some of this data may contain personal data.</span></span> <span data-ttu-id="d32d1-164">如需詳細資訊，請參閱 [GDPR 的 Microsoft 支援服務與專業服務資料主體要求](gdpr-dsr-prof-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d32d1-164">Microsoft Support and Professional Services Data Subject Requests for the GDPR</span></span>

### <a name="microsoft-controller-products"></a><span data-ttu-id="d32d1-165">Microsoft 控制者產品</span><span class="sxs-lookup"><span data-stu-id="d32d1-165">Microsoft Controller Products</span></span>

<span data-ttu-id="d32d1-166">在某些情況下，組織的使用者可以存取 Microsoft 為資料控制者的 Microsoft 產品或服務。</span><span class="sxs-lookup"><span data-stu-id="d32d1-166">In some circumstances, your organization’s users may access Microsoft products or services for which Microsoft is the data controller.</span></span> <span data-ttu-id="d32d1-167">在這些情況下，使用者必須直接向 Microsoft 起始自己的 DSR，而 Microsoft 會直接向使用者履行要求。</span><span class="sxs-lookup"><span data-stu-id="d32d1-167">In those cases, your users need to initiate their own DSRs directly to Microsoft, and Microsoft fulfills the requests directly to the user.</span></span>

### <a name="third-party-products"></a><span data-ttu-id="d32d1-168">協力廠商產品</span><span class="sxs-lookup"><span data-stu-id="d32d1-168">Third-party Products</span></span>

<span data-ttu-id="d32d1-169">針對透過 Microsoft 帳戶驗證存取的協力廠商產品和服務，應該將任何資料主體要求導向至適當的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="d32d1-169">For third-party products and services accessed through Microsoft account authentication, any data subject requests should be directed to the applicable third party.</span></span>

## <a name="learn-more"></a><span data-ttu-id="d32d1-170">深入了解</span><span class="sxs-lookup"><span data-stu-id="d32d1-170">Learn more</span></span>

- [<span data-ttu-id="d32d1-171">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="d32d1-171">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
