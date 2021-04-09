---
title: Microsoft Defender for Endpoint data storage and 隱私權
description: 瞭解 Microsoft Defender for Endpoint 如何處理隱私權和其收集的資料。
keywords: Microsoft Defender for Endpoint，Microsoft Defender ATP，data storage and 隱私權，storage，隱私權，授權，地理位置，資料保留，資料
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e19c64c01c892a8a5f47f5892882feab1242f897
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644485"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Microsoft Defender for Endpoint data storage and 隱私權

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

本節涵蓋一些有關隱私權和用於 Defender 的資料處理的最常見常見問題。
> [!NOTE]
> 這份檔說明與 Defender for Endpoint 相關的資料儲存區與隱私權詳細資料。 如需與 Defender for Endpoint 和其他產品及服務如 Microsoft Defender 防病毒和 Windows 10 相關的詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=827576)。 如需詳細資訊，另請參閱 [Windows 10 隱私權 FAQ](https://go.microsoft.com/fwlink/?linkid=827577) 。


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Microsoft Defender for Endpoint 會收集哪些資料？

Microsoft Defender for Endpoint 會收集和儲存已設定裝置中已設定之裝置的資訊，以供系統管理、追蹤和報告之用的客戶專用和隔離租使用者使用。 

收集的資訊包括檔案資料 (例如：檔案名、大小和雜湊) 、處理資料 (執行中的程式、雜湊) 、登錄資料、網路連線資料 (主機 IPs 及埠) ，以及裝置詳細資料 (（如裝置識別碼、名稱和作業系統版本) ）。

Microsoft 會安全地將此資料儲存在 Microsoft Azure 中，並依照 Microsoft 隱私權慣例和 [Microsoft 信任中心原則](https://go.microsoft.com/fwlink/?linkid=827578)加以維護。

此資料可讓 Defender for Endpoint：
- 主動識別組織中 (IOAs) 的攻擊指示器
- 偵測到可能的攻擊時產生警示
- 在裝置、檔案和 URLs 中，提供與網路威脅信號相關的安全性作業，讓您能夠調查和探索網路上是否有安全性威脅。

Microsoft 不會使用您的資料進行廣告。

## <a name="data-protection-and-encryption"></a>資料保護和加密
「Defender for Endpoint service」利用以 Microsoft Azure 基礎結構為基礎的 art 資料保護技術狀態。 

有許多與我們的服務維護相關之資料保護的相關事項。 加密是一項最重要的功能，其中包括靜態資料加密、航班中的加密，以及使用主要 Vault 的金鑰管理。 如需有關供 Defender for Endpoint service 使用之其他技術的詳細資訊，請參閱 [Azure 加密概述](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)。 

在所有案例中，至少會以256位的 [AES 加密](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) 加密資料。


## <a name="data-storage-location"></a>資料儲存位置

在歐洲同盟、英國或美國地區的 Microsoft Azure 資料中心內，用來進行端點的 Defender。 服務所收集的客戶資料可能會儲存在： (a) 租使用者地理位置（如布建期間所識別）; 若要使用其他 Microsoft online 服務處理這類資料，則 (b) （如其他線上服務的資料儲存規則所定義的地理位置）。

在假名化表單中的客戶資料也可以儲存在美國的中央儲存區與處理系統中。

設定後，您就無法變更儲存資料的位置。 這會透過主動選取資料所在的地理位置，提供一種簡便的方法來降低法規遵從性風險。 

## <a name="is-my-data-isolated-from-other-customer-data"></a>我的資料是否獨立于其他客戶資料？
是的，您的資料會透過存取驗證及根據客戶識別碼的邏輯隔離來隔離。 每個客戶只能存取來自其自身組織的資料，以及 Microsoft 所提供的一般資料。

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Microsoft 如何防止惡意內部人員活動和濫用高許可權角色？

根據設計，Microsoft 開發人員和系統管理員已獲足夠的許可權來執行所指派的職責，以進行服務的運作及演化。 Microsoft 會部署預防性、偵探和反應性控制措施的組合，包括下列機制，以協助防止未經授權的開發人員和/或管理活動：

- 敏感性資料的緊密存取控制
- 極大地增強獨立偵測惡意活動的控制群組合
- 多層的監控、記錄和報告

此外，Microsoft 會執行某些作業人員的後臺驗證檢查，並限制對應用程式、系統和網路基礎結構的存取，以與背景驗證層級成比例。 當您需要存取客戶的帳戶或其職責效能中的相關資訊時，作業人員會遵循正式的處理常式。

在 Microsoft Azure 政府資料中心內部署之服務的資料存取權只會授與受限於特定政府法規和需求的資料，例如 FedRAMP、NIST 800.171 (DIB) 、ITAR、IRS 1075、DoD L4 及 CJIS。


## <a name="is-data-shared-with-other-customers"></a>資料是否與其他客戶共用？
否。 客戶資料會與其他客戶隔離，而且不會共用。 不過，Microsoft 處理所產生的資料或不包含任何客戶特有資料的深入資訊，可能會與其他客戶共用。 每個客戶只能存取來自其自身組織的資料，以及 Microsoft 所提供的一般資料。

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Microsoft 將資料儲存多久？ 什麼是 Microsoft 的資料保留原則？
**在服務上架**<br>
您可以選擇資料的資料保留原則。 這會決定 Windows Defender 端點用來儲存資料的時間長短。 您可以在一個月的範圍內靈活選擇六個月，以滿足公司的法規遵從性需求。

**合同終止或到期**<br>
您的資料將會保留，並可供您使用，但授權是在寬限期間或暫留模式下。 在此期間結束時，將會從 Microsoft 系統中清除該資料，使其無法復原，不得超過180天的合約終止或到期時間。

**高級搜尋資料**<br>
進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Microsoft 是否可以協助我們維護法規遵從性？

Microsoft 為客戶提供 Microsoft 安全性與合規性計畫的詳細資訊，包括審核報告和規範套件，以協助客戶根據自己的法律和法規需求，針對其評估 Endpoint 服務。 Defender for Endpoint 已取得許多憑證，包括 ISO、SOC、FedRAMP 高及 PCI，並繼續採用其他國家、地區和行業特定的認證。

透過為客戶提供相容且獨立驗證的服務，Microsoft 可讓客戶輕鬆取得所執行之基礎結構和應用程式的規範。

如需有關 Defender for Endpoint 認證報告的詳細資訊，請參閱 [Microsoft 信任中心](https://servicetrust.microsoft.com/)。 

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
