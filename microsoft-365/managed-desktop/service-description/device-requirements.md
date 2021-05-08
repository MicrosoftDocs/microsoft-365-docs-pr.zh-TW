---
title: 裝置需求
description: 與 Microsoft 受管理的電腦搭配使用之裝置的基本硬體及軟體需求摘要
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: fcd7f192ba0846e3bf3051cde927095088f32d26
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245789"
---
# <a name="device-requirements"></a>裝置需求

Microsoft 受管理的電腦會定期評估服務中要包含的裝置需求。 本文說明裝置必須符合的硬體和軟體需求，才能與 Microsoft 受管理的電腦搭配使用。 您可以根據這些需求，複查已核准供服務使用的特定裝置清單。 [Windows 10 專業版商務裝置](https://www.microsoft.com/windowsforbusiness/view-all-devices)網站上的 Microsoft 受管理的電腦篩選

> [!NOTE]
> 這些需求可以隨時變更，但我們會在任何硬體需求變更後提供30天的通知。 最近變更的需求會以標記 **\*** 。 

## <a name="check-hardware-requirements"></a>檢查硬體需求

除了檢查裝置規格之外，您也可以使用可下載的 [準備情況評估檢查](../get-ready/readiness-assessment-downloadable.md) 程式，以確認指定的裝置符合必要的需求。 此工具也會檢查服務運作所需的網路設定和端點。

## <a name="minimum-requirements"></a>基本需求

若要在 Microsoft 受管理的電腦中註冊，裝置必須符合或超過所有這些需求。

### <a name="manufacturer"></a>製造商

裝置必須由下列其中一個製造商進行：

- 戴爾
- 惠普
- 聯想
- Microsoft


### <a name="installed-software"></a>已安裝軟體

裝置必須預先安裝此軟體：

- Windows 10 企業版、Pro 或 Pro Workstation edition
- 64位版本的 Microsoft 365 Apps 企業版 
- 所有適用的裝置驅動程式


### <a name="physical-features"></a>實體功能

裝置必須具備下列功能：

- 啟用 UEFI 安全引導 
- 受信任的平臺模組2。0 
- 具備虛擬化的安全性 
- [虛擬機器監控程式-BIOS 支援的受保護程式碼完整性](/windows-hardware/drivers/bringup/device-guard-and-credential-guard)

如需這些功能和服務所使用之相關技術的詳細資訊，請參閱[Microsoft 受管理的電腦技術](../intro/technologies.md)。

> [!NOTE]
> 不支援 ARM 處理器。

裝置應該符合或超過下列儲存區和記憶體的限制：

- 啟動磁片磁碟機必須是硬碟以外的任何類型。 例如，SSD、NVMe 和 eMMC 磁片磁碟機都是有效的選擇。
- 啟動磁片磁碟機必須具有至少 128 GB 的容量。
- 內部裝置記憶體 (RAM) 必須等於或超過 8 GB。

如果裝置是在2020年6月1日之後進行，也應同時有紅外相機、指紋辨識器或兩者，才能支援[Windows Hello](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)。

## <a name="recommended-features"></a>建議功能

如果您選擇具有這些功能的裝置，您的使用者將有更好的體驗：

- Intel vPro 平臺處理器或 AMD Ryzen Pro 處理器
- SSD 類型的啟動磁片磁碟機，其容量至少為 256 GB
- 內部裝置記憶體 (RAM) 至少 16 GB
- 支援新式待命
- 裝置屬於安全核心電腦類型
- 支援內核 DMA 保護
