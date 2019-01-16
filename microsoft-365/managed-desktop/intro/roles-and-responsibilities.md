---
title: Microsoft 受管理的桌上型電腦的角色與責任
description: 本主題說明的角色與 Microsoft 提供的 Microsoft 受管理的桌上型電腦的責任。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 96131f7577e0e655067c70bffdd75163ba790adf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866760"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft 受管理的桌上型電腦的角色與責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

在 Microsoft 受管理的桌上型電腦中註冊您的組織，當 Microsoft 何在您？與貴組織的責任為何吗？

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft 的角色與責任

以下是幾個重要的角色與將會由 Microsoft 提供給您的責任。

角色或責任 | 描述
--- | ---
MDM 原則管理 | Microsoft 會將符合最佳作法 MDM 原則套用並考慮要求原則的變更。我們也會對您的租用戶前述[裝置原則](../service-description/device-policies.md)進行變更。
使用者支援 | Microsoft 會提供使用者支援的裝置、 Windows 及 Office 的所有註冊的使用者透過取得協助的應用程式上所有 Microsoft 受管理的桌上型電腦裝置已預先安裝的產品套件。 
Microsoft 受管理的桌上型電腦服務支援 | Microsoft 會提供支援給客戶 IT 部門有關透過 Microsoft 受管理的桌上型電腦作業小組。此小組會支援技術的疑難排解、 變更要求和事件管理客戶的 Microsoft 受管理的桌上型電腦環境。如需詳細資訊，請參閱[Microsoft 受管理的桌上型電腦支援的系統](../working-with-managed-desktop/admin-support.md)。
安全性監控 | Microsoft 會監視使用 Windows 防禦者 ATP 客戶 Microsoft 受管理的桌上型電腦裝置。如果威脅偵測到由 Microsoft 受管理的桌上型電腦安全性作業中心 (SOC)、 Microsoft 將通知客戶、 隔離裝置，並從遠端修正問題。如需詳細資訊，請參閱[安全性](../service-description/security.md)。
更新監視與管理 | Microsoft 將主動監視以確保最新的品質和功能更新已安裝 Microsoft Windows 與 Microsoft Office 的客戶 Microsoft 受管理的桌上型電腦裝置。如需詳細資訊，請參閱[如何處理更新](../service-description/updates.md)。
使用者和裝置群組 | Microsoft 受管理的桌上型電腦作業小組會建立並管理所需的裝置與使用者群組 IT 作業的一部分。不應該從 Microsoft 受管理的桌上型電腦作業小組不核准這些群組所做的變更。

## <a name="your-roles-and-responsibilities"></a>角色與責任

下面是常見的角色與責任沒有提供 Microsoft、 但成功部署所需的其他設定。它不是詳盡但適用於大多數的組織。有幾個項目下方 Microsoft 及客戶共用 responsibilties。 

角色或責任 | 描述
--- | ---
變更管理 | Microsoft 會通知客戶、 事先，需要在其 Microsoft 受管理的桌上型電腦環境中做的變更。客戶，則需要有其專屬變更管理程序與已與 Microsoft 受管理的桌上型電腦作業小組建立的連絡人。客戶也需要檢閱和核准這些變更的資源。如需詳細資訊，請參閱[作業和監控](../service-description/operations-and-monitoring.md)。  
身分識別管理 | 客戶負責建立使用者帳戶、 將使用者指派給群組以及保持最新的中繼資料。 
Office 365 設定與管理 | Microsoft 負責確保 Office 應用程式部署至使用者及這些應用程式保持在最新。 <br><br> 「 客戶 」 負責管理 Office 365 服務與原則，包括 Exchange Online 管理責任：<br>電子郵件管理<br>信箱及規則設定<br>Exchange 內部部署管理<br><br>客戶也是負責共同作業工具、 SharePoint server 管理、 網域管理、 安全性及資訊原則設定 Office 365 系統管理入口網站中。 
使用者支援 | 「 客戶 」 負責提供使用者支援： <br>位在站台基礎架構： 所有網路與網際網路連線、 VPN 基礎結構和用戶端組態、 本機會議會議室設備、 印表機、 proxy 伺服器和防火牆的組態。<br><br>-全公司的雲端資源： 電子郵件、 SharePoint、 共同作業服務及其他雲端基礎結構與全公司的技術之上。<br><br>-線的業務與任何其他公司特定應用程式。
應用程式 | Microsoft 提供要求時使用 Intune 的已核准應用程式的部署的指導。<br><br>「 客戶 」 負責：<br>-為其組織 （非由 Office 365 應用程式） 提供應用程式的清單<br>宣告應用程式授權管理<br>– 具有正確的類型和授權數量<br>宣告應用程式工作分派<br>– 應用程式指派給 Azure AD 使用者群組<br>宣告應用程式更新<br>– 監視、 封裝，以及部署應用程式功能和安全性更新<br>使用者應用程式測試 (UAT)<br>-提供適當的可部署套件<br><br>如需詳細資訊，請參閱[應用程式](../get-ready/apps.md)
安全性監視和回應 | 客戶負責調查並解決非的 Microsoft 受管理的桌上型電腦裝置和確保 Microsoft 受管理的桌上型電腦作業小組會通知可能會影響服務的所有問題的事件。
作業支援 | 客戶負責提供慣用的客戶連絡人和主題專家所提供的清單。Microsoft 需要這些以防非的 Microsoft 受管理的桌上型電腦操作事件。 <br><br>客戶也是負責調查並解決非的 Microsoft 受管理的桌上型電腦裝置及服務和確保 Microsoft 受管理的桌上型電腦作業小組一律會通知資訊的事件。
網路基礎結構，包括 VPN | 「 客戶 」 負責安裝、 設定及管理 （包括疑難排解和偵錯） 的所有網路相關的基礎結構和服務，包括網際網路連線的網路控制項、 proxy 設定和遠端連線基礎結構。<br><br>如果 proxy 設定 （在硬體或軟體），有一群必須允許 proxy 的 Url。客戶負責疑難排解任何衝突或不相容性因多個 proxy。<br><br>如需詳細資訊，請參閱[Proxy 設定](../get-ready/network.md)。
列印 | 客戶負責安裝、 維護及管理印表機和列印佇列。雲端是建議的解決方案，但不是必要的列印。 




