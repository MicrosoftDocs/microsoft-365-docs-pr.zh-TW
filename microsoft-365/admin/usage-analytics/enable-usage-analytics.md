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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: 瞭解如何使用 Power BI 中的 Microsoft 365 流量分析範本應用程式，來開始收集租使用者的資料。
ms.openlocfilehash: 0817e6441540086bf679c6533b1bad2e4087b4b9
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841454"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="26147-103">啟用 Microsoft 365 使用情況分析</span><span class="sxs-lookup"><span data-stu-id="26147-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="26147-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="26147-104">The admin center is changing.</span></span> <span data-ttu-id="26147-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="26147-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="26147-106">Microsoft 365 美國政府社區尚無可用的 microsoft 365 使用方式分析功能。</span><span class="sxs-lookup"><span data-stu-id="26147-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="26147-107">啟用 Microsoft 365 使用方式分析的步驟</span><span class="sxs-lookup"><span data-stu-id="26147-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="26147-108">若要開始使用 Microsoft 365 流量分析，您必須先將資料提供給 Microsoft 365 系統管理中心，然後在 Power BI 中啟動範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="26147-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="26147-109">取得 Power BI</span><span class="sxs-lookup"><span data-stu-id="26147-109">Get Power BI</span></span>

<span data-ttu-id="26147-110">如果您還沒有 Power BI，可以 [註冊 POWER Bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="26147-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="26147-111">選取 [ **嘗試免費** 註冊試用版] 或 [ **立即購買** ]，以取得 Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="26147-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="26147-112">您也可以展開 [ **產品** ] 以購買 Power BI 的版本。</span><span class="sxs-lookup"><span data-stu-id="26147-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="26147-113">您需要具備 Power BI Pro 授權才能安裝、自訂及發佈範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="26147-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="26147-114">如需詳細資訊，請參閱 [必要條件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="26147-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="26147-115">若要共用您的資料，這兩者和您與您共用資料的人員、需要 Power BI Pro 授權，或是內容必須位於 [POWER bi premium 服務](https://docs.microsoft.com/power-bi/service-premium-what-is)的工作區中。</span><span class="sxs-lookup"><span data-stu-id="26147-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="26147-116">啟用範本應用程式</span><span class="sxs-lookup"><span data-stu-id="26147-116">Enable the template app</span></span>

<span data-ttu-id="26147-117">若要啟用範本應用程式，您必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="26147-117">To enable the template app, you have to be one of the following:</span></span> 
- <span data-ttu-id="26147-118">**全域管理員**</span><span class="sxs-lookup"><span data-stu-id="26147-118">**Global administrator**</span></span>
- <span data-ttu-id="26147-119">**報表讀取器**</span><span class="sxs-lookup"><span data-stu-id="26147-119">**Report reader**</span></span>
- <span data-ttu-id="26147-120">**Exchange 系統管理員**</span><span class="sxs-lookup"><span data-stu-id="26147-120">**Exchange administrator**</span></span>
- <span data-ttu-id="26147-121">**商務用 Skype 系統管理員**</span><span class="sxs-lookup"><span data-stu-id="26147-121">**Skype for Business administrator**</span></span>
- <span data-ttu-id="26147-122">**SharePoint 系統管理員**</span><span class="sxs-lookup"><span data-stu-id="26147-122">**SharePoint administrator**</span></span> 
  
<span data-ttu-id="26147-123">如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md) 。</span><span class="sxs-lookup"><span data-stu-id="26147-123">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="26147-124">在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="26147-124">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="26147-125">在 [ **使用狀況** ] 頁面上，找出 [ **Microsoft 365 流量分析** 卡]，然後選取 [ **開始** ]。</span><span class="sxs-lookup"><span data-stu-id="26147-125">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started** .</span></span>
    
3. <span data-ttu-id="26147-126">在開啟的 [報告] 面板上，設定 [ **讓 power BI 的 Microsoft 365 流量分析使用的資料可供** **On** \> **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="26147-126">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save** .</span></span> 
  
<span data-ttu-id="26147-127">資料收集程式會在兩到48小時內完成，視租使用者的大小而定。</span><span class="sxs-lookup"><span data-stu-id="26147-127">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="26147-128">[ **移至 POWER BI** ] 按鈕將會啟用 () 資料收集完成時不再是灰色的。</span><span class="sxs-lookup"><span data-stu-id="26147-128">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="26147-129">啟動範本應用程式</span><span class="sxs-lookup"><span data-stu-id="26147-129">Start the template app</span></span>

<span data-ttu-id="26147-130">若要啟動範本應用程式，您必須是 **全域系統管理員** 、 **報告讀取** 者、 **Exchange 系統** 管理員、 **商務用 Skype 系統管理員** 或 **SharePoint 管理員** 。</span><span class="sxs-lookup"><span data-stu-id="26147-130">To start the template app, you have to be either a **global administrator** , **report reader** , **Exchange administrator** , **Skype for Business administrator** , or **SharePoint administrator** .</span></span> 
  
1. <span data-ttu-id="26147-131">複製租使用者識別碼，然後選取 [ **移至 POWER BI** ]。</span><span class="sxs-lookup"><span data-stu-id="26147-131">Copy the tenant ID and select **Go to Power BI** .</span></span>
    
2.  <span data-ttu-id="26147-132">當您移到 Power BI 時，進行登入。</span><span class="sxs-lookup"><span data-stu-id="26147-132">When you get to Power BI, sign in.</span></span> <span data-ttu-id="26147-133">然後 **Select Apps** -> 從流覽功能表中選取 [應用程式 **取得應用程式** ]。</span><span class="sxs-lookup"><span data-stu-id="26147-133">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="26147-134">在 [ **應用程式** ] 索引標籤的 [搜尋] 方塊中，輸入 microsoft 365，然後選取 [ **microsoft 365 使用方式分析** ] \> **立即取得** 。</span><span class="sxs-lookup"><span data-stu-id="26147-134">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now** .</span></span>

    <span data-ttu-id="26147-135">[![選取 [立即取得]](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="26147-135">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="26147-136">安裝應用程式之後。</span><span class="sxs-lookup"><span data-stu-id="26147-136">Once the app is installed.</span></span> <span data-ttu-id="26147-137">選取拼貼以開啟它。</span><span class="sxs-lookup"><span data-stu-id="26147-137">Select the tile to open it.</span></span>

5.  <span data-ttu-id="26147-138">選取 [ **流覽應用程式** ] 以查看具有範例資料的應用程式。</span><span class="sxs-lookup"><span data-stu-id="26147-138">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="26147-139">選擇 **[連線]，將** 應用程式連線至您組織的資料。</span><span class="sxs-lookup"><span data-stu-id="26147-139">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="26147-140">選擇 **[連線]，** 在 [連線 **至 Microsoft 365 流量分析畫面]** 畫面上，輸入 [租使用者識別碼] (不含破折號) 您已複製步驟 (1) ，然後選取 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="26147-140">Choose **Connect** , on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next** .</span></span>
    
7. <span data-ttu-id="26147-141">在下一個畫面中，選取 [ **OAuth2** ] 做為 **驗證方法** [登 \> **入** ]。</span><span class="sxs-lookup"><span data-stu-id="26147-141">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in** .</span></span> <span data-ttu-id="26147-142">如果您選擇任何其他驗證方法，則與範本應用程式的連線將會失敗。</span><span class="sxs-lookup"><span data-stu-id="26147-142">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![選擇 Microsoft 帳戶做為驗證方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="26147-144">範本應用程式具現化後，Microsoft 365 流量分析儀表板會出現在 web 上的 Power BI 中。</span><span class="sxs-lookup"><span data-stu-id="26147-144">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="26147-145">儀表板的初次載入需要2到30分鐘。</span><span class="sxs-lookup"><span data-stu-id="26147-145">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="26147-146">所有報告都提供租使用者層級匯總。</span><span class="sxs-lookup"><span data-stu-id="26147-146">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="26147-147">**使用者層級的詳細資料只會在 [行事曆] 月的第一天或第15天之後變為使用** 。</span><span class="sxs-lookup"><span data-stu-id="26147-147">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in** .</span></span> <span data-ttu-id="26147-148">這會影響所有「使用者活動的報表。</span><span class="sxs-lookup"><span data-stu-id="26147-148">This will impact all reports under User Activity.</span></span> <span data-ttu-id="26147-149">如需如何查看和使用這些報告的秘訣，請參閱 [流覽並使用 Microsoft 365 使用方式分析中的報告](navigate-and-utilize-reports.md) 。</span><span class="sxs-lookup"><span data-stu-id="26147-149">See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports.</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="26147-150">將收集的資料匿名化</span><span class="sxs-lookup"><span data-stu-id="26147-150">Make the collected data anonymous</span></span>

<span data-ttu-id="26147-151">若要將所有報表收集的資料匿名化，您必須是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="26147-151">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="26147-152">這會在報表和範本應用程式中隱藏識別資訊，例如使用者、群組和網站名稱。</span><span class="sxs-lookup"><span data-stu-id="26147-152">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="26147-153">在系統管理中心中，移至 [ **設定** \> **組織設定** ]，然後在 [ **服務** ] 索引標籤上選擇 [ **報告** ]。</span><span class="sxs-lookup"><span data-stu-id="26147-153">In the admin center, go to the **Settings** \> **Org Settings** , and under **Services** tab, choose **Reports** .</span></span>
    
2. <span data-ttu-id="26147-154">選取 [ **報告** ]，然後選擇 **顯示匿名識別碼** 。</span><span class="sxs-lookup"><span data-stu-id="26147-154">Select **Reports** , and then choose to **Display anonymous identifiers** .</span></span> <span data-ttu-id="26147-155">此設定會同時套用至使用狀況報告和範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="26147-155">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="26147-156">選取 **[儲存變更]** 。</span><span class="sxs-lookup"><span data-stu-id="26147-156">Select **Save changes** .</span></span>
