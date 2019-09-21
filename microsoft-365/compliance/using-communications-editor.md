---
title: 使用通訊編輯器
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
description: ''
ms.openlocfilehash: 78865efc5c10ebcff9742f922f675b637bb9b2b0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077725"
---
# <a name="use-the-communications-editor"></a>使用通訊編輯器

當您定義入口網站內容的內容，法律保留通知和相關的提醒/呈報之後，您可以利用通訊編輯器]，以格式化，並以動態方式來自訂您的內容。

## <a name="rich-text-editor"></a>Rtf 編輯器 

通訊編輯器可讓使用者自訂使用 [編輯器] 選項的文字。 例如，使用者可以變更字型類型，建立項目符號清單、 醒目提示內容等等。 

## <a name="merge-field-variables"></a>合併欄位變數

您可以利用電子郵件合併變數將嵌入的通訊內文文字的自訂的 custodian 屬性從通訊編輯器。 傳送至 custodian 時，合併列印欄位也會填入對應的欄位。 例如，傳送至 custodian John Smith 時，[Custodian 名稱] 的合併列印欄位會轉譯與對應的名稱。 

您可以藉由選取編排 rtf 編輯器控制項的**合併列印欄位**圖示使用電子郵件合併列印功能變數。 版面配置區將新增型關閉使用者的資料指標的位置。 

### <a name="list-of-merge-field-variables"></a>合併列印欄位變數的清單

| 欄位名稱                  | 欄位的詳細資訊 | 
| :------------------- | :------------------- |
| 顯示名稱  | Custodian 的名字和姓氏。 | 
| 認可連結 | 記錄每個 custodian 認可自訂的連結。|                 |
| 入口網站的連結     | Custodian 規範入口網站自訂的連結。|                |
| 發出長                   | 指定的單位法務人員的電子郵件地址。|                   |
| 發行日期                   | 請注意所發出的 (時間 UTC) 日期。              |