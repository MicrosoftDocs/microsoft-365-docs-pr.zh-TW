---
title: 保護使用者和裝置存取權
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 瞭解如何保護使用者和裝置存取 Microsoft 365 資料和服務，並防止資料遺失。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051695"
---
# <a name="protect-user-and-device-access"></a>保護使用者和裝置存取權

保護 Microsoft 365 資料和服務的存取權，對於防禦 cyberattacks 及防止資料遺失而言很重要。 相同的保護可以套用至您環境中的其他 SaaS 應用程式，甚至適用于使用 Azure Active Directory 應用程式 Proxy 發佈的內部部署應用程式。
  
## <a name="step-1-review-recommendations"></a>步驟1：複查建議

推薦可用於保護身分識別和裝置的功能，其可存取 Office 365、其他 SaaS 服務，以及與 Azure AD 應用程式 Proxy 一起發佈的內部部署應用程式。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>步驟2：保護系統管理員帳戶和存取
用來管理 Microsoft 365 環境的管理帳戶包含較高的權限。 這些是駭客和 cyberattackers 的有用目標。 

僅使用管理員帳戶來開始。 系統管理員應該要有個別的使用者帳戶，以進行一般的非系統管理，而且只有在必要時才使用系統管理帳戶，才可完成與工作職能相關聯的工作。

使用多重要素驗證和條件式存取來保護您的系統管理員帳戶。 如需詳細資訊，請參閱 [保護系統管理員帳戶](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)。 

接下來，在 Office 365 中設定特殊許可權存取管理。 特殊權限存取管理可對 Office 365 中的特殊權限系統管理工作提供細微的存取控制。 它可以協助保護您的組織不會因可能使用現有的許可權系統管理員帳戶存取機密資料或存取重要的設定設定而遭到破壞。

- [特殊許可權存取管理的概述](privileged-access-management-overview.md)
- [設定特殊權限存取管理](privileged-access-management-configuration.md)

另一個主要建議是使用專門設定管理工作的工作站。 這些是僅供管理工作使用的專用裝置。 請參閱 [保護特殊許可權存取](/windows-server/identity/securing-privileged-access/securing-privileged-access)。

最後，您可以在您的租使用者中建立兩個或多個緊急存取帳戶，以減輕意外缺乏管理存取的影響。 請參閱 [管理 AZURE AD 中的緊急存取帳戶](/azure/active-directory/users-groups-roles/directory-emergency-access)。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>步驟3：設定建議的身分識別和裝置存取原則
多重要素驗證 (MFA) 和條件式存取原則，都是一些強大的工具，可減輕受到損害的帳戶和未經授權的存取。 建議您實施一組已一起測試的原則。 如需詳細資訊，包括部署步驟，請參閱 [Identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md)設定。

 這些原則會執行下列功能：
- 單行因素驗證
- 條件式存取
- Intune app protection (裝置的應用程式和資料保護) 
- Intune 裝置合規性
- Azure AD Identity Protection

實施 Intune 裝置合規性需要裝置註冊。 管理裝置可讓您在允許存取您環境中的資源之前，確定這些裝置的健康和相容性。 請參閱 [在 Intune 中註冊裝置以進行管理](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>步驟4：設定 SharePoint 裝置存取原則

Microsoft 建議您使用裝置存取控制，以機密和高管制內容來保護 SharePoint 網站中的內容。 如需詳細資訊，請參閱[保護 SharePoint 網站和檔案的原則建議](../security/defender-365-security/sharepoint-file-access-policies.md)。



