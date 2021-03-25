---
title: 將使用者存取權指派給 Microsoft Defender 安全中心
description: 對 Microsoft Defender for Endpoint 入口網站指派讀取和寫入或唯讀存取權。
keywords: 指派使用者角色、指派讀取和寫入權限、指派唯讀存取、使用者、使用者角色、角色
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164749"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>將使用者存取權指派給 Microsoft Defender 安全中心

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- Azure Active Directory
- Office 365
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint 支援兩種管理許可權的方式：

- **基本版權管理**：將許可權設定為「完整存取」或「唯讀」。
- 以 **角色為基礎的存取控制 (RBAC)**：透過定義角色、指派 Azure AD 使用者群組和授予使用者群組存取裝置群組，來設定細微許可權。 如需 RBAC 的詳細資訊，請參閱 [使用以角色為基礎的存取控制管理入口網站存取](rbac.md)。

> [!NOTE]
> 如果您已指派基本許可權，您可以隨時切換至 RBAC。 進行切換之前，請先考慮下列專案：
> 
> - 在 Azure AD) 中，在指派全域系統管理員或安全性管理員目錄角色的使用者上，具有完整 (存取權的使用者，系統會自動為端點系統管理員角色指派預設的 Defender，也就是具有完整存取權。 在切換至 RBAC 後，可將其他 Azure AD 使用者群組指派給 Defender for Endpoint 系統管理員角色。  只有指派給 Endpoint 系統管理員角色的使用者才能使用 RBAC 來管理許可權。 
> - 具有唯讀存取權的使用者 (的安全性讀取者) 在被指派角色後，才會失去對入口網站的存取權。 請注意，只有 Azure AD 使用者群組可以指派角色下的 RBAC。
> - 切換 RBAC 後，您將無法再切換回使用基本版權管理。

## <a name="related-topics"></a>相關主題

- [使用基本許可權來存取入口網站](basic-permissions.md)
- [使用 RBAC 管理入口網站存取](rbac.md)
