---
title: 以角色為基礎之存取控制的自訂角色
description: 瞭解如何在 Microsoft 365 的安全性中心管理自訂角色
keywords: access，許可權，MTP，Microsoft 威脅防護，M365，安全性，MCAS，MDATP，Cloud App Security，Microsoft Defender 高級威脅防護，範圍，範圍，RBAC，以角色為基礎的存取，以自訂角色為基礎的存取，以角色為基礎的授權，在 MDO、角色、rolegroups、許可權繼承和微調許可權中的 RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 35ac4e26406fe6fde1385008b527dc4865e0392b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928925"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Microsoft 365 Defender 角色型存取控制中的自訂角色

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

適用於：

- Microsoft 365 Defender
 
有兩種類型的角色可用於存取 Microsoft 365 Defender：
- **全域 Azure Active Directory (AD) 角色**
- **自訂角色**

使用[Azure Active Directory (AAD) 中的全域角色](mtp-permissions.md)，可共同管理 Microsoft 365 Defender 的存取

如果您需要更大的彈性，並控制特定產品資料的存取權，也可以透過各自的安全性入口網站建立自訂角色，以管理 Microsoft 365 Defender access。  

例如，透過 Microsoft Defender for Endpoint 建立的自訂角色，可以存取相關的產品資料，包括 Microsoft 365 security center 中的端點資料。 同樣地，透過 Microsoft Defender for Office 365 所建立的自訂角色，可以存取相關的產品資料，包括 Microsoft 365 安全性中心內的電子郵件 & 協同作業資料。

具有現有自訂角色的使用者可能會根據現有的工作負載許可權，存取 Microsoft 365 security center 中的資料，而不需要進行其他設定。

## <a name="create-and-manage-custom-roles"></a>建立及管理自訂角色
您可以建立自訂角色和許可權，並透過下列各項安全性入口網站進行個別管理： 

- Microsoft Defender for Endpoint – [編輯 Microsoft defender For endpoint 中的角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- Microsoft Defender for Office 365 – [Security & 合規性中心的許可權](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security- [管理系統管理員存取權](/cloud-app-security/manage-admins)

透過個別入口網站所建立的每個自訂角色，都可以存取相關的產品入口網站的資料。 例如，透過 Microsoft Defender for Endpoint 所建立的自訂角色，只會允許 access Defender 的端點資料。

> [!TIP]
> 您也可以透過 Microsoft 365 的安全性中心來存取許可權和角色，方法是從功能窗格中選取 [許可權] & 角色。 存取 Microsoft Cloud App Security (MCAS) 是透過 MCAS 入口網站進行管理，而且也可控制對 Microsoft Defender 身分識別的存取。  請參閱 [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> 在 Microsoft Cloud App Security 中建立的自訂角色，也可以存取 Microsoft Defender 以取得識別資料。 具有使用者群組管理員的使用者或應用程式/實例管理員 Microsoft Cloud App Security role 無法透過 Microsoft 365 Security center 存取 Microsoft Cloud App Security 資料。

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>在 Microsoft 365 安全中心管理許可權和角色
您也可以在 Microsoft 365 的「安全中心」中管理許可權和角色：

1. 以 security.microsoft.com 登入 Microsoft 365 的安全性中心。
2. 在功能窗格中，選取 [ **許可權] & 角色**。
3. 在 [ **許可權** ] 標頭底下，選取 [ **角色**]。

> [!NOTE]
> 這只適用于 Office 365 和 Defender for Endpoint 的 Defender。 其他工作負載的存取必須在其相關入口網站中完成。


## <a name="required-roles-and-permissions"></a>必要角色和權限
下表概述在每個工作負載中存取每個整合體驗所需的角色和許可權。 下表中定義的角色是指個別入口網站中的自訂角色，而且不會連線至 Azure AD 中的全域角色，即使名稱類似。

> [!NOTE]
> 事件管理需要屬於事件一部分之所有產品的管理許可權。
 
| **Microsoft 365 Defender 需要下列其中一個角色**  | **Defender for Endpoint 需要下列其中一個角色**  | **在 Office 365 的 Defender 中需要下列其中一個角色** | **Cloud App Security 需要下列其中一個角色** | 
|---------|---------|---------|---------|
| 查看調查資料： <ul><li>警示頁面</li> <li>警示佇列</li> <li>事件</li>  <li>事件佇列</li> <li>行動中心</li></ul>| View data-安全性作業 | <ul><li>僅供查看的管理提醒 </li> <li>組織組態</li><li>稽核記錄</li> <li>僅限查看的審計記錄檔</li> <li>安全性讀取者</li> <li>安全性系統管理員</li><li>僅供查看的收件者</li></ul>  | <ul><li>全域系統管理員</li> <li>安全性系統管理員</li> <li>合規性系統管理員</li> <li>安全性操作員</li> <li>安全性讀取者</li> <li>全域讀取者</li></ul> |
| 查看搜尋資料 | View data-安全性作業 | <ul><li>安全性讀取者</li> <li>安全性系統管理員</li> <li>僅供查看的收件者</li> | <ul><li>全域系統管理員</li> <li>安全性系統管理員</li> <li>合規性系統管理員</li> <li>安全性操作員</li> <li>安全性讀取者</li> <li>全域讀取者</li></ul> |
| 管理警示和事件 | 警示調查 | <ul><li>管理提醒</li> <li>安全性系統管理員</li> | <ul><li>全域系統管理員</li> <li>安全性系統管理員</li> <li>合規性系統管理員</li> <li>安全性操作員</li> <li>安全性讀取者</li></ul> |
| 行動中心修正 | 主動修正動作–安全性作業 | 搜尋及清除 | |
| 設定自訂偵測 | 管理安全性設定 |<ul><li>管理提醒</li> <li>安全性系統管理員</li></ul> | <ul><li>全域系統管理員</li> <li>安全性系統管理員</li> <li>合規性系統管理員</li> <li>安全性操作員</li> <li>安全性讀取者</li> <li>全域讀取者</li></ul> |
| 威脅分析 | 警示和事件資料： <ul><li>View data-安全性作業</li></ul>TVM 緩解：<ul><li>View data-威脅和弱點管理</li></ul> | 警示和事件資料：<ul> <li>僅供查看的管理提醒</li> <li>管理提醒</li> <li>組織組態</li><li>稽核記錄</li> <li>僅限查看的審計記錄檔</li><li>安全性讀取者</li> <li>安全性系統管理員</li><li>僅供查看的收件者</li> </ul> 禁止電子郵件嘗試： <ul><li>安全性讀取者</li> <li>安全性系統管理員</li><li>僅供查看的收件者</li> | 無法供 MCAS 或 MDI 使用者使用 |

例如，若要從 Microsoft Defender for Endpoint 中查看搜尋資料，必須要有 View data security operations 許可權。  

同樣地，若要從 Microsoft Defender for Office 365 查看搜尋資料，使用者需要下列其中一個角色：  

- 查看資料安全性作業
- 安全性讀取者
- 安全性系統管理員
- 僅供查看的收件者

## <a name="related-topics"></a>相關主題
- [管理 Microsoft 365 Defender 的存取權](mtp-permissions.md)
- [管理 MCAS 的系統管理員存取權](/cloud-app-security/manage-admins)