---
title: 在 Microsoft 365 中建立及管理高級 eDiscovery 案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-ediscovery
- m365initiative-compliance
- m365initiative-scenario
search.appverid:
- MOE150
- MET150
description: 本文說明如何建立及管理高級 eDiscovery 案例。 第一步是建立案例，並開始使用 Advanced eDiscovery 的功能和功能。
ms.openlocfilehash: 80cfe31a86060cb3603a101b314273cc67750bd8
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727540"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>建立及管理高級 eDiscovery 案例

在將管理案例的組織中設定高級 eDiscovery 並 [指派對 ediscovery 管理員的許可權](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) 之後，下一步是建立並管理案例。

本文也提供使用案例來管理法律調查之高級 eDiscovery 工作流程的高層次概述。

## <a name="create-a-case"></a>建立案例

完成下列步驟以建立案例並新增成員。 建立案例的使用者會自動新增為成員。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並使用已獲指派 eDiscovery 許可權之使用者帳戶的認證登入。 組織管理角色群組的成員也可以建立高級 eDiscovery 案例。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [ **全部顯示**]，然後按一下 [ **eDiscovery > Advanced**]。

3. 在 [ **高級 eDiscovery** ] 頁面上，按一下 [ **案例** ] 索引標籤，然後按一下 [ **建立案例**]。

4. 在 [ **新 eDiscovery 案例** 飛出] 頁面上，為案例輸入 (必要) 的名稱，然後輸入選用的案例編號及描述。 案例名稱在您的組織中必須是唯一的。

5. 按一下 [ **儲存** ] 以建立案例。

   會建立新案例，並顯示新案例中的 [ **設定** ] 索引標籤。

6. 在 [**設定**] 索引標籤上的 [ **Access & 許可權**] 方塊中，按一下 [**選取**]，然後按一下 [**更新**]。

7. 按一下 [更新]。

8. 在 [ **管理此案例** 飛入] 頁面上的 [ **管理成員**] 底下，按一下 [ **新增** ] 以將成員新增至案例。

9. 在 [人員] 清單中，選取您要新增至案例之人員名稱旁邊的核取方塊。 如先前所述，請確定您加入案例的人員已獲指派適當的 eDiscovery 許可權。

10. 在您選取要新增為案例成員的人員之後，按一下 [ **新增**]。

11. 在 [ **管理此案例** 飛入] 頁面中，按一下 [ **儲存** ] 儲存新的案例成員清單。

12. 按一下 [ **首頁** ] 索引標籤，移至案例首頁。

## <a name="manage-the-workflow"></a>管理工作流程

為了讓您開始使用高級 eDiscovery，這裡是一個與 [一般 ediscovery 作法](advanced-ediscovery-edrm.md)對齊的基本工作流程。 在上述每個步驟中，我們也會強調您可以探索的一些擴充的高級 eDiscovery 功能。

![高級 eDiscovery 工作流程](../media/AeDWorkflow.png)

