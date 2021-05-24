---
title: Microsoft 365 使用情況分析
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 77ff780d-ab19-4553-adea-09cb65ad0f1f
description: 深入瞭解您的組織如何採用 Microsoft 365 服務來進行通訊及共同作業。
ms.openlocfilehash: db61ed4d4c087b76895d08e43f6b1a2c00ed8172
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635387"
---
# <a name="microsoft-365-usage-analytics"></a><span data-ttu-id="e6d37-103">Microsoft 365 使用情況分析</span><span class="sxs-lookup"><span data-stu-id="e6d37-103">Microsoft 365 usage analytics</span></span>

<span data-ttu-id="e6d37-104">使用 Power BI 中 Microsoft 365 的流量分析，深入瞭解您的組織如何採用 Microsoft 365 內的各種服務。</span><span class="sxs-lookup"><span data-stu-id="e6d37-104">Use Microsoft 365 usage analytics within Power BI to gain insights on how your organization is adopting the various services within Microsoft 365.</span></span> <span data-ttu-id="e6d37-105">您可以視覺化和分析 Microsoft 365 使用狀況資料、建立自訂報告，以及分享組織內的洞察力。</span><span class="sxs-lookup"><span data-stu-id="e6d37-105">You can visualize and analyze Microsoft 365 usage data, create custom reports and share the insights within your organization.</span></span> <span data-ttu-id="e6d37-106">您也可以深入瞭解特定地區或部門如何使用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e6d37-106">You can also gain insights into how specific regions or departments are using Microsoft 365.</span></span>
  
<span data-ttu-id="e6d37-107">Microsoft 365 流量分析可讓您存取預先構建的儀表板，該儀表板提供最近12個月的叉積視圖，並包含許多預先建立的報告。</span><span class="sxs-lookup"><span data-stu-id="e6d37-107">Microsoft 365 usage analytics gives you access to a pre-built dashboard that provides a cross-product view of the last 12 months and contains a number of pre-built reports.</span></span> <span data-ttu-id="e6d37-108">每個報告都可提供特定的使用情況深入解析。</span><span class="sxs-lookup"><span data-stu-id="e6d37-108">Each report provides you with specific usage insights.</span></span> <span data-ttu-id="e6d37-109">使用者特有的資訊可用於最近的完整行事曆月份。</span><span class="sxs-lookup"><span data-stu-id="e6d37-109">User-specific information is available for the last full calendar month.</span></span>
  
<span data-ttu-id="e6d37-110">為範本應用程式供電的 [資料模型](usage-analytics-data-model.md) 包含 Active Directory 中的使用者屬性，可讓您在特定報告中進行 pivot 的功能。</span><span class="sxs-lookup"><span data-stu-id="e6d37-110">The [data model](usage-analytics-data-model.md) that powers the template app includes user attributes from Active Directory, enabling the ability to pivot in certain reports.</span></span> <span data-ttu-id="e6d37-111">包含下列 Active Directory 屬性：位置、部門和組織。</span><span class="sxs-lookup"><span data-stu-id="e6d37-111">The following Active Directory attributes are included: location, department, and organization.</span></span> 
  
<span data-ttu-id="e6d37-112">請參閱[啟用 Microsoft 365 使用情況分析](enable-usage-analytics.md) (機器翻譯) 以開始收集資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-112">See [Enable Microsoft 365 usage analytics](enable-usage-analytics.md) to start collecting data.</span></span> 
  
<span data-ttu-id="e6d37-113">Microsoft 365 流量分析包含下列各節所詳述的報表數目。</span><span class="sxs-lookup"><span data-stu-id="e6d37-113">Microsoft 365 usage analytics contains a number of reports detailed in the following sections.</span></span> 

