---
title: 在 Microsoft 365 使用方式分析中自訂報告
f1.keywords:
- NOCSH
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
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: 瞭解如何在瀏覽器和 Power BI Desktop 中自訂報告。
ms.openlocfilehash: d36e07a19b0ebda0d154b11723630e38b746eb8d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471086"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="ed517-103">在 Microsoft 365 使用方式分析中自訂報告</span><span class="sxs-lookup"><span data-stu-id="ed517-103">Customize the reports in Microsoft 365 usage analytics</span></span>

<span data-ttu-id="ed517-104">Microsoft 365 流量分析提供 Power BI 中的儀表板，可深入瞭解使用者採用和使用 Microsoft 365 的方式。</span><span class="sxs-lookup"><span data-stu-id="ed517-104">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="ed517-105">儀表板只是與使用狀況資料互動的起點。</span><span class="sxs-lookup"><span data-stu-id="ed517-105">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="ed517-106">您可以自訂報告，以獲得更多個人化洞察力。</span><span class="sxs-lookup"><span data-stu-id="ed517-106">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="ed517-107">您也可以使用 Power BI 桌面來進一步自訂報告，方法是將其連線至其他資料來源，以深入瞭解您的企業。</span><span class="sxs-lookup"><span data-stu-id="ed517-107">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="ed517-108">在瀏覽器中自訂報告</span><span class="sxs-lookup"><span data-stu-id="ed517-108">Customizing reports in the browser</span></span>

<span data-ttu-id="ed517-109">下列兩個範例示範如何修改現有的視覺效果，以及如何建立新的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="ed517-109">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="ed517-110">修改現有的視覺效果</span><span class="sxs-lookup"><span data-stu-id="ed517-110">Modify an existing visual</span></span>

