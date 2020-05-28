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
ms.openlocfilehash: fa0973521f5a5e7e8b9b0fda161a5b4779d64c68
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401503"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="20df2-103">啟用 Microsoft 365 使用情況分析</span><span class="sxs-lookup"><span data-stu-id="20df2-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="20df2-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="20df2-104">The admin center is changing.</span></span> <span data-ttu-id="20df2-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="20df2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="20df2-106">Microsoft 365 的流量分析也適用于 Microsoft 365 美國政府社區。</span><span class="sxs-lookup"><span data-stu-id="20df2-106">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="20df2-107">啟用 Microsoft 365 使用方式分析的步驟</span><span class="sxs-lookup"><span data-stu-id="20df2-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="20df2-108">若要開始使用 Microsoft 365 流量分析，您必須先將資料提供給 Microsoft 365 系統管理中心，然後在 Power BI 中啟動範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="20df2-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="20df2-109">取得 Power BI</span><span class="sxs-lookup"><span data-stu-id="20df2-109">Get Power BI</span></span>

<span data-ttu-id="20df2-110">如果您還沒有 Power BI，可以[註冊 POWER Bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="20df2-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="20df2-111">選取 [**嘗試免費**註冊試用版] 或 [**立即購買**]，以取得 Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="20df2-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="20df2-112">您也可以展開 [**產品**] 以購買 Power BI 的版本。</span><span class="sxs-lookup"><span data-stu-id="20df2-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="20df2-113">您需要具備 Power BI Pro 授權才能安裝、自訂及發佈範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="20df2-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="20df2-114">如需詳細資訊，請參閱[必要條件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="20df2-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="20df2-115">您需要一個 Power BI Pro 授權，以共用您的內容，以及您與其共用的人員，或其內容必須位於高[容量](https://docs.microsoft.com/power-bi/service-premium-what-is)的工作區中。</span><span class="sxs-lookup"><span data-stu-id="20df2-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="20df2-116">啟用範本應用程式</span><span class="sxs-lookup"><span data-stu-id="20df2-116">Enable the template app</span></span>

<span data-ttu-id="20df2-117">若要啟用範本應用程式，您必須是**全域系統管理員**、**報告讀取**者、 **Exchange 系統**管理員、**商務用 Skype 系統管理員**或**SharePoint 管理員**。</span><span class="sxs-lookup"><span data-stu-id="20df2-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="20df2-118">如需詳細資訊，請參閱[關於系統管理員角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="20df2-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="20df2-119">在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="20df2-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="20df2-120">在 [**使用狀況**] 頁面上，找出 [ **Microsoft 365 流量分析**卡]，然後選取 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="20df2-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="20df2-121">在開啟的 [報告] 面板上，設定 [**讓 power BI 的 Microsoft 365 流量分析使用的資料可供** **On** \> **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="20df2-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="20df2-122">這會啟動資料收集程式，並且會在2到48小時內完成，視租使用者的大小而定。</span><span class="sxs-lookup"><span data-stu-id="20df2-122">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="20df2-123">資料收集完成時，將會啟用（不再是灰色） [**移至 POWER BI** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="20df2-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="20df2-124">啟動範本應用程式</span><span class="sxs-lookup"><span data-stu-id="20df2-124">Initiate the template app</span></span>

<span data-ttu-id="20df2-125">若要啟動範本應用程式，您必須是**全域系統管理員**、**報告讀取**者、 **Exchange 系統**管理員、**商務用 Skype 系統管理員**或**SharePoint 管理員**。</span><span class="sxs-lookup"><span data-stu-id="20df2-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="20df2-126">複製租使用者識別碼，然後選取 [**移至 POWER BI**]。</span><span class="sxs-lookup"><span data-stu-id="20df2-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="20df2-127">當您移到 Power BI 時，進行登入。</span><span class="sxs-lookup"><span data-stu-id="20df2-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="20df2-128">從流覽功能表中選取 [App->取得應用程式]。</span><span class="sxs-lookup"><span data-stu-id="20df2-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="20df2-129">在 [**應用程式**] 索引標籤的 [搜尋] 方塊中，輸入 microsoft 365，然後選取 [ **microsoft 365 使用方式分析**] \> **立即取得**。</span><span class="sxs-lookup"><span data-stu-id="20df2-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="20df2-130">[![選取 [立即取得]](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="20df2-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="20df2-131">安裝應用程式之後。</span><span class="sxs-lookup"><span data-stu-id="20df2-131">Once the app is installed.</span></span> <span data-ttu-id="20df2-132">按一下平鋪開啟它。</span><span class="sxs-lookup"><span data-stu-id="20df2-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="20df2-133">按一下 [**流覽應用程式**] 以查看具有範例資料的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20df2-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="20df2-134">按一下 **[連線]** ，將應用程式連線至您組織的資料。</span><span class="sxs-lookup"><span data-stu-id="20df2-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="20df2-135">按一下 [連線 **]** 之後，在 [連線**至 Microsoft 365 流量分析]** 畫面上，輸入您在步驟（1）複製的租使用者識別碼（無短杠），然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="20df2-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="20df2-136">在下一個畫面中，選取 [ **oAuth2** ] 作為**驗證方法**[登 \> **入**]。</span><span class="sxs-lookup"><span data-stu-id="20df2-136">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="20df2-137">如果您選擇任何其他驗證方法，則與範本應用程式的連線將會失敗。</span><span class="sxs-lookup"><span data-stu-id="20df2-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="20df2-139">當範本應用程式範例化後，Microsoft 365 流量分析儀表板將會出現在網路上的 Power BI 中。</span><span class="sxs-lookup"><span data-stu-id="20df2-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="20df2-140">儀表板的初次載入需要2到30分鐘。</span><span class="sxs-lookup"><span data-stu-id="20df2-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="20df2-141">所有報告都提供租使用者層級匯總。</span><span class="sxs-lookup"><span data-stu-id="20df2-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="20df2-142">**使用者層級的詳細資料只會在 [行事曆] 月的第一天或第15天之後變為使用**。</span><span class="sxs-lookup"><span data-stu-id="20df2-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="20df2-143">這會影響所有「使用者活動」下的報告（請參閱[流覽並使用 Microsoft 365 流量分析中的報告](navigate-and-utilize-reports.md)，以取得如何查看和使用這些報告的秘訣）。</span><span class="sxs-lookup"><span data-stu-id="20df2-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="20df2-144">將收集的資料匿名化</span><span class="sxs-lookup"><span data-stu-id="20df2-144">Make the collected data anonymous</span></span>

<span data-ttu-id="20df2-145">若要將所有報表收集的資料匿名化，您必須是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="20df2-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="20df2-146">這會在報表和範本應用程式中隱藏識別資訊，例如使用者、群組和網站名稱。</span><span class="sxs-lookup"><span data-stu-id="20df2-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="20df2-147">在系統管理中心中，移至 [**設定** \> **組織設定**]，然後在 [**服務**] 索引標籤上選擇 [**報告**]。</span><span class="sxs-lookup"><span data-stu-id="20df2-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="20df2-148">選取 [**報告**]，然後選擇**顯示匿名識別碼**。</span><span class="sxs-lookup"><span data-stu-id="20df2-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="20df2-149">此設定會同時套用至使用狀況報告和範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="20df2-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="20df2-150">選取 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20df2-150">Select **Save changes**.</span></span>
