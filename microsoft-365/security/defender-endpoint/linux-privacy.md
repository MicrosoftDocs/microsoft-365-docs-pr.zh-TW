---
title: Linux 上的 Microsoft Defender for Endpoint 的隱私權
description: 隱私權控制，如何設定會影響隱私權的原則設定，以及在 Linux 上為端點所收集之診斷資料的相關資訊。
keywords: microsoft、defender、Microsoft Defender for Endpoint、linux、隱私權、診斷
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4be0960e8ba868df2acb313b171a08f667c287a7
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651329"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-linux"></a>Linux 上的 Microsoft Defender for Endpoint 的隱私權

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft 致力於為您提供您所需的資訊和控制，讓您選擇如何在 Linux 上使用 Defender for Endpoint 時收集和使用資料。

本主題說明產品內可用的隱私權控制，如何使用原則設定管理這些控制項，以及收集的資料事件的詳細資料。

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-linux"></a>在 Linux 上的 Microsoft Defender for Endpoint 中取得隱私權控制的概覽

本節說明在 Linux 上的 Defender for Endpoint 所收集的不同資料類型的隱私權控制。

### <a name="diagnostic-data"></a>診斷資料

診斷資料是用來將 Defender 設定為安全和更新、偵測、診斷和修正問題，也可讓產品改進。

某些診斷資料為必要，而某些診斷資料為選用。 我們可讓您選擇要透過隱私權控制 (如組織的原則設定) 向我們傳送必要或選用的診斷資料。

您可以選擇下列兩個適用于 Defender 的 Defender 用戶端軟體層級診斷資料。

* **必要**：必要的資料，以協助讓 Defender 保持在最新狀態，並且在安裝此裝置的裝置上如期執行。

* **選用**：其他資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷和修正問題。

根據預設，只會將所需的診斷資料傳送給 Microsoft。

### <a name="cloud-delivered-protection-data"></a>雲端已傳送保護資料

雲端提供的保護功能可讓您在存取雲端中的最新保護資料時，提供更快且更快速的保護。

啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和網路上的惡意程式碼提供重要防護。

### <a name="sample-data"></a>資料範例

範例資料是用來改善產品的保護功能，方法是傳送 Microsoft 可疑的範例，使其能夠進行分析。 啟用自動範例提交是選用的。

有三個層級可用於控制範例提交：

- **None**：沒有可疑的範例提交給 Microsoft。
- **安全**：只有不含個人身分識別資訊 (PII) 的可疑範例會自動提交。 此為此設定的預設值。
- **All**：將所有可疑的範例提交給 Microsoft。

## <a name="manage-privacy-controls-with-policy-settings"></a>使用原則設定管理隱私權控制項

如果您是 IT 管理員，您可能會想要在企業層級設定這些控制項。 

在 [Linux 上的 Defender For Endpoint 的 [設定偏好設定](linux-preferences.md)] 中，詳細說明上述各節所述各類資料的隱私權。

就像任何新的原則設定一樣，您應該在有限的受控環境中仔細測試這些設定，以確保您設定的設定在您的組織中更廣泛地實施原則設定之前具有適當的效果。

## <a name="diagnostic-data-events"></a>診斷資料事件

本節說明什麼是被視為必要的診斷資料，以及哪些專案會被視為選用的診斷資料，以及所收集的事件及欄位的描述。

### <a name="data-fields-that-are-common-for-all-events"></a>所有事件通用的資料欄位
有一些事件的相關資訊是所有事件通用，而不論類別或資料子類型為何。 

下欄欄位對於所有事件都是常見的：

