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
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 了解 Microsoft Office 365 中的資料復原。
ms.openlocfilehash: ec7f794a62a910fadaece890cf73451644d44109
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071110"
---
# <a name="office-365-service-encryption"></a>Office 365 服務加密

除了使用磁碟區層級加密，Exchange Online、 Skype for Business、 SharePoint Online 和商務用 OneDrive 也使用服務加密來加密客戶資料。 服務加密可讓兩個金鑰管理選項：

- Microsoft 可管理所有的密碼編譯金鑰。 （此選項是 SharePoint Online、 商務用 OneDrive 與 Skype for Business 中目前無法使用）。

- 客戶提供根機碼搭配服務加密和客戶管理使用 Azure Key Vault 這些機碼。 Microsoft 可管理所有其他機碼。 此選項稱為客戶金鑰，而且目前適用於 Exchange Online、 SharePoint Online 和商務用 OneDrive。 （先前稱為使用 BYOK 進階加密。 請參閱[增強透明度及控制 Office 365 客戶](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)的原始的宣告。）

服務加密提供多個好處。 例如，客戶金鑰：

- 提供的權限以強式的加密保護的保護和管理功能。

- 包含客戶金鑰] 選項，可讓多承租人服務來提供每個租用戶金鑰管理。

- 提供 Windows 作業系統系統管理員與分開存取客戶資料儲存或處理的作業系統。

- 增強了 Office 365 能夠滿足客戶的有關加密的符合性需求。

## <a name="customer-key"></a>客戶金鑰

您可以使用客戶金鑰，來產生您自己的密碼編譯金鑰，使用內部部署硬體服務模組 (HSM) 或 Azure Key Vault (AKV)。 不論您如何產生金鑰，您可以使用 AKV 來控制及管理 Office 365 所使用的密碼編譯金鑰。 一旦您金鑰會儲存在 AKV，他們可以做的其中一個加密您的信箱資料或檔案 keychains 根目錄。

客戶金鑰的另一個好處是控制項必須透過 Microsoft 能夠處理您的資料。 如果您想要移除 Office 365 中的資料，例如好像您想要終止與 Microsoft 服務或移除資料儲存在雲端的一部份，您可以這麼做為技術的控制項使用客戶金鑰。 這可確保沒有人，包括 Microsoft，則可以存取或處理的資料。 客戶金鑰是此外，您用來控制由 Microsoft 人員自您資料的存取權的客戶加密箱的補充。

若要了解如何設定客戶金鑰的 Office 365 的 Exchange Online、 商務用 Skype、 SharePoint Online，包括小組網站和商務用 OneDrive，請參閱下列文章：

- [使用 Office 365 中的客戶金鑰服務加密](customer-key-overview.md)

- [設定 Office 365 客戶金鑰](customer-key-set-up.md)

- [管理 office 365 的客戶金鑰](customer-key-manage.md)

- [展開或旋轉客戶金鑰或可用性機碼](customer-key-availability-key-roll.md)

- [了解可用性機碼](customer-key-availability-key-understand.md)
 
