---
title: 隱私權和個人資料
description: 詳述服務收集、儲存及使用的資料
keywords: GDPR，保留，刪除，儲存，保留，處理，安全性，審核
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 0ee214cf7ff5d5998a7fa35688574a23f8b082f0
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229596"
---
# <a name="overview"></a>概觀

Microsoft 受管理的電腦是一種服務 (ITaaS) 服務，適用于設計用來保持員工 Windows 裝置部署和更新的企業雲端客戶。 它還提供 IT 服務管理和作業、監控安全性和事件回應，以及提供使用者支援。 這份檔提供 Microsoft 受管理的電腦的資料平臺及隱私權相容性的其他詳細資料。

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft 受管理的電腦資料來源和用途

Microsoft 受管理的電腦為企業客戶提供其服務，並使用各種來源的資料，正確地管理客戶的註冊裝置。 這些來源（包括 Azure Active Directory、Microsoft Intune、microsoft Windows 10 和 Microsoft Defender for Endpoint）提供 Microsoft 受管理的電腦管理之裝置的完整視圖。 服務也會使用這些 Microsoft 服務，讓 Microsoft 受管理的電腦提供 ITaaS 功能：

- [Microsoft Windows 10 企業版](/windows/windows-10/)-用於管理裝置設定體驗、管理其他服務的連線，以及 IT 專業人員的操作支援。
- [Windows 商務更新](/windows/deployment/update/waas-manage-updates-wufb)-使用 Windows 10 企業版診斷資料，以提供 Windows 10 更新的詳細資訊。 
- [Microsoft 端點管理員](/mem/endpoint-manager-overview)–用於裝置管理並保證您的資料安全。
  - [Microsoft Azure Active Directory](/azure/active-directory/) -用於驗證及識別所有使用者帳戶。 
  - [Microsoft Intune](/mem/intune/) –用於散佈裝置設定、裝置管理及應用程式管理。
  - [端點分析](/mem/analytics/overview) -用於有關裝置和應用程式使用狀況的分析洞察力。
  - [Windows Autopilot](/microsoft-365/windows/windows-autopilot) –用於裝置布建及部署。
  - [Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint/) –提供諸如裝置安全性監控和安全性情報資料等安全性服務。
