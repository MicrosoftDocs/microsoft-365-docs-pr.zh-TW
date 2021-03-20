---
title: Microsoft 365 身分識別模型和 Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: 瞭解如何使用僅限雲端或混合式身分識別模型，在 Microsoft 365 中管理 Azure AD 使用者身分識別服務。
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905701"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365 身分識別模型和 Azure Active Directory

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft 365 使用 Azure Active Directory (Azure AD) （包含在您的 Microsoft 365 訂閱中的雲端架構使用者身分識別和驗證服務）來管理 Microsoft 365 的身分識別和驗證。 正確設定您的身分識別基礎結構，對管理組織的 Microsoft 365 使用者存取和許可權而言是很重要的。

開始之前，請觀看這段影片，以大略了解身分識別模型和 Microsoft 365 的驗證。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

您第一次規劃選擇是 Microsoft 365 身分識別模型。

## <a name="microsoft-365-identity-models"></a>Microsoft 365 身分識別模型

若要規劃使用者帳戶，您必須先瞭解 Microsoft 365 中的兩個身分識別模型。 您只能在雲端維護組織的身分識別，也可以維護內部部署 Active Directory 網域服務 (AD DS) 身分識別，並在使用者存取 Microsoft 365 雲端服務時，使用這些身分驗證。  

以下是兩種身分識別類型及其最大和優點。

| 屬性 | 僅雲端身分識別 | 混合式身分識別 |
|:-------|:-----|:-----|
| **定義** | 使用者帳戶只存在於 Microsoft 365 訂閱的 Azure AD 租使用者中。 | 使用者帳戶存在於 AD DS 中，而且副本也位於您的 Microsoft 365 訂閱的 Azure AD 租使用者中。 Azure AD 中的使用者帳戶可能也包含已雜湊的 AD DS 使用者帳戶密碼的雜湊版本。 |
| **Microsoft 365 如何驗證使用者認證** | Microsoft 365 訂閱的 Azure AD 租使用者使用雲端身分識別帳戶來執行驗證。 | Microsoft 365 訂閱的 Azure AD 租使用者可以處理驗證程式，也可以將使用者重新導向至另一個身分識別提供者。 |
| **適用** | 不需要內部部署 AD DS 的組織。 | 使用 AD DS 或其他身分識別提供者的組織。 |
| **最大好處** | 便於使用。 不需要額外的目錄工具或伺服器。 | 當存取內部部署或雲端式資源時，使用者可以使用相同的認證。 |
||||

## <a name="cloud-only-identity"></a>僅雲端身分識別

僅限雲端的身分識別只會使用存在於 Azure AD 中的使用者帳戶。 僅限雲端的身分識別通常是由沒有內部部署伺服器的小型組織使用，或是不使用 AD DS 來管理本機身分識別。 

以下是僅限雲端身分識別的基本元件。
 
![僅限雲端身分識別的基本元件](../media/about-microsoft-365-identity/cloud-only-identity.png)

內部部署和遠端 (線上) 使用者可以使用其 Azure AD 使用者帳戶和密碼來存取 Microsoft 365 雲端服務。 Azure AD 會根據其儲存的使用者帳戶和密碼驗證使用者認證。

### <a name="administration"></a>系統管理
因為使用者帳戶只會儲存在 Azure AD 中，您可以使用 [Microsoft 365 系統管理中心](../admin/add-users/index.yml) 和 [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)之類的工具來管理雲端身分識別。 

## <a name="hybrid-identity"></a>混合式身分識別

混合式身分識別使用內部部署 AD DS 中的帳戶，並在 Microsoft 365 訂閱的 Azure AD 租使用者中擁有複本。 不過，大部分的變更只流向單一方式。 您對 AD DS 使用者帳戶所做的變更會同步處理至其 Azure AD 中的副本。 但是，在 Azure AD 中對雲端型帳戶所做的變更（例如新的使用者帳戶）不會與 AD DS 同步。

Azure AD Connect 提供進行中的帳戶同步處理。 它會在內部部署伺服器上執行，檢查 AD DS 中的變更，並將這些變更轉送到 Azure AD。 Azure AD Connect 可讓您篩選要同步處理的帳戶，以及是否同步處理已雜湊的版本的使用者密碼，稱為密碼雜湊同步處理 (PHS) 。

當您執行混合式身分識別時，您的內部部署 AD DS 是帳戶資訊的授權來源。 這表示您執行大部分內部部署的管理工作，然後同步處理到 Azure AD。 

以下是混合式身分識別的元件。

![混合身分識別的元件](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD 租使用者具有 AD DS 帳戶的副本。 在此設定中，內部部署和遠端使用者都會存取 Microsoft 365 雲端服務，以針對 Azure AD 進行驗證。

>[!Note]
>您永遠需要使用 Azure AD Connect，以同步處理混合身分識別的使用者帳戶。 您需要 Azure AD 中已同步處理的使用者帳戶，以執行授權指派和群組管理、設定許可權，以及其他涉及使用者帳戶的系統管理工作。
>

### <a name="administration"></a>系統管理

由於原始和權威性的使用者帳戶是儲存在內部部署 AD DS 中，因此您可以在管理 AD DS 時使用相同的工具來管理您的身分識別。 

您不會使用 Microsoft 365 系統管理中心或 Microsoft 365 的 PowerShell 來管理 Azure AD 中已同步的使用者帳戶。

## <a name="next-step"></a>後續步驟

如果您需要僅限雲端的身分識別模型，請參閱 [僅限雲端身分識別](cloud-only-identities.md)。

如果您需要混合式身分識別模型，請參閱 [混合身分識別](plan-for-directory-synchronization.md)。


## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)