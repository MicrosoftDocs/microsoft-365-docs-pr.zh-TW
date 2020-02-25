---
title: 啟用 Microsoft 365 使用情況分析
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: 了解如何開始使用 Power BI 中的 Microsoft 365 使用情況分析範本應用程式租用戶收集資料。
ms.openlocfilehash: 651a820916f65a1695b7300772b1d2ce8aee92bb
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240039"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="f4d66-103">啟用 Microsoft 365 使用情況分析</span><span class="sxs-lookup"><span data-stu-id="f4d66-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="f4d66-104">Microsoft 365 使用情況分析也適用於 Microsoft 365 美國政府社群。</span><span class="sxs-lookup"><span data-stu-id="f4d66-104">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="f4d66-105">若要啟用 Microsoft 365 使用情況分析的步驟</span><span class="sxs-lookup"><span data-stu-id="f4d66-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="f4d66-106">若要開始使用 Microsoft 365 使用情況分析，您必須先在 Microsoft 365 系統管理中心中，提供資料，然後啟動 Power BI 中的範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4d66-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="f4d66-107">取得 Power BI</span><span class="sxs-lookup"><span data-stu-id="f4d66-107">Get Power BI</span></span>

<span data-ttu-id="f4d66-108">如果您還沒有 Power BI，您可以[註冊 Power BI 專業版](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="f4d66-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="f4d66-109">選取 [**免費試用**來註冊試用或若要取得 Power BI 專業人員的**立即購買**]。</span><span class="sxs-lookup"><span data-stu-id="f4d66-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="f4d66-110">您也可以展開 [**產品**] 購買其中 Power BI 的版本。</span><span class="sxs-lookup"><span data-stu-id="f4d66-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="f4d66-111">您必須安裝、 自訂及發佈的範本應用程式的 Power BI 專業版授權。</span><span class="sxs-lookup"><span data-stu-id="f4d66-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="f4d66-112">如需詳細資訊，請參閱[必要條件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="f4d66-112">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="f4d66-113">您需要專業 Power BI 的授權，以共用您的內容，以及您將它與共用的人員進行太，或內容必須可在工作區中的[高階容量](https://docs.microsoft.com/power-bi/service-premium-what-is)。</span><span class="sxs-lookup"><span data-stu-id="f4d66-113">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="f4d66-114">啟用範本應用程式</span><span class="sxs-lookup"><span data-stu-id="f4d66-114">Enable the template app</span></span>

<span data-ttu-id="f4d66-115">若要啟用的範本應用程式，您必須是**全域系統管理員**、**報告讀取者**、 **Exchange 系統管理員**、**商務用 Skype 系統管理員**或**SharePoint 系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-115">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="f4d66-116">如需詳細資訊，請參閱[關於系統管理員角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f4d66-116">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="f4d66-117">在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f4d66-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="f4d66-118">在 [**使用狀況**] 頁面上，找出 [ **Microsoft 365 使用情況分析**卡片，並選取**要開始**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="f4d66-119">在報表上會開啟的面板設**使可 Power bi 的 Microsoft 365 使用情況分析的資料\*\*\*\*上** \> **儲存**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="f4d66-120">這會資料收集程序，且會視您的租用戶大小而定的 2 到 48 小時內完成。</span><span class="sxs-lookup"><span data-stu-id="f4d66-120">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="f4d66-121">**移至 Power BI** ] 按鈕將會啟用 （不再灰色） 資料收集完畢時。</span><span class="sxs-lookup"><span data-stu-id="f4d66-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="f4d66-122">啟動的範本應用程式</span><span class="sxs-lookup"><span data-stu-id="f4d66-122">Initiate the template app</span></span>

<span data-ttu-id="f4d66-123">若要啟動的範本應用程式，您必須是**全域系統管理員**、**報告讀取者**、 **Exchange 系統管理員**、**商務用 Skype 系統管理員**或**SharePoint 系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-123">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="f4d66-124">複製租用戶識別碼，然後選取 [**移至 Power BI**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-124">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="f4d66-125">當您移到 Power BI 時，進行登入。</span><span class="sxs-lookup"><span data-stu-id="f4d66-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="f4d66-126">從瀏覽功能表中選取應用程式->取得應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4d66-126">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="f4d66-127">在 [**應用程式**] 索引標籤中，輸入 [搜尋] 方塊中的 Microsoft 365，然後選取 [ **Microsoft 365 使用情況分析** \> **取得它現在**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="f4d66-128">[![選取 [立即取得](../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="f4d66-128">[![Select Get it now](../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="f4d66-129">一旦安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4d66-129">Once the app is installed.</span></span> <span data-ttu-id="f4d66-130">按一下 [上] 磚以開啟它。</span><span class="sxs-lookup"><span data-stu-id="f4d66-130">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="f4d66-131">按一下 [**瀏覽應用程式**來檢視將含有範例資料的應用程式]。</span><span class="sxs-lookup"><span data-stu-id="f4d66-131">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="f4d66-132">按一下 [應用程式連線至您的組織資料的**連線**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-132">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="f4d66-133">按一下之後**連線**，在 [**連線至 Microsoft 365 使用情況分析**] 畫面上，輸入您在步驟 (1) 複製的識別碼在租用戶中\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-133">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id you copied in step (1) \> **Next**.</span></span>
    
7. <span data-ttu-id="f4d66-134">在下一個畫面上，選取**oAuth2**作為**驗證方法** \> **登入**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-134">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="f4d66-135">如果您選擇任何其他驗證方法，將會失敗的範本應用程式的連線。</span><span class="sxs-lookup"><span data-stu-id="f4d66-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="f4d66-137">一旦具現化範本應用程式的 Microsoft 365 流量分析儀表板將可在 Power BI 網頁。</span><span class="sxs-lookup"><span data-stu-id="f4d66-137">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="f4d66-138">儀表板的初始載入需要 2 到 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="f4d66-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="f4d66-139">租用戶層級彙總則可在所有報告。</span><span class="sxs-lookup"><span data-stu-id="f4d66-139">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="f4d66-140">**使用者層級的詳細資訊才會變成可用 1st 或 15 天後選擇中的行事曆月之後**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-140">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="f4d66-141">這會影響使用者活動下的所有報告 (請參閱[瀏覽和運用 Microsoft 365 使用情況分析中的報告](navigate-and-utilize-reports.md)的祕訣如何檢視及使用這些報告)。</span><span class="sxs-lookup"><span data-stu-id="f4d66-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="f4d66-142">將收集的資料匿名化</span><span class="sxs-lookup"><span data-stu-id="f4d66-142">Make the collected data anonymous</span></span>

<span data-ttu-id="f4d66-143">若要將所有報表收集的資料匿名化，您必須是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f4d66-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="f4d66-144">這麼做會隱藏和範本應用程式中報告的使用者、 群組和網站名稱等識別資訊。</span><span class="sxs-lookup"><span data-stu-id="f4d66-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="f4d66-145">在系統管理中心，移至 [**設定** \> **設定**，並在 [**服務**] 索引標籤中，選擇**報告**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-145">In the admin center, go to the **Settings** \> **Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="f4d66-146">選取 [**報告**]，然後再選擇**顯示匿名識別碼**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="f4d66-147">使用狀況報告以及範本應用程式，取得套用此設定。</span><span class="sxs-lookup"><span data-stu-id="f4d66-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="f4d66-148">選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="f4d66-148">Select **Save changes**.</span></span>
