---
title: Microsoft 365 技術控制項
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文概述 microsoft 365 中 Microsoft for 技術控制項使用的工具和技術。
ms.openlocfilehash: 66faac9c045dd9b6f6c0c7ea29ca1570e3ad8e19
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332697"
---
# <a name="microsoft-365-technology-controls"></a>Microsoft 365 技術控制項 

Microsoft 使用數種工具和技術來控制、管理及審核其線上服務中客戶資料的存取權。 這些功能適用于 Exchange Online、SharePoint 線上、密碼箱及客戶密碼箱、多重要素驗證等等。 Yammer 使用 [Yammer 企業存取控制](microsoft-365-yammer-enterprise-access-controls.md)中所述的類似控制項。

Microsoft 365 工程師在存取 Microsoft 365 客戶資料時，都有零。 在存取客戶資料以進行服務作業之前，工程師必須先進行 Microsoft 核准程式。 如果客戶授權 Exchange Online 的客戶密碼箱功能和 SharePoint 線上，必須由客戶核准才能存取客戶資料。 經過核准後，服務特有的管理帳戶即會為服務要求所需的工作布建即時存取。

## <a name="lockbox-and-customer-lockbox"></a>密碼箱及客戶密碼箱

雖然很少，客戶也可以從 Microsoft 取得協助，以將客戶內容公開給 Microsoft 工程師。 若要控制對 Exchange Online 的存取，Microsoft 使用稱為「密碼箱」的存取控制系統。 在任何 Microsoft 工程師存取任何 Exchange Online 或 SharePoint 線上系統或資料之前，必須使用密碼箱提交存取要求。 所有 Exchange Online 和 SharePoint 線上服務要求都是由密碼箱系統處理。 有了密碼箱和客戶密碼箱，所有核准的存取都會針對唯一的使用者進行追蹤，讓工程師對客戶資料的處理負責。

> [!NOTE]
> Exchange Online 包含儲存在使用者信箱中的任何商務用 Skype 資料。 商務用 skype 覆蓋範圍不包括 Skype 會議廣播錄製或使用者上傳至會議的內容。 線上 SharePoint 包括商務 OneDrive。

[！注意] 密碼箱處理要求，使工程師能夠在服務中執行作業和系統管理功能的許可權。 工程師透過密碼箱提交要求，而 Microsoft 管理員必須核准要求，工程師才能存取客戶資料。 管理員核准後，工程師對客戶資料的存取能力有限且範圍有限，以處理客戶的問題。

適用于 Microsoft 365 的客戶加密箱，可在您需要進行明確資料存取授權的程式時，滿足法規遵從性義務。 這是某些規範標準（例如 FedRAMP 和 HIPAA）的必要條件。 客戶加密箱會將您插入密碼箱核准程式，並讓您能夠控制對您的 Exchange Online 或 SharePoint 線上內容服務作業的 Microsoft access 授權。

在 Microsoft service 工程師需要存取資料的少數情況下，您只會將存取權授與解決問題所需的資料，並限制一段時間。 如果您拒絕存取要求，Microsoft 工程師無法存取您的內容，也無法完成服務作業。 如果您核准要求，Microsoft 工程師會透過受監控和限制的管理介面，以即時存取您的內容。

支援工程師採取的動作會記錄下來以供審核之用，並可透過 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) 與 [安全性與合規性中心](https://protection.office.com/)存取。

>[!NOTE]
> 客戶加密箱可在 [Microsoft 365 E5](https://products.office.com/business/office-365-enterprise-e5-business-software) 中作為附加元件購買。 如需詳細資訊，請參閱 [Microsoft 365 客戶加密箱要求](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。

## <a name="just-in-time-access"></a>即時存取

Microsoft 會使用即時 (JIT) Microsoft 365 的 access 原則，以減輕認證篡改風險和側向攻擊。 JIT 可移除服務的持續系統管理存取權，並以要求提升許可權，取代權利。 從系統管理員移除持續性存取權力，可確保認證只有在需要時才可使用，並可減少認證盜竊風險。

JIT 存取模型要求工程師要求較高的期限，以執行管理性的許可權。 此外，工程師會使用以機器產生的複雜密碼建立的暫存帳戶，並只授與允許其執行必要工作的角色。 例如，由密碼箱授與的系統管理員存取權是時間界限的，而且所授與的存取時間取決於要求的角色。 工程師指定要求存取密碼箱系統所需的時間。 當所要求的時間超過提升的允許時間上限時，密碼箱系統會拒絕要求。 到期後，系統會移除系統管理存取權，且暫時帳戶到期。

授權和核准進行存取時，工程師會收到一次使用授權系統所產生的「管理密碼」。 每當要求提升存取權要求時，就會產生新密碼。 密碼會被覆制到密碼安全，與工程師的 Microsoft 公司環境認證不同，且僅適用于已核准的高存取會話。

## <a name="constrained-management-interfaces"></a>受限制的管理介面

工程師使用兩個管理介面來執行系統管理工作：透過安全的終端服務閘道 (TSGs) 和遠端 PowerShell 的遠端桌面。 在這些管理介面內，軟體原則和存取控制對執行哪些應用程式，以及可以使用哪些命令和 Cmdlet 進行重要的限制。

Microsoft 365 伺服器會將同時會話限制為一個會話，每個服務小組管理員、每個伺服器。 TSGs 只允許使用者單一同時會話，而且不允許多個會話。 TSGs 可讓 Microsoft 365 服務小組管理員同時連線到多部伺服器，讓系統管理員能有效地執行其職責。 服務小組管理員對 TSGs 本身沒有任何許可權。 TSG 只用于強制執行多重要素驗證 (MFA) 和加密需求。 一旦服務小組管理員透過 TSG 連接至特定伺服器，該特定伺服器會強制每個系統管理員一個會話的會話限制。

Microsoft 365 人員的使用限制與連線和設定需求是由 Active Directory 群組原則所建立。 這些原則包含下列特性：

- TSGs 只使用 [FIPS](https://www.microsoft.com/TrustCenter/Compliance/FIPS) 140-2 驗證的加密。
- 在非活動狀態30分鐘後，TSG 會話會中斷連線。
- TSG 會話會在24小時後自動登出。

TSGs 的連線也需要使用個別的實體智慧卡和與工程師的 Microsoft 公司認證不同的帳戶，來進行 MFA。 工程師針對各種平臺和機密管理平臺發佈不同的智慧卡，以確保認證的安全儲存。 TSGs 使用 Active Directory 群組原則來控制可登入遠端伺服器的使用者、允許的會話數目及空閒超時設定。 其他原則會限制允許的應用程式存取，並限制網際網路存取。

除了使用特別設定之 TSGs 的遠端存取之外，Exchange Online 還允許具有「服務工程師運作」角色的使用者使用遠端 PowerShell 來存取生產伺服器上的特定管理功能。 若要這麼做，使用者必須獲得唯讀 (調試) 對 Microsoft 365 生產環境的存取權。 啟用許可權提升的方式，與使用密碼箱處理常式對 TSGs 啟用許可權提升的方式相同。

針對遠端存取，每個資料中心都有一種負載平衡虛擬 IP，可充當單一存取點。 可用的遠端 PowerShell Cmdlet 是以驗證期間所取得存取宣告中所識別的許可權層級為基礎。 這些 Cmdlet 只會提供使用此方法連線之使用者可存取的唯一管理功能。 Remote PowerShell 會限制工程師可使用的命令範圍，並根據透過密碼箱處理常式授與的存取層級而定。 例如，在 Exchange Online 中，可能會有 Get-Mailbox，但 Set-Mailbox 不會。
