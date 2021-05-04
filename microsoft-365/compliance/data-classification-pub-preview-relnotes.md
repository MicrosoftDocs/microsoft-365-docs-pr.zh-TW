---
title: 資料分類版本資訊
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 資料分類的版本資訊。
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086704"
---
# <a name="data-classification-release-notes"></a>資料分類版本資訊


## <a name="exchange-mailbox-count"></a>Exchange 信箱帳戶

當您深入了解 Exchange 信箱時，會注意到出現小工具提示。 這是為了表明以下事實：對於敏感資訊類型、敏感度標籤和保留標籤顯示的彙總計數，可能與信箱中所找到的項目數不完全相符。 原因是深入查看資料夾時會提取分類內容的即時檢視，同時計算彙總的計數。


## <a name="rendering-of-encrypted-documents"></a>呈現加密的文件

加密的 SharePoint、Exchange 和 OneDrive 檔案不會呈現在內容總管中。 這是敏感問題，需要在內容總管中查看檔案內容與將內容保留加密狀態中，這兩種需求之間取得平衡。 透過 **內容總管清單檢視器** 和 **內容總管內容檢視器** 角色群組授與的權限，您會看到一個清單檢視，其中列出檔案、檔案中繼資料，以及可以用來透過 Web 用戶端存取內容的連結。

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>SharePoint 搜尋中保留標籤名稱中的支援字元

SharePoint 搜尋不支援內含 `-` 或 `_` 的保留標籤名稱。 例如，不支援 `Label-MIP` 和 `Label_MIP`。 SharePoint 搜尋不支援在敏感性標籤名稱和敏感資訊類型名稱中使用那些字元。

## <a name="onedrive-remains-in-preview"></a>OneDrive 仍處於預覽階段

感謝您在預覽計劃期間對 OneDrive 整合提出的寶貴意見反應。 當我們在解決細節時，您可能會遇到不一致的資料/流程。 我們會繼續在預覽中展示 OneDrive，直到完成所有修正為止。 非常感謝您的持續支持。


## <a name="see-also"></a>另請參閱

- [開始使用資料分類 (預覽)](data-classification-overview.md)
- [查看標籤活動 (預覽)](data-classification-activity-explorer.md)
- [檢視已套用標籤的內容 (預覽)](data-classification-content-explorer.md)
- [了解敏感度標籤](sensitivity-labels.md)
- [瞭解保留原則和保留標籤](retention.md)
- [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)