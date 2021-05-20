---
title: 步驟 2： 使用 Microsoft Teams 建立您的合約管理通道
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/19/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何使用 Microsoft Teams，透過使用 Microsoft 365 解決方案來建立您的合約管理通道。
ms.openlocfilehash: 20ace5d17550c8dd800368957dd940c9857bce5d
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583133"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a><span data-ttu-id="2dc6c-104">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="2dc6c-104">Step 2.</span></span> <span data-ttu-id="2dc6c-105">使用 Microsoft Teams 建立您的合約管理通道</span><span class="sxs-lookup"><span data-stu-id="2dc6c-105">Use Microsoft Teams to create your contract management channel</span></span>

<span data-ttu-id="2dc6c-106">當您的組織設定合約管理解決方案時，您需要有一個集中位置，以供專案關係人查看和管理合約。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-106">When your organization sets up a contracts management solution, you need a central location in which stakeholders can review and manage contracts.</span></span> <span data-ttu-id="2dc6c-107">為了達到此目的，您可以使用[Microsoft Teams](https://docs.microsoft.com/microsoftteams/)設定 Teams 通道，並使用 Teams 中的功能來：</span><span class="sxs-lookup"><span data-stu-id="2dc6c-107">For this purpose, you can use [Microsoft Teams](https://docs.microsoft.com/microsoftteams/) to set up a Teams channel and use the features in Teams to:</span></span>

- <span data-ttu-id="2dc6c-108">**建立專案關係人的位置，以輕鬆查看所有需要採取動作的合約。**</span><span class="sxs-lookup"><span data-stu-id="2dc6c-108">**Create a location for stakeholders to easily see all contracts that require action.**</span></span> <span data-ttu-id="2dc6c-109">例如，在 Teams 您可以在合約管理通道中建立 [**合約**] 索引標籤，在此通道中，成員可以查看需要核准之所有合約的有用磚視圖。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-109">For example, in Teams you can create a **Contracts** tab in the Contract Management channel in which members can see a useful tile view of all contracts that need approval.</span></span> <span data-ttu-id="2dc6c-110">您也可以設定視圖，讓每個「卡片」列出您關心 (的重要資料，例如 *客戶*、 *合同工* 和 *費用金額*) 。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-110">You can also configure the view so that each "card" lists the important data you care about (such as *Client*, *Contractor*, and *Fee amount*).</span></span>

     ![[合約] 索引標籤。](../media/content-understanding/tile-view.png)

- <span data-ttu-id="2dc6c-112">**有一個位置可讓成員彼此互動，並查看重要的事件。**</span><span class="sxs-lookup"><span data-stu-id="2dc6c-112">**Have a location for members to interact with each other and see important events.**</span></span> <span data-ttu-id="2dc6c-113">例如，在 Teams 中，[**文章**] 索引標籤可用於進行交談、取得更新，以及查看動作 (例如拒絕合約) 的成員。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-113">For example, in Teams, the **Posts** tab can be used to have conversations, get updates, and see actions (such as a member rejecting a contract).</span></span> <span data-ttu-id="2dc6c-114">當發生某些事情 (例如送出以供核准) 的新合約時，[ **張貼** ] 索引標籤不僅可以宣告，也可以保留其記錄。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-114">When something has happened (such as a new contract submitted for approval), the **Posts** tab can be used not only to announce it, but also to keep a record of it.</span></span> <span data-ttu-id="2dc6c-115">而且，如果成員訂閱通知，當有更新時，他們會收到通知。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-115">And if members subscribe to notifications, they'll get notified whenever there's an update.</span></span> 

     ![[文章] 索引標籤。](../media/content-understanding/posts.png)</br> 

- <span data-ttu-id="2dc6c-117">**具有成員的位置，以查看已核准的合約，以瞭解何時可以提交付款。**</span><span class="sxs-lookup"><span data-stu-id="2dc6c-117">**Have a location for members to see approved contracts to know when they can be submitted for payment.**</span></span> <span data-ttu-id="2dc6c-118">在 Teams 中，您可以建立一個付款通道，<b>以</b>列出需要提交至付款的所有合約。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-118">In Teams, you can create a <b>For Payment</b> channel that will list all contracts that will need to be submitted to payment.</span></span> <span data-ttu-id="2dc6c-119">您可以輕鬆地擴充此方案，改為將此資訊直接寫入協力廠商財務應用程式 (例如 Dynamics CRM) 。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-119">You can easily extend this solution to instead write this information directly to a third-party financial application (for example, Dynamics CRM).</span></span>

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a><span data-ttu-id="2dc6c-120">將 SharePoint 文件庫附加至 [合約] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="2dc6c-120">Attach your SharePoint document library to the Contracts tab</span></span> 

