---
title: 從 Microsoft Cloud Deutschland 進行遷移的 AD FS 遷移步驟
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要： Active Directory Federation Services (AD FS) 從 Microsoft Cloud Deutschland 進行遷移的遷移步驟。
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727464"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行遷移的 AD FS 遷移步驟

在第4階段開始之前，您可以隨時套用此設定變更。
當階段2完成之後，設定變更便可運作，而且您可以登入 Office 365 全域端點，例如 `https://portal.office.com` 。 如果您要在第2階段之前實施設定變更，Office 365 全域端點仍會 _運作_ ，但新的信賴憑證者信任仍是 Active Directory Federation SERVICES (AD FS) 設定的一部分。

若要從 Microsoft Cloud Deutschland 遷移您的 AD FS 伺服器陣列：

1. 使用 [下列步驟](#backup)備份您的 AD FS 設定包括 FF 信任資訊。 命名備份 **Microsoft cloud Deutschland_Only** ，以表示它只具有 Microsoft Cloud Deutschland 租使用者資訊。
2. 使用 Microsoft 雲端 Deutschland_Only 備份來測試還原，AD FS 伺服器陣列應該繼續以 Microsoft Cloud Deutschland 的方式運作。

完成並測試 AD FS 備份後，請執行下列步驟，以將新的信賴憑證者信任新增至 ADFS 設定：

1. 開啟 AD FS 管理主控台
2. 在 ADFS 管理主控台的左窗格中，依次展開 [ **adfs**]、[**信任關係**] 及 [信賴憑證者 **信任**]。
3. 在右窗格中，選取 [**新增信賴憑證者信任 ...** ]。
4. 在 [新增信賴憑證者信任] 嚮導的 [**歡迎**] 頁面上選取 **[下一步**]。
5. 在 [ **選取資料來源** ] 頁面上，選取 [匯 **入已發佈線上或本機網路上的信賴憑證者相關資料**]。 **(主機名稱或 URL) 值的同盟中繼資料位址** 必須設定為 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。 然後按一下 **「下一步」**。
6. 在 [ **選取資料來源** ] 頁面上，輸入顯示名稱，例如「 **全球通用的 Microsoft Office 365 身分識別平臺**」。 然後按一下 **「下一步」**。
7. 在 [嚮導] 頁面 [ **立即設定多重要素驗證？**] 中，根據您的驗證需求選取適當的選項。 如果您堅持使用預設值，請選取 [ **我不想要設定此信賴憑證者信任的多重要素驗證設定**]。 您可以稍後在需要時變更此設定。
8. 在 [**選擇發行授權規則**] 下，保留 [**允許所有使用者存取此信賴憑證方** **] 按 [下一步]** 。
9. 在 [**準備新增信任**] 頁面上，按一下 **[下一步**] 完成該嚮導。
10. 按一下 [**完成]** 頁面上的 [**關閉**]。

關閉嚮導後，就會建立與 Office 365 泛型服務的信賴憑證者信任。 不過，尚未設定發行轉換規則。

您可以使用 [AD FS 説明](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 產生正確的發行轉換規則。 您可以透過 AD FS 管理主控台或 PowerShell，手動新增以 AD FS 協助所產生的宣告規則。 AD FS 説明會產生必要執行的必要 PowerShell 腳本。  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. Run 在 AD FS 說明上執行 [ **產生宣告** ]，然後使用腳本的右上角的 [ **複製** ] 選項，複製 PowerShell 宣告轉換腳本。
2. 開啟您偏好的文字編輯器，並將 PowerShell 腳本貼到新的文字視窗中。
3. 在步驟2中，將下列 PowerShell 行新增至已貼上腳本的結尾
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. 安全並執行 PowerShell 腳本。
5. 確認兩個信賴憑證者信任都存在;一個用於 Microsoft Cloud Deutschland，另一個適用于 Office 365 全域服務。
6. 使用 [下列步驟](#backup)備份您的信任。 使用名稱 **FFAndWorldwide** 進行儲存。
7. 完成您的後端遷移，並確認 AD FS 在遷移過程中仍可運作。

## <a name="ad-fs-disaster-recovery-wid-database"></a> (WID 資料庫) 的 AD FS 災難修復

若要在嚴重損壞的 [ad](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) fs 伺服器陣列中還原 ad fs 伺服器陣列，您必須加以利用。 因此，必須先下載工具，並在開始進行遷移之前，必須先建立備份，並安全地儲存備份。 在此範例中 (TAT 環境) 已執行下列命令以備份伺服器陣列：

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>備份 AD FS 伺服器陣列

1. 在主要 AD FS 伺服器上安裝 AD FS 快速還原工具。
2. 使用此命令，匯入 PowerShell 會話中的模組。
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. 執行備份命令：
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. 將備份安全地儲存在所需的目的地。

### <a name="restore-an-ad-fs-farm"></a>還原 AD FS 伺服器陣列

如果您的伺服器陣列完全失敗，且無法返回舊的伺服器陣列，請執行下列動作。 

1. 將先前產生及儲存的備份移至新的主要 AD FS 伺服器。
2. 執行下列 `Restore-ADFS` PowerShell 命令。 如有必要，請預先匯入 AD FS SSL 憑證。

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. 將新的 DNS 記錄或負載平衡器指向新的 AD FS 伺服器。

## <a name="more-information"></a>詳細資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
