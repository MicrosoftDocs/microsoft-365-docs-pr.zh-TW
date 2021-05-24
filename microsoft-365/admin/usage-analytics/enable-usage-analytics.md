---
title: 啟用 Microsoft 365 使用情況分析
f1.keywords:
- CSH
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
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: 瞭解如何使用 Power BI 中的 Microsoft 365 流量分析範本應用程式，來開始收集租使用者的資料。
ms.openlocfilehash: 01923887b4af143d1490e14d59a6174700e6ae93
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635411"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="b7d2c-103">啟用 Microsoft 365 使用情況分析</span><span class="sxs-lookup"><span data-stu-id="b7d2c-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="b7d2c-104">Microsoft 365 美國政府 Community 尚無法使用 Microsoft 365 流量分析。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b7d2c-105">開始之前</span><span class="sxs-lookup"><span data-stu-id="b7d2c-105">Before you begin</span></span>

<span data-ttu-id="b7d2c-106">若要開始使用 Microsoft 365 流量分析，您必須先在 Microsoft 365 系統管理中心中提供資料，然後在 Power BI 中啟動範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
## <a name="get-power-bi"></a><span data-ttu-id="b7d2c-107">取得 Power BI</span><span class="sxs-lookup"><span data-stu-id="b7d2c-107">Get Power BI</span></span>

<span data-ttu-id="b7d2c-108">如果您尚無 Power BI，可以[註冊 Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="b7d2c-109">選取 [**嘗試免費** 註冊試用版] 或 [**立即購買**] 以取得 Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="b7d2c-110">您也可以展開 [**產品**] 以購買 Power BI 的版本。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="b7d2c-111">您需要 Power BI Pro 授權才能安裝、自訂及發佈範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="b7d2c-112">如需詳細資訊，請參閱 [必要條件](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="b7d2c-113">若要共用您的資料，這兩者和您與您共用資料的人員、需要 Power BI Pro 授權，或是內容必須位於[Power BI premium service](/power-bi/service-premium-what-is)的工作區中。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
## <a name="enable-the-template-app"></a><span data-ttu-id="b7d2c-114">啟用範本應用程式</span><span class="sxs-lookup"><span data-stu-id="b7d2c-114">Enable the template app</span></span>

<span data-ttu-id="b7d2c-115">若要啟用範本應用程式，您必須是 **全域系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="b7d2c-116">如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md) 。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="b7d2c-117">在系統管理中心中，移至 [**設定** 的 \> **組織設定** \> **服務**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span> 
    
2. <span data-ttu-id="b7d2c-118">在 [ **服務** ] 索引標籤上，選取 [  **報告**]。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-118">On the **Services** tab, select  **Reports**.</span></span>
    
3. <span data-ttu-id="b7d2c-119">在開啟的 [報告] 面板上，設定 **可讓報表資料 Microsoft 365 Power BI 儲存的流量分析**  \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="b7d2c-120">資料收集程式會在兩到48小時內完成，視租使用者的大小而定。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="b7d2c-121">將會啟用 [**移至 Power BI** ] 按鈕 (當資料收集完成時，) 不再是灰色的。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
## <a name="start-the-template-app"></a><span data-ttu-id="b7d2c-122">啟動範本應用程式</span><span class="sxs-lookup"><span data-stu-id="b7d2c-122">Start the template app</span></span>

<span data-ttu-id="b7d2c-123">若要啟動範本應用程式，您必須是 **全域系統管理員**、**報告讀取** 者、 **Exchange 管理員**、**商務用 Skype 系統管理員** 或 **SharePoint 系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="b7d2c-124">複製租使用者識別碼，然後選取 [**移至 Power BI**]。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="b7d2c-125">當您移到 Power BI 時，進行登入。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="b7d2c-126">然後 -> 從流覽功能表中選取 [應用程式 **取得應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="b7d2c-127">在 [**應用程式**] 索引標籤的 [搜尋] 方塊中輸入 Microsoft 365，然後選取 [ **Microsoft 365 流量分析**] \> **立即取得**。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="b7d2c-128">[![選取 [立即取得]](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="b7d2c-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="b7d2c-129">安裝應用程式之後。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-129">Once the app is installed.</span></span> <span data-ttu-id="b7d2c-130">選取拼貼以開啟它。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="b7d2c-131">選取 [ **流覽應用程式** ] 以查看具有範例資料的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="b7d2c-132">選擇 [**連線**]，將應用程式連線至您組織的資料。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="b7d2c-133">選擇 [**連線**]，在 **連線上 Microsoft 365 流量分析**] 畫面中，輸入 [租使用者識別碼] (不含破折號，) 您在步驟 (1) 中複製，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="b7d2c-134">在下一個畫面中，選取 [ **OAuth2** ] 做為 **驗證方法**[登 \> **入**]。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="b7d2c-135">如果您選擇任何其他驗證方法，則與範本應用程式的連線將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![選擇 Microsoft 帳戶做為驗證方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="b7d2c-137">範本應用程式具現化後，網頁上 Power BI 會提供 Microsoft 365 流量分析儀表板。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="b7d2c-138">儀表板的初次載入需要2到30分鐘。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="b7d2c-139">在 [加入] 中的所有報告中，均提供租使用者層級匯總。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="b7d2c-140">**使用者層級的詳細資料只會在下一個行事曆中的第五個月使用**。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="b7d2c-141">這會影響所有「使用者活動」下的報告 (請參閱[流覽並使用報表 Microsoft 365 流量分析](navigate-and-utilize-reports.md)，以取得如何查看和使用這些報表的秘訣) 。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="b7d2c-142">將收集的資料匿名化</span><span class="sxs-lookup"><span data-stu-id="b7d2c-142">Make the collected data anonymous</span></span>

<span data-ttu-id="b7d2c-143">若要將所有報表收集的資料匿名化，您必須是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="b7d2c-144">這會在報表和範本應用程式中隱藏識別資訊，例如使用者、群組和網站名稱。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="b7d2c-145">在系統管理中心中，移至 [**設定** 的 \> **Org 設定**]，然後在 [**服務**] 索引標籤上選擇 [**報告**]。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="b7d2c-146">選取 [ **報告**]，然後選擇 **顯示匿名識別碼**。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="b7d2c-147">此設定會同時套用至使用狀況報告和範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="b7d2c-148">選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="b7d2c-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="b7d2c-149">相關內容</span><span class="sxs-lookup"><span data-stu-id="b7d2c-149">Related content</span></span>

<span data-ttu-id="b7d2c-150">[關於流量分析](usage-analytics.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="b7d2c-150">[About usage analytics](usage-analytics.md) (article)</span></span>\
<span data-ttu-id="b7d2c-151">[取得最新版的流量分析](get-the-latest-version-of-usage-analytics.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="b7d2c-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="b7d2c-152">[流覽並使用報表 Microsoft 365 流量分析](navigate-and-utilize-reports.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="b7d2c-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>