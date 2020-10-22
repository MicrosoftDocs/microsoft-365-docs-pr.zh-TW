---
title: Microsoft 365 租使用者藍圖
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: 設定 Microsoft 365 承租人的藍圖。
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656004"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Microsoft 365 租使用者藍圖

您的 Microsoft 365 租使用者是指派給您組織的一組服務。 此租使用者通常會與一或多個 DNS 功能變數名稱產生關聯，並充當不同訂閱的中央容器，以及您指派給使用者帳戶的授權。 如需詳細資訊，請參閱 [Microsoft 雲端供應專案的訂閱、授權、帳戶及承租人](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。

當您建立 Microsoft 365 租使用者時，您可以將其指派給特定的地理位置。 您也可以讓租使用者使用多個地理位置，並將租使用者從一個位置移至另一個位置。

若要讓您的承租人準備好身分識別，請務必謹慎規劃並執行您的租使用者設定。


## <a name="set-up-your-microsoft-365-tenant"></a>設定您的 Microsoft 365 租使用者

確定您的網路可針對內部部署和遠端工作者存取 Microsoft 365 之後，您的下一個重要工作是針對 DNS 功能變數名稱、泛型服務，以及支援安全使用者登入的身分識別基礎結構，設定您的 Microsoft 365 租使用者。

## <a name="plan"></a>計劃

若要規劃租使用者的執行：

- [瞭解訂閱、授權和 Azure Active Directory (Azure AD) 承租人](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [瞭解如何使用協力廠商 SSL 憑證](plan-for-third-party-ssl-certificates.md)
- [瞭解 Microsoft 365 租使用者與 Azure AD 服務的整合方式](integrated-apps-and-azure-ads.md)
- [規劃用戶端應用程式的支援](microsoft-365-client-support-certificate-based-authentication.md)
- [決定如何使用混合式新式驗證](hybrid-modern-auth-overview.md)
- [規劃 Office 2007 和 Office 2010 升級](plan-upgrade-previous-versions-office.md)
- [瞭解租使用者隔離](microsoft-365-tenant-isolation-overview.md)
- [取得 Microsoft 365 服務保障的詳細資料](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a>部署

若要部署您的租使用者： 

- 為您的組織新增 [DNS 網域](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 。
- 使用 [Microsoft 365 系統管理中心的設定指南](setup-guides-for-microsoft-365.md)。
- 組建您的身分 [識別基礎結構](identity-roadmap-microsoft-365.md) ，並 [保護使用者登入](microsoft-365-secure-sign-in.md)。

### <a name="move-a-tenants-geographic-locations"></a>移動租使用者的地理位置

Microsoft 會繼續開啟新的資料中心地理位置， (geos) Microsoft 365 服務。 這些新的資料中心 geos 可增加容量及計算資源，以支援客戶需求和使用量成長。 此外，新的資料中心 geos 提供核心客戶資料的地理位置資料派駐服務。

如需詳細資訊，請參閱 [將核心資料移至新的 Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md)。


## <a name="deploy-microsoft-365-multi-geo"></a>部署 Microsoft 365 多地理位置

使用 Microsoft 365 多地理位置，您的組織可以將 Microsoft 365 存在狀態擴展到現有租用戶中的多個地理區域和/或國家/地區。

如需詳細資訊，請參閱 [Microsoft 365 多地理](microsoft-365-multi-geo.md)位置。

## <a name="manage-multiple-microsoft-365-tenancies"></a>管理多個 Microsoft 365 租用 

雖然有單一租使用者 oganization 是理想的，但您可以是許多組織中有多個租用的組織。 多個租用的原因可能包括合併和收購、您想要管理隔離，或您有分散的原因。

如果您有多個 Microsoft 365 租用，請參閱下列文章，以取得詳細資訊：

- [租用戶間共同作業](microsoft-365-inter-tenant-collaboration.md)
- [跨租用戶信箱移轉](cross-tenant-mailbox-migration.md)
- [租用戶到租用戶的移轉](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a>後續步驟

以 [訂閱、授權、帳戶及](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)租使用者的方式開始規劃承租人。
