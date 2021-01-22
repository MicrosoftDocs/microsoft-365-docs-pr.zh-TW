---
title: 可下載的備應評定檢查程式
description: 檢查裝置和網路設定，包括所需的端點
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921939"
---
# <a name="downloadable-readiness-assessment-checker"></a>可下載的備應評定檢查程式

若要順利使用 Microsoft 受管理的桌面，裝置必須符合硬體和設定的某些需求。 此外，每個裝置必須能夠到達關鍵端點。 下載並執行此工具以取得 HTML 報告、查看結果，然後採取行動。 您必須下載工具和支援檔案，然後在您想要註冊 Microsoft 管理桌面的每個裝置上手動執行。

工具會針對每項檢查報告三種可能的結果之一：


|結果  |意義  |
|---------|---------|
|就緒     | 完成註冊之前，無需執行任何動作。        |
|諮詢    | 請遵循工具中的步驟，為註冊和使用者提供最佳使用體驗。 您可以 *完成* 註冊，但必須在部署第一個裝置之前修正這些問題。        |
|未就緒 | *如果您沒有修正這些問題* ，註冊將會失敗。 請遵循工具中的步驟來解決問題。        |

## <a name="obtain-the-checker"></a>取得檢查程式

下載 .zip 檔案 https://aka.ms/mmddratoolv0 。

> [!NOTE]
> 執行工具的使用者必須在執行此工具的裝置上擁有當地系統管理員許可權。

 然後按照下列步驟執行工具：

1. 將下載的 .zip 檔案複製到每個要檢查的裝置。
2. 解壓縮下載中所有的檔案。
3. 執行 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe。**
4. 出現使用者存取控制提示時， **請選取是**。 這項工具會隨即在預設瀏覽器中執行並開啟報表。

您也可以將 .zip 存檔下載並解壓縮到共用位置，Microsoft.MMD.DeviceReadinessAssessmentTool.exe裝置存取檔案，然後在當地執行。


## <a name="checks"></a>檢查

可下載的工具會檢查這些裝置和網路相關專案：

### <a name="hardware"></a>硬體

裝置必須符合特定硬體需求，以使用 Microsoft Managed Desktop。 目前僅允許特定 [核准的](../service-description/device-list.md) 裝置註冊。 

如果您的裝置未通過任何檢查，就與 Microsoft Managed Desktop 不相容。

### <a name="network-endpoints"></a>網路端點

裝置能連接到數 [個金鑰](network.md) 端點，以使用 Microsoft Managed Desktop。

如果工具報告尚未 **就緒** 的結果，請參閱詳細報告，瞭解哪些端點無法連接。 然後調整防火牆或其他網路設定，以確保可以連接到這些端點。

### <a name="other-settings"></a>其他設定

#### <a name="enterprise-wi-fi-profiles"></a>企業 Wi-Fi 設定檔

建議 **結果** 表示您目前使用一些需要憑證及設定檔的 Wi-Fi 設定檔，以正常運作。 有關詳細資訊，請參閱 [部署憑證和 Wi-Fi/VPN 設定檔](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。

#### <a name="lan-profiles"></a>LAN 設定檔

建議 **結果** 表示您擁有需要憑證及設定檔的 LAN，以正常運作。 有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。

#### <a name="vpn-profiles"></a>VPN 設定檔

建議 **結果** 表示您目前使用 VPN (私人網路) 。 建立部署與 Microsoft Intune 整合之憑證的 VPN 設定檔。 有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。

#### <a name="mapped-drives"></a>對應磁片磁碟機

建議 **結果** 表示您擁有一些對應磁片磁碟機，這是不建議的。 有關詳細資訊，請參閱 [準備適用于 Microsoft Managed Desktop 的對應磁片磁碟機](mapped-drives.md)。

#### <a name="print-queues"></a>列印佇列

建議 **結果** 表示您有一些未付的列印佇列，這是不建議的。 其中一個解決方案是使用雲端列印。 有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的列印資源](printing.md)。

#### <a name="proxies"></a>代理

建議 **結果** 表示您擁有使用中的 Proxy 伺服器。 詳細資訊請參閱 Microsoft [Managed Desktop 的網路組配置](network.md)。

