---
title: 使用基本許可權來存取 Microsoft Defender 資訊安全中心
description: 瞭解如何使用基本許可權來存取 Microsoft Defender for Endpoint 入口網站。
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
ms.technology: mde
ms.openlocfilehash: 2d022e903111c498d6f3b7411857748fcb637b64
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844655"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>使用基本權限存取入口網站

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- Azure Active Directory
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

請參閱下列指示，以使用基本的版權管理。

您可以使用下列任一種解決方案：
- Azure PowerShell
- Azure 入口網站

若要對許可權進行精細的控制，請 [切換至以角色為基礎的存取控制](rbac.md)。

## <a name="assign-user-access-using-azure-powershell"></a>使用 Azure PowerShell 指派使用者存取
您可以將下列其中一個許可權等級指派給使用者：
-  (讀寫) 的完整存取權
- 唯讀存取權

### <a name="before-you-begin"></a>開始之前

- 安裝 Azure PowerShell。 如需詳細資訊，請參閱[如何安裝和設定 Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)。<br>

    > [!NOTE]
    > 您必須在已提升許可權的命令列中執行 PowerShell Cmdlet。

- 連線 Azure Active Directory。 如需詳細資訊，請參閱[Connect-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)。

**完全存取** <br>
具有完整存取權的使用者可以登入、查看所有系統資訊及解決提醒、提交檔案進行深層分析，以及下載上架套件。
指派「完整存取」許可權時，需要將使用者新增至「安全性管理員」或「全域系統管理員」 AAD 內建角色。

**唯讀存取權** <br>
具有唯讀存取權的使用者可以登入、查看所有警示和相關資訊。
他們將無法變更警示狀態、提交檔案進行深入分析，或執行任何狀態變更作業。
指派唯讀存取權限時，需要將使用者新增至「Security Reader」 Azure AD 內建角色。

使用下列步驟來指派安全性角色：

- 若要進行 **讀取和寫入** 存取，請使用下列命令，將使用者指派給安全性管理員角色：

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- 若為 **唯讀** 存取，請使用下列命令，將使用者指派給 security reader role：

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

如需詳細資訊，請參閱[使用 Azure Active Directory 新增或移除群組成員](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)。

## <a name="assign-user-access-using-the-azure-portal"></a>使用 Azure 入口網站指派使用者存取

如需詳細資訊，請參閱[使用 Azure Active Directory 指派系統管理員和非系統管理員角色給使用者](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="related-topic"></a>相關主題

- [使用 RBAC 管理入口網站存取](rbac.md)
