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
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688662"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行遷移的 AD FS 遷移步驟

若要從 Microsoft Cloud Deutschland 遷移 Active Directory Federation Services (AD FS) 伺服器陣列：

1. 使用 [下列步驟](#backup)備份您的 AD FS 設定包括 FF 信任資訊。 命名備份 **Microsoft cloud Deutschland_Only** ，以表示它只具有 Microsoft Cloud Deutschland 租使用者資訊。
2. 使用 Microsoft 雲端 Deutschland_Only 備份來測試還原，AD FS 伺服器陣列應該繼續以 Microsoft Cloud Deutschland 的方式運作。
3. 從 **AD FS > Office 365 服務** 建立新的信賴憑證者信任。
4. 在 [AD FS 管理主控台] 中的 [信賴憑證者 **信任** ] 中，選取 [ **新增信賴** 憑證者信任]。
5. 在 [新增信賴憑證者信任] 嚮導的 [**歡迎**] 頁面上選取 **[下一步**]。
6. 在 [ **選取資料來源** ] 頁面上，選取 [匯 **入已發佈線上或本機網路上的信賴憑證者相關資料**]。 **(主機名稱或 URL) 值的同盟中繼資料位址** 設為 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。 按 [下一步 **]**。
7. 在 [ **選取資料來源** ] 頁面上，輸入顯示名稱。 Microsoft 建議 **全球的 Microsoft Office 365 身分識別平臺**。 按 [下一步 **]**。
8. 在 [**立即設定多重要素驗證**] 中按 **[下一步]** ，**選擇 [發行授權規則**]，並 **準備好新增信任** 頁面。
9. 按一下 [**完成]** 頁面上的 [**關閉**]。

關閉嚮導後，就會建立 Office 365 服務 eSTS 的信賴憑證者信任。 不過，不會建立任何發行轉換規則。

您可以使用 [AD FS 説明](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 產生正確的發行轉換規則。 您可以透過 AD FS 管理主控台或 PowerShell，手動新增以 AD FS 協助所產生的宣告規則。 AD FS 説明會產生必要的 PowerShell 腳本，必須執行。  

1. Run 在 AD FS 說明上執行 [ **產生宣告** ]，然後使用腳本的右上角的 [ **複製** ] 選項，複製 PowerShell 宣告轉換腳本。
2. 將產生的 PowerShell 貼到下列專案：

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  執行已完成的腳本。
4.  確認兩個信賴憑證者信任都存在;一個供全球用，一個用於 BF。
5.  使用 [下列步驟](#backup)備份您的信任。 使用名稱 **FFAndWorldwide** 進行儲存。
6.  完成後端遷移，並確認 AD FS 在遷移過程中仍可運作。

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

## <a name="more-information"></a>其他資訊

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