| 欄位                   | 描述 |
| ----------------------- | ----------- |
| 平台                | 應用程式執行所在平臺的廣泛分類。 可讓 Microsoft 識別可能發生問題的平臺，使其可正確地設定優先順序。 |
| machine_guid            | 與裝置相關聯的唯一識別碼。 可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。 |
| sense_guid              | 與裝置相關聯的唯一識別碼。 可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。 |
| org_id                  | 與裝置所屬之企業相關聯的唯一識別碼。 可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目。 |
| 主機 名                | 本機裝置名稱 (，但沒有 DNS 尾碼) 。 可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。 |
| product_guid            | 產品的唯一識別碼。 可讓 Microsoft 區分影響不同產品風格的問題。 |
| app_version             | Linux 應用程式的 Defender for Endpoint 版本。 可讓 Microsoft 找出顯示問題的產品版本，使其可正確地設定優先順序。|
| sig_version             | 安全性情報資料庫的版本。 可讓 Microsoft 找出顯示問題的安全性情報版本，使其可正確地設定優先順序。 |
| supported_compressions  | 例如，應用程式支援的壓縮演算法清單 `['gzip']` 。 可讓 Microsoft 瞭解哪些類型的 compressions 可以在與應用程式通訊時使用。 |
| release_ring            | 裝置與 (相關聯的環，例如，內幕人士快、內幕人士緩慢、實際執行) 。 可讓 Microsoft 識別可能發生問題的發行環，使其可正確地設定優先順序。 |

### <a name="required-diagnostic-data"></a>必要診斷資料

必要的 **診斷資料** 是必要的最少資料，以協助讓 Defender 保持在最新狀態，並且在安裝此裝置的裝置上如期執行。

必要的診斷資料可協助識別可能與裝置或軟體設定有關的 Microsoft Defender 端點相關問題。 例如，它可協助判斷在特定作業系統版本、新引進的功能，或停用特定的 Defender 功能時，是否要讓 Defender for Endpoint 功能的情況更頻繁地崩潰。 必要的診斷資料可協助 Microsoft 偵測、診斷及修正這些問題，以加快對使用者或組織的影響。

#### <a name="software-setup-and-inventory-data-events"></a>軟體安裝和庫存資料事件

**Microsoft Defender for Endpoint 安裝/卸載**

下列是收集的欄位：

| 欄位            | 描述 |
| ---------------- | ----------- |
| correlation_id   | 與安裝相關聯的唯一識別碼。 |
| 版本          | 套件的版本。 |
| 嚴重性         | 郵件的嚴重性 (例如，) 的資訊。 |
| code             | 描述工序的程式碼。 |
| 文字             | 產品安裝相關的其他資訊。 |

**適用於端點的 Microsoft Defender 設定**

下列是收集的欄位：

| 欄位                                               | 描述 |
| --------------------------------------------------- | ----------- |
| antivirus_engine antivirus_engine.enable_real_time_protection        | 是否已在裝置上啟用即時保護功能。 |
| antivirus_engine antivirus_engine.passive_mode                       | 是否已在裝置上啟用被動式模式。 |
| cloud_service。 enabled                               | 是否已在裝置上啟用雲端已傳送保護功能。 |
| cloud_service。超時                               | 當應用程式與 Endpoint cloud 的 Defender 進行通訊時超時。 |
| cloud_service cloud_service.heartbeat_interval                    | 產品傳送至雲端的連續心跳之間的間隔。 |
| cloud_service cloud_service.service_uri                           | 用於與雲端通訊的 URI。 |
| cloud_service cloud_service.diagnostic_level                      | 裝置的診斷層級 (必要，選用) 。 |
| cloud_service cloud_service.automatic_sample_submission           | 裝置的自動範例提交層級 (無，安全，所有) 。 |
| cloud_service cloud_service.automatic_definition_update_enabled   | 是否已開啟自動定義更新。 |
| edr.early_preview                                   | 裝置是否應該執行 EDR 早期預覽功能。 |
| edr.group_id                                        | 偵測及回應元件所使用的群組識別碼。 |
| edr 標記                                            | 使用者定義的標記。 |
| 功能。 \[選用功能名稱\]                  | 預覽功能的清單，及其是否已啟用。 |

#### <a name="product-and-service-usage-data-events"></a>產品和服務使用資料事件

**安全性智慧更新報告**