- [Microsoft 受管理的電腦](https://endpoint.microsoft.com/#home)–在服務執行期間由客戶提供或由服務所產生的資料。
- [Microsoft 365 企業應用程式](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1)–用於 Microsoft 365 Apps 管理。

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft 受管理的電腦資料處理程式和儲存區

Microsoft 受管理的電腦依賴多個 Microsoft 產品和服務中的資料，為企業客戶提供其服務。 為了達到保護及維護已註冊裝置的目的，我們會從這些服務處理及複製資料，以 Microsoft 受管理的電腦。 當我們處理資料時，我們會依照線上服務條款和 Microsoft 隱私權聲明中所述，遵循您提供的記錄方向。 當我們處理資料時，我們會依照 [線上服務條款](https://www.microsoft.com/licensing/product-licensing/products) 和 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)中所述，遵循您提供的記錄方向。 Microsoft 受管理的電腦的處理器職責包括確保適當的機密性、安全性和恢復能力。 Microsoft 受管理的電腦採用額外的隱私權和安全性措施，以確保正確處理個人身分識別的資料。 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft 受管理的電腦資料儲存區和人員位置

Microsoft 受管理的電腦會將其資料儲存在美國的 Azure 資料中心。 您必須使用 Microsoft 受管理的電腦及其他服務所取得的個人資料，才能讓服務保持運作。 如果從 Microsoft 受管理的電腦中移除裝置，我們會將個人資料保留最多30天，除了 Microsoft Defender for Endpoint 所收集的警示資料之外，出於安全性目的，它會儲存為180天。 如需資料保留的詳細資訊，請參閱[資料保留、刪除及銷毀 Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。

Microsoft 受管理的電腦工程運作及安全性作業小組位於美國和印度。 

## <a name="microsoft-windows-10-diagnostic-data"></a>Microsoft Windows 10 診斷資料

Microsoft 受管理的電腦會使用[Windows 10 增強型診斷資料](/windows/privacy/windows-diagnostic-data)，以保持 Windows 安全、更新、疑難排解問題，以及改善產品的功能。 [增強型診斷資料] 設定包括有關登錄 Microsoft 受管理的電腦裝置的詳細資訊，以及其設定、功能和裝置健康情況。 選取增強的診斷資料時，會收集資料（包括所需的診斷資料）。 如需有關 Windows 10 診斷資料設定與資料收集的詳細資訊，請參閱[Windows 診斷資料收集的變更](/windows/privacy/changes-to-windows-diagnostic-data-collection)。

在未來版本的 Windows 中，診斷資料術語會變更。 Microsoft 受管理的電腦承諾只處理服務所需的資料。 雖然這會使診斷層級變更為 **選用**，但 Microsoft 受管理的電腦會執行有限的診斷原則，以微調服務所需的診斷資料收集。 如需詳細資訊，請參閱[變更至 Windows 診斷資料收集](/windows/privacy/changes-to-windows-diagnostic-data-collection)。

Microsoft 受管理的電腦只處理來自已註冊裝置（如應用程式和裝置可靠性及效能資訊） Windows 10 選用診斷資料，並儲存系統層級的資料。 Microsoft 受管理的電腦不會處理及儲存客戶的個人資料，例如聊天與瀏覽器的記錄、語音、文字或語音資料。 

如需 microsoft Windows 10 之診斷資料集合的詳細資訊，請參閱 microsoft 隱私權聲明的 [[我們儲存及處理個人資料的位置](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule)] 區段。

## <a name="microsoft-windows-update-for-business"></a>Microsoft Windows 商務更新
Microsoft Windows 商務更新使用來自 Windows diagnostics 的資料來分析更新狀態和失敗。 Microsoft 受管理的電腦會利用此資料，並使用它來緩解及解決問題，以確保所有已註冊的裝置都會根據預先定義的更新節奏保持最新狀態。

## <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
Microsoft 受管理的電腦所用的識別資料是由在組織中 Azure Active Directory (Azure AD) 時所儲存，該位置是根據組織在訂閱 Microsoft online services 時所提供的位置，例如 enterprise 和 Azure 的 Microsoft Apps。 Microsoft 受管理的電腦所用的識別資料會根據組織在訂閱 Microsoft online 服務（如 enterprise 和 Azure Microsoft Apps 等）的地點，在地理位置儲存。 如需 Azure AD 資料所在位置的詳細資訊，請參閱[Azure Active Directory-您的資料位於何處？](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

## <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune 收集、處理及共用資料，以 Microsoft 受管理的電腦支援商務作業和服務。 如需 Intune 中所收集資料的詳細資訊，請參閱 [Intune 中的資料收集](/mem/intune/protect/privacy-data-collect) 。 

如需 Microsoft Intune 資料位置的詳細資訊，請參閱[儲存 Microsoft 365 客戶資料的位置](/microsoft-365/enterprise/o365-data-locations)。 Intune 會尊重管理員為客戶資料所做的儲存位置選擇。

## <a name="microsoft-defender-for-endpoint"></a>適用於端點的 Microsoft Defender
Microsoft Defender for Endpoint 會收集和儲存在 Microsoft 受管理的電腦中登記的裝置資訊，以進行管理、追蹤及報告目的。 收集的資訊包括檔案資料 (例如：檔案名、大小和雜湊) 、處理資料 (執行中的程式、雜湊) 、登錄資料、網路連線資料和裝置詳細資料 (例如裝置識別碼、裝置名稱和作業系統版本) 。 如需 Microsoft Defender for Endpoint 資料收集和儲存位置的詳細資訊，請參閱 [Microsoft defender For endpoint data storage and 隱私權](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) 。 

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps 企業版 
Microsoft 365 Apps 企業版會使用 Microsoft 受管理的電腦收集及共用資料，以確保根據 Microsoft 受管理的電腦所管理的預先定義的更新通道，使用最新版本的應用程式。 如需 Microsoft 365 Apps 的資料收集和儲存位置的詳細資訊，請參閱[Microsoft Defender for Endpoint data storage and 隱私權](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)。

## <a name="major-data-change-notification"></a>主要資料變更通知
Microsoft 受管理的電腦遵循我們服務通訊架構中所述的變更控制處理常式。 我們會透過 Microsoft 365 訊息中心通知客戶，並 Microsoft 受管理的電腦管理入口網站的安全性事件及主要變更服務。 對收集到的資料類型所做的變更，以及儲存位置的變更，都會視為一項材料變更。 我們會提供至少30天的此變更的高級通知，因為這是 Microsoft 365 產品和服務的標準作法。 如需詳細資訊，請參閱 [服務變更和通訊](/microsoft-365/managed-desktop/service-description/servicechanges)。

## <a name="compliance"></a>合規性
Microsoft 受管理的電腦已完成外部審核，並取得一組完整的規範服務。 您可以在 Microsoft 受管理的電腦[法規遵從性](/microsoft-365/managed-desktop/intro/compliance)中找到詳細資訊。 您可以在 microsoft[服務信任入口網站](https://aka.ms/stp)上下載審計報告，其充當 microsoft Enterprise 線上服務的中央存放庫。  (Microsoft 受管理的電腦會列在這些檔中的「監控與管理」類別之下。)  

## <a name="legal"></a>法律資訊
**Microsoft 對於組織客戶提供之產品的使用者隱私權通知** - [microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement) 會通知使用者，當使用者使用工作帳戶登入 Microsoft 產品時，就會通知使用者。 a) 其組織可以控制和管理其帳戶 (包括控制隱私權相關設定) 和存取及處理其資料，而 b) Microsoft 可能會收集並處理資料，以提供服務給組織和使用者。
