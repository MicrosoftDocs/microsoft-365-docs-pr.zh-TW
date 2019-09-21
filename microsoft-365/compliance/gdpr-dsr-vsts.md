---
title: GDPR 的 Azure DevOps 資料主體要求
keywords: Visual Studio Team Services、VSTS、Azure DevOps 文件、隱私權、GDPR
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: jitojo
ms.author: jominana
manager: douge
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: ce5ccb1961fe1751604b32bb5b37595b0884b395
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071482"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="5b662-103">GDPR 的 Azure DevOps Services 資料主體要求</span><span class="sxs-lookup"><span data-stu-id="5b662-103">Azure DevOps Services Data Subject Requests for the GDPR</span></span>

<span data-ttu-id="5b662-p101">歐盟[一般資料保護規範 (GDPR)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm) 賦予人員 (在規範中稱為「資料主體」**) 權限，以管理由「資料控制者」** 收集而來的個人資料，「資料控制者」(或簡稱「控制者」**) 是雇主或其他類型的公司或組織。個人資料在 GDPR 中的定義很廣泛，係指與已識別或可識別的自然人相關的任何資料。GDPR 賦予資料主體對其個人資料的特定權限，這些權限包括取得個人資料副本、要求更正資料、限制資料的處理、刪除資料或以電子格式接收資料，以便轉交給其他控制者。由資料主體向控制者提出對其個人資料採取某項動作的正式要求，稱為「資料主體要求」** 或 DSR。</span><span class="sxs-lookup"><span data-stu-id="5b662-p101">The European Union [General Data Protection Regulation (GDPR)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people, known in the regulation as *data subjects*, to manage the personal data that's collected by a *data controller*. A data controller, or just *controller*, is an employer or other type of agency or organization. Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data. These rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request*, or DSR.</span></span>

<span data-ttu-id="5b662-110">如需關於 GDPR 的一般資訊，請參閱[服務信任入口網站的 GDPR 區段](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)。</span><span class="sxs-lookup"><span data-stu-id="5b662-110">For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

<span data-ttu-id="5b662-111">本指南將討論如何使用 Microsoft 工具，將 Visual Studio Team Services (先前稱為 Visual Studio Team Services) 的驗證 (登入) 工作階段期間所收集的個人資料匯出或刪除。</span><span class="sxs-lookup"><span data-stu-id="5b662-111">This guide discusses how to use Microsoft tools to export or delete personal data collected during an authenticated (signed-in) session of Azure DevOps Services (formerly known as Visual Studio Team Services).</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="5b662-112">其他隱私權資訊</span><span class="sxs-lookup"><span data-stu-id="5b662-112">Additional privacy information</span></span>

<span data-ttu-id="5b662-113">[Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)、[線上服務條款 (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx)，和 [Microsoft 的 GDPR 承諾](/legal/gdpr)文章描述我們的資料處理做法。</span><span class="sxs-lookup"><span data-stu-id="5b662-113">The [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement), [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx), and [Microsoft's GDPR Commitments](/legal/gdpr) articles describe our data processing practices.</span></span>

## <a name="personal-data-we-collect"></a><span data-ttu-id="5b662-114">我們收集的個人資料</span><span class="sxs-lookup"><span data-stu-id="5b662-114">Personal data we collect</span></span>

<span data-ttu-id="5b662-p102">Microsoft 會向使用者收集資料來運作及改善 Azure DevOps Services。Azure DevOps Services 會收集兩個類型的資料：客戶資料和系統產生的記錄。客戶資料包括 Azure DevOps Services 運作服務所需的使用者識別交易式和互動式資料。系統產生的記錄包含針對每個產品區域和功能所彙總的服務使用狀況資料。</span><span class="sxs-lookup"><span data-stu-id="5b662-p102">Microsoft collects data from users to operate and improve Azure DevOps Services. Azure DevOps Services collects two categories of datacustomer data and system-generated logs. Customer data includes user-identifiable transactional and interactional data that Azure DevOps Services needs to operate the service. System-generated logs include service usage data that is aggregated for each product area and feature.</span></span>

## <a name="delete-azure-devops-data"></a><span data-ttu-id="5b662-119">刪除 Azure DevOps 資料</span><span class="sxs-lookup"><span data-stu-id="5b662-119">Delete Azure DevOps data</span></span>

<span data-ttu-id="5b662-p103">若要刪除相關聯的 Azure DevOps Services 客戶資料，並將系統產生的記錄中找到的個人識別資料匿名化，第一個步驟是關閉您的 Azure Active Directory (AAD) 或 Microsoft 帳戶 (MSA)。會利用嚴格的整合性、追蹤功能與稽核規則，仰賴 Azure DevOps Services 作為記錄的系統。這些現有規範會影響我們刪除及保留 GDPR 的義務。關閉身分識別帳戶並不會修改、移除或變更與 Azure DevOps 組織中個人身分識別相關聯的成品和記錄。我們已確定在刪除整個 Azure DevOps 組織時，該帳戶中找到的所有相關聯個人識別資料和系統產生的記錄都會從我們的系統中移除 (在必要的 Azure DevOps 組織 30 天虛刪除期間結束後)。</span><span class="sxs-lookup"><span data-stu-id="5b662-p103">The first step to delete associated Azure DevOps Services customer data and to anonymize personally identifiable data found in system-generated logs is to close your Azure Active Directory (AAD) identity account or Microsoft Account (MSA). Azure DevOps Services is relied upon as a system of record with strict integrity, traceability, and audit rules. These existing obligations affect our delete and retention obligations for GDPR. Closing the identity account does not alter, remove, or change artifacts and records associated with the individual identity in the Azure DevOps organization. We have ensured that when an entire Azure DevOps organization is deleted, all associated personally identifiable data and system-generated logs found in that organization are removed from our system (after the requisite Azure DevOps organization 30-day soft-delete period).</span></span>

## <a name="export-azure-devops-data"></a><span data-ttu-id="5b662-125">匯出 Azure DevOps 資料</span><span class="sxs-lookup"><span data-stu-id="5b662-125">Export Azure DevOps data</span></span>

<span data-ttu-id="5b662-126">控制者可以藉由兩種方法之一，將向其資料主題收集的客戶資料和系統產生記錄匯出，取決於用來登入 Azure DevOps Services 的身分識別提供者 (MSA 或 AAD) 而定。</span><span class="sxs-lookup"><span data-stu-id="5b662-126">Controllers can export customer data and system-generated logs collected from their data subjects by one of two methods, depending upon the identity provider (MSA or AAD) used to sign in to the Azure DevOps service.</span></span>

- <span data-ttu-id="5b662-127">使用 Azure 租用戶所支援帳戶，例如與 Azure 訂閱相關聯的 AAD 帳戶或 MSA 帳戶的使用者可遵循 [GDPR 的 Azure 資料主體要求](gdpr-dsr-azure.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="5b662-127">Users that authenticate using an account that is backed by an Azure tenant, for example, AAD account or MSA account associated with an Azure subscription, can follow the instructions in [Azure Data Subject Requests for the GDPR](gdpr-dsr-azure.md).</span></span>

- <span data-ttu-id="5b662-p104">使用 MSA 身分識別進行驗證的使用者可以使用這個[隱私權要求網站](https://www.microsoft.com/concern/privacyrequest-msa)來查看多個 Microsoft 服務中繫結至 MSA 身分識別的活動資料。在此案例中，使用者是自己的個人資料的控制者。</span><span class="sxs-lookup"><span data-stu-id="5b662-p104">Users that authenticate using an MSA identity can use this [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) to view activity data tied to their MSA identity across multiple Microsoft services. In this scenario, the user is a controller for their own personal data.</span></span>

## <a name="export-or-delete-issues"></a><span data-ttu-id="5b662-130">匯出或刪除問題</span><span class="sxs-lookup"><span data-stu-id="5b662-130">Export or delete issues</span></span>

<span data-ttu-id="5b662-131">針對 AAD 身分識別，如果您從 Azure 入口網站匯出或刪除資料時遇到問題，請前往 Azure 入口網站 [協助 + 支援]\*\*\*\* 刀鋒視窗，並在 [訂閱管理]\*\*\*\* > [其他安全性和法規遵循要求]\*\*\*\* > [隱私權刀鋒視窗和 GDPR 要求]\*\*\*\* 下提交新票證。</span><span class="sxs-lookup"><span data-stu-id="5b662-131">For AAD identities, if you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management** > **Other Security and Compliance Request** > **Privacy Blade and GDPR Requests**.</span></span>

<span data-ttu-id="5b662-132">針對 MSA 身分識別，如果您從隱私權要求網站匯出資料時遇到問題，請登入[隱私權要求網站](https://www.microsoft.com/concern/privacyrequest-msa)並提交要求，以透過要求網路表格取得 Microsoft 隱私權小組提供的協助。</span><span class="sxs-lookup"><span data-stu-id="5b662-132">For MSA identities, if you run into issues while exporting data from the Privacy Request site, log on to the [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) and submit a request for help from the Microsoft Privacy team via the request webform.</span></span>

## <a name="learn-more"></a><span data-ttu-id="5b662-133">深入了解</span><span class="sxs-lookup"><span data-stu-id="5b662-133">Learn more</span></span>

<span data-ttu-id="5b662-p105">Microsoft 會竭盡所能確保 Azure DevOps Services 資料保持安全且隱私，沒有任何例外。若要深入了解我們如何保護您的 Azure DevOps Services 資料，請造訪 [Azure DevOps Services 資料保護概觀](/vsts/articles/team-services-security-whitepaper?view=vsts)白皮書。</span><span class="sxs-lookup"><span data-stu-id="5b662-p105">Microsoft is committed to ensuring that your Azure DevOps Services data remains secure and private, without exception. Visit the [Azure DevOps Services data protection overview](/vsts/articles/team-services-security-whitepaper?view=vsts) whitepaper to learn more about how we protect your Azure DevOps Services data.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b662-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5b662-136">See also</span></span>

- [<span data-ttu-id="5b662-137">Microsoft 對公開發行企業軟體產品客戶的 GDPR 承諾</span><span class="sxs-lookup"><span data-stu-id="5b662-137">Microsoft's GDPR commitments to customers of our generally available enterprise software products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="5b662-138">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="5b662-138">Microsoft Trust center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [<span data-ttu-id="5b662-139">服務信任入口網站</span><span class="sxs-lookup"><span data-stu-id="5b662-139">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="5b662-140">Microsoft 隱私權儀表板</span><span class="sxs-lookup"><span data-stu-id="5b662-140">Microsoft privacy dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="5b662-141">Microsoft 隱私權回應中心</span><span class="sxs-lookup"><span data-stu-id="5b662-141">Microsoft privacy response center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="5b662-142">GDPR 的 Azure 資料主體要求</span><span class="sxs-lookup"><span data-stu-id="5b662-142">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)