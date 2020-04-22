---
title: eDiscovery 解決方案系列資料外泄案例-搜尋和清除
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: 使用 eDiscovery 和搜尋工具來管理和回應組織中的資料外泄事件。
ms.openlocfilehash: fd230d3e54ca61046a28f60d81d497a413bfa4f7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630590"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>eDiscovery 解決方案系列：資料外泄案例-搜尋和清除

 **何謂資料外泄以及您為何要注意？** 資料外泄是當機密檔發佈至不受信任的環境時。 偵測到資料外泄事件時，請務必快速評估外泄的大小和位置，檢查其周圍的使用者活動，然後從系統中永久清除溢出的資料。 
  
## <a name="data-spillage-scenario"></a>資料外泄案例

您是 Contoso 的潛在客戶資訊安全性監察官。 您會收到一種資料外泄狀況，其中員工在不知情的情況下，透過電子郵件與多位人員分享高度機密檔。 您想要快速評估在內部和外部接收此檔的人員。 識別後，您想要與其他調查人員分享案例調查，以進行審核，然後永久移除 Office 365 中的資料。 調查完成後，您想要產生一個報告，其中包含永久移除的證據，以及其他案例的詳細資料，以備日後參考。
  
### <a name="scope-of-this-article"></a>本文的範圍

這份檔提供如何永久移除 Microsoft 365 中的郵件，使其無法存取或可復原的指令清單。 若要刪除郵件並使其可復原，直到刪除的專案保留期間到期為止，請參閱[搜尋並刪除組織中的電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)。
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>管理資料外泄事件的工作流程

以下是管理資料外泄事件的方法：

