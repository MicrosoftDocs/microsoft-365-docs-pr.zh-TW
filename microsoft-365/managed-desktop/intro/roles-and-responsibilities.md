---
title: Microsoft 受管理的桌面角色和責任
description: 本主題說明 Microsoft 針對 Microsoft 受管理的電腦所提供的角色和責任。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: a51738b993a8a3683769d10882877b3b42d34ddf
ms.sourcegitcommit: 7edeea1311ebb79a8c72418d2c6451b94fb788cb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2019
ms.locfileid: "35061846"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft 受管理的桌面角色和責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

當您的組織註冊 Microsoft 受管理的電腦時, Microsoft 會為您做什麼？ 您的組織有何責任？

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft 的角色和責任

以下是 Microsoft 會提供給您的幾個重要角色和責任。

角色或責任 | 描述
--- | ---
MDM 原則管理 | Microsoft 會根據最佳作法套用 MDM 原則, 並考慮原則變更的要求。 我們也會對您的租使用者所做的變更, 如[裝置原則](../service-description/device-policies.md)所述。
使用者支援 | Microsoft 會透過預先安裝在所有 Microsoft 受管理的電腦裝置上的 Get Help app, 為裝置、Windows 和 Office 產品套件提供使用者支援。 
Microsoft 受管理的桌面服務支援 | Microsoft 會透過 Microsoft 受管理的桌面作業小組, 為客戶 IT 部門提供支援。 此小組將支援客戶的 Microsoft 受管理桌面環境的技術疑難排解、變更要求和事件管理。 如需詳細資訊, 請參閱[Microsoft 受管理電腦的系統管理支援](../working-with-managed-desktop/admin-support.md)。
安全性監視 | Microsoft 會使用 Windows Defender ATP 來監視客戶 Microsoft 受管理的電腦裝置。 如果 Microsoft 受管理的桌面安全性作業中心 (SOC) 偵測到威脅, Microsoft 會通知客戶、隔離裝置, 並從遠端修正問題。 如需詳細資訊, 請參閱[安全性](../service-description/security.md)。
更新監控與管理 | Microsoft 會主動監視客戶 Microsoft 受管理的電腦裝置, 以確定已安裝 Microsoft Windows 和 Microsoft Office 的最新品質和功能更新。 如需詳細資訊, 請參閱[處理更新的方式](../service-description/updates.md)。
使用者和裝置群組 | Microsoft 受管理的桌面作業小組會建立並管理所需的裝置和使用者群組, 做為 IT 作業的一部分。 這些群組都不允許任何成員資格或設定變更。 變更這些群組可能會導致裝置未預期的設定及功能遺失。 關於這些群組的任何問題或問題已建立之後, IT 系統管理員可以聯絡 Microsoft 受管理的桌面作業。 如需詳細資訊, 請參閱[Microsoft 受管理電腦的系統管理支援](../working-with-managed-desktop/admin-support.md)。

## <a name="your-roles-and-responsibilities"></a>您的角色和責任

以下是 Microsoft 未提供的一組其他共同角色和責任, 但是是成功部署所需的。 這並不是完整的, 但適用于大部分的組織。 以下是 Microsoft 和客戶共用 responsibilties 的一些專案。 

角色或責任 | 描述
--- | ---
變更管理 | Microsoft 會在需要對其 Microsoft 受管理的桌面環境進行變更時, 提前通知客戶。 客戶需要有自己的變更管理程式, 且有與 Microsoft 受管理的桌面作業小組建立的連絡人。 客戶也需要有資源來審查及核准這些變更。 如需詳細資訊, 請參閱[Operations and monitoring](../service-description/operations-and-monitoring.md)。  
身分識別管理 | 客戶負責建立使用者帳戶、將使用者指派給群組, 以及將中繼資料保持在最新狀態。 
Office 365 設定和管理 | Microsoft 負責確保 Office 應用程式已部署至使用者, 而這些應用程式會保持在最新狀態。 <br><br> 客戶負責管理 Office 365 服務和原則, 包括 Exchange Online 系統管理責任:<br>-電子郵件管理<br>-信箱和規則設定<br>-Exchange 內部部署管理<br><br>客戶也負責 Office 365 系統管理入口網站中設定的共同作業工具、SharePoint server 管理、網域管理、安全性和資訊原則。 
使用者支援 | 客戶負責提供下列專案的使用者支援: <br>-網站基礎結構: 所有網路和網際網路連線、VPN 基礎結構和用戶端設定、本機會議會議室設備、印表機、proxy 伺服器和設定、防火牆。<br><br>-全公司的雲端資源: 電子郵件、SharePoint、共同作業服務和其他雲端基礎結構, 與全公司的技術需求量有關。<br><br>-業務線和任何其他公司特定的應用程式。
App | 角色和責任對作為 Microsoft 受管理的桌面部分所提供, 與您所提供的應用程式稍有不同。 <br><br>針對 Microsoft 所提供的應用程式 (Office 365 專業增強版 Standard Suite, 包含 Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype、小組和 OneNote), **Microsoft**會提供部署、更新及支援的完整服務。 **您**必須取得並指派這些應用程式的授權、將使用者新增至安全性群組, 以及管理您所需的任何 Office 365 Addons。<br><br>針對您提供的應用程式 (例如企業營運應用程式), 無論您是自行包裝, 還是請與非 Microsoft 廠商接洽,**您**必須負責這些動作: <br><br>-識別目標使用者群組所需的應用程式<br>-建立和管理應用程式部署的 Azure AD 群組<br>-打包應用程式以符合 Microsoft Intune 部署標準<br>-將應用程式上傳至 Microsoft Intune<br>-在 Microsoft 受管理的桌面環境中測試應用程式<br>-與您的使用者一起測試應用程式<br>-管理與指派使用者至應用程式<br>-透過 Microsoft Intune 識別及部署應用程式更新<br>-卸載並移除已淘汰的應用程式<br>-購置和指派授權<br>-提供企業營運應用程式的使用者支援<br>-遠端管理應用程式設定<br><br>**Microsoft**會提供 microsoft Intune 部署工具, 將應用程式提供給遠端用戶端。<br><br>如需詳細資訊, 請參閱[app](../get-ready/apps.md)
安全性監視和回應 | 客戶負責調查和解決非 Microsoft 受管理的桌面裝置的事件, 並確保 Microsoft 受管理的桌面作業小組獲悉任何可能會影響服務的問題。
作業支援 | 客戶負責提供一份喜好的客戶連絡人和主題專家的清單。 如果有非 Microsoft 受管理的桌面作業事件, 則 Microsoft 需要這些服務。 <br><br>客戶也負責調查和解決非 Microsoft 受管理的桌面裝置和服務的事件, 並確保始終會通知 Microsoft 受管理的桌面作業小組。
網路基礎結構, 包括 VPN | 客戶負責所有網路相關基礎結構和服務 (包括網際網路連線、網路控制、proxy 設定和遠端) 的設定、設定和管理 (包括疑難排解及調試)。連線基礎結構。<br><br>如果已設定 proxy (在硬體或軟體中), 則必須有 proxy 所允許的 Url 的集合。 客戶負責疑難排解因多個 proxy 而造成的任何衝突或不相容性。 您可以使用可設定的設定來新增組織特有的網路 proxy。 如需詳細資訊, 請參閱[可設定的設定](../working-with-managed-desktop/config-setting-ref.md#proxy)。<br><br>如需詳細資訊, 請參閱[Proxy Configuration](../get-ready/network.md)。
列印 | 客戶負責安裝、維護和管理印表機和列印佇列。 雲端列印是建議的解決方案, 但不是必要的。 




