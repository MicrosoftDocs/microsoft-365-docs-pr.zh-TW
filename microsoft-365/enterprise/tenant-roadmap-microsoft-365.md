---
title: Microsoft 365 的承租人藍圖
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: 設定 Microsoft 365 承租人的藍圖。
ms.openlocfilehash: 4b94540293b86bd922ce4b29f970e52eb1245a01
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464030"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Microsoft 365 的承租人藍圖

您的 Microsoft 365 租使用者是指派給您組織的一組服務。 此租使用者通常會與一或多個公用 DNS 功能變數名稱產生關聯，並且充當不同訂閱的中央和獨立容器，以及您指派給使用者帳戶的授權。 如需詳細資訊，請參閱 [Microsoft 雲端供應專案的訂閱、授權、帳戶及承租人](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。

當您建立 Microsoft 365 租使用者時，您可以將其指派給特定的地理位置。 您也可以讓租使用者使用多個地理位置，並將租使用者從一個位置移至另一個位置。

若要讓您的租使用者準備好進行使用者、群組、授權和雲端應用程式，請務必仔細規劃並執行您的租使用者設定。

## <a name="set-up-your-microsoft-365-tenant"></a>設定 Microsoft 365 租使用者

確定您的網路已針對內部部署和遠端工作者的 Microsoft 365 存取進行優化後，您下一次的大型工作會進行規劃，然後針對 DNS 功能變數名稱、泛型服務，以及支援安全使用者登入的身分識別基礎結構，設定 Microsoft 365 租使用者。

### <a name="plan"></a>方案

若要規劃租使用者的執行：

- [瞭解訂閱、授權和 Azure Active Directory (Azure AD) 承租人](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [瞭解如何使用協力廠商 SSL 憑證](plan-for-third-party-ssl-certificates.md)
- [瞭解 Microsoft 365 租使用者與 Azure AD 服務整合的方式](integrated-apps-and-azure-ads.md)
- [規劃用戶端應用程式的支援](microsoft-365-client-support-certificate-based-authentication.md)
- [決定如何使用混合式新式驗證](hybrid-modern-auth-overview.md)
- [規劃 Office 2007 和 Office 2010 升級](plan-upgrade-previous-versions-office.md)
- [瞭解租使用者隔離](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a>部署

若要部署您的租使用者： 

- 為您的組織新增 [DNS 網域](../admin/setup/add-domain.md) 。
- 使用[Microsoft 365 系統管理中心中的設定指南](setup-guides-for-microsoft-365.md)。
- 組建您的身分 [識別基礎結構](identity-roadmap-microsoft-365.md) ，並 [保護使用者登入](microsoft-365-secure-sign-in.md)。

### <a name="move-a-tenants-geographic-locations"></a>移動租使用者的地理位置

Microsoft 繼續開啟新的資料中心地理位置， (geos) Microsoft 365 服務。 這些新的資料中心 geos 可增加容量及計算資源，以支援客戶需求和使用量成長。 此外，新的資料中心 geos 提供核心客戶資料的地理位置資料派駐服務。

如需詳細資訊，請參閱[將核心資料移至新 Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md)。


## <a name="deploy-microsoft-365-multi-geo"></a>部署 Microsoft 365 多地理位置

使用 Microsoft 365 多地理位置，您的組織可以將 Microsoft 365 存在狀態擴展到現有租用戶中的多個地理區域和/或國家/地區。

如需詳細資訊，請參閱 [Microsoft 365 多地理位置](microsoft-365-multi-geo.md)。

## <a name="manage-multiple-microsoft-365-tenants"></a>管理多個 Microsoft 365 承租人 

雖然為您的 oganization 使用單一租使用者是理想的，但您可以是具有多個承租人的眾多組織之一。 原因包括合併和收購、您想要管理隔離，或您具有分散的方式。

如果您有多個 Microsoft 365 承租人，請參閱下列文章，以取得詳細資訊：

- [租用戶間共同作業](microsoft-365-inter-tenant-collaboration.md)
- [跨租用戶信箱移轉](cross-tenant-mailbox-migration.md)
- [租用戶到租用戶的移轉](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>下一個步驟

以 [訂閱、授權、帳戶及](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)租使用者的方式開始規劃承租人。