![用於管理資料外泄事件的8步驟工作流程](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[選步驟1：管理可以存取案例及設定規范界限的人員](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[步驟2：建立電子檔探索案例](#step-2-create-an-ediscovery-case)<br/>
[步驟3：搜尋溢出的資料](#step-3-search-for-the-spilled-data)<br/>
[步驟4：複查和驗證案例發現](#step-4-review-and-validate-case-findings)<br/>
[步驟5：使用郵件追蹤記錄檔檢查溢出的資料共用方式](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[步驟6：準備信箱](#step-6-prepare-the-mailboxes)<br/>
[步驟7：永久刪除溢出的資料](#step-7-permanently-delete-the-spilled-data)<br/>
[步驟8：確認、提供刪除的證明及審核](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>開始之前的須知事項

- 當信箱處於保留狀態時，已刪除的郵件會保留在 [可復原的專案] 資料夾中，直到保留期間到期或解除保留為止。 [步驟 6](#step-6-prepare-the-mailboxes)說明如何從信箱移除保留。 移除保留之前，請與您的記錄管理或法律部門核實。 您的組織可能具有定義信箱保留或資料外泄事件是否優先的原則。 
    
- 若要控制資料外泄調查人員可以搜尋及管理誰可以存取此案例的使用者信箱，您可以設定規范界限，以及建立自訂角色群組，如[步驟 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)所述。 若要這麼做，您必須是「組織管理」角色群組的成員，或被指派角色管理角色。 如果您或您組織中的系統管理員已設定合規性界限，您可以略過步驟1。
    
- 若要建立案例，您必須是 eDiscovery 管理員角色群組的成員，或是已指派案例管理角色之自訂角色群組的成員。 如果您不是成員，請要求 Microsoft 365 系統管理員[將您新增至 eDiscovery 管理員角色群組](assign-ediscovery-permissions.md)。
    
- 若要建立和執行內容搜尋，您必須是「eDiscovery 管理員」角色群組的成員，或者獲指派「符合性搜尋」管理角色。 若要刪除郵件，您必須是「組織管理」角色群組的成員，或者獲指派「搜尋及清除」管理角色。 如需新增使用者至角色群組的詳細資訊，請參閱[在安全性與合規性中心中指派電子文件探索權限](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)。
    
- 若要搜尋步驟8中的「審核記錄電子檔探索」活動，必須為您的組織開啟審計。 您可以搜尋過去90天內執行的活動。 若要深入瞭解如何啟用和使用審核，請參閱步驟8中的「[審核資料外泄調查](#auditing-the-data-spillage-investigation-process)程式」一節。 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>選步驟1：管理可以存取案例及設定規范界限的人員

根據您的組織實踐，您必須控制誰可以存取 eDiscovery 案例，以調查資料外泄事件及設定規范界限。 最簡單的方法是將調查人員新增為安全性 & 合規性中心內現有角色群組的成員，然後將角色群組新增為 eDiscovery 案例的成員。 如需內建 eDiscovery 角色群組的相關資訊，以及如何新增成員至 eDiscovery 案例，請參閱[指派 ediscovery 許可權](assign-ediscovery-permissions.md)。
  
您也可以建立符合組織需求的新角色群組。 例如，您可能想要組織中的資料外泄調查人員群組，以存取及共同作業所有的資料外泄案例。 若要執行此動作，您可以建立「資料外泄調查員」角色群組、指派適當的角色（匯出、RMS 解密、審閱、預覽、符合性搜尋及案例管理）、將資料外泄調查人員新增至角色群組，然後將角色群組新增為數據外泄 eDiscovery 案例的成員。 如需如何執行此動作的詳細指示，請參閱[設定 Office 365 中 eDiscovery 調查的規範界限](tagging-and-assessment-in-advanced-ediscovery.md)。 
  
## <a name="step-2-create-an-ediscovery-case"></a>步驟2：建立電子檔探索案例

EDiscovery 案例提供一種有效的方法來管理資料外泄調查。 您可以將成員新增至您在步驟1中建立的角色群組，將角色群組新增為新電子檔探索案例的成員，執行重複搜尋以找出溢出的資料、將報告匯出至共用、追蹤案例的狀態，然後視需要傳回案例的詳細資料。 請考慮為數據外泄事件使用的 eDiscovery 案例建立命名慣例，並提供您在案例名稱和描述中盡可能多的資訊，以便在未來必要時找到及參考。
  
若要建立新案例，您可以使用安全性與合規性中心的 eDiscovery。 請參閱[eDiscovery 案例](ediscovery-cases.md#step-2-create-a-new-case)中的「建立新案例」。
  
## <a name="step-3-search-for-the-spilled-data"></a>步驟3：搜尋溢出的資料

現在，您已經建立了案例和受管理的存取，您可以使用此案例以重複搜尋來尋找溢出的資料，並找出包含溢出資料的信箱。 您將會使用相同的搜尋查詢，您可以在[步驟 7](#step-7-permanently-delete-the-spilled-data)中用來尋找電子郵件訊息以刪除這些相同郵件。
  
若要建立與 eDiscovery 案例相關聯的內容搜尋，請參閱[eDiscovery 案例](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)中的「建立及執行與案例相關聯的內容搜尋」。
  
 **重要：** 您在搜尋查詢中使用的關鍵字可能會包含您要搜尋的實際濺入資料。 例如，如果您搜尋包含社交安全性號碼的檔，並使用它作為搜尋關鍵字，則必須在以後刪除該查詢，以避免進一步外泄。 請參閱刪除步驟8中[的搜尋查詢](#deleting-the-search-query)。 
  
## <a name="step-4-review-and-validate-case-findings"></a>步驟4：複查和驗證案例發現

在您建立內容搜尋之後，您必須複查並驗證搜尋結果，並確認其是否只包含必須刪除的電子郵件。 在內容搜尋中，您可以預覽1000電子郵件的隨機抽樣，而不匯出搜尋結果，以避免進一步的資料外泄。 您可以閱讀[內容搜尋限制](limits-for-content-search.md)的更多相關預覽限制。
  
如果您有超過1000個信箱或每個信箱的電子郵件超過100個，您可以使用其他關鍵字或條件，例如日期範圍或寄件者/收件者，逐一查看每個搜尋的結果，將初始搜尋分割成多個搜尋。 請務必記下在[步驟 7](#step-7-permanently-delete-the-spilled-data)刪除郵件時所要使用的所有搜尋查詢。

如果系統管理員或使用者已獲指派 Office 365 E5 授權，您可以使用「高級 eDiscovery」一次檢查最多10000個搜尋結果。 若要檢查的電子郵件超過10000個，您可以依日期範圍分割搜尋查詢，並個別查看每個結果，因為搜尋結果會依日期排序。 在 [Advanced eDiscovery] 中，您可以使用預覽面板中的 [**標籤標為**] 功能來標記搜尋結果，並依據您標示的標記篩選搜尋結果。 當您與次要檢閱者共同作業時，這會很有説明。 透過使用高級 eDiscovery 中的其他分析工具（例如光學字元辨識、電子郵件執行緒及預測編碼），您可以快速處理及檢查數千封郵件，並標記它們以供進一步複查。 請參閱[Quick setup For Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md)。

當您發現包含溢出資料的電子郵件時，請檢查郵件的收件者，以判斷其是否為外部共用。 若要進一步追蹤郵件，您可以收集寄件者資訊和日期範圍，讓您可以使用[步驟 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)中所述的郵件追蹤記錄檔。

Afer 您已驗證搜尋結果，您可能想要與其他人共用您的結果，以進行次要審閱。 您在步驟1中指派案例的人員可以在 eDiscovery 和高級 eDiscovery 和核准案例探索中查看案例內容。 您也可以在不匯出實際內容的情況下產生報告。 您也可以使用這個相同的報告做為刪除的證據，如[步驟 8](#step-8-verify-provide-a-proof-of-deletion-and-audit)所述。
  
 **產生統計報告：**
  
1. 移至 eDiscovery 案例中的 [**搜尋**] 頁面，然後按一下您要產生報告的搜尋。 
    
2. 在飛入頁面上，按一下 [**更多 > 匯出報告**]。
 
      [匯出報告] 頁面隨即顯示。

    ![選取 [搜尋]，然後按一下彈出頁面上的 [更多 > 匯出報告]](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. 選取 [**所有專案] （包括具有未辨識格式的專案）、[已加密] 或 [未針對其他原因建立索引**]，然後按一下 [**產生報告**]。

4. 在 eDiscovery 案例中，按一下 [**匯出**] 以顯示匯出工作清單。 您可能需要按一下 [重新整理] 以更新**清單，以**顯示您剛才建立的匯出工作。

5. 按一下 [匯出工作]，然後按一下彈出頁面上的 [**下載**報告]。
 
    ![在 [匯出] 頁面上，按一下 [匯出]，然後按一下 [下載報告]](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

[**匯出摘要**報告] 包含找到的位置和搜尋結果大小的位置數目。 您可以使用此方式，與刪除之後所產生的報表進行比較，並提供刪除的證明。 **結果**報告包含搜尋結果的詳細摘要，包括主旨、寄件者、收件者、電子郵件已讀取、日期和大小的每封郵件。 如果此報告中的任何詳細資料包含實際溢出的資料，請務必在調查完成時，永久刪除結果 .csv 檔案。

如需匯出報告的詳細資訊，請參閱[匯出內容搜尋報告](export-a-content-search-report.md)。
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>步驟5：使用郵件追蹤記錄檔檢查溢出的資料共用方式

若要進一步調查是否已共用含有溢出資料的電子郵件，您可以選擇性地查詢郵件追蹤記錄，其中包含寄件者資訊，以及您在步驟4中收集的日期範圍資訊。 請注意，針對即時資料，郵件追蹤的保留期間是30天，而歷史資料則為90天。
  
您可以在安全性與合規性中心使用郵件追蹤，也可以在 Exchange Online 中使用對應的 Cmdlet PowerShell。 請務必注意，郵件追蹤不會對傳回的資料完整性提供完整的保證。 如需使用郵件追蹤的詳細資訊，請參閱： 
  
- [安全性與合規性中心內的訊息追蹤](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [安全性 & 規範中心內的新郵件追蹤](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>步驟6：準備信箱

在您複查及驗證搜尋結果是否只包含必須刪除的郵件之後，您必須在刪除溢出的資料時，收集步驟7中所要使用之受影響信箱的電子郵件地址清單。 您也可以先準備好信箱，然後才能永久刪除電子郵件訊息，視包含溢出之資料的信箱上是否啟用單一專案復原，或是否有任何信箱處於保留狀態。
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>取得包含溢出資料之信箱的地址清單

有兩種方法可以收集溢出資料之信箱的電子郵件地址清單。

**選項1：取得包含溢出資料之信箱的地址清單**

1. 開啟 eDiscovery 案例，移至 [**搜尋**] 頁面，然後選取適當的內容搜尋。 
    
2. 在飛入頁面上，按一下 [**查看結果**]。
    
3. 在 **[個別結果]** 下拉式清單中，按一下 **[搜尋統計資料]**。
    
4. 在 [ **Type** ] （類型）下拉式清單中，按一下 [**頂端位置**]。
    
    ![在搜尋統計資料的「頂端位置」頁面上，取得包含搜尋結果的信箱清單](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    隨即會顯示包含搜尋結果的信箱清單。 也會顯示每個信箱中符合搜尋查詢的專案數。
    
5. 複製清單中的資訊，並將其儲存至檔案，或按一下 [**下載**]，將資訊下載到 CSV 檔案。 
    
**選項2：從匯出報告中取得信箱位置**

開啟您在[步驟 4](#step-4-review-and-validate-case-findings)中下載的匯出摘要報告。 在報告的第一欄中，每個信箱的電子郵件地址會列在 [**位置**] 底下。
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>準備信箱，讓您可以刪除溢出的資料

如果已啟用單一專案復原或信箱處於保留狀態，則會永久刪除（清除的）郵件會保留在 [可復原的專案] 資料夾中。 因此，在您可以清除溢出的資料之前，您必須先檢查現有的信箱設定，並停用單一專案復原，並移除任何保留或保留原則。 請記住，您可以一次準備一個信箱，然後在不同的信箱上執行相同的命令，或建立 PowerShell 腳本，以在同一時間準備多個信箱。

- 有關如何檢查是否已啟用單一專案復原，或是如果信箱保留或指派給保留原則，請參閱「步驟1：收集信箱的資訊」中[的 [刪除專案] 中的 [可復原的專案] 資料夾中的 [刪除專案](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)]。 
    
- 請參閱「[刪除位於雲端架構信箱的可復原專案」資料夾中的「刪除專案](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)」中的「步驟2：準備信箱」，以取得停用單一專案復原的指示。 
    
- 請參閱在[雲端式信箱的 [可復原的專案] 資料夾中刪除專案](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)中的 [刪除信箱中的所有保留]，以取得如何從信箱移除保留原則或保留原則的指示。 

- 請參閱在[雲端式信箱的 [可復原的專案] 資料夾中的 [刪除專案] 中的 [刪除資料夾](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox)中的延遲保留]，以取得移除任何類型的保留後，移除信箱的延遲保留的指示。
    
 **重要：** 移除保留原則或保留原則之前，請先與您的記錄管理或法律部門核實。 您的組織可能具有定義信箱保留或資料外泄事件是否優先的原則。 
  
在您確認溢出的資料已永久刪除之後，請務必將信箱還原為先前的設定。 請參閱[步驟 7](#step-7-permanently-delete-the-spilled-data)中的詳細資料。

## <a name="step-7-permanently-delete-the-spilled-data"></a>步驟7：永久刪除溢出的資料

使用您在步驟6中收集並準備的信箱位置，以及在步驟3中建立及完善的搜尋查詢中，以尋找包含溢出資料的電子郵件，您現在可以永久刪除溢出的資料。  如先前所述，若要刪除郵件，您必須是「組織管理」角色群組的成員，或是被指派「搜尋並清除」管理角色。 如需新增使用者至角色群組的詳細資訊，請參閱[在安全性與合規性中心中指派電子文件探索權限](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)。

若要刪除濺入的郵件，請參閱步驟 2 & 3[搜尋並刪除電子郵件訊息](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>步驟8：確認、提供刪除的證明及審核

工作流程中用於管理資料外泄事件的最後一個步驟，就是移至 eDiscovery 案例，並重新執行用來刪除資料以確認未傳回任何結果的相同搜尋查詢，以確認是否已永久移除信箱中溢出的資料。 在您確認已永久移除溢出的資料之後，您可以匯出報告並包含它（連同原始報告）做為刪除的證明。 然後您可以[關閉案例](ediscovery-cases.md#optional-step-9-close-a-case)，如果您已在將來參考，將允許您重新開啟此案例。 此外，您也可以將信箱還原為先前的狀態、刪除搜尋查詢以找出溢出的資料，以及搜尋在管理資料外泄事件時所執行之工作的審計記錄。 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>將信箱還原為先前的狀態

如果您在步驟6中已變更任何信箱設定，以在溢出的資料刪除之前準備信箱，您必須將它們還原為先前的狀態。 請參閱[刪除專案的 [可](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)復原的專案] 資料夾中的「保留」資料夾中的「步驟6：將信箱還原為先前的狀態」。
  
### <a name="deleting-the-search-query"></a>刪除搜尋查詢

如果您在步驟3中建立及使用之搜尋查詢中的關鍵字包含部分實際溢出的資料，則應該刪除搜尋查詢以避免進一步的資料外泄。
  
1. 在 [安全性與合規性中心] 中，開啟 eDiscovery 案例，移至 [**搜尋**] 頁面，然後選取適當的內容搜尋。
    
2. 在飛入頁面上，按一下 [**刪除**]。

    ![選取搜尋，然後按一下彈出頁面上的 [刪除]](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>審核資料外泄調查過程

您可以在調查期間搜尋執行中的 eDiscovery 活動的審計記錄。 您也可以搜尋審計記錄，傳回您在步驟7中執行的**New-ComplianceSearchAction-Purge**命令的審計記錄，以刪除濺入的資料。 如需詳細資訊，請參閱：

- [搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md)

- [在稽核記錄中搜尋電子文件探索活動](search-for-ediscovery-activities-in-the-audit-log.md)
  
