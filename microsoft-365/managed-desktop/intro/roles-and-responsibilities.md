---
title: Microsoft 受管理的桌上型電腦的角色與責任
description: 本主題說明的角色與 Microsoft 提供的 Microsoft 受管理的桌上型電腦的責任。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 923cde6353e4ff5122317f2c053fef244ee7e1b6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
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
應用程式部署 | Microsoft 會部署至用戶端之間的 Microsoft 受管理的桌上型電腦裝置使用 Intune 的已核准應用程式。如需詳細資訊，請參閱[應用程式](../get-ready/apps.md)。 
使用者支援 | Microsoft 會提供使用者支援的裝置、 Windows 及 Office 產品套件的所有註冊的使用者。 
Microsoft 受管理的桌上型電腦服務支援 | Microsoft 會提供支援給客戶 IT 部門有關透過 Microsoft 受管理的桌上型電腦作業小組。此小組會支援技術的疑難排解、 變更要求和事件管理客戶的 Microsoft 受管理的桌上型電腦環境。如需詳細資訊，請參閱[取得支援](../service-description/support.md)。
安全性監控 | Microsoft 會監視使用 Windows 防禦者 ATP 客戶 Microsoft 受管理的桌上型電腦裝置。如果威脅偵測到由 Microsoft 受管理的桌上型電腦安全性作業中心 (SOC)、 Microsoft 將通知客戶、 隔離裝置，並從遠端修正問題。如需詳細資訊，請參閱[安全性](../service-description/security.md)。
更新監視與管理 | Microsoft 將主動監視以確保最新的品質、 功能和定義更新已安裝 Microsoft Windows 與 Microsoft Office 的客戶 Microsoft 受管理的桌上型電腦裝置。如需詳細資訊，請參閱[如何處理更新](../service-description/updates.md)。
裝置採購 | Microsoft 會放置傳送至使用者或 IT 發佈點您選擇的排序的 Microsoft 受管理的桌上型電腦裝置。如需詳細資訊，請參閱[裝置](../get-started/devices.md)。

## <a name="your-roles-and-responsibilities"></a>角色與責任

下面是常見的角色不提供 Microsoft、 但成功部署所需的其他設定。它不是詳盡但一般用於大多數的組織。 

角色或 reponsibility | 描述
--- | ---
變更管理 | Microsoft 受管理的桌上型電腦會通知客戶、 事先，需要在其 Microsoft 受管理的桌上型電腦環境中做的變更。客戶需要有其專屬變更管理程序及所需具備 Microsoft 受管理的桌上型電腦的連絡人。客戶需要檢閱和核准這些變更的資源。如需詳細資訊，請參閱[作業和監控。](../service-description/operations-and-monitoring.md)  
身分識別管理 | 建立使用者帳戶，將使用者指派給群組並保持最新的中繼資料。 
Office 365 設定與管理 | Exchange Oonline 管理包括：<br>電子郵件管理<br>信箱及規則設定<br>Exchange 內部部署管理<br><br>共同作業工具、 SharePoint server 管理、 網域管理、 安全性及資訊原則設定在 Office 365 系統管理入口網站 （Microsoft 受管理的桌上型電腦會確保 Office 應用程式部署至使用者裝置與保持最新）。 
使用者支援 | 客戶提供使用者支援： <br>位在站台基礎架構： 所有網路與網際網路連線、 VPN 基礎結構和用戶端組態、 本機會議會議室設備、 印表機、 proxy 伺服器和防火牆的組態。<br><br>-全公司的雲端資源： 電子郵件、 SharePoint、 共同作業服務及其他雲端基礎結構與全公司的技術之上。<br><br>-主要的商務應用程式： 自訂軟體、 第 3 廠商軟體、 企業資源規劃 (ERP) 軟體、 設計工具及未指定此文件中的任何項目。
使用者和裝置群組 | Microsoft 受管理的桌上型電腦作業小組會建立並管理所需的裝置與使用者群組 IT 作業的一部分。客戶不會透過支援通道的第一個連絡 IT 作業而這些群組以進行變更。所有偵測到變更將會還原。
應用程式 | 客戶提供他們想要在其組織 （超過隨附於 Microsoft 365 授權的應用程式） 中使用的應用程式的清單。客戶也提供可部署套件 （Appx 或 MSI）<br>「 客戶 」 負責：<br>宣告應用程式授權管理 – 具有正確的類型和授權數量<br>宣告應用程式工作分派-以 Azure AD 使用者群組指派應用程式<br>宣告應用程式更新-監視封裝、 和部署應用程式功能與安全性更新<br>使用者應用程式測試 (UAT)<br><br>如需詳細資訊，請參閱[應用程式](../get-ready/apps.md)
安全性監視和回應 | 如果安全性事件會偵測到這是 Microsoft 受管理的桌上型電腦作業的範圍之外，我們需要根據問題的嚴重性的慣用的客戶連絡人的清單。<br><br>客戶負責調查並解決非的 Microsoft 受管理的桌上型電腦裝置和確保 Microsoft 受管理的桌上型電腦作業小組會通知可能會影響服務的所有問題的事件。
作業支援 | Microsoft 受管理的桌上型電腦作業需要慣用的客戶連絡人和主題專家所提供的清單。我們需要這些以防非的 Microsoft 受管理的桌上型電腦操作事件。 <br><br>客戶負責調查並解決非的 Microsoft 受管理的桌上型電腦裝置及服務和確保 Microsoft 受管理的桌上型電腦作業小組一律會通知資訊的事件。
網路基礎結構，包括 VPN | 安裝、 設定及管理 （包括疑難排解和偵錯） 的所有網路相關的基礎結構和服務，包括網際網路連線的網路控制項、 proxy 設定和遠端連線基礎結構。<br><br>根據預設，Microsoft 受管理的桌上型電腦沒有指定或需要 proxy。不過，如果其中一個設定 （在硬體或軟體），是一群必須允許 proxy 的 Url。客戶負責疑難排解任何衝突或不相容性因多個 proxy。<br><br>如需詳細資訊，請參閱[Proxy 設定](../get-ready/network.md)。
列印 | 安裝、 維護及管理印表機與列印的佇列。雲端是建議的解決方案，但不是必要的列印。 
行動裝置 | 裝置及 [附屬應用程式沒有提供 Microsoft 受管理的桌面。Microsoft 受管理的桌上型電腦作業小組僅支援 Microsoft 受管理的桌上型電腦裝置、 膝上型及包含附屬應用程式。




