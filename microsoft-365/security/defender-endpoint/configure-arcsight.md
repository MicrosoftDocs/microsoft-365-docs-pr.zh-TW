---
title: 設定微焦點 ArcSight 以拉入 Microsoft Defender for Endpoint 偵測
description: 設定從 Microsoft Defender 資訊安全中心接收及提取偵測的微焦點 ArcSight
keywords: 設定微焦點 ArcSight、安全性資訊和事件管理工具、ArcSight
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
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166182"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>設定微焦點 ArcSight 以拉入 Defender for Endpoint 偵測

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

您將需要安裝及設定部分檔案和工具，以使用微型焦點 ArcSight，以便讓其能夠拉入 Defender 以進行端點偵測。

>[!Note]
>- 從一或多個偵測中組成[的 Defender For Endpoint Alert](alerts.md)
>- [Endpoint 偵測的 Defender](api-portal-mapping.md) 是由裝置上發生的可疑事件及其相關警示詳細資料所組成。

## <a name="before-you-begin"></a>開始之前

設定微型聚焦 ArcSight Connector 工具需要數個設定檔，才能從您的 Azure Active Directory (AAD) 應用程式中拉入和分析偵測。

本節會引導您取得正確設定及使用必要設定檔的必要資訊。

- 請確認您已從 **設定** 功能表啟用 SIEM 整合功能。 如需詳細資訊，請參閱 [ENABLE SIEM integration In Defender For Endpoint](enable-siem-integration.md)。

- 讓您儲存的檔案啟用 SIEM 整合功能。 您必須取得下列值：
  - OAuth 2.0 Token 重新整理 URL
  - OAuth 2.0 用戶端識別碼
  - OAuth 2.0 用戶端密碼

- 已準備好下列設定檔：
  - WDATP-連接器。屬性
  - WDATP-connector.jsonparser 屬性

    當您選擇微焦點 ArcSight 做為您在組織中使用的 SIEM 類型時，您就會儲存一個包含這兩個檔案的 .zip 檔案。

- 請確定您產生下列標記並準備好：
  - 存取權杖
  - 重新整理權杖

  您可以從入口網站的 [ **SIEM 整合** 設定] 區段中產生這些權杖。

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>安裝和設定微型焦點 ArcSight FlexConnector

