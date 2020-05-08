---
title: GDPR 和 CCPA 的 Visual Studio 系列資料主體要求
description: 了解如何使用 Microsoft 工具管理 Visual Studio 中的家族資料主體要求，以符合 GDPR 和 CCPA。
keywords: Visual Studio、Visual Studio Code、Visual Studio for Mac、Visual Studio 文件、隱私權、GDPR、CCPA
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6d5e4fe6db8ef776435cc75da04ac5d2e038a47
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036298"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="30b06-104">GDPR 和 CCPA 的 Visual Studio 系列資料主體要求</span><span class="sxs-lookup"><span data-stu-id="30b06-104">Visual Studio Family Data Subject Requests for the GDPR and CCPA</span></span>

<span data-ttu-id="30b06-p101">歐盟[一般資料保護規範 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 賦予人員 (在規範中稱為「資料主體」__) 權限，以管理他們的個人資料。個人資料在 GDPR 中的定義非常廣泛，係指與已識別或可識別之自然人相關的任何資料。GDPR 賦予資料主體對其個人資料的特定權限，這些權限包括取得個人資料副本、要求更正資料、限制資料的處理、刪除資料或以電子格式接收資料。由資料主體向資料控制者 (具有個人資料控制權的雇主或其他類型的公司或組織) 提出對該資料主體的個人資料採取某項動作的正式要求，稱為「資料主體要求」__ 或 DSR。</span><span class="sxs-lookup"><span data-stu-id="30b06-p101">The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as _data subjects_) to manage their personal data. Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format. A formal request by a data subject to a data controller (an employer or other type of agency or organization that has control over personal data) to take an action on that data subject's personal data is called a _data subject request_ or DSR.</span></span>

<span data-ttu-id="30b06-109">同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。</span><span class="sxs-lookup"><span data-stu-id="30b06-109">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR's Data Subject Rights, such as the right to delete, access and receive (portability) their personal information.</span></span>  <span data-ttu-id="30b06-110">CCPA 也提供特定揭露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。</span><span class="sxs-lookup"><span data-stu-id="30b06-110">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and "opt-out/ opt-in" requirements for certain data transfers classified as "sales".</span></span> <span data-ttu-id="30b06-111">銷售的廣泛定義，包括出於有價值的考量而共用資料。</span><span class="sxs-lookup"><span data-stu-id="30b06-111">Sales are broadly defined to include the sharing of data for a valuable consideration.</span></span> <span data-ttu-id="30b06-112">如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="30b06-112">For more information about the CCPA, see the [California Consumer Privacy Act](offering-ccpa.md) and the [California Consumer Privacy Act FAQ](ccpa-faq.md).</span></span>

<span data-ttu-id="30b06-113">如需關於 GDPR 的一般資訊，請參閱[服務信任入口網站的 GDPR 區段](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)。</span><span class="sxs-lookup"><span data-stu-id="30b06-113">For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

## <a name="products-covered-by-this-guide"></a><span data-ttu-id="30b06-114">本指南所涵蓋的產品</span><span class="sxs-lookup"><span data-stu-id="30b06-114">Products covered by this guide</span></span>

<span data-ttu-id="30b06-115">本指南將討論如何使用 Microsoft 工具，匯出或刪除在驗證的 (登入的) 工作階段期間使用 Visual Studio 和 Visual Studio for Mac，以及這兩個產品和 Visual Studio Code 的 Microsoft 擴充功能所收集的個人資料。</span><span class="sxs-lookup"><span data-stu-id="30b06-115">This guide discusses how to use Microsoft tools to export or delete personal data collected during authenticated (signed-in) session usage of Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code.</span></span> <span data-ttu-id="30b06-116">本指南也涵蓋如何針對使用 Visual Studio 開發人員社群、NuGet.org 和 ASP.NET 網站時收集的個人資料進行資料主體要求。</span><span class="sxs-lookup"><span data-stu-id="30b06-116">This guide also covers how to make data subject requests for personal data collected when using Visual Studio Developer Community, NuGet.org, and the ASP.NET website.</span></span> <span data-ttu-id="30b06-117">這些產品可讓您使用非 Microsoft 工具和擴充功能，而 Microsoft 不是這些工具和擴充功能的資料處理者或控制者。</span><span class="sxs-lookup"><span data-stu-id="30b06-117">These products may enable the use of non-Microsoft tools and extensions, and Microsoft is not a data processor or controller for these tools and extensions.</span></span> <span data-ttu-id="30b06-118">使用者應連絡工具或擴充功能提供者，以瞭解這些工具和擴充功能的個人資料和集合原則。</span><span class="sxs-lookup"><span data-stu-id="30b06-118">Users should contact the tool or extension provider to understand the personal data and collection policies for these tools and extensions.</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="30b06-119">其他隱私權資訊</span><span class="sxs-lookup"><span data-stu-id="30b06-119">Additional privacy information</span></span>

