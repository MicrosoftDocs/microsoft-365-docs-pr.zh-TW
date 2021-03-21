---
title: 裝置需求
description: 與 Microsoft 受管理的電腦搭配使用之裝置的最低硬體和軟體需求摘要
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18422f74d87bbadf014de24849235ce5c25bd614
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920465"
---
# <a name="device-requirements"></a>裝置需求

Microsoft 受管理的桌面會定期評估服務中要包含的裝置需求。 本文說明裝置為了與 Microsoft 受管理的桌面搭配使用，必須符合的硬體和軟體需求。 您可以根據這些需求，複查 [已核准](device-list.md) 供服務使用的特定裝置清單。

> [!NOTE]
> 這些需求可以隨時變更，但我們會在任何硬體需求變更後提供30天的通知。 最近變更的需求會以標記 **\*** 。 

## <a name="check-hardware-requirements"></a>檢查硬體需求

除了檢查裝置規格之外，您也可以使用可下載的 [準備情況評估檢查](../get-ready/readiness-assessment-downloadable.md) 程式，以確認指定的裝置符合必要的需求。 此工具也會檢查服務運作所需的網路設定和端點。

## <a name="minimum-requirements"></a>基本需求

若要在 Microsoft 受管理的桌上型電腦註冊，裝置必須符合或超過所有這些需求。

### <a name="manufacturer"></a>製造商

裝置必須由下列其中一個製造商進行：

- 戴爾
- 惠普
- 聯想
- 微軟


### <a name="installed-software"></a>已安裝軟體

裝置必須預先安裝此軟體：

- Windows 10 企業版、專業版或專業版工作站版
- Microsoft Office 隨選即用的64位版本 
- 所有適用的裝置驅動程式


### <a name="physical-features"></a>實體功能

裝置必須具備下列功能：

- 啟用 UEFI 安全引導 
- 受信任的平臺模組2。0 
- 具備虛擬化的安全性 
- 支援管理程式保護的程式碼完整性 

如需這些功能及服務所使用之相關技術的詳細資訊，請參閱 [Microsoft 受管理的桌面技術](../intro/technologies.md)。

> [!NOTE]
> 不支援 ARM 處理器。

裝置應該符合或超過下列儲存區和記憶體的限制：

- 啟動磁片磁碟機必須是硬碟以外的任何類型。 例如，SSD、NVMe 和 eMMC 磁片磁碟機都是有效的選擇。
- 啟動磁片磁碟機必須具有至少 128 GB 的容量。
- 內部裝置記憶體 (RAM) 必須等於或超過 8 GB。

如果裝置是在2020年6月1日之後進行，也應同時有紅外相機、指紋辨識器或兩者，以便支援 [Windows Hello](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)。

## <a name="recommended-requirements"></a>建議的需求

雖然這不是絕對的需求，但如果您選擇具備這些功能的裝置，您的使用者將有更好的體驗：

- Intel vPro 平臺處理器或 AMD Ryzen Pro 處理器
- SSD 類型的啟動磁片磁碟機，其容量至少為 256 GB
- 支援新式待命
- 裝置屬於安全核心電腦類型
- 支援內核 DMA 保護