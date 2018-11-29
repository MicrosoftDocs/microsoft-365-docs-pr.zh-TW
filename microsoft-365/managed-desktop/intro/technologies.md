---
title: Microsoft 受管理的桌上型電腦技術
description: 本主題將列出的技術及 Microsoft 受管理的桌上型電腦中所使用的應用程式。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: da0268c6b0eddbd44cf62de2a95b963a443c3278
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866324"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 受管理的桌上型電腦技術

本主題將列出的技術及 Microsoft 受管理的桌上型電腦中所使用的應用程式。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 E5 授權 （或對等資格），則需要 Microsoft 受管理的桌上型電腦服務。以下是此授權與 Microsoft 受管理的桌上型電腦與 Microsoft 受管理的桌上型電腦裝置所使用的每個元件中所包含的所有元件。 特定的角色與責任每個區域的詳細說明整個 Microsoft 受管理的桌上型電腦的主題。 

Microsoft 365 E5 由 3 元件組成： Office 365 E5、 Windows 10 Enterprise 和 E5、 企業行動性 + 安全性 E5。  

## <a name="office-365-e5"></a>Office 365 E5
 |
 --- | ---
Office 365 Standard Suite （64 位元） * | 標準 Office 套件的應用程式將隨附裝置： Word、 Excel、 PowerPoint、 Outlook、 Publisher、 存取、 Skype for Business、 OneNote。<br><br>按一下此選項即可執行 64 位元 (C2R) 完整版本的 Microsoft Project 與 Microsoft Visio 不會包含在 Office 365 Standard Suite。 不過，這些應用程式的安裝都取決於標準 Office 套件安裝，因為 Microsoft 受管理的桌上型電腦已建立預設 Intune 部署和客戶會部署至這些應用程式使用的安全性群組授權給使用者。  
儲存應用程式 |    Microsoft Sway、 的 Microsoft 小組、 Power BI 桌面 （不專業人員） 未隨附於裝置。這些應用程式都可供下載 （英文） 從 Microsoft 存放區。
Win32 應用程式 |    Power BI Pro、 Azure 資訊保護用戶端及 Microsoft 規劃未隨附於裝置並可由客戶封裝部署。 
Web 應用程式 |  Yammer，Office Online Delve、 流程 StaffHub、 PowerApps 未隨附於裝置。使用者可存取 web 瀏覽器中使用這些應用程式版本。
Skype 商務線上雲端 PBX | 這項功能是透過 Office 365 E5。Microsoft 受管理的桌上型電腦將不會設定這項服務的任何層面

## <a name="windows-10-enterprise-e5"></a>Windows 10 企業 E5

 |
 --- | ---
認證 Guard |  Microsoft 受管理的桌上型電腦將提供相關指導和管理的這項功能的雲端層面
裝置 Guard （Windows 防禦者應用程式控制項）   | Microsoft 受管理的桌上型電腦會建立原則。客戶管理簽章
AppLocker 管理 |  Microsoft 受管理的桌上型電腦會建立原則。客戶管理簽章
Application Virtualization (APP-V) |    當它不支援 Intune Microsoft 受管理的桌上型電腦不支援這種類型的部署。
使用者經驗虛擬化 (使用者教育 V) | 這不會使用與受管理的 Microsoft 受管理的桌上型電腦裝置
受管理的使用者經驗  | 這不會使用與受管理的 Microsoft 受管理的桌上型電腦裝置。MDM 作為解決方案的裝置管理
Windows Defender 進階威脅防護 |   這是由 Microsoft 受管理的桌上型電腦用來管理裝置安全性原則。 

## <a name="enterprise-mobility--security"></a>企業行動力 + 安全性 

 |
 --- | ---
Enterprise 行動性 + 安全性 E3<br>Azure Active Directory Premium P2 |    Enterprise 行動性 + 安全性 E3 及 AADP 各方面的可能會用來管理 MDM 裝置
Microsoft Cloud App Security |  這是選用的功能，客戶可以使用與 Microsoft 受管理的桌上型電腦服務。
Azure 的資訊保護 P2  |這是選用的功能，客戶可以使用與 Microsoft 受管理的桌上型電腦服務。