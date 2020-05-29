---
title: 關閉、重新開啟和刪除核心 eDiscovery 案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明如何管理核心 eDiscovery 案例。 這包括關閉案例、開啟關閉的案例，以及刪除案例。
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412792"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>關閉、重新開啟和刪除核心 eDiscovery 案例

本文說明如何關閉、重新開啟和刪除 Microsoft 365 中的核心 eDiscovery 案例。

## <a name="close-a-case"></a>關閉案例

當核心 eDiscovery 案例支援的法律案例或調查完成後，您就可以關閉案例。 以下是關閉案例時會發生的情況：
  
- 若案例包含 eDiscovery 保留中的任何內容位置，將會關閉那些保留。 關閉關閉後，30天的寬限期（稱為*延遲保留*）會套用到保留中的內容位置。 這有助於防止內容立即刪除，並可讓系統管理員在延遲保留期間到期後，永久刪除內容之前，先進行搜尋並還原內容的機會。 如需詳細資訊，請參閱[移除 eDiscovery 保留中的內容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。

- 關閉案例只會關閉與該案例相關聯的保留。 如果其他保留放在內容位置（例如訴訟暫止、保留原則或不同核心 eDiscovery 案例的保留）上，則仍會保留這些保留。

- 此案例仍列在 Microsoft 365 規範中心的核心 eDiscovery 頁面上。 已關閉案例的詳細資料、保留、搜尋及成員都會保留。

- 您可以在關閉案例後進行編輯。 例如，您可以新增或移除成員、建立搜尋並匯出搜尋結果。 主動和封閉式案例之間的主要差異是關閉案例時，會關閉 eDiscovery 保留。

若要關閉案例：
  
1. 在 Microsoft 365 規範中心，按一下 [ **eDiscovery**  >  **Core** ] 以顯示您組織中的核心 eDiscovery 案例清單。

2. 按一下您要關閉之案例的名稱。

    [**管理此案例**飛出] 頁面隨即顯示。

3. 在 [**管理案例狀態**] 底下，按一下 [**關閉案例**]。

    會顯示警告，指出與案例相關聯的保留會關閉。

4. 按一下 **[是]** 以關閉案例。

    [**管理此案例**] 飛入頁面上的狀態會**從 [** 使用中] 改為 [**關閉**]。

5. 關閉 [**管理此案例**] 頁面。

6. 在 [**核心 eDiscovery** ] 頁面上 **，按一下 [** 重新整理] 以更新封閉式案例的狀態。 完成關閉程式可能需要長達60分鐘的時間。

    當程式完成時，**核心 eDiscovery**頁面上的案例狀態會變更為 [**已關閉**]。 再次按一下案例的名稱，以顯示 [**管理此案例**飛出] 頁面，該頁面包含案例已關閉及關閉者的相關資訊。

## <a name="reopen-a-closed-case"></a>重新開啟已關閉的案例

當您重新開啟案例時，關閉案例時所使用的任何 eDiscovery 保留都不會自動復原。 在重新開啟案例之後，您必須移至 [**保留**] 頁面並開啟先前保留。 若要開啟保留，請選取它以顯示飛入頁面，然後將**狀態**切換設定為 [**開啟**]。
  
1. 在 Microsoft 365 規範中心，按一下 [ **eDiscovery**  >  **Core** ] 以顯示您組織中的核心 eDiscovery 案例清單。

2. 按一下您要重新開啟之案例的名稱。

    [**管理此案例**飛出] 頁面隨即顯示。 

3. 在 [**管理案例狀態**] 底下，按一下 [**重新開啟案例**]。

    會顯示警告，指出在關閉此案例時，其所關聯的保留不會自動開啟。

4. 按一下 **[是]** 重新開啟案例。

    「**管理此案例**」彈出頁面上的狀態會從 [**已關閉**] 變更為 [**使用中]。**

5. 關閉 [**管理此案例**] 頁面。 

6. 在**核心 eDiscovery**頁面上 **，按一下 [** 重新整理] 以更新重新開啟之案例的狀態。 最多可能需要60分鐘的時間，重新開啟程式才會完成。 

    當程式完成時，**核心 eDiscovery**頁面上的案例狀態會變更為 [**作用中]** 。 
  
## <a name="delete-a-case"></a>刪除案例

您也可以刪除主動及封閉式核心 eDiscovery 案例。 當您刪除案例時，案例中的所有搜尋和匯出都會被刪除，而且案例會從 Microsoft 365 規範中心的**核心 eDiscovery**頁面上的案例清單中移除。 您無法重新開啟已刪除的案例。

您必須先刪除*所有*與案例相關聯的 eDiscovery 保留，才可刪除案例（不論是作用中或已關閉）。 這包括刪除狀態為**Off**的保留。 

若要刪除 eDiscovery 保留：

1. 移至 [**保留**] 索引標籤中您要刪除的情況。

2. 按一下您要刪除的保留。

3. 在飛入頁面上，按一下 [**刪除保留**]。

若要刪除案例：

1. 在 Microsoft 365 規範中心，按一下 [ **eDiscovery**  >  **Core** ] 以顯示您組織中的核心 eDiscovery 案例清單。

2. 按一下您要刪除之案例的名稱。

3. 在 [飛入] 頁面上，按一下 [**管理案例狀態**] 底下的 [**刪除案例**]。

如果您嘗試刪除的案例仍包含 eDiscovery 保留，您會收到錯誤訊息。 您必須刪除所有與案例相關聯的保留，然後再試一次，以刪除案例。
