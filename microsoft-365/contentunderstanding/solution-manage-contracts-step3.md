---
title: 步驟 3： 使用 Power Automate 建立流程以處理您的合約
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
description: 瞭解如何使用 Power Automate 建立您使用 Microsoft 365 解決方案處理合約的流程。
ms.openlocfilehash: 54e92f36b19cefde92111cdbc960fad7715cf8b0
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583097"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a>步驟 3. 使用 Power Automate 建立流程以處理您的合約

您已建立您的合約管理通道，並已附加您的 SharePoint 文件庫。 下一步是建立 Power Automate 流程，處理您的 SharePoint Syntex 模型所識別和分類的合約。 您可以[在 SharePoint 文件庫中建立 Power Automate 流程，以](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)執行此步驟。

針對您的合約管理解決方案，您想要建立 Power Automate 流程以執行下列動作：

-  在 SharePoint Syntex 模型分類合約後，請將合同狀態變更為 [**正在審查**]。
- 然後，便會檢查合約，並以核准或拒絕。
- 針對核准的合約，合約資訊會發佈到標籤以進行付款處理。
- 若為被拒絕的合約，會通知小組進行進一步的分析。 

下圖顯示合約管理解決方案的 Power Automate 流程。

![顯示整個方案的 Flow 圖表。](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a>準備您的合約以供審查

當您 SharePoint Syntex 檔理解模型識別和分類合約時，Power Automate 流程會先將狀態變更為 [**評審**]。

![更新狀態。](../media/content-understanding/flow-overview.png)

取出檔案之後，請將狀態值變更為 [ **正在審查**]。

![在 [檢查狀態]。](../media/content-understanding/in-review.png)

下一步是建立適應性卡片，表明該合約等候進行審閱，並將其發佈至合約管理通道。

![合同檢查文章。](../media/content-understanding/contract-approval-post.png)


![建立適應性卡片以供複查。](../media/content-understanding/adaptive-card.png)

下列程式碼是在 Power Automate 流程中用於此步驟的 JSON。

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional"></a>條件

在您的流程中，您必須建立一個條件，讓您的合約會核准或拒絕。

![條件。](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a>如果已核准合約

當合約已獲核准時，會發生下列情況：

- 在 [ **合約** ] 索引標籤上，合同卡片中的狀態會變更為 [ **已核准**]。

   ![已核准卡狀態。](../media/content-understanding/approved-contracts-tab.png)

- 在您的流程中，狀態會變更為 [ **已核准**]。

   ![Flow 狀態已核准。](../media/content-understanding/status-approved.png)

- 在此方案中，合約資料將會新增至 [增加 **比率** ] 索引標籤，讓 payouts 可以管理。 此程式可延長以允許流程提交由協力廠商財務應用程式 (的合約，例如 Dynamics CRM) 。

   ![合同已移動至向之外支付。](../media/content-understanding/for-payout.png)

- 在流程中，您會建立下列專案，以將核准的合約移至 [ **以付出比率** ] 索引標籤。

   ![Flow 要移動的專案以支付。](../media/content-understanding/ready-for-payout.png)

- 表示已核准合約的適應性卡，會建立併發布到合約管理通道。

   ![已發佈合約核准。](../media/content-understanding/adaptive-card-approval.png)

   ![適應性卡核准。](../media/content-understanding/adaptive-card.png)


   下列程式碼是在 Power Automate 流程中用於此步驟的 JSON。

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a>如果拒絕合約

當合約遭到拒絕時，會發生下列情況：

- 在 [ **合約** ] 索引標籤上，合同卡片中的狀態會變更為 [ **拒絕**]。

   ![已拒絕智慧卡狀態。](../media/content-understanding/rejected-contracts-tab.png)

- 在您的流程中，您會取出合約檔，將狀態變更為 [已 **拒絕**]，然後再將檔案存回。

   ![Flow 狀態為「已拒絕」。](../media/content-understanding/reject-flow.png)

- 在您的流程中，您會建立一個自我調整卡，表明已拒絕該合約。

   ![Flow 狀態為「已拒絕」。](../media/content-understanding/reject-flow-item.png)

下列程式碼是在 Power Automate 流程中用於此步驟的 JSON。

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- 該卡會在合約管理通道中公佈。

   ![Flow 的最適適應性卡拒絕。](../media/content-understanding/rejected.png)