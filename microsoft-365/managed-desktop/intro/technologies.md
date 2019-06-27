---
title: Microsoft 受管理的桌面技術
description: 本主題列出 Microsoft 受管理的電腦中所使用的技術和應用程式。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9c0e6481d0dc80e7cf03de2b748935c2f59f132a
ms.sourcegitcommit: e54ec86310a18101f4688890cd5a9fc16bbe6f55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2019
ms.locfileid: "35257816"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 受管理的桌面技術

本主題列出 Microsoft 受管理的電腦中所使用的技術和應用程式。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

所有 Microsoft 受管理的桌面使用者都需要 microsoft 365 企業版授權。 如需服務授權需求的詳細資訊, 請參閱[Microsoft 受管理電腦的必要條件](../get-ready/prerequisites.md)。

以下是所需企業授權中包含的所有元件, 以及服務如何使用 Microsoft 受管理的電腦裝置的每個元件。 每個區域的特定角色和責任都是在整個 Microsoft 受管理的桌面主題中詳細說明。 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite (64 位) * | 標準的 Office 套件應用程式會隨附裝置: Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype、OneNote。<br><br>64位的按一下以執行 (C2R) 完整版本的 Microsoft Project 和 Microsoft Visio 不包含在 Office 365 Standard Suite 中。  不過, 由於這些應用程式的安裝取決於標準 Office 套件安裝, Microsoft 受管理的桌面已建立了預設的 Intune 部署和安全性群組, 客戶將使用這些部署來將這些應用程式部署到授權的使用者。  
儲存應用程式 |    Microsoft Sway、Power BI Desktop 不會隨附裝置。 這些應用程式可從 Microsoft Store 下載。
Win32 應用程式 |    Power BI Pro、Azure 資訊保護用戶端和 Microsoft Planner 不會隨附裝置, 且可由客戶進行部署。 
Web 應用程式 |  Yammer、Office Online、Delve、Flow、StaffHub、PowerApps 不會隨裝置一起隨附。 使用者可以使用瀏覽器來存取這些應用程式的 web 版。
商務用 Skype Online Cloud PBX | 此功能可透過 Office 365 取得。 Microsoft 受管理的桌面不會設定此服務的任何方面

## <a name="windows-10-enterprise-e5"></a>Windows 10 企業版 E5

 |
 --- | ---
Credential Guard |  Microsoft 會提供此功能的指引和管理雲端層面。
Application Virtualization (App-v) |    Microsoft 受管理的桌面不支援此類型的部署, 因為 Intune 上不支援此部署。
使用者體驗虛擬化 (UE-V) | 這不是 Microsoft 受管理的桌面受管理裝置使用。
受管理的使用者經驗  | 這不是 Microsoft 受管理的桌面受管理裝置使用。 MDM 是用來做為裝置管理的解決方案。
Windows Defender 進階威脅防護 |   Microsoft 受管理的桌面會使用此功能來管理裝置安全性原則。 

## <a name="enterprise-mobility--security-e5"></a>企業行動 + 安全性 E5

 |
 --- | ---
企業行動性 + 安全性 E3<br>Azure Active Directory Premium P2 |    企業行動性 + 安全性 E3 和 AADP 的所有層面都可以用來管理 MDM 裝置。
Microsoft Cloud App Security |  這是客戶可以搭配 Microsoft 受管理的桌面服務使用的選用功能。
Azure 資訊保護 P2  |這是客戶可以搭配 Microsoft 受管理的桌面服務使用的選用功能。
