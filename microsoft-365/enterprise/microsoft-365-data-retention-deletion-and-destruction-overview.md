---
title: Microsoft 365 中的資料保留、刪除及毀損
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Microsoft 365 有關資料保留、刪除及銷毀的 Microsoft 原則的概述。
ms.openlocfilehash: c522c1a1a4de46a4fc36bd87a031be8b47c5523d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688444"
---
# <a name="data-retention-deletion-and-destruction-in-microsoft-365"></a>Microsoft 365 中的資料保留、刪除及毀損

Microsoft 有一個適用于 Microsoft 365 的資料處理標準原則，可指定在刪除之後保留客戶資料的時間。 通常有兩種情況會刪除客戶資料：

- 使用中**刪除**：承租人具有使用中的訂閱，且使用者或系統管理員刪除資料，或系統管理員刪除使用者。
- **被動式刪除**：承租人訂閱已結束。

## <a name="data-retention"></a>資料保留

在每個刪除案例中，下表會根據資料類別和分類，顯示資料保留期間上限：

| 資料類別 | 資料分類 | 描述 | 範例 | 保留期間 |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| 客戶資料 | 客戶內容| 管理員和使用者直接提供或建立的內容 <br><br> 在 microsoft 資料中心使用 Microsoft 365 中的服務時，包含所有文字、聲音、影片、圖像檔案，以及軟體所建立及儲存的軟體 | 最常使用的 Microsoft 365 應用程式範例，可讓使用者製作資料包含 Word、Excel、PowerPoint、Outlook 和 OneNote <br><br> 客戶內容也包含由客戶擁有/提供的機密 (密碼、憑證、加密金鑰、儲存金鑰)  | **主動刪除案例：** 最多30天 <br><br> **被動刪除案例：** 最多180天 |
| 客戶資料 |  (EUII 的使用者身分識別資訊)  | 識別或可用來識別 Microsoft 服務使用者的資料。 EUII 不含客戶內容 | 使用者名稱或顯示名稱 (網域 \ 使用者名稱)  <br><br>  (name@domain 的使用者主要名稱)  <br><br>  使用者特有的 IP 位址 | 使用中**刪除案例：** 最多180天 (僅限租使用者系統管理員的動作)  <br><br> **被動刪除案例：** 最多180天 |
| 個人資料 <br>  (不包含在客戶資料) 中的資料 | 最終使用者 Pseudonymous 識別碼 (EUPI)  | Microsoft 所建立的識別碼，會與 Microsoft 服務的使用者關聯。 結合其他資訊（例如對應表格）時，EUPI 會識別使用者 <br><br> EUPI 不包含客戶上傳或建立的資訊 | 使用者 Guid、PUIDs 或 Sid <br><br> 會話 IDs | **主動刪除案例：** 最多30天 <br><br> **被動刪除案例：** 最多180天 |

## <a name="subscription-retention"></a>訂閱保留

在使用中訂閱的期限內，訂戶可以存取、解壓縮或刪除儲存在 Microsoft 365 中的客戶資料。 如果付費訂閱結束或終止，Microsoft 會將 Microsoft 365 中儲存的客戶資料，保留90天的「有限的功能」帳戶，讓訂閱者能夠解壓縮資料。 在90日保留期間結束後，Microsoft 會停用帳戶並刪除客戶資料。 在 Microsoft 365 訂閱到期或終止後，不得超過180天。 Microsoft 會停用帳戶，並刪除帳戶中的所有客戶資料。 在任何資料的保留期間上限之後，就會呈現無法取得商業用的資料。

在您的免費試用版中，您的帳戶會在大部分的國家和地區中，移至30天的寬限狀態。 在此寬限期期間，您可以購買 Microsoft 365。 如果您決定不購買 Microsoft 365，您可以取消您的試用版或讓寬限期過期，並刪除您的試用版帳戶資訊和資料。

## <a name="expedited-deletion"></a>加急刪除

針對任何訂閱，訂戶可以聯繫 Microsoft 支援服務，並要求進行加急訂閱取消布建。 在此程式中，系統管理員進入 Microsoft 所提供的封鎖代碼之後，會在三天內刪除所有使用者資料。 這包括 SharePoint 線上和 Exchange Online 中的資料，保留或儲存于非使用中的信箱。

如需加速取消布建的詳細資訊，請參閱 [取消您的訂閱](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription)。

## <a name="related-links"></a>相關連結

- [資料毀損](microsoft-365-data-destruction.md)
- [Office 365 中的不變性](microsoft-365-data-immutability.md)
- [Exchange Online 資料刪除](microsoft-365-exchange-online-data-deletion.md)
- [SharePoint Online 資料刪除](microsoft-365-sharepoint-online-data-deletion.md)
- [商務用 Skype 資料刪除](microsoft-365-skype-data-deletion.md)
