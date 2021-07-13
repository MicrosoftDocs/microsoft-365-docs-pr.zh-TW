---
title: '管理 Microsoft 隱私權管理中的主體權力要求 (預覽) '
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Microsoft 隱私權管理中的主體權利要求解決方案可協助您尋找個人資料，並共同作業檢查內容及建立報告。
ms.openlocfilehash: b1f92aa7b5e6f8117d8e3a4af758f13d6c91fe99
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378474"
---
# <a name="manage-subject-rights-requests-in-privacy-management-preview"></a>管理隱私權管理中的主體權力要求 (預覽) 

在本文中：瞭解如何使用主體權利要求解決方案，尋找您環境中的 **個人資料** 、 **在評論上進行共同** 作業、建立 **報告**，以及 **自動化** 重要工作。

## <a name="purpose-of-subject-rights-requests"></a>主體權力要求的目的

隱私權管理可提供強大的主體權力要求功能，以協助您處理組織中尋找管理其個人資料之人員的要求。 這些要求有時也稱為資料主體要求 (Dsr) 、資料主體存取要求 (DSARs) 或使用者權限要求。 隱私權管理可讓負責滿足主體權力要求的人員輕鬆識別資料主體，並在組織中的資料中尋找其個人資訊 Exchange、SharePoint、OneDrive 及 Teams。

隱私權管理可提供獨特的功能，可協助您優先考慮您為這些要求收集的資料中所要查看的專案。 此解決方案會知曉 Microsoft 資訊保護敏感度標籤，表示可能有機密的內容，而且可能需要特殊的審閱，並使用這些標籤來標示專案。 如需敏感度標籤的詳細資訊，請參閱 [瞭解敏感度標籤](sensitivity-labels.md)。 此外，隱私權管理可以偵測和標示包含多位人員資料的專案，在此情況下，您可能需要在將內容提供給資料主體之前，進行內容密文。

收集並評估資料後，您可以選取要包含在報表和匯出中的最相關專案，並安全地與其他小組成員合作，以移動要求直到完成。

## <a name="get-started-with-subject-rights-requests"></a>主題許可權要求快速入門

隱私權管理為您的隱私權系統管理員提供中央中樞，以處理組織收到的主體權力要求。

若要開始處理新的要求案例，或處理正在進行的要求，請造訪 [主要 **主題權要求** ] 頁面。 它提供您的小組在隱私權管理中建立之案例的視覺效果，其狀態 (使用中、已關閉或逾期) ，以及要求類型，以及所有要求的可篩選清單。 您也可以在此頁面上開啟新的要求。

