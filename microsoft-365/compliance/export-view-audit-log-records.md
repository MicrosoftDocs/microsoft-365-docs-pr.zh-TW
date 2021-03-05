---
title: 匯出、 設定及檢視稽核記錄檔的記錄
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: 在本文中，您將會瞭解如何匯出、設定及查看 Microsoft 365 的審計記錄檔記錄。
ms.openlocfilehash: a7f731bb30ffdddfe7898ee4051060b8e22c093e
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454664"
---
# <a name="export-configure-and-view-audit-log-records"></a>匯出、 設定及檢視稽核記錄檔的記錄

在您搜尋審核記錄並將搜尋結果下載至 CSV 檔案之後，該檔案會包含一個名為 **AuditData** 的欄，其中包含每個事件的詳細資訊。 此欄中的資料已格式化為 JSON 物件，包含多個屬性設定為 *property：值* 組合，以逗號分隔。 您可以在 Excel 的 Power Query 編輯器中使用 JSON 轉換功能，將 **AuditData** 欄中 JSON 物件的每個屬性分割成多個欄，使每個屬性都有自己的資料行。 這可讓您在一個或多個屬性上進行排序和篩選，這可協助您快速找到所要尋找的特定審核資料。

## <a name="step-1-export-audit-log-search-results"></a>步驟1：匯出審計記錄搜尋結果

第一步是搜尋審核記錄檔，然後以逗號分隔值 (CSV) 檔案將結果匯出至本機電腦。
  
1. 如有需要，請執行 [審計記錄搜尋](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) 並修正搜尋準則，直到您有需要的結果為止。

2. 按一下 [ **匯出結果** ]，然後選取 [ **下載所有結果**]。 

   ![按一下 [下載所有結果]](../media/ExportAuditSearchResults.png)

   此選項可從您在步驟1中執行的審計記錄搜尋中匯出所有的審計記錄，並將原始資料從審核記錄檔下載到 CSV 檔案。 

   會在視窗底部顯示一則訊息，提示您開啟或儲存 CSV 檔案。 

