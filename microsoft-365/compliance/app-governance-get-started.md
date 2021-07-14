---
title: 開始使用應用程式控管
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 開始使用應用程式控管功能來控管您的應用程式。
ms.openlocfilehash: 0fc00819947d3d472de9199b0381c6f33de0acd6
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420074"
---
# <a name="get-started-with-app-governance-in-preview"></a>開始使用應用程式控管 (預覽)

若要開始使用 Microsoft 雲端 App 安全性的應用程式控管功能：

1. 確認您的帳戶具有適當的授權等級。 應用程式控管是 Microsoft 雲端 App 安全性 (MCAS) 的附加元件功能，因此 MCAS 必須以獨立產品或屬於下列各種授權套件的一部分存在於您的帳戶中。
1. 您必須具有下列其中一個系統管理員角色，才能存取入口網站中的應用程式控管頁面。

## <a name="licensing-for-app-governance"></a>應用程式控管的授權

開始使用應用程式控管之前，您應先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)以及任何附加元件。 若要存取並使用應用程式控管，貴組織必須具備下列其中一種訂閱或附加元件：

- Microsoft 雲端 App 安全性
- Microsoft 365 E5
- Microsoft 365 E5 合規性
- Microsoft 365 E5 開發人員 (不含 Windows 和音訊會議)
- Microsoft 365 E5 資訊保護和控管
- Microsoft 365 E5 安全性
- Microsoft 365 E5 (含通話分鐘數)
- Microsoft 365 E5 (不含音訊會議)
- 教職員用 Microsoft 365 A5 合規性
- 學生用 Microsoft 365 A5 合規性
- 教職員用 Microsoft 365 A5
- 學生用 Microsoft 365 A5
- 教職員用 Microsoft 365 A5 資訊保護和控管
- 學生用 Microsoft 365 A5 資訊保護和控管
- 教職員用 Microsoft 365 A5 安全性
- 學生用 Microsoft 365 A5 安全性
- Microsoft 365 A5 學生使用優惠
- 教職員用 Microsoft 365 A5 (含通話分鐘數)
- 學生用 Microsoft 365 A5 (含通話分鐘數)
- 教職員用 Microsoft 365 A5 (不含音訊會議)
- 學生用 Microsoft 365 A5 (不含音訊會議)
- 學生用 Microsoft 365 A5 (不含音訊會議) 使用優惠

## <a name="administrator-roles"></a>系統管理員角色

若要查看應用程式控管頁面或管理原則與設定，需要下列其中一個系統管理員角色：

- 應用程式系統管理員
- 雲端應用程式系統管理員
- 公司系統管理員
- 合規性系統管理員
- 合規性資料系統管理員
- 合規性讀取者 (唯讀)
- 全域讀取者
- 安全性系統管理員
- 安全性操作員
- 安全性讀取者 (唯讀)

以下是每個角色的功能。

| 角色 | 讀取儀表板 | 讀取所有應用程式 |讀取原則 | 建立、更新或刪除原則 | 讀取警示 | 更新警示 | 讀取設定 | 更新設定 | 讀取補救 | 更新補救 |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| 應用程式系統管理員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| 雲端應用程式系統管理員 | ![核取記號](..\media\checkmark.png) | | | | | | | | | |
| 公司系統管理員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| 合規性系統管理員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | |
| 合規性資料系統管理員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | |
| 合規性讀取者 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | | |
| 全域讀取者  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | | |
| 安全性系統管理員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | |
| 安全性操作員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | |
| 安全性讀取者  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) | |
|||||||||| | |

如需每個角色的其他資訊，請參閱[系統管理員角色權限](/azure/active-directory/roles/permissions-reference)。

## <a name="add-app-governance-to-your-microsoft-365-account"></a>將應用程式控管新增至您的 Microsoft 365 帳戶

針對現有 Microsoft 365 客戶：

1. 在 [Microsoft 365 系統管理中心][](https://admin.microsoft.com) 中，瀏覽至 [計費 - 購買服務]，然後按一下 [附加元件]。
1. 在應用程式控管卡片中，按一下 [詳細資料]。
1. 按一下 [開始免費試用]。
1. 填寫要求的資訊，將應用程式控管新增到您選取的租用戶。 如果您是新的客戶，您必須先提供資訊以建立帳戶並建立試用期的租用戶。 完成之後，就可以將應用程式控管新增到試用版。

針對新 Microsoft 365 客戶：

1. 在此頁面頂端，按一下 [免費帳戶] 按鈕。
1. 在 [試用商務用 Microsoft 365] 下按一下 [免費試用 1 個月]。

針對這兩種客戶：

1. 在註冊入口網站中，提供您的電子郵件地址以用於試用版。 如果您是現有的客戶，請使用與您的帳戶相關聯的電子郵件。 按一下 [下一步]。
1. 完成註冊後，請按一下 [立即試用] 以取得免費試用版。
1. 按一下 [繼續] 以關閉頁面並開始試用版設定。 對於新的應用程式控管客戶，您的應用程式控管執行個體最多需要兩個小時才可供使用。 對於現有客戶，現有的服務不會中斷。
  > [!NOTE]
如果您還沒有帳戶，系統會提示您設定新帳戶，才能繼續試用。

1. 輸入您 AAD 租用戶可用的網域名稱，然後按一下 [檢查可用性]。 系統會自動將系統管理員角色指派給您 (如果您沒有應用程式控管的現有角色)，而且您之後隨時都可以透過 Microsoft 365 系統管理中心變更網域名稱和/或購買更多租用戶。
1. 輸入要用於登入帳戶的使用者名稱和密碼。 按一下 [註冊]。
1. 按一下 [開始使用] 以前往應用程式控管入口網站，或按一下 [管理您的訂閱]，以前往 Microsoft 365 系統管理中心。
