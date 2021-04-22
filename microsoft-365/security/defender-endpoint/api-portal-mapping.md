---
title: Microsoft Defender for Endpoint 偵測 API 欄位
description: 瞭解偵測 API 欄位如何對應至 Microsoft Defender Security Center 中的值
keywords: 偵測、偵測欄位、欄位、api、欄位、提取偵測、rest api、要求、回應
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
ms.openlocfilehash: d6d2ad9abe88d0099b58dd2df486120082bb22c1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933634"
---
# <a name="microsoft-defender-for-endpoint-detections-api-fields"></a>Microsoft Defender for Endpoint 偵測 API 欄位

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-apiportalmapping-abovefoldlink)

瞭解哪些資料欄位會公開成為偵測 API 的一部分，以及它們如何對應至 Microsoft Defender Security Center。

>[!Note]
>- 已從一或多個偵測中所組成[的 Defender For Endpoint 警示](alerts.md)。
>- **Microsoft DEFENDER ATP 偵測** 是由裝置上發生的可疑事件及其相關 **警示** 詳細資料所組成。
>- Microsoft Defender for Endpoint Alert API 是最新的警示消耗 API，且包含每個警示的相關證據的詳細清單。 如需詳細資訊，請參閱 [Alert 方法和屬性](alerts.md) 和 [清單警示](get-alerts.md)。

## <a name="detections-api-fields-and-portal-mapping"></a>偵測 API 欄位及入口網站對應
下表列出偵測 API 負載中公開的可用欄位。 它會顯示已填入值的範例，以及資料在入口網站上的反映參照。

[ArcSight 欄位] 欄包含 ArcSight 中的 [在端點] 欄位及內建欄位之間的預設對應。 您可以在啟用 SIEM 整合功能時，從入口網站下載對應檔案，而且可以修改它以符合組織的需求。 如需詳細資訊，請參閱 [ENABLE SIEM integration In Defender For Endpoint](enable-siem-integration.md)。

域編號會符合下列圖像中的數位。

