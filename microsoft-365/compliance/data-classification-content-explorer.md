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
ms.openlocfilehash: 8a795e0582599dc3160f896a6361b773caa6c4e4
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823795"
---
# <a name="using-data-classification-content-explorer-preview"></a>使用資料分類內容總管 (預覽)

資料分類內容總管可讓您本機檢視概觀頁面中摘要的項目。

## <a name="content-explorer"></a>內容總管

內容總管會顯示具有敏感度標籤、保留標籤或已分類為貴組織敏感性資訊類型之項目的目前快照。

### <a name="sensitive-information-types"></a>敏感性資訊類型

[DLP 原則](data-loss-prevention-policies.md)有助於保護敏感性資訊 (已定義為**敏感性資訊類型**)。 Microsoft 365 包括涵蓋許多不同區域的[許多常見敏感性資訊類型的定義](what-the-sensitive-information-types-look-for.md)，可供您使用。 例如，信用卡號碼、銀行帳戶號碼、國家/地區識別碼和 Windows Live ID 服務號碼。

### <a name="sensitivity-labels"></a>敏感度標籤

[敏感度標籤](sensitivity-labels.md)只是一個標記，指出您組織的項目值。 可手動或自動套用。 一旦套用，即會將它內嵌在文件中，並在所有的位置追蹤。 敏感性標籤會啟用各種防護行為，例如強制浮水印或加密。 啟用端點保護後，您甚至可以防止項目離開組織控制。

SharePoint 和 OneDrive 中的檔案必須啟用敏感度標籤，以便在資料分類頁面中顯示對應資料。 如需詳細資訊，請參閱[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md) (英文版)。

### <a name="retention-labels"></a>保留標籤

[保留標籤](labels.md)可讓您定義保留標記的項目的時間長度，以及刪除它之前要採取的步驟。 它們會透過原則來手動或自動套用。 它們可以在協助您組織保持遵守法律和法規需求方面扮演一個角色。

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
5. 按兩下以在內容總管中於機開啟項目。

## <a name="see-also"></a>另請參閱

- [敏感性標籤](sensitivity-labels.md)
- [保留標籤](labels.md)
- [敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)
- [保留原則概觀](retention-policies.md)
- [資料外洩防護概觀](data-loss-prevention-policies.md)
