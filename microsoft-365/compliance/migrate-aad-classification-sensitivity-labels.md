---
title: Microsoft 365 群組的 Azure Active Directory 分類和敏感度標籤
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: 本文討論傳統 Azure Active Directory 分類和敏感度標籤。
ms.openlocfilehash: 1be7e31ee4091e561f7eedb34b41958efc69a339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926331"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Microsoft 365 群組的 Azure Active Directory 分類和敏感度標籤

本文討論傳統 Azure Active Directory 分類和敏感度標籤。

[這些服務](./sensitivity-labels-teams-groups-sites.md#support-for-the-sensitivity-labels)支援敏感性標籤。

如需敏感度標籤的完整資訊，請參閱 [瞭解敏感度標籤](sensitivity-labels.md)。

若要深入瞭解敏感度標籤及其對於網站和 Microsoft 365 群組的行為，請參閱 [使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](sensitivity-labels-teams-groups-sites.md)。

從傳統的 AAD 分類遷移到敏感度標籤時，請參閱下列案例以取得最佳作法。

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>案例1：租使用者永不使用傳統 AAD 分類或檔和電子郵件的敏感度標籤

- 租使用者系統管理員透過 AAD powershell Cmdlet 將租使用者標誌 "EnableMIPLabels" 設定為 true，即可為群組啟用敏感度標籤。
- 租使用者系統管理員會在 [Microsoft 365 規範中心](https://compliance.microsoft.com)內建立靈敏度標籤。
    - 租使用者管理員可以選擇檔案和電子郵件相關的動作，例如加密和浮水印。
    - 承租人管理員可以選擇 Microsoft 365 群組，並 SharePoint 與網站相關的線上動作至靈敏度標籤。
- 租使用者系統管理員會發佈原則。
- **相容工作負載** 顯示敏感度標籤。 使用靈敏度標籤建立群組。 相容工作負載是支援靈敏度標籤的服務。
- **不相容的工作負載** 是指尚未支援敏感性標籤的服務。 不過，您可以建立群組，但無法透過不相容的工作負載與敏感度標籤相關聯。 若要將這類群組與敏感度標籤相關聯，租使用者系統管理員可以執行 PowerShell Cmdlet。

表 1. 相容和非相容工作負載的行為–建立、編輯或刪除群組

|工作負載|使用者可在群組視窗中看見的標籤清單？|建立新的群組 |編輯群組 |刪除群組 |
|:-------|:-------|:--------|:--------|:--------|   
|相容   |敏感度標籤。 |不會變更行為。 |不會變更行為。 |不會變更行為。 |
|不相容 |不顯示敏感度標籤。 |使用者可以建立沒有選取敏感度標籤的群組。 <br><br> 請注意，系統管理員可以執行 Cmdlet，以在背景套用敏感度標籤。 |**案例 1**：尚未選取任何敏感度標籤。 使用者可以編輯群組。<br><br> **案例 2**：使用 Cmdlet 于背景中的敏感度標籤。 使用者可以成功編輯群組，不需要使用者選擇標籤的無效隱私權組合的情況。 |不會變更行為。|

> [!NOTE]
> 在 Outlook 桌面用戶端 (Win 32) 時，系統管理員會在其承租人上啟用敏感度標籤，而其使用者位於舊版的 Outlook 桌面用戶端 (Win 32) ：
>
> - 使用者看到敏感度標籤會出現在舊版的 Outlook desktop 用戶端上。
> - 不過，當使用者編輯群組，並以靈敏度標籤儲存群組時，所選取的隱私權設定會被套用靈敏度標籤的隱私權設定所取代。
>
> 建議您的使用者在舊版本的 Outlook 用戶端升級至較新的版本。

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>案例2：承租人已使用傳統的 AAD [分類](../enterprise/manage-microsoft-365-groups-with-powershell.md)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>案例 A：承租人永不對檔和電子郵件使用敏感度標籤

1. 在 [Microsoft 365 規範中心](https://compliance.microsoft.com)，我們建議您建立與現有傳統 Azure AD 標籤具有相同名稱的靈敏度標籤。
2. 使用 PowerShell Cmdlet，將這些敏感度標籤套用至現有的 Microsoft 365 群組，並使用名稱對應套用 SharePoint 網站。
3. 管理員可以選擇刪除傳統 Azure AD 標籤：
    - 相容工作負載顯示這些敏感度標籤和群組是以它們建立。
    - 不相容的工作負載會在建立群組時運作，但不會附加任何敏感度標籤。
4. 系統管理員可以執行 PowerShell Cmdlet，將敏感度標籤套用至不含標籤的群組。
    - 或者，系統管理員可以選擇保留傳統 Azure AD 標籤：
        - 相容工作負載會顯示這些敏感度標籤，而群組會自行建立。 相容工作負載是支援靈敏度標籤的服務。
        - 在建立群組時，不相容的工作負載會正常運作，並顯示傳統的 Azure AD 標籤。 這些傳統 Azure AD 標籤會附加到以不相容的工作負載建立的這些群組。
5. 我們強烈建議管理員執行 PowerShell Cmdlet，將敏感度標籤套用至使用傳統 Azure AD 標籤的群組。

表 2. 相容和非相容工作負載的行為–建立、編輯或刪除群組

|工作負載|使用者可在群組視窗中看見的標籤清單？|建立新的群組 |編輯群組 |刪除群組 |
|:-------|:-------|:--------|:--------|:--------|   
|相容   |敏感度標籤。 |不會變更行為。 |不會變更行為。 |不會變更行為。 |
|不相容 |舊的傳統 AAD 標籤。 |使用者可以建立已選取 [傳統 Azure AD] 標籤的群組。 <br><br>請注意，系統管理員可以執行 Cmdlet，以在背景套用敏感度標籤。 |**案例 1**：尚未選取任何敏感度標籤。 使用者可以編輯群組。<br><br> **案例 2**：先前選取的傳統 AAD 標籤。 使用者可以編輯群組。<br><br> **案例 3**：先前使用 Cmdlet 于背景中套用的敏感度標籤。 使用者應該可以編輯群組，但不包括一種案例，使用者可以在標籤中選取 [隱私權] 設定的無效組合。 |使用者可以刪除群組。 |

> [!NOTE]
> 在 Outlook 桌面用戶端 (Win 32) 時，系統管理員會在其承租人上啟用敏感度標籤，而其使用者位於舊版的 Outlook 桌面用戶端 (Win 32) ：
>
> - 使用者看到敏感度標籤會出現在舊版的 Outlook desktop 用戶端上。
> - 不過，當使用者編輯群組，並以靈敏度標籤儲存群組時，所選取的隱私權設定會被套用靈敏度標籤的隱私權設定所取代。
>
> 建議您的使用者在舊版本的 Outlook 用戶端升級至較新的版本。

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>案例 B：租使用者對檔和電子郵件使用敏感度標籤

1. 在承租人上，系統管理員只要將租使用者旗標 ' EnableMIPLabels ' 設定為 true，就會顯示 [群組/網站/小組建立及編輯] 對話方塊中的 [檔和電子郵件敏感度] 標籤。
2. 系統管理員可以使用相同的檔和電子郵件敏感度標籤，透過指定相關的群組設定，在群組/網站/小組上強制執行隱私權和外部使用者存取：
    1. 在 [ [Microsoft 365 規範中心](https://compliance.microsoft.com)] 中，選取 [ **網站和群組** ] 索引標籤。
    2. 編輯檔或電子郵件敏感度標籤。

## <a name="sample-script"></a>指令碼範例

如需將具有傳統 AAD 標籤的群組遷移至敏感度標籤的範例腳本，請參閱 [傳統 AZURE AD 群組分類](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification)。