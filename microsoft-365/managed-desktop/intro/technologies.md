---
title: Microsoft 受管理的電腦技術
description: 本主題列出 Microsoft 受管理的桌面中所用的技術和應用程式。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4af346877b41b03c07750508ff93661cc642ec4
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289102"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 受管理的電腦技術

本主題列出 Microsoft 受管理的桌面中所用的技術和應用程式。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

所有 Microsoft 受管理的桌面使用者都需要 microsoft 365 企業版授權。 如需服務授權需求的詳細資訊，請參閱 [Microsoft Managed Desktop 的必要條件](../get-ready/prerequisites.md)。

本主題摘要說明所需企業授權中包含的元件，並說明服務如何使用每個元件與 Microsoft 受管理的桌面裝置。 在整個 Microsoft 受管理的桌面檔中會詳細說明每個區域的特定角色和責任。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 或 E5
 |
 --- | ---
適用于企業的 Microsoft 365 應用程式 (64-位)  | 這些 Office 應用程式會隨裝置運送： Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype、OneNote。<br><br>不包含 Microsoft Project 和 Microsoft Visio 的64位完整版本。 不過，由於安裝這些應用程式取決於 Microsoft 365 應用程式的 enterprise 安裝，因此 Microsoft Managed Desktop 已建立預設的 Microsoft Intune 部署和安全性群組，您可以用來將這些應用程式部署至授權的使用者。 如需詳細資訊，請參閱 [在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio](../get-started/project-visio.md)。
商務用 OneDrive |在第一次登入商務用 OneDrive 時，會為使用者啟用 Azure Active Directory 單一登入。<br><br>包含「桌面」、「檔」及「圖片」資料夾的已知資料夾重新導向;由 Microsoft Managed Desktop 啟用和設定。 
儲存應用程式 |    Microsoft Sway 和 Power BI 未附帶裝置。 這些應用程式可從 Microsoft Store 下載。
Win32 應用程式 |    小組未附帶裝置，但是會打包並由 Microsoft 提供給 Microsoft 受管理的桌面裝置。 Azure 資訊保護用戶端未附帶裝置，但是您可以將此裝置打包以進行部署。 
Web 應用程式 |  在瀏覽器中的 [Yammer]、「Delve」、「流程」、「StaffHub」、「PowerApps」及「Planner」都不會隨裝置附帶。 使用者可以使用瀏覽器存取這些應用程式的 web 版本。


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 企業版 E3 或 E5

 |
 --- | ---
Application Virtualization (App-V)  |    客戶可以使用 Intune Win32 應用程式管理用戶端部署 App-V 套件。
Microsoft Defender 進階威脅防護 |  Microsoft 受管理的桌面用來監視裝置安全性。 

## <a name="enterprise-mobility--security-e5"></a>企業行動 + 安全性 E5

 |
 --- | ---
企業行動性 + 安全性 E3<br>Azure Active Directory Premium P2 |    您可以使用企業行動裝置 + Security E3 和 Azure Active Directory Premium P2 的所有功能來管理 MDM 裝置。
Microsoft Cloud App Security |  您可以將此選用功能與 Microsoft Managed Desktop 搭配使用。
Azure 資訊保護 P2  | 您可以將此選用功能與 Microsoft Managed Desktop 搭配使用。
