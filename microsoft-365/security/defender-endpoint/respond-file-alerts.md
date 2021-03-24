---
title: 在 Microsoft Defender for Endpoint 中對檔案採取回應動作
description: 透過停止和隔離檔案，或封鎖檔案及檢查活動詳細資料，對檔相關警示採取回應動作。
keywords: 回應、停止和隔離、封鎖檔、深入分析
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ba48adcf93c5b768b2280729b33a1a7d361919cb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059359"
---
# <a name="take-response-actions-on-a-file"></a>對檔案採取回應動作

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-responddile-abovefoldlink)

停用或隔離檔案或封鎖檔案，以快速回應偵測到的攻擊。 對檔案採取動作後，您可以在「行動中心」中檢查活動詳細資料。

回應動作可用於檔案的詳細設定檔頁面面。 在此頁面上，您可以透過切換新的檔案 **頁面**，在新的和舊的頁面配置之間切換。 本文的其餘部分將說明較新的頁面配置。

回應動作會沿著檔案頁面頂端執行，並包括：

- 停止與隔離檔
- 新增指示器
- 下載檔案
- 諮詢威脅專家
- 控制中心

您也可以提交檔案進行深入分析，以在安全的雲端沙箱中執行檔案。 分析完成後，您將會收到提供檔案行為相關資訊的詳細報告。 您可以透過選取 [ **深入分析** ] 索引標籤，提交檔案以進行深入分析和舊報告讀取。它位於檔資訊卡片底下。

有些動作需要某些許可權。 下表說明某些許可權可對可遷移的可執行檔採取的動作 (PE) 和非 PE 檔案：

| 權限             | PE 檔案 | 非 PE 檔案 |
| :--------------------- | :------: | :----------: |
| 查看資料              |     X    |       X      |
| 警示調查   | &#x2611; |       X      |
| Live 回應基本    |     X    |       X      |
| 即時回應高級 | &#x2611; |   &#x2611;   |

如需角色的詳細資訊，請參閱 [建立與管理角色型存取控制的角色](user-roles.md)。

## <a name="stop-and-quarantine-files-in-your-network"></a>在您的網路中停止和隔離檔

您可以在您的組織中包含攻擊，方法是停止惡意程式，然後在觀察到的位置隔離該檔。

