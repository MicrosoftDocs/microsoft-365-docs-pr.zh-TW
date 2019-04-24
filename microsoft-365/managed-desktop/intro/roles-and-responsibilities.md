---
title: Microsoft 受管理電腦角色和責任
description: 本主題說明的角色和責任 Microsoft 所提供的 Microsoft 受管理的電腦。
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 161be07907754cdd7a0cd88dd3342d4b5e3c72e4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283556"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft 受管理電腦角色和責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

當您的組織已註冊 Microsoft 受管理電腦中時，Microsoft 的作用為何您？ 以及為何您組織的責任？

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft 的角色和責任

以下是幾個重要的角色和會由 Microsoft 提供給您的責任。

角色或責任 | 說明
--- | ---
MDM 原則管理 | Microsoft 將會套用 MDM 原則根據最佳作法，並且考慮的原則變更要求。 我們也會對您的租用戶前述[裝置原則](../service-description/device-policies.md)進行變更。
使用者支援 | Microsoft 會提供使用者支援的裝置、 Windows 及 Office 的所有註冊的使用者，透過取得說明應用程式上所有的 Microsoft 受管理的電腦裝置已預先安裝的產品套件。 
Microsoft 受管理的電腦服務支援 | Microsoft 會提供支援給客戶 IT 部門透過 Microsoft 受管理的桌上型電腦作業小組。 此小組會支援技術的疑難排解，請變更要求和事件管理客戶的 Microsoft 受管理的桌上型電腦環境。 如需詳細資訊，請參閱 <<c0>支援的 Microsoft 受管理電腦的系統管理員。
安全性監視 | Microsoft 會監視客戶 Microsoft 受管理的電腦裝置使用 Windows Defender ATP。 如果威脅偵測到由 Microsoft 受管理的桌面安全性作業中心 (SOC)，Microsoft 將會通知客戶、 隔離裝置，並修正此問題： 從遠端。 如需詳細資訊，請參閱 < <b0>Security</b0>。
監視和管理更新 | Microsoft 將主動監視客戶 Microsoft 受管理的電腦裝置，以確保 Microsoft Windows 和 Microsoft Office 安裝最新的品質與功能更新。 如需詳細資訊，請參閱[更新的處理方式](../service-description/updates.md)。
使用者和裝置群組 | Microsoft 受管理電腦作業小組會建立及管理必要的裝置和使用者群組的 IT 作業過程。 這些群組允許沒有成員資格或組態變更。 更換這些群組可能會導致未預期的裝置設定與遺失的功能。 對於任何問題或周圍一次建立這些群組的問題，IT 系統管理員可以連絡 Microsoft 受管理電腦作業。 如需詳細資訊，請參閱 <<c0>支援的 Microsoft 受管理電腦的系統管理員。

## <a name="your-roles-and-responsibilities"></a>您的角色和責任

下面是常見的角色和責任，未提供的 Microsoft，但成功部署所需的其他設定。 它不是詳盡，但適用於大多數的組織。 有幾項目下方 Microsoft 與客戶共用 responsibilties。 

角色或責任 | 說明
--- | ---
變更管理 | Microsoft 會事先通知客戶，時對其 Microsoft 受管理的桌上型電腦環境需要變更。 需要有自己的變更管理處理程序，必須與 Microsoft 受管理的桌上型電腦作業小組建立連絡人客戶。 客戶也需要檢閱及核准這些變更的資源。 如需詳細資訊，請參閱[作業和監控](../service-description/operations-and-monitoring.md)。  
身分識別管理 | 客戶負責建立使用者帳戶指派使用者至群組，將中繼資料保持在最新狀態。 
Office 365 組態和管理 | Microsoft 負責確保 Office 應用程式會部署至使用者，且這些應用程式會保持在最新狀態。 <br><br> 客戶負責管理 Office 365 服務和原則，包括 Exchange Online 的管理責任：<br>電子郵件管理<br>信箱及規則設定<br>Exchange 內部部署管理<br><br>客戶也負責進行共同作業工具、 SharePoint server 管理、 網域管理、 設定 Office 365 系統管理入口網站中的安全性和資訊原則。 
使用者支援 | 客戶負責提供使用者支援： <br>-在站台基礎結構： 所有網路和網際網路連線能力、 VPN 基礎結構和用戶端組態、 本機的會議房間設備、 印表機、 proxy 伺服器和防火牆的組態。<br><br>-全公司雲端資源： 電子郵件、 SharePoint、 共同作業服務和其他雲端基礎結構與相關的全公司的技術使用量。<br><br>-一行商務和任何其他公司特定應用程式。
App | Microsoft 會提供核准要求時使用 Intune 的應用程式的部署指導。<br><br>客戶負責：<br>-提供其組織 （外部 Office 365 應用程式） 的應用程式清單<br>應用程式授權管理<br>– 具有授權的數量和正確的類型<br>應用程式工作分派<br>– 應用程式指派給 Azure AD 使用者群組<br>應用程式更新<br>– 監視、 封裝，以及部署應用程式功能和安全性更新<br>使用者應用程式測試 (UAT)<br>-提供適當的可部署套件<br><br>如需詳細資訊，請參閱[應用程式](../get-ready/apps.md)
安全性監視和回應 | 客戶負責調查並解決的非-Microsoft 受管理的電腦裝置，以確保 Microsoft 受管理的桌上型電腦作業小組會通知可能會影響服務的任何問題的事件。
作業支援 | 客戶負責提供慣用的客戶連絡人與主題專家所提供的清單。 Microsoft 會需要這些非-Microsoft 受管理電腦作業事件的情況下。 <br><br>客戶也負責進行調查並解決非-Microsoft 受管理的電腦裝置和服務及確保 Microsoft 受管理的桌上型電腦作業小組會永遠通知事件。
網路基礎結構，包括 VPN | 客戶負責安裝、 設定及管理 （包括疑難排解及偵錯） 的所有網路相關的基礎結構和服務，包括網際網路連線能力，網路控制項、 proxy 設定及遠端連線基礎結構。<br><br>如果 proxy 設定 （在硬體或軟體），還有一群必須 proxy 所允許的 Url。 客戶負責疑難排解任何衝突或不相容，因為多個 proxy。 您可以新增網路 proxy 特定組織使用可設定的設定。 如需詳細資訊，請參閱 <<c0>組態設定。<br><br>如需詳細資訊，請參閱[Proxy 設定](../get-ready/network.md)。
列印 | 客戶負責安裝、 維護及管理印表機和列印佇列。 雲端列印是建議的解決方案，但不是必要。 




