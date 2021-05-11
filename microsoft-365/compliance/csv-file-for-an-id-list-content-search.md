---
title: 準備用於識別碼清單內容搜尋的 CSV 檔案
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: 使用來自現有內容搜尋的 CSV 檔案，以建立會傳回特定電子郵件專案的 ID 清單搜尋。
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311533"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>準備用於識別碼清單內容搜尋的 CSV 檔案

您可以使用 Exchange IDs 清單來搜尋特定的信箱電子郵件訊息和其他信箱專案。 若要建立識別碼清單搜尋，您可以提交逗點分隔值 (CSV) 檔案，以識別要搜尋的特定信箱項目。 針對此 CSV 檔案，您可以使用當您匯出內容搜尋結果時所包含的 **Results.csv** 檔或未 **編制索引的 Items.csv** 檔案，或從現有的內容搜尋中匯出內容搜尋報告時所包含的檔。 然後，編輯這些檔案中的其中一個，以指出要搜尋的特定專案、建立新的識別碼清單搜尋，然後提交 CSV 檔案。

**為何要建立識別碼清單搜尋？** 如果您無法根據 **Results.csv** 或非 **索引的 Items.csv** 檔案中的中繼資料來判斷某個專案是否回應 eDiscovery 要求，您可以使用識別碼清單搜尋來尋找、預覽及匯出該專案，以判斷其是否回應您正在調查的案例。 識別碼清單搜尋通常是用來搜尋並傳回一組特定的未編制索引的專案。

以下是建立識別碼清單搜尋之程式的快速概覽。

1. 在 Microsoft 365 規範中心建立並執行新的搜尋。

2. 匯出內容搜尋結果或內容搜尋報告。 如需詳細資訊，請參閱：

    - [匯出內容搜尋結果](export-search-results.md)

    - [匯出內容搜尋報告](export-a-content-search-report.md)

3. 編輯 **Results.csv** 檔或未 **編制索引的 Items.csv** 檔案，並識別要包含在識別碼清單搜尋中的特定信箱專案。 請參閱針對識別碼清單搜尋準備 CSV 檔案的 [指示](#prepare-the-csv-file-for-an-id-list-search) 。

4. 建立新的識別碼清單搜尋 (請參閱 [指示](#create-an-id-list-search)) 並提交您準備的 CSV 檔案。 所建立的搜尋查詢只會搜尋 CSV 檔案中選取的專案。

> [!NOTE]
> 僅支援信箱專案的 ID 清單搜尋。 您無法在識別碼清單搜尋中搜尋 SharePoint 和 OneDrive 檔。

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>準備用於識別碼清單搜尋的 CSV 檔案

匯出搜尋結果或報表進行搜尋之後，請執行下列步驟，以準備用於識別碼清單搜尋的 CSV 檔案。 此 CSV 檔案識別識別碼清單搜尋中的每個專案。

您可以從包含 SharePoint 網站和 OneDrive 帳戶的搜尋使用 CSV 檔案，但您只能選取識別碼清單搜尋的信箱專案。 如果您選取 SharePoint 或 OneDrive 中的檔，當您建立識別碼清單搜尋時，CSV 檔案會失敗驗證。

1. 在 Excel 中開啟 **Results.csv** 或未 **編制索引的 Items.csv** 檔案。

2. 在 [ **選取** ] 欄的儲存格中輸入 **[是]** ，對應至您要搜尋的專案。 針對您要搜尋的每個專案重複此步驟。

    > [!IMPORTANT]
    > 當您在 Excel 中開啟 CSV 檔案時，檔 **識別碼** 欄的資料格式可能已變更為 **[一般**]。 這會導致顯示以科學記數法表示的專案檔案識別碼。 例如，[481037338205] 的檔識別碼會顯示為 "4.81037 E + 11"。 如果發生這種情況，您必須執行後續步驟，將 [ **檔識別碼** ] 欄的資料格式變更為 [ **數位** ]，以還原檔識別碼的正確格式。 否則，使用 CSV 檔案的 ID 清單搜尋會失敗。

3. 以滑鼠右鍵按一下 [整個 **檔識別碼** ] 欄，然後選取 [ **設定儲存格格式**]。

4. 在 [ **類別** ] 方塊中，按一下 [ **數位**]。

5. 將小數位位數變更為 **0**，然後按一下 **[確定]** 以儲存變更。 請注意，[檔識別碼] 欄中的值會變更為 [數位]。

    以下是可提交識別碼清單內容搜尋之 CSV 檔案的範例。

    ![目標內容搜尋的 CSV 檔案範例](../media/SearchIDListCSVFile.png)

6. 儲存 CSV 檔案，或使用另 **存** 新檔案名儲存檔案。 在這兩種情況下，請務必以 CSV 格式儲存檔案。

## <a name="create-an-id-list-search"></a>建立識別碼清單搜尋

下一步是建立新的識別碼清單搜尋，並提交您在上一個步驟中準備的 CSV 檔案。

> [!IMPORTANT]
> 在匯出搜尋結果或報告之後，您應建立至少2天的 ID 清單搜尋。 如果搜尋結果或報告的輸出超過2天，您應該重新匯出搜尋結果或報表，以產生更新的 CSV 檔案。 然後您可以準備其中一個更新的 CSV 檔案，並使用它來建立識別碼清單搜尋。

1. 移至 <https://compliance.microsoft.com> 並登入。

2. 在 Microsoft 365 合規性中心的左瀏覽窗格中，按一下 **[顯示全部]**，然後按一下 **[內容搜尋]**。

3. 在 [ **內容搜尋** ] 頁面上，按一下 [ **依識別碼搜尋] 清單**。

4. 在 [ **依識別碼搜尋] 清單** 快顯視窗中，命名搜尋 (並選擇性地描述它) 然後按一下 **[流覽]** ，然後選取您在上一個步驟中準備好的 CSV 檔案。

    Microsoft 365 會嘗試驗證 CSV 檔案。 如果驗證失敗，則會顯示錯誤訊息，以協助您疑難排解驗證錯誤。 CSV 檔案必須成功驗證，才能建立識別碼清單搜尋。

5. 在成功驗證 CSV 檔案之後，按一下 [ **搜尋** ] 以建立識別碼清單搜尋。

    以下是識別碼清單搜尋中的飛出頁面範例，顯示產生的查詢及估計的搜尋結果數目。

    ![識別碼清單搜尋的搜尋查詢](../media/SearchIDListFlyout.png)

    在識別碼搜尋的統計資料中顯示的預估專案數目，應符合您在 CSV 檔案中選取的專案數。

6. 預覽或匯出識別碼清單搜尋傳回的專案。

## <a name="more-information"></a>其他資訊

如果您在建立 ID 清單搜尋之後移動信箱，則搜尋查詢不會傳回指定的專案。 這是因為在移動信箱時，信箱專案的 **DocumentId** 屬性會變更。 在您建立識別碼清單搜尋之後移動信箱的少數情況下，您應該建立新的內容搜尋 (或更新現有搜尋) 的搜尋結果，然後匯出搜尋結果或報告，以產生可用來建立新的 ID 清單搜尋的更新 CSV 檔案。
