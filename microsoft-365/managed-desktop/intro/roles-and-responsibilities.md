---
title: Microsoft 受管理的電腦角色和責任
description: 本文說明 Microsoft 為 Microsoft 受管理的電腦提供的角色和責任。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7b9efe1a52c108e3de46429d64f9a5535ad13e4e
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362747"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft 受管理的電腦角色和責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

當您的組織註冊 Microsoft 受管理的電腦時，Microsoft 會為您做什麼？ 您的組織的責任為何？

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft 的角色與責任

Microsoft 提供下列主要角色和責任：

角色或責任 | 描述
--- | ---
MDM 原則管理 | Microsoft 會根據最佳作法套用 MDM 原則，並考慮原則變更的要求。 我們也會依照 [裝置原則](../service-description/device-policies.md)中的規定，對租使用者進行變更。
使用者支援 | 我們提供一種機制，以提升裝置存取權，並在必要時上報問題。 如需詳細資訊，請參閱 [使用者支援](../service-description/user-support.md)。
Microsoft 受管理的電腦服務支援 | Microsoft 將透過 Microsoft 受管理的電腦運作小組為您的 IT 部門提供支援。 此小組將支援客戶的 Microsoft 受管理的電腦環境的技術疑難排解、變更要求和事件管理。 如需詳細資訊，請參閱[Microsoft 受管理的電腦的系統管理員支援](../working-with-managed-desktop/admin-support.md)。
安全性監視 | microsoft 將使用 microsoft Defender for Endpoint 來監視您的 Microsoft 受管理的電腦裝置。 如果 Microsoft 受管理的電腦的安全性作業中心 (SOC) 偵測到威脅，我們會通知您、隔離裝置，並以遠端方式修正問題。 如需詳細資訊，請參閱 [安全性](../service-description/security.md)。
更新監控與管理 | 我們積極監控您的 Microsoft 受管理的電腦裝置，以確保為 Microsoft Windows 和 Microsoft Office 安裝最新的品質和功能更新。 如需詳細資訊，請參閱 [如何處理更新](../service-description/updates.md)。
使用者和裝置群組 | Microsoft 受管理的電腦運作小組會建立及管理必要的裝置和使用者群組做為 IT 作業的一部分。 這些群組不允許任何成員資格或設定變更。 變更這些群組可能會造成裝置的意外設定和功能喪失。 如需在建立這些群組之後的任何問題或問題，IT 系統管理員可以聯繫 Microsoft 受管理的電腦作業。 如需詳細資訊，請參閱[Microsoft 受管理的電腦的系統管理員支援](../working-with-managed-desktop/admin-support.md)。

## <a name="your-roles-and-responsibilities"></a>您的角色與責任

部署時需要這組共同角色和責任，但不是由 Microsoft 提供。 這不是詳盡，但適用于大部分的組織。 您和 Microsoft 共同擔負的部分專案。 

角色或責任 | 描述
--- | ---
變更管理 | 當需要對其 Microsoft 受管理的電腦環境進行變更時，Microsoft 會事先通知客戶。 如需詳細資訊，請參閱 [服務變更和通訊](../service-description/servicechanges.md)。<br><br>您必須要有自己的變更管理程式，並讓 Microsoft 受管理的電腦運作小組建立連絡人。 您也必須要有資源，才能複查及核准這些變更。 如需詳細資訊，請參閱 [Operations and monitoring](../service-description/operations-and-monitoring.md)。  
身分識別管理 | 您負責建立使用者帳戶、將使用者指派給群組，以及將中繼資料保持在最新狀態。 
Microsoft 365 Apps 企業版設定與管理 | Microsoft 負責確定為使用者部署 Office 的應用程式，而這些應用程式會維持在最新狀態。 <br><br> 您負責管理 Microsoft 365 服務和原則，包括 Exchange Online 管理責任：<br>-電子郵件管理<br>-信箱和規則設定<br>-Exchange 內部部署管理<br><br>您也負責共同作業工具、SharePoint 伺服器管理、網域管理，以及在 Microsoft 365 系統管理中心中設定的安全性和資訊原則。 
使用者支援 | 透過您或透過指定的支援合作夥伴，為使用者提供的第一個連絡人的所有使用者支援和技術援助。 您必須直接提供使用者支援，或與合作夥伴合作以提供下列方面的支援： <br><br>-現場基礎結構：所有網路及網際網路連線、VPN 基礎結構及用戶端設定、本機會議會議室設備、印表機、proxy 伺服器和設定，以及防火牆。<br><br>-全公司的雲端資源：電子郵件、SharePoint、共同作業服務，以及其他與整個公司的技術空間有關的雲端基礎結構。<br><br>-業務線和任何其他公司特定的應用程式。
應用程式 | 角色和責任因 Microsoft 受管理的電腦和您所提供的應用程式所提供的應用程式稍有不同。 <br><br>針對 microsoft (提供的應用程式 Microsoft 365 Apps 企業版組成 Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype、Teams 和 OneNote) ， **Microsoft** 將為部署、更新及支援提供完整服務。 **您** 必須取得並指派這些應用程式的授權、將使用者新增至安全性群組、管理生命週期，以及部署您所需的任何附加元件。<br><br>針對您提供 (的應用程式，例如您的企業營運應用程式) ，不論是自行打包，還是要與非 Microsoft 供應商 **接洽，以** 進行下列動作： <br><br>-識別目標使用者群組所需的應用程式<br>-針對應用程式部署建立及管理 Azure AD 群組<br>-打包應用程式以符合 Microsoft Intune 部署標準<br>-將應用程式上傳至 Microsoft Intune<br>-測試 Microsoft 受管理的電腦環境中的應用程式<br>-隨使用者測試應用程式<br>-管理及指派使用者至應用程式<br>-透過 Microsoft Intune 識別及部署應用程式更新<br>-卸載並移除已停用的應用程式<br>-購置和指派授權<br>-提供使用者對企業營運應用程式的支援<br>-遠端管理應用程式設定<br><br>**Microsoft** 會提供 Microsoft Intune 部署工具，將應用程式傳送至遠端用戶端。<br><br>如需詳細資訊，請參閱 [應用程式](../get-ready/apps.md)。
安全性監視和回應 | 您負責調查和解決未 Microsoft 受管理的電腦裝置之裝置的事件，並確保 Microsoft 受管理的電腦作業小組獲悉任何可能會影響服務的問題。
作業支援 | 您必須提供組織中偏好的連絡人和主題專家的清單。 如果有與 Microsoft 受管理的電腦無關的作業事件，我們需要這些連絡人。 <br><br>您也負責調查和解決不在 Microsoft 受管理的電腦中之裝置和服務的事件，並確保永遠知道 Microsoft 受管理的電腦作業團隊。
網路基礎結構（包含 VPN） | 您負責設定、設定和管理 (，包括所有網路相關基礎結構和服務的疑難排解與調試) ，包括網際網路連線、網路控制、proxy 設定及遠端連線基礎結構。<br><br>如果已在硬體或軟體) 中 (設定 proxy，則必須有 proxy 的 URLs 集合。 您負責疑難排解因多個 proxy 的任何衝突或不相容性。 您可以使用可設定的設定，新增組織特有的網路 proxy。 如需詳細資訊，請參閱 [可設定的設定](../working-with-managed-desktop/config-setting-ref.md#proxy)。<br><br>如需詳細資訊，請參閱 [Proxy Configuration](../get-ready/network.md)。
列印 | 您負責安裝、維護及管理印表機及列印佇列。 雲端列印是建議的解決方案，但不是必要的。 




