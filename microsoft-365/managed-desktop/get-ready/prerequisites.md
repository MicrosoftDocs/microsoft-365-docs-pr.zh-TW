---
title: Microsoft 受管理電腦的先決條件
description: 在註冊 Microsoft 受管理的電腦之前設定的授權、Azure 帳戶、驗證設定和 Microsoft 365 設定
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e4469d8abcfa8308c64e2efa7f7dc4f0156e5718
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957524"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 受管理電腦的先決條件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

本主題概述您必須符合的基礎結構需求，以確保 Microsoft 受管理的電腦的成功。 


區域 | 必要條件詳細資料
--- | ---
授權 |Microsoft 受管理的電腦需要 Microsoft 365 E3 授權才能將 Microsoft Defender 用於端點 (或對等) 指派給您的使用者。<br>如需特定服務方案的詳細資訊，請參閱本主題中 [有關授權的詳細](#more-about-licenses) 資訊。<br>如需可用授權的詳細資訊，請參閱[Microsoft 365 授權](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans)。
連線能力 |  所有 Microsoft 受管理的電腦裝置都需要從公司網路連接許多 Microsoft 服務端點。<br><br>如需必要 IPs 和 URLs 的完整清單，請參閱 [Network configuration](../get-ready/network.md)。 
Azure Active Directory |    Azure Active Directory (azure ad) 必須是所有使用者帳戶的授權來源，或使用者帳戶必須從內部部署 Active Directory 同步處理，但必須使用最新的 Azure AD 連線版本。<br><br>Microsoft 受管理的電腦使用者必須啟用[Enterprise 狀態漫遊](/azure/active-directory/devices/enterprise-state-roaming-overview)。<br><br>如需詳細資訊，請參閱[AZURE AD 連線](/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>如需支援的 Azure AD 連線版本的詳細資訊，請參閱[AZURE AD 連線：版本發行歷程記錄](/azure/active-directory/hybrid/reference-connect-version-history)。
驗證 |    如果 Azure AD 不是使用者帳戶的主要驗證來源，您必須在 Azure AD 連線中設定下列其中一項：<br>-密碼雜湊同步處理<br>傳遞驗證<br>-外部身分識別提供者 (包括 Windows 伺服器 ADFS 和非 Microsoft IDPs) 設定為符合 Azure AD 整合需求。 如需詳細資訊，請參閱 [指導方針](https://www.microsoft.com/download/details.aspx?id=56843) 。 <br><br>使用 Azure AD 連線設定驗證選項時，也建議使用密碼回寫。 如需詳細資訊，請參閱 [密碼回寫](/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>如果已執行外部身分識別提供者，則必須驗證解決方案：<br>-符合 Azure AD 整合需求<br>-支援 Azure AD 條件式存取，允許設定 Microsoft 受管理的電腦裝置合規性原則<br>-啟用裝置註冊，並使用 Microsoft 受管理的電腦部分所需的 Microsoft 365 服務或功能 <br><br>如需 Azure AD 驗證選項的詳細資訊，請參閱[AZURE ad 連線使用者登入選項](/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Microsoft 365 | Microsoft 受管理的電腦使用者必須啟用商務用 OneDrive。<br><br>雖然不需要使用 Microsoft 受管理的電腦註冊，我們強烈建議您將下列服務遷移至雲端：<br>-電子郵件：以 Exchange 2013 或更高的內部部署方式，遷移至雲端架構信箱、Exchange 線上或使用 Exchange Online 混合式進行設定。<br>-檔案和資料夾：遷移至商務用 OneDrive 或 SharePoint 線上。<br>-線上共同作業工具：遷移至 Teams。
裝置管理 | Microsoft 受管理的電腦裝置需要使用 Microsoft Intune 管理。 必須將 Intune 設定為行動裝置管理授權。<br><br>如需詳細資訊，請參閱[Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
資料備份和修復 |  Microsoft 受管理的電腦需要將檔案同步處理至商務用 OneDrive 以進行保護。 任何未同步處理至商務用 OneDrive 的檔案不會受到 Microsoft 受管理的電腦的保證，而且可能會在裝置交換或支援裝置重設的呼叫期間遺失。<br><br>Microsoft 受管理的電腦強烈建議您從對應的網路磁碟機遷移至適當的雲端解決方案，但這不是必要的。 如需詳細資訊，請參閱為[Microsoft 受管理的電腦準備對應的磁片磁碟機](mapped-drives.md)

當您準備好開始使用 Microsoft 受管理的電腦時，請與您的 Microsoft 帳戶管理員聯繫。 

## <a name="more-about-licenses"></a>有關授權的詳細資訊

Microsoft 受管理的電腦需要某些授權選項才能正常運作。 如需如何使用這些授權的詳細資訊，請參閱[Microsoft 受管理的電腦技術](../intro/technologies.md)。

> [!TIP]
> 若要將這些授權選項指派給特定使用者，建議您利用 Azure Active Directory 的[群組型授權功能](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。

- Azure Active Directory 進階版 P1
- Microsoft Intune 
- Windows 10 企業版  
- 適用於端點的 Microsoft Defender
- Microsoft 365 Apps 企業版
- Microsoft Teams
- [SharePoint Online 計劃 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online 方案 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> 您的 Microsoft 帳戶管理員會協助您檢查目前的授權和服務方案，並尋找最有效率的路徑，讓您能取得任何其他可能需要的授權或服務方案，同時避免重複。

## <a name="steps-to-get-ready"></a>準備就緒的步驟

1. 審查[Microsoft 受管理的電腦的必要條件](prerequisites.md)。  (本文) 
2. 使用 [準備工作評估工具](readiness-assessment-tool.md)。
3. [來賓帳戶的先決條件](guest-accounts.md)
4. [Microsoft 受管理的電腦的網路設定](network.md)
5. [為 Microsoft 受管理的電腦準備認證和網路設定檔](certs-wifi-lan.md)
6. [為 Microsoft 受管理的電腦準備內部部署資源存取](authentication.md)
7. [Microsoft 受管理的電腦中的應用程式](apps.md)
8. [為 Microsoft 受管理的電腦準備對應磁碟機](mapped-drives.md)
9. [為 Microsoft 受管理的電腦準備列印資源](printing.md)
