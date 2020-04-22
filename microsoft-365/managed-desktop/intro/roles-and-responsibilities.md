---
title: Microsoft 受管理的桌面角色與責任
description: 本主題說明 Microsoft 受管理的桌面的 Microsoft 所提供的角色和責任。
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 02a0b11a1a210367d76e73c75ac5c1fc7a66f94f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636205"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft 受管理的桌面角色與責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

當您的組織註冊 Microsoft Managed Desktop 時，Microsoft 會為您做什麼？ 您的組織的責任為何？

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft 的角色與責任

以下是 Microsoft 會提供給您的一些重要角色和責任。

角色或責任 | 描述
--- | ---
MDM 原則管理 | Microsoft 會根據最佳作法套用 MDM 原則，並考慮原則變更的要求。 我們也會依照[裝置原則](../service-description/device-policies.md)中的規定對租使用者進行變更。
使用者支援 | Microsoft 會透過預先安裝于所有 Microsoft 受管理的桌面裝置上的 Get Help 應用程式，為所有已註冊的使用者提供使用者、Windows 和 Office 產品套件的使用者支援。 
Microsoft 受管理的桌面服務支援 | Microsoft 將透過 Microsoft 受管理的桌面作業小組為客戶 IT 部門提供支援。 此小組將支援客戶的 Microsoft 受管理桌面環境的技術疑難排解、變更要求和事件管理。 如需詳細資訊，請參閱[Microsoft Managed Desktop 的系統管理支援](../working-with-managed-desktop/admin-support.md)。
安全性監控 | Microsoft 將使用 Microsoft Defender ATP 監視客戶 Microsoft 受管理的桌面裝置。 如果 Microsoft Managed Desktop Security Operations Center （SOC）偵測到威脅，Microsoft 會通知客戶、隔離裝置，並以遠端方式修正問題。 如需詳細資訊，請參閱[安全性](../service-description/security.md)。
更新監控與管理 | Microsoft 將主動監視客戶 Microsoft 受管理的桌面裝置，以確保已安裝 Microsoft Windows 和 Microsoft Office 的最新品質和功能更新。 如需詳細資訊，請參閱[如何處理更新](../service-description/updates.md)。
使用者和裝置群組 | Microsoft 受管理的桌面作業小組會建立及管理必要的裝置和使用者群組做為 IT 作業的一部分。 這些群組不允許任何成員資格或設定變更。 變更這些群組可能會造成裝置的意外設定和功能喪失。 如需在建立這些群組之後的任何問題或問題，IT 管理員可以與 Microsoft 受管理的桌面作業聯繫。 如需詳細資訊，請參閱[Microsoft Managed Desktop 的系統管理支援](../working-with-managed-desktop/admin-support.md)。

## <a name="your-roles-and-responsibilities"></a>您的角色與責任

以下是 Microsoft 未提供的一組共同共同角色和責任，但這些是成功部署所需的。 這不是詳盡，但適用于大部分的組織。 在下列專案中，Microsoft 與客戶共用 responsibilties。 

角色或責任 | 描述
--- | ---
變更管理 | 當需要對 Microsoft 受管理的桌面環境進行變更時，Microsoft 會事先通知客戶。 如需詳細資訊，請參閱[服務變更和通訊](../service-description/servicechanges.md)<br><br>客戶必須有其自己的變更管理程式，且有與 Microsoft Managed Desktop Operations 小組建立的連絡人。 客戶也需要有資源來審閱及核准這些變更。 如需詳細資訊，請參閱[Operations and monitoring](../service-description/operations-and-monitoring.md)。  
身分識別管理 | 客戶負責建立使用者帳戶，將使用者指派給群組，並將中繼資料保持在最新狀態。 
適用于企業設定和管理的 Microsoft 365 應用程式 | Microsoft 負責確保將 Office 應用程式部署至使用者，而這些應用程式會保持最新狀態。 <br><br> 客戶負責管理 Microsoft 365 服務和原則，包括 Exchange Online 系統管理責任：<br>-電子郵件管理<br>-信箱和規則設定<br>-Exchange 內部部署管理<br><br>客戶也負責共同作業工具、SharePoint 伺服器管理、網域管理、安全性和資訊原則設定于 Microsoft 365 系統管理中心。 
使用者支援 | 客戶負責提供下列專案的使用者支援： <br>-On site 基礎結構：所有網路及網際網路連線、VPN 基礎結構及用戶端設定、本機會議會議室設備、印表機、proxy 伺服器及設定、防火牆。<br><br>-全公司的雲端資源：電子郵件、SharePoint、共同作業服務，以及其他與整個公司的技術空間有關的雲端基礎結構。<br><br>-業務線和任何其他公司特定的應用程式。
App | 角色和責任因 Microsoft 受管理的桌面所提供的應用程式和您所提供的應用程式稍有不同。 <br><br>針對 Microsoft 所提供的應用程式（Microsoft 365 Apps for enterprise （包含 Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype、小組和 OneNote）， **Microsoft**將為部署、更新及支援提供完整服務。 **您**必須取得並指派這些應用程式的授權、將使用者新增至安全性群組和管理生命週期，以及部署您所需的任何附加元件。<br><br>針對您所提供的應用程式（例如，您的企業營運應用程式），您是否自行打包或接洽非 Microsoft 供應商來執行這項作業，**您**負責下列動作： <br><br>-識別目標使用者群組所需的應用程式<br>-針對應用程式部署建立及管理 Azure AD 群組<br>-打包應用程式以符合 Microsoft Intune 部署標準<br>-將應用程式上傳至 Microsoft Intune<br>-在 Microsoft 管理的桌面環境中測試應用程式<br>-隨使用者測試應用程式<br>-管理及指派使用者至應用程式<br>-透過 Microsoft Intune 識別及部署應用程式更新<br>-卸載並移除已停用的應用程式<br>-購置和指派授權<br>-提供企業營運服務應用程式的使用者支援<br>-遠端管理應用程式設定<br><br>**Microsoft**會提供 microsoft Intune 部署工具，將應用程式傳送至遠端用戶端。<br><br>如需詳細資訊，請參閱[應用程式](../get-ready/apps.md)
安全性監控和回應 | 客戶負責調查和解決非 Microsoft 受管理桌面裝置的事件，並確保 Microsoft 受管理的桌面作業小組已獲悉任何可能會影響服務的問題。
作業支援 | 客戶負責提供一份偏好的客戶連絡人及主題專家的清單。 Microsoft 需要這些功能，以防發生非 Microsoft 管理的桌面作業事件。 <br><br>客戶也負責調查和解決非 Microsoft 受管理的桌面裝置和服務的事件，並確保永遠知道 Microsoft 受管理的桌面作業團隊。
網路基礎結構（包含 VPN） | 客戶負責所有網路相關基礎結構和服務（包括網際網路連線、網路控制、proxy 設定及遠端連線基礎結構）的設定、設定和管理（包括疑難排解及調試）。<br><br>如果已設定 proxy （在硬體或軟體中），則必須有 proxy 所允許的 URLs 集合。 客戶負責疑難排解因多個 proxy 的任何衝突或不相容性。 您可以使用可設定的設定，新增組織特有的網路 proxy。 如需詳細資訊，請參閱[可設定的設定](../working-with-managed-desktop/config-setting-ref.md#proxy)。<br><br>如需詳細資訊，請參閱[Proxy Configuration](../get-ready/network.md)。
列印 | 客戶負責安裝、維護及管理印表機及列印佇列。 雲端列印是建議的解決方案，但不是必要的。 