<span data-ttu-id="e6d37-114">您可以選取資料表格，以存取每個區域的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="e6d37-114">You can access detailed reports for each area by selecting the data tables.</span></span> <span data-ttu-id="e6d37-115">您可以選取網站底部的索引標籤，以查看所有預先建立的報告。</span><span class="sxs-lookup"><span data-stu-id="e6d37-115">You can view all pre-built reports by selecting the tabs at the bottom of the site.</span></span> <span data-ttu-id="e6d37-116">如需詳細指示，請參閱 [流覽並使用報表](navigate-and-utilize-reports.md) 及 [自訂報告](customize-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="e6d37-116">For more detailed instructions, read [Navigating and utilizing the reports](navigate-and-utilize-reports.md) and [Customizing the reports](customize-reports.md).</span></span>

## <a name="executive-summary"></a><span data-ttu-id="e6d37-117">摘要</span><span class="sxs-lookup"><span data-stu-id="e6d37-117">Executive summary</span></span>

<span data-ttu-id="e6d37-118">「執行摘要」是一種高層次、一覽的 Microsoft 365，可供商務採用、使用狀況、行動性、通訊、共同作業和儲存報告，也適用于業務決策者。</span><span class="sxs-lookup"><span data-stu-id="e6d37-118">The executive summary is a high-level, at-a-glance view of Microsoft 365 for Business adoption, usage, mobility, communication, collaboration, and storage reports, and is meant for business decision makers.</span></span> <span data-ttu-id="e6d37-119">它會根據已啟用的所有使用者和使用中的使用者，提供某些個別服務的使用方式。</span><span class="sxs-lookup"><span data-stu-id="e6d37-119">It provides a view into how some individual services are being used, based on all the users who have been enabled and those who are active.</span></span> <span data-ttu-id="e6d37-120">報告上顯示的月份所有值都是指最近的完整月份。</span><span class="sxs-lookup"><span data-stu-id="e6d37-120">All values of the month shown on the report refer to the latest complete month.</span></span> 

<span data-ttu-id="e6d37-121">這項摘要可讓您快速瞭解 Office 的使用模式，以及員工的合作方式和位置。</span><span class="sxs-lookup"><span data-stu-id="e6d37-121">This summary lets you quickly understand usage patterns in Office and how and where your employees are collaborating.</span></span>

![Microsoft 365 使用方式執行摘要的影像。](../../media/office365usage-exec-summary.png)

## <a name="overview"></a><span data-ttu-id="e6d37-123">概觀</span><span class="sxs-lookup"><span data-stu-id="e6d37-123">Overview</span></span>

<span data-ttu-id="e6d37-124">Microsoft 365 綜述報告包含下列報告。</span><span class="sxs-lookup"><span data-stu-id="e6d37-124">The Microsoft 365 overview report contains the following reports.</span></span> <span data-ttu-id="e6d37-125">您可以選擇報表頁面上方的索引標籤來進行查看。</span><span class="sxs-lookup"><span data-stu-id="e6d37-125">You can view them by choosing the tab on top of the report page.</span></span> <span data-ttu-id="e6d37-126">顯示在報表上方區段中的月份所有值，都是最新的完整月份。</span><span class="sxs-lookup"><span data-stu-id="e6d37-126">All values of the month shown on the top section of the report refer to the latest complete month.</span></span>

- <span data-ttu-id="e6d37-127">**採用** &ndash; 提供採用趨勢的完整摘要。</span><span class="sxs-lookup"><span data-stu-id="e6d37-127">**Adoption** &ndash; Offers an all-up summary of adoption trends.</span></span> <span data-ttu-id="e6d37-128">使用本節中的報告，瞭解您的使用者如何採用 Microsoft 365，以及個別服務的整體使用量如何隨月份變更。</span><span class="sxs-lookup"><span data-stu-id="e6d37-128">Use the reports in this section to learn how your users have adopted Microsoft 365, as well as how overall usage of the individual services has changed month over month.</span></span> <span data-ttu-id="e6d37-129">您可以查看如何啟用使用者、組織中的多少人積極使用 Microsoft 365、傳回使用者的數量，以及第一次使用該產品的數目。</span><span class="sxs-lookup"><span data-stu-id="e6d37-129">You can see how may users are enabled, how many people in your organization are actively using Microsoft 365, how many are returning users, and how many are using the product for the first time.</span></span>

- <span data-ttu-id="e6d37-130">**使用** &ndash; 可深入查看使用中使用者的數量，以及最近12個月的每一種產品的主要活動。</span><span class="sxs-lookup"><span data-stu-id="e6d37-130">**Usage** &ndash; Offers a drill-down view into the volume of active users and the key activities for each product for the last 12 months.</span></span> <span data-ttu-id="e6d37-131">使用本節中的報告，瞭解組織中的人員如何使用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e6d37-131">Use the reports in this section to learn how people in your organization are using Microsoft 365.</span></span>

- <span data-ttu-id="e6d37-132">**通訊** &ndash;您可以立即查看組織中的人員是否喜歡使用 Teams、Yammer、電子郵件或 Skype 通話保持聯繫。</span><span class="sxs-lookup"><span data-stu-id="e6d37-132">**Communication** &ndash; You can see at a glance whether people in your organization prefer to stay in touch by using Teams, Yammer, email, or Skype calls.</span></span> <span data-ttu-id="e6d37-133">您可以觀察您的員工在使用通訊工具時，是否有變化的模式。</span><span class="sxs-lookup"><span data-stu-id="e6d37-133">You can observe if there are shifts in patterns in the use of communication tools among your employees.</span></span> 

- <span data-ttu-id="e6d37-134">共同作業 &ndash;請參閱貴組織中的人員如何使用 OneDrive 和 SharePoint 來儲存檔，以及彼此共同作業，以及這些趨勢如何隨月演變。</span><span class="sxs-lookup"><span data-stu-id="e6d37-134">**Collaboration** &ndash; See how people in your organization use OneDrive and SharePoint to store documents and collaborate with each other, and how these trends evolve month over month.</span></span> <span data-ttu-id="e6d37-135">您也可以查看內部或外部共用的檔數量，以及正在使用的 SharePoint 網站或 OneDrive 帳戶數目，由擁有者及其他合作者分割。</span><span class="sxs-lookup"><span data-stu-id="e6d37-135">You can also see how many documents are shared internally or externally and how many SharePoint sites or OneDrive accounts are actively being used, broken out by owners and other collaborators.</span></span>

- <span data-ttu-id="e6d37-136">**儲存體** &ndash;使用此報告可追蹤信箱、OneDrive 和 SharePoint 網站的雲端儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e6d37-136">**Storage** &ndash; Use this report to track cloud storage for mailboxes, OneDrive, and SharePoint sites.</span></span>

- <span data-ttu-id="e6d37-137">**行動性** &ndash;追蹤人員和裝置用來連線到電子郵件、Teams、Skype 或 Yammer 的用戶端和裝置。</span><span class="sxs-lookup"><span data-stu-id="e6d37-137">**Mobility** &ndash; Track which clients and devices people use to connect to email, Teams, Skype, or Yammer.</span></span>

## <a name="activation-and-licensing"></a><span data-ttu-id="e6d37-138">啟用和授權</span><span class="sxs-lookup"><span data-stu-id="e6d37-138">Activation and licensing</span></span>

<span data-ttu-id="e6d37-139">「啟用與授權」頁面提供 Microsoft 365 啟用的報告;也就是有多少使用者已下載和啟用 Office 的應用程式，以及您的組織已指派多少個授權。</span><span class="sxs-lookup"><span data-stu-id="e6d37-139">The activation and license page offers reports on Microsoft 365 activation; that is, how many users have downloaded and activated Office apps and how many licenses have been assigned by your organization.</span></span> <span data-ttu-id="e6d37-140">朝上的月值指的是目前的月，而度量值會反映從當月開始到目前日期的匯總值。</span><span class="sxs-lookup"><span data-stu-id="e6d37-140">The month value towards the top refers to the current month, and the metrics reflect values aggregated from the beginning of the month to the current date.</span></span>

- <span data-ttu-id="e6d37-141">**啟用** &ndash;追蹤服務方案 (例如，Microsoft 365 Apps 企業版、Project 和 Visio) 組織中的啟用。</span><span class="sxs-lookup"><span data-stu-id="e6d37-141">**Activation** &ndash; Track service plan (for example, Microsoft 365 Apps for enterprise, Project, and Visio) activations in your organization.</span></span> <span data-ttu-id="e6d37-142">擁有 Office 授權的每個人員都能在多達五部裝置上安裝產品。</span><span class="sxs-lookup"><span data-stu-id="e6d37-142">Each person with an Office license can install products on up to five devices.</span></span> <span data-ttu-id="e6d37-143">您也可以使用本節中的報告，查看人員已安裝 Office 應用程式的裝置。</span><span class="sxs-lookup"><span data-stu-id="e6d37-143">You can also use reports in this section to see the devices on which people have installed Office apps.</span></span> <span data-ttu-id="e6d37-144">請注意，若要啟動計畫，使用者必須安裝應用程式，並以其帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="e6d37-144">Note that to activate a plan, a user must install the app and sign in with their account.</span></span>

- <span data-ttu-id="e6d37-145">**授權** &ndash; 此報告包含授權類型、指派每個授權類型的使用者計數，以及每個月的授權指派發佈的概述。</span><span class="sxs-lookup"><span data-stu-id="e6d37-145">**Licensing** &ndash; This report contains an overview of license types, the count of users who were assigned each license type, and the license assignment distribution for each month.</span></span> <span data-ttu-id="e6d37-146">朝上的月值指的是目前的月，而度量值會反映從當月開始到目前日期的匯總值。</span><span class="sxs-lookup"><span data-stu-id="e6d37-146">The month value towards the top refers to the current month, and the metrics reflect values aggregated from the beginning of the month to the current date.</span></span>

## <a name="product-usage"></a><span data-ttu-id="e6d37-147">產品使用</span><span class="sxs-lookup"><span data-stu-id="e6d37-147">Product usage</span></span>

<span data-ttu-id="e6d37-148">此報告包含每個 Microsoft 365 服務的個別報告，包括 Exchange、Microsoft 365 群組、OneDrive、SharePoint、Skype、Teams 和 Yammer。</span><span class="sxs-lookup"><span data-stu-id="e6d37-148">This report contains a separate report for each Microsoft 365 service, including Exchange, Microsoft 365 groups, OneDrive, SharePoint, Skype, Teams, and Yammer.</span></span> <span data-ttu-id="e6d37-149">每個報告都包含 [啟用總數] 和 [總使用中使用者] 報告、實體的計數、網站、群組和帳戶，以及活動類型報告（適當位置）。</span><span class="sxs-lookup"><span data-stu-id="e6d37-149">Each report contains total enabled vs. total active user reports, counts of entities such as mailboxes, sites, groups, and accounts, as well as activity type reports where appropriate.</span></span> <span data-ttu-id="e6d37-150">顯示在報表上方區段中的月份所有值，都是最新的完整月份。</span><span class="sxs-lookup"><span data-stu-id="e6d37-150">All values of the month shown on the top section of the report refer to the latest complete month.</span></span>

## <a name="user-activity"></a><span data-ttu-id="e6d37-151">使用者活動</span><span class="sxs-lookup"><span data-stu-id="e6d37-151">User activity</span></span>

<span data-ttu-id="e6d37-152">使用者活動報告可用於特定的個別服務。</span><span class="sxs-lookup"><span data-stu-id="e6d37-152">User activity reports are available for certain individual services.</span></span> <span data-ttu-id="e6d37-153">這些報告提供使用 Active Directory 屬性加入的使用者層級詳細資料使用方式資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-153">These reports provide user-level detail usage data joined with Active Directory attributes.</span></span> <span data-ttu-id="e6d37-154">此外，「部門採用」報告可讓您透過 Active Directory 屬性進行切分，這樣您就可以在所有個別服務上看到作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="e6d37-154">In addition, the Department Adoption report lets you slice by Active Directory attributes so that you can see active users across all individual services.</span></span> <span data-ttu-id="e6d37-155">所有度量都是以最新的完整月份為匯總。</span><span class="sxs-lookup"><span data-stu-id="e6d37-155">All metrics are aggregated for the latest complete month.</span></span>

## <a name="faq"></a><span data-ttu-id="e6d37-156">常見問題集</span><span class="sxs-lookup"><span data-stu-id="e6d37-156">FAQ</span></span>

### <a name="is-this-template-app-going-to-be-available-through-purchase-or-will-it-be-free"></a><span data-ttu-id="e6d37-157">這個範本應用程式是否可透過購買取得，或是是免費的？</span><span class="sxs-lookup"><span data-stu-id="e6d37-157">Is this template app going to be available through purchase or will it be free?</span></span>

<span data-ttu-id="e6d37-158">這不是免費的，您將需要 Power BI Pro 授權。</span><span class="sxs-lookup"><span data-stu-id="e6d37-158">It is not free, you will need a Power BI Pro license.</span></span> <span data-ttu-id="e6d37-159">如需詳細資訊，請參閱安裝、自訂及發佈範本應用程式的 [必要條件](/power-bi/service-template-apps-install-distribute#prerequisites) 。</span><span class="sxs-lookup"><span data-stu-id="e6d37-159">For details see [prerequisites](/power-bi/service-template-apps-install-distribute#prerequisites) for installing, customizing, and distributing a template app.</span></span>

<span data-ttu-id="e6d37-160">若要與其他人共用儀表板，請參閱 [共用儀表板和報告](/power-bi/service-how-to-collaborate-distribute-dashboards-reports#share-dashboards-and-reports)。</span><span class="sxs-lookup"><span data-stu-id="e6d37-160">To share the dashboards with others, please see more at [Share dashboards and reports](/power-bi/service-how-to-collaborate-distribute-dashboards-reports#share-dashboards-and-reports).</span></span>
### <a name="is-the-usage-summary-reports-reader-role-enough-to-view-the-usage-analytics"></a><span data-ttu-id="e6d37-161">使用狀況摘要報告讀取器角色是否足以查看流量分析？</span><span class="sxs-lookup"><span data-stu-id="e6d37-161">Is the Usage Summary Reports Reader role enough to view the usage analytics?</span></span>

<span data-ttu-id="e6d37-162">流量摘要報告讀取器角色只允許存取租使用者層級匯總 Microsoft 365 流量分析。</span><span class="sxs-lookup"><span data-stu-id="e6d37-162">The Usage Summary Reports Reader role only allows access to tenant level aggregates in Microsoft 365 usage analytics.</span></span>  <span data-ttu-id="e6d37-163">我們建議將「報告讀取者」或「使用狀況摘要報告讀取者」角色，加入負責變更管理和採用的任何人員，但不一定是 IT 管理員。</span><span class="sxs-lookup"><span data-stu-id="e6d37-163">We recommend the Reports Reader or Usage Summary Reports Reader role to anyone who's responsible for change management and adoption, but is not necessarily an IT administrator.</span></span>

### <a name="who-can-connect-to-microsoft-365-usage-analytics"></a><span data-ttu-id="e6d37-164">誰可以連線到 Microsoft 365 使用情況分析？</span><span class="sxs-lookup"><span data-stu-id="e6d37-164">Who can connect to Microsoft 365 usage analytics?</span></span>

<span data-ttu-id="e6d37-165">您必須是 **全域系統管理員**、Exchange 系統 **管理員**、**商務用 Skype** 系統管理員、 **SharePoint** 系統管理員、**全域讀取器** 或 **報告讀取** 者，才能建立與範本應用程式的連線。</span><span class="sxs-lookup"><span data-stu-id="e6d37-165">You have to be either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** in order to establish the connection to the template app.</span></span> <span data-ttu-id="e6d37-166">如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md) 。</span><span class="sxs-lookup"><span data-stu-id="e6d37-166">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span>

### <a name="who-can-customize-the-usage-analytics-reports"></a><span data-ttu-id="e6d37-167">神秘可以自訂使用方式分析報告？</span><span class="sxs-lookup"><span data-stu-id="e6d37-167">Who can customize the usage analytics reports?</span></span>

<span data-ttu-id="e6d37-168">只有初次連接至範本應用程式的使用者，才可以自訂報表或在 Power BI web 介面中建立新的報表。</span><span class="sxs-lookup"><span data-stu-id="e6d37-168">Only the user who made the initial connection to the template app can customize the reports or create new reports in the Power BI web interface.</span></span> <span data-ttu-id="e6d37-169">如需相關指示，請參閱[自訂報告 Microsoft 365 流量分析](customize-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="e6d37-169">See [Customizing the reports in Microsoft 365 usage analytics](customize-reports.md) for instructions.</span></span>

### <a name="can-i-only-customize-the-reports-from-the-power-bi-web-interface"></a><span data-ttu-id="e6d37-170">我是否可以只從 Power BI 網頁介面自訂報告？</span><span class="sxs-lookup"><span data-stu-id="e6d37-170">Can I only customize the reports from the Power BI web interface?</span></span>

<span data-ttu-id="e6d37-171">除了從 Power BI 網頁介面自訂報告之外，使用者也可以使用 Power BI Desktop 直接連線至 Microsoft 365 報表服務，以建立自己的報告。</span><span class="sxs-lookup"><span data-stu-id="e6d37-171">In addition to customizing the reports from the Power BI web interface, users can also use Power BI Desktop to connect directly to the Microsoft 365 reporting service to build their own reports.</span></span>

### <a name="how-can-i-get-the-pbit-file-that-this-dashboard-is-associated-with"></a><span data-ttu-id="e6d37-172">如何取得此儀表板相關聯的 pbit 檔案？</span><span class="sxs-lookup"><span data-stu-id="e6d37-172">How can I get the pbit file that this dashboard is associated with?</span></span>

<span data-ttu-id="e6d37-173">您可以從 [Microsoft 下載中心](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)存取 pbit 檔案。</span><span class="sxs-lookup"><span data-stu-id="e6d37-173">You can access to the pbit file from the [Microsoft Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span>

### <a name="who-can-view-the-dashboards-and-reports"></a><span data-ttu-id="e6d37-174">神秘可以查看儀表板和報告？</span><span class="sxs-lookup"><span data-stu-id="e6d37-174">Who can view the dashboards and reports?</span></span>

<span data-ttu-id="e6d37-175">如果您已連線至範本應用程式，您可以使用 [共用功能](/power-bi/collaborate-share/service-share-dashboards)與任何人共用。</span><span class="sxs-lookup"><span data-stu-id="e6d37-175">If you connected to the template app, you can share it with anybody by using the [sharing functionality](/power-bi/collaborate-share/service-share-dashboards).</span></span> <span data-ttu-id="e6d37-176">Power BI 授權要求共用儀表板的使用者和使用者皆 Power BI Pro 或 Power BI Premium。</span><span class="sxs-lookup"><span data-stu-id="e6d37-176">Power BI licensing requires that both the user sharing and the user with whom a dashboard is shared have Power BI Pro or Power BI Premium.</span></span>

### <a name="can-anyone-share-the-dashboard-or-does-it-have-to-be-the-person-who-connected-to-the-dashboard"></a><span data-ttu-id="e6d37-177">是否任何人都可以共用儀表板，或者必須是已連線到儀表板的人員？</span><span class="sxs-lookup"><span data-stu-id="e6d37-177">Can anyone share the dashboard, or does it have to be the person who connected to the dashboard?</span></span>

<span data-ttu-id="e6d37-178">共用儀表板時，您可以允許使用者重新與其他人共用儀表板。</span><span class="sxs-lookup"><span data-stu-id="e6d37-178">When sharing the dashboard, you can either allow users to re-share the dashboard with others or not.</span></span> <span data-ttu-id="e6d37-179">您可以在共用時設定此選項。</span><span class="sxs-lookup"><span data-stu-id="e6d37-179">You can set this option at the time of sharing.</span></span>

### <a name="is-it-possible-to-work-on-and-customize-the-same-template-app-with-a-group-of-people"></a><span data-ttu-id="e6d37-180">是否可以使用和自訂使用者群組的相同範本應用程式？</span><span class="sxs-lookup"><span data-stu-id="e6d37-180">Is it possible to work on and customize the same template app with a group of people?</span></span>

<span data-ttu-id="e6d37-181">是。</span><span class="sxs-lookup"><span data-stu-id="e6d37-181">Yes.</span></span> <span data-ttu-id="e6d37-182">若要讓一組系統管理員能夠在相同的範本應用程式上共同作業，您可以運用 Power BI 的應用程式工作區功能。如需詳細資訊，請參閱[我應該如何共同作業及共用儀表板和報告？](/power-bi/collaborate-share/service-how-to-collaborate-distribute-dashboards-reports)</span><span class="sxs-lookup"><span data-stu-id="e6d37-182">To enable a group of admins to work together on the same template app, you can leverage the app workspace functionality of Power BI, for more information, see [How should I collaborate and share dashboards and reports?](/power-bi/collaborate-share/service-how-to-collaborate-distribute-dashboards-reports)</span></span> 

### <a name="for-which-timeframe-is-data-available"></a><span data-ttu-id="e6d37-183">可提供哪個時間範圍內的資料？</span><span class="sxs-lookup"><span data-stu-id="e6d37-183">For which timeframe is data available?</span></span>

<span data-ttu-id="e6d37-184">大部分報告會顯示前12個月的資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-184">The majority of the reports display data for the previous 12 months.</span></span> <span data-ttu-id="e6d37-185">不過，部分圖表可能會顯示較少的史，因為不同產品和報告的資料收集會在不同的時間啟動，因此可能無法使用完整12個月的資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-185">However, some of the charts may show less history since the data collection for different products and reports were started at different times and thus data for the full 12 months might not be available.</span></span> <span data-ttu-id="e6d37-186">所有報告最後會建立最多12個月的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="e6d37-186">All the reports will eventually build up to 12 months of history.</span></span> <span data-ttu-id="e6d37-187">顯示使用者層級詳細資料的報告會顯示前一個完整月份的資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-187">Reports that show user level details show data for the previous complete month.</span></span>

### <a name="what-data-is-included-in-the-template-app"></a><span data-ttu-id="e6d37-188">範本應用程式中所包含的資料為何？</span><span class="sxs-lookup"><span data-stu-id="e6d37-188">What data is included in the template app?</span></span>

<span data-ttu-id="e6d37-189">範本應用程式中的資料目前涵蓋 [活動報告](../activity-reports/activity-reports.md)中所提供的相同一組活動計量。</span><span class="sxs-lookup"><span data-stu-id="e6d37-189">The data in the template app currently covers the same set of activity metrics available in the [Activity Reports](../activity-reports/activity-reports.md).</span></span> <span data-ttu-id="e6d37-190">當報告新增至活動報告時，將在未來的版本中新增至範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6d37-190">As reports are added to the activity reports, they will be added to the template app in a future release.</span></span>

### <a name="how-does-the-data-in-the-template-app-differ-from-the-data-in-the-usage-reports"></a><span data-ttu-id="e6d37-191">範本應用程式中的資料與使用狀況報告中的資料有何差異？</span><span class="sxs-lookup"><span data-stu-id="e6d37-191">How does the data in the template app differ from the data in the usage reports?</span></span>

<span data-ttu-id="e6d37-192">您在範本應用程式中所看到的基礎資料，會比對 Microsoft 365 系統管理中心的活動報告中所看到的資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-192">The underlying data you see in the template app matches the data you see in the activity reports in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e6d37-193">主要差異在於，在「系統管理中心」資料中的「系統管理中心」資料可用於過去的7/30/90/180 天，而範本應用程式每月顯示最多12個月的資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-193">The key differences are that in the admin center data is available for the last 7/30/90/180 days while the template app presents data on a monthly basis for up to 12 months.</span></span>

<span data-ttu-id="e6d37-194">此外，範本應用程式中的使用者層級詳細資料只適用于已獲指派產品授權並執行活動的使用者的最後一個完整月份。</span><span class="sxs-lookup"><span data-stu-id="e6d37-194">In addition, user level details in the template app are only available for the last complete month for users who were assigned a product license and performed an activity.</span></span>

### <a name="when-should-i-use-the-template-app-and-when-the-usage-reports"></a><span data-ttu-id="e6d37-195">何時應該使用範本應用程式以及使用方式報告？</span><span class="sxs-lookup"><span data-stu-id="e6d37-195">When should I use the template app and when the usage reports?</span></span>

<span data-ttu-id="e6d37-196">「[活動報告](../activity-reports/activity-reports.md)」是瞭解 Microsoft 365 的使用狀況和採用狀況的良好起點。</span><span class="sxs-lookup"><span data-stu-id="e6d37-196">The [Activity Reports](../activity-reports/activity-reports.md)  are a good starting point to understand usage and adoption of Microsoft 365.</span></span> <span data-ttu-id="e6d37-197">範本應用程式會結合 Microsoft 365 使用方式資料和組織的 Active Directory 資訊，並讓系統管理員使用 Power BI 的視覺分析功能來分析資料集。</span><span class="sxs-lookup"><span data-stu-id="e6d37-197">The template app combines the Microsoft 365 usage data and your organization’s Active Directory information and enables admins to analyze the data set using the visual analytics capabilities of Power BI.</span></span> <span data-ttu-id="e6d37-198">這可讓系統管理員不只是視覺化和分析 Microsoft 365 使用狀況資料，也可以透過 Active Directory 屬性（例如部門、位置等）加以切分。他們也可以建立自訂報告，並在其組織中共用洞察力。</span><span class="sxs-lookup"><span data-stu-id="e6d37-198">This enables admins to not just visualize and analyze Microsoft 365 usage data, but also slice it by Active Directory properties such as departments, location etc. They can also create custom reports and share the insights within their organization.</span></span> 

### <a name="how-often-is-the-data-refreshed"></a><span data-ttu-id="e6d37-199">資料重新整理的頻率為何？</span><span class="sxs-lookup"><span data-stu-id="e6d37-199">How often is the data refreshed?</span></span> 

<span data-ttu-id="e6d37-200">當您第一次連線至範本應用程式時，它會自動填入前12個月的資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-200">When you connect to the template app for the first time, it will automatically populate with your data for the previous 12 months.</span></span> <span data-ttu-id="e6d37-201">之後，範本應用程式資料將會重新整理一周。</span><span class="sxs-lookup"><span data-stu-id="e6d37-201">After that, the template app data will refresh weekly.</span></span> <span data-ttu-id="e6d37-202">客戶可以選擇修改重新整理排程，如果其使用此資料要求不同的更新 rhythm。</span><span class="sxs-lookup"><span data-stu-id="e6d37-202">Customers can choose to modify the refresh schedule if their use of this data demands a different update rhythm.</span></span>

<span data-ttu-id="e6d37-203">後端 Microsoft 365 服務會每日重新整理資料，並提供介於5-8 天（從目前日期）的資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-203">The back-end Microsoft 365 service will refresh data on a daily basis and provides data that is between 5-8 days latent from the current date.</span></span>

<span data-ttu-id="e6d37-204">每個資料集中的 [ **內容日期** ] 欄代表範本應用程式中資料的新鮮度日期。</span><span class="sxs-lookup"><span data-stu-id="e6d37-204">The **Content date** column in each dataset represents the freshness date of the data in the template app.</span></span>

### <a name="how-is-an-active-user-defined"></a><span data-ttu-id="e6d37-205">如何定義作用中使用者？</span><span class="sxs-lookup"><span data-stu-id="e6d37-205">How is an active user defined?</span></span>

<span data-ttu-id="e6d37-206">作用中使用者的定義與活動報告中的作用中 [使用者](../activity-reports/active-users.md) 的定義相同。</span><span class="sxs-lookup"><span data-stu-id="e6d37-206">The definition of active user is the same as the definition of [active user](../activity-reports/active-users.md) in the activity reports.</span></span>

### <a name="what-sharepoint-site-collections-are-included-in-the-sharepoint-reports"></a><span data-ttu-id="e6d37-207">SharePoint 報告包含哪些 SharePoint 網站集合？</span><span class="sxs-lookup"><span data-stu-id="e6d37-207">What SharePoint site collections are included in the SharePoint reports?</span></span>

<span data-ttu-id="e6d37-208">目前的範本應用程式版本包括來自 SharePoint 小組網站的檔案活動，以及 SharePoint 群組網站。</span><span class="sxs-lookup"><span data-stu-id="e6d37-208">The current version of the template app includes file activity from SharePoint team sites and SharePoint group sites.</span></span>

### <a name="which-groups-are-included-in-the-microsoft-365-groups-usage-report"></a><span data-ttu-id="e6d37-209">Microsoft 365 群組使用量報告中包含哪些群組？</span><span class="sxs-lookup"><span data-stu-id="e6d37-209">Which groups are included in the Microsoft 365 Groups usage report?</span></span>

<span data-ttu-id="e6d37-210">目前的範本應用程式版本包括 Outlook 群組、Yammer 群組和 SharePoint 群組的使用方式。</span><span class="sxs-lookup"><span data-stu-id="e6d37-210">The current version of the template app includes usage from Outlook groups, Yammer groups, and SharePoint groups.</span></span> <span data-ttu-id="e6d37-211">不包括與 Microsoft Teams 或 Planner 相關的群組。</span><span class="sxs-lookup"><span data-stu-id="e6d37-211">It does not include groups related to Microsoft Teams or Planner.</span></span>

### <a name="when-will-an-updated-version-of-the-template-app-become-available"></a><span data-ttu-id="e6d37-212">何時將範本應用程式的更新版本變為可用？</span><span class="sxs-lookup"><span data-stu-id="e6d37-212">When will an updated version of the template app become available?</span></span>

<span data-ttu-id="e6d37-213">範本應用程式的主要變更會發佈兩年兩次（可能包含新的報表或新的資料）。</span><span class="sxs-lookup"><span data-stu-id="e6d37-213">Major changes to the template app will be released twice a year which may include new reports or new data.</span></span> <span data-ttu-id="e6d37-214">報告的次要變更可能會在較頻繁的基礎上發佈。</span><span class="sxs-lookup"><span data-stu-id="e6d37-214">Minor changes to the reports may be released on a more frequent basis.</span></span>

### <a name="is-it-possible-to-integrate-the-data-from-the-template-app-into-existing-solutions"></a><span data-ttu-id="e6d37-215">是否可以將範本應用程式中的資料整合到現有的解決方案中？</span><span class="sxs-lookup"><span data-stu-id="e6d37-215">Is it possible to integrate the data from the template app into existing solutions?</span></span> 

<span data-ttu-id="e6d37-216">您可以透過預覽) 中的 Microsoft 365 APIs (來檢索範本應用程式中的資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-216">The data in the template app can be retrieved through the Microsoft 365 APIs (in preview).</span></span> <span data-ttu-id="e6d37-217">當他們運送生產產品時，將會在[Microsoft Graph 報告 APIs](https://go.microsoft.com/fwlink/p/?linkid=848843)內合併。</span><span class="sxs-lookup"><span data-stu-id="e6d37-217">When they ship to production they will be merged within the [Microsoft Graph reporting APIs](https://go.microsoft.com/fwlink/p/?linkid=848843).</span></span> 

### <a name="are-there-plans-to-expand-the-template-app-to-show-usage-data-from-other-microsoft-products"></a><span data-ttu-id="e6d37-218">是否有任何計畫展開範本應用程式來顯示其他 Microsoft 產品的使用方式資料？</span><span class="sxs-lookup"><span data-stu-id="e6d37-218">Are there plans to expand the template app to show usage data from other Microsoft products?</span></span>

<span data-ttu-id="e6d37-219">這會考慮未來的改進。</span><span class="sxs-lookup"><span data-stu-id="e6d37-219">This is considered for future improvements.</span></span> <span data-ttu-id="e6d37-220">檢查[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)是否有更新。</span><span class="sxs-lookup"><span data-stu-id="e6d37-220">Check the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) for updates.</span></span>

### <a name="how-can-i-pivot-by-company-information-in-active-directory"></a><span data-ttu-id="e6d37-221">如何使用 Active Directory 中的公司資訊進行樞紐分析？</span><span class="sxs-lookup"><span data-stu-id="e6d37-221">How can I pivot by company information in Active Directory?</span></span>

<span data-ttu-id="e6d37-222">「公司資訊」會包含在範本應用程式中的其中一個 Active Directory 欄位，您可以在 **產品使用者活動** 報告中將其看作預先建立的篩選器。</span><span class="sxs-lookup"><span data-stu-id="e6d37-222">Company information is included one of the Active Directory fields in the template app and you can see it as a pre-built filter in the **Product User activity** reports.</span></span> <span data-ttu-id="e6d37-223">可在 **UserState** 表格中做為欄。</span><span class="sxs-lookup"><span data-stu-id="e6d37-223">It is available as column in the **UserState** table.</span></span>

### <a name="is-it-possible-to-bring-in-additional-fields-from-active-directory"></a><span data-ttu-id="e6d37-224">是否可以帶入來自 Active Directory 的其他欄位？</span><span class="sxs-lookup"><span data-stu-id="e6d37-224">Is it possible to bring in additional fields from Active Directory?</span></span>

<span data-ttu-id="e6d37-225">您可以連線至[Microsoft Graph 報告 APIs](https://go.microsoft.com/fwlink/p/?linkid=848843)以從 Azure Active Directory 中拉入其他欄位，並加入至 dataset，以進一步自訂此資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-225">Additional customization on this data is possible by connecting to the [Microsoft Graph reporting APIs](https://go.microsoft.com/fwlink/p/?linkid=848843) to pull additional fields from Azure Active Directory and join to the dataset.</span></span> 

### <a name="is-it-possible-to-aggregate-the-information-in-the-template-app-across-multiple-subscriptions"></a><span data-ttu-id="e6d37-226">是否可以在多個訂閱中匯總範本應用程式中的資訊？</span><span class="sxs-lookup"><span data-stu-id="e6d37-226">Is it possible to aggregate the information in the template app across multiple subscriptions?</span></span>

<span data-ttu-id="e6d37-227">此時，範本應用程式是針對單一訂閱，因為它與用來建立初始連線的認證相關聯。</span><span class="sxs-lookup"><span data-stu-id="e6d37-227">At this time, the template app is for a single subscription, as it is associated with the credentials that was used to initially connect to it.</span></span>

### <a name="is-it-possible-to-see-usage-by-plan-ie-e1-e3"></a><span data-ttu-id="e6d37-228">使用 plan (（即 E1、E3) ，是否可以查看使用方式）？</span><span class="sxs-lookup"><span data-stu-id="e6d37-228">Is it possible to see usage by plan (i.e. E1, E3)?</span></span>

<span data-ttu-id="e6d37-229">在範本應用程式中，使用方式是以每個產品層級來表示。</span><span class="sxs-lookup"><span data-stu-id="e6d37-229">In the template app, usage is represented at the per product level.</span></span> <span data-ttu-id="e6d37-230">會提供指派給使用者之各種訂閱的相關資料，但不可能將使用者活動與指派給使用者的訂閱建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e6d37-230">Data about the various subscriptions that are assigned to users are provided, however it is not possible to correlate user activity to the subscription assigned to user.</span></span>

### <a name="is-it-possible-to-integrate-other-data-sets-into-the-template-app"></a><span data-ttu-id="e6d37-231">是否可以將其他資料集整合至範本應用程式？</span><span class="sxs-lookup"><span data-stu-id="e6d37-231">Is it possible to integrate other data sets into the template app?</span></span>

<span data-ttu-id="e6d37-232">您可以使用 Power BI Desktop 連線到預覽) 中的 Microsoft 365 APIs (，以將其他資料來源與範本應用程式資料合併。</span><span class="sxs-lookup"><span data-stu-id="e6d37-232">You can use Power BI Desktop to connect to the Microsoft 365 APIs (in preview) to bring additional data sources to combine with the template app data.</span></span>

<span data-ttu-id="e6d37-233">如需詳細資訊，請參閱 [自訂檔](customize-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="e6d37-233">For more information see the [Customize document](customize-reports.md).</span></span>

### <a name="is-it-possible-to-see-the-top-users-reports-for-a-specific-timeframe"></a><span data-ttu-id="e6d37-234">是否可以查看特定時間範圍的「主要使用者」報告？</span><span class="sxs-lookup"><span data-stu-id="e6d37-234">Is it possible to see the "Top Users" reports for a specific timeframe?</span></span>

<span data-ttu-id="e6d37-235">所有使用者層級報表都顯示上個月的匯總資料。</span><span class="sxs-lookup"><span data-stu-id="e6d37-235">All user level reports present aggregated data for the previous month.</span></span>

### <a name="will-the-template-app-be-localized"></a><span data-ttu-id="e6d37-236">範本應用程式是否會當地語系化？</span><span class="sxs-lookup"><span data-stu-id="e6d37-236">Will the template app be localized?</span></span> 

<span data-ttu-id="e6d37-237">這目前不在藍圖上。</span><span class="sxs-lookup"><span data-stu-id="e6d37-237">This is currently not on the roadmap.</span></span>

### <a name="i-have-a-specific-question-about-the-data-im-seeing-for-my-organization-who-can-i-reach-out-to"></a><span data-ttu-id="e6d37-p134">有關我在組織所看到之資料的特定問題。我可以跟誰連絡？</span><span class="sxs-lookup"><span data-stu-id="e6d37-p134">I have a specific question about the data I'm seeing for my organization. Who can I reach out to?</span></span>

<span data-ttu-id="e6d37-240">您可以使用系統管理中心的 [活動一覽表] 頁面上的 [回饋] 按鈕，也可以開啟 [支援案例](../../business-video/get-help-support.md) 以取得範本應用程式的說明。</span><span class="sxs-lookup"><span data-stu-id="e6d37-240">You can use the feedback button in the admin center activity overview page, or you can open a [support case](../../business-video/get-help-support.md) to get help with the template app.</span></span> 

### <a name="how-can-partners-access-the-data"></a><span data-ttu-id="e6d37-241">合作夥伴如何存取資料？</span><span class="sxs-lookup"><span data-stu-id="e6d37-241">How can partners access the data?</span></span>

<span data-ttu-id="e6d37-242">如果合作夥伴已委派系統管理員許可權，則其可代表其客戶連線至範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6d37-242">If a partner has delegated admin rights, he or she can connect to the template app on behalf of their customer.</span></span>

### <a name="can-i-hide-identifiable-information-such-as-user-group-and-site-names-in-reports"></a><span data-ttu-id="e6d37-243">是否可以隱藏報告中的使用者、群組和網站名稱等識別資訊？</span><span class="sxs-lookup"><span data-stu-id="e6d37-243">Can I hide identifiable information such as user, group, and site names in reports?</span></span>

<span data-ttu-id="e6d37-244">是，請參閱 [使收集的資料成為匿名的](enable-usage-analytics.md#make-the-collected-data-anonymous)。</span><span class="sxs-lookup"><span data-stu-id="e6d37-244">Yes, see [Make the collected data anonymous](enable-usage-analytics.md#make-the-collected-data-anonymous).</span></span>

## <a name="related-content"></a><span data-ttu-id="e6d37-245">相關內容</span><span class="sxs-lookup"><span data-stu-id="e6d37-245">Related content</span></span>

<span data-ttu-id="e6d37-246">[啟用 Microsoft 365 使用情況分析](enable-usage-analytics.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="e6d37-246">[Enable Microsoft 365 usage analytics](enable-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="e6d37-247">[流覽並使用報表 Microsoft 365 流量分析](navigate-and-utilize-reports.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="e6d37-247">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>\
<span data-ttu-id="e6d37-248">[在 Microsoft 365 (的 [影片] 中查看使用狀況報告](../../business-video/act-on-report.md)) </span><span class="sxs-lookup"><span data-stu-id="e6d37-248">[Review usage reports in Microsoft 365](../../business-video/act-on-report.md) (video)</span></span>