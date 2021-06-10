---
title: 無限制封存概觀
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 瞭解自動展開的封存，它會為 Exchange Online 信箱提供無限制的封存存放區。
ms.openlocfilehash: d61d3649ed65a93298928cced21180bbeca6aa95
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476264"
---
# <a name="overview-of-unlimited-archiving"></a>無限制封存概觀

在 Office 365 中，封存信箱可為使用者提供額外的信箱儲存空間。 啟用使用者的封存信箱之後，最多可有 100 GB 的額外儲存空間。 過去，當達到 100 GB 的儲存配額時，組織必須與 Microsoft 聯繫以要求封存信箱的額外儲存空間。 不再是這樣。

稱為 *自動展開* 封存的 Microsoft 365 (中的無限制封存功能) 會在封存信箱中提供額外的儲存空間。 當封存信箱中的儲存配額達到時，Microsoft 365 會自動增加封存的大小，這表示使用者將不會耗盡信箱儲存空間，而且系統管理員不需要針對封存信箱要求額外的儲存空間。

如需開啟自動展開封存的逐步指示，請參閱 [啟用無限期](enable-unlimited-archiving.md)封存。

> [!NOTE]
> 自動展開封存也支援共用信箱。 若要啟用共用信箱的封存，則需要有 Exchange Online 封存授權的 Exchange Online plan 2 授權或 Exchange Online plan 1 授權。

## <a name="how-auto-expanding-archiving-works"></a>自動展開封存的運作方式

如先前所述，在啟用使用者的封存信箱時，會建立額外的信箱儲存空間。 當自動展開的封存啟用時，Microsoft 365 會定期檢查封存信箱的大小。 封存信箱接近其儲存限制時，Microsoft 365 會自動為封存建立額外的儲存空間。 如果使用者已耗盡此額外的儲存空間，Microsoft 365 會為使用者的封存新增更多儲存空間。 此程式會自動進行，這表示系統管理員不需要要求額外的封存儲存或管理自動展開的封存。

以下是程式的快速綜述。

