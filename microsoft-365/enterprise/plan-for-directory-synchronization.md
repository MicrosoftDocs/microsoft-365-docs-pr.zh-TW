---
title: Microsoft 365 的混合式身分識別及目錄同步處理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 06/09/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: 說明與 Microsoft 365、Active Directory 網域服務清理和 Azure Active Directory Connect 工具的目錄同步處理。
ms.openlocfilehash: 2d3161fb835073a22743ea4f3b00ac508479f0f2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688507"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Microsoft 365 的混合式身分識別及目錄同步處理

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

根據您的業務需求和技術需求，混合式身分識別模型及目錄同步處理對於採用 Microsoft 365 的企業客戶而言是最常見的選擇。 目錄同步處理可讓您在 Active Directory 網域服務 (AD DS) 中管理身分識別，並且將所有對使用者帳戶、群組和連絡人的更新，同步處理至您的 Microsoft 365 訂閱的 Azure Active Directory (Azure AD) 承租人。

>[!Note]
>當 AD DS 使用者帳戶第一次同步處理時，不會自動將其指派給 Microsoft 365 許可證，而且無法存取 Microsoft 365 服務，例如電子郵件。 您必須先將其指派為使用位置。 然後，透過群組成員資格個別或動態指派授權給這些使用者帳戶。
>

## <a name="authentication-for-hybrid-identity"></a>混合式識別的驗證

使用混合式識別模型時，有兩種驗證類型：

- 管理的驗證

  Azure AD 會使用本機儲存的雜湊版本的密碼，或將認證傳送至內部部署 AD DS 來驗證內部部署軟體代理程式，以處理驗證程式。

- 同盟驗證

  Azure AD 會將要求驗證的用戶端電腦重新導向至另一個身分識別提供者。

### <a name="managed-authentication"></a>管理的驗證

受管理的驗證類型有兩種：

- 密碼雜湊同步處理 (PHS) 

  Azure AD 會自行執行驗證。

- 傳遞驗證 (PTA)

  Azure AD 具有 AD DS 執行驗證。


#### <a name="password-hash-synchronization-phs"></a>密碼雜湊同步處理 (PHS) 

透過 PHS，您可以將 AD DS 使用者帳戶與 Microsoft 365 同步處理，並管理內部部署的使用者。 使用者密碼的雜湊會從您的 AD DS 同步處理到 Azure AD，讓使用者在內部部署和雲端都有相同的密碼。 這是在 Azure AD 中啟用 AD DS 身分識別驗證的最簡單方式。 

![密碼雜湊同步處理 (PHS) ](../media/plan-for-directory-synchronization/phs-authentication.png)

當密碼變更或重設為內部部署時，新的密碼雜湊會同步處理至 Azure AD，這樣您的使用者就可以在雲端資源和內部部署資源中永遠使用相同的密碼。 使用者密碼永遠不會以明文形式傳送至 Azure AD 或儲存在 Azure AD 中。 不論選取哪一種驗證方法，Azure AD 的某些精品功能（例如身分識別保護）都需要 PHS。
  
