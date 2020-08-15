---
title: Microsoft 365 合規性支援雙位元組字元集的版本資訊 (預覽版)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 針對雙位元組字元集支援的版本資訊。
ms.openlocfilehash: 13bac873f2ba18bc166451ea73ec0d569fb30f68
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695239"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>支援雙位元組字元集的版本資訊 (預覽版)

 Microsoft 365 資訊保護目前支援預覽版的雙位元組字元集語言：

- 中文 (簡體)
- 中文 (繁體)
- 韓文
- 日文

此預覽僅限商愛業雲端中，且僅限部署至：

- 日本
- 韓國
- 中國
- 香港特別行政區
- 澳門特別行政區
- 台灣

這項支援適用於敏感性資訊類型和關鍵字字典，並將反映在資料外洩防護、通訊合規性、Exchange Online、SharePoint Online、商務用 OneDrive 和 Teams 解決方案中。

## <a name="known-issues"></a>已知問題

- 當電子郵件附加的文字檔採用不含位元組順序標記 (BOM) 的 UTF-8 格式時，通訊合規性原則不會偵測到該電子郵件。

- 如果針對原則條件輸入句子，通訊合規性原則就無法偵測值：「電子郵件包含這些文字」。 如果在原則中指定的文字是以字組的形式寫入，可以偵測到該文字；不過，如果是以句子中間寫入，將不會偵測到。

- 將字典指定為類型資訊的通訊合規性原則，不會偵測 Teams 的個人交談和頻道交談。

- 在此階段中，通訊合規性不支援下列條件 (我們計劃在日後修正這些問題)： 
  - 「電子郵件包含任何這些文字」
  - 「電子郵件不包含任何這些文字」
  - 「附件包含任何這些文字」
  - 「附件包含任何這些文字」

而我們建議您使用關鍵字字典建立自訂敏感性資訊類型 (SIT)，這樣會偵測電子郵件和附件的模式，並使用此自訂 SIT 做為通訊合規性原則條件。