1. **[將保管人](add-custodians-to-case.md) 和 [非 custodial 資料來源](non-custodial-data-sources.md) 新增至案例**。 建立案例之後的第一個步驟是新增保管人。 *管理員* 是指具有可能與案例相關之檔或電子檔的系統管理控制權的人員。 此外，您也可以新增與特定使用者沒有關聯但可能與案例相關的資料來源。

   以下是一些 (，也就是在您將保管人新增至案例時) 的情況：

   - 保管人的 Exchange 信箱、OneDrive 帳戶，以及保管人隸屬的任何 Microsoft 團隊或 Yammer 群組中的資料，都可以 "標示" 為案例中的 custodial 資料。
  
   - 保管人資料是由稱為「 *高級索引*) 」的程式 (重新編制索引。 這可協助您在下一個步驟中優化搜尋。
  
   - 您可以對保管人資料進行保留。 這會在調查期間保留與案例相關的資料。
  
   - 您可以將其他資料來源與保管人 (產生關聯。例如，您可以將 SharePoint 網站或 Microsoft 365 群組與保管人) 產生關聯，這樣就可以重新編制索引、保留及搜尋此資料，就像是保管人的信箱或 OneDrive 帳戶中的資料一樣。

   - 您可以使用高級 eDiscovery 中的 [通訊工作流程](managing-custodian-communications.md) ，將合法保留通知傳送給保管人。

2. **[搜尋與案例相關之資料的資料來源](collecting-data-for-ediscovery.md)**。 在您將保管人和非 custodial 資料來源新增至案例後，請使用內建的搜尋工具，針對可能與案例相關的資料，搜尋這些資料來源。 您可以使用關鍵字、屬性和條件來 [建立搜尋查詢](building-search-queries.md) ，以利用最可能與案例相關的資料傳回搜尋結果。 您也可以：

   - 查看可協助您縮小搜尋查詢以縮小結果的 [搜尋統計資料](search-statistics-in-advanced-ediscovery.md) 。

   - 預覽搜尋結果，以快速確認是否找到相關資料。

   - 修改查詢，然後重新執行搜尋。

3. **[將資料新增至審閱集](add-data-to-review-set.md)**。 當您設定並確認搜尋傳回所需的資料之後，下一步是將搜尋結果新增至審閱集。 當您將資料新增至審閱集時，專案會從其原始位置複製到安全的 Azure 存放位置。 當審閱及分析審閱集中的專案時，會再次重新編制索引資料，以優化完整和快速的搜尋。 此外，您也可以 [將非 Office 365 資料新增至審閱集](load-non-office-365-data-into-a-review-set.md)。

   此外還有一種特殊的審閱集，您可以將資料新增至（稱為「 *交談複查集*」）。 這兩種審閱集可提供交談重新構建功能，以重新構建、審閱及匯出像是 Microsoft 小組中的對話交談。 如需詳細資訊，請參閱 [在高級 eDiscovery 中查看交談](conversation-review-sets.md)。

4. **檢查及分析審閱集中的資料**。 現在，資料是在審校集中，您可以使用各種各樣的工具和功能來查看及分析案例資料，將資料集減至最適合您所調查之案例的目標。 以下是您可以在此程式中使用之部分工具和功能的清單。

   - [View documents](view-documents-in-review-set.md)。 這包括針對審閱集中的每一份檔，查看其中繼資料，並以原生版本或文字版本查看該檔。

   - [建立查詢和篩選](review-set-search.md)。 您可以使用各種搜尋準則來建立搜尋查詢 (包括可搜尋所有檔案 [中繼資料屬性](document-metadata-fields-in-advanced-ediscovery.md) 的功能) 以進一步精煉及挑選案例資料至與案例最為相關的專案。 您也可以使用 [審閱集合篩選]，將其他條件快速套用至搜尋查詢的結果，以進一步精煉這些結果。 

   - [建立及使用標記](tagging-documents.md)。 您可以將標記套用至審閱集合中的檔，以識別哪些回應 (或沒有回應案例) ，然後在建立搜尋查詢以包含或排除已標記的檔時，使用這些標記。 您也可以進行標記，以決定要匯出的檔。

   - [批註和密文檔](view-documents-in-review-set.md#annotate-view)。 您可以使用審閱中的批註工具，註釋檔，並在檔中以工作產品標記密文內容。 我們會在評審時產生 PDF 版本的批註或 redacted 檔，以降低匯出檔的 unredacted 原生版本的風險。

   - [分析案例資料](analyzing-data-in-review-set.md)。 高級 eDiscovery 的分析功能非常強大。 在複查集中的資料執行分析之後，我們會執行分析，例如接近重複偵測、電子郵件執行緒和主題，可協助減少您必須查看的檔數量。 我們也會產生分析報告，以匯總執行分析的結果。 如先前所述，執行分析也會執行 [律師-用戶端許可權偵測模型](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。

5. **匯出及下載案例資料**。 收集、複查及分析案例資料的最後一個步驟是，將其匯出至「高級 eDiscovery」以供外部檢查，或由調查小組以外的人員進行審閱。 匯出資料的過程分為兩個步驟。 第一步是將資料 [匯出](export-documents-from-review-set.md) 至審閱集，並將它複製到不同的 Azure 存放位置， (由 Microsoft 提供，或是由組織) 所管理。 然後，您使用 Azure Storage Explorer 將資料 [下載](download-export-jobs.md) 到本機電腦。 除了匯出的資料檔案之外，匯出套件也包含匯出報告、摘要報告及錯誤報表。