3. 按一下 [ **儲存 > 另存** 新檔]，然後將 CSV 檔案儲存至本機電腦。 下載許多搜尋結果需要一段時間。 這通常是搜尋所有活動或廣泛的日期範圍時的情況。 當 CSV 檔案下載完畢後，就會顯示視窗底部的訊息。

   ![當 CSV 檔案下載完成時所顯示的訊息](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > 您可以從單一稽核記錄搜尋下載最多 50,000 個項目至 CSV 檔案。 如果已下載 50,000 個項目至 CSV 檔案，您可能可以假設有超過 50,000 個符合搜尋準則的事件。 若要匯出超過此限制，請嘗試使用日期範圍來減少審計記錄檔的數量。 您可能需要使用較小的日期範圍執行多次搜尋，以匯出 50,000 個以上的項目。

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>步驟2：使用 Power Query 編輯器格式化匯出的審計記錄檔

下一步是在 Excel 的 Power Query 編輯器中使用 JSON 轉換功能，將 **AuditData** 欄中 JSON 物件中的每個屬性分割成自己的資料行。 然後，根據特定屬性的值，篩選欄以查看記錄。 這可協助您快速找到您要尋找的特定審核資料。

1. 在 Excel 中開啟空白活頁簿，以供 Office 365、Excel 2019 或 Excel 2016 使用。

2. 在 [ **資料** ] 索引標籤的 [ **取得 & 轉換資料** ] 功能區群組中，按一下 [ **從文字/CSV**]。

    ![在 [資料] 索引標籤上，按一下 [從文字/CSV]](../media/JSONTransformOpenCSVFile.png)

3. 開啟您在步驟1中下載的 CSV 檔案。

4. 在顯示的視窗中，按一下 [ **轉換資料**]。

   ![按一下 [轉換資料]](../media/JSONOpenPowerQuery.png)

   CSV 檔案會在 **查詢編輯器** 中開啟。 有四個欄： **CreationDate**、 **UserIds**、 **作業** 及 **AuditData**。 **AuditData** 欄是包含多個屬性的 JSON 物件。 下一步是為 JSON 物件中的每個屬性建立欄。

5. 以滑鼠右鍵按一下 [ **AuditData** ] 欄中的標題，按一下 [ **轉換**]，然後按一下 [ **JSON**]。 

   ![以滑鼠右鍵按一下 [AuditData] 欄，按一下 [轉換]，然後選取 [JSON]。](../media/JSONTransform.png)

6. 在 [ **AuditData** ] 欄的右上角，按一下展開圖示。

   ![在 [AuditData] 欄中，按一下展開圖示](../media/JSONTransformExpandIcon.png)

   隨即會顯示 [ **AuditData** ] 欄中 JSON 物件的屬性部分清單。

7. 按一下 [ **載入更多** ]，以在 [ **AuditData** ] 欄中顯示 JSON 物件中的所有屬性。

   ![按一下 [載入更多] 以顯示 JSON 物件中的所有屬性](../media/JSONTransformLoadJSONProperties.png)

   您可以取消選取不想要包含的任何屬性旁的核取方塊。 消除對調查沒有用的資料行，是減少審核記錄中所顯示之資料量的好方法。 

   > [!NOTE]
   > 上一個螢幕擷取畫面所顯示的 JSON 屬性 (按一下 [ **載入更多**) 時所依據的屬性，取決於 CSV 檔案中的第一個1000資料列中找到的 [ **AuditData** ] 資料行。 如果在第一個1000列之後的記錄中有不同的 JSON 屬性，當 **AuditData** 欄位分割成多個欄時，這些屬性 (和對應的資料行) 不會包含在此欄位中。 為了協助避免這種情況，請考慮重新執行審核記錄搜尋並縮小搜尋準則，以減少傳回的記錄。 另一個解決方法是在 [ **作業** ] 欄中篩選項目，以在您執行上述步驟5之前，先在) 中 (的列數，再轉換 **AuditData** ] 欄中的 JSON 物件。

   > [!TIP]
   > 若要在清單中查看屬性，例如 AuditData AffectedItems，按一下您想要從中拉出屬性的欄右上角的 **展開** 圖示，然後選取 [ **展開至新** 列]。  從這裡將會有一筆記錄，您可以按一下欄右上角的 **展開** 圖示，查看屬性，然後選取要查看或抽出的屬性。

8. 請執行下列其中一項動作，以格式化所選取的每個 JSON 屬性所新增的欄標題。

    - 取消選取 [ **使用原始欄名稱做為前置** 詞] 核取方塊，以使用 JSON 屬性的名稱做為欄名稱;例如， **RecordType** 或 **SourceFileName**。

    - 選取 [ **使用原始欄名稱做為前置** 詞] 核取方塊，以將 AuditData 前置詞加入欄名稱中;例如， **AuditData。 RecordType** 或 **AuditData SourceFileName**。

9. 按一下 [確定]。

    **AuditData** 欄會分割成多個欄。 每個新欄會對應至 AuditData JSON 物件中的屬性。 資料行中的每一列都包含屬性的值。 如果此屬性不包含值，則會顯示 *null* 值。 在 Excel 中，具有 null 值的儲存格是空白的。
  
10. 在 [ **常用** ] 索引標籤上，按一下 [ **關閉 & 載入** ]，關閉 Power Query 編輯器，並在 Excel 活頁簿中開啟轉換後的 CSV 檔案。

## <a name="use-powershell-to-search-and-export-audit-log-records"></a>使用 PowerShell 來搜尋和匯出審計記錄記錄

您可以使用 Exchange Online PowerShell 中的 [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) Cmdlet，將審核記錄搜尋的結果匯出至 CSV 檔案，而不是在安全性 & 合規性中心使用「審核記錄搜尋」工具。 接著，您可以遵循步驟2所述的相同程式，以使用 Power Query 編輯器來格式化審核記錄檔。 使用 PowerShell Cmdlet 的其中一個優點是，您可以使用 *RecordType* 參數，從特定服務搜尋事件。 以下是一些使用 PowerShell 將審核記錄匯出至 CSV 檔案的範例，因此您可以使用 Power Query 編輯器，依步驟2所述，在 **AuditData** 欄中轉換 JSON 物件。

在此範例中，執行下列命令以傳回與 SharePoint 共用作業相關的所有記錄。

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

搜尋結果會匯出至名為 *PowerShellAuditlog* 的 CSV 檔案，該檔案包含四個欄： CreationDate、UserIds、RecordType AuditData) 。

您也可以使用 record 類型的 name 或 enum 值做為 *RecordType* 參數的值。 如需記錄類型名稱及其對應列舉值的清單，請參閱 [Office 365 管理活動 API 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)中的 *AuditLogRecordType* 表格。

*RecordType* 參數只能包含單一值。 若要搜尋其他記錄類型的審計記錄，您必須再次執行這兩個先前的命令，以指定不同的記錄類型，並將這些結果附加至原始 CSV 檔案。 例如，您可以執行下列兩個命令，將相同日期範圍的 SharePoint 檔案活動新增至 PowerShellAuditlog.csv 檔案。

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>匯出及查看審核記錄的秘訣

以下是在您使用 JSON 轉換功能將 **AuditData** 欄分割成多個欄之前和之後，匯出及查看審核記錄的一些秘訣和範例。

- 篩選 **RecordType** 欄，只顯示特定服務或功能區域中的記錄。 例如，若要顯示與 SharePoint 共用相關的事件，您可以選取 [ **14** ] (SharePoint 共用活動) 所觸發之記錄的列舉值。 如需與 **RecordType** ] 欄中所顯示之列舉值相對應的服務清單，請參閱 [audit Log 中的詳細](detailed-properties-in-the-office-365-audit-log.md)內容。

- 篩選 [ **作業** ] 欄，以顯示特定活動的記錄。 如需與安全性 & 規範中心的「審核記錄」搜尋工具中的可搜尋活動相對應的大部分作業清單，請參閱 [安全性 & 規範中心的「搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md#audited-activities)」一節中的「審核的活動」一節。
