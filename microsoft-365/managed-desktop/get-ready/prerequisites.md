---
title: Microsoft 受管理電腦的先決條件
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 041e7dc89ddd42326ce0a5040364306e26fd2413
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653386"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 受管理電腦的先決條件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

本主題概述您必須符合，以確保 Microsoft Managed Desktop 成功的基礎結構需求。 

Microsoft FastTrack 可協助您符合這些需求，協助您準備加入 Microsoft 受管理的桌面。 如需詳細資訊，請參閱[Microsoft FastTrack](https://fasttrack.microsoft.com/about)。 

範圍 | 必要條件詳細資料
--- | ---
授權 |Microsoft 受管理的桌面需要下列其中一個 Microsoft 365 授權 (或對應) ：<br>-Microsoft 365 E5<br>-使用 Microsoft 365 E5 安全性附加元件的 microsoft 365 E3<br><br>如需 Microsoft Managed Desktop 中特定服務方案及其角色的詳細資訊，請參閱本主題中的[相關授權](#more-about-licenses)。<br>如需可用授權的詳細資訊，請參閱[Microsoft 365 授權](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
連線能力 |  所有 Microsoft 受管理的桌面裝置都需要從公司網路連接至眾多的 Microsoft 服務端點。<br><br>如需必要 IPs 和 URLs 的完整清單，請參閱[Network configuration](../get-ready/network.md)。 
Azure Active Directory |    Azure Active Directory (Azure AD) 必須是所有使用者帳戶的授權來源，或是必須使用最新版的 Azure AD Connect 從內部部署 Active Directory 同步處理使用者帳戶。<br><br>必須對 Microsoft 受管理的桌面使用者啟用[企業狀態漫遊](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview)。<br><br>如需詳細資訊，請參閱[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>如需支援的 Azure AD Connect 版本的詳細資訊，請參閱[AZURE Ad connect：版本發行歷程記錄](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)。
驗證 |    如果 Azure AD 不是使用者帳戶的主要驗證來源，您必須在 Azure AD Connect 中設定下列其中一項：<br>-密碼雜湊同步處理<br>傳遞驗證<br>-外部身分識別提供者 (，包括 Windows Server ADFS 和非 Microsoft IDPs) 設定為符合 Azure AD 整合需求。 如需詳細資訊，請參閱[指導方針](https://www.microsoft.com/en-us/download/details.aspx?id=56843)。 <br><br>使用 Azure AD Connect 設定驗證選項時，也建議使用密碼回寫。 如需詳細資訊，請參閱[密碼回寫](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>如果已執行外部身分識別提供者，則必須驗證解決方案：<br>-符合 Azure AD 整合需求<br>-支援 Azure AD 條件式存取，這是為了啟用設定 MMD 裝置合規性原則<br>-啟用裝置註冊，並使用 microsoft 365 服務或 Microsoft 受管理桌面的一部分所需功能 <br><br>如需 Azure AD 驗證選項的詳細資訊，請參閱[AZURE Ad Connect 使用者登入選項](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Microsoft 365 | 必須為 Microsoft 受管理的桌面使用者啟用商務 OneDrive。<br><br>雖然不需要向 Microsoft 受管理的桌上型電腦註冊，我們強烈建議您將下列服務遷移至雲端：<br>-電子郵件：以 exchange Online 混合方式遷移至雲端架構信箱、Exchange online，或使用 exchange 2013 或更高版本（內部部署）進行設定。<br>-檔案和資料夾：針對商務或 SharePoint 線上，遷移至 OneDrive。<br>-線上共同作業工具：向小組遷移。
裝置管理 | Microsoft 受管理的桌面裝置需要使用 Microsoft Intune 進行管理。 必須將 Intune 設定為行動裝置管理授權。<br><br>如需詳細資訊，請參閱[Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
資料備份和復原 | Microsoft 受管理的桌面需要將檔案同步處理至 OneDrive 以供商務用以進行保護。 Microsoft 受管理的桌面不會保證任何未同步處理至商務 OneDrive 的檔案，也可能會在更換裝置時或支援裝置重設的呼叫期間遺失。<br><br>Microsoft 受管理的電腦強烈建議您從對應的網路磁碟機遷移至適當的雲端解決方案，但這不是必要的。 如需詳細資訊，請參閱為[Microsoft Managed Desktop 準備對應的磁片磁碟機](mapped-drives.md)

當您準備好開始使用 Microsoft Managed Desktop 時，請與您的 Microsoft 帳戶管理員聯繫。 

## <a name="more-about-licenses"></a>有關授權的詳細資訊

Microsoft 受管理的桌面需要某些授權選項才能正常運作。 這些選項可用於許多不同的授權捆綁，有些您可能已經擁有。 下表顯示哪些授權可使用哪些授權，以及如何在 Microsoft 受管理的電腦中匯總其角色。

> [!TIP]
> 若要將這些授權選項指派給特定使用者，建議您利用 Azure Active Directory 的[群組型授權功能](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。



|授權選項 |可在*這些*許可證產品中使用 |Microsoft 受管理的桌面如何使用它|
|-------------|-------------|-------------|
|Azure Active Directory Premium P2     |-Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5*安全性附加元件<br>-企業行動 + 安全性 E5<br>-Enterprise 可移動性 + Security E3<br>-Azure Active Directory Premium P2|  提供 Microsoft Cloud Services 的存取權;允許 AutoPilot 註冊裝置      |
|Microsoft Intune | -Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5*安全性附加元件<br>-企業行動 + 安全性 E5<br>-Enterprise 可移動性 + Security E3<br>-Microsoft Intune  |  註冊裝置、部署更新及管理裝置所需       |
|Windows 10 企業版  |-Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5*安全性附加元件<br>-Windows 10 企業版 E3<br>-Windows 10 企業版 E5 | 提供 Windows 10 的企業版功能       |
|Microsoft Defender 進階威脅防護 | -Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5*安全性附加元件<br>-Windows 10 企業版 E5<br>-Microsoft Defender 高級威脅防護   |  提供偵測、監控、對威脅的警示和回應  |
|Microsoft 365 Apps 企業版  |-Microsoft 365 E5<br>-Microsoft 365 E3<br>-Office 365 E5<br>-Office 365 E3| 啟用 Office 和生產力與共同作業工具    |

> [!TIP]
> 您的 Microsoft 帳戶管理員會協助您檢查目前的授權和服務方案，並尋找最有效率的路徑，讓您能取得任何其他可能需要的授權或服務方案，同時避免重複。