> [!div class="mx-tableFixed"]
> 
> | 入口網站標籤   | SIEM 功能變數名稱           | ArcSight 欄位      | 範例值                                                                      | 說明                                                                                                                                                                    |
> |------------------|---------------------------|---------------------|------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
> | 1                | AlertTitle                | name                | Microsoft Defender AV 偵測到 ' Mikatz ' 高嚴重性惡意程式碼 | 可供每個偵測使用的值。                                                                                                                                               |
> | 第                | 嚴重性                  | deviceSeverity      | 高                                                                             | 可供每個偵測使用的值。                                                                                                                                               |
> | 個                | 類別                  | deviceEventCategory | 惡意程式碼                                                               | 可供每個偵測使用的值。                                                                                                                                               |
> | 4                 | 偵測來源                    | sourceServiceName   | 防毒                                                                 | Microsoft Defender 防病毒或 Defender for Endpoint。 可供每個偵測使用的值。                                                                                         |
> | 5                 | MachineName               | sourceHostName      | 桌面4a5ngd6                                                                           | 可供每個偵測使用的值。                                                                                                                                               |
> | 6                 | FileName                  | 檔案名            | Robocopy.exe                                                                       | 可用於與檔案或處理常式相關聯的偵測。                                                                                                                      |
> | 7                 | FilePath                  | filePath            | C:\Windows\System32\Robocopy.exe                                                   | 可用於與檔案或處理常式相關聯的偵測。                                                                                                                     |
> | 8                 | UserDomain                | sourceNtDomain      | 尚未                                                                            | 執行活動之使用者內容的網域，可供 Defender 用於以 Endpoint 為基礎之行為的偵測。                                                           |
> | 9                 | UserName                  | sourceUserName      | liz bean                                                                           | 執行活動的使用者內容，可供使用 Defender 以進行基於端點行為的偵測。                                                                           |
> | 10                | Sha1                      | fileHash            | 3da065e07b990034e9db7842167f70b63aa5329                                           | 可用於與檔案或處理常式相關聯的偵測。                                                                                                                      |
> | 11                | Sha256                    | deviceCustomString6 | ebf54f745dc81e1958f75e4ca91dd0ab989fc9787bb6b0bf993e2f5                   | 可用於 Microsoft Defender AV 偵測。                                                                                                                                    |
> | 12                | Md5                       | deviceCustomString5 | db979c04a99b96d370988325bb5a8b21                                                   | 可用於 Microsoft Defender AV 偵測。                                                                                                                                    |
> | 13               | ThreatName                | deviceCustomString1  | HackTool： Win32/Mikatz！ dha                                                         | 可用於 Microsoft Defender AV 偵測。                                                                                                                                    |
> | 14                | 址                 | sourceAddress       | 218.90.204.141                                                                     | 可用於與網路事件關聯的偵測。 例如，「與惡意網路目的通訊」。                                                        |
> | 15                | URL                       | requestUrl          | down.esales360.cn                                                                  | 可用於與網路事件關聯的偵測。 例如，「與惡意網路目的通訊」。                                                         |
> | 16                | RemediationIsSuccess      | deviceCustomNumber2 | TRUE                                                                               | 可用於 Microsoft Defender AV 偵測。 當 TRUE 時，ArcSight 值為1，當為 FALSE 時則為0。                                                                                    |
> | 17                | WasExecutingWhileDetected | deviceCustomNumber1 | 假                                                                              | 可用於 Microsoft Defender AV 偵測。 當 TRUE 時，ArcSight 值為1，當為 FALSE 時則為0。                                                                                    |
> | 18                | 為 alertid                   | externalId          | 636210704265059241_673569822                                                       | 可供每個偵測使用的值。                                                                                                                                               |
> | 19               | LinkToWDATP               | flexString1         | `https://securitycenter.windows.com/alert/636210704265059241_673569822`            | 可供每個偵測使用的值。                                                                                                                                               |
> | 共               | AlertTime                 | deviceReceiptTime   | 2017-05-07T01：56： 59.3191352 Z                                                       | 事件發生的時間。 可供每個偵測使用的值。                                                                                       |
> |  21               | MachineDomain             | sourceDnsDomain     | contoso.com                                                                        | 不相關的 AAD 加入裝置的功能變數名稱。 可供每個偵測使用的值。                                                                                           |
> | 22               | 演員                     | deviceCustomString4 | 硼                                                                                   | 可用於與已知的主角群組相關的警示。                                                                                                                         |
> | 21 + 5             | ComputerDnsName           | 無對應          | liz-bean.contoso.com                                                               | 裝置完全限定的功能變數名稱。 可供每個偵測使用的值。                                                                                                    |
> |                  | LogOnUsers                | sourceUserId        | contoso\liz-bean;  contoso\jay-hardee                                             | 在事件發生時，互動式登入使用者的網域和使用者。 附注：針對 Windows 10 版本1607上的裝置，網域資訊將無法使用。 |
> |                  | InternalIPv4List          | 無對應          | 192.168.1.7, 10.1.14.1                                                             | 作用中網路介面的 IPV4 內部 Ip 清單。                                                                                                                                                                               |
> |                  | InternalIPv6List          | 無對應          | fd30：0000：0000：0001： ff4e：003e：0009：000e，FE80： CD00：0000：0CDE：1257：0000：211E：729C | 作用中網路介面的 IPV6 內部 Ip 清單。                                                                                                                                                                               |
| | LinkToMTP | 無對應 | `https://security.microsoft.com/alert/da637370718981685665_16349121` | 可供每個偵測使用的值。
| | IncidentLinkToMTP | 無對應 | `"https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | 可供每個偵測使用的值。
| | IncidentLinkToWDATP | 無對應 | `https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | 可供每個偵測使用的值。
> | 內部欄位 | LastProcessedTimeUtc      | 無對應          | 2017-05-07T01：56： 58.9936648 Z                                                       | 事件到達後端的時間。 在設定偵測偵測時間範圍的要求參數時，可以使用此欄位。                         |
> |                  | 不屬於架構    | deviceVendor        |                                                                                    | ArcSight 對應中的靜態值-"Microsoft"。                                                                                                                          |
> |                  | 不屬於架構    | deviceProduct       |                                                                                    | ArcSight 對應中的靜態值-"Microsoft Defender ATP"。                                                                                                               |
> |                  | 不屬於架構    | deviceVersion       |                                                                                    | ArcSight 對應中的靜態值-' 2.0 '，用來識別對應版本。                                                                                         


![具有數位的警示影像](images/atp-alert-page.png)

![具有數位的警示詳細資料窗格影像](images/atp-siem-mapping13.png)

![具有 numbers1 的專案時程表的圖像](images/atp-siem-mapping3.png)

![具有 numbers2 的專案時程表的圖像](images/atp-siem-mapping4.png)

![影像電腦視圖](images/atp-mapping6.png)

![影像瀏覽器 URL](images/atp-mapping5.png)

![圖像演員警示](images/atp-mapping7.png)


## <a name="related-topics"></a>相關主題
- [在 Microsoft Defender for Endpoint 中啟用 SIEM 整合](enable-siem-integration.md)
- [設定 ArcSight 以拉入 Microsoft Defender for Endpoint 偵測](configure-arcsight.md)
- [使用 REST API 提取 Microsoft Defender for Endpoint 偵測](pull-alerts-using-rest-api.md)
- [為 SIEM 工具整合問題疑難排解](troubleshoot-siem.md)
