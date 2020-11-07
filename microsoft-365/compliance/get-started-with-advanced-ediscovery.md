---
title: Microsoft 365 中的高級 eDiscovery 入門
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 本文說明如何開始使用 Microsoft 365 中的「高級 eDiscovery」。 完成一些快速步驟之後，就可以使用「高級 eDiscovery」工具。 第一步是建立案例，然後開始使用 Advanced eDiscovery 的功能和功能。
ms.openlocfilehash: 59537499ed52f44a9d32b8921fd297c5cd7c0d3f
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944331"
---
# <a name="get-started-with-advanced-ediscovery"></a>開始使用進階電子文件探索

Microsoft 365 中的「高級 eDiscovery」提供 [端對端工作流程](overview-ediscovery-20.md#advanced-ediscovery-architecture) ，可保留、收集、審查、分析和匯出回應組織內部和外部調查的資料。 不需要部署高級 eDiscovery，但是必須先執行一些必要的工作，IT 系統管理員和 eDiscovery 管理員必須完成，您的組織才可以開始建立及使用高級 eDiscovery 案例來管理調查。

本文討論設定高級 eDiscovery 所需的步驟。 這包括確定存取高級 eDiscovery 及將保管人新增至案例的適當授權，以及將許可權指派給法律和調查小組，讓他們可以存取和管理案例。 本文也提供使用案例來管理法律調查之高級 eDiscovery 工作流程的高層次概述。

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>步驟1：確認並指派適當的授權

「高級 eDiscovery」的授權需要適當的組織訂閱和每一使用者授權。

- **組織訂閱：** 若要存取 Microsoft 365 規範中心或安全性 & 規範中心的高級 eDiscovery，您的組織必須具備下列其中一項：

  - Microsoft 365 E5 或 Office 365 E5 訂閱
  
  - 含 E5 合規性附加元件的 Microsoft 365 E3 訂閱

  - 具有 E5 電子檔探索和審核附加元件的 Microsoft 365 E3 訂閱

  如果您沒有現有的 Microsoft 365 E5 計畫，且想要嘗試使用 Advanced eDiscovery，您可以 [將 microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 至現有的訂閱，或註冊 Microsoft 365 E5 的 [試用版](https://www.microsoft.com/microsoft-365/enterprise) 。

- **每位使用者授權：** 若要在預先 eDiscovery 案例中將使用者新增為系統管理員，該使用者必須根據您的組織訂閱，被指派下列其中一個授權：

  - Microsoft 365：使用者必須被指派 Microsoft 365 E5 授權、E5 相容性附加元件授權或 E5 eDiscovery 和審核附加元件授權。

  - Office 365：使用者必須獲指派 Office 365 E5 授權。

   如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

> [!NOTE]
> 使用者只需要 E5 授權 (或適當的附加元件授權) ，以在高級 eDiscovery 案例中新增為保管人。 IT 系統管理員、eDiscovery 管理員、律師、paralegals 或調查人員，使用高級 eDiscovery 來管理案例及審閱案例資料，不需要 E5 或附加元件授權。

## <a name="step-2-assign-ediscovery-permissions"></a>步驟2：指派 eDiscovery 許可權

若要存取高級 eDiscovery 或新增為高級 eDiscovery 案例的成員，必須對使用者指派適當的許可權。 具體說來，使用者必須新增為安全性 & 規範中心的 eDiscovery 管理員角色群組成員。 這個角色群組的成員可以建立及管理高級 eDiscovery 案例。 他們可以新增及移除成員、將保管人和內容位置置於保留狀態、管理合法保留通知、建立及編輯案例中相關聯的搜尋、將搜尋結果新增至審閱集、分析複查集中的資料，以及從高級 eDiscovery 案例匯出及下載。

完成下列步驟，將使用者新增至 eDiscovery 管理員角色群組：

1. 移至 [https://protection.office.com/permissions](https://protection.office.com/permissions) 並使用您的 Microsoft 365 組織中的系統管理員帳戶的認證登入。

2. 在 [ **許可權** ] 頁面上，選取 [ **eDiscovery 管理員** ] 角色群組。

3. 在 [eDiscovery 管理員飛出] 頁面上，按一下 [ **Ediscovery 管理員** ] 區段旁邊的 [ **編輯** ]。

4. 在 [編輯角色群組] 嚮導的 [ **選擇 EDiscovery 管理員** ] 頁面上，按一下 **[選擇探索管理員** ]。

5. 按一下 [ **新增** ]，然後選取您要新增至角色群組之所有使用者的核取方塊。

6. 按一下 [ **新增** ] 以新增選取的使用者，然後按一下 [ **完成** ]。

7. 按一下 [ **儲存** ]，將使用者新增至角色群組，然後按一下 [ **關閉** ] 完成步驟。

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>EDiscovery 管理員角色群組的詳細資訊

EDiscovery 管理員角色群組中有兩個子群組。 這些子群組之間的差異是以範圍為基礎。

- **EDiscovery 管理員：** 可以查看和管理其所建立或其成員的高級 eDiscovery 案例。 如果另一個 eDiscovery 管理員建立了案例，但沒有將第二個 eDiscovery 管理員新增為該案例的成員，則第二個 eDiscovery 管理員將無法在「規範中心」的 [高級 eDiscovery] 頁面上，查看或開啟此案例。 一般說來，您組織中的大部分人員都可以新增至 eDiscovery Manager 子組。

- **EDiscovery 管理員：** 可以執行 eDiscovery 管理員可以執行的所有案例管理工作。 此外，電子檔探索管理員也可以：

  - 查看 [高級 eDiscovery] 頁面上列出的所有案例。
  
  - 管理組織中的任何案例後，將自己新增為案例成員。

  - 針對組織中的任何案例，存取及匯出案例資料。

  因為存取範圍廣泛，所以組織應該只有少數管理員是 eDiscovery Administrators 子群組的成員。

如需有關 eDiscovery 許可權的詳細資訊，以及指派給 eDiscovery 管理員角色群組之每個角色的說明，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>步驟3：設定高級電子檔探索的全域設定

在貴組織中的人員開始建立及使用案例之前完成的最後一個步驟，就是設定適用于組織中所有案例的全域設定。 目前只有一個全域設定是 *律師-用戶端許可權偵測* (未來) 會提供更多全域設定。 當您分析考核集中的資料時，此設定可讓律師-用戶端許可權模型執行。 模型使用電腦學習，判斷檔中包含法律性質的內容的可能性。 此外，它也會比較檔的參與者清單 (在您設定模型) 時所提交的律師清單，以判斷檔是否至少有一個擁有者的參與者。

如需設定和使用律師-用戶端許可權偵測模型的詳細資訊，請參閱 [Advanced eDiscovery 中的設定律師-用戶端許可權偵測](attorney-privilege-detection.md)。

> [!NOTE]
> 這是選擇性的步驟，您可以隨時執行。 未實施律師-用戶端許可權偵測模型不會妨礙您建立及使用高級 eDiscovery 案例。

## <a name="step-4-create-an-advanced-ediscovery-case"></a>步驟4：建立高級 eDiscovery 案例

下一步是建立案例，並開始使用高級 eDiscovery。 完成下列步驟以建立案例並新增成員。 建立案例的使用者會自動新增為成員。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。 組織管理角色群組的成員也可以建立高級 eDiscovery 案例。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [ **全部顯示** ]，然後按一下 [ **eDiscovery > Advanced** ]。

3. 在 [ **高級 eDiscovery** ] 頁面上，按一下 [ **案例** ] 索引標籤，然後按一下 [ **建立案例** ]。

4. 在 [ **新 eDiscovery 案例** 飛出] 頁面上，為案例輸入 (必要) 的名稱，然後輸入選用的案例編號及描述。 案例名稱在您的組織中必須是唯一的。

5. 按一下 [ **儲存** ] 以建立案例。

   會建立新案例，並顯示新案例中的 [ **設定** ] 索引標籤。 

6. 在 [ **設定** ] 索引標籤上的 [ **Access & 許可權** ] 方塊中，按一下 [ **選取** ]，然後按一下 [ **更新** ]。

7. 按一下 [更新]。

8. 在 [ **管理此案例** 飛入] 頁面上的 [ **管理成員** ] 底下，按一下 [ **新增** ] 以將成員新增至案例。

9. 在 [人員] 清單中，選取您要新增至案例之人員名稱旁邊的核取方塊。 如先前所述，請確定您加入案例的人員已獲指派適當的 eDiscovery 許可權。

10. 在您選取要新增為案例成員的人員之後，按一下 [ **新增** ]。

11. 在 [ **管理此案例** 飛入] 頁面中，按一下 [ **儲存** ] 儲存新的案例成員清單。

12. 按一下 [ **首頁** ] 索引標籤，移至案例首頁。

## <a name="explore-the-advanced-ediscovery-workflow"></a>探索高級 eDiscovery 工作流程

為了讓您開始使用高級 eDiscovery，以下是一個簡單的工作流程，可與 [一般 ediscovery 做法](overview-ediscovery-20.md#alignment-with-edrm)搭配使用。 在上述每個步驟中，我們也會強調您可以探索的一些擴充的高級 eDiscovery 功能。

![高級 eDiscovery 工作流程](../media/AeDWorkflow.png)

1. **[將保管人新增至案例](add-custodians-to-case.md)** 。 建立案例之後的第一個步驟是新增保管人。 *管理員* 是指具有可能與案例相關之檔或電子檔的系統管理控制權的人員。 以下是一些 (，也就是在您將保管人新增至案例時) 的情況：

   - 保管人的 Exchange 信箱、OneDrive 帳戶，以及保管人隸屬的任何 Microsoft 團隊或 Yammer 群組中的資料，都可以 "標示" 為案例中的 custodial 資料。
  
   - 保管人資料是由稱為「 *高級索引* ) 」的程式 (重新編制索引。 這可協助您在下一個步驟中優化搜尋。
  
   - 您可以對保管人資料進行保留。 這會在調查期間保留與案例相關的資料。
  
   - 您可以將其他資料來源與保管人 (產生關聯。例如，您可以將 SharePoint 網站或 Microsoft 365 群組與保管人) 產生關聯，這樣就可以重新編制索引、保留及搜尋此資料，就像是保管人的信箱或 OneDrive 帳戶中的資料一樣。

   - 您可以使用高級 eDiscovery 中的 [通訊工作流程](managing-custodian-communications.md) ，將合法保留通知傳送給保管人。

2. **[搜尋與案例相關之資料的 custodial 資料來源](collecting-data-for-ediscovery.md)** 。 在您將保管人新增至案例後，請使用內建的搜尋工具，針對可能與案例相關的資料，搜尋保管人資料位置。 您可以使用關鍵字、屬性和條件來 [建立搜尋查詢](building-search-queries.md) ，以利用最可能與案例相關的資料傳回搜尋結果。 您也可以：

   - 查看可協助您縮小搜尋查詢以縮小結果的 [搜尋統計資料](search-statistics.md) 。

   - 預覽搜尋結果，以快速確認是否找到相關資料。

   - 修改查詢，然後重新執行搜尋。

3. **[將資料新增至審閱集](add-data-to-review-set.md)** 。 當您設定並確認搜尋傳回所需的資料之後，下一步是將搜尋結果新增至審閱集。 當您將資料新增至審閱集時，專案會從其原始位置複製到安全的 Azure 存放位置。 當審閱及分析審閱集中的專案時，會再次重新編制索引資料，以優化完整和快速的搜尋。 此外，您也可以 [將非 Office 365 資料新增至審閱集](load-non-office-365-data-into-a-review-set.md)。

   此外還有一種特殊的審閱集，您可以將資料新增至（稱為「 *交談複查集* 」）。 這兩種審閱集可提供交談重新構建功能，以重新構建、審閱及匯出像是 Microsoft 小組中的對話交談。 如需詳細資訊，請參閱 [在高級 eDiscovery 中查看交談](conversation-review-sets.md)。

4. **檢查及分析審閱集中的資料** 。 現在，資料是在審校集中，您可以使用各種各樣的工具和功能來查看及分析案例資料，將資料集減至最適合您所調查之案例的目標。 以下是您可以在此程式中使用之部分工具和功能的清單。

   - [View documents](view-documents-in-review-set.md)。 這包括針對審閱集中的每一份檔，查看其中繼資料，並以原生版本或文字版本查看該檔。

   - [建立查詢和篩選](review-set-search.md)。 您可以使用各種搜尋準則來建立搜尋查詢 (包括搜尋所有檔案 [中繼資料屬性](document-metadata-fields-in-advanced-ediscovery.md) 的功能) 以進一步精煉及挑選案例資料至與案例最為相關的專案。 您也可以使用 [審閱集合篩選]，將其他條件快速套用至搜尋查詢的結果，以進一步精煉這些結果。 

   - [建立及使用標記](tagging-documents.md)。 您可以將標記套用至審閱集合中的檔，以識別哪些回應 (或沒有回應案例) ，然後在建立搜尋查詢以包含或排除已標記的檔時，使用這些標記。 您也可以進行標記，以決定要匯出的檔。

   - [批註和密文檔](view-documents-in-review-set.md#annotate-view)。 您可以使用審閱中的批註工具，註釋檔，並在檔中以工作產品標記密文內容。 我們會在評審時產生 PDF 版本的批註或 redacted 檔，以降低匯出檔的 unredacted 原生版本的風險。

   - [分析案例資料](analyzing-data-in-review-set.md)。 高級 eDiscovery 的分析功能非常強大。 在複查集中的資料執行分析之後，我們會執行分析，例如接近重複偵測、電子郵件執行緒和主題，可協助減少您必須查看的檔數量。 我們也會產生分析報告，以匯總執行分析的結果。 如先前所述，執行分析也會執行 [律師-用戶端許可權偵測模型](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。

5. **匯出及下載案例資料** 。 收集、複查及分析案例資料的最後一個步驟是，將其匯出至「高級 eDiscovery」以供外部檢查，或由調查小組以外的人員進行審閱。 匯出資料的過程分為兩個步驟。 第一步是將資料 [匯出](export-documents-from-review-set.md) 至審閱集，並將它複製到不同的 Azure 存放位置， (由 Microsoft 提供，或是由組織) 所管理。 然後，您使用 Azure Storage Explorer 將資料 [下載](download-export-jobs.md) 到本機電腦。 除了匯出的資料檔案之外，匯出套件也包含匯出報告、摘要報告及錯誤報表。
