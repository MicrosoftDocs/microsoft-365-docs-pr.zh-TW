---
title: 適用于企業商務持續性管理緩解的 Microsoft 365
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 服務事件案例的部分緩和範例。
ms.openlocfilehash: 71f2aade674d1d3f2ba95701f9d8113a8b57afeb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686043"
---
# <a name="service-incident-mitigation-strategies"></a>服務事件緩和策略

以下的一些策略和案例，說明如何緩和企業流程中 Microsoft 365 服務事件的影響。

## <a name="service-incident-scenarios-and-potential-mitigations"></a>服務事件案例和潛在緩和

|Microsoft 365 相依性|潛在緩和|
|---------|---------|
|事件管理系統仰賴 Exchange Online 來接洽值勤工程師和事件管理員。|請確認您的事件管理系統支援多管道通訊 (例如平行電子郵件、電話和簡訊通知) 和呼叫樹狀目錄階層，以便在無法接洽主要值勤人員時，系統會自動接洽備用人員。 也會在每個通知中包含備用的連絡方法，使得備用的通訊方法會內嵌在其中供輕鬆參考。 如果事件管理服務無法使用，則可使用替代的通訊方法 (例如 Yammer) 進行緊急共同作業。|
|Microsoft Teams 可用於儲存透過用戶端存取的檔案。|Teams 會將上傳到用戶端的檔案儲存在 SharePoint Online 文件庫中。 這些檔案仍可透過 SharePoint Online 存取。 訓練使用者有關 SharePoint Online 中的檔案位置。|
|一般通訊和事件管理分級仰賴使用 Microsoft Teams 電話會議。|建立使用協力廠商提供者的備用會議解決方案。|
|使用 VoIP 電話做為溝通的次要方法。|實作支援 PSTN 通話的非 VoIP 電話，特別針對在事件期間的網路與服務作業中心。 將員工的行動電話號碼新增至公司目錄，以便透過行動網路連絡重要人員。|
|檔案儲存和使用者生產力仰賴使用商務用 OneDrive。 [檔案隨選](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-On-Demand-For-The-Enterprise/ba-p/117234)的設定可釋出本機使用者磁碟機上的空間。|OneDrive 同步處理會提供群組原則，允許系統管理員在本機同步處理特定內容，或在需要時釋出空間。 若要緩和文件無法存取的風險，請設定此原則以同步處理本機的重要檔案。 訓練使用者對重要文件手動套用 [永遠保留在此裝置上] 設定。|
|向客戶和供應商溝通相關的業務中斷仰賴使用 Exchange Online。|公用協力廠商社交網路可做為大量通訊的備用方式。
|混合式內部部署架構（例如 ADFS 或 Pass 驗證）會造成使用者無法驗證雲端服務。|將 [密碼散列同步處理](https://docs.microsoft.com/azure/active-directory/authentication/concept-resilient-controls#deploy-password-hash-sync-even-if-you-are-federated-or-use-pass-through-authentication)與混合式驗證服務搭配使用，做為輔助雲端型驗證服務，避免在中斷期間登入。 [如需有關建立彈性驗證和存取控制架構的進一步資訊，請參閱建立 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-resilient-controls) 彈性存取控制管理原則。|  

## <a name="leveraging-mobile-app-access"></a>運用行動應用程式存取

隨著行動裝置的使用情況大幅增加，有一些新方法可讓您保持連線，而 Microsoft 365 行動應用程式可能是復原能力策略的重要部分。 因為它們透過行動服務提供者網路連線到雲端服務，因此它們不依賴於您的組織網路基礎結構。

讓我們以 Outlook 為例。 使用者可以根據所使用的電子郵件應用程式，透過不同的網路通訊協定 (https 或 MAPI) 連線到其 Exchange Online 信箱。 如果某個服務事件涉及其中一個通訊協定，比方說，桌面用戶端使用的是 MAPI，那麼您的使用者仍可以透過 Outlook 行動 App 支援或 Outlook 網頁版來進入其信箱。
  
如果您決定允許使用者透過行動裝置連線至 Microsoft 365 服務，則可以使用 Microsoft Intune 來安全地設定及管理這些裝置。 在行動裝置管理解決方案中註冊使用者帳戶和裝置之後，請確保已下載並設定應用程式。