下列是收集的欄位：

| 欄位            | 描述 |
| ---------------- | ----------- |
| from_version     | 原始安全性智慧版本。 |
| to_version       | 新的安全性智慧版本。 |
| 地位           | 表明成功或失敗之更新的狀態。 |
| using_proxy      | 是否已透過 proxy 進行更新。 |
| 錯誤            | 如果更新失敗，則為錯誤碼。 |
| reason           | 更新失敗時的錯誤訊息。 |

#### <a name="product-and-service-performance-data-events"></a>產品和服務效能資料事件

**內核擴充統計資料**

下列是收集的欄位：

| 欄位            | 描述 |
| ---------------- | ----------- |
| 版本          | Linux 上端點的版本。 |
| instance_id      | 在內核擴充啟動時產生的唯一識別碼。 |
| trace_level      | 內核擴充的追蹤層級。 |
| 子系統        | 用於即時保護的底層子系統。 |
| ipc。連接     | 內核擴充所接收的連線要求數目。 |
| ipc。拒絕      | 內核擴充所拒絕的連線要求數目。 |
| ipc。已連線    | 是否有任何作用中連接至內核分機。 |

#### <a name="support-data"></a>支援資料

**診斷記錄**

僅當使用者同意提交功能時，才會收集診斷記錄。 下列檔案會收集為支援記錄檔的一部分：

- */Var/log/microsoft/mdatp* 下的所有檔案
- 由 Linux 上的 Defender for Endpoint 所建立及使用之 */etc/opt/microsoft/mdatp* 底下的檔案子集
- */Var/log/microsoft_mdatp_ \* .log 中的* 產品安裝和卸載記錄

### <a name="optional-diagnostic-data"></a>選擇性診斷資料

**選用診斷資料** 是額外的資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷及修正問題。

如果您選擇將選用的診斷資料傳送給我們，則也會包含必要的診斷資料。

