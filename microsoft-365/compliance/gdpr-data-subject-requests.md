---
title: GDPR 和 CCPA 的資料主體要求
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR, CCPA
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
description: 了解如何使用 Microsoft 產品和服務來完成一般資料保護規定 (GPDR) 和加州消費者隱私法 (CCPA) 底下的 DSR。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a9dc9c390aa912bbbfa433a6c98acc188eb0f024
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417956"
---
# <a name="data-subject-requests-and-the-gdpr-and-ccpa"></a><span data-ttu-id="a92c5-104">GDPR 與 CCPA 和資料主體要求</span><span class="sxs-lookup"><span data-stu-id="a92c5-104">Data Subject Requests and the GDPR and CCPA</span></span>

<span data-ttu-id="a92c5-105">針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處都必須遵守。</span><span class="sxs-lookup"><span data-stu-id="a92c5-105">The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located.</span></span> <span data-ttu-id="a92c5-106">您可以在 [GDPR 摘要主題](gdpr.md)中找到其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-106">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span>

<span data-ttu-id="a92c5-107">同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。</span><span class="sxs-lookup"><span data-stu-id="a92c5-107">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR's Data Subject Rights, such as the right to delete, access, and receive (portability) their personal information.</span></span>  <span data-ttu-id="a92c5-108">CCPA 也提供特定揭露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。</span><span class="sxs-lookup"><span data-stu-id="a92c5-108">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and "opt-out/ opt-in" requirements for certain data transfers classified as "sales".</span></span> <span data-ttu-id="a92c5-109">本文件會引導您了解依據 GDPR 和 CCPA 使用 Microsoft 產品和服務時，完成資料主體要求 (DSR) 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a92c5-109">This document guides you to information on the completion of Data Subject Requests (DSRs) under the GDPR and CCPA using Microsoft products and services.</span></span>

