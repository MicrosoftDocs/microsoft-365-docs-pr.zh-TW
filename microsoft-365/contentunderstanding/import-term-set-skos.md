---
title: 使用 SKOS 格式匯入字詞組
description: 瞭解如何使用 SKOS 格式匯入字詞組
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 734edbb462193291b6bd2fb4a8e6afc3a0b709cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928245"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>使用 SKOS 格式匯入字詞組

您可以使用 SKOS 格式匯入字詞組。 如需有關格式的詳細資訊，請參閱[「SharePoint 分類法的SKOS 格式參考」](skos-format-reference.md) (英文) 。 此功能需要 [SharePoint Syntex](index.md) 授權。

我們建議您將匯入檔案維持在少於 20,000 個字詞。 較大的檔案可能會增加驗證和匯入所需的時間。

1. 在 SharePoint 系統管理中心展開 **[內容服務]**，然後按一下 **[字詞庫]**。

2. 選取您要匯入字詞組的字詞群組。

3. 在命令列中，按一下 **[ 匯入字詞組]**。
 
4.  如果您想要下載用作範本的範例檔案，請按一下 **[sample-metadata. ttl]** ，取得使用 SKOS 格式的範例檔案。
 
5.  建立重要檔案以涵蓋您要匯入的字詞組和字詞。

6.  在 **[檔案格式]** 底下，選取 **[SKOS (*.ttl)]**。

7.  按一下 **[瀏覽]** 並瀏覽至新增匯入檔案。

8.  按一下 **[匯入]**。 直到匯入完成之後，才能關閉面板。

成功匯入檔案時，系統會顯示一則成功訊息，而字詞儲存區將會重新整理，您可以瀏覽至新建立的字詞組。

## <a name="see-also"></a>請參閱

[受管理的中繼資料簡介](/sharepoint/managed-metadata)

[文件瞭解概觀](document-understanding-overview.md)

[匯入字詞組 (網站層級)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)