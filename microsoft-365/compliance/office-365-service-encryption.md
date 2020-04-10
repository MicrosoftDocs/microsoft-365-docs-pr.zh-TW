---
title: Office 365 服務加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：瞭解 Microsoft Office 365 的服務層級資料加密。
ms.openlocfilehash: fb6bf87fbd51bcb4383e9eb595ef11f081989d86
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211940"
---
# <a name="office-365-service-encryption"></a>Office 365 服務加密

除了使用 BitLocker 用於大量加密、Exchange Online、商務用 Skype、SharePoint Online、OneDrive 商務用，以及小組也會使用服務加密來加密客戶資料。 服務加密允許兩個主要的管理選項：

- Microsoft 管理所有的加密金鑰。 此選項目前可用於 SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype 和團隊聊天。 根據預設，您的資料會以 Microsoft 管理的金鑰加密。

- 您的組織提供根機碼。 您可以使用 Azure Key Vault 管理這些金鑰。 此選項稱為「客戶金鑰」。 客戶金鑰目前適用于 Exchange Online、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype 及小組檔案。 如果您使用客戶金鑰，這些金鑰會取代 Microsoft 受管理的金鑰來加密您的資料。

不論選擇哪個選項，服務加密都會提供多項優點：

- 強制進行使用者驗證，以取得及解密已授權使用者要求的資料。

- 讓 Windows 作業系統管理員分開存取作業系統所儲存或處理的客戶資料。

- 增強 Office 365 的功能，以符合具有加密之相容性需求之客戶的需求。

若要瞭解如何設定適用于 Exchange Online、商務用 Skype、SharePoint 線上、商務 OneDrive 或小組檔案的 Office 365 客戶金鑰，請參閱下列文章：

- [Office 365 中的客戶機碼服務加密](customer-key-overview.md)

- [設定 Office 365 的客戶金鑰](customer-key-set-up.md)

- [管理 Office 365 的客戶金鑰](customer-key-manage.md)

- [滾動或輪替客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)

- [瞭解可用性金鑰](customer-key-availability-key-understand.md)
