---
title: GDPR 的資料主體要求
description: ''
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: dc4352ac14f42a227f1572b0c7f1442aa4dec838
ms.sourcegitcommit: c201f5cc13d501e5207ebad166e42f90260af0c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2019
ms.locfileid: "35078903"
---
# <a name="data-subject-requests-and-the-gdpr"></a><span data-ttu-id="2f655-103">資料主體要求和 GDPR</span><span class="sxs-lookup"><span data-stu-id="2f655-103">Data Subject Requests for the GDPR</span></span>

<span data-ttu-id="2f655-104">針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處。</span><span class="sxs-lookup"><span data-stu-id="2f655-104">The GDPR introduces new rules for companies, government agencies, non-profits, and other organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents. The GDPR applies no matter where you or your enterprise are located.</span></span> <span data-ttu-id="2f655-105">您可以在 [GDPR 摘要主題](gdpr.md)中找到其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-105">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWs1SI] 

<span data-ttu-id="2f655-106">本文件會引導您了解依據 GDPR 使用 Microsoft 產品和服務時，完成資料主體要求 (DSR) 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2f655-106">This document guides you to information on the completion of Data Subject Requests (DSRs) under the GDPR using Microsoft products and services.</span></span>

- [<span data-ttu-id="2f655-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="2f655-107">Office 365</span></span>](gdpr-dsr-Office365.md)
- [<span data-ttu-id="2f655-108">Azure</span><span class="sxs-lookup"><span data-stu-id="2f655-108">Azure</span></span>](gdpr-dsr-Azure.md)
- [<span data-ttu-id="2f655-109">Intune</span><span class="sxs-lookup"><span data-stu-id="2f655-109">Intune</span></span>](gdpr-dsr-Intune.md)
- [<span data-ttu-id="2f655-110">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2f655-110">Dynamics 365</span></span>](gdpr-dsr-Dynamics365.md)
- [<span data-ttu-id="2f655-111">Visual Studio 系列</span><span class="sxs-lookup"><span data-stu-id="2f655-111">Visual Studio Family</span></span>](gdpr-dsr-visual-studio-family.md)
- [<span data-ttu-id="2f655-112">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="2f655-112">Azure DevOps Services</span></span>](gdpr-dsr-vsts.md)
- [<span data-ttu-id="2f655-113">Microsoft 支援服務與專業服務</span><span class="sxs-lookup"><span data-stu-id="2f655-113">Microsoft Support and Professional Services</span></span>](gdpr-dsr-prof-services.md)

## <a name="terminology"></a><span data-ttu-id="2f655-114">術語</span><span class="sxs-lookup"><span data-stu-id="2f655-114">Terminology</span></span>

<span data-ttu-id="2f655-115">本文件中使用的 GDPR 術語的實用定義：</span><span class="sxs-lookup"><span data-stu-id="2f655-115">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="2f655-116">*資料控制者 (控制者)*：法律人員、公開授權單位、公司或其他實體，不論單獨或聯合其他單位，會決定個人資料處理方式的用途及方式。</span><span class="sxs-lookup"><span data-stu-id="2f655-116">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="2f655-117">*個人資料*和*資料主體*：與已識別或可識別的自然人 (資料主體) 相關的任何資訊；可識別的自然人為可直接或間接識別的個人。</span><span class="sxs-lookup"><span data-stu-id="2f655-117">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="2f655-118">*處理者：* 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。</span><span class="sxs-lookup"><span data-stu-id="2f655-118">*Processor.* A natural or legal person, public authority, agency or other body which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="2f655-119">*客戶資料：* 在公司運作的日常作業中產生並儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-119">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dsr"></a><span data-ttu-id="2f655-120">什麼是 DSR？</span><span class="sxs-lookup"><span data-stu-id="2f655-120">What is a MultiPage?</span></span>

<span data-ttu-id="2f655-121">一般資料保護規定 (GDPR) 賦予人們 (在此法規中稱為資料主體) 權利來管理雇主或其他類型的代理機構或組織 (稱為資料控制者或僅稱為控制者) 所收集的個人資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-121">The General Data Protection Regulation (GDPR) gives rights to people (known in the regulation as data subjects) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the data controller or just controller).</span></span> <span data-ttu-id="2f655-122">GDPR 為資料主體提供其個人資料的特定權限；這些權限包括取得個人資料副本、要求對該資料的變更、限制對該資料的處理、刪除該資料，或是以電子格式接收該資料以移至另一個控制者。</span><span class="sxs-lookup"><span data-stu-id="2f655-122">The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller.</span></span>

<span data-ttu-id="2f655-123">身為控制者的您，有義務盡快考慮每項 DSR，並採取要求的動作來提供實質回應，或針對控制者無法滿足 DSR 的原因進行說明。</span><span class="sxs-lookup"><span data-stu-id="2f655-123">As a controller you are obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller.</span></span> <span data-ttu-id="2f655-124">控制者應向其法律或法務遵循顧問諮詢有關適當處置任何特定 DSR 的方法。</span><span class="sxs-lookup"><span data-stu-id="2f655-124">A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.</span></span>

<span data-ttu-id="2f655-125">受限於組織的 GDPR 符合性規則，完成 DSR 可能涉及數個程序。</span><span class="sxs-lookup"><span data-stu-id="2f655-125">Several processes may be involved completing a DSR, subject to your organization’s GDPR-compliance rules.</span></span>
  
- <span data-ttu-id="2f655-126">**探索**。</span><span class="sxs-lookup"><span data-stu-id="2f655-126">**Discovery mailboxes**</span></span> <span data-ttu-id="2f655-127">決定需要什麼資料才能完成 DSR 的程序。</span><span class="sxs-lookup"><span data-stu-id="2f655-127">The process of determining what data is needed to complete a DSR.</span></span>
- <span data-ttu-id="2f655-128">**存取**。</span><span class="sxs-lookup"><span data-stu-id="2f655-128">Access</span></span> <span data-ttu-id="2f655-129">擷取並可能傳輸給所發現資訊的資料主體。</span><span class="sxs-lookup"><span data-stu-id="2f655-129">Retrieval and potential transmission to the data subject of discovered information.</span></span>
- <span data-ttu-id="2f655-130">**修正**。</span><span class="sxs-lookup"><span data-stu-id="2f655-130">Rectify</span></span> <span data-ttu-id="2f655-131">實作變更或其他要求的個人資料變更。</span><span class="sxs-lookup"><span data-stu-id="2f655-131">Implement changes or other requested personal data changes.</span></span>
- <span data-ttu-id="2f655-132">**限制**。</span><span class="sxs-lookup"><span data-stu-id="2f655-132">Restrict</span></span> <span data-ttu-id="2f655-133">利用限制存取或從 Microsoft 雲端中移除資料來變更存取或個人資料的處理。</span><span class="sxs-lookup"><span data-stu-id="2f655-133">Changing the access or processing of persona data by restricting access, or removing data from the Microsoft cloud.</span></span>
- <span data-ttu-id="2f655-134">**匯出**。</span><span class="sxs-lookup"><span data-stu-id="2f655-134">Export</span></span> <span data-ttu-id="2f655-135">對資料主體提供「結構化、常用、機器可讀取格式」的個人資料，如 GDPR 的「資料可攜帶權」所提供。</span><span class="sxs-lookup"><span data-stu-id="2f655-135">Providing a “structured, commonly used, machine-readable format” of personal data to the data subject, as provided by the GDPR’s “right of data portability.”</span></span>
- <span data-ttu-id="2f655-136">**刪除**。</span><span class="sxs-lookup"><span data-stu-id="2f655-136">**Delete**.</span></span> <span data-ttu-id="2f655-137">從 Microsoft 雲端永久移除個人資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-137">Permanent removal of personal data from the Microsoft cloud.</span></span>

## <a name="specific-dsr-considerations"></a><span data-ttu-id="2f655-138">指定 DSR 考量</span><span class="sxs-lookup"><span data-stu-id="2f655-138">Specific DSR Considerations</span></span>

### <a name="insights-generated-by-microsoft-products-or-services"></a><span data-ttu-id="2f655-139">Microsoft 產品或服務產生的深入資訊</span><span class="sxs-lookup"><span data-stu-id="2f655-139">Insights generated by Microsoft Products or Services</span></span>

<span data-ttu-id="2f655-140">[深入資訊](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)可能由服務 (MyAnalytics 等) 產生。Office 365 包含的線上服務可為其使用其服務的使用者和組織提供深入資訊。</span><span class="sxs-lookup"><span data-stu-id="2f655-140">[Insights](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) may be generated by services (MyAnalytics, etc.) Office 365 includes online services that provide insights to users and organizations that use them.</span></span> <span data-ttu-id="2f655-141">這些服務所產生的資料可能會產生與 DSR 相關的個人資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-141">Data generated by these services may produce personal data relevant to a DSR.</span></span> <span data-ttu-id="2f655-142">請遵循下列連結來取得有關特定服務 DSR 程序的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-142">Follow the link in the list below for details regarding service-specific DSR processes.</span></span>  

### <a name="dsrs-for-system-generated-logs"></a><span data-ttu-id="2f655-143">系統產生的記錄檔的 DSR</span><span class="sxs-lookup"><span data-stu-id="2f655-143">Part 2: Responding to DSRs for system-generated logs</span></span>

<span data-ttu-id="2f655-144">Microsoft 產生的記錄檔和相關資料可能包含依據 GDPR 的「個人資料」定義，被視為個人的資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-144">Logs and related data generated by Microsoft may contain data deemed personal under GDPR's definition of "personal data."</span></span> <span data-ttu-id="2f655-145">不支援限制或修正系統產生的記錄檔中的資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-145">Restricting or rectifying data in system-generated logs is not supported.</span></span> <span data-ttu-id="2f655-146">系統產生的記錄檔中的資料構成了 Microsoft 雲端內所進行的實際動作和診斷資料，修改會危害動作的歷程記錄，並增加詐騙和安全性風險。</span><span class="sxs-lookup"><span data-stu-id="2f655-146">Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.</span></span> <span data-ttu-id="2f655-147">Microsoft 提供存取、匯出和刪除系統產生的記錄檔的功能，這些記錄檔可能是完成 DSR 所需。</span><span class="sxs-lookup"><span data-stu-id="2f655-147">Microsoft provides the ability to access, export, and delete system-generated logs that may be necessary to complete a DSR.</span></span> <span data-ttu-id="2f655-148">這類資料的範例可能包括：</span><span class="sxs-lookup"><span data-stu-id="2f655-148">Examples of such data may include:</span></span>  

- <span data-ttu-id="2f655-149">產品和服務使用情況資料 (例如使用者活動記錄)</span><span class="sxs-lookup"><span data-stu-id="2f655-149">Product and service usage data such as user activity logs</span></span>
- <span data-ttu-id="2f655-150">使用者搜尋要求和查詢資料</span><span class="sxs-lookup"><span data-stu-id="2f655-150">User search requests and query data</span></span>
- <span data-ttu-id="2f655-151">產品和服務透過系統功能和使用者或其他系統的互動產生的資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-151">Data generated by product and services as a product of system functionality and interaction by users or other systems</span></span>  

### <a name="yammer-and-kaizala"></a><span data-ttu-id="2f655-152">Yammer 和 Kaizala</span><span class="sxs-lookup"><span data-stu-id="2f655-152">Yammer and Kaizala</span></span>

<span data-ttu-id="2f655-p112">刪除使用者帳戶不會移除系統為 Yammer 和 Kaizala 所產生的記錄。若要從這些應用程式中移除資料，請參閱以下資訊：</span><span class="sxs-lookup"><span data-stu-id="2f655-p112">Deleting a user’s account will not remove system-generated logs for Yammer and Kaizala. To remove the data from these applications, see one of the following:</span></span>

- [<span data-ttu-id="2f655-155">管理 Yammer Enterprise 中的 GDPR 資料主體要求</span><span class="sxs-lookup"><span data-stu-id="2f655-155">Manage GDPR data subject requests in Yammer Enterprise</span></span>](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [<span data-ttu-id="2f655-156">在 Kaizala 中匯出或刪除使用者的組織資料</span><span class="sxs-lookup"><span data-stu-id="2f655-156">Export or delete a user's organizational data in Kaizala</span></span>](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a><span data-ttu-id="2f655-157">國家/地區雲端</span><span class="sxs-lookup"><span data-stu-id="2f655-157">National clouds</span></span>

<span data-ttu-id="2f655-158">在某些國家/地區的雲端中，全域 IT 系統管理員必須刪除由系統產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="2f655-158">In some national clouds, a global IT Administrator needs to delete system-generated logs.</span></span>

### <a name="microsoft-services"></a><span data-ttu-id="2f655-159">Microsoft 服務</span><span class="sxs-lookup"><span data-stu-id="2f655-159">Microsoft Services</span></span>

<span data-ttu-id="2f655-160">如果您的組織或使用者與 Microsoft 交涉以接收與 Microsoft 產品和服務相關的支援，則此資料中的一部分可能包含個人資料。</span><span class="sxs-lookup"><span data-stu-id="2f655-160">If your organization or users engage with Microsoft to receive,  support related to Microsoft products and services some of this data may contain personal data.</span></span> <span data-ttu-id="2f655-161">如需詳細資訊，請參閱 [GDPR 的 Microsoft 支援服務與專業服務資料主體要求](gdpr-dsr-prof-services.md)。</span><span class="sxs-lookup"><span data-stu-id="2f655-161">Microsoft Support and Professional Services Data Subject Requests for the GDPR</span></span>

### <a name="microsoft-controller-products"></a><span data-ttu-id="2f655-162">Microsoft 控制者產品</span><span class="sxs-lookup"><span data-stu-id="2f655-162">Microsoft Controller Products</span></span>

<span data-ttu-id="2f655-163">在某些情況下，組織的使用者可以存取 Microsoft 為資料控制者的 Microsoft 產品或服務。</span><span class="sxs-lookup"><span data-stu-id="2f655-163">In some circumstances, your organization’s users may access Microsoft products or services for which Microsoft is the data controller.</span></span> <span data-ttu-id="2f655-164">在這些情況下，使用者必須直接向 Microsoft 起始自己的 DSR，而 Microsoft 會直接向使用者履行要求。</span><span class="sxs-lookup"><span data-stu-id="2f655-164">In those cases, your users need to initiate their own DSRs directly to Microsoft, and Microsoft fulfills the requests directly to the user.</span></span>

### <a name="third-party-products"></a><span data-ttu-id="2f655-165">協力廠商產品</span><span class="sxs-lookup"><span data-stu-id="2f655-165">Third-party Products</span></span>

<span data-ttu-id="2f655-166">針對透過 Microsoft 帳戶驗證存取的協力廠商產品和服務，應該將任何資料主體要求導向至適當的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="2f655-166">For third-party products and services accessed through Microsoft account authentication, any data subject requests should be directed to the applicable third party.</span></span>

## <a name="learn-more"></a><span data-ttu-id="2f655-167">深入了解</span><span class="sxs-lookup"><span data-stu-id="2f655-167">Learn more</span></span>

- [<span data-ttu-id="2f655-168">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="2f655-168">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
