---
title: 使用完全符合結構描述和敏感性資訊類型精靈
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何使用完全符合結構描述和敏感性資訊類型精靈。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699149"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>使用完全符合結構描述和敏感性資訊類型精靈

[使用以精確資料比對為基礎 (EDM) 的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 包含諸多步驟。  您可以使用此精靈來建立結構描述和敏感性資訊類型模式 (規則套件) 檔案，以協助簡化程式。

> [!NOTE]
> 「完全符合結構描述和敏感性資訊類型」精靈只適用于 World Wide 和 GCC 雲端。

您可以使用這個精靈取代：

- [定義用於敏感性資訊的資料庫結構描述](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [設定模式 (規則套件)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

[第 1 部分：設定以 EDM 為基礎的分類](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification) 的步驟。

## <a name="pre-requisites"></a>先決條件

1. 快速瞭解使用 EDM 建立自訂敏感性資訊類型的步驟 [工作流程概覽](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance)。

2. 執行 [將敏感性資料儲存為 .csv 格式](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) 一節中的步驟。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>使用完全符合結構描述和敏感性資訊類型模式精靈

1. 針對您的租使用者，在 Microsoft 365 合規性中心，移至 **資料分類** > **完全資料比對**。

2. 選擇 **[建立 EDM 結構描述]** 以開啟結構描述精靈設定飛出視窗。

![EDM 結構描述建立精靈設定飛出視窗](../media/edm-schema-wizard-1.png)

3. 請填入適當的 **名稱** 和 **描述**。

4. 如果您想要執行該行為，請選擇 **[忽略所有結構描述欄位的分隔符號及標點符號]**。 若要深入瞭解如何設定 EDM 以忽略案例或分隔符號，請參閱 [使用以精確資料對比 (EDM) 為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

5. 在 **結構描述欄位 #1** 填入您想要的值，並視需要新增更多欄位。 

> [!IMPORTANT]
> 您至少必須將其中一個最多五個結構描述欄位指定為可供搜尋。

6. 選擇 [儲存]。 您的結構描述會隨即列出。

7. 選擇 **[EDM 敏感性資訊類型]** 和 **[建立 EDM 敏感性資訊類型]**，以開啟 [敏感性資訊類型設定] 精靈。

8. 選擇 **[選擇現有的 EDM 結構描述]**，然後從清單中選擇您在步驟2-6 中所建立的結構描述。

9. 選擇 **[下一步]**，然後選擇 **[建立模式]**。

10. 選擇 **[信賴等級]** 和 **[主要元素]**。  若要深入瞭解如何設定模式，請參閱 [在合規性中心內建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)

11.  選擇 **[主要元素的敏感性資訊類型]** 以建立關聯。 若要深入瞭解可用的敏感性資訊類型，請參閱 [[敏感性資訊類型實體定義]](sensitive-information-type-entity-definitions.md)。

12. 選擇 **[完成]**。

13. 選擇您想要的 **[信賴等級和字元概量]**。  這會是整個 EDM 敏感性資訊類型的預設值

13. 如果您想要為 EDM 敏感性資訊類型建立其他模式，請選擇 **[建立模式]**。

14. 選擇 **[下一步]** 並填入 **[名稱]** 和 **[系統管理員的描述]**。

15. 檢閱並選擇 **[提交]**。

您可以選取顯示 [編輯] 和 [刪除] 的控制項，以刪除或編輯敏感性資訊類型模式。

> [!IMPORTANT]
> 如果您想要移除某一結構描述，且它已與 EDM 敏感性資訊類型相關聯，您必須先刪除 EDM 敏感性資訊類型，然後您就可以刪除該結構描述。

## <a name="post-steps"></a>文章步驟

在您使用這個精靈建立 EDM 結構描述和模式 (規則套件) 檔案之後，您仍需執行 [第2部分：雜湊並上傳敏感性資料]](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) 中的步驟，您才能使用 EDM 自訂敏感性資訊類型。