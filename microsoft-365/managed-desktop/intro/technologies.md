---
title: Microsoft 受管理電腦技術
description: 本主題列出在 Microsoft 受管理電腦中使用的應用程式與技術。
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 843a8cd066bbaf87a8b2b7cc74d8817207e47153
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283465"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 受管理電腦技術

本主題列出在 Microsoft 受管理電腦中使用的應用程式與技術。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 企業版授權，則需要為 Microsoft 受管理電腦的所有使用者。 如需有關服務的授權需求的詳細資訊，請參閱 < <b0>Microsoft 受管理電腦的必要條件</b0>。

以下是必要的企業授權及服務與 Microsoft 受管理的電腦裝置所使用的每個元件中包含的所有元件。 每個區域的特定角色和責任的詳細資訊整個 Microsoft 受管理電腦主題。 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite （64 位元） * | 標準的 Office 應用程式套件將會隨附裝置： Word、 Excel、 PowerPoint、 Outlook、 Publisher、 Access、 Skype for Business，OneNote。<br><br>64 位元隨選 (C2R) 的 Microsoft Project 和 Microsoft Visio 的完整版本不包含在 Office 365 Standard Suite。  不過，由於這些應用程式的安裝是取決於標準 Office 套件安裝，Microsoft 受管理的電腦已建立預設 Intune 部署和安全性群組，客戶會用來部署這些應用程式授權使用者。  
市集應用程式 |    Microsoft Sway、 Power BI Desktop 未隨附於裝置。 這些應用程式可供從 Microsoft Store 下載。
Win32 應用程式 |    Power BI 專業人員、 Azure 資訊保護用戶端，Microsoft Planner 未隨附於裝置並可由客戶封裝部署。 
Web 應用程式 |  Yammer，Office Online，Delve、 流程、 StaffHub、 PowerApps 未隨附於裝置。 使用者可以存取這些應用程式與瀏覽器網頁版。
Skype 商務線上雲端 PBX | 這項功能可透過 Office 365。 Microsoft 受管理電腦將不會設定這項服務的任何層面

## <a name="windows-10-enterprise-e5"></a>Windows 10 企業版 E5

 |
 --- | ---
Credential Guard |  Microsoft 會提供指引，以及管理雲端的這項功能的各個層面。
裝置 Guard （Windows Defender 應用程式控制） | Microsoft 受管理的電腦會建立原則。 <br><br>客戶會管理簽章。
AppLocker 管理 |  Microsoft 將會建立原則。 <br><br>客戶會管理簽章。
Application Virtualization (APP-V) |    Microsoft 受管理的電腦不支援這種類型的部署，因為它不支援 Intune。
使用者經驗虛擬化 (使用者教育 virtualization，AMD-V) | 這不會使用與受管理的 Microsoft 受管理電腦裝置。
受管理的使用者經驗  | 這不會使用與受管理的 Microsoft 受管理電腦裝置。 MDM 會當做裝置管理解決方案。
Windows Defender 進階威脅防護 |   這是 Microsoft 受管理電腦用來管理裝置安全性原則。 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
企業行動力 + 安全性版 E3<br>Azure Active Directory 進階版 P2 |    企業行動力 + 安全性版 E3 和 AADP 的所有層面可能都用來管理 MDM 裝置。
Microsoft Cloud App Security |  這是選擇性功能，客戶可以使用 Microsoft 受管理的電腦服務。
Azure 資訊保護 P2  |這是選擇性功能，客戶可以使用 Microsoft 受管理的電腦服務。
