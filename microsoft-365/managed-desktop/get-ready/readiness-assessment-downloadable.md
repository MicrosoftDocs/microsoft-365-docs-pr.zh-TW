---
title: 可下載的整備評估檢查程式
description: 檢查裝置和網路設定（包括必要的端點）
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581031"
---
# <a name="downloadable-readiness-assessment-checker"></a>可下載的整備評估檢查程式

裝置必須符合硬體和設定的特定需求，才能搭配 Microsoft 受管理的電腦運作。 此外，每個裝置都必須能夠到達機碼端點。 下載並執行此工具以取得 HTML 報告、查看結果，然後採取動作。 您將需要下載工具和支援檔案，然後在您要 Microsoft 受管理的電腦註冊的每一個裝置上手動執行。

針對每個檢查，該工具會報告三個可能結果中的其中一項：


|結果  |意義  |
|---------|---------|
|就緒     | 完成註冊之前，不需要執行任何動作。        |
|公告    | 請遵循工具中的步驟，以取得註冊和使用者的最佳體驗。 您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。        |
|未就緒 | 如果您未修正這些問題，*註冊將會失敗*。 請遵循工具中的步驟加以解決。        |

## <a name="obtain-the-checker"></a>取得檢查

從下載 .zip 檔案 https://aka.ms/mmddratoolv0 。

> [!NOTE]
> 執行工具的使用者必須具有其所執行之裝置上的本機系統管理員許可權。

 請遵循下列步驟來執行工具：

1. 將下載的 .zip 檔複製到您想要檢查的每一個裝置。
2. 解壓縮壓縮下載中的所有檔案。
3. 執行 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**。
4. 顯示使用者存取控制提示時，請選取 **[是]**。 工具會在您的預設瀏覽器中執行並開啟報表。

您也可以將 .zip 封存下載並解壓縮到共用位置，從每個裝置存取 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** ，然後在本機執行。


## <a name="checks"></a>檢查

可下載的工具會檢查這些裝置和網路相關專案：

### <a name="hardware"></a>硬體

裝置必須符合特定硬體需求，才能與 Microsoft 受管理的電腦搭配使用。 目前，只允許特定 [已核准的裝置](../service-description/device-list.md) 進行註冊。 

如果您的裝置失敗任何檢查，就不會與 Microsoft 受管理的電腦相容。

### <a name="network-endpoints"></a>網路端點

裝置很大可以到達數個[主要端點](network.md)，以與 Microsoft 受管理的電腦搭配使用。

若工具報告 **未就緒** 的結果，請參閱詳細報告以找出無法到達的端點。 然後調整您的防火牆或其他網路設定，以確保可以到達這些端點。

### <a name="other-settings"></a>其他設定

#### <a name="enterprise-wi-fi-profiles"></a>Enterprise wi-fi 設定檔

**建議** 結果表示您使用的某些 wi-fi 設定檔需要憑證和設定檔才能正常運作。 如需詳細資訊，請參閱 [部署憑證和 Wi-Fi/VPN 設定檔](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。

#### <a name="lan-profiles"></a>LAN 設定檔

**建議** 的結果表示您有需要憑證和設定檔才能正常運作的局域網。 如需詳細資訊，請參閱[為 Microsoft 受管理的電腦準備憑證和網路設定檔](certs-wifi-lan.md)。

#### <a name="vpn-profiles"></a>VPN 設定檔

**建議** 的結果表示您使用的是虛擬私人網路 (VPN) 。 建立 VPN 設定檔，以部署與 Microsoft Intune 整合的憑證。 如需詳細資訊，請參閱[為 Microsoft 受管理的電腦準備憑證和網路設定檔](certs-wifi-lan.md)。

#### <a name="mapped-drives"></a>對應磁片磁碟機

**建議** 結果表示您有一些對應的磁片磁碟機，不建議使用。 如需詳細資訊，請參閱為[Microsoft 受管理的電腦準備對應的磁片磁碟機](mapped-drives.md)。

#### <a name="print-queues"></a>列印佇列

**建議** 的結果表示您有一些尚未處理的列印佇列，不建議您這麼做。 一個解決方案是使用雲端列印。 如需詳細資訊，請參閱[準備列印資源以供 Microsoft 受管理的電腦](printing.md)。

#### <a name="proxies"></a>代理

**建議** 的結果表示您有使用 proxy 伺服器。 如需詳細資訊，請參閱[Microsoft 受管理的電腦的網路](network.md)設定。

