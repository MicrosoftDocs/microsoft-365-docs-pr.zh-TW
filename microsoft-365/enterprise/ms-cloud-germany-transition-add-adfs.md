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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="3197e-103">從 Microsoft Cloud Deutschland 進行遷移的 AD FS 遷移步驟</span><span class="sxs-lookup"><span data-stu-id="3197e-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="3197e-104">若要從 Microsoft Cloud Deutschland 遷移 Active Directory Federation Services (AD FS) 伺服器陣列：</span><span class="sxs-lookup"><span data-stu-id="3197e-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="3197e-105">使用 [下列步驟](#backup)備份您的 AD FS 設定包括 FF 信任資訊。</span><span class="sxs-lookup"><span data-stu-id="3197e-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="3197e-106">命名備份 **Microsoft cloud Deutschland_Only** ，以表示它只具有 Microsoft Cloud Deutschland 租使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="3197e-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="3197e-107">使用 Microsoft 雲端 Deutschland_Only 備份來測試還原，AD FS 伺服器陣列應該繼續以 Microsoft Cloud Deutschland 的方式運作。</span><span class="sxs-lookup"><span data-stu-id="3197e-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="3197e-108">從 **AD FS > Office 365 服務** 建立新的信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="3197e-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="3197e-109">在 [AD FS 管理主控台] 中的 [信賴憑證者 **信任** ] 中，選取 [ **新增信賴** 憑證者信任]。</span><span class="sxs-lookup"><span data-stu-id="3197e-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="3197e-110">在 [新增信賴憑證者信任] 嚮導的 [**歡迎**] 頁面上選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="3197e-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="3197e-111">在 [ **選取資料來源** ] 頁面上，選取 [匯 **入已發佈線上或本機網路上的信賴憑證者相關資料**]。</span><span class="sxs-lookup"><span data-stu-id="3197e-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="3197e-112">**(主機名稱或 URL) 值的同盟中繼資料位址** 設為 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。</span><span class="sxs-lookup"><span data-stu-id="3197e-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="3197e-113">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="3197e-113">Click **Next**.</span></span>
7. <span data-ttu-id="3197e-114">在 [ **選取資料來源** ] 頁面上，輸入顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="3197e-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="3197e-115">Microsoft 建議 **全球的 Microsoft Office 365 身分識別平臺**。</span><span class="sxs-lookup"><span data-stu-id="3197e-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="3197e-116">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="3197e-116">Click **Next**.</span></span>
8. <span data-ttu-id="3197e-117">在 [**立即設定多重要素驗證**] 中按 **[下一步]** ，**選擇 [發行授權規則**]，並 **準備好新增信任** 頁面。</span><span class="sxs-lookup"><span data-stu-id="3197e-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="3197e-118">按一下 [**完成]** 頁面上的 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3197e-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="3197e-119">關閉嚮導後，就會建立 Office 365 服務 eSTS 的信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="3197e-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="3197e-120">不過，不會建立任何發行轉換規則。</span><span class="sxs-lookup"><span data-stu-id="3197e-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="3197e-121">您可以使用 [AD FS 説明](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 產生正確的發行轉換規則。</span><span class="sxs-lookup"><span data-stu-id="3197e-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="3197e-122">您可以透過 AD FS 管理主控台或 PowerShell，手動新增以 AD FS 協助所產生的宣告規則。</span><span class="sxs-lookup"><span data-stu-id="3197e-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="3197e-123">AD FS 説明會產生必要的 PowerShell 腳本，必須執行。</span><span class="sxs-lookup"><span data-stu-id="3197e-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="3197e-124">Run 在 AD FS 說明上執行 [ **產生宣告** ]，然後使用腳本的右上角的 [ **複製** ] 選項，複製 PowerShell 宣告轉換腳本。</span><span class="sxs-lookup"><span data-stu-id="3197e-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="3197e-125">將產生的 PowerShell 貼到下列專案：</span><span class="sxs-lookup"><span data-stu-id="3197e-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="3197e-126">執行已完成的腳本。</span><span class="sxs-lookup"><span data-stu-id="3197e-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="3197e-127">確認兩個信賴憑證者信任都存在;一個供全球用，一個用於 BF。</span><span class="sxs-lookup"><span data-stu-id="3197e-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="3197e-128">使用 [下列步驟](#backup)備份您的信任。</span><span class="sxs-lookup"><span data-stu-id="3197e-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="3197e-129">使用名稱 **FFAndWorldwide** 進行儲存。</span><span class="sxs-lookup"><span data-stu-id="3197e-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="3197e-130">完成後端遷移，並確認 AD FS 在遷移過程中仍可運作。</span><span class="sxs-lookup"><span data-stu-id="3197e-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="3197e-131"> (WID 資料庫) 的 AD FS 災難修復</span><span class="sxs-lookup"><span data-stu-id="3197e-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="3197e-132">若要在嚴重損壞的 [ad](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) fs 伺服器陣列中還原 ad fs 伺服器陣列，您必須加以利用。</span><span class="sxs-lookup"><span data-stu-id="3197e-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="3197e-133">因此，必須先下載工具，並在開始進行遷移之前，必須先建立備份，並安全地儲存備份。</span><span class="sxs-lookup"><span data-stu-id="3197e-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="3197e-134">在此範例中 (TAT 環境) 已執行下列命令以備份伺服器陣列：</span><span class="sxs-lookup"><span data-stu-id="3197e-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="3197e-135">備份 AD FS 伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="3197e-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="3197e-136">在主要 AD FS 伺服器上安裝 AD FS 快速還原工具。</span><span class="sxs-lookup"><span data-stu-id="3197e-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="3197e-137">使用此命令，匯入 PowerShell 會話中的模組。</span><span class="sxs-lookup"><span data-stu-id="3197e-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="3197e-138">執行備份命令：</span><span class="sxs-lookup"><span data-stu-id="3197e-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="3197e-139">將備份安全地儲存在所需的目的地。</span><span class="sxs-lookup"><span data-stu-id="3197e-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="3197e-140">還原 AD FS 伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="3197e-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="3197e-141">如果您的伺服器陣列完全失敗，且無法返回舊的伺服器陣列，請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="3197e-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="3197e-142">將先前產生及儲存的備份移至新的主要 AD FS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3197e-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="3197e-143">執行下列 `Restore-ADFS` PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="3197e-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="3197e-144">如有必要，請預先匯入 AD FS SSL 憑證。</span><span class="sxs-lookup"><span data-stu-id="3197e-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="3197e-145">將新的 DNS 記錄或負載平衡器指向新的 AD FS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3197e-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="3197e-146">其他資訊</span><span class="sxs-lookup"><span data-stu-id="3197e-146">More information</span></span>

<span data-ttu-id="3197e-147">開始：</span><span class="sxs-lookup"><span data-stu-id="3197e-147">Getting started:</span></span>

- [<span data-ttu-id="3197e-148">從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務</span><span class="sxs-lookup"><span data-stu-id="3197e-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="3197e-149">Microsoft Cloud Deutschland 移轉協助</span><span class="sxs-lookup"><span data-stu-id="3197e-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="3197e-150">如何選擇加入移轉</span><span class="sxs-lookup"><span data-stu-id="3197e-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="3197e-151">遷移期間的客戶體驗</span><span class="sxs-lookup"><span data-stu-id="3197e-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="3197e-152">在轉換中移動：</span><span class="sxs-lookup"><span data-stu-id="3197e-152">Moving through the transition:</span></span>

- [<span data-ttu-id="3197e-153">移轉階段的動作與影響</span><span class="sxs-lookup"><span data-stu-id="3197e-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="3197e-154">其他預備工作</span><span class="sxs-lookup"><span data-stu-id="3197e-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="3197e-155">[AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="3197e-155">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="3197e-156">雲端應用程式：</span><span class="sxs-lookup"><span data-stu-id="3197e-156">Cloud apps:</span></span>

- [<span data-ttu-id="3197e-157">Dynamics 365 的移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="3197e-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="3197e-158">Power BI 移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="3197e-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="3197e-159">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3197e-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
