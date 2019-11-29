---
title: 使用資料分類內容總管 (預覽)
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
description: 內容總管可讓您本機檢視已套用標籤的項目。
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268469"
---
# <a name="using-data-classification-content-explorer-preview"></a>使用資料分類內容總管 (預覽)

資料分類內容總管可讓您本機檢視概觀頁面中摘要的項目。

## <a name="content-explorer"></a>內容總管

內容總管是具有敏感度標籤、保留標籤或已分類為貴組織敏感性資訊類型之項目的目前快照。

![內容總管摺疊的螢幕擷取畫面](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a>權限

有兩個角色可以將存取權授與內容瀏覽器：

- **內容瀏覽器清單檢視器**：這個角色的成員資格可讓您查看每個項目及其位置。

- **內容瀏覽器內容檢視器**：這個角色的成員資格可讓您檢視清單中每個項目的內容。

您用來存取內容瀏覽器的帳戶必須屬於其中一個或兩個角色。 這些是獨立的角色，不會累計。 例如，如果您想要授與某個帳戶只能檢視項目及其位置的權限，請授與「內容瀏覽器清單檢視器」權限。 如果您想要讓該相同帳戶也能夠檢視清單中項目的內容，也請授與「內容瀏覽器內容檢視器」權限。

### <a name="how-to-use-content-explorer"></a>如何使用內容總管

1. 開啟 **Microsoft 365 合規性中心**  > **資料分類** > **內容總管**。
2. 如果您知道標籤的名稱或敏感性資訊類型，便可在搜尋方塊中輸入。
3. 您也可以展開標籤類型，然後從清單選取標籤來瀏覽項目，以下顯示的是清單保留標籤部分中的項目。
4. 在 **[所有位置]** 底下選取位置，並向下切入資料夾結構至項目。
5. 按兩下以在內容總管中於本機開啟項目。

## <a name="see-also"></a>另請參閱

- [敏感性標籤](sensitivity-labels.md)
- [保留標籤](labels.md)
- [敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)
- [保留原則概觀](retention-policies.md)