![自動展開的封存處理常式概述](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. 啟用使用者信箱或共用信箱的封存。 會建立具有 100 GB 儲存空間的封存信箱，並將封存信箱的警告配額設定為 90 GB。

2. 管理員啟用信箱的自動擴充封存。 當封存信箱 (包含 [可復原的專案] 資料夾) 達到 90 GB 時，它會轉換成自動展開的封存，而且 Microsoft 365 會將儲存空間新增至封存。 最多可能需要30天的時間，才能布建額外的儲存空間。

   > [!NOTE]
   > 如果信箱處於暫止狀態或指派給保留原則，當自動擴充封存啟用時，封存信箱的儲存配額會提升為 110 GB。 同樣地，封存警告配額增加為 100 GB。

3. Microsoft 365 會在必要時自動新增更多儲存空間。

> [!IMPORTANT]
> 只支援針對個別使用者使用的信箱 (或共用信箱) ，其成長率不會超過每日 1 GB。 使用者的封存信箱僅供該使用者使用。 不允許使用日誌記錄、傳輸規則或自動轉寄規則，將郵件複製到封存信箱。 Microsoft 保留在使用者的封存信箱用來儲存其他使用者的封存資料或其他不適當用途的情況下，拒絕無限封存的權利。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>哪些專案會移至其他封存儲存空間？

若要有效使用自動展開的封存儲存區，資料夾可能會移動。 Microsoft 365 會決定將其他儲存區新增至封存時，要移動的資料夾。 有時移動資料夾時，會自動建立一個或多個子資料夾，而且原始檔案夾中的專案會發佈到這些資料夾，以協助移動程式。 在 Outlook 中查看資料夾清單的封存部分時，這些子資料夾會顯示在原始檔案夾底下。  Microsoft 365 用來命名這些子資料夾的命名慣例是 **\<folder name\> _yyyy (在 mmm dd yyyy，yyyy h_mm) 上建立**，其中：

- **yyyy** 是一年接收資料夾中的郵件。

- **mmm dd，yyyy h_m** 是根據使用者的時區及 Outlook 中的區域設定，以 UTC 格式 Office 365 建立子資料夾的日期和時間。

下列螢幕擷取畫面顯示將郵件移至自動展開的封存之前和之後的資料夾清單。

 **新增額外的儲存體之前**

![已布建自動擴充封存之前，封存信箱的資料夾清單](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **新增額外的儲存空間之後**

![已布建自動展開封存後的封存信箱的資料夾清單](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> 如先前所述，Microsoft 365 會將專案移至子資料夾 (並以上述) 所述的命名慣例加以命名，以協助將內容散佈至輔助封存。 但是將專案移至子資料夾可能不一定是這樣。 有時候整個資料夾可能會移至輔助封存。 在此情況下，資料夾將保留其原始名稱。  在 Outlook 的資料夾清單中，資料夾已經移至輔助封存，它不會明顯。

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Outlook 存取自動擴充封存中的專案的需求

若要存取儲存在自動展開的封存中的郵件，使用者必須使用下列其中一個 Outlook 用戶端：

- Outlook 2016 或 Outlook 2019 for Windows

- Outlook 網頁版

- Outlook 2016 或 Outlook 2019 for Mac

以下是在網頁上使用 Outlook 或 Outlook 時所需考慮的一些事項，用以存取儲存在自動擴充封存中的郵件。

- 您可以存取封存信箱中的任何資料夾，包括已移至自動擴充儲存區域的資料夾。

- 在 web (OWA) 的 Outlook 中，可搜尋自動展開的封存。 類似于線上封存，您可以搜尋移至其他儲存體區域的專案。 選取 [封存] 做為 OWA 的搜尋範圍時，所有的封存 (（包括自動展開的封存）都會搜尋) 及其對應的子資料夾。

- 您可以在目前通道的 Outlook 桌面 (預覽) 中取得自動展開的封存搜尋。 在此預覽中，目前的信箱範圍可供使用，因此可讓您搜尋自動展開的封存。 如需此和其他 Microsoft 搜尋支援功能的相關資訊，請參閱使用[Microsoft 搜尋 Windows 連線至 Exchange Online 的 Outlook](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)。 

- 在自動展開的封存中，Outlook 和 Outlook (的 Outlook 和讀取/未讀取的計數中) 的專案計數，可能不會準確。

- 您可以刪除子資料夾中的專案，使其指向自動擴充的儲存區，但是無法刪除資料夾本身。

- 您無法使用 [復原刪除的郵件] 功能，從自動擴充的儲存區中復原已刪除的專案。

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>自動展開封存和其他符合性功能

本節說明自動擴充封存與其他法規遵從性及資料管理功能之間的功能。

- **eDiscovery：** 當您使用 eDiscovery 工具（例如內容搜尋或 In-Place 電子檔探索）時，也會搜尋自動擴充封存中的其他儲存區。

- **保留：** 當您使用訴訟 Exchange Online 暫止等工具（例如，[安全性與合規性中心] 中的「訴訟暫止」和「保留原則」）將信箱設為保留狀態時，位於自動展開封存中的內容也會處於暫止狀態。

- **通訊記錄管理 (MRM) ：** 如果您在 Exchange Online 中使用 MRM 刪除原則，以永久刪除到期的信箱專案，則也會刪除位於自動展開封存中的過期專案。

- 匯 **入服務：** 您可以使用 Office 365 匯入服務，將 PST 檔案匯入至使用者的自動展開封存。 您可以將最多 100 GB 的資料從 PST 檔案匯入至使用者的封存信箱。

## <a name="more-information"></a>其他資訊

如需自動展開封存的相關技術詳細資訊，請參閱[Microsoft 365：自動展開的封存常見問題](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)。