- [<span data-ttu-id="a92c5-110">Office 365</span><span class="sxs-lookup"><span data-stu-id="a92c5-110">Office 365</span></span>](gdpr-dsr-Office365.md)
- [<span data-ttu-id="a92c5-111">Azure</span><span class="sxs-lookup"><span data-stu-id="a92c5-111">Azure</span></span>](gdpr-dsr-Azure.md)
- [<span data-ttu-id="a92c5-112">Intune</span><span class="sxs-lookup"><span data-stu-id="a92c5-112">Intune</span></span>](gdpr-dsr-Intune.md)
- [<span data-ttu-id="a92c5-113">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a92c5-113">Dynamics 365</span></span>](gdpr-dsr-Dynamics365.md)
- [<span data-ttu-id="a92c5-114">Visual Studio 系列</span><span class="sxs-lookup"><span data-stu-id="a92c5-114">Visual Studio Family</span></span>](gdpr-dsr-visual-studio-family.md)
- [<span data-ttu-id="a92c5-115">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="a92c5-115">Azure DevOps Services</span></span>](gdpr-dsr-vsts.md)
- [<span data-ttu-id="a92c5-116">Microsoft 支援服務與專業服務</span><span class="sxs-lookup"><span data-stu-id="a92c5-116">Microsoft Support and Professional Services</span></span>](gdpr-dsr-prof-services.md)

## <a name="terminology"></a><span data-ttu-id="a92c5-117">術語</span><span class="sxs-lookup"><span data-stu-id="a92c5-117">Terminology</span></span>

<span data-ttu-id="a92c5-118">本文件中使用的 GDPR 術語的實用定義：</span><span class="sxs-lookup"><span data-stu-id="a92c5-118">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="a92c5-119">資料控制者 (控制者)\*\*：法律人員、公開授權單位、公司或其他實體，不論單獨或聯合其他單位，會決定個人資料處理方式的用途及方式。</span><span class="sxs-lookup"><span data-stu-id="a92c5-119">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="a92c5-120">個人資料\*\* 和資料主體\*\*：與已識別或可識別的自然人 (資料主體) 相關的任何資訊；可識別的自然人為可直接或間接識別的個人。</span><span class="sxs-lookup"><span data-stu-id="a92c5-120">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="a92c5-121">處理者：\*\* 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。</span><span class="sxs-lookup"><span data-stu-id="a92c5-121">*Processor*: A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="a92c5-122">*客戶資料：* 在公司運作的日常作業中產生並儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-122">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dsr"></a><span data-ttu-id="a92c5-123">什麼是 DSR？</span><span class="sxs-lookup"><span data-stu-id="a92c5-123">What is a DSR?</span></span>

<span data-ttu-id="a92c5-124">一般資料保護規定 (GDPR) 賦予人們 (在此法規中稱為資料主體) 權利來管理雇主或其他類型的代理機構或組織 (稱為資料控制者或僅稱為控制者) 所收集的個人資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-124">The General Data Protection Regulation (GDPR) gives rights to people (known in the regulation as data subjects) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the data controller or just controller).</span></span> <span data-ttu-id="a92c5-125">GDPR 為資料主體提供其個人資料的特定權限；這些權限包括取得個人資料副本、要求對該資料的變更、限制對該資料的處理、刪除該資料，或是以電子格式接收該資料以移至另一個控制者。</span><span class="sxs-lookup"><span data-stu-id="a92c5-125">The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller.</span></span>

<span data-ttu-id="a92c5-126">加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。</span><span class="sxs-lookup"><span data-stu-id="a92c5-126">California Consumer Privacy Act (CCPA) provides privacy rights and obligations to California consumers, including rights similar to GDPR's Data Subject Rights, such as the right to delete, access, and receive (portability) their personal information.</span></span>  

<span data-ttu-id="a92c5-127">身為控制者的您，有義務盡快考慮每項 DSR，並採取要求的動作來提供實質回應，或針對控制者無法滿足 DSR 的原因進行說明。</span><span class="sxs-lookup"><span data-stu-id="a92c5-127">As a controller, you are obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller.</span></span> <span data-ttu-id="a92c5-128">控制者應向其法律或法務遵循顧問諮詢有關適當處置任何特定 DSR 的方法。</span><span class="sxs-lookup"><span data-stu-id="a92c5-128">A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.</span></span>

<span data-ttu-id="a92c5-129">受限於組織的 GDPR 符合性規則，完成 DSR 可能涉及數個程序。</span><span class="sxs-lookup"><span data-stu-id="a92c5-129">Several processes may be involved completing a DSR, subject to your organization's GDPR-compliance rules.</span></span>
  
- <span data-ttu-id="a92c5-130">**探索**。</span><span class="sxs-lookup"><span data-stu-id="a92c5-130">**Discovery**.</span></span> <span data-ttu-id="a92c5-131">決定需要什麼資料才能完成 DSR 的程序。</span><span class="sxs-lookup"><span data-stu-id="a92c5-131">The process of determining what data is needed to complete a DSR.</span></span>
- <span data-ttu-id="a92c5-132">**存取**。</span><span class="sxs-lookup"><span data-stu-id="a92c5-132">**Access**.</span></span> <span data-ttu-id="a92c5-133">擷取並可能傳輸給所發現資訊的資料主體。</span><span class="sxs-lookup"><span data-stu-id="a92c5-133">Retrieval and potential transmission to the data subject of discovered information.</span></span>
- <span data-ttu-id="a92c5-134">**修正**。</span><span class="sxs-lookup"><span data-stu-id="a92c5-134">**Rectify**.</span></span> <span data-ttu-id="a92c5-135">實作變更或其他要求的個人資料變更。</span><span class="sxs-lookup"><span data-stu-id="a92c5-135">Implement changes or other requested personal data changes.</span></span>
- <span data-ttu-id="a92c5-136">**限制**。</span><span class="sxs-lookup"><span data-stu-id="a92c5-136">**Restrict**.</span></span> <span data-ttu-id="a92c5-137">利用限制存取或從 Microsoft 雲端中移除資料來變更存取或個人資料的處理。</span><span class="sxs-lookup"><span data-stu-id="a92c5-137">Changing the access or processing of persona data by restricting access, or removing data from the Microsoft cloud.</span></span>
- <span data-ttu-id="a92c5-138">**匯出**。</span><span class="sxs-lookup"><span data-stu-id="a92c5-138">**Export**.</span></span> <span data-ttu-id="a92c5-139">對資料主體提供「結構化、常用、機器可讀取格式」的個人資料，如 GDPR 的「資料可攜帶權」所提供。</span><span class="sxs-lookup"><span data-stu-id="a92c5-139">Providing a "structured, commonly used, machine-readable format" of personal data to the data subject, as provided by the GDPR's "right of data portability."</span></span>
- <span data-ttu-id="a92c5-140">**刪除**。</span><span class="sxs-lookup"><span data-stu-id="a92c5-140">**Delete**.</span></span> <span data-ttu-id="a92c5-141">從 Microsoft 雲端永久移除個人資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-141">Permanent removal of personal data from the Microsoft cloud.</span></span>

## <a name="specific-dsr-considerations"></a><span data-ttu-id="a92c5-142">指定 DSR 考量</span><span class="sxs-lookup"><span data-stu-id="a92c5-142">Specific DSR Considerations</span></span>

### <a name="insights-generated-by-microsoft-products-or-services"></a><span data-ttu-id="a92c5-143">Microsoft 產品或服務產生的深入資訊</span><span class="sxs-lookup"><span data-stu-id="a92c5-143">Insights generated by Microsoft Products or Services</span></span>

<span data-ttu-id="a92c5-144">[深入資訊](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)可能由服務 (MyAnalytics 等) 產生。Office 365 包含的線上服務可為其使用其服務的使用者和組織提供深入資訊。</span><span class="sxs-lookup"><span data-stu-id="a92c5-144">[Insights](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) may be generated by services (MyAnalytics, etc.) Office 365 includes online services that provide insights to users and organizations that use them.</span></span> <span data-ttu-id="a92c5-145">這些服務所產生的資料可能會產生與 DSR 相關的個人資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-145">Data generated by these services may produce personal data relevant to a DSR.</span></span> <span data-ttu-id="a92c5-146">請遵循下列連結來取得有關特定服務 DSR 程序的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-146">Follow the link in the list below for details regarding service-specific DSR processes.</span></span>  

### <a name="dsrs-for-system-generated-logs"></a><span data-ttu-id="a92c5-147">系統產生的記錄檔的 DSR</span><span class="sxs-lookup"><span data-stu-id="a92c5-147">DSRs for system-generated logs</span></span>

<span data-ttu-id="a92c5-148">Microsoft 產生的記錄檔和相關資料可能包含依據 GDPR 的「個人資料」定義，被視為個人的資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-148">Logs and related data generated by Microsoft may contain data deemed personal under GDPR's definition of "personal data."</span></span> <span data-ttu-id="a92c5-149">不支援限制或修正系統產生的記錄檔中的資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-149">Restricting or rectifying data in system-generated logs is not supported.</span></span> <span data-ttu-id="a92c5-150">系統產生的記錄檔中的資料構成了 Microsoft 雲端內所進行的實際動作和診斷資料，修改會危害動作的歷程記錄，並增加詐騙和安全性風險。</span><span class="sxs-lookup"><span data-stu-id="a92c5-150">Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data; modifications would compromise the historical record of actions and increase fraud and security risks.</span></span> <span data-ttu-id="a92c5-151">Microsoft 提供存取、匯出和刪除系統產生的記錄檔的功能，這些記錄檔可能是完成 DSR 所需。</span><span class="sxs-lookup"><span data-stu-id="a92c5-151">Microsoft provides the ability to access, export, and delete system-generated logs that may be necessary to complete a DSR.</span></span> <span data-ttu-id="a92c5-152">這類資料的範例可能包括：</span><span class="sxs-lookup"><span data-stu-id="a92c5-152">Examples of such data may include:</span></span>  

- <span data-ttu-id="a92c5-153">產品和服務使用情況資料 (例如使用者活動記錄)</span><span class="sxs-lookup"><span data-stu-id="a92c5-153">Product and service usage data such as user activity logs</span></span>
- <span data-ttu-id="a92c5-154">使用者搜尋要求和查詢資料</span><span class="sxs-lookup"><span data-stu-id="a92c5-154">User search requests and query data</span></span>
- <span data-ttu-id="a92c5-155">產品和服務透過系統功能和使用者或其他系統的互動產生的資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-155">Data generated by product and services resulting from system functionality and interaction by users or other systems.</span></span>  

### <a name="yammer-and-kaizala"></a><span data-ttu-id="a92c5-156">Yammer 和 Kaizala</span><span class="sxs-lookup"><span data-stu-id="a92c5-156">Yammer and Kaizala</span></span>

<span data-ttu-id="a92c5-157">刪除使用者的帳戶不會移除系統針對 Yammer 和 Kaizala 產生的記錄。</span><span class="sxs-lookup"><span data-stu-id="a92c5-157">Deleting a user's account will not remove system-generated logs for Yammer and Kaizala.</span></span> <span data-ttu-id="a92c5-158">若要移除這些應用程式中的資料，請參閱下列其中一項資源：</span><span class="sxs-lookup"><span data-stu-id="a92c5-158">To remove the data from these applications, see one of the following resources:</span></span>

- [<span data-ttu-id="a92c5-159">管理 Yammer Enterprise 中的 GDPR 資料主體要求</span><span class="sxs-lookup"><span data-stu-id="a92c5-159">Manage GDPR data subject requests in Yammer Enterprise</span></span>](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [<span data-ttu-id="a92c5-160">在 Kaizala 中匯出或刪除使用者的組織資料</span><span class="sxs-lookup"><span data-stu-id="a92c5-160">Export or delete a user's organizational data in Kaizala</span></span>](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a><span data-ttu-id="a92c5-161">國家/地區雲端</span><span class="sxs-lookup"><span data-stu-id="a92c5-161">National Clouds</span></span>

<span data-ttu-id="a92c5-162">在某些國家/地區的雲端中，全域 IT 系統管理員必須刪除由系統產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a92c5-162">In some national clouds, a global IT Administrator needs to delete system-generated logs.</span></span>

### <a name="microsoft-services"></a><span data-ttu-id="a92c5-163">Microsoft 服務</span><span class="sxs-lookup"><span data-stu-id="a92c5-163">Microsoft Services</span></span>

<span data-ttu-id="a92c5-164">如果您的組織或使用者與 Microsoft 交涉以接收與 Microsoft 產品和服務相關的支援，則此資料中的一部分可能包含個人資料。</span><span class="sxs-lookup"><span data-stu-id="a92c5-164">If your organization or users engage with Microsoft to receive,  support related to Microsoft products and services some of this data may contain personal data.</span></span> <span data-ttu-id="a92c5-165">如需詳細資訊，請參閱 [GDPR 的 Microsoft 支援服務與專業服務資料主體要求](gdpr-dsr-prof-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a92c5-165">For more information, see [Microsoft Support and Professional Services Data Subject Requests for the GDPR](gdpr-dsr-prof-services.md).</span></span>

### <a name="microsoft-controller-products"></a><span data-ttu-id="a92c5-166">Microsoft 控制者產品</span><span class="sxs-lookup"><span data-stu-id="a92c5-166">Microsoft Controller Products</span></span>

<span data-ttu-id="a92c5-167">在某些情況下，組織的使用者可以存取 Microsoft 為資料控制者的 Microsoft 產品或服務。</span><span class="sxs-lookup"><span data-stu-id="a92c5-167">In some circumstances, your organization's users may access Microsoft products or services for which Microsoft is the data controller.</span></span> <span data-ttu-id="a92c5-168">在這些情況下，使用者必須直接向 Microsoft 起始自己的 DSR，而 Microsoft 會直接向使用者履行要求。</span><span class="sxs-lookup"><span data-stu-id="a92c5-168">In those cases, your users need to initiate their own DSRs directly to Microsoft, and Microsoft fulfills the requests directly to the user.</span></span>

### <a name="third-party-products"></a><span data-ttu-id="a92c5-169">協力廠商產品</span><span class="sxs-lookup"><span data-stu-id="a92c5-169">Third-party Products</span></span>

<span data-ttu-id="a92c5-170">針對透過 Microsoft 帳戶驗證存取的協力廠商產品和服務，應該將任何資料主體要求導向至適當的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="a92c5-170">For third-party products and services accessed through Microsoft account authentication, any data subject requests should be directed to the applicable third party.</span></span>

## <a name="data-subject-request-admin-tools"></a><span data-ttu-id="a92c5-171">資料主體要求系統管理工具</span><span class="sxs-lookup"><span data-stu-id="a92c5-171">Data Subject Request admin tools</span></span>

- <span data-ttu-id="a92c5-172">**安全性與合規性中心**：使用者產生的資料是由[安全性與合規性中心](https://aka.ms/stpsecurityandcompliance)匯出，或以應用程式功能匯出。</span><span class="sxs-lookup"><span data-stu-id="a92c5-172">**Security & Compliance Center**: User-generated data is exported by the [Security & Compliance Center](https://aka.ms/stpsecurityandcompliance) or in-application features.</span></span>
- <span data-ttu-id="a92c5-173">**Azure AD 系統管理中心**：使用 [Azure AD 系統管理中心](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/)刪除來自 Azure Active Directory 及相關服務的資料主體。</span><span class="sxs-lookup"><span data-stu-id="a92c5-173">**Azure AD Admin Center**: Delete a data subject from Azure Active Directory and related services using [Azure AD Admin Center](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/).</span></span>
- <span data-ttu-id="a92c5-174">**Microsoft 資料記錄匯出**：租用戶系統管理員可以使用 [Microsoft 資料記錄匯出](https://aka.ms/MicrosoftGDPR)，將系統產生的記錄匯出。</span><span class="sxs-lookup"><span data-stu-id="a92c5-174">**Microsoft Data Log Export**: System-generated logs can be exported by tenant administrators using the [Microsoft Data Log Export](https://aka.ms/MicrosoftGDPR).</span></span>

## <a name="learn-more"></a><span data-ttu-id="a92c5-175">深入了解</span><span class="sxs-lookup"><span data-stu-id="a92c5-175">Learn more</span></span>

- [<span data-ttu-id="a92c5-176">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="a92c5-176">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