<span data-ttu-id="30b06-120">產品隨附的 Microsoft 軟體授權條款 ([Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?LinkId=660726)和 [Microsoft 的 GDPR 承諾](https://docs.microsoft.com/legal/gdpr)) 會描述我們的資料處理做法。</span><span class="sxs-lookup"><span data-stu-id="30b06-120">The Microsoft Software License Terms accompanying the products, the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=660726), and [Microsoft's GDPR Commitments](https://docs.microsoft.com/legal/gdpr) describe our data processing practices.</span></span>

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a><span data-ttu-id="30b06-121">Visual Studio、Visual Studio for Mac 和 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="30b06-121">Visual Studio, Visual Studio for Mac, and Visual Studio Code</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="30b06-122">我們收集的個人資料</span><span class="sxs-lookup"><span data-stu-id="30b06-122">Personal data we collect</span></span>

<span data-ttu-id="30b06-p104">Microsoft 身為 GDPR 底下的資料處理者，會向我們要提供體驗的使用者收集所需資料，藉以改善 Visual Studio 和 Visual Studio for Mac，以及 Microsoft 對此上述兩種軟體和對 Visual Studio Code 的擴充功能。資料有兩種類別：客戶資料以及系統所產生的記錄。客戶資料包含這些產品執行其所提供服務所需的使用者識別交易和互動資料。例如，若要為使用者提供個人化體驗 (例如漫遊設定)，我們必須收集使用者帳戶資訊和設定資料。系統所產生的記錄是用來協助您找出問題並針對問題進行疑難排解的使用狀況或診斷資料，從而改善我們的產品和服務，並也可能包含關於使用者的識別資訊 (例如使用者名稱)。系統所產生記錄的保留時間不會超過 18 個月。例如，系統所產生的記錄會針對每一天的產品使用情形進行彙總，並且會包含使用日期、所使用的產品 (例如，"Visual Studio 2017")、您所採取的動作 (例如，"vs/core/packagecostsummary/solutionload")，以及採取動作的次數，如本範例中所示：</span><span class="sxs-lookup"><span data-stu-id="30b06-p104">As a data processor under the GDPR, Microsoft collects the data we need from users to provide experiences for and improve Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code. There are two categories of data: customer data and system-generated logs. Customer data includes user-identifiable transactional and interactional data that these products need to perform the service they provide. For example, to provide users with personalized experiences such as roaming settings, we need to collect user account information and settings data. System-generated logs are usage or diagnostic data that are used to help identify and troubleshoot problems and improve our products and services, and may also contain identifiable information about end users, such as a user name. System-generated logs are retained for no more than 18 months. As an example, system-generated logs are aggregated for each day of product usage and include the usage date, the product used (for example, "Visual Studio 2017"), the action you took (for example, "vs/core/packagecostsummary/solutionload"), and the number of times the action was taken, as shown in this sample:</span></span>

```Log
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

<span data-ttu-id="30b06-130">如需詳細資訊，請參閱 [Visual Studio 所收集的系統所產生記錄](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection)。</span><span class="sxs-lookup"><span data-stu-id="30b06-130">For more information, see [System-generated logs collected by Visual Studio](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection).</span></span>

<span data-ttu-id="30b06-p105">DSR 僅針對附加到已驗證身分識別的個人資料提供服務。例如，Visual Studio Code 不支援登入，因此不會將其中的系統所產生記錄附加至已驗證的身分識別，且無法獲得服務。不過，Visual Studio Code 的某些 Microsoft 擴充功能可能會提供驗證的資料，而 DSR 可為此資料提供服務。如需詳細資訊，請參閱[ GDPR 與 Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code)。一般而言，我們不會儲存 Visual Studio 2013 及較舊版本的資料；不過，某些擴充功能和元件可能會提供附加到已驗證身分識別的資料，而 DSR 可以為其提供服務，如下所示。</span><span class="sxs-lookup"><span data-stu-id="30b06-p105">Only personal data that is attached to authenticated identities can be serviced by a DSR. So, for example, because Visual Studio Code does not support sign-in, system-generated logs from it are not attached to an authenticated identity and cannot be serviced. However, some Microsoft extensions for Visual Studio Code may provide authenticated data, and this data can be serviced by a DSR. For more information, see [GDPR and Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code). In general, we do not store data for Visual Studio 2013 and earlier; however, certain extensions and components may provide data attached to authenticated identities and can be serviced by a DSR as outlined below.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="30b06-136">使用者如何控制個人資料</span><span class="sxs-lookup"><span data-stu-id="30b06-136">How users can control personal data</span></span>

<span data-ttu-id="30b06-137">Visual Studio 2015 及更新版本、Visual Studio for Mac 和 Visual Studio Code 可提供下列方法，讓您的使用者停止資料收集，並讓您以控制者身分將已收集到的資料匯出或刪除。</span><span class="sxs-lookup"><span data-stu-id="30b06-137">Visual Studio 2015 and later, Visual Studio for Mac, and Visual Studio Code provide the following means for your users to stop data collection, and for you as controller to export, or delete data that has already been gathered.</span></span>

#### <a name="in-app-settings"></a><span data-ttu-id="30b06-138">應用程式內設定</span><span class="sxs-lookup"><span data-stu-id="30b06-138">In-app settings</span></span>

<span data-ttu-id="30b06-p106">使用者可以控制這些產品的隱私權設定。如需詳細資訊，請參閱下列內容</span><span class="sxs-lookup"><span data-stu-id="30b06-p106">Users can control the privacy settings for these products. For more information, see the following</span></span>

- <span data-ttu-id="30b06-141">[如何管理 Visual Studio 中的隱私權設定](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program)。</span><span class="sxs-lookup"><span data-stu-id="30b06-141">[How to manage privacy settings in Visual Studio](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="30b06-142">[如何管理 Visual Studio for Mac 中的隱私權設定](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program)。</span><span class="sxs-lookup"><span data-stu-id="30b06-142">[How to manage privacy settings in Visual Studio for Mac](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="30b06-143">[如何停用 Visual Studio Code 中的遙測報告](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting)。</span><span class="sxs-lookup"><span data-stu-id="30b06-143">[How to disable telemetry reporting in Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).</span></span>

#### <a name="exporting-or-deleting-data"></a><span data-ttu-id="30b06-144">匯出或刪除資料</span><span class="sxs-lookup"><span data-stu-id="30b06-144">Exporting or deleting data</span></span>

<span data-ttu-id="30b06-p107">控制者可以透過兩種方法之一 (取決於他們 Visual Studio 系列產品或 Microsoft 擴充功能的註冊方式)，來管理從其資料主體收集到的客戶資料和系統所產生記錄。在某些情況下，必須同時使用這兩種方法。這兩種方法都可讓控制者下載一份受該方法管理的活動歷程記錄。關閉 AAD 或 MSA 帳戶會刪除相關聯的 Visual Studio 客戶資料，並將與這些產品相關的系統所產生記錄中的個人識別資料進行匿名。已匿名之系統所產生記錄的保留時間不會超過 18 個月。</span><span class="sxs-lookup"><span data-stu-id="30b06-p107">Controllers can manage customer data and system-generated logs collected from their data subjects by one of two methods, depending upon how their Visual Studio Family product or Microsoft extensions were registered. In some cases, both methods must be used. Both methods allow Controllers to download a copy of their activity history managed by that method. Closure of an AAD or MSA account deletes associated Visual Studio customer data, and anonymizes personally identifiable data in system-generated logs pertaining to these products. Anonymized system-generated logs are retained for no more than 18 months.</span></span>

- <span data-ttu-id="30b06-150">使用 Azure 租用戶所支援帳戶例如，與 Azure 訂閱相關聯的 AAD 帳戶或 MSA 帳戶註冊 Visual Studio 系列產品的使用者可遵循 [GDPR 的 Azure 資料主體要求](gdpr-dsr-azure.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="30b06-150">Users that have registered a Visual Studio Family product by using an account that is backed by an Azure tenant — for example, AAD account or  MSA account associated with an Azure subscription — can follow the instructions in [Azure Data Subject Requests for the GDPR](gdpr-dsr-azure.md).</span></span>
- <span data-ttu-id="30b06-151">未使用 Azure 租用戶所支援帳戶例如，許多使用 Microsoft 帳戶 (MSA) 的帳戶註冊 Visual Studio 系列產品的使用者，可使用透過其 Microsoft 帳戶提供的[ Web 式 Microsoft 隱私權回應中心](https://aka.ms/userprivacysite)來檢視、控制及刪除繫結至其多項 Microsoft 服務中 Microsoft 帳戶的活動資料。</span><span class="sxs-lookup"><span data-stu-id="30b06-151">Users that have registered a Visual Studio Family product without an account that is backed by an Azure tenant — for example many accounts using a Microsoft Account (MSA) — can use [the web-based Microsoft Privacy Response Center](https://aka.ms/userprivacysite) available through their Microsoft account to view, control, and delete activity data tied to their Microsoft account across multiple Microsoft services.</span></span> <span data-ttu-id="30b06-152">在此案例中，使用者是自己個人資料的控制者。</span><span class="sxs-lookup"><span data-stu-id="30b06-152">In this scenario, the user is a controller for their own personal data.</span></span>

> [!NOTE]
> <span data-ttu-id="30b06-153">當 MSA 帳戶擁有者刪除其帳戶時，所有與這些產品相關的個人識別資料都會加以刪除 (無論帳戶是否受 Azure 租用戶所支援)，且會將系統產生的記錄加以匿名。</span><span class="sxs-lookup"><span data-stu-id="30b06-153">When an MSA account holder deletes their account, all their personally identifiable data pertaining to these products is deleted, whether the account is backed by an Azure tenant or not, and system-generated logs are anonymized.</span></span>

<span data-ttu-id="30b06-p109">針對 Visual Studio 2013，我們所收集的資料會加以匿名。針對 Visual Studio 2012 與先前版本，我們在收到資料後會立即加以刪除。在這兩種情況下，稍後沒有任何內容可供檢視、匯出或刪除。</span><span class="sxs-lookup"><span data-stu-id="30b06-p109">For Visual Studio 2013, the data we collect is anonymized. For Visual Studio 2012 and prior releases, we immediately delete the data upon receipt. In both cases, there is nothing to view, export, or delete at a later time.</span></span>

## <a name="visual-studio-developer-community"></a><span data-ttu-id="30b06-157">Visual Studio 開發人員社群</span><span class="sxs-lookup"><span data-stu-id="30b06-157">Visual Studio Developer Community</span></span>

<span data-ttu-id="30b06-p110">我們透過[開發人員社群](https://developercommunity.visualstudio.com)網站支援[一般資料保護規定 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 要求。您可以檢視、匯出或刪除您的意見反應資料。</span><span class="sxs-lookup"><span data-stu-id="30b06-p110">We support [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) requests through the [Developer Community](https://developercommunity.visualstudio.com) website. You can View, Export, or Delete your feedback data.</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="30b06-160">我們收集的個人資料</span><span class="sxs-lookup"><span data-stu-id="30b06-160">Personal data we collect</span></span>

<span data-ttu-id="30b06-p111">Microsoft 會收集資料，以協助我們重現您使用 Visual Studio 系列產品回報的問題，並針對問題進行疑難排解。這項資料包含個人資料和公開意見反應。個人資料包括：</span><span class="sxs-lookup"><span data-stu-id="30b06-p111">Microsoft collects data to help us reproduce and troubleshoot issues you report with Visual Studio Family products. This data includes personal data and public feedback. Personal data includes:</span></span>

- <span data-ttu-id="30b06-164">您的[開發人員社群](https://developercommunity.visualstudio.com)設定檔資訊；</span><span class="sxs-lookup"><span data-stu-id="30b06-164">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="30b06-165">喜好設定和通知；</span><span class="sxs-lookup"><span data-stu-id="30b06-165">Preferences and notifications;</span></span>
- <span data-ttu-id="30b06-166">您透過[在 Visual Studio 中回報的問題](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)或透過[開發人員社群](https://developercommunity.visualstudio.com)提供的附件和系統所產生記錄；</span><span class="sxs-lookup"><span data-stu-id="30b06-166">Attachments and system-generated logs you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com);</span></span>
- <span data-ttu-id="30b06-167">您的投票。</span><span class="sxs-lookup"><span data-stu-id="30b06-167">Your votes.</span></span>

<span data-ttu-id="30b06-168">公開意見反應包含：回報的問題、註解和解決方案。</span><span class="sxs-lookup"><span data-stu-id="30b06-168">Public feedback includes: reported problems, comments, and solutions.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="30b06-169">使用者如何控制個人資料</span><span class="sxs-lookup"><span data-stu-id="30b06-169">How users can control personal data</span></span>

#### <a name="view"></a><span data-ttu-id="30b06-170">檢視</span><span class="sxs-lookup"><span data-stu-id="30b06-170">View</span></span>

<span data-ttu-id="30b06-171">若要檢視與您意見反應相關的資料，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="30b06-171">To View your feedback-related data, follow these steps:</span></span>

1. <span data-ttu-id="30b06-172">登入[開發人員社群](https://developercommunity.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="30b06-172">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="30b06-173">從右上角按一下您的設定檔，然後選取 [設定檔和喜好設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="30b06-173">From the top-right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="30b06-174">按一下任一個 [設定檔]\*\*\*\*、[通知]\*\*\*\*、[活動]\*\*\*\* 和 [附件]\*\*\*\* 索引標籤來檢視提交至意見反應系統的資料。</span><span class="sxs-lookup"><span data-stu-id="30b06-174">Click on any of the **Profile**, **Notifications**, **Activity**, and **Attachments** tabs to view the data submitted to the feedback systems.</span></span>
   1. <span data-ttu-id="30b06-175">[設定檔]\*\*\*\* 是指您的[開發人員社群](https://developercommunity.visualstudio.com)設定檔，其中包含使用者名稱、電子郵件地址、關於等等。</span><span class="sxs-lookup"><span data-stu-id="30b06-175">**Profile** refers to your [Developer Community](https://developercommunity.visualstudio.com) profile, including user name, email address, about, etc.</span></span>
   2. <span data-ttu-id="30b06-176">\*\*通知是控制您接收電子郵件通知的方式。</span><span class="sxs-lookup"><span data-stu-id="30b06-176">\*\*Notifications are how you control the email notifications you receive.</span></span>
   3. <span data-ttu-id="30b06-177">[活動]\*\*\*\* 會提供您已在使用中項目 (已張貼、已註解等) 和已執行活動的意見反應。</span><span class="sxs-lookup"><span data-stu-id="30b06-177">**Activity** will give you the feedback items you have been active on (posted, commented, etc.), and the activities performed.</span></span>
   4. <span data-ttu-id="30b06-178">[附件]\*\*\*\* 是您附件歷程記錄的清單，格式如 `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`。</span><span class="sxs-lookup"><span data-stu-id="30b06-178">**Attachments** is a list of your attachment history in a format like `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`.</span></span>

#### <a name="export"></a><span data-ttu-id="30b06-179">匯出</span><span class="sxs-lookup"><span data-stu-id="30b06-179">Export</span></span>

<span data-ttu-id="30b06-p113">您可以將您的意見反應資料匯出作為 DSR 的一部分。我們將會建立一個或多個 .zip 封存檔，當中包含：</span><span class="sxs-lookup"><span data-stu-id="30b06-p113">You can export your feedback data as part of DSR. We will create one or more .zip archives that will include:</span></span>

- <span data-ttu-id="30b06-182">您的[開發人員社群](https://developercommunity.visualstudio.com)設定檔資訊；</span><span class="sxs-lookup"><span data-stu-id="30b06-182">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="30b06-183">喜好設定和通知設定；</span><span class="sxs-lookup"><span data-stu-id="30b06-183">Preferences and notification settings;</span></span>
- <span data-ttu-id="30b06-184">您透過[在 Visual Studio 中回報的問題](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)或透過[開發人員社群](https://developercommunity.visualstudio.com)提供的附件。</span><span class="sxs-lookup"><span data-stu-id="30b06-184">Attachments you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>

> [!NOTE]
> <span data-ttu-id="30b06-185">我們會將您從封存檔中提供的下列公開意見反應排除：註解、解決方案、回報的問題。</span><span class="sxs-lookup"><span data-stu-id="30b06-185">We will exclude the following public feedback you have provided from your archive: comments, solutions, reported problems.</span></span>

<span data-ttu-id="30b06-186">若要開始匯出，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="30b06-186">To start an Export, follow these steps:</span></span>

1. <span data-ttu-id="30b06-187">登入[開發人員社群](https://developercommunity.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="30b06-187">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="30b06-188">從右上角按一下您的設定檔，然後選取 [設定檔和喜好設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="30b06-188">From the top-right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="30b06-189">按一下 [隱私權]\*\*\*\* 索引標籤，然後按一下 [建立封存]\*\*\*\* 以要求匯出您的資料。</span><span class="sxs-lookup"><span data-stu-id="30b06-189">Click the **Privacy** tab, and then click **Create an archive** to request exporting your data.</span></span>
3. <span data-ttu-id="30b06-p115">[封存狀態]\*\*\*\* 將會更新，以顯示我們正在準備資料。資料可供使用之前的時間長度會依據我們所需匯出的資料量而定。</span><span class="sxs-lookup"><span data-stu-id="30b06-p115">The **Archive Status** will update to show that we are preparing the data. The length of time before the data is available depends on the amount of data we need to export.</span></span>
4. <span data-ttu-id="30b06-192">一旦資料就緒之後，我們會傳送電子郵件給您。</span><span class="sxs-lookup"><span data-stu-id="30b06-192">Once the data is ready, we will send you an email.</span></span>
5. <span data-ttu-id="30b06-193">按一下電子郵件中的 [下載封存]\*\*\*\*，或回到 [隱私權] 索引標籤來下載您的資料。</span><span class="sxs-lookup"><span data-stu-id="30b06-193">Click **Download Archive** in the email, or go back to the Privacy tab to download your data.</span></span>

> [!NOTE]
> - <span data-ttu-id="30b06-194">如果您在 [通知] 索引標籤中選擇不要收到通知，我們就不會傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="30b06-194">We will not send email if you chose not to receive notifications in the Notifications tab.</span></span>
> - <span data-ttu-id="30b06-195">如果您再次要求匯出，我們就會移除您的舊封存，並建立新的封存。</span><span class="sxs-lookup"><span data-stu-id="30b06-195">If you request Export again, we will remove your old archive and create a new one.</span></span>

#### <a name="delete"></a><span data-ttu-id="30b06-196">刪除</span><span class="sxs-lookup"><span data-stu-id="30b06-196">Delete</span></span>

<span data-ttu-id="30b06-197">刪除將會從[開發人員社群](https://developercommunity.visualstudio.com)中移除下列關於您的資訊</span><span class="sxs-lookup"><span data-stu-id="30b06-197">Deleting will remove the following information about you from [Developer Community](https://developercommunity.visualstudio.com):</span></span>

- <span data-ttu-id="30b06-198">設定檔資訊；</span><span class="sxs-lookup"><span data-stu-id="30b06-198">Profile information;</span></span>
- <span data-ttu-id="30b06-199">喜好設定和通知設定；</span><span class="sxs-lookup"><span data-stu-id="30b06-199">Preferences and notification settings;</span></span>
- <span data-ttu-id="30b06-200">您透過[在 Visual Studio 中回報的問題](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)或透過[開發人員社群](https://developercommunity.visualstudio.com)提供的附件。</span><span class="sxs-lookup"><span data-stu-id="30b06-200">Attachments you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>
- <span data-ttu-id="30b06-201">您的投票</span><span class="sxs-lookup"><span data-stu-id="30b06-201">Your votes</span></span>

> [!NOTE]
> <span data-ttu-id="30b06-202">我們將不會刪除下列公開資訊，但會加以匿名：您的註解、解決方案、您所回報的問題。</span><span class="sxs-lookup"><span data-stu-id="30b06-202">We will not delete, but will anonymize, the following public information: your comments, your solutions, problems that you reported.</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="30b06-203">刪除 AAD 或 MSA 帳戶會觸發[開發人員社群](https://developercommunity.visualstudio.com)的 [刪除] 程序。</span><span class="sxs-lookup"><span data-stu-id="30b06-203">Delete of an AAD or MSA account triggers the Delete process for [Developer Community](https://developercommunity.visualstudio.com).</span></span>

<span data-ttu-id="30b06-204">若要開始 [刪除]，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="30b06-204">To initiate a Delete, follow these steps:</span></span>

1. <span data-ttu-id="30b06-205">登入[開發人員社群](https://developercommunity.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="30b06-205">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="30b06-206">從右上角按一下您的設定檔，然後選取 [設定檔和喜好設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="30b06-206">From the top-right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="30b06-207">按一下 [隱私權]\*\*\*\* 索引標籤，然後按一下 [刪除資料與帳戶]\*\*\*\* 以開始刪除資料。</span><span class="sxs-lookup"><span data-stu-id="30b06-207">Click the **Privacy** tab, and then click **Delete your data and account** to start deleting your data.</span></span>
3. <span data-ttu-id="30b06-208">[確認] 畫面隨即出現。</span><span class="sxs-lookup"><span data-stu-id="30b06-208">A confirmation screen will appear.</span></span>
4. <span data-ttu-id="30b06-209">在方塊中輸入「刪除」，然後按一下 [刪除我的帳戶]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="30b06-209">Type "delete" in the box, and then click **Delete my account**.</span></span>

<span data-ttu-id="30b06-210">當您按一下 [刪除帳戶]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="30b06-210">Once you click **Delete my account:**</span></span>

- <span data-ttu-id="30b06-211">我們會將您登出。</span><span class="sxs-lookup"><span data-stu-id="30b06-211">We will sign you out.</span></span>
- <span data-ttu-id="30b06-212">我們將會刪除您的[開發人員社群](https://developercommunity.visualstudio.com)帳戶、您的個人資料和附件。</span><span class="sxs-lookup"><span data-stu-id="30b06-212">We will delete your [Developer Community](https://developercommunity.visualstudio.com) account, your personal data, and attachments.</span></span>
- <span data-ttu-id="30b06-p117">我們會將您的公開意見反應匿名。您的公開意見反應將仍在開發人員社群中顯示，且會指示為以匿名使用者回報。</span><span class="sxs-lookup"><span data-stu-id="30b06-p117">We will anonymize your public feedback. Your public feedback will remain available on Developer Community, and will be indicated as reported by an Anonymous user.</span></span>
- <span data-ttu-id="30b06-215">我們在刪除您的帳戶之後，就不會傳送電子郵件給您，因為您將不再顯示於系統中。</span><span class="sxs-lookup"><span data-stu-id="30b06-215">We won't email you after we delete your account, because you will no longer be present in the system.</span></span>
- <span data-ttu-id="30b06-216">如果您報告新的問題或登入[開發人員社群](https://developercommunity.visualstudio.com)，則系統會將您視為新的使用者。</span><span class="sxs-lookup"><span data-stu-id="30b06-216">If you report a new problem or log into [Developer Community](https://developercommunity.visualstudio.com), you will be identified as a new user.</span></span>
- <span data-ttu-id="30b06-217">如果您從[開發人員社群](https://developercommunity.visualstudio.com)中刪除您的帳戶，我們並不會將它從其他 Microsoft 服務中刪除。</span><span class="sxs-lookup"><span data-stu-id="30b06-217">If you delete your account from [Developer Community](https://developercommunity.visualstudio.com), we will not delete it from other Microsoft services.</span></span>

## <a name="xamarin-forums"></a><span data-ttu-id="30b06-218">Xamarin 論壇</span><span class="sxs-lookup"><span data-stu-id="30b06-218">Xamarin Forums</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="30b06-219">我們收集的個人資料</span><span class="sxs-lookup"><span data-stu-id="30b06-219">Personal Data We Collect</span></span>

<span data-ttu-id="30b06-220">透過 [Xamarin 論壇](https://forums.xamarin.com/)使用者社群，Microsoft 會收集您提供的資料，協助我們重現您在使用 Microsoft 產品和服務時遇到的問題並進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="30b06-220">Through the [Xamarin Forums](https://forums.xamarin.com/) user community, Microsoft collects data you provide to help us reproduce and troubleshoot issues you may have with Microsoft products and services.</span></span> <span data-ttu-id="30b06-221">這些資料包括個人資料和公開意見反應。</span><span class="sxs-lookup"><span data-stu-id="30b06-221">This data includes personal data and public feedback.</span></span> <span data-ttu-id="30b06-222">我們收集的個人資料是使用者帳戶資料 (例如，與您的 Xamarin 論壇相關聯的使用者名稱和電子郵件地址)，我們收集的公開意見反應包括您透過 Xamarin 論壇提供的錯誤、問題、註解和解決方案。</span><span class="sxs-lookup"><span data-stu-id="30b06-222">The personal data we collect is user account data (for example, user names and email addresses associated with your Xamarin Forums), and the public feedback we collect includes bugs, problems, comments, and solutions you provide via the Xamarin Forums.</span></span>

### <a name="how-you-can-control-your-data"></a><span data-ttu-id="30b06-223">您可以控制資料的方式</span><span class="sxs-lookup"><span data-stu-id="30b06-223">How You Can Control Your Data</span></span>

#### <a name="xamarin-forums"></a><span data-ttu-id="30b06-224">Xamarin 論壇</span><span class="sxs-lookup"><span data-stu-id="30b06-224">Xamarin Forums</span></span>

##### <a name="view"></a><span data-ttu-id="30b06-225">檢視</span><span class="sxs-lookup"><span data-stu-id="30b06-225">View</span></span>

<span data-ttu-id="30b06-p119">具有有效 Xamarin 論壇帳戶的使用者可以在 Xamarin 論壇帳戶頁面中檢視其個人資料和公開意見反應 (例如，所有已張貼的對話和文章)。使用者也會透過其帳戶頁面編輯其個人資料。</span><span class="sxs-lookup"><span data-stu-id="30b06-p119">Users with active Xamarin Forums accounts may view their personal data and public feedback (for example, all of their posted threads and posts) from their Xamarin Forums account page. Users may also edit their personal data through their account page.</span></span>

##### <a name="export"></a><span data-ttu-id="30b06-228">匯出</span><span class="sxs-lookup"><span data-stu-id="30b06-228">Export</span></span>

<span data-ttu-id="30b06-p120">Xamarin 論壇是由第三方 Vanilla 論壇託管。如需要求匯出您的公開資料，使用者需連絡 forums@xamarin.com (受 Xamarin 小組監視)。接著，我們會直接與 Vanilla 論壇合作來處理此要求。</span><span class="sxs-lookup"><span data-stu-id="30b06-p120">Xamarin Forums are hosted by a third party, Vanilla Forums. To request export of your public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then work directly with Vanilla Forums to process this request.</span></span>

##### <a name="delete"></a><span data-ttu-id="30b06-232">刪除</span><span class="sxs-lookup"><span data-stu-id="30b06-232">Delete</span></span>

<span data-ttu-id="30b06-p121">Xamarin 論壇是由第三方 Vanilla 論壇託管。如需要求刪除您的個人及公開資料，使用者需連絡 forums@xamarin.com (受 Xamarin 小組監視)。接著，我們會手動處理使用者的個人資料刪除要求。</span><span class="sxs-lookup"><span data-stu-id="30b06-p121">Xamarin Forums are hosted by a third party, Vanilla Forums. To request deletion of your personal and public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then manually service the user's personal data deletion request.</span></span>

> [!NOTE]
> <span data-ttu-id="30b06-236">Xamarin 的 Bugzilla 不再接受新問題。</span><span class="sxs-lookup"><span data-stu-id="30b06-236">Bugzilla for Xamarin no longer accepts new issues.</span></span> <span data-ttu-id="30b06-237">前一版的 Xamarin Bugzilla 帳戶擁有者可以在下列網址檢視他們報告之所有錯誤以及新增至錯誤之所有註解的封存於 [https://xamarin.github.io/bugzilla-archives/](https://xamarin.github.io/bugzilla-archives/)。</span><span class="sxs-lookup"><span data-stu-id="30b06-237">Former Xamarin Bugzilla accounts holders can view an archive of all bugs they've reported and all comments they've added to bugs at [https://xamarin.github.io/bugzilla-archives/](https://xamarin.github.io/bugzilla-archives/).</span></span> <span data-ttu-id="30b06-238">若要要求刪除封存中所包含的個人資料，使用者可以在 [https://github.com/xamarin/bugzilla-archives/issues/new/choose](https://github.com/xamarin/bugzilla-archives/issues/new/choose) 進行歸檔和發布。</span><span class="sxs-lookup"><span data-stu-id="30b06-238">To request deletion of personal data contained in the archive, users can file and issue at [https://github.com/xamarin/bugzilla-archives/issues/new/choose](https://github.com/xamarin/bugzilla-archives/issues/new/choose).</span></span> <span data-ttu-id="30b06-239">使用者張貼到 Xamarin Bugzilla 的公開意見反應 (例如錯誤、問題、註解和解決方案) 在收到刪除要求後不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="30b06-239">Public feedback (for example, bugs, problems, comments, and solutions) that users have posted to the Xamarin Bugzilla will not be deleted after receipt of a delete request.</span></span> <span data-ttu-id="30b06-240">透過移除與提交刪除要求的使用者建立之任何公開意見反應相關聯的名稱和電子郵件地址，將匿名公開意見反應。</span><span class="sxs-lookup"><span data-stu-id="30b06-240">Public feedback will instead be anonymized by removing the name and email address associated with any public feedback created by the user submitting the delete request.</span></span>

## <a name="nuget"></a><span data-ttu-id="30b06-241">NuGet</span><span class="sxs-lookup"><span data-stu-id="30b06-241">NuGet</span></span>

<span data-ttu-id="30b06-242">如需 NuGet.org 的 DSR 相關詳細資訊，請參閱 [NuGet 使用者資料要求](https://docs.microsoft.com/nuget/policies/data-requests)。</span><span class="sxs-lookup"><span data-stu-id="30b06-242">For more information on DSR for NuGet.org, see [NuGet User Data Requests](https://docs.microsoft.com/nuget/policies/data-requests).</span></span>

## <a name="aspnet"></a><span data-ttu-id="30b06-243">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30b06-243">ASP.NET</span></span>

<span data-ttu-id="30b06-244">如需 ASP.NET 網站的 DSR 相關資訊，請參閱 [ASP.NET 網站和 GDPR 資料主體要求處理](https://www.asp.net/gdpr)。</span><span class="sxs-lookup"><span data-stu-id="30b06-244">For information on DSR for the ASP.NET website, see [The ASP.NET Website and GDPR Data Subject Request processing](https://www.asp.net/gdpr).</span></span>

## <a name="iisnet"></a><span data-ttu-id="30b06-245">IIS.NET</span><span class="sxs-lookup"><span data-stu-id="30b06-245">IIS.NET</span></span>

<span data-ttu-id="30b06-246">如需 IIS.NET 網站的 DSR 相關資訊，請參閱 [IIS.NET 網站和 GDPR 資料主體要求處理](https://www.iis.net/gdpr)。</span><span class="sxs-lookup"><span data-stu-id="30b06-246">For information on DSR for the IIS.NET website, see [The IIS.NET Website and GDPR Data Subject Request processing](https://www.iis.net/gdpr).</span></span>

## <a name="other-visual-studio-family-services"></a><span data-ttu-id="30b06-247">其他 Visual Studio 系列服務</span><span class="sxs-lookup"><span data-stu-id="30b06-247">Other Visual Studio Family Services</span></span>

### <a name="surveymonkey"></a><span data-ttu-id="30b06-248">SurveyMonkey</span><span class="sxs-lookup"><span data-stu-id="30b06-248">SurveyMonkey</span></span>

<span data-ttu-id="30b06-p123">有時，我們會邀請客戶透過 SurveyMonkey 提供關於這些產品的意見反應。這項資料會在 28 天內刪除。在處理這些產品的資料主體要求時，如果我們已驗證問卷回應，我們會將其包含在匯入及刪除資料主體要求中。</span><span class="sxs-lookup"><span data-stu-id="30b06-p123">From time to time, we invite customers to provide feedback on these products via SurveyMonkey. This data is deleted within 28 days. When servicing data subject requests for these products, if we have authenticated survey responses we include them in export and delete data subject requests.</span></span>

## <a name="learn-more"></a><span data-ttu-id="30b06-252">深入了解</span><span class="sxs-lookup"><span data-stu-id="30b06-252">Learn more</span></span>

- [<span data-ttu-id="30b06-253">Microsoft 對公開發行企業軟體產品客戶的 GDPR 承諾</span><span class="sxs-lookup"><span data-stu-id="30b06-253">Microsoft's GDPR Commitments to Customers of our Generally Available Enterprise Software Products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="30b06-254">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="30b06-254">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
- [<span data-ttu-id="30b06-255">服務信任入口網站</span><span class="sxs-lookup"><span data-stu-id="30b06-255">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="30b06-256">Microsoft 隱私權儀表板</span><span class="sxs-lookup"><span data-stu-id="30b06-256">Microsoft Privacy Dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="30b06-257">Microsoft 隱私權回應中心</span><span class="sxs-lookup"><span data-stu-id="30b06-257">Microsoft Privacy Response Center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="30b06-258">GDPR 的 Azure 資料主體要求</span><span class="sxs-lookup"><span data-stu-id="30b06-258">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)
