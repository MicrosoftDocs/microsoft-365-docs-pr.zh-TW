---
title: Office 365 服務加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 了解 Microsoft Office 365 中的資料復原。
ms.openlocfilehash: 7fec40db9ce12b52d37f2003d7ee8db68739aa41
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38690218"
---
# <a name="office-365-service-encryption"></a>Office 365 服務加密

除了使用磁碟區層級加密，Exchange Online、 Skype for Business、 SharePoint Online 和商務用 OneDrive 也使用服務加密來加密客戶資料。 服務加密可讓兩個金鑰管理選項：
- Microsoft 可管理所有的密碼編譯金鑰。 （此選項是 SharePoint Online、 商務用 OneDrive 與 Skype for Business 中目前無法使用。 它目前已在 Exchange Online 的藍圖。）
- 客戶提供根機碼搭配服務加密和客戶管理使用 Azure Key Vault 這些機碼。 Microsoft 可管理所有其他機碼。 此選項稱為客戶金鑰，而且目前適用於 Exchange Online、 SharePoint Online 和商務用 OneDrive。 （先前稱為使用 BYOK 進階加密。 請參閱[增強透明度及控制 Office 365 客戶](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)的原始的宣告。）

服務加密提供多個好處。 例如，它：
- 提供的權限以強式的加密保護的保護和管理功能。
- 包含客戶金鑰] 選項，可讓多承租人服務來提供每個租用戶金鑰管理。
- 提供 Windows 作業系統系統管理員與分開存取客戶資料儲存或處理的作業系統。
- 增強了 Office 365 能夠滿足客戶的有關加密的符合性需求。

## <a name="customer-key"></a>客戶金鑰
您可以使用客戶金鑰，來產生您自己的密碼編譯金鑰，使用內部 HSM 或 Azure 金鑰保存庫。 不論如何產生金鑰，客戶會使用 Azure Key Vault 控制和管理 Office 365 所使用的密碼編譯金鑰。 後金鑰會儲存在 Azure 金鑰保存庫，他們可以指派給工作負載，例如 Exchange Online 和 SharePoint Online，以做為用來加密您的信箱資料及檔案金鑰鏈的根目錄。
使用客戶金鑰的其他優點之一是來控制 Microsoft 能夠處理客戶資料。 這項功能存在，讓客戶想要移除 Office 365 （例如客戶終止與 Microsoft 服務或時移除資料儲存在雲端的一部份） 中的資料可以這麼做，與使用客戶金鑰做為技術的控制項，以確保沒有人包括 Microsoft，則可以存取或處理的資料。 這是加入 （和互補） 可以用來控制客戶資料的存取權，由 Microsoft 人員自該客戶加密箱功能。

若要了解如何設定客戶金鑰的 Office 365 的 Exchange Online、 Skype for Business、 SharePoint Online 和商務用 OneDrive，請參閱[控制使用客戶金鑰的 Office 365 中的資料](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697)。 如需詳細資訊，請參閱[Office 365 常見問題集的客戶金鑰](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)，並[使用客戶金鑰管理和控制需求，有助於符合規範資料](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580)。
