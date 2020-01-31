---
title: 管理 custodians 進階電子文件探索案例中
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0b6776571f4abafaf8e050fa6c31311df452d90e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41582912"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>管理 custodians 進階電子文件探索案例中

在進階電子文件中的 [Custodians] 索引標籤包含所有 custodians 已新增至案例清單。 您將 custodians 新增至案例之後，每個 custodian 詳細自動收集自 Azure Active Directory 且進階電子文件探索中檢視。

![管理 Custodians](media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>檢視 custodian 詳細資料

若要檢視有關 custodian 的詳細資訊，請按一下 [ **Custodians** ] 索引標籤上，從清單 custodian。彈出式頁面隨即出現，並包含 custodian 的下列資訊：

- 連絡人資訊

  - **顯示名稱**-custodian 顯示在通訊錄中的名稱。 這通常是 custodian 名字]、 [中間的初始，和最後一個名稱的組合。
  
   - **郵件/SMTP** -custodian，例如 brianj@contoso.onmicrosoft.com 的主要 SMTP 位址。 請注意 custodian 的使用者主要名稱 (UPN) 也會列。

  - **標題**-custodian 的職稱。

  - **部門**-custodian 適用於部門的名稱。

  - **管理員**-custodian 的管理員。 指定的管理員會收到此 custodian 任何呈報通訊。
  
- 位置資訊

  - **縣/市**-custodian 所在的市/鎮。

  - **狀態**-縣 / 市 custodian 的地址。

  - **國家/地區**-custodian 所在的國家/地區。

  - **Office** -商務版 custodian 就地的辦公室位置。

- 案例資訊

  - **保留狀態**-會指出是否 custodian 具有已處於保留狀態。 

  - **通訊狀態**： 指出 custodian 是否已經發出保留通知。 如果 custodian 已發出的通知，此屬性的這個值會是**已發佈**。 如果 custodian 已不發出通知，狀態會**取消發佈**。 

  - **狀態**-在 case custodian 的狀態。 **作用中的**] 狀態表示 custodian 是這種情況的一部分。 如果 custodian 一經釋出從案例，狀態會變更為**發行**。 

- 資料來源及索引資訊

    - **資料來源**-顯示計數和類型的資料來源 （信箱、 網站和小組） 與 custodian 相關聯，而且這種情況的一部分。

    - **索引更新時間**-會指出上次觸發進階索引工作的日期和時間。 此屬性也會指出當進階索引處理序正在進行中。


## <a name="edit-a-custodian"></a>編輯 custodian

隨著您案例的進度，您可能會發現可能有其他資料來源相關的特定 custodian & 您的案例。 在其他情況下，您可能想要移除特定資料來源的檢閱和視為不相關。

若要更新 custodian 相關聯的資料來源：

1. 移至**eDiscovery > 進階電子文件**，並開啟案例。
  
2. 按一下 [ **Custodians** ] 索引標籤。
  
3. 從清單中選取 custodian，然後按一下 [彈出式頁面的 [**編輯**。

    ![編輯資料來源](media/EditCustodianDataSource.PNG)
  
4. 按一下 [**選擇資料來源**] 索引標籤，若要變更 custodian 的 Exchange 信箱和 OneDrive 帳戶的設定，請按一下 [**選擇資料來源**。
  
5. 按一下 [**選取其他資料來源**] 索引標籤來新增或移除小組、 SharePoint，或 Exchange custodian 相關聯的信箱。 

    如需 custodian 相關聯的資料來源的詳細資訊，請參閱 「 步驟 3： 建立關聯的其他資料來源]，以 custodian 「[新增 custodians 案例](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian)中。 
  
6. 按一下 [啟用或停用保留 custodian **custodial 就地保留**]。

## <a name="resolve-custodian-processing-errors"></a>解決 custodian 處理錯誤

在大部分法律調查的 eDiscovery 工作流程，custodian 新增的法律案件之後搜尋 custodian 資料的子集。 非常大的檔案大小或可能造成資料損毀，因為 custodian 相關聯的資料來源中的某些項目可能是已局部編製索引。 在進階電子文件中使用的[進階編製索引](indexing-custodian-data.md)的功能，最局部編製索引的項目可進行自動修復藉由重新編製索引視需要這些項目。

當 custodian 新增至案例時，位於 custodian 相關聯的資料來源的資料會自動重新編製索引 （藉由進階索引程序）。 這表示您可以將保留資料就地而不必下載並修復它再搜尋離線）。 不過，週期中法律案例新資料來源可能與 custodian 相關聯。 在此情況下，您重新編製索引 custodian 的資料重新執行 [進階索引程序，以修正任何已局部編製索引的項目，並更新 custodian 資料的索引。

若要觸發地址重新編製索引程序已局部編製索引的項目：

1. 移至**eDiscovery > 進階電子文件**，並開啟案例。

2. 按一下以**Custodians] 索引標籤**，，然後選取 [的 custodian，其資料必須編製索引。 

3. 在彈出式頁面上，按一下 [**更新索引**]。

   會顯示對話方塊，指出已建立索引工作。

重新編製索引 custodian 資料是長時間執行的程序;相對應的工作會建立名為**重新編製索引 custodian 資料**。 您可以藉由監視**編製索引工作狀態**] 欄中的狀態，[**工作**] 索引標籤或 [ **Custodians** ] 索引標籤上追蹤進度。

如需詳細資訊，請參閱：

- [使用處理錯誤](processing-data-for-case.md)

- [管理工作](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>釋出 custodian 從案例

發行日期 custodian 在會在關閉案例的情況下，custodian 不再下義務以保留內容的情況下，或當 custodian 會被視為不會再是與案件相關。 

如果已發佈保留通知之後，您就會釋放 custodian，發行通知會傳送至 custodian。 此外，會移除任何已 custodian 相關聯的資料來源上的保留。 如果 custodian 放在*無訊息保留*、 他們未發出任何法律保留通知、 發行通知將不會傳送，但已與該 custodian 相關聯的資料來源上任何保留移除。

若要發行 custodian: 

1. 移至**eDiscovery > 進階電子文件**，並開啟案例。

2.  移至 [ **Custodians** ] 索引標籤。

3.  **Custodians] 索引標籤上**，按一下，然後選取 [從案例的 [custodian 正在發行日期。

4. 在彈出式頁面上，按一下 [**發行 custodian**]。

   警告] 頁面上會顯示說明，是否保留暫留 custodian 相關聯的資料來源時，保留會被移除，以及其他任何保留與不同的進階電子文件探索案例相關聯仍然會套用。 包括 Office 365 中的其他類型的保留和保留功能 （例如 Office 365 保留原則）。

5. 按一下 **[是]** ，確認您想要釋出 custodian。 

    請注意，此使用者**Custodians** ] 索引標籤上的狀態設為**已發行**和**保留狀態**的彈出式頁面會變更為**False**。 

> [!NOTE]
> Custodian 可能同時參與數個法律案件。 當 custodian 發行從案例時，不會影響保留和跨其他事件通知。

## <a name="bulk-edit-custodians"></a>大量編輯 custodians

您可以使用大量編輯器來編輯多個 custodians 為同一時間。 若要這麼做，請只選取兩個或多個 custodians **Custodians** ] 索引標籤上的顯示大量編輯程式，然後按一下下列其中一個工作。

![若要編輯的多個 custodians 設定彈出式頁面](media/AeDBulkEditCustodians.png)