---
title: 資料分類預覽版本資訊 (預覽)
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
description: 資料分類公開預覽版的版本資訊。
ms.openlocfilehash: fecf643d12cf544c16570c173b15bb1e0dc043f0
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887333"
---
# <a name="data-classification-public-preview-release-notes-preview"></a>資料分類公開預覽版本資訊 (預覽)

此公開預覽版引進新功能，可在您建立任何原則*之前*，開始掃描敏感內容和標籤內容。 這稱為**零變更管理**。 這可讓您查看所有保留和敏感度標籤對環境的影響，並協助您開始評估自己的保護和控管原則需求。

請檢閱這些版本資訊，讓您可以享有公開預覽版的最佳體驗。 我們將在目前版本與正式版本 (GA) 之間致力於處理這些要點。

## <a name="permissions-for-accessing-content-explorer"></a>存取內容總管的權限

內容總管的存取權限受到高度限制，因為該權限可讓您讀取掃描檔案的內容。 若要存取內容總管，需要**內容總管清單檢視器**和**內容總管內容檢視器**角色群組中的成員資格。 根據預設，沒有帳戶可以存取內容總管。 請參閱[使用資料分類內容總管 (預覽)](data-classification-content-explorer.md#permissions)。 全域系統管理員、合規性系統管理員或資料系統管理員可以指派必要的**內容總管清單檢視器**和**內容總管內容檢視器**角色群組成員資格。

> [!TIP]
> 在全球部署角色型存取控制 (RBAC) 時，**內容總管清單檢視器**和**內容總管內容檢視器**角色群組可能不會出現在權限頁面上。 如果權限頁面上沒有顯示該角色群組，則必須建立自訂角色群組，並將 `data classification list viewer` 角色和 (或) `data classification content viewer` 角色指派給您自訂的角色群組。

## <a name="exchange-mailbox-count"></a>Exchange 信箱帳戶

當您深入了解 Exchange 信箱時，會注意到出現小工具提示。 這是為了表明以下事實：對於敏感資訊類型、敏感度標籤和保留標籤顯示的彙總計數，可能與信箱中所找到的項目數不完全相符。 原因是深入查看資料夾時會提取分類內容的即時檢視，同時計算彙總的計數。

## <a name="seeing-guids-instead-of-label-names"></a>看到 GUID 而不是標籤名稱

私人預覽版客戶已看到下列情況：刪除貼有內容的標籤時，會導致標籤名稱解析為內容總管和活動總管中的 32位元 GUID，而不是標籤名稱。 

## <a name="rendering-of-encrypted-documents"></a>呈現加密的文件

加密的 SharePoint、Exchange 和 OneDrive 檔案不會呈現在內容總管中。 這是敏感問題，需要在內容總管中查看檔案內容與將內容保留加密狀態中，這兩種需求之間取得平衡。 透過**內容總管清單檢視器**和**內容總管內容檢視器**角色群組授與的權限，您會看到一個清單檢視，其中列出檔案、檔案中繼資料，以及可以用來透過 Web 用戶端存取內容的連結。

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>SharePoint 搜尋中保留標籤名稱中的支援字元

SharePoint search 不支援內含 `-``_` 的保留標籤名稱。 例如，不支援 `Label-MIP` 和 `Label_MIP`。 SharePoint 搜尋不支援在敏感性標籤名稱和敏感資訊類型名稱中使用那些字元。

## <a name="see-also"></a>另請參閱

- [開始使用資料分類 (預覽)](data-classification-overview.md)
- [查看標籤活動 (預覽)](data-classification-activity-explorer.md)
- [檢視已套用標籤的內容 (預覽)](data-classification-content-explorer.md)
- [敏感性標籤](sensitivity-labels.md)
- [保留標籤](labels.md)
- [敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

