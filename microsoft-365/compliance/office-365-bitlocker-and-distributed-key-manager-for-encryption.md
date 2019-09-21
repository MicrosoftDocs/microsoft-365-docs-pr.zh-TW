---
title: Office 365 BitLocker 加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 摘要： BitLocker 加密定域機組中的資訊。
ms.openlocfilehash: bbe32f642f214d27c7f9f82c39b11237556d51bf
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077870"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker 與 Distributed Key Manager (DKM) 的加密

Office 365 伺服器使用 BitLocker 加密包含客戶資料磁碟區層級的靜態的磁碟機。 BitLocker 加密是內建於 Windows 的資料保護功能。 BitLocker 是硬體的下列其中一個以預防威脅，萬一有漏洞其他處理程序或可能會導致其他人存取實體磁碟包含客戶資料的控制項 （例如，存取控制或重複使用） 中所使用的技術。 在此情況下，BitLocker 會由於遺失、 遭竊或不當解除委任電腦和磁碟消除竊取或曝光的可能性。

使用進階加密標準 (AES) 256 位元加密磁碟包含客戶資料在 Exchange Online、 SharePoint Online 和商務用 Skype 部署 BitLocker。 磁碟的磁區會進行加密與完整磁碟區加密金鑰 (FVEK)，其中已加密與磁碟區的主要金鑰 (VMK)，其中依次有繫結至受信任的平台模組 (TPM) 的伺服器中。 因此，保護 VMK 得極為重要，VMK 直接保護 FVEK。 下圖說明 BitLocker 金鑰保護鏈結針對指定的伺服器 （在此案例中，使用 Exchange Online 的伺服器） 的範例。

下表說明 BitLocker 金鑰保護鏈結，針對指定的伺服器 （在此情況下，Exchange Online 伺服器）。

| 金鑰保護裝置 | 精確度 | 如何產生嗎？ | 是它儲存在哪裡？ | 保護 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| 使用 AES 256 位元外部索引鍵 | 每個伺服器 | BitLocker Api | TPM 或秘密安全 | 加密箱 / 存取控制 |
|  |  |  | 信箱伺服器登錄 | TPM 加密 |
| 48 位數數字密碼 | 每個磁碟 | BitLocker Api | Active Directory | 加密箱 / 存取控制 |
| 做為資料修復代理 (DRA) 的 X.509 憑證也稱為 「 公開金鑰保護裝置 | 環境 (例如，Exchange Online multitenant) | Microsoft CA | 建置系統 | 沒有一位使用者具有私密金鑰完整的密碼。 Password 是實體保護之下。 |


BitLocker 金鑰管理牽涉到可用來解除鎖定/復原在 Office 365 資料中心中的加密的磁碟的修復金鑰的管理。 Office 365 中的安全共用，只能由遮蔽並核准的個人儲存主索引鍵。 索引鍵的認證會儲存在安全存放庫的存取控制資料 （我們所謂"secret store"），這需要提高權限與管理核准存取使用剛時間存取權限提高工具較高層級。

BitLocker 支援可分為兩個管理類別的機碼：

- BitLocker managed 鍵，這通常是短暫和採用在伺服器上安裝作業系統執行個體的存留時間，或指定磁碟。 這些機碼的刪除和伺服器重新安裝或磁碟格式設定重設。

- BitLocker 復原鍵，受管理的外部 BitLocker 但用於磁碟解密。 BitLocker 會使用案例中重新安裝作業系統，和加密的資料磁碟存在復原機碼。 受管理的可用性，監視探查在 Exchange Online 需要回應程式也會使用復原金鑰來解除鎖定磁碟。

BitLocker 受保護的磁碟區加密使用依次加密與磁碟區的主要金鑰的完整磁碟區加密金鑰。 BitLocker 會使用 FIPS 相容演算法，以確保加密金鑰會永遠不會儲存或傳送透過線路傳輸中清除。 客戶資料在-rest-保護的 Office 365 實作不會從預設 BitLocker 實作以外。