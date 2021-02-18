---
title: 安全性與合規性中心內的郵件追蹤
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以在安全性與合規性中心使用郵件追蹤，以了解郵件發生什麼情況。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ce26f7a6cdad15019e2b40eb6f8746e5723d4f0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290654"
---
# <a name="message-trace-in-the-security--compliance-center"></a>安全性與合規性中心內的郵件追蹤

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="message-trace-features"></a>郵件追蹤功能

安全性與合規性中心內的郵件追蹤可追蹤透過 Exchange Online 組織收發的電子郵件。 您可以判斷服務是否已經收到、拒絕、延遲或傳遞郵件。 它也會顯示在郵件到達其最終狀態前，已對郵件執行哪些動作。

安全性 & 規範中心內的郵件追蹤改善於 Exchange 系統管理中心中提供的原始郵件追蹤 (EAC) 。 您可以使用郵件追蹤中的資訊，有效地解答使用者對郵件發生什麼問題、疑難排解郵件流程問題，以及驗證原則變更。

> [!NOTE]
>
> - 若要執行郵件追蹤，您必須是「組織管理」、「合規性管理」或「服務台」角色群組的成員。 如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。
>
> - 結果中顯示的訊息數目上限取決於您選取的報告類型 (請參閱 [選擇報告類型](#choose-report-type) 一節，以取得詳細資料) 。 Exchange Online PowerShell 或獨立 EOP 中的 [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) Cmdlet PowerShell 會傳回結果中的所有郵件。

## <a name="open-message-trace"></a>開啟郵件追蹤

1. 開啟安全性 & 規範中心，網址為 <https://protection.office.com> 。

2. 展開 [ **郵件流程**]，然後選取 [ **郵件追蹤**]。

## <a name="message-trace-page"></a>[訊息追蹤] 頁面

您可以按一下 [開始追蹤] 按鈕，從這裡開始新的預設追蹤。 這會搜尋過去兩天的所有寄件者和收件者的所有郵件。 或者，您也可以從可用的查詢類別使用其中一個已儲存的查詢，並且依現狀執行它們或將它們用來作為自己的查詢起點：

- **預設查詢**： Microsoft 365 提供的內建查詢。

- **自訂查詢**：貴組織的系統管理員所儲存的查詢，可供日後使用。

- **自動儲存的查詢**：過去十筆最近執行的查詢。 此清單可讓您輕鬆繼續進行您上次未完成的工作。

此外，此頁面也提供一個 [可下載的報告] 區段，顯示您已提交的要求，以及本身可供下載的報告。

## <a name="options-for-a-new-message-trace"></a>新郵件追蹤的選項

### <a name="filter-by-senders-and-recipients"></a>依寄件者和收件者篩選

預設值為 [所有寄件者] 和 [所有收件者]，但您可以使用下列欄位來篩選結果：

- **依據這些人**：在此欄位中按一下以選取貴組織中的一或多個寄件者。 您也可以開始輸入名稱，然後清單中的項目將依據您輸入的內容進行篩選，就像搜尋頁面的運作方式一樣。

- **給這些人**：在此欄位中按一下以選取貴組織中的一或多個收件者。

> [!NOTE]
>
> - 您也可以輸入外部寄件者和收件者的電子郵件地址。 支援萬用字元 (例如 `*@contoso.com`)，但您無法同時在相同的欄位中使用多個萬用字元項目。
>
> - 您可以貼上多份以分號 (`;`) 分隔的寄件者或收件者清單。 空格 (`\s`)、歸位字元 (`\r`) 或換行 (`\n`)。

### <a name="time-range"></a>時間範圍

預設值為 [2 天]，但您最多可指定 90 天的日期/時間範圍。 當您使用日期/時間範圍時，請考慮這些問題：

- 根據預設，您使用時間線在 [滑桿] 檢視中選取時間範圍。 您只能選取顯示的天數或時間設定。 嘗試選取介於中間的值會讓開始/結束泡泡貼齊最近的顯示設定。

  ![安全性與合規性中心的新增郵件追蹤內的滑桿時間範圍](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  不過，您也可以切換到 [自訂] 檢視，您可以在該檢視中指定 [開始日期] 和 [結束日期] 值 (包括時間)，而且還可以選取日期/時間範圍的 [時區]。 請注意，[時區] 設定會同時套用到您的查詢輸入和查詢結果。

  ![安全性與合規性中心的新增郵件追蹤內的自訂時間範圍](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  10 天內的結果會立即以 [摘要] 報告的形式提供。 如果您指定甚至稍微大於 10 天的時間範圍，結果將會顯示為只能以可下載的 CSV 檔案形式提供 ([增強摘要] 或 [延伸] 報告)。

  如需不同報告類型的詳細資訊，請參閱本文中的 [選擇報告類型](#choose-report-type) 一節。

  > [!NOTE]
  > 已使用封存的郵件追蹤資料來準備增強的摘要和擴充報告，而且可能需要數小時的時間，您的報告才可供下載。 根據有多少個其他系統管理員也已同時提交報告要求而定，您可能也會在系統開始處理您的佇列要求前察覺到延遲的情形。

- 在 [滑桿] 檢視中儲存查詢會儲存相對的時間範圍 (例如，今天起 3 天之後的日期)。 在 [自訂] 檢視中儲存查詢會儲存絕對的日期/時間範圍 (例如，2018-05-06 13:00 到 2018-05-08 18:00)。

### <a name="more-search-options"></a>其他搜尋選項

#### <a name="delivery-status"></a>傳遞狀態

您可以將預設值 [全部] 保留為選取狀態，或者也可以選取下列其中一個值來篩選結果：

- **已傳遞**：郵件已成功傳遞到預定目的地。

- **擱置**：仍在嘗試或正在重新嘗試傳遞郵件。

- **已展開**：在傳遞到群組的個別成員之前，已展開通訊群組收件者。

- **失敗**：未傳遞郵件。

- **已隔離**：已隔離郵件 (垃圾郵件、大宗郵件或網路釣魚)。 如需詳細資訊，請參閱 [在 EOP 中隔離的電子郵件訊息](quarantine-email-messages.md)。

- **篩選為垃圾郵件**：已將郵件識別為垃圾郵件，而且已拒絕或封鎖該郵件 (未隔離)。

- **取得狀態：** 郵件最近是由 Microsoft 365 收到，但其他狀態資料仍無法使用。 請在幾分鐘後再回來查看。

> [!NOTE]
> 僅限超過10天的搜尋才可使用 **擱置中、** **隔離** 及 **篩選的垃圾郵件** 。 此外，實際和報告的傳遞狀態之間可能會有 5 到 10 分鐘的延遲。

#### <a name="message-id"></a>郵件識別碼

這是網際網路郵件識別碼 (也稱為「用戶端識別碼」)，可在郵件標頭的 [郵件識別碼:] 標頭欄位中找到。 使用者可將此值提供給您，以便您調查特定郵件。

此值是郵件存留時間的常數。 針對 Microsoft 365 或 Exchange 中建立的郵件，此值的格式為 `<GUID@ServerFQDN>` （包括角括弧 () ） \< \> 。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。 其他郵件系統可能會使用不同的語法或值。 此值應為唯一的狀態，但並非所有電子郵件系統都會嚴格遵循此要求。 如果來自外部來源的內送郵件的 [郵件識別碼:] 標頭欄位不存在或空白，則會指派任意值。

當您使用 [郵件識別碼:] 來篩選結果時，請務必包含完整的字串，包括任何角括號。

#### <a name="direction"></a>方向

您可以將預設值 [全部] 保留為選取狀態，或者也可以選取 [內送] (傳送給貴組織中收件者的郵件) 或 [外寄] (貴組織中使用者所傳送的郵件) 來篩選結果。

#### <a name="original-client-ip-address"></a>原始用戶端 IP 位址

您可以依據用戶端 IP 位址篩選結果，來調查傳送大量垃圾郵件或惡意程式碼，所以遭到駭客入侵的電腦。 雖然郵件看起來可能像是來自多個寄件者，真實的情況有可能是來自產生所有這些郵件的同一部電腦。

> [!NOTE]
> 用戶端 IP 位址資訊只可用於10天，且只有 **增強型摘要** 或 **延伸** 報告 (可供下載的 CSV 檔案) 。

### <a name="choose-report-type"></a>選擇報告類型

提供下列報告類型：

- **摘要**：適用於時間範圍小於 10 天，且不需要任何額外篩選選項的情況。 幾乎可在按一下 [搜尋] 後立即取得結果。 報告會傳回最多20000的結果。

- **增強摘要** 或 **延伸**：這些報告僅以可下載的 CSV 檔案形式提供，而且需要下列一或多個篩選選項 (無論時間範圍為何)：[依據這些人]、[給這些人] 或 [郵件識別碼]。 您可以將萬用字元用於寄件者或收件者 (例如，\*@contoso.com)。 增強型摘要報告會傳回最多50000的結果。 延伸報告會傳回最多1000個結果。

> [!NOTE]
> 
> - 系統會使用封存的郵件追蹤資料來準備 [增強摘要] 和 [延伸] 報告，而且最多可能需要數小時的時間，才能下載您的報告。 根據有多少個其他系統管理員也已同時提交報告要求而定，您可能也會在系統開始處理您的佇列要求前察覺到延遲的情形。
> 
> - 雖然您可以選取任何日期/時間範圍的 [增強摘要] 或 [延伸] 報告，通常將還無法取得這兩種報告類型過去四個小時的封存資料。

當您按一下 [下一步] 時，會呈現列出您已選取的篩選選項的摘要頁面、唯一 (可編輯) 的報告標題，以及在郵件追蹤完成時接收通知的電子郵件地址 (也可編輯，而且必須位於貴組織的其中一個可接受的網域中)。 按一下 [準備報告] 來提交郵件追蹤。 在主要的 [郵件追蹤] 頁面上，您可以在 [可下載的報告] 區段中查看報告狀態。

如需有關各種不同報告類型中傳回資訊的詳細資訊，請參閱下一節。

## <a name="message-trace-results"></a>訊息追蹤結果

不同的報告類型會傳回不同程度的資訊。 下列各節將說明各種不同報告中所提供的資訊。

### <a name="summary-report-output"></a>摘要報告輸出

執行郵件追蹤之後，將會列出結果，並依遞減日期/時間進行排序 (先列出最近的項目)。

![安全性與合規性中心的郵件追蹤摘要報告結果](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

摘要報告包含下列資訊：

- **日期**：服務接收到郵件的日期和時間 (使用設定的 UTC 時區)。

- **寄件者**：寄件者的電子郵件地址 (*別名*@*網域*)。

- **收件者**：收件者的電子郵件地址。 針對傳送給多個收件者的郵件，每個收件者各有一行。 如果收件者是通訊群組、動態通訊群組或具備郵件功能的安全性群組，群組將會是第一個收件者，然後每個群組成員會列在個別的行中。

- **主旨**：郵件的 [主旨：] 欄位的前 256 個字元。

- **狀態**：這些值在 [＜傳遞狀態＞](#delivery-status)一節中有相關說明。

根據預設，會載入前 250 筆結果，而且可供使用。 當您向下捲動時，在載入下一批結果時有稍微停頓的情形。 您可以按一下 [全部載入] 來載入所有結果 (最多 10,000 筆)，而不使用捲動的方式。

您可以按一下欄標頭，依該欄中的值以遞增或遞減順序排序結果。

您可以按一下 [篩選結果] 來依一或多個欄篩選結果。

您可以按一下 [匯出結果]，然後選取 [匯出所有結果]、[匯出載入的結果] 或 [匯出選取項目]，以在選取一或多列後匯出結果。

#### <a name="find-related-records-for-this-message"></a>尋找此郵件的相關記錄

相關郵件記錄是擁有相同 [郵件識別碼] 的記錄。 請記得，甚至兩個人之間所傳送的單一郵件都會產生多筆記錄。 在郵件受到通訊群組展開、轉寄、郵件流程規則 (也稱為傳輸規則) 等因素影響時，郵件數目也會增加。

選取某一列的核取方塊之後，您可以按一下出現的 [尋找相關內容] 按鈕，或選取 [其他選項] ![更多](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> [尋找此郵件的相關記錄]，以尋找郵件的相關記錄。

如需郵件識別碼的詳細資訊，請參閱本文前面的「郵件識別碼」一節。

#### <a name="message-trace-details"></a>訊息追蹤詳細資料

在摘要報告輸出中，您可以使用下列任一方法檢視郵件的相關詳細資料：

- 選取列 (按一下列中的任何位置，除了核取方塊以外)。

- 選取列的核取方塊，然後按一下 [其他選項] ![更多](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> [檢視郵件詳細資料]。

   ![在安全性與合規性中心的郵件追蹤摘要報告結果資料列上按兩下後的詳細資料](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

郵件追蹤詳細資料包含摘要報告中未呈現的下列額外資訊：

- **郵件事件**：此區段包含多種分類，可協助針對服務在郵件上執行的動作進行分類。 以下是您可能會遇到的 **某些更有趣的事件**：

  - **接收**：服務收到郵件。

  - **傳送**：服務寄出的郵件。

  - **失敗**：無法傳遞郵件。

  - **傳遞**：郵件已傳遞到信箱。

  - **展開**：郵件已傳送到展開的通訊群組。

  - **轉換**：因為內容轉換、郵件收件者限制或代理程式的緣故，收件者已移至傳遞路徑分為兩條的郵件。

  - **延遲**：郵件傳遞已延遲，且稍後可能再試。

  - **已解析**：根據 Active Directory 查閱，已將郵件重新導向至新的收件者地址。 發生此情況時，原始收件者地址會伴隨著郵件的最終傳遞狀態，出現在郵件追蹤裡的另一列。

  > [!NOTE]
  > 
  > - 一封已成功傳遞的普通郵件都會在郵件追蹤中產生多個 [事件] 項目。
  > 
  > - 這份清單不應詳盡。 如需更多事件的說明，請參閱[郵件追蹤記錄中事件種類](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。 請注意，此連結是 Exchange Server (內部部署 Exchange) 主題。

- **其他資訊**：此區段包含下列詳細資料：

  - **郵件識別碼**：此值會在本文稍早的 [郵件識別碼](#message-id) 一節中說明。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。

  - **郵件大小**

  - **來源 IP**：傳送郵件的電腦 IP 位址。 對於從 Exchange Online 傳送的外寄郵件，此值為空白。

  - **目標 IP**：服務嘗試傳遞郵件的目標 IP 位址。 如果郵件有多位收件者，則會顯示這些位址。 對於傳送至 Exchange Online 的輸入郵件，此值為空白。

### <a name="enhanced-summary-reports"></a>增強摘要報告

您可以在訊息追蹤開頭的 [可下載的報告] 區段中取得可用 (已完成) 的 [增強摘要] 報告。 報告提供下列資訊：

- **origin_timestamp**<sup>*</sup>：服務一開始接收到郵件的日期和時間 (使用設定的 UTC 時區)。

- **sender_address**：寄件者的電子郵件地址 (*別名*@*網域*)。

- **Recipient_status**：將郵件傳遞至收件者的狀態。 如果郵件傳送給多個收件者，它會顯示每個收件者的所有收件者和對應狀態，格式為： \<*email address*\> ## \<*status*\> 。 例如：

  - **##接收、傳送** 表示郵件已由服務接收，而且已傳送到預定的目的地。

  - **##接收、失敗** 表示郵件已由服務接收，但無法傳遞到預定的目的地。

  - **##接收、傳遞** 表示郵件已由服務接收，而且已傳遞到收件者的信箱。

- **message_subject**：郵件的 [主旨] 欄位的前 256 個字元。

- **total_bytes**：郵件大小 (以位元組為單位)，包括附件。

- **message_id**：此值會在本文稍早的 [郵件識別碼](#message-id) 一節中說明。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。

- **network_message_id**：唯一的郵件識別碼值，會持續存在於郵件可能因為複本發送或通訊群組展開等原因而產生的所有複本上。 例如，此值可能為 `1341ac7b13fb42ab4d4408cf7f55890f`。

- **original_client_ip**：寄件者的用戶端 IP 位址。

- **directionality**：表示郵件是內送 (1) 到您的組織，或由您的組織外寄 (2)。

- **connector_id**：來源或目的地連接器的名稱。 如需 Exchange Online 中連接器的詳細資訊，請參閱[使用 Office 365 中的連接器設定郵件流程](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

- **delivery_priority**<sup>*</sup>：傳送優先順序是否為 [高]、[低] 或 [標準] 的郵件。

<sup>*</sup> 這些屬性只能在增強型摘要報告中使用。

### <a name="extended-reports"></a>[延伸] 報告

您可以在郵件追蹤開頭的 [可下載的報告] 區段中取得可用 (已完成) 的 [延伸] 報告。 幾乎所有來自 [增強摘要] 報告的資訊都可在 [延伸] 報告中取得 (除了 **origin_timestamp** 和 **delivery_priority** 以外)。 下列額外資訊只有在 [延伸] 報告中才能取得：

- **client_ip**：已提交郵件之電子郵件伺服器或郵件用戶端的 IP 位址。

- **client_hostname**：已提交郵件之電子郵件伺服器或郵件用戶端的主機名稱或 FQDN。

- **server_ip**：來源或目的地伺服器的 IP 位址。

- **server_hostname**：目的地伺服器的主機名稱或 FQDN。

- **source_context**：與 **source** 欄位相關聯的額外資訊。 例如：

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **source**：負責事件的 Exchange Online 元件。 例如：

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**：這些對應到 [尋找此郵件的相關記錄](#find-related-records-for-this-message)一節中所說明的 [郵件事件] 值。

- **internal_message_id**：目前正在處理郵件之 Exchange Online 伺服器所指派的郵件識別碼。

- **recipient_address**：郵件收件者的電子郵件地址。 多個電子郵件地址會以分號字元 (;) 隔開。

- **recipient_count**：郵件中的收件者總人數。

- **related_recipient_address**：與 `EXPAND`、`REDIRECT` 和 `RESOLVE` 事件搭配使用，顯示與郵件相關聯的其他收件者電子郵件地址。

- **reference**：此欄位包含特定事件類型的其他資訊。 例如：

  - **DSN**：包含報告連結，也就是在此事件後續產生 DSN 的情況下，相關聯之傳遞狀態通知 (也稱為 DSN、未傳遞回報、NDR 或退回的郵件) 的 **message_id** 值。 如果這是 DSN 郵件，此欄位會包含產生 DSN 之原始郵件的 **message_id** 值。

  - **EXPAND**：包含相關郵件的 **related_recipient_address** 值。

  - **RECEIVE**：如果郵件是由其他程序 (例如 [收件匣] 規則) 所產生，可能會包含相關郵件的 **message_id** 值。

  - **SEND**：包含任何 DSN 郵件的 **internal_message_id** 值。

  - **TRANSFER**：包含分支之郵件的 **internal_message_id** 值 (例如，由於內容轉換、郵件收件者限制或代理程式)。

  - **MAILBOXRULE**：包含導致 [收件匣] 規則產生外寄郵件之內送郵件的 **internal_message_id** 值。

    對於其他類型的事件，此欄位通常為空白。

- **return_path**：傳送郵件的 **MAIL FROM** 命令所指定的傳回電子郵件地址。 雖然此欄位絕對不會是空白，但會以 `<>` 來表示 Null 寄件者地址值。

- **message_info**：郵件的其他相關資訊。 例如：

  - `DELIVER` 與 `SEND` 事件的郵件原始日期時間 (UTC)。 原始日期時間是指郵件最初進入 Exchange Online 組織的時間。 以 ISO 8601 日期時間格式表示 UTC 日期時間：`yyyy-mm-ddThh:mm:ss.fffZ`，其中 `yyyy` = 年、`mm` = 月、`dd` = 日，`T` 表示時間元件的開頭，`hh` = 時、`mm` = 分、`ss` = 秒、`fff` = 秒的分數，以及另外一個表示 UTC 的方法 `Z` 代表 `Zulu`。

  - 驗證錯誤。 例如，您可能會看見值 `11a`，以及發生驗證錯誤時所使用的驗證類型。

- **tenant_id**：代表 Exchange Online 組織的 GUID 值 (例如，`39238e87-b5ab-4ef6-a559-af54c6b07b42`)。

- **original_server_ip**：原始伺服器的 IP 位址。

- **custom_data**：包含特定事件類型的相關資料。 如需詳細資訊，請參閱下列各節。

#### <a name="custom_data-values"></a>custom_data 值

各種 Exchange Online 代理程式會使用 `AGENTINFO` 事件的 **custom_data** 欄位來記錄郵件處理詳細資料。 下列各節說明某些更有趣的代理程式。

#### <a name="spam-filter-agent"></a>垃圾郵件篩選器代理程式

以 `S:SFA` 做為開頭的 **custom_data** 值是來自垃圾郵件篩選器代理程式。 下表說明重要的詳細資料：

****

|值|描述|
|---|---|
|`SFV=NSPM`|郵件標記為非垃圾郵件，並傳送給預定的收件者。|
|`SFV=SPM`|郵件被反垃圾郵件篩選 (（也稱為內容篩選) ）標示為垃圾郵件。|
|`SFV=BLK`|已略過篩選，且郵件來自封鎖的寄件者，所以封鎖郵件。|
|`SFV=SKS`|在反垃圾郵件篩選處理之前，郵件會標示為垃圾郵件。 這包括符合郵件流程規則 (也稱為傳輸規則) 而自動標記為垃圾郵件，因而略過所有其他篩選的郵件。|
|`SCL=<number>`|如需不同 SCL 值和其意義的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。|
|`PCL=<number>`|郵件的網路釣魚信賴等級 (PCL) 值。 這些值的解譯方式與[垃圾郵件信賴等級](spam-confidence-levels.md)中所記載的 SCL 值相同。|
|`DI=SB`|已封鎖郵件的寄件者。|
|`DI=SQ`|已隔離郵件。|
|`DI=SD`|已刪除郵件。|
|`DI=SJ`|郵件被傳送到收件者的 [垃圾郵件] 資料夾。|
|`DI=SN`|已透過標準輸出傳遞集區路由傳送郵件。|
|`DI=SO`|已透過較高風險傳遞集區路由傳送郵件。 如需詳細資訊，請參閱[外寄郵件的較高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)。|
|`SFS=[a]|SFS=[b]`|這表示已符合垃圾郵件規則。|
|`IPV=CAL`|因為 IP 位址指定於連線篩選的 [IP 允許] 清單中，所以已透過垃圾郵件篩選允許郵件。|
|`H=<EHLOstring>`|連線電子郵件伺服器的 HELO 或 EHLO 字串。|
|`PTR=<ReverseDNS>`|傳送 IP 位址 (也稱為反向 DNS 位址) 的 PTR 記錄。|
|

篩選出垃圾郵件之郵件的 **custom_data** 範例值，例如：

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>惡意程式碼篩選代理程式

以 `S:AMA` 做為開頭的 **custom_data** 值是來自惡意程式碼篩選器代理程式。 下表說明重要的詳細資料：

****

|值|描述|
|---|---|
|`AMA=SUM|v=1|` 或 `AMA=EV|v=1`|郵件已判定為包含惡意程式碼。 `SUM` 表示任意數目的引擎可能已偵測到惡意程式碼。 `EV` 表示特定引擎偵測到惡意程式碼。 引擎偵測到惡意程式碼時，這會觸發後續動作。|
|`Action=r`|已取代郵件。|
|`Action=p`|已略過郵件。|
|`Action=d`|已延遲郵件。|
|`Action=s`|已刪除郵件。|
|`Action=st`|已略過郵件。|
|`Action=sy`|已略過郵件。|
|`Action=ni`|已拒絕郵件。|
|`Action=ne`|已拒絕郵件。|
|`Action=b`|已封鎖郵件。|
|`Name=<malware>`|偵測到之惡意程式碼的名稱。|
|`File=<filename>`|含有惡意程式碼之檔案的名稱。|
|

內含惡意程式碼之郵件的 **custom_data** 範例值看起來像這樣：

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>傳輸規則代理程式

以 `S:TRA` 作為開頭的 **custom_data** 值是來自郵件流程規則 (也稱為傳輸規則) 的傳輸規則代理程式。 下表說明重要的詳細資料：

****

|值|描述|
|---|---|
|`ETR|ruleId=<guid>`|已符合的規則 ID。|
|`St=<datetime>`|規則相符時的日期和時間 (以 UTC 表示)。|
|`Action=<ActionDefinition>`|已套用的動作。 如需可用動作的清單，請參閱 [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。|
|`Mode=<Mode>`|規則的模式。 有效值為：<ul><li>**強制**：將強制執行規則上的所有動作。</li><li>搭配 **原則提示來測試：**：將會傳送任何原則提示動作，但不會處理其他強制執行動作。</li><li>**無原則提示的測試**：動作將會列在記錄檔中，但是不會以任何方式通知寄件者，而且不會處理強制執行動作。</li></ul>|
|

符合郵件流程規則條件之郵件的 **custom_data** 範例值看起來像這樣：

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