若要深入瞭解，請參閱 [選擇正確的驗證方法](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 。
  
#### <a name="pass-through-authentication-pta"></a>傳遞驗證 (PTA)

PTA 提供使用一或多個內部部署伺服器上執行的軟體代理程式，直接向您的 AD DS 驗證使用者，以進行 Azure AD 驗證服務的簡單密碼驗證。 透過 PTA，您可以同步處理 AD DS 使用者帳戶與 Microsoft 365，並管理內部部署的使用者。 

![傳遞驗證 (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

PTA 可讓您的使用者使用內部部署帳戶和密碼，登入內部部署和 Microsoft 365 資源及應用程式。 此設定會直接驗證使用者密碼與您的內部部署 AD DS，而不會在 Azure AD 中儲存密碼雜湊。 

PTA 也適用于具有安全性需求的組織，以立即強制執行內部部署使用者帳戶狀態、密碼原則和登入時間。 
  
若要深入瞭解，請參閱 [選擇正確的驗證方法](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 。
  
### <a name="federated-authentication"></a>同盟驗證

同盟驗證主要針對大型企業組織，其驗證需求較複雜。 AD DS 身分識別與 Microsoft 365 同步處理，而且使用者帳戶是在內部部署管理。 透過同盟驗證，使用者在內部部署和雲端都有相同的密碼，而且不需要重新登入即可使用 Microsoft 365。 

同盟驗證可支援其他驗證需求，例如智慧卡型驗證或協力廠商的多重要素驗證，而且在組織具備 Azure AD 本身不支援的驗證需求時，通常需要使用。
 
若要深入瞭解，請參閱 [選擇正確的驗證方法](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 。
  
#### <a name="third-party-authentication-and-identity-providers"></a>協力廠商驗證和身分識別提供者

內部部署目錄物件可能會同步處理至 Microsoft 365，而雲端資源存取主要是由協力廠商身分識別提供者 (IdP) 所管理。 如果您的組織使用協力廠商同盟解決方案，您可以將協力廠商同盟解決方案與 Azure AD 相容，以供 Microsoft 365 的解決方案進行登錄。
  
請參閱 [AZURE AD federation 相容性清單](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) 以深入瞭解。
  
## <a name="ad-ds-preparation"></a>AD DS 準備

若要協助確保透過同步處理順利轉換至 Microsoft 365，您必須先準備您的 AD DS 樹系，再開始 Microsoft 365 目錄同步部署。
  
您的目錄準備工作應該著重于下列工作：

- 移除重複的 **proxyAddress** 和 **userPrincipalName** 屬性。
- 使用有效的**userPrincipalName**屬性，更新空白及不正確**userPrincipalName**屬性。
- 移除 **givenName**、姓 ( **sn** ) 、 **sAMAccountName**、 **displayName**、 **mail**、 **proxyAddresses**、 **mailNickname**及 **userPrincipalName** 屬性中的無效且可疑的字元。 如需準備屬性的詳細資訊，請參閱 [由 Azure Active Directory 同步處理工具同步處理的屬性清單](https://go.microsoft.com/fwlink/p/?LinkId=396719)。

    > [!NOTE]
    > 這些是 Azure AD Connect 同步處理的相同屬性。 
  
## <a name="multi-forest-deployment-considerations"></a>多樹系部署的考慮

若為多個樹系和 SSO 選項，請使用 [AZURE AD Connect 的自訂安裝](https://go.microsoft.com/fwlink/p/?LinkId=698430)。
  
如果您的組織有多個樹系用於驗證 (登入樹系) ，我們強烈建議下列事項：
  
- **請考慮合併您的樹系。** 一般說來，維護多個樹系需要額外的額外負荷。 除非您的組織有規定個別樹系需求的安全性限制，否則請考慮簡化您的內部部署環境。
- **僅在您的主要登入樹系中使用。** 請考慮只在您的主要登入樹系中部署 Microsoft 365，以進行初次展示 Microsoft 365。 

如果您無法合併多樹系 AD DS 部署，或正在使用其他目錄服務來管理身分識別，您可以使用 Microsoft 或協力廠商的說明同步處理這些身分識別。
  
如需詳細資訊，請參閱 [AZURE AD Connect 的拓撲](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) 。
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>依存于目錄同步處理的功能
  
下列功能需要目錄同步處理：
  
-  (SSO) 的 Azure AD 無縫單一 Sign-On
- Skype 共存
- Exchange 混合式部署，包括：
  - 在您的內部部署 Exchange 環境與 Microsoft 365 之間 (GAL) 的完全共用全域通訊清單。
  - 同步處理來自不同郵件系統的 GAL 資訊。
  - 可在 Microsoft 365 服務產品中新增及移除使用者的功能。 這需要下列各項：
  - 在目錄同步處理設定期間，必須設定雙向同步處理。 根據預設，目錄同步處理工具只會將目錄資訊寫入雲端。 當您設定雙向同步處理時，您可以啟用寫回功能，使有限數目的物件屬性從雲端複製，然後再將其寫入您的本機 AD DS。 回寫也稱為 Exchange 混合模式。 
  - 內部部署 Exchange 混合式部署
  - 將部分使用者信箱移至 Microsoft 365 的功能，同時保留其他使用者信箱的內部部署。
  - 安全寄件者和封鎖的寄件者內部部署會複製到 Microsoft 365。
  - 基本委派和代理傳送電子郵件功能。
  - 您有整合式內部部署智慧卡或多重要素驗證解決方案。
- 同步處理相片、縮圖、會議室及安全性群組

## <a name="next-step"></a>下一步

當您準備好部署混合式身分識別時，請參閱 [prepare to](prepare-for-directory-synchronization.md)布建使用者。
  
## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

