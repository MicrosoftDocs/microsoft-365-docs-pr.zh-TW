---
title: 在 Office 365 中的無限制封存概觀
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
description: 了解自動展開封存在 Office 365 中，可提供無限制的封存儲存 Exchange Online 信箱。
ms.openlocfilehash: e7d004c7ef92fbcb331191432a70114f36dabc07
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601361"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a>在 Office 365 中的無限制封存概觀

在 Office 365 中封存信箱提供使用者額外信箱儲存空間。 啟用使用者的封存信箱之後，最多 100 GB 的額外儲存空間使用。 在過去，當已達到 100 GB 的儲存空間配額，組織必須與 Microsoft 連絡到的封存信箱的要求額外儲存空間。 這不再是這種情況。

Office 365 （稱為*自動展開封存*） 中的無限制封存功能提供封存信箱中的額外儲存空間。 達到封存信箱中的儲存配額時，Office 365 會自動增加的封存，這表示使用者不會用盡信箱儲存空間和系統管理員不需要要求封存信箱的額外儲存空間。

如需逐步指示的開啟自動展開封存，請參閱[啟用 Office 365 中的無限制封存](enable-unlimited-archiving.md)。

> [!NOTE]
> 自動展開封存也支援共用信箱。 若要啟用信箱的共用信箱的封存，Exchange Online Plan 2 授權或具有 Exchange Online Archiving 授權的 Exchange Online Plan 1 授權就需要。

## <a name="how-auto-expanding-archiving-works"></a>如何自動展開封存的運作

為先前所述的其他信箱啟用使用者的封存信箱時，會建立儲存空間。 啟用自動展開封存時，Office 365 會定期檢查封存信箱的大小。 當封存信箱取得接近其儲存限制時，Office 365 會自動建立封存的額外儲存空間。 如果使用者執行此額外儲存空間不足，Office 365 會將更多儲存空間新增至使用者的封存。 這表示系統管理員不必要求其他封存儲存區，或管理自動展開封存此程序會自動發生。

以下是程序的簡要概觀。

![自動展開封存程序概觀](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. 使用者信箱或共用的信箱啟用封存。 會建立封存信箱具有 100 GB 的儲存空間，且封存信箱的 [警告] 配額設為 90 GB。

2. 系統管理員可讓自動展開封存信箱。 當封存信箱 （包括 [可復原的項目] 資料夾） 達到 90 GB 時，則會轉換成自動展開封存，與 Office 365 會儲存空間新增至封存。 可能需要最多 30 天的額外儲存空間來佈建。

   > [!NOTE]
   > 如果信箱會處於暫止狀態或指派給 Office 365 保留原則，啟用自動展開封存時增加封存信箱的儲存配額為 110 GB。 同樣地，封存警告配額增加到 100GB。

3. Office 365 會自動新增更多儲存空間，必要時。

> [!IMPORTANT]
> 自動展開封存才支援信箱用於個別使用者 （或共用信箱） 不會超過 1 GB，每天成長率。 使用者的封存信箱僅供該使用者使用。 不允許使用日誌、 傳輸規則或自動轉寄規則將郵件複製到封存信箱。 Microsoft 保留拒絕使用者的封存信箱用於儲存其他使用者的封存資料的執行個體中或在另一些情況的不當使用無限制封存的權限。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>項目取得移至其他封存儲存空間？

若要有效使用自動展開封存儲存，可能會移動資料夾。 Office 365 會決定哪些資料夾取得移至封存新增額外的儲存空間時。 有時時移動資料夾，會自動建立一或多個的子資料夾，原來的資料夾中的項目會分配到這些資料夾以利移動程序。 當您在 Outlook 中檢視資料夾清單] 的封存部分，這些子資料夾會顯示原始資料夾下。  Office 365 使用來命名這些子資料夾的命名慣例為**\<資料夾名稱\>_yyyy （上建立 mmm dd，yyyy h_mm）**，其中：

- **yyyy**是所收到的郵件] 資料夾中的年份。

- **mmm dd，yyyy h_m**是子資料夾由 Office 365 中，建立以 UTC 格式，根據使用者的時區和 Outlook 中的地區設定的時間與日期。

下列螢幕擷取畫面顯示的資料夾清單前面和後面的郵件會移至自動展開封存。

 **之前新增額外儲存空間**

![之前已佈建自動展開封存的封存信箱的資料夾清單](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **之後新增額外儲存空間**

![之後已佈建自動展開封存的封存信箱的資料夾清單](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> 如先前所述，Office 365 將項目移至子資料夾 （以及它們使用的命名慣例上面所述的名稱），協助分配到輔助封存的內容。 但是，將項目移至子資料夾不一定大小寫。 有時整個資料夾可能會移到輔助封存。 在此情況下，該資料夾會保留其原始的名稱。  它不會明顯資料夾已移至輔助封存在 Outlook 中的資料夾清單。

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Outlook 需求，來存取自動展開封存中的項目

若要存取儲存在自動展開封存的郵件，使用者必須使用下列其中一個下列 Outlook 用戶端：

- Outlook 2016 或 Windows 版 Outlook 2019

- Outlook 網頁版

- Outlook 2016 或 Outlook for Mac 的 2019

以下是使用 Outlook 或 Outlook 來存取郵件中自動展開封存儲存網頁時要考慮的事項。

- 您可以存取封存信箱時，包括已移至自動展開存放區中的任何資料夾。

- 您可以搜尋的只是藉由搜尋資料夾本身已移至其他儲存區的項目。 這表示您已選取 [封存] 資料夾在資料夾清單中選取 [**目前的資料夾**選項作為搜尋範圍。 同樣地，如果自動展開存放區中的資料夾含有子資料夾，您必須個別搜尋每個子資料夾。

- Outlook 中的項目計數，而且可能無法正確自動展開封存中的讀取/未讀計數 （在 Outlook 和 outlook 網頁版）。

- 您可以刪除指向自動展開存放裝置] 區域中，子資料夾中的項目，但不能刪除資料夾本身。

- 您無法使用 [復原刪除的項目] 功能來復原已從自動展開存放區刪除的項目。

## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a>自動展開封存和其他 Office 365 合規性功能

本章節說明自動展開封存和其他 Office 365 合規性和資料控管功能之間的功能。

- **eDiscovery:** 當您使用 Office 365 電子文件探索工具，例如內容搜尋 」 或 「 就地 eDiscovery 」 也會搜尋中自動展開封存的額外儲存空間區域。

- **保留：** 當您讓信箱處於保留使用例如訴訟暫止的工具在 Exchange 線上] 或 [eDiscovery 案例保留與位於自動展開封存的保留原則中的安全性與合規性中心，內容也會處於暫止。

- **通訊記錄管理 (MRM):** 如果您使用 Exchange Online 中的 MRM 刪除原則若要永久刪除過期的信箱項目，也會刪除過期的項目位於自動展開封存。

- **匯入服務：** 您可以使用 Office 365 匯入服務將 PST 檔案匯入使用者的自動展開封存。 您可以到使用者的封存信箱，最多 100 GB 的資料匯入從 PST 檔案。

## <a name="more-information"></a>詳細資訊

如需自動展開封存，請參閱詳細技術的詳細資訊[Office 365： 自動展開封存常見問題集](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。
