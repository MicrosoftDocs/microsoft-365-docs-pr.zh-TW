---
title: 在 Microsoft 合規性管理員中使用評估範本
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何使用和管理範本，以在 Microsoft 合規性管理員中建立評估。 使用已格式化的 Excel 檔案建立及修改範本。
ms.openlocfilehash: ac5fe5f0a62c3b20021a9829499d8cec9339f72a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499025"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>在合規性管理員中使用評估範本

**本文內容：** 瞭解 **範本的運作方式** ，以及如何從評估範本頁面進行 **管理** 。 取得如何 **建立** 新範本、**修改** 現有範本、**使用 Excel 格式化範本資料**，以及匯出範本 **報告** 的指示。

> [!IMPORTANT]
> 您的組織可使用的評估範本取決於您的授權協定。 [查看詳細資料](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="templates-overview"></a>範本概述

範本是在合規性管理員中建立評估的控制項框架。 我們的綜合樣板集合可協助您的組織遵循管理資料集合及使用的本國、區域及特定行業的需求。 我們會將範本命名為與其基礎憑證或法規（如歐盟 GDPR 範本及 ISO 27001:2013 範本相同）的名稱。

 查看 [完整的範本清單](compliance-manager-templates-list.md)。

## <a name="template-types-included-and-premium-active-and-inactive"></a>範本類型：包括和特優、作用中和非使用中

#### <a name="included-and-premium-templates"></a>包含和精品範本

可供使用的範本是根據您組織的授權協定 ([查看授權詳細資料](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)) 。 範本有兩種類別：包括和特優。

1. **包含的範本** 可做為組織的授權合約的一部分使用。
2. 您必須購買 **進階版範本**，才能建立評估。 購買後，您可以視需要建立來自範本的評估數目。 [瞭解您可以如何購買精品範本](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。

#### <a name="active-and-inactive-templates"></a>使用中和非使用中範本

範本會顯示啟用狀態為 [使用中] 或 [非使用中]：

- **當您** 從該範本建立評估之後，就會將範本視為作用中。
- 如果您的組織未將範本用於評估，便會將其視為 **非** 使用中。

當您購買高階範本並從中建立評估時，該範本會在一年中使用。 除非您取消更新，否則您的購買將會自動更新。

**啟用的範本計數器**

「評估」頁面和「評估範本」頁面的上方有一個已啟動的 **範本** 計數器。 此計數器會顯示已使用的範本數目，而這些數目已超出您的授權合約的資格使用。

例如，如果計數器顯示2/5，這表示您的組織已啟動2個範本，可供使用。

如果計數器顯示5/2，這表示您的組織超出其限制，需要購買使用中的高級範本3。

如需詳細資訊，請參閱 [合規性管理員授權指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager) 。

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>從 [評估範本] 頁面查看及管理範本

合規性管理員中的 [評估範本] 頁面會顯示範本及主要詳細資料的清單。 此清單包含合規性管理員所提供的範本，以及您的組織已修改或建立的任何範本。 您可以套用篩選器，以根據憑證、產品範圍、國家、工業、建立者，以及範本是否啟用評估功能來尋找範本。

從其列中選取範本以顯示其詳細資料頁面。 此頁面包含範本的描述，以及憑證、範圍和控制項詳細資料的進一步資訊。 您可以從這個頁面選取適當的按鈕來建立評估、將範本資料匯出至 Excel，或修改範本。

## <a name="creating-and-modifying-templates-overview"></a>建立及修改範本概述

若要修改現有範本或建立您自己的新範本，您可以使用專門格式化的 Excel 試算表 ([下載範例](https://go.microsoft.com/fwlink/?linkid=2124865)) 來組合必要的控制項資料。 在完成試算表後，您可以在建立或修改範本的過程中將其匯入合規性管理員。

> [!NOTE]
> 試算表具有必須使用的特定格式和架構，否則將無法正確地匯入合規性管理員。 [格式設定指令](#formatting-your-template-data-with-excel)如下。

**所需角色**

只有擁有全域管理員或合規性管理員管理角色的使用者，才可以建立及修改範本。 深入瞭解 [角色和許可權](compliance-manager-setup.md#set-user-permissions-and-assign-roles)。

## <a name="create-a-new-template"></a>建立新的範本

若要建立您自己的新範本 (用來建立自訂評估) ，請遵循下列步驟。

1. 移至合規性管理員中的 [ **評估範本** ] 頁面。
2. 選取 [ **建立新範本**]。 隨即會開啟範本建立嚮導。
3. 選擇您要建立的範本類型。 在此情況下，請選取 [ **建立自訂範本**]，然後選取 **[下一步]**。
4. 在 [ **Upload** 檔案] 畫面中，選取 **[流覽]** ，尋找並上傳已格式化的 Excel 檔案包含所有必要的範本資料 (請參閱 [指示，以適當地格式化您](#formatting-your-template-data-with-excel)的檔案) 。
5. 如果您的檔案沒有任何問題，將會顯示上傳的檔案檔案名。 選取 **[下一步]** 繼續。  (如果您需要變更檔，請選取 [ **Upload 其他** 檔案) 。
    - 如果檔案有錯誤，頂端的錯誤訊息就會說明錯誤。 您必須修正檔案，然後重新上傳。 如果您的試算表格式不正確，或是某些欄位中有不正確資訊 (請重新參考 [格式設定](#formatting-your-template-data-with-excel)) 中，就會產生錯誤。  
    
6. [ **審閱] 和 [完成]** 畫面會顯示提升動作和控制項的數目，以及範本的最大分數。 準備好核准時，請選取 [ **建立範本]。**  (如果您需要進行變更，請選取 [ **上一步**]。 ) 
7. 最後一個畫面會確認已建立新的範本。 選取 [完成]， **結束** 嚮導。
8. 您將會收到新範本的詳細資料頁面，您可以在其中 [建立評估](compliance-manager-assessments.md#create-your-own-custom-assessment)。

## <a name="formatting-your-template-data-with-excel"></a>使用 Excel 格式化範本資料

用來建立範本的 Excel 試算表包含四個索引標籤，其中三個是必要的：

1. [範本](#template-tab) (必要) 
2. [ControlFamily](#controlfamily-tab) (必要) 
3.  (必要的[動作](#actions-tab)) 
4. [維度](#dimensions-tab) (選用) 

當您使用範本資料填滿試算表時，試算表  **必須依上述順序包含** 索引標籤，否則您的資料將無法成功匯入至範本。

##### <a name="template-tab"></a>範本] 索引標籤

[ **範本** ] 索引標籤是必要的。 此索引標籤中的資訊提供範本的中繼資料。 有四個必要的欄。 欄必須在 Excel 工作表上保持順序如下所列。 您可以在四欄 **後** 新增您自己的欄，以提供您自己的維度。 如果您這麼做，請務必使用 [下列指示](#dimensions-tab)將其新增至 [**維度**] 索引標籤。

- **職稱**：這是範本的標題，必須是唯一的。 您可以在合規性管理員中與其他範本共用名稱稱，包括您自己的範本或合規性管理員範本。

- **產品**：這是必要的維度。 列出與範本相關聯的產品。

- **認證**：這是您用來做為範本的規章。

- **inScopeServices**：這些是此項評估在產品內所用的服務 (例如，如果您 Office 365 產品中列出，Microsoft Teams 可能是一個範圍內的服務) 。 您可以列出多個以兩個分號分隔的服務。

> [!NOTE]
> 當您匯入試算表以建立或自訂範本後，您在 [ **產品** **] 和 [** 憑證] 儲存格中插入的資料便無法編輯。 此外，群組不能包含兩個具有相同 **產品/認證** 組合的評估。 您可以有多個範本搭配相同的產品/認證組合。

##### <a name="controlfamily-tab"></a>ControlFamily] 索引標籤

[ **ControlFamily** ] 索引標籤是必要的。  此索引標籤中的必要欄（必須遵循範例試算表中提供的順序）為：

- **controlName**：這是來自憑證、標準或法規（通常是某些類型的 ID）的控制項名稱。 控制項名稱在範本內必須是唯一的。 試算表中不可以有多個具有相同名稱的控制項。

- **controlFamily**：提供 controlFamily 的單字或片語，它會識別控制項的廣泛群組。 ControlFamily 不必是唯一的;它可以在試算表中列出一次以上。 同一個 controlFamily 也可以列于多個範本中，但彼此之間彼此沒有關系。 每個 controlFamily 都必須對應至至少一個控制項。

- **controlTitle**：提供控制項的標題。 雖然 controlName 是參考碼，但標題是一般會出現在規章中的 rtf 文字格式。

- **controlDescription**：提供控制項的描述。

- **controlActionTitle**：這是您想要與此控制項相關之動作的標題。 您可以新增多個分號，並以兩個分號隔開，中間沒有空格。 您清單中的每個控制項都必須至少包含一個動作，而且該動作必須存在 (也就是說，您可以在相同試算表的 [ **動作** ] 索引標籤、存在於不同範本中的動作，或是 Microsoft) 所建立的動作，列出您所列出的動作。 不同的控制項可以參照相同的動作。

##### <a name="actions-tab"></a>動作] 索引標籤

[ **動作** ] 索引標籤是必要的。  它會指定由您的組織管理的改進動作，而不是 Microsoft 的功能，這些動作已存在於合規性管理員中。 此索引標籤的必要欄（必須遵循範例試算表中提供的順序）為：

- **actionTitle**：這是您動作的標題，而且是必要的欄位。 您提供的標題必須是唯一的。 **重要**：如果您參考的是已存在的動作 (例如在另一個範本中) ，且在後續欄中修改其任何元素，這些變更將會傳播至其他範本中的相同動作。

- **implementationType**：在此必要欄位中，列出下列三種實施類型之一：
    - 由人員和程式所 **執行的動作**，以保護組織系統、資產、資料和人員的機密性、完整性和可用性 (範例：安全性意識和訓練) 
    - **技術** -透過使用資訊系統的硬體、軟體或固件元件所包含的技術和機制完成的動作，以保護組織系統和資料的機密性、完整性和可用性 (範例：多重要素驗證) 
    - **檔** -透過記錄的原則及程式所執行的動作，建立及定義保護組織系統、資產、資料和人員的機密性、完整性和可用性所需的控制項 (範例：資訊安全性原則) 

- **actionScore**：在這個必要的欄位中，為您的動作提供數值分數值。 它必須是介於1到99的整數。它不得為0、null 或空白。 數位越高，其價值越高，以改善您的相容性狀況。 下圖示范合規性管理員的分數控制項：

![合規性管理員控制點值](../media/compliance-score-action-scoring.png "合規性管理員控制點值")

- **actionDescriptionTitle**：這是描述的標題，而且是必要專案。 此描述標題可讓您在多個範本中使用相同的動作，並在每個範本中呈現不同的描述。  此欄位可協助您澄清描述所參照的範本。 在大多數情況下，您可以在此欄位中放置您建立的範本名稱。

- **actionDescription**：提供動作的描述。 您可以套用粗體文字和超連結等格式。 這是必要欄位。

- **維度-動作目的**：這是選用的欄位。 如果包含此標頭，則標頭必須包含 "dimension" 前置詞。 在此包含的任何維度，都將做為合規性管理員中的篩選器，並顯示在合規性管理員的 [改進動作詳細資料] 頁面上。

##### <a name="dimensions-tab"></a>維度] 索引標籤

[ **維度** ] 索引標籤是選用的。 不過，如果您在其他位置參照維度，但如果它不存在於您已建立的範本或在 Microsoft 範本中，則需要在這裡加以指定。 此索引標籤的欄如下所示：

- **dimensionKey**：清單為 "product"，"認證，" 「動作目的」
- **dimensionValue**：範例： Office 365、HIPPA、預防性、偵探

您可以前往 **租使用者管理** ，然後選取 [ **維度** ] 索引標籤，以查看現有的維度。此外，當您匯出現有的範本時，匯出的試算表會有 [ **維度** ] 索引標籤，該索引標籤會列出範本中所用的所有維度。

## <a name="modify-a-template"></a>修改範本

您可能想要修改已經建立的範本，例如新增控制項，或新增或移除改進動作。 此程式類似于範本建立程式，您會使用範本資料上傳已格式化的 Excel 檔案。

不過，當您使用現有範本資料的變更來格式化檔案時，會有特定的詳細資料需要注意。 **建議您仔細閱讀這些指示，以確保您不會覆寫任何您想要保留的現有資料。**

### <a name="template-modification-process-steps"></a>範本修改流程步驟

若要修改範本，請遵循下列步驟：

1. 在 [ **評估範本** ] 頁面上，選取您要修改的範本，它會顯示其詳細資料頁面。
2. 選取 [**匯出至 Excel**]。 將下載所有範本資料的 Excel 檔案。 將檔案儲存到您的本機電腦。
3. [使用下列指示，修改 Excel](#formatting-your-excel-file-to-modify-a-template)檔案，以進行您的範本變更。
4. 當您變更 Excel 檔案之後，請儲存檔案。
5. 在範本的 [詳細資料] 頁面上，選取 [ **修改範本** ] 以啟動修改嚮導。 
6. 在 **Upload** 檔] 畫面上，選取 **[流覽]** ，尋找並上傳您的 Excel 檔案。
7. 如果您的檔案沒有任何問題，下一個畫面會顯示上傳的檔案名稱。 選取 **[下一步]** 繼續 (如果您需要變更檔案，請選取 [ **Upload 其他** 檔案) ]。
    - 如果檔案有問題，頂端的錯誤訊息會說明錯誤。 您必須修正檔案，然後重新上傳。 如果您的試算表格式不正確，或某些欄位中有不正確資訊，就會產生錯誤。

8. [ **審閱] 和 [完成]** 畫面會顯示提升動作和控制項的數目，以及範本的最大分數。 準備好核准時，請選取 **[下一步]**。
9. 最後一個畫面會確認已修改範本。 選取 [完成]， **結束** 嚮導。

您的範本現在會包含您所做的變更。 使用此修改範本的任何評估現在會顯示暫止的更新，而且您必須接受評估的更新，以反映在範本中所做的變更。 深入瞭解 [評估的更新](compliance-manager-assessments.md#accepting-updates-to-assessments)。

> [!NOTE]
> 如果您以英文以外的語言使用合規性管理員，請注意，當您將範本匯出成 Excel 時，有些文字會以英文顯示。 您的 [改進動作] 和 [Microsoft 動作]) 的動作標題，都必須以英文的方式 (以供控制項識別。 如果您變更動作標題，請務必以英文撰寫，這樣檔案才能正確地匯入。

### <a name="formatting-your-excel-file-to-modify-a-template"></a>格式化您的 Excel 檔案以修改範本

請跳至下列章節，快速找出您需要的指示：

- [編輯主要範本屬性](#edit-the-main-template-attributes)
- [新增改進動作](#add-an-improvement-action)
- [編輯改進動作的資訊](#edit-an-improvement-actions-information)
- [變更改進動作的名稱](#change-an-improvement-actions-name)
- [移除改進動作](#remove-an-improvement-action)
- [移除控制項](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>編輯主要範本屬性

在 [ **範本** ] 索引標籤上，您可以編輯 [ **標題** ] 欄中的任何專案、[ **inScopeServices** ] 欄，以及您可能新增的任何其他欄位。 不過，您無法在 [ **產品** ] 或 [ **認證** ] 欄中編輯任何專案。

#### <a name="add-an-improvement-action"></a>新增改進動作

1. 移至 [ **動作** ] 索引標籤。將您的資訊新增至現有動作下方第一個空白列中的必要欄位。
2. 移至 [ **ControlFamily** ] 索引標籤。尋找包含您的改善動作所對應之控制項的列。 將您的新動作新增至該列中的 [ **controlActionTitle** ] 欄 (請記得在此欄位中，將多個動作與兩個分號隔開，介於) 之間沒有空格。
3. 儲存試算表。

#### <a name="edit-an-improvement-actions-information"></a>編輯改進動作的資訊

您可以變更任何改進動作的資訊 *，但其標題除外*。 您可以編輯來自 B + + 的任何儲存格，以及將檔案匯入範本後，該範本中的改進動作現在會包含更新的資料。

您無法編輯 **actionTitle** (] 欄位 A) ，因為如果您這麼做，合規性管理員會將此項視為新的改進動作。 如果您想要變更改進動作的名稱，請參閱下列直接的指示。

#### <a name="change-an-improvement-actions-name"></a>變更改進動作的名稱

如果您想要變更改進動作的名稱，您必須在試算表中明確指定您要以新名稱取代現有名稱。 遵循下列步驟：

1. 在試算表的 [ **動作** ] 索引標籤中，將新欄新增至 a 欄後的試算表中。
2. 在這個新欄中（現在是 B 欄），置於第1列： **oldActionTitle** 中的標題。
3. 複製欄 A 的內容，並將其貼到 B 欄中。這會將您現有的改進動作標題（即您想變更的專案）放入 B 欄中。
4. 在 [欄 A] 中， **actionTitle**] 刪除舊名稱，並以新名稱取代，以進行改進動作。

請注意，您的改善動作和 Microsoft 動作的動作標題都必須以英文撰寫，以便在控制項中參照時加以識別。

#### <a name="remove-an-improvement-action"></a>移除改進動作

若要從範本移除 [改進] 動作，您必須將其從每一個參照它的控制項中移除。 請遵循下列步驟來修改您的試算表：

1. 在 [ **ControlFamily** ] 索引標籤上，搜尋您要移除之 [改進動作] 的標題。
2. 在顯示的儲存格中刪除改進動作的標題。 如果 [改進] 動作是該資料列上唯一的動作，請刪除整列 (移除控制項) 。
3. 在 [ **動作** ] 索引標籤上，刪除包含您要刪除之 [改進] 動作的列。
4. 儲存試算表。

當您將試算表重新匯入範本時，您的改善動作將會從範本中移除。

從範本移除改進動作並不會完全移除合規性管理員的改進動作。 該動作仍可由另一個範本參照。

#### <a name="remove-a-control"></a>移除控制項

若要移除控制項，請遵循下列步驟修改您的試算表，然後重新匯入試算表：

1. 在 [ **ControlFamily** ] 索引標籤的 [ **controlName** ] 欄中，找到您要移除的控制項。
2. 刪除該控制項的列。
    - 如果這個已刪除的控制項包含其他控制項未參考的改善動作，您必須從 [ **動作** ] 索引標籤中移除這些改進動作。否則，您會收到驗證錯誤。

3. 儲存試算表。

當您將試算表重新匯入範本時，您的控制項將會從範本中移除。

## <a name="export-a-template"></a>匯出範本

您可以匯出包含所有範本資料的 Excel 檔案。 您必須匯出範本，才能修改範本，因為這會是您在[修改](#modify-a-template)程式中編輯和上傳的 Excel 檔案。

若要匯出範本，請移至您的 [範本詳細資料] 頁面，然後選取 [**匯出至 Excel** ] 按鈕。

請注意，匯出您從合規性管理員範本擴充的範本時，匯出的檔案只會包含您新增至範本的屬性。 匯出的檔案不會包含 Microsoft 所提供的原始範本資料。 若要取得這類報告，請參閱 [匯出評估報告](compliance-manager-assessments.md#export-an-assessment-report)的指示。