下列步驟假設您已在 [開始之前](#before-you-begin)完成所有必要步驟。

1. 安裝最新的32位 Windows FlexConnector 安裝程式。 您可以在 HPE 軟體中心找到這種情況。 工具通常安裝在下列預設位置： `C:\Program Files\ArcSightFlexConnectors\current\bin` 。</br></br>您可以選擇儲存工具的位置，例如 C： \\ *folder_location*\current\bin，其中 *folder_location* 代表安裝位置。

2. 依照下列工作執行安裝精靈：
   - 簡介
   - 選擇 [安裝資料夾]
   - 選擇安裝集
   - 選擇快捷方式資料夾
   - 安裝前摘要
   - 安裝。。。

   您可以保留每個任務的預設值，或修改選取範圍以符合您的需求。

3. 開啟 [檔案瀏覽器]，並找到啟用 SIEM 整合功能時所儲存的兩個設定檔。 將這兩個檔案放在 FlexConnector 安裝位置，例如：

   - WDATP-connector.jsonparser。屬性： C： \\ *folder_location*\current\user\agent\flexagent\

   - WDATP-連接器。屬性： C： \\ *folder_location*\current\user\agent\flexagent\

   > [!NOTE]
   > 
   > 您必須將設定檔放在此位置，其中 *folder_location* 代表您安裝工具的位置。

4. 在核心連接器安裝完成後，[連接器設定] 視窗隨即開啟。 在 [連接器設定] 視窗中，選取 [ **新增連接器**]。

5. 選取 [類型： **ArcSight FLEXCONNECTOR REST** ]，然後按 **[下一步]**。

6. 在 [參數詳細資料] 表單中輸入下列資訊。 表單中的所有其他值都是選用的，而且可以保留空白。

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th>欄位</th>
    <th>值</th>
    </tr>
    <tr>
    <td>設定檔</td>
    <td>輸入用戶端屬性檔的名稱。 此名稱必須符合您所下載的 .zip 所提供的檔案。
例如，如果 flexagent 目錄中的配置 &quot; 檔 &quot; 命名為 &quot;WDATP-Connector.jsonparser 屬性 &quot; ，您必須輸入 &quot; WDATP 連接器 &quot; 做為用戶端屬性檔案名的名稱。</td>
    </tr>
    <td>事件 URL</td>
    <td>根據資料中心的位置，選取歐盟或 US URL: </br></br> <b>適用于 EU</b>： HTTPs:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc = $START _AT_TIME <br>
   </br><b>美國：</b> HTTPs:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc = $START _AT_TIME <br> <br> 若<b>為 UK</b>： HTTPs:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc = $START _AT_TIME</td>
    <tr>
    <td>驗證類型</td>
    <td>OAuth 2</td>
    </tr>
    <td>OAuth 2 用戶端屬性檔</td>
    <td>流覽至 <em>wdatp-connector</em> 的位置。 此名稱必須符合您所下載的 .zip 所提供的檔案。</td>
    <tr>
    <td>重新整理權杖</td>
    <td>您可以透過兩種方式取得重新整理權杖：透過從 [ <b>SIEM 設定</b> ] 頁面產生重新整理權杖，或使用 restutil 工具來取得更新。 <br><br> 如需從 <b>偏好設定</b> 中產生重新整理權杖的詳細資訊，請參閱 <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration In Defender for Endpoint</a>。 </br> </br><b>使用 restutil 工具取得您的重新整理權杖：</b> </br> a. 開啟命令提示字元。 流覽至 C：\<em>folder_location</em>\current\bin，其中 <em>folder_location</em> 代表您安裝工具的位置。 </br></br> b. 類型： <code>arcsight restutil token -config</code> 從 bin 目錄。例如： <b>arcsight restutil boxtoken-proxy proxy.location.hp.com:8080</b> 隨即會開啟網頁瀏覽器視窗。 </br> </br>c. 輸入您的認證，然後按一下 [密碼] 欄位，讓頁面重新導向。 在 [登入] 提示中，輸入您的認證。 </br> </br>d. 重新整理權杖會顯示在命令提示字元中。 </br></br> e. 複製並貼到 [重新整理 <b>權杖</b> ] 欄位。
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. 由連接器開啟瀏覽器視窗。 使用您的應用程式認證登入。 登入後，系統會要求您將許可權授與您的 OAuth2 用戶端。 您必須授與 OAuth 2 用戶端的許可權，讓連接器設定可以進行驗證。

   如果 <code>redirect_uri</code> 是 HTTPS URL，則會重新導向至本機主機上的 URL。 您會看到一個頁面，要求您信任本機主機上執行之連接器所提供的憑證。 如果 redirect_uri 為 HTTPs，您必須信任此憑證。
   
   不過，如果您指定 redirect_uri 的 HTTP URL，則不需要在信任憑證時提供同意。

8. 透過返回 [微焦點 ArcSight Connector Setup] 視窗，繼續執行連接器設定。

9. 選取 **ArcSight 管理員 (加密)** 做為目的地，然後按 **[下一步]**。

10. 在 **管理員主機名稱** 中輸入目的地 IP/主機名稱，並在 [參數] 表單中輸入您的認證。 表單中的所有其他值都應該以預設值保留。 按 [下一步 **]**。

11. 在 [連接器詳細資料] 表單中輸入連接器的名稱。 表單中的所有其他值都是選用的，而且可以保留空白。 按 [下一步 **]**。

12. [ESM 管理員匯入憑證] 視窗會顯示。 選取 **[將憑證匯入連接器從目的地** ]，然後按 **[下一步]**。 隨即會顯示 [ **新增連接器摘要** ] 視窗，並匯入該憑證。

13. 確認 [ **新增連接器摘要** ] 視窗中的詳細資訊正確無誤，然後按 **[下一步]**。

14. 選取 [ **安裝為服務** ]，然後按 **[下一步]**。

15. 在 [ **服務內部名稱** ] 欄位中輸入名稱。 表單中的所有其他值都可以保留預設值或保留空白。 按 [下一步 **]**。

16. 輸入服務參數，然後按 **[下一步]**。 顯示「 **安裝服務摘要** 」的視窗。 按 [下一步 **]**。

17. **選取 [** 結束] 和 **[下一步**]，完成安裝。

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>安裝和設定微型焦點 ArcSight 主控台

1. 依照下列工作執行安裝精靈：
   - 簡介
   - 授權合約
   - 特殊注意事項
   - 選擇 [ArcSight 安裝目錄]
   - 選擇快捷方式資料夾
   - 安裝前摘要

2. 按一下 **[安裝]**。 安裝完成之後，ArcSight 主控台設定向導隨即開啟。

3. 在 manager 的 [ **主機名稱** ] 和 8443 **In** **[下一步]** 中輸入 localhost。

4. 選取 [ **使用直接** 連線]，然後按 **[下一步]**。

5. 選取 [ **基於密碼的驗證**]，然後按 **[下一步]**。

6. 選取 [ **這是單一使用者安裝。 (建議)**]，然後按 **[下一步]**。

7. 按一下 [ **完成] 結束** 安裝程式。

8. 登入微焦 ArcSight 主控台。

9. 流覽至 [**現用通道集**]  >  **新的條件**  >  **裝置**  >  **裝置產品**。

10. 設定 **裝置產品 = Microsoft Defender ATP**。 當您驗證事件已流過工具時，請停止此程式，然後移至 Windows 服務]，然後啟動 ArcSight FlexConnector REST。

您現在可以在 [微焦點 ArcSight] 主控台中執行查詢。

Endpoint 偵測的 Defender 會顯示為獨立的事件，並使用 "Microsoft" 作為廠商，而 "Windows Defender ATP" 為裝置名稱。


## <a name="troubleshooting-micro-focus-arcsight-connection"></a>疑難排解微型聚焦 ArcSight connection

**問題：** 無法重新整理權杖。 您可以在 C： folder_location \current\logs 中找到記錄檔 \\ **， *folder_location* 代表安裝此工具的位置。 開啟 _代理程式 .log_ 和尋找 `ERROR/FATAL/WARN` 。

**症狀：** 您會收到下列錯誤訊息：

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**解決 方案：**

1. 按一下 [連接器] 視窗上的 [Ctrl+C]，以停止此程式。 當要求「終止批次處理工作 Y/N？」時，請按一下 **Y** 。

2. 流覽至儲存 WDATP-connector 的資料夾，然後編輯該檔案，以新增下列值： `reauthenticate=true` 。

3. 執行下列命令，以重新開機連接器： `arcsight.bat connectors` 。

   瀏覽器視窗隨即出現。 允許它執行，應該會消失，連接器現在應該正在執行。

> [!NOTE]
> 請停止此程式，以確認連接器是否正在執行。 然後再啟動連接器，不應出現瀏覽器視窗。

## <a name="related-topics"></a>相關主題
- [在 Defender for Endpoint 中啟用 SIEM 整合](enable-siem-integration.md)
- [向 SIEM 工具提取偵測](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [使用 REST API 的端點偵測的拉取 Defender](pull-alerts-using-rest-api.md)
- [為 SIEM 工具整合問題疑難排解](troubleshoot-siem.md)