> [!IMPORTANT]
> 只有在下列情況中才能採取此動作：
>
> - 您正在執行該動作的裝置執行 Windows 10、版本1703或更新版本
> - 檔案不屬於受信任的協力廠商發行者，或未由 Microsoft 簽署
> - Microsoft Defender 防病毒至少必須以被動模式執行。 如需詳細資訊，請參閱 [Microsoft Defender 防毒程式相容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

**Stop 和隔離** 檔動作包括停止執行中的程式、隔離檔案，以及刪除持久性資料（例如登錄機碼）。

此巨集指令會在具有 Windows 10 版本1703或更新版本的裝置上生效，在過去30天內觀察到的檔案。

> [!NOTE]
> 您可以在任何時間從隔離區還原檔案。

### <a name="stop-and-quarantine-files"></a>停止和隔離檔

1. 選取您要停止和隔離的檔案。 您可以從下列任何視圖中選取檔案，或使用搜尋方塊：

   - **警示** -按一下專案時程表中的 [描述] 或 [詳細資料] 中對應的連結。
   - **搜尋框** **-從下拉式功能表** 中選取檔案，並輸入檔案名

   > [!NOTE]
   > Stop 和隔離檔動作的最大限制為1000裝置。 若要在大量的裝置上停止檔案，請參閱 [Add block to block 或 allow file](#add-indicator-to-block-or-allow-a-file)。

2. 移至頁首，然後選取 [ **停止] 和 [隔離** 檔]。

   ![Stop 和隔離檔動作的影像](images/atp-stop-quarantine-file.png)

3. 指定原因，然後選取 [ **確認**]。

   ![Stop 和隔離檔強制回應視窗的影像](images/atp-stop-quarantine.png)

   行動中心會顯示提交資訊：
   
   ![停止和隔離檔案動作中心的影像](images/atp-stopnquarantine-file.png)

   - **提交時間** -顯示何時提交動作。
   - **成功** -顯示已停止並隔離檔案的裝置數目。
   - **Failed** -顯示動作失敗的裝置數目，以及失敗的詳細資料。
   - **擱置** -顯示檔案尚未停用並從中隔離的裝置數目。 當裝置離線或未連接到網路時，可能需要一些時間。

4. 選取任何狀態指示器，以查看有關動作的詳細資訊。 例如，選取 [ **失敗** ] 以查看動作失敗的位置。

**在裝置使用者上的通知**：</br>
從裝置移除檔案時，會顯示下列通知：

![裝置使用者上的通知圖像](images/atp-notification-file.png)

在裝置時程表中，會為每個停用或隔離檔案的裝置新增一個新的事件。

在針對整個組織中廣泛使用的檔案實施動作之前，會顯示一則警告。 其主要是驗證作業的運作方式。

## <a name="restore-file-from-quarantine"></a>從隔離區還原檔案

如果您已決定在調查之後清除檔案，您可以從隔離區復原檔案並將其移除。 在隔離檔案的每個裝置上執行下列命令。

1. 在裝置上開啟已提升許可權的命令列提示：

   1. 轉至 **[開始]** 並鍵入 _「cmd」_。

   1. 以滑鼠右鍵按一下 [ **命令提示** 字元]，然後選取 [ **以管理員身分執行**]。

2. 輸入下列命令，然後按 **enter**：

   ```powershell
   “%ProgramFiles%\Windows Defender\MpCmdRun.exe” –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
   ```

> [!NOTE]
> 在某些情況下， **ThreatName** 可能會顯示為： EUS： Win32/CustomEnterpriseBlock！ cl。
>
> 在過去30天內，在此裝置上已隔離的所有自訂封鎖檔案都會還原為端點。

> [!IMPORTANT]
> 被隔離成可能網路威脅的檔案可能無法復原。 如果使用者嘗試在隔離後還原檔案，該檔案可能無法存取。 這可能是因為系統已無法再有存取該檔案的網路認證。 一般來說，這是暫時登入系統或共用資料夾，且存取權杖已到期的結果。

## <a name="download-or-collect-file"></a>下載或收集檔案

從回應動作選取 [ **下載** 檔案]，可讓您下載包含檔案的本機密碼保護 .zip 封存。 快顯視窗會出現，您可以在其中記錄下載檔案的原因，並設定密碼。

根據預設，您將無法下載隔離中的檔案。

![下載檔案動作的影像](images/atp-download-file-action.png)

### <a name="collect-files"></a>收集檔案

如果檔案尚未由 Microsoft Defender for Endpoint 儲存，則無法下載。 相反地，您會在相同位置看到 [ **收集** 檔案] 按鈕。 如果過去30天內沒有看到組織中的檔案，則會停用 **收集** 檔案。
> [!Important]
> 被隔離成可能網路威脅的檔案可能無法復原。 如果使用者嘗試在隔離後還原檔案，該檔案可能無法存取。 這可能是因為系統已無法再有存取該檔案的網路認證。 一般來說，這是暫時登入系統或共用資料夾，且存取權杖已到期的結果。

## <a name="add-indicator-to-block-or-allow-a-file"></a>新增指示器以封鎖或允許檔

Banning 潛在的惡意檔案或可疑惡意程式碼，以防止進一步傳播您組織中的攻擊。 如果您知道可能是惡意遷移的可執行檔 (PE) file，您可以將它封鎖。 此作業可防止在組織中的裝置上讀取、寫入或執行此作業。

> [!IMPORTANT]
>
> - 如果您的組織使用 Microsoft Defender 防病毒和雲端傳遞的保護功能，便可使用此功能。 如需詳細資訊，請參閱 [管理 cloud-已提供的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。
>
> - 反惡意軟體用戶端版本必須是4.18.1901 或更新版本。
> - 這項功能的設計是為了防止可疑的惡意程式碼 (或可能的惡意檔案) 從網頁下載。 它目前支援可遷移的可執行檔 (PE) 檔案（包括 _.exe_ 和 _.dll_ 檔案）。 覆蓋範圍會隨著時間擴充。
> - 此回應動作適用于 Windows 10 版本1703或更新版本上的裝置。
> - 如果檔案的分類存在於 allow 或封鎖動作之前，則無法在檔案上執行 allow 或 block 功能。

> [!NOTE]
> PE 檔案必須位於裝置時程表中，讓您能夠採取此動作。
>
> 在採取動作和實際封鎖的檔案之間，可能會有幾分鐘的延遲時間。

### <a name="enable-the-block-file-feature"></a>啟用封鎖檔功能

若要開始封鎖檔案，您必須先在 [設定] 中 [關閉 [ **封鎖] 或 [允許** ] 功能](advanced-features.md) 。
### <a name="allow-or-block-file"></a>允許或封鎖檔

當您為檔案新增指示器雜湊時，您可以選擇每當組織中的設備嘗試執行時，就會引發警示並封鎖檔案。

標記自動封鎖的檔案不會出現在檔案的動作中心，但提醒仍會顯示在 [警示] 佇列中。

請參閱 [管理](manage-indicators.md) 指標以取得封鎖和引發檔警示的詳細資料。

若要停止封鎖檔，請移除指標。 您可以透過檔案的 [設定檔] 頁面上的 [ **編輯指示器** ] 動作來執行此動作。 在新增指示器之前，此巨集指令會在 [ **新增指示器** ] 動作相同的位置上顯示。

您也可以從 [**設定**] 頁面的 [**規則** 指標] 底下編輯指示器  >  ****。 指示器會以檔案的雜湊列在此區域中。

## <a name="consult-a-threat-expert"></a>諮詢威脅專家

請參閱 Microsoft 威脅專家，以取得可能受損裝置或已受損裝置的更深入資訊。 Microsoft 威脅專家直接從 Microsoft Defender Security Center 內直接接洽，以取得及時且準確的回應。 專家對潛在的受損裝置提供深入瞭解，協助您瞭解複雜威脅及目標攻擊通知。 他們也可以提供您在入口網站儀表板上看到之警示或威脅情報內容的相關資訊。

如需詳細資訊，請參閱查看 [Microsoft 威脅專家](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) 。

## <a name="check-activity-details-in-action-center"></a>檢查重要訊息中心的活動詳細資料

「 **行動中心** 」提供對裝置或檔案所採取動作的資訊。 您可以查看下列詳細資料：

- 調查套件集合
- 防病毒掃描
- 應用程式限制
- 裝置隔離

也會顯示所有其他相關詳細資料，例如提交日期/時間、提交使用者，以及動作成功或失敗。

![包含資訊的動作中心影像](images/action-center-details.png)

## <a name="deep-analysis"></a>深入分析

網路安全性調查通常是由警示所觸發。 警示與一個或多個觀測到的檔案（通常是新的或未知的）有關。 選取檔案會帶您前往檔案視圖，您可以在其中看到檔案的中繼資料。 若要濃縮檔相關的資料，您可以提交檔案進行深層分析。

Deep analysis 功能會在安全且充分受充分規范的雲端環境中執行檔案。 深入分析結果會顯示檔案的活動、觀測的行為和相關聯的專案，例如：刪除的檔案、登錄修改以及與 IPs 的通訊。
深入分析目前支援可遷移的可執行檔 (PE) 檔案的廣泛分析 (包括 _.exe_ 和 _.dll_ 檔案) 。

檔案的深層分析需要數分鐘的時間。 檔案分析完成之後，[深入分析] 索引標籤將會更新，以顯示摘要及最新可用結果的日期和時間。

深入分析摘要包含觀測 *行為* 的清單，其中一些可能表示惡意活動和 *observables*，包括與磁片上建立的相互聯繫的 IPs 和檔案。 如果找不到任何專案，這些區段會顯示簡短訊息。

深入分析的結果會與威脅智慧相符，而且任何相符專案都會產生適當的警示。

使用「深入分析」功能，調查任何檔案的詳細資料，通常是在調查警示或您懷疑惡意行為的任何其他原因期間進行。 此功能可在 [ **深入分析** ] 索引標籤中，于檔案的 [設定檔] 頁面上。<br/>
<br/>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4aAYy?rel=0]

當檔案可用於「Defender for Endpoint」範例集合，或是在支援送出深入分析的 Windows 10 裝置上進行深入分析時，會啟用送出 **以進行深入分析**。

> [!NOTE]
> 只會自動收集來自 Windows 10 的檔案。

您也可以在 Windows 10 裝置上未觀察到檔案時，透過 [Microsoft Security Center 入口網站](https://www.microsoft.com/security/portal/submission/submit.aspx) 提交範例，並等候 [ **提交深入分析** ] 按鈕變為可用。

> [!NOTE]
> 由於 Microsoft Security Center 入口網站中的後端處理流程，在檔提交與更新的 Defender 中的「深入分析」功能之間可能有10分鐘的延遲。

收集樣本時，端點會在安全的環境中執行檔案。 然後，它會建立觀測行為和相關聯之專案的詳細報告，例如在裝置上丟棄的檔案、IPs 的通訊以及登錄修改。

### <a name="submit-files-for-deep-analysis"></a>提交檔案進行深入分析

1. 選取您要提交以進行深入分析的檔案。 您可以從下列任何一種視圖中選取或搜尋檔案：

    - 警示-從專案時程表的 **描述** 或 **詳細資料** 中選取檔連結
    - **裝置清單**-從 [**組織中裝置** 的 **描述** 或 **詳細資料**] 區段中選取檔連結。
    - 搜尋框 **-從下拉式功能表** 中選取檔案，並輸入檔案名

2. 在檔視圖的 [ **深入分析** ] 索引標籤中，選取 [ **提交**]。

   ![您只能在 [檔詳細資料] 區段中提交 PE 檔案。](images/submit-file.png)

   > [!NOTE]
   > 只支援 PE 檔案，包括 _.exe_ 和 _.dll_ 檔案。

隨即會顯示進度列，並提供分析的不同階段的資訊。 然後您就可以在分析完成時查看報告。

> [!NOTE]
> 根據裝置可用性而定，範例集合時間可能會不同。 範例集合的超時為 3-小時。 如果目前沒有線上 Windows 10 設備報告，此集合就會失敗，且作業會終止。 您可以重新提交檔案進行深入分析，以取得檔案的新資料。

### <a name="view-deep-analysis-reports"></a>查看深入分析報告

查看提供的深入分析報告，以查看您提交之檔案的更深入深入資訊。 您可以在檔案查看內容中使用此功能。

您可以在下列各節中查看提供詳細資料的綜合報告：

- Behaviors
- Observables

提供的詳細資料可協助您調查是否有潛在攻擊的跡象。

1. 選取您提交進行深層分析的檔案。
2. 選取 [ **深入分析** ] 索引標籤。如果有任何先前的報告，報表摘要將會出現在此索引標籤中。

    ![深入分析報告會顯示多個類別的詳細資訊](images/analysis-results-nothing500.png)

#### <a name="troubleshoot-deep-analysis"></a>深入分析疑難排解

如果您在嘗試提交檔案時遇到問題，請嘗試下列每個疑難排解步驟。

1. 確定有問題的檔案是 PE 檔案。 PE 檔案一般會有 _.exe_ 或 _.dll_ 副檔名 (可執行檔程式或應用程式) 。
2. 請確定服務具有存取權，但仍然存在且未損毀或修改的檔案。
3. 請稍等片刻，然後再次嘗試提交檔案。 佇列可能已滿，或發生暫時連線或通訊錯誤。
4. 若未設定範例集合原則，則預設行為為允許範例集合。 如果已設定，請確認原則設定允許範例集合，再提交檔案。 設定範例集合後，請檢查下列登錄值：

    ```powershell
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 – block sample collection
      Value = 1 – allow sample collection
    ```

1. 透過「群組原則」變更組織單位。 如需詳細資訊，請參閱 [Configure With Group Policy](configure-endpoints-gp.md)。
1. 如果這些步驟無法解決問題，請與 [winatp@microsoft.com](mailto:winatp@microsoft.com)聯繫。

## <a name="related-topics"></a>相關主題

- [在裝置上採取回應動作](respond-machine-alerts.md)
- [調查檔](investigate-files.md)
