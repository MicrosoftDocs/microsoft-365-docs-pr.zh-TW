---
title: 建立及管理以角色為基礎的存取控制的角色
description: 建立角色並定義指派給角色的許可權，作為 Microsoft Defender Security Center 中角色型存取控制執行的一部分。
keywords: 使用者角色、角色、存取 rbac
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
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059236"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>建立及管理以角色為基礎的存取控制的角色

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>建立角色並將角色指派給 Azure Active Directory 群組

下列步驟會引導您瞭解如何在 Microsoft Defender Security Center 中建立角色。 它假設您已建立 Azure Active Directory 使用者群組。

1. 使用已指派安全性管理員或全域系統管理員角色的帳戶登入 [Microsoft Defender 安全中心](https://securitycenter.windows.com/) 。

2. 在功能窗格中，選取 [ **設定] > 角色**。

3. 選取 [ **新增專案**]。

4. 輸入您想要指派給角色的角色名稱、描述及許可權。

5. 選取 **[下一步]** ，將角色指派給 Azure AD 安全性群組。

6. 使用篩選器來選取您想要新增至此角色的 Azure AD 群組。

7. **儲存並關閉**。

8. 套用設定設定。

> [!IMPORTANT]
> 建立角色之後，您將需要建立裝置群組，並將其指派給剛才建立的角色，以提供對該裝置群組的存取權。

### <a name="permission-options"></a>許可權選項

- **查看資料**
    - **安全性作業** -查看入口網站中的所有安全性作業資料
    - **威脅和弱點管理** -在入口網站中查看威脅和弱點管理資料

- **主動修正動作**
    - **安全性作業** -採取回應動作、核准或取消未決修正動作、管理允許/封鎖的自動化和指示器清單
    - **威脅和弱點管理-例外處理** -建立新的例外狀況及管理作用中的例外狀況
    - **威脅和弱點管理-修正處理** -提交新的修復要求、建立票證，以及管理現有的修復活動

- **警示調查** -管理提醒、啟動自動化調查、執行掃描、收集調查套件、管理裝置標記，並只下載可遷移的可執行檔 (PE) 檔案 

- **管理入口網站系統設定** -設定儲存設定、SIEM 及威脅 intel API 設定 (會套用全域) 、高級設定、自動化檔案上傳、角色和裝置群組

    > [!NOTE]
    > 此設定僅適用于 Microsoft Defender for Endpoint 管理員 (default) role。

- **Manage Security Center 中的安全性設定** -設定警示抑制設定、管理自動化、板載和下架裝置的資料夾排除，以及管理電子郵件通知、管理評估實驗室

- **即時回應功能**
    - **基本** 命令：
        - 啟動 live response session
        - 在遠端裝置上執行「唯讀即時回應」命令 (但不包括檔案複製和執行
    - **Advanced** 命令：
        - 透過即時回應從遠端裝置下載檔案
        - 從檔頁面下載 PE 和非 PE 檔案
        - 將檔案上傳至遠端裝置
        - 從檔案庫中查看腳本
        - 從檔案庫在遠端裝置上執行腳本

如需可用命令的詳細資訊，請參閱 [使用即時回應調查裝置](live-response.md)。
  
## <a name="edit-roles"></a>編輯角色

1. 使用已指派安全性管理員或全域系統管理員角色的帳戶登入 [Microsoft Defender 安全中心](https://securitycenter.windows.com/) 。

2. 在功能窗格中，選取 [ **設定] > 角色**。

3. 選取您要編輯的角色。

4. 按一下 [編輯]。

5. 修改指派給角色的詳細資料或群組。 

6. 按一下 [ **儲存並關閉**]。

## <a name="delete-roles"></a>刪除角色

1. 使用已指派安全性管理員或全域系統管理員角色的帳戶登入 [Microsoft Defender 安全中心](https://securitycenter.windows.com/) 。

2. 在功能窗格中，選取 [ **設定] > 角色**。

3. 選取您想要刪除的角色。

4. 按一下下拉式按鈕，然後選取 [ **刪除角色**]。

## <a name="related-topic"></a>相關主題

- [存取入口網站的使用者基本許可權](basic-permissions.md)
- [建立及管理裝置群組](machine-groups.md)