選用診斷資料的範例包括 Microsoft 收集有關產品設定 (的資料，例如，) 裝置上的排除專案數目，以及產品) 的元件效能 (匯總度量。

#### <a name="software-setup-and-inventory-data-events"></a>軟體安裝和庫存資料事件

**適用於端點的 Microsoft Defender 設定**

下列是收集的欄位：

| 欄位                                              | 描述 |
| -------------------------------------------------- | ----------- |
| connection_retry_timeout                           | 與雲端通訊時，連線重試超時。 |
| file_hash_cache_maximum                            | 產品快取的大小。 |
| crash_upload_daily_limit                           | 每天上傳的崩潰記錄檔限制。 |
| antivirus_engine。排除 [] .is_directory         | 掃描的排除是否為目錄。 |
| antivirus_engine。排除 [] 路徑                 | 排除在掃描之外的路徑。 |
| antivirus_engine。排除 [] 副檔名            | 排除來自掃描的分機號碼。 |
| antivirus_engine。排除 []。名稱                 | 排除在掃描之外的檔案名。 |
| antivirus_engine antivirus_engine.scan_cache_maximum                | 產品快取的大小。 |
| antivirus_engine antivirus_engine.maximum_scan_threads              | 掃描時所用的執行緒數目上限。 |
| antivirus_engine antivirus_engine.threat_restoration_exclusion_time | 在從隔離區還原的檔案之前，可再次偵測到超時。 |
| antivirus_engine antivirus_engine.threat_type_settings              | 產品如何處理不同威脅類型的設定。 |
| filesystem_scanner filesystem_scanner.full_scan_directory             | 完整掃描目錄。 |
| filesystem_scanner filesystem_scanner.quick_scan_directories          | 快速掃描中所用的目錄清單。 |
| edr.latency_mode                                   | 偵測及回應元件所使用的延遲模式。 |
| edr.proxy_address                                  | 偵測及回應元件所使用的 Proxy 位址。 |

**Microsoft 自動更新設定**

下列是收集的欄位：

| 欄位                       | 描述 |
| --------------------------- | ----------- |
| how_to_check                | 會決定如何檢查產品更新 (例如，自動或手動) 。 |
| channel_name                | 更新與裝置相關聯的通道。 |
| manifest_server             | 用於下載更新的伺服器。 |
| update_cache                | 用來儲存更新的快取位置。 |

### <a name="product-and-service-usage"></a>產品和服務使用

#### <a name="diagnostic-log-upload-started-report"></a>已開始診斷記錄上載報告

下列是收集的欄位：

| 欄位            | 描述 |
| ---------------- | ----------- |
| sha256           | 支援記錄檔的 SHA256 識別碼。 |
| Size             | 支援記錄檔的大小。 |
| original_path    | 支援記錄檔的路徑 (always 低於 */var/opt/microsoft/mdatp/wdavdiag/*) 。 |
| format           | 支援記錄檔的格式。 |

#### <a name="diagnostic-log-upload-completed-report"></a>診斷記錄上載已完成報告

下列是收集的欄位：

| 欄位            | 描述 |
| ---------------- | ----------- |
| request_id       | 支援記錄檔上載要求的相互關聯識別碼。 |
| sha256           | 支援記錄檔的 SHA256 識別碼。 |
| blob_sas_uri     | 應用程式用來上傳支援記錄的 URI。 |

#### <a name="product-and-service-performance-data-events"></a>產品和服務效能資料事件

**非預期的應用程式結束 (當機)**

非預期的應用程式結束，以及在該情況下應用程式的狀態。

**內核擴充統計資料**

下列是收集的欄位：

| 欄位                          | 描述 |
| ------------------------------ | ----------- |
| pkt_ack_timeout                | 下列屬性是匯總數值，代表自內核延伸啟動之後發生的事件計數。 |
| pkt_ack_conn_timeout             | |
| ipc.ack_pkts                     | |
| ipc.nack_pkts                    | |
| ipc.send.ack_no_conn             | |
| ipc.send.nack_no_conn            | |
| ipc.send.ack_no_qsq              | |
| ipc.send.nack_no_qsq             | |
| ipc.ack.no_space                 | |
| ipc ack。超時                  | |
| ipc.ack.ackd_fast                | |
| ackd                     | |
| ipc.recv.bad_pkt_len             | |
| ipc.recv.bad_reply_len           | |
| ipc.recv.no_waiter               | |
| ipc.recv.copy_failed             | |
| kauth vnode             | |
| vnode 讀取的 kauth             | |
| kauth vnode            | |
| ipc.kauth.vnode.exec             | |
| vnode kauth              | |
| ipc.kauth.vnode.read_attr        | |
| ipc.kauth.vnode.write_attr       | |
| ipc.kauth.vnode.read_ex_attr     | |
| ipc.kauth.vnode.write_ex_attr    | |
| ipc.kauth.vnode.read_sec         | |
| ipc.kauth.vnode.write_sec        | |
| ipc.kauth.vnode.take_own         | |
| ipc.kauth.vnode.link             | |
| vnode 建立 kauth           | |
| vnode 移動的 kauth             | |
| vnode 裝載 kauth            | |
| kauth 拒絕的 vnode           | |
| ipc.kauth.vnode.ackd_before_deadline | |
| ipc.kauth.vnode.missed_deadline  | |
| ipc.kauth.file_op 遮罩           | |
| ipc.kauth_file_op。開啟           | |
| ipc.kauth.file_op。關閉          | |
| ipc.kauth.file_op ipc.kauth.file_op.close_modified | |
| ipc.kauth.file_op。移動           | |
| ipc.kauth.file_op。連結           | |
| ipc.kauth.file_op.exec           | |
| ipc.kauth.file_op。移除         | |
| ipc.kauth.file_op。卸載        | |
| ipc.kauth.file_op 的派生           | |
| ipc.kauth.file_op。建立         | |

## <a name="resources"></a>資源

- [Microsoft 中的隱私權](https://privacy.microsoft.com/)
