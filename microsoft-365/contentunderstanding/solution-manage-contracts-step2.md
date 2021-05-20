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
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>步驟 2. 使用 Microsoft Teams 建立您的合約管理通道

當您的組織設定合約管理解決方案時，您需要有一個集中位置，以供專案關係人查看和管理合約。 為了達到此目的，您可以使用[Microsoft Teams](https://docs.microsoft.com/microsoftteams/)設定 Teams 通道，並使用 Teams 中的功能來：

- **建立專案關係人的位置，以輕鬆查看所有需要採取動作的合約。** 例如，在 Teams 您可以在合約管理通道中建立 [**合約**] 索引標籤，在此通道中，成員可以查看需要核准之所有合約的有用磚視圖。 您也可以設定視圖，讓每個「卡片」列出您關心 (的重要資料，例如 *客戶*、 *合同工* 和 *費用金額*) 。

     ![[合約] 索引標籤。](../media/content-understanding/tile-view.png)

- **有一個位置可讓成員彼此互動，並查看重要的事件。** 例如，在 Teams 中，[**文章**] 索引標籤可用於進行交談、取得更新，以及查看動作 (例如拒絕合約) 的成員。 當發生某些事情 (例如送出以供核准) 的新合約時，[ **張貼** ] 索引標籤不僅可以宣告，也可以保留其記錄。 而且，如果成員訂閱通知，當有更新時，他們會收到通知。 

     ![[文章] 索引標籤。](../media/content-understanding/posts.png)</br> 

- **具有成員的位置，以查看已核准的合約，以瞭解何時可以提交付款。** 在 Teams 中，您可以建立一個付款通道，<b>以</b>列出需要提交至付款的所有合約。 您可以輕鬆地擴充此方案，改為將此資訊直接寫入協力廠商財務應用程式 (例如 Dynamics CRM) 。

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>將 SharePoint 文件庫附加至 [合約] 索引標籤 

在您的合約管理通道中建立 [**合約**] 索引標籤之後，您必須 [將 SharePoint 文件庫附加到該](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)組織單位。 您要附加的 SharePoint 文件庫是您在上一節中套用 SharePoint Syntex 檔理解模型的模型。

附加 SharePoint 文件庫之後，您就可以透過預設清單視圖來查看任何分類合約。

   ![清單視圖。](../media/content-understanding/list-view.png) 

## <a name="customize-your-contracts-tab-tile-view"></a>自訂 [您的合約] 索引標籤視圖

> [!NOTE]
> 本節參考的程式碼範例包含在「[合約管理解決方案資產存放庫](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)」中的檔案[ContractTileFormatting.js上](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json)。

雖然 Teams 可讓您在平鋪視圖中查看您的合約，但您可能會想要自訂它，以查看您想要在合同卡中顯示的合約資料。 例如，對於 [ **合約** ] 索引標籤，成員可以查看合同卡片上的客戶、合同工和費用金額，這一點很重要。 所有這些欄位都是透過已套用至文件庫的 SharePoint Syntex 模型從每個合約中解壓縮。 您也想要將磚標題列變更為不同狀態的不同色彩，讓成員可以輕鬆查看合約在核准程式中的位置。 例如，所有核准的合約都會有藍色標頭欄。

   ![清單視圖。](../media/content-understanding/tile.png)

您使用的自訂圖格視圖，需要您變更用來格式化目前麻將牌視圖的 JSON 檔案。 您可以透過查看檔案 [ 上的ContractTileFormatting.js](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ，參考用來建立卡片視圖的 JSON 檔案。 在下列各節中，您將會看到合約卡片中的功能的特定程式碼區段。

如果您想要在 Teams 通道中查看或變更您的視圖的 JSON 代碼，請在 Teams 通道中，選取 [視圖] 下拉式功能表，然後選取 [**格式化目前的視圖**]。

   ![json 格式。](../media/content-understanding/jason-format.png) 

## <a name="card-size-and-shape"></a>卡片大小和圖形

在 [ [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file] 中，查看下列區段，以查看如何格式化卡片大小及圖形的程式碼。

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


## <a name="contract-status"></a>合約狀態

下列程式碼可讓您定義每個標題卡片的狀態。 請 *注意，每* 個狀態值 (*New*、*核准* 和 *拒絕*) 都會針對每個值顯示不同的色彩代碼。 在 [ [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file] 中，查看定義狀態的區段。

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


## <a name="extracted-fields"></a>提取的欄位

每個合約卡都會顯示三個欄位，每個合約 (的 *用戶端*、 *合同工* 和 *費用金額*) 中解壓縮。 此外，您也想要顯示 Syntex 用來識別檔的 SharePoint 模型所分類的時間/日期。 

在 [ [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file] 中，下列各節定義上述各項。

### <a name="client"></a>用戶端

本節定義「用戶端」會如何顯示在卡片上，並使用特定合約的值。

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

### <a name="contractor"></a>承包商

本節定義「承包商」會如何顯示在卡片上，並使用特定合約的值。

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


### <a name="fee-amount"></a>費用金額

本節定義「費用金額」會如何顯示在卡片上，並使用特定合約的值。

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



### <a name="classification-date"></a>分類日期

本節會定義如何在卡片上顯示「分類」，並使用特定合約的值。

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

## <a name="next-step"></a>後續步驟

[步驟3。使用 Power Automate 建立流程以處理您的合約](solution-manage-contracts-step3.md)
