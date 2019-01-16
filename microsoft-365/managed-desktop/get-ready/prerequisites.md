---
title: Microsoft 受管理電腦的先決條件
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.openlocfilehash: 303765d6804071b3a3de18ee412304566cbbe089
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866631"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 受管理電腦的先決條件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Microsoft 受管理的桌上型電腦廣大開頭為已知、 所記載，並同意客戶的基礎結構需求。本節概述這些必要條件。 

Microsoft FastTrack 是可用來協助客戶符合這些需求，以及協助您準備參與現代工作場所以服務方式。如需詳細資訊，請參閱[Microsoft FastTrack](https://fasttrack.microsoft.com/about)。 

範圍 | 必要條件的詳細資訊
--- | ---
授權 | Microsoft 365 E5 授權或對等的授權是必要的。<br><br>此授權包含 Office 365 E5、 Windows 10 企業 E5 與企業行動性 + 安全性 （EMS） E5。如需詳細資訊，請參閱[Microsoft 365 授權](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
連線能力 |  Microsoft 受管理的桌上型電腦的所有裝置連線到許多 Microsoft 服務端點都需要從組織內部的網路，包括：<br>Windows 更新<br>適用於企業的 Microsoft 存放區<br>-Azure Active Directory<br>Windows 錯誤報告<br>-線上損毀分析<br>連線的使用者經驗及遙測<br>-Windows 10 OneDrive 應用程式<br><br>及的完整清單所需 IP 的[Proxy 組態](../get-ready/network.md)中可以找到的 Url。 
Azure Active Directory |    Azure Active Directory (Azure AD) 必須是所有的使用者帳戶的授權來源或使用者帳戶必須使用 Azure AD 連線、 版本 1.1.654.0 的內部部署 Active directory 同步處理或更新版本。如需詳細資訊，請參閱[Azure AD 連線](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。
驗證 |    如果 Azure AD 不是使用者帳戶的授權來源，您必須設定其中一個在 Azure AD 連線：<br>-密碼雜湊同步處理 （建議）<br>-Passthrough 驗證<br>-使用 ADFS 同盟<br><br>設定驗證選項與時 Azure AD 連線密碼回寫也是必要的。如需詳細資訊，請參閱[密碼回寫](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。<br><br>如需有關 Azure AD 驗證選項的詳細資訊，請參閱[Azure AD 連線使用者登入選項](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Office 365 |    強烈建議雲端可移轉下列服務：<br>-電子郵件-移轉至雲端架構信箱，Exchange online 或 Exchange Online 混合使用 Exchange 2013 或更高，內部部署與設定。<br>檔案及資料夾 – 移轉至 SharePoint Online/Office 365。<br>-Skype for Business – 移轉至 Skype for Business Online]。
裝置管理 | Microsoft Intune-僅限雲端 MDM 解決方案 （非混合） 是必要的這可讓 IT 系統管理員能夠管理 Microsoft 受管理的桌上型電腦裝置世界中隨處使用可從 web 主控台。Microsoft Intune 是必要的 MDM 解決方案。<br><br>如需詳細資訊，請參閱[Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
資料備份及復原 | Microsoft 受管理的桌上型電腦需要同步處理至 OneDrive for Business 的保護的檔案。無法同步處理至 OneDrive for Business 任何檔案不保證由 Microsoft 受管理的桌上型電腦，可能會遺失裝置交換或需要裝置重設的支援呼叫期間。Microsoft 受管理的桌上型電腦不支援對應的網路磁碟機。  

[了解如何符合 Microsoft 受管理的桌上型電腦註冊的必要條件。](../get-ready/index.md)

當您準備好開始使用 Microsoft 受管理的桌上型電腦時，請連絡您的 Microsoft 帳戶管理員。 