<span data-ttu-id="2dc6c-121">在您的合約管理通道中建立 [**合約**] 索引標籤之後，您必須 [將 SharePoint 文件庫附加到該](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)組織單位。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-121">After you create a **Contracts** tab in your Contracts Management channel, you need to [attach your SharePoint document library to it](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).</span></span> <span data-ttu-id="2dc6c-122">您要附加的 SharePoint 文件庫是您在上一節中套用 SharePoint Syntex 檔理解模型的模型。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-122">The SharePoint document library you want to attach is the one in which you applied your SharePoint Syntex document understanding model to in the previous section.</span></span>

<span data-ttu-id="2dc6c-123">附加 SharePoint 文件庫之後，您就可以透過預設清單視圖來查看任何分類合約。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-123">After you attach the SharePoint document library, you'll be able to view any classified contracts through a default list view.</span></span>

   ![清單視圖。](../media/content-understanding/list-view.png) 

## <a name="customize-your-contracts-tab-tile-view"></a><span data-ttu-id="2dc6c-125">自訂 [您的合約] 索引標籤視圖</span><span class="sxs-lookup"><span data-stu-id="2dc6c-125">Customize your Contracts tab tile view</span></span>

> [!NOTE]
> <span data-ttu-id="2dc6c-126">本節參考的程式碼範例包含在「[合約管理解決方案資產存放庫](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)」中的檔案[ContractTileFormatting.js上](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json)。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-126">This section references code examples that are contained in the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file that is included in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span>

<span data-ttu-id="2dc6c-127">雖然 Teams 可讓您在平鋪視圖中查看您的合約，但您可能會想要自訂它，以查看您想要在合同卡中顯示的合約資料。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-127">While Teams lets you view your contracts in a tile view, you might want to customize it to view the contract data you want to make visible in the contract card.</span></span> <span data-ttu-id="2dc6c-128">例如，對於 [ **合約** ] 索引標籤，成員可以查看合同卡片上的客戶、合同工和費用金額，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-128">For example, for the **Contracts** tab, it is important for members to see the client, contractor, and fee amount on the contract card.</span></span> <span data-ttu-id="2dc6c-129">所有這些欄位都是透過已套用至文件庫的 SharePoint Syntex 模型從每個合約中解壓縮。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-129">All of these fields were extracted from each contract through your SharePoint Syntex model that was applied to your document library.</span></span> <span data-ttu-id="2dc6c-130">您也想要將磚標題列變更為不同狀態的不同色彩，讓成員可以輕鬆查看合約在核准程式中的位置。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-130">You also want to be able to change the tile header bar to different colors for each status so that members can easily see where the contract is in the approval process.</span></span> <span data-ttu-id="2dc6c-131">例如，所有核准的合約都會有藍色標頭欄。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-131">For example, all approved contracts will have a blue header bar.</span></span>

   ![清單視圖。](../media/content-understanding/tile.png)

<span data-ttu-id="2dc6c-133">您使用的自訂圖格視圖，需要您變更用來格式化目前麻將牌視圖的 JSON 檔案。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-133">The custom tile view you use requires you to make changes to the JSON file used to format the current tile view.</span></span> <span data-ttu-id="2dc6c-134">您可以透過查看檔案 [ 上的ContractTileFormatting.js](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ，參考用來建立卡片視圖的 JSON 檔案。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-134">You can reference the JSON file used to create the card view by looking at the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file.</span></span> <span data-ttu-id="2dc6c-135">在下列各節中，您將會看到合約卡片中的功能的特定程式碼區段。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-135">In the following sections, you'll see specific sections of the code for features that are in the contract cards.</span></span>