若要查看有關開啟案例的詳細資訊，請選取清單中的任何要求，然後選擇 [ **前往要求詳細資料**]。 如需詳細資訊，請參閱 [複查並對要求採取動作](#review-and-take-action-on-requests)。

若要開啟新的要求，請參閱 [建立要求](#create-a-request)。

## <a name="create-a-request"></a>建立要求

主體權力管理管理員可以使用隱私權管理的嚮導來建立要求。 這個嚮導將引導您完成尋找資料主體的個人資料，並完成其要求的程式。

四個主要步驟包含下列。

### <a name="identify-the-data-subject"></a>識別資料主體

提供提出要求的主旨名稱，並指定其與貴公司的關聯性。

### <a name="select-the-request-type"></a>選取要求類型

根據資料主體想要在資料中執行的動作，選擇要求類型。 如果他們的要求與特定的資料隱私權規定有關，您也可以從提供的清單中選取，以新增更多內容。  (必要) 設定期限，可讓您輕鬆地排序已臨近或已逾期的要求，並以適時方式加以解決。 要求類型包括：

- **Access**：提供組織在 Microsoft 365 中所用之資料主體個人資訊的摘要。
- **匯出**：提供資料主體的個人資訊的摘要及匯出，如審閱時所收集及批註。
- **後續的標記清單**：會產生可能需要在隱私權管理以外進行其他動作的檔案摘要。 一個範例案例可能是您需要協助每個要求刪除資料主體的個人資訊時。

### <a name="confirm-the-request-name"></a>確認要求名稱

這個步驟可讓您確認此要求的名稱，並新增參考的選擇性描述。

### <a name="review-and-finish"></a>檢閱並完成

您在先前步驟中輸入的內容摘要。 您可以先編輯任何欄位，然後再選取 [ **建立要求**]。

在此層級上，有些屬性可以在建立要求之後編輯，包含期限、要求名稱和描述，但無法變更主體的身分識別等重要屬性。 若要編輯現有的要求，請在 [主體權利要求] 頁面的要求清單中找到它，並使用 [ **編輯要求詳細資料** ] 動作。

## <a name="review-and-take-action-on-requests"></a>檢查要求並採取動作

開啟要求之後，隱私權管理便會開始搜尋您的 Microsoft 365 資料，以尋找您的主旨的相關資料。 若要查看初始結果，請選取清單中的要求，然後選擇 [ **移至要求詳細資料**]。 您可以在這裡深入瞭解要求的屬性、搜尋結果，以及要求的狀態。 此頁面也會變成您的 hub，可供您管理所找到的檔案、建立報告及匯出，以及完成要求的共同作業。

此頁面上的麻將牌包括：

- **詳細資料**：有關要求的核心詳細資料，包括其期限和要求日期、描述和相關的隱私權規定。
- **進度**：時程表，指出完成的步驟和尚未完成的任何工作。
- **資料預估摘要**：搜尋中評估的資料一覽。 若要深入瞭解此資訊，請參閱 View and edit search 查詢。
- **要複查的優先順序專案**：如果適用的話，這會顯示隱私權管理已偵測到之重要專案的相關資訊，包括已在 Microsoft 敏感度標籤上的機密資訊，或包含可能需要密文之多個個人之資料的專案。 您可以在「優先順序類型」欄篩選收集的資料下找到優先順序專案。

### <a name="monitor-progress-and-complete-requests"></a>監視進度和完成要求

主體權力要求會在完成的方式中經歷多個階段。 某些階段會自動進行，因為隱私權管理會進行資料評估，而其他階段則會在主體許可權要求系統管理員和投稿時進行處理。

因為要求可能需要一段時間或多個參與者運作，所以隱私權管理會對要求的狀態進行持續的更新，並提供後續步驟進行的指導。 您可以在 [主體權利要求的概覽] 頁面上查看這些更新。 進度階段包括下列各項。

#### <a name="data-estimate"></a>資料預估

資料預估是資料求值的初始階段。 在建立要求之後，隱私權管理會識別您組織的資料中有多少專案包含可能符合您的資料主體，並記錄這些專案在 Microsoft 365 中的位置。 完成資料預估後，您就可以預覽結果，並複查原始搜尋查詢的詳細資料。 如果您想要編輯搜尋查詢，請參閱 [查看和編輯搜尋查詢](#view-and-edit-search-queries)的指示。 如果您的初始結果看似滿意，您可以繼續 **取得資料**。

- 您可以從任何搜尋中檢索最多10000個個別專案。 與相符專案相關聯的檔案 (例如，電子郵件) 上的檔案附件可能會計入您的總數。 如果您的搜尋超出檔計數閾值，請嘗試修改您的搜尋以精簡其範圍。 如需詳細資訊，請參閱 [View and edit search 查詢](#view-and-edit-search-queries) 一節。 一旦您啟動 [檢索資料] 階段，您將無法編輯搜尋查詢。

#### <a name="retrieve-data"></a>檢索資料

此階段指出隱私權管理正在檢索您的資料。 完成後，它會自動推進以 **查看資料**。

#### <a name="review-data"></a>檢查資料

在此階段，您的參與者應該查看 [資料收集] 索引標籤下的結果。基本步驟包括：

- 選擇是否要在摘要和/或匯出中包含識別的專案。 如果 [匯出] 或 [報告] 中不需要報告的相符項，請選取 [排除] 選項。 如果內容顯示為誤報，您可以選擇 [不符合專案]，以從您的最後一個報告中排除該檔案，並將該專案標記為未被要求挑選的專案。 若要設定專案的狀態，請使用 [動作] 功能表 () 旁邊的豎直省略號，然後選取您想要的選擇。 如果出現提示，請為內部參考新增附注，以解釋您的決定。 排除檔案時，需要附注。
- 使用套用 **標記** 選項可協助您識別需要注意的專案。 可用的標記包含系統所提供的選項，例如，將專案標記為待跟進，而且可能會包含在設定下定義的自訂標記。
- 使用 **批註** 在選取的檔案上建立內嵌標記或密文。 例如，如果您需要針對也包含其他人的個人資訊的個別人員包含檔案，您可以在命令列中使用 [繪圖] 按鈕的 [ **區域密文** ] () ，以黑色輸出所有不屬於要求要求之人員的資訊。 當您編輯完成時，選取 [包含]，將 redacted 檔案新增至要求。 請注意，批註會建立檔案的複本，使原始檔案中的任何專案都不會變更，而且會保留在原來的位置。 此副本會儲存在您的 Azure blob 中，並在您規定的資料保留期間內保留。 如需詳細資訊，請參閱下列 [資料保留](#data-retention) 。
- 若要查看專案上的附注，請選取它，然後移至 [檔案附注] 索引標籤。您也可以使用 [新增檔附注] 選項來建立新的批註。 若要在整體案例層級查看或新增附注，請移至上方的 [主要備忘] 索引標籤，然後使用 [ **新增案例附注**]。 這些附注對使用要求的使用者可以看見，但不會包含在最後一個報告中，也不會與資料主體共用。

當所有專案都已經過檢查並設定其狀態時，請選取 [ **完成複查** ] 以開啟 [flyover] 窗格，您可以在其中查看資料摘要及新增相關的附注。 這些附注適用于內部記錄，而且不會與資料主體共用。 再次選取 [完成回顧]，以移至下一個階段。 您將會在稍後的 [報告] 索引標籤下提供您的決策摘要。

#### <a name="generate-reports"></a>產生報告

此階段表示您的報表正在產生中。 完成後，即可在 [ **報告** ] 索引標籤底下找到。您可以在這裡匯出您的完成檔案，以傳遞給進行要求的資料主體。

#### <a name="close-the-request"></a>關閉要求

當您執行必要的動作來解決您的主體權力要求時，請選擇 [ **關閉要求**]。 這會建立最終報告，該報告會進行加密，並在 [ **報表** ] 索引標籤中提供。這可能需要一段時間，視要求中的檔案數目而定。

### <a name="view-and-edit-search-queries"></a>查看和編輯搜尋查詢

若要查看有關主體權利要求背後之資料搜尋的詳細資訊，請選取 [資料預估摘要卡] 中的 [ **查看搜尋查詢詳細** 資料]。 這會開啟窗格摘要查詢，並顯示找到之內容的進一步詳細資料。

您可以在這裡選擇 **預覽搜尋結果** ，以查看會傳回此查詢的內容類型。 如果您決定要變更此搜尋的屬性，但尚未開始「檢索資料」階段，您可以使用 [ **編輯搜尋查詢** ] 選項。 這個嚮導可讓您變更或新增資料主體識別、搜尋篩選和條件的內容，以及要在其中尋找資料 (的位置，包括 Exchange、SharePoint、OneDrive 及/或 Teams) 。 使用這些選項可達成您想要的明確程度。 您可以先查看新查詢的最後一個版本，然後再進行 **儲存**。

當您完成編輯搜尋查詢時，會執行新的搜尋以取代先前的搜尋結果。 這會將您的狀態從 [進度] 區段重設為第一個步驟（ **資料預估**）。 新的搜尋可能需要長達60分鐘才能完成。 完成後，您會在要求的 [詳細資料] 頁面上看到更新的結果。

### <a name="data-retention"></a>資料保留

透過此工具產生的報告和相關聯的資料（例如，在 Azure 中儲存的批註檔案）會儲存指定的時間長度。 這段期間是透過「**資料保留期間**」區段中 **設定**，在全域層級定義，可讓您選擇30到90天。 若要深入瞭解，請參閱 [開始使用隱私權管理](privacy-management-setup.md)。

## <a name="collaborate-on-requests-with-teams"></a>Teams 的要求共同作業

隱私權管理可透過 Microsoft Teams 共同作業，以允許群組在主體權力要求中共同作業。 當您建立新的要求時，會自動建立 Teams 通道，並依預設將其關聯至您的要求。 在這裡，您可以討論要求，並在它移動到完成時，安全地分享輸入和貢獻。 若要加入交談，請開啟您的要求並使用 [ **與合作者** 互動] 選項。 這會開啟 Microsoft Teams，並將您放在您的主體權力要求小組網站的一般通道內。

若要查看可在您的小組網站上流覽及參與的活動合作者清單，請在您的主體許可權要求中開啟 [ **合作者** ] 索引標籤。若要新增此要求的其他使用者共同作業，請選取 [新增合作者的選項]。

若要在建立主體權力要求時變更產生 Teams 網站的預設行為，請選取 [主體權利要求] 頁面右上角的 [**設定** 齒輪]，然後選取 [ **Teams** 共同作業] 以修改設定。

您也可以使用主體權利要求中右上方的 [**共用**] 選項，透過 Teams 或電子郵件來迴圈人員，或複製隱私權管理頁面的連結。 透過 Teams 共用，可讓您選取您的帳戶可使用的現有 Teams 網站，然後在該網站中選取特定通道，以在該網站中傳送此案例的連結，以及您提供的任何訊息。

## <a name="automate-subject-rights-request-tasks"></a>自動要求的主體權力要求任務

Microsoft Power Automate 是一種工作流程服務，可在應用程式和服務間自動執行動作。 當您為隱私權管理啟用 Power Automate 資料流程時，您可以自動化案例和使用者的重要工作。 若要深入瞭解 Power Automate，請流覽其[檔網站](/power-automate/getting-started)。

使用包含隱私權管理的 Microsoft 365 訂閱的客戶不需要另一個 Power Automate 授權，即可使用建議的隱私權管理 Power Automate 範本。 您可以自訂這些範本，以支援您的組織及涵蓋核心隱私權管理案例。 如果您選擇在這些範本中使用特優 Power Automate 功能，請使用 Microsoft 365 規範連接器建立自訂範本，或在 Microsoft 365 中使用其他規範區域的 Power Automate 範本，您可能需要更多 Power Automate 授權。

以下是隱私權管理中包含的 Power Automate 範本：

- **在 ServiceNow 中建立隱私權管理案例的記錄**：此範本適用于想要使用其 ServiceNow 解決方案追蹤主體權力要求案例的組織。 系統會要求您輸入 ServiceNow 實例的詳細資料。 連線至您的實例之後，系統管理員就可以在 ServiceNow 中為案例建立記錄，並視需要自訂範本將填入所選欄位的內容。 如需連接器的詳細資訊，請參閱 [ServiceNow connector reference] 頁面](/connectors/service-now/)。
- **建立行事曆提醒**：此範本是用於設定 Outlook 行事曆中的主體許可權要求的到期日期提醒。 該工具會為您從要求的屬性填入特定詳細資料，例如要求的名稱及其到期日。 您可以新增描述性詳細資料、指定收件者，以及調整其他的高級設定。

### <a name="create-a-new-power-automate-flow-from-a-template"></a>從範本建立新的 Power Automate 流程

若要開始，請開啟您要使用的主體權力要求，選取 [**自動**]，然後選取 [**管理 Power Automate 流程**]。 這會開啟 [資料流程] 飛彈出窗格。 使用 [新增] 選項，然後從可用的選項中選擇您要使用的範本。 從這裡，依照提示完成安裝程式。

在儲存範本的實例之後，您必須從主體權利要求的詳細資料頁面執行它，使流程實例具有正確的內容和識別碼。 開啟要求，回到 [ **自動化** ] 功能表中，選取範本，然後選取 [ **執行流程**]。 您可以選取 [ **查看流程執行活動**]，以查看過去的活動。

### <a name="share-a-power-automate-flow"></a>共用 Power Automate 流程

透過分享 Power Automate 流程，您可以新增另一個擁有者，並允許他們編輯、更新和刪除流程。 所有擁有者也可以存取「執行歷程記錄」，並新增或移除其他擁有者。 若要共用流程，請開啟您要使用的主體權力要求，選取 [**自動**]，然後選取 [**管理 Power Automate 流程**]。 您可以從這個窗格選取現有的流程，然後使用 [共用] 選項新增使用者或群組。

此窗格也可讓您選擇管理內嵌連線至 Power Automate 流程中所使用的服務。 變更這些設定可能會影響您執行流程的能力。

### <a name="edit-or-delete-power-automate-flow"></a>編輯或刪除 Power Automate 流程

若要調整 Power Automate 流程的詳細資料，請開啟主體權利要求，選取 [**自動**]，然後選取 [**管理 Power Automate 流程**]。 您可以從這個窗格選取現有流程以查看詳細資料。 使用任何區段中的 Edit 若要變更屬性，請使用 [儲存]。

若要徹底移除流程，請使用 [ **刪除** ] 選項。 它會移除所有擁有者的流程，並將其卸載給所有使用者。 先前的流程實例將繼續執行，以避免資料遺失。 您可以先確認您的選擇，最後再刪除。

## <a name="data-matching"></a>資料符合

透過資料比對，組織可以啟用隱私權管理解決方案，以根據正確提供的資料值來識別資料主體。 這有助於提高內部人員和您與您互動的外部使用者的資料主體內容的準確性。 此外，它也可簡化在建立主體許可權時手動提供欄位的需求，並提供主題許可權要求中的內容，以及顯示最具資料主體內容之專案的總覽磚。 若要深入瞭解該視圖，請參閱 [尋找及形象化您的資料](privacy-management-data-profile.md#items-with-the-most-data-subject-content)。

若要使用資料符合功能，您必須是隱私權管理角色群組的成員。 從 [主要主體權利要求] 頁面的右上方選取 [設定] 齒輪圖示，然後選取 [ **資料** 比對]。 在這裡，您將需要定義個人資料架構，並提供個人資料上傳，如下所示。 請注意，您可以新增專案，也可以刪除透過 UI 新增的專案。 不過，您此時無法從 UI 修改專案。

### <a name="prepare-for-data-import"></a>準備資料匯入

在定義架構或上傳資料之前，您需要識別資料主體資訊的來源。 必要的檔案格式為 .csv，可由諸如 Microsoft Excel 等應用程式讀取。 結構此匯出，使欄標題出現在第一列。 這些標題應包含您個人資料架構的屬性名稱。 檢查每個欄位中的資料格式。 如果有任何資料包含逗號，請使用雙引號括住這些值，以確保不會將它剖析成不同的欄位。

### <a name="define-the-personal-data-schema"></a>定義個人資料架構

個人資料架構會說明資料主體的屬性。 在 [資料對應設定] 區域的第一個索引標籤上 Upload 此架構。 必要檔案包含 **個人資料架構** xml 檔和 **規則套件** xml 檔案。

#### <a name="personal-data-schema-xml"></a>個人資料架構 XML

個人資料架構檔案是一個 XML 檔，可定義預期的欄名稱。

- 將此架構檔案命名為 *pdm.xml*。
- 使用下列範例所示的功能變數名稱標記，定義每個欄名稱。
- 可搜尋 = "true" 為您想要搜尋的欄位，最多可以有五個欄位。 您必須至少有一個功能變數名稱可供搜尋。 範例語法： `\<Field name="" searchable=""/>` 。
- 個人資料架構具有「資料存儲」標記區段。 必須將四個強制欄位對應至您的功能變數名稱： primaryKeyField、upnField、firstNameField、lastNameField。

舉例來說，下列 XML 檔案會定義一個範例架構，其中有五個指定為可搜尋的欄位： PatientID、MRN、SSN、電話及 DOB。 PrimaryKeyField 會對應至 PatientID，upnField 會對應至 MRN，firstNameField 會對應至 FirstName，而 lastNameField 會對應至 LastName。

您可以複製、修改及使用我們的範例。

 ```xml
<PdmSchema xmlns="http://schemas.microsoft.com/office/2020/pdm">
      <DataStore name="Patientrecords" description="Schema for patient records" version="1" primaryKeyField="PatientID" upnField="MRN" firstNameField="FirstName" lastNameField="LastName">
            <Field name="PatientID" searchable="true"/>
            <Field name="MRN" searchable="true" />
            <Field name="FirstName" />
            <Field name="LastName" />
            <Field name="SSN" searchable="true" />
            <Field name="Phone" searchable="true" />
            <Field name="DOB" searchable="true" />
            <Field name="Gender" />
            <Field name="Address" />
      </DataStore>
</PdmSchema>
 ```

#### <a name="rule-package-xml"></a>規則套件 XML

當您設定規則套件時，請務必正確參考上述建立的個人資料架構檔案： pdm.xml。 在下列範例規則套件 XML 中，必須自訂下欄欄位，以建立資料符合機密類型：

- **RulePack 識別碼**  & **PrivacyMatch 識別碼**：使用新的 guid 來產生 GUID。
- **資料** 儲存：此欄位會指定要使用的個人資料相符的查閱資料存放區。 為已設定的個人資料架構提供已定義的資料存儲名稱。
- **idMatch**：此欄位指向 [個人資料相符] 的主要元素。
  - **相符**：指定要在完全查閱中使用的欄位。 提供個人資料架構的可搜尋功能變數名稱。
  - **分類**：此欄位指定觸發個人資料相符的敏感類型相符專案。 您可以提供現有內建或自訂敏感性資訊類型的名稱或 GUID。 為了避免出現效能問題，如果您使用自訂的機密資訊類型做為個人資料符合中的分類元素，請勿使用會符合大量內容 (的自訂敏感資訊類型，例如 "任何數位" 或 "任何五個字母的字" ) 。 建議您新增支援關鍵字，或在自訂分類機密資訊類型的定義中包含格式設定。
- **相符**：此欄位會指出 idMatch 中鄰近的其他證據。
  - **相符**：在資料存儲的個人資料架構中提供任何功能變數名稱。
- **Resource**：此區段會在多個地區設定中指定敏感類型的名稱和描述。
  - **idRef**：提供 ExactMatch 識別碼的 GUID。
  - **名稱 & 描述**：按需自訂。

在下列的規則套件 XML 範例中，我們會參考上一個步驟中建立個人資料架構 XML 的 pdm.xml 範例檔案：

- **資料** 檔：資料檔案名稱參考我們先前建立的架構檔案：資料檔案 = "PatientRecords"。
- **idMatch**： idMatch 值會參照先前建立的 pdm.xml 檔案中所列出的可搜尋欄位： idMatch 相符 = "SSN"。
  - **分類**：分類值參考現有或自訂的機密資訊類型：分類 = "U.S. Social Security NUMBER (SSN) "。 (在此案例中，我們使用美國社會安全號碼作為現有的敏感性資訊類型)。

以 Unicode 編碼) 以 XML 格式 (建立規則套件，如下列程式碼範例所示。 您可以複製、修改及使用此範例。

 ```xml
<RulePackage xmlns="http://schemas.microsoft.com/office/2020/pdm">
  <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b21">
    <Version build="0" major="2" minor="0" revision="0" />
    <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
    <Details defaultLangCode="en-us">
      <LocalizedDetails langcode="en-us">
        <PublisherName>IP DLP</PublisherName>
        <Name>Health Care PDM Rulepack</Name>
        <Description>This rule package contains the Personal Data Match sensitive type for health care sensitive types.</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  <Rules>
    <PrivacyMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB381" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="6">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </PrivacyMatch>
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB381">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">PDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
 ```

### <a name="upload-personal-data"></a>Upload 個人資料
在定義個人資料架構之後，您可以在 [資料比對設定] 頁面的第二個索引標籤上執行 [ **個人資料上傳** ]。 當您選取 [ **新增**] 時，請選擇您在第一個步驟中定義的個人架構，然後上傳包含個人資料的檔。

您可以選擇本機檔，或提供 SAS URL 至包含您個人資料檔的現有 Microsoft Azure 儲存體位置，以上傳此個人資料。
如果您已在此程式中，將檔案當做符合建立之架構的第一個步驟，您可以使用該檔案進行上傳。
