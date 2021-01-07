---
title: 使用通訊編輯器
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 當您設定內容格式時，請使用通訊編輯器變更文字和合併欄位變數。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769158"
---
# <a name="use-the-communications-editor"></a>使用通訊編輯器

當您定義入口網站內容、法律封存通知和相關的提醒/上報內容時，您可以使用通訊編輯器來格式化並動態自訂您的內容。

## <a name="rich-text-editor"></a>富文字編輯器

通訊編輯器可讓使用者使用編輯器選項自訂文字。 例如，使用者可以變更字型類型、建立專案符號清單、反白顯示內容等等。

## <a name="merge-field-variables"></a>合併欄位變數

您可以使用通訊編輯器中的電子郵件合併變數，將自訂的系統管理員屬性嵌入通訊的本文文字。 傳送給管理員時，會以對應的欄位填入合併欄位。 例如，當傳送給「保管人 John Smith」時，合併欄位 [保管人 Name] 會以對應的名稱加以轉譯。

您可以透過選取 rtf 文字編輯器控制項頂端的 **合併欄位** 圖示，使用電子郵件合併欄位。 會根據使用者游標的位置來新增預留位置。

### <a name="list-of-merge-field-variables"></a>合併欄位變數清單

| 欄位名稱                  | 欄位詳細資料 |
| :------------------- | :------------------- |
| 顯示名稱  | 管理員的名字和姓氏。 | 
| 確認連結 | 自訂的連結，可記錄每個保管人的認可。|                 |
| 入口網站連結     | 管理員的規範入口網站的自訂連結。|                |
| 簽發官                   | 指定之簽發專員的電子郵件地址。|                   |
| 簽發日期                   | 發出通知的日期 (UTC) 。              |
|||