<span data-ttu-id="2dc6c-136">如果您想要在 Teams 通道中查看或變更您的視圖的 JSON 代碼，請在 Teams 通道中，選取 [視圖] 下拉式功能表，然後選取 [**格式化目前的視圖**]。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-136">If you want to see or make changes to the JSON code for your view in your Teams channel, in the Teams channel, select the view drop-down menu, and then select **Format current view**.</span></span>

   ![json 格式。](../media/content-understanding/jason-format.png) 

## <a name="card-size-and-shape"></a><span data-ttu-id="2dc6c-138">卡片大小和圖形</span><span class="sxs-lookup"><span data-stu-id="2dc6c-138">Card size and shape</span></span>

<span data-ttu-id="2dc6c-139">在 [ [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file] 中，查看下列區段，以查看如何格式化卡片大小及圖形的程式碼。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-139">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the following section to see the code for how the size and shape of the card is formatted.</span></span>

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```


## <a name="contract-status"></a><span data-ttu-id="2dc6c-140">合約狀態</span><span class="sxs-lookup"><span data-stu-id="2dc6c-140">Contract status</span></span>

<span data-ttu-id="2dc6c-141">下列程式碼可讓您定義每個標題卡片的狀態。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-141">The following code lets you define the status of each title card.</span></span> <span data-ttu-id="2dc6c-142">請 *注意，每* 個狀態值 (*New*、*核准* 和 *拒絕*) 都會針對每個值顯示不同的色彩代碼。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-142">Note that each status value (*New*, *In review*, *Approved*, and *Rejected*) will display a different color code for each.</span></span> <span data-ttu-id="2dc6c-143">在 [ [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file] 中，查看定義狀態的區段。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-143">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the section that defines the status.</span></span>

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```


## <a name="extracted-fields"></a><span data-ttu-id="2dc6c-144">提取的欄位</span><span class="sxs-lookup"><span data-stu-id="2dc6c-144">Extracted fields</span></span>

<span data-ttu-id="2dc6c-145">每個合約卡都會顯示三個欄位，每個合約 (的 *用戶端*、 *合同工* 和 *費用金額*) 中解壓縮。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-145">Each contract card will display three fields that were extracted for each contract (*Client*, *Contractor*, and *Fee Amount*).</span></span> <span data-ttu-id="2dc6c-146">此外，您也想要顯示 Syntex 用來識別檔的 SharePoint 模型所分類的時間/日期。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-146">Additionally, you also want to display the time/date that the file was classified by the SharePoint Syntex model used to identify it.</span></span> 

<span data-ttu-id="2dc6c-147">在 [ [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file] 中，下列各節定義上述各項。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-147">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, the following sections define each of these.</span></span>

### <a name="client"></a><span data-ttu-id="2dc6c-148">用戶端</span><span class="sxs-lookup"><span data-stu-id="2dc6c-148">Client</span></span>

<span data-ttu-id="2dc6c-149">本節定義「用戶端」會如何顯示在卡片上，並使用特定合約的值。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-149">This section defines how "Client" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a><span data-ttu-id="2dc6c-150">承包商</span><span class="sxs-lookup"><span data-stu-id="2dc6c-150">Contractor</span></span>

<span data-ttu-id="2dc6c-151">本節定義「承包商」會如何顯示在卡片上，並使用特定合約的值。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-151">This section defines how the "Contractor" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
},
```


### <a name="fee-amount"></a><span data-ttu-id="2dc6c-152">費用金額</span><span class="sxs-lookup"><span data-stu-id="2dc6c-152">Fee Amount</span></span>

<span data-ttu-id="2dc6c-153">本節定義「費用金額」會如何顯示在卡片上，並使用特定合約的值。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-153">This section defines how the "Fee Amount" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```



### <a name="classification-date"></a><span data-ttu-id="2dc6c-154">分類日期</span><span class="sxs-lookup"><span data-stu-id="2dc6c-154">Classification date</span></span>

<span data-ttu-id="2dc6c-155">本節會定義如何在卡片上顯示「分類」，並使用特定合約的值。</span><span class="sxs-lookup"><span data-stu-id="2dc6c-155">This section defines how "Classification" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a><span data-ttu-id="2dc6c-156">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2dc6c-156">Next step</span></span>

[<span data-ttu-id="2dc6c-157">步驟3。使用 Power Automate 建立流程以處理您的合約</span><span class="sxs-lookup"><span data-stu-id="2dc6c-157">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