<span data-ttu-id="ed517-111">此範例顯示如何在 **啟用/授權** 報告中修改 [**啟用**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ed517-111">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="ed517-112">在 [ **啟用/授權** ] 報告中，選取 [ **啟用** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ed517-112">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="ed517-113">在 [Power BI] 的 [其他頁面] 按鈕中，選擇上方的 [ **編輯** ] 按鈕，以進入編輯模式 ![ ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 。</span><span class="sxs-lookup"><span data-stu-id="ed517-113">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![按一下右上方導覽中的 [編輯報告]](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="ed517-115">在右上方，選擇 [ **複製此頁面**]。</span><span class="sxs-lookup"><span data-stu-id="ed517-115">On the top right, choose **Duplicate this page**.</span></span>
    
    ![選擇 [複製此頁面]](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="ed517-117">在右下方，選擇顯示根據 OS （如 Android、iOS、Mac 等）啟動之使用者計數的任何橫條圖。</span><span class="sxs-lookup"><span data-stu-id="ed517-117">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="ed517-118">在右側的 **視覺化** 區域中，若要從視覺中移除 **Mac 計數** ，請選取它旁邊的 **X** 。</span><span class="sxs-lookup"><span data-stu-id="ed517-118">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![移除 Mac 計數](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="ed517-120">建立新的視覺</span><span class="sxs-lookup"><span data-stu-id="ed517-120">Create a new visual</span></span>

<span data-ttu-id="ed517-121">下列範例顯示如何建立新的視覺效果，以每月追蹤新的 Yammer 使用者。</span><span class="sxs-lookup"><span data-stu-id="ed517-121">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="ed517-122">使用左導覽移至 [ **產品使用狀況** ] 報告，然後選取 [ **Yammer** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ed517-122">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="ed517-123">選擇 ![ [POWER BI] 和 [編輯] 中的 [更多頁面] 按鈕，切換至編輯模式 ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed517-123">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="ed517-124">在頁面底部，選取</span><span class="sxs-lookup"><span data-stu-id="ed517-124">At the bottom of the page, select the</span></span> ![Power BI 中的 [新增頁面] 按鈕](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="ed517-126">以建立新的頁面。</span><span class="sxs-lookup"><span data-stu-id="ed517-126">to create a new page.</span></span>
  
4. <span data-ttu-id="ed517-127">在右側的 **視覺化** 區域中，選擇 [ **堆疊橫條圖** ] (頂端列（從左) 開始）。</span><span class="sxs-lookup"><span data-stu-id="ed517-127">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![選取橫條圖](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="ed517-129">選取該視覺化效果的右下方，並拖曳以放大顯示。</span><span class="sxs-lookup"><span data-stu-id="ed517-129">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="ed517-130">在右側的 [ **欄位** ] 區域中，展開 [行事 **曆** ] 表格。</span><span class="sxs-lookup"><span data-stu-id="ed517-130">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="ed517-131">將 **MonthName** 拖曳至 [欄位] 區域，其位於 **視覺化** 區域的 [**座標軸**] 標題下方。</span><span class="sxs-lookup"><span data-stu-id="ed517-131">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![拖曳月份名稱](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="ed517-133">在右側的 [ **欄位** ] 區域中，展開 [ **TenantProductUsage** ] 表格。</span><span class="sxs-lookup"><span data-stu-id="ed517-133">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="ed517-134">將 **FirstTimeUsers** 拖曳至 [欄位] 區域，直接在 **值** 標題下方。</span><span class="sxs-lookup"><span data-stu-id="ed517-134">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="ed517-135">將 **產品** 拖曳至 [ **篩選** ] 區域，直接在 [ **視覺層級篩選** ] 標題下。</span><span class="sxs-lookup"><span data-stu-id="ed517-135">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="ed517-136">在出現的 [ **篩選類型** ] 區域中，選取 [ **Yammer** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ed517-136">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![選取 Yammer 核取方塊](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="ed517-138">在視覺效果的清單下方，選擇 [  ![ Power BI Visualizaions] 中的格式圖示格式圖示 ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) 。</span><span class="sxs-lookup"><span data-stu-id="ed517-138">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="ed517-139">按月，展開 [標題]，然後將 [ **標題] 文字** 值變更為 [ **第一次 Yammer] 使用者**。</span><span class="sxs-lookup"><span data-stu-id="ed517-139">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="ed517-140">將 **文字大小** 值變更為 **12**。</span><span class="sxs-lookup"><span data-stu-id="ed517-140">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="ed517-141">在右下方編輯頁面名稱，以變更新頁面的標題。</span><span class="sxs-lookup"><span data-stu-id="ed517-141">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="ed517-142">按一下頂端的 [ **閱讀檢視** ]，然後按一下 [ **儲存**] 來儲存報告。</span><span class="sxs-lookup"><span data-stu-id="ed517-142">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="ed517-143">自訂 Power BI Desktop 中的報表</span><span class="sxs-lookup"><span data-stu-id="ed517-143">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="ed517-144">大多數客戶在 Power BI web 中修改報告和圖表視覺效果的情況都會夠用。</span><span class="sxs-lookup"><span data-stu-id="ed517-144">For most customers modifying the reports and chart visuals in Power BI web will be sufficient.</span></span> <span data-ttu-id="ed517-145">在某些情況下，您可能需要將此資料與其他資料來源結合，以獲得更深入的業務相關內容，在這種情況下，他們可以使用 Power BI Desktop 自訂及建立其他報告。</span><span class="sxs-lookup"><span data-stu-id="ed517-145">For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop.</span></span> <span data-ttu-id="ed517-146">您可以免費下載 [POWER BI desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) 。</span><span class="sxs-lookup"><span data-stu-id="ed517-146">You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="ed517-147">使用報表 APIs</span><span class="sxs-lookup"><span data-stu-id="ed517-147">Use the reporting APIs</span></span>

<span data-ttu-id="ed517-148">您可以開始直接連線至 Microsoft 365 的 ODATA 報告 APIs，以加上這些報告。</span><span class="sxs-lookup"><span data-stu-id="ed517-148">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="ed517-149">移至 [ **取得資料** \> ] **其他** \> **ODATA** 摘要 \> **Connect**。</span><span class="sxs-lookup"><span data-stu-id="ed517-149">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="ed517-150">在 [URL] 視窗中，輸入 "HTTPs:// <i></i> reports.office.com/pbi/v1.0/ \<tenantid\> "</span><span class="sxs-lookup"><span data-stu-id="ed517-150">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="ed517-151">**附注：** 報告 APIs 是在預覽中，且在實際執行之前必須變更。</span><span class="sxs-lookup"><span data-stu-id="ed517-151">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData Power BI desktop 的摘要 URL](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="ed517-153">當系統提示時，請輸入您的 Microsoft 365 (組織或學校) 系統管理員認證，以向 Microsoft 365 驗證。</span><span class="sxs-lookup"><span data-stu-id="ed517-153">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="ed517-154">如需允許存取 Microsoft 365 採用範本應用程式報告之使用者的詳細資訊，請參閱 [FAQ](usage-analytics.md#faq) 。</span><span class="sxs-lookup"><span data-stu-id="ed517-154">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="ed517-155">連線授權後，您將會看到 [Navigator] 視窗，顯示可供連線的資料集。</span><span class="sxs-lookup"><span data-stu-id="ed517-155">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="ed517-156">選取 [全部]，然後選擇 [ **負載**]。</span><span class="sxs-lookup"><span data-stu-id="ed517-156">Select all and choose **Load**.</span></span>
    
    <span data-ttu-id="ed517-157">這會將資料下載到您的 Power BI Desktop。</span><span class="sxs-lookup"><span data-stu-id="ed517-157">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="ed517-158">儲存此檔案，然後您就可以開始建立所需的報告。</span><span class="sxs-lookup"><span data-stu-id="ed517-158">Save this file and then you can start creating the reports you need.</span></span>
    
    ![報告 API 中可用的 ODATA 值](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="ed517-160">使用 Microsoft 365 流量分析範本</span><span class="sxs-lookup"><span data-stu-id="ed517-160">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="ed517-161">您也可以使用與 Microsoft 365 使用方式分析報告對應的 Power BI 範本檔案，作為連接至資料的起點。</span><span class="sxs-lookup"><span data-stu-id="ed517-161">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="ed517-162">使用 pbit 檔案的優點是已建立連接字串。</span><span class="sxs-lookup"><span data-stu-id="ed517-162">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="ed517-163">您也可以利用基礎架構傳回的資料與基礎架構傳回的所有自訂量值，並進一步加以建立。</span><span class="sxs-lookup"><span data-stu-id="ed517-163">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="ed517-164">您可以從 [Microsoft 下載中心](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)下載 Power BI 範本檔案。</span><span class="sxs-lookup"><span data-stu-id="ed517-164">You can download the Power BI template file from the [Microsoft Download Center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="ed517-165">下載 Power BI 範本檔案之後，請遵循下列步驟開始執行：</span><span class="sxs-lookup"><span data-stu-id="ed517-165">After you download the Power BI template file, follow these steps to get started:</span></span>
  
1. <span data-ttu-id="ed517-166">開啟 pbit 檔案。</span><span class="sxs-lookup"><span data-stu-id="ed517-166">Open the pbit file.</span></span>
    
2. <span data-ttu-id="ed517-167">在對話方塊中輸入您的租使用者識別碼值。</span><span class="sxs-lookup"><span data-stu-id="ed517-167">Enter your tenant id value in the dialog.</span></span>
    
    ![輸入您的租使用者識別碼，以開啟 pbit 檔案](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="ed517-169">當系統提示時，請輸入您的系統管理員認證以驗證 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ed517-169">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="ed517-170">以取得允許存取 Microsoft 365 使用方式分析報告之使用者的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ed517-170">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="ed517-171">授權後，就會在 Power BI 檔案中重新整理資料。</span><span class="sxs-lookup"><span data-stu-id="ed517-171">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="ed517-172">資料負載可能需要一些時間，完成後，您可以將檔案儲存為 .pbix 檔案，繼續自訂報告或將額外的資料來源帶入此報告。</span><span class="sxs-lookup"><span data-stu-id="ed517-172">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="ed517-173">遵循 [POWER bi 檔快速](/power-bi/fundamentals/desktop-getting-started) 入門，以瞭解如何建立報表、將其發佈至 Power BI 服務，以及與您的組織共用。</span><span class="sxs-lookup"><span data-stu-id="ed517-173">Follow [Getting started with Power BI](/power-bi/fundamentals/desktop-getting-started) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization.</span></span> <span data-ttu-id="ed517-174">請遵循此路徑進行自訂和共用，可能需要額外的 Power BI 授權。</span><span class="sxs-lookup"><span data-stu-id="ed517-174">Following this path for customization and sharing may require additional Power BI licenses.</span></span> <span data-ttu-id="ed517-175">如需詳細資訊，請參閱 Power BI [授權指南](https://go.microsoft.com/fwlink/p/?linkid=849803) 。</span><span class="sxs-lookup"><span data-stu-id="ed517-175">See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
