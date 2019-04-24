---
title: Microsoft 的必要條件受管理的電腦
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8d9c008af9531bc5b829d248665dc5b58ac6034b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277384"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 的必要條件受管理的電腦

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

使用 Microsoft 受管理電腦的成功開頭已知、 記錄，且同意的客戶的基礎結構需求。 本節概述這些 infastructure 需求。 

Microsoft FastTrack 是可協助客戶符合這些需求和協助您準備參與 Microsoft 受管理的電腦。 如需詳細資訊，請參閱 < <b0>Microsoft FastTrack</b0>。 

範圍 | 必要條件的詳細資料
--- | ---
授權 | 每個 MMD 使用者必須被指派其中一個下列的授權選項：<br>-Microsoft 365 E5<br>-Microsoft 365 E3、 Enterprise Mobility + Security E5 及 Windows 10 企業版 E5<br>-Office 365 E3、 Enterprise Mobility + Security E5 及 Windows 10 企業版 E5<br><br>現有 Enterprise Agreement 客戶可能需要遵循相關指導，以啟用 Azure AD 租用戶中的 Windows 10 企業版訂閱啟用。 如需詳細資訊，請參閱[部署 Windows 10 企業版授權](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses#enabling-subscription-activation-with-an-existing-ea)。<br><br>可以使用安全性群組設定 Azure AD 群組為基礎的授權指派的產品授權。 如需詳細資訊，請參閱 <<c0>什麼是在 Azure Active Directory 群組為基礎的授權。<br><br>如需可用授權的詳細資訊，請參閱[Microsoft 365 授權](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
連線能力 |  Microsoft 受管理電腦的所有裝置都需要許多 Microsoft 服務端點從公司網路的連線。<br><br>如需 Ip 和 Url 的完整清單，請參閱[網路組態](../get-ready/network.md)。 
Azure Active Directory |    Azure Active Directory (Azure AD) 必須是來源的授權單位以取得所有使用者帳戶，或必須從內部部署 Active Directory 使用最新支援的版本的 Azure AD Connect 同步處理使用者帳戶。<br><br>如需有關 Azure AD Connect 的詳細資訊，請參閱[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>如需有關支援 Azure AD Connect 版本，請參閱[Azure AD Connect： 版本版本歷程記錄](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)。
驗證 |    如果 Azure AD 不是使用者帳戶的授權來源，您必須設定其中一個，在 Azure AD Connect 中：<br>-密碼雜湊同步處理<br>-傳遞驗證<br>-使用 ADFS 同盟<br><br>設定時的 Azure AD Connect 的驗證選項，則也需要密碼回寫。 如需詳細資訊，請參閱[密碼回寫](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>如需有關與 Azure AD 的驗證選項的詳細資訊，請參閱[Azure AD Connect 使用者登入選項](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Office 365 |    雖然不需要進行註冊 Microsoft 受管理的電腦時，我們建議下列服務移轉至雲端：<br>-電子郵件-移轉至雲端架構信箱，Exchange online，或使用 Exchange Online 混合式 Exchange 2013 或更高版本，在內部設定。<br>-檔案和資料夾 – 商務/SharePoint online 移轉至 OneDrive。<br>-線上共同作業工具 – 移轉至 Teams。
裝置管理 | Microsoft 受管理的電腦裝置需要使用 Microsoft Intune 管理。 Intune 必須設定為行動裝置管理授權單位。<br><br>如需詳細資訊，請參閱 < <b0>Microsoft Intune</b0>。 
資料備份及復原 | Microsoft 受管理的電腦需要保護先同步至商務用 OneDrive 的檔案。 任何未同步處理至商務用 OneDrive 的檔案不保證由 Microsoft 受管理的電腦，且可能會遺失裝置交換或需要裝置重設的支援通話期間。<br><br>雖然並非必要，Microsoft 受管理電腦強烈建議您從對應的網路磁碟機移轉至適當的雲端解決方案。  

當您準備好要開始使用 Microsoft 受管理的電腦時，請連絡您的 Microsoft 帳戶管理員。 
