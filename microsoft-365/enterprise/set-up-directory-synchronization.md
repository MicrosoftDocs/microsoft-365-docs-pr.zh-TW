---
title: 設定 Microsoft 365 的目錄同步處理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: 瞭解如何在 Microsoft 365 和您的內部部署 Active Directory 之間設定目錄同步處理。
ms.openlocfilehash: 3a846a6c558f221c1869dce6da27e3d34680f75d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688313"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>設定 Microsoft 365 的目錄同步處理

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft 365 使用 Azure Active Directory (Azure AD) 租使用者來儲存和管理身分驗證的身分識別，以及存取雲端架構資源的許可權。 

如果您有內部部署 Active Directory 網域服務 (AD DS) ，您可以使用 Microsoft 365 訂閱的 Azure AD 租使用者來同步處理您的 AD DS 使用者帳戶、群組和連絡人。 這是 Microsoft 365 的混合式身分識別。 以下是其元件。

![Microsoft 365 的目錄同步處理元件](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect 會在內部部署伺服器上執行，並與 Azure AD 租使用者同步處理 AD DS。 除了目錄同步處理之外，您還可以指定下列驗證選項：

- 密碼雜湊同步處理 (PHS) 

  Azure AD 會自行執行驗證。

- 傳遞驗證 (PTA)

  Azure AD 具有 AD DS 執行驗證。

- 同盟驗證

  Azure AD 重新導向要求驗證的用戶端電腦，以與另一個身分識別提供者聯繫。

如需詳細資訊，請參閱 [混合式識別碼](plan-for-directory-synchronization.md) 。
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. 檢查 Azure AD Connect 的先決條件

您可以使用 Microsoft 365 訂閱取得免費的 Azure AD 訂閱。 當您設定目錄同步處理時，您會在其中一個內部部署伺服器上安裝 Azure AD Connect。
  
若為 Microsoft 365，您將需要：
  
- 驗證您的內部部署網域。 Azure AD Connect 嚮導會引導您完成此步驟。
- 取得您的 Microsoft 365 租使用者和 AD DS 之系統管理員帳戶的使用者名稱和密碼。

針對您在其上安裝 Azure AD Connect 的內部部署伺服器，您需要：
  
|**伺服器作業系統**|**其他軟體**|
|:-----|:-----|
|Windows Server 2012 R2 和更新版本 | -預設會安裝 PowerShell，不需要採取任何動作。  <br> -透過 Windows Update 提供 Net 4.5.1 和更新版本。 請確認您已在 [控制台] 中安裝最新的 Windows Server 更新。 |
|Windows Server 2008 R2 Service Pack 1 (SP1) * * 或 Windows Server 2012 | -Windows Management Framework 4.0 提供 PowerShell 的最新版本。 在 [Microsoft 下載中心](https://go.microsoft.com/fwlink/p/?LinkId=717996)搜尋。  <br> -您可以在 [Microsoft 下載中心](https://go.microsoft.com/fwlink/p/?LinkId=717996)取得 .net 4.5.1 和更新版本。 |
|Windows Server 2008 | -您可以在 [Microsoft 下載中心](https://go.microsoft.com/fwlink/p/?LinkId=717996)上使用 Windows Management Framework 3.0，提供最新支援的 PowerShell 版本。  <br> -您可以在 [Microsoft 下載中心](https://go.microsoft.com/fwlink/p/?LinkId=717996)取得 .net 4.5.1 和更新版本。 |

請參閱 [Azure Active Directory connect 的必要條件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) ，以取得硬體、軟體、帳戶與許可權需求、SSL 憑證需求，以及 Azure AD Connect 的物件限制等詳細資訊。
  
您也可以查看 Azure AD Connect [版本發行歷程記錄](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) ，以查看每個版本中包含和修正的內容。

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. 安裝 Azure AD Connect 及設定目錄同步處理

開始之前，請確定您已具備下列專案：

- Microsoft 365 全域管理員的使用者名稱和密碼
- AD DS 域管理員的使用者名稱和密碼
- 哪種驗證方法 (PHS、PTA、同盟) 
- 您是否要使用 [AZURE AD 無縫單一登入 (SSO) ](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)

請遵循下列步驟：

1. 登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) (https://admin.microsoft.com) 並選擇左側導覽中的 [ **使用者**] [作用中 \> **使用者** ]。
2. 在 [作用中 **使用者** ] 頁面上，選擇 [ **其他** (三個點) \> **目錄同步**處理]。
  
3. 在 [ **Azure Active Directory 準備** ] 頁面上，選取 [ **移至下載中心] 以取得 Azure AD Connect 工具** 連結開始使用。 
4. 請遵循 [AZURE Ad connect 和 AZURE Ad Connect Health 安裝藍圖](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap)中的步驟進行。

## <a name="3-finish-setting-up-domains"></a>3. 完成網域的設定

當您管理您的 DNS 記錄以完成網域的設定時，請遵循下列步驟，以 [建立 Microsoft 365 的 dns 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 。

## <a name="next-step"></a>下一步

[將授權指派給使用者帳戶](assign-licenses-to-user-accounts.md)
