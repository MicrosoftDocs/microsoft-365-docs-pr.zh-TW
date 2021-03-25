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
ms.openlocfilehash: 12465acf5b4afe7e252586ddd076250628b57dd3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165654"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="cc97c-103">從 Microsoft Cloud Deutschland 進行遷移的 AD FS 遷移步驟</span><span class="sxs-lookup"><span data-stu-id="cc97c-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="cc97c-104">在第2階段開始之前，必須套用此設定變更。</span><span class="sxs-lookup"><span data-stu-id="cc97c-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="cc97c-105">當階段2完成之後，設定變更便可運作，而且您可以透過 Office 365 全域端點（例如）登入 `https://portal.office.com` 。</span><span class="sxs-lookup"><span data-stu-id="cc97c-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="cc97c-106">如果您要在第2階段之前實施設定變更，Office 365 全域端點仍會 _運作_ ，但新的信賴憑證者信任仍是 Active Directory Federation SERVICES (AD FS) 設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="cc97c-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="cc97c-107">使用同盟驗證搭配 Active Directory Federation Services (AD FS 的客戶) 不應該對使用內部部署 Active Directory 網域服務之所有驗證的發行人 URIs 進行變更，以進行遷移時 (AD DS) 。</span><span class="sxs-lookup"><span data-stu-id="cc97c-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="cc97c-108">變更簽發者 URIs 會導致網域中的使用者驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="cc97c-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="cc97c-109">簽發者 URIs 可以直接在 AD FS 中變更，或將網域從 _managed_ 轉換成 _同盟，反之亦然_ 。</span><span class="sxs-lookup"><span data-stu-id="cc97c-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="cc97c-110">建議您不要在已遷移的 Azure AD 租使用者中新增、移除或轉換同盟網域。</span><span class="sxs-lookup"><span data-stu-id="cc97c-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="cc97c-111">在遷移完全完成後，可以變更發行者 URIs。</span><span class="sxs-lookup"><span data-stu-id="cc97c-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="cc97c-112">若要準備用於從 Microsoft Cloud Deutschland 進行遷移的 AD FS 伺服器陣列，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cc97c-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="cc97c-113">使用 [下列步驟](#backup)備份您的 AD FS 設定，包括現有的 Microsoft Cloud Deutschland 信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="cc97c-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="cc97c-114">命名備份 **MicrosoftCloudDeutschlandOnly** ，以表示它只具有 Microsoft Cloud Deutschland 租使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="cc97c-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cc97c-115">此備份不僅會包含適用于 Microsoft Cloud Deutschland 的現有 Office 365 信賴憑證者信任，還會在各自的 AD FS 伺服器陣列上顯示所有其他信賴憑證方信任。</span><span class="sxs-lookup"><span data-stu-id="cc97c-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="cc97c-116">使用 MicrosoftCloudDeutschlandOnly 備份測試還原，AD FS 伺服器陣列應繼續以 Microsoft Cloud Deutschland 的方式運作。</span><span class="sxs-lookup"><span data-stu-id="cc97c-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="cc97c-117">完成並測試 AD FS 備份後，請執行下列步驟，以將新的信賴憑證者信任新增至 ADFS 設定：</span><span class="sxs-lookup"><span data-stu-id="cc97c-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="cc97c-118">開啟 [AD FS 管理主控台]。</span><span class="sxs-lookup"><span data-stu-id="cc97c-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="cc97c-119">在 ADFS 管理主控台的左窗格中，流覽至 [ **信賴** 憑證者信任] 功能表。</span><span class="sxs-lookup"><span data-stu-id="cc97c-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="cc97c-120">在右窗格中，選取 [**新增信賴憑證者信任 ...** ]。</span><span class="sxs-lookup"><span data-stu-id="cc97c-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="cc97c-121">在 [新增信賴憑證者信任] 嚮導的 [**歡迎**] 頁面上，選取 [**啟動**]。</span><span class="sxs-lookup"><span data-stu-id="cc97c-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="cc97c-122">在 [ **選取資料來源** ] 頁面上，選取 [匯 **入已發佈線上或本機網路上的信賴憑證者相關資料**]。</span><span class="sxs-lookup"><span data-stu-id="cc97c-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="cc97c-123">**(主機名稱或 URL) 值的同盟中繼資料位址** 必須設定為 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。</span><span class="sxs-lookup"><span data-stu-id="cc97c-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="cc97c-124">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="cc97c-124">Click **Next**.</span></span>

6. <span data-ttu-id="cc97c-125">在 [ **指定顯示名稱** ] 頁面上，輸入顯示名稱，例如「 **全球通用的 Microsoft Office 365 身分識別平臺**」。</span><span class="sxs-lookup"><span data-stu-id="cc97c-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="cc97c-126">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="cc97c-126">Click **Next**.</span></span>

7. <span data-ttu-id="cc97c-127">如果您是在 Windows Server 2012 中使用 ADFS，請在 [嚮導] 頁面上的 [ **立即設定多重要素驗證？**] 中，根據您的驗證需求選取適當的選項。</span><span class="sxs-lookup"><span data-stu-id="cc97c-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="cc97c-128">如果您堅持使用預設值，請選取 [ **我不想要設定此信賴憑證者信任的多重要素驗證設定**]。</span><span class="sxs-lookup"><span data-stu-id="cc97c-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="cc97c-129">您可以稍後在需要時變更此設定。</span><span class="sxs-lookup"><span data-stu-id="cc97c-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="cc97c-130">針對 AD FS 2012：在 [ **選擇發行授權規則**] 上，[保留 **允許所有使用者存取此信賴憑證方** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cc97c-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

9. <span data-ttu-id="cc97c-131">針對 AD FS 2016 和 AD FS 2019：在 [ **選擇存取控制原則** ] 頁面上，選取適當的存取控制原則，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cc97c-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="cc97c-132">若未選擇 [無]，信賴憑證者信任將 **無法** 運作。</span><span class="sxs-lookup"><span data-stu-id="cc97c-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

10. <span data-ttu-id="cc97c-133">在 [**準備新增信任**] 頁面上，按一下 **[下一步**] 完成該嚮導。</span><span class="sxs-lookup"><span data-stu-id="cc97c-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

11. <span data-ttu-id="cc97c-134">按一下 [**完成]** 頁面上的 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="cc97c-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="cc97c-135">關閉嚮導後，就會建立與 Office 365 泛型服務的信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="cc97c-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="cc97c-136">不過，尚未設定發行轉換規則。</span><span class="sxs-lookup"><span data-stu-id="cc97c-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="cc97c-137">您可以使用 [AD FS 説明](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 產生正確的發行轉換規則。</span><span class="sxs-lookup"><span data-stu-id="cc97c-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="cc97c-138">您可以透過 AD FS 管理主控台或 PowerShell，手動新增以 AD FS 協助所產生的宣告規則。</span><span class="sxs-lookup"><span data-stu-id="cc97c-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="cc97c-139">AD FS 説明會產生必要執行的必要 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="cc97c-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="cc97c-140">[AD FS 説明](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 會產生產品隨附的標準發行轉換規則。</span><span class="sxs-lookup"><span data-stu-id="cc97c-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="cc97c-141">不過，如果在 Microsoft 雲端 Deutschland 信賴憑證者信任 (中使用自訂發行轉換規則，例如，自訂發行者 URIs、非標準不彈性識別碼s 或任何其他自訂) ，必須修改 AD FS 説明所產生的規則，使其符合目前就地適用于 Microsoft Cloud Deutschland 信賴憑證者信任的自訂邏輯。</span><span class="sxs-lookup"><span data-stu-id="cc97c-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="cc97c-142">如果這些自訂未在透過 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)說明所產生的規則內整合，則 **全球的 Microsoft Office 365 身分識別平臺** 驗證很可能 **無法** 用於您的同盟身分識別。</span><span class="sxs-lookup"><span data-stu-id="cc97c-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="cc97c-143">Run 在 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)說明上執行 [**產生宣告**]，並使用腳本右上角的 [**複製**] 選項來複製 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="cc97c-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="cc97c-144">請遵循在 Ad fs 伺服器陣列中執行 PowerShell 腳本以產生全域信賴憑證者信任的 [AD fs](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 說明中所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="cc97c-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span> <span data-ttu-id="cc97c-145">在執行腳本之前，請將下列程式程式碼取代產生的腳本，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc97c-145">Before you run the script, replace the following code lines in the generated script as outlined below:</span></span>

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. <span data-ttu-id="cc97c-146">確認有兩個信賴 PartyTtrusts 存在;一個用於 Microsoft Cloud Deutschland，另一個適用于 Office 365 全域服務。</span><span class="sxs-lookup"><span data-stu-id="cc97c-146">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="cc97c-147">您可以利用下列命令進行檢查。</span><span class="sxs-lookup"><span data-stu-id="cc97c-147">The following command can be leveraged for the check.</span></span> <span data-ttu-id="cc97c-148">它應傳回兩列以及各自的名稱和識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc97c-148">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="cc97c-149">使用 [下列步驟](#backup)，備份您的完整遷移設定，包括信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="cc97c-149">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="cc97c-150">使用名稱 **MicrosoftCloudDeutschlandAndWorldwide** 進行儲存。</span><span class="sxs-lookup"><span data-stu-id="cc97c-150">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="cc97c-151">當您的租使用者處於遷移時，請定期確認 AD FS 驗證使用的是 Microsoft Cloud Deutschland and Microsoft Global Cloud in 各種支援的遷移步驟。</span><span class="sxs-lookup"><span data-stu-id="cc97c-151">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="cc97c-152"> (WID 資料庫) 的 AD FS 災難修復</span><span class="sxs-lookup"><span data-stu-id="cc97c-152">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="cc97c-153">若要在嚴重損壞的 [ad](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) fs 伺服器陣列中還原 ad fs 伺服器陣列，您必須加以利用。</span><span class="sxs-lookup"><span data-stu-id="cc97c-153">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="cc97c-154">因此，必須先下載工具，並在開始進行遷移之前，必須先建立備份，並安全地儲存備份。</span><span class="sxs-lookup"><span data-stu-id="cc97c-154">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="cc97c-155">在此範例中，已執行下列命令來備份在 WID 資料庫上執行的伺服器陣列：</span><span class="sxs-lookup"><span data-stu-id="cc97c-155">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="cc97c-156">備份 AD FS 伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="cc97c-156">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="cc97c-157">在主要 AD FS 伺服器上安裝 AD FS 快速還原工具。</span><span class="sxs-lookup"><span data-stu-id="cc97c-157">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="cc97c-158">使用此命令，匯入 PowerShell 會話中的模組。</span><span class="sxs-lookup"><span data-stu-id="cc97c-158">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="cc97c-159">執行備份命令：</span><span class="sxs-lookup"><span data-stu-id="cc97c-159">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="cc97c-160">將備份安全地儲存在所需的目的地。</span><span class="sxs-lookup"><span data-stu-id="cc97c-160">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="cc97c-161">還原 AD FS 伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="cc97c-161">Restore an AD FS Farm</span></span>

<span data-ttu-id="cc97c-162">如果您的伺服器陣列完全失敗，且無法返回舊的伺服器陣列，請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="cc97c-162">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="cc97c-163">將先前產生及儲存的備份移至新的主要 AD FS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc97c-163">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="cc97c-164">執行下列 `Restore-ADFS` PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="cc97c-164">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="cc97c-165">如有必要，請預先匯入 AD FS SSL 憑證。</span><span class="sxs-lookup"><span data-stu-id="cc97c-165">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="cc97c-166">將新的 DNS 記錄或負載平衡器指向新的 AD FS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc97c-166">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="cc97c-167">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="cc97c-167">More information</span></span>

<span data-ttu-id="cc97c-168">開始：</span><span class="sxs-lookup"><span data-stu-id="cc97c-168">Getting started:</span></span>

- [<span data-ttu-id="cc97c-169">從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務</span><span class="sxs-lookup"><span data-stu-id="cc97c-169">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="cc97c-170">Microsoft Cloud Deutschland 移轉協助</span><span class="sxs-lookup"><span data-stu-id="cc97c-170">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="cc97c-171">如何選擇加入移轉</span><span class="sxs-lookup"><span data-stu-id="cc97c-171">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="cc97c-172">遷移期間的客戶體驗</span><span class="sxs-lookup"><span data-stu-id="cc97c-172">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="cc97c-173">在轉換中移動：</span><span class="sxs-lookup"><span data-stu-id="cc97c-173">Moving through the transition:</span></span>

- [<span data-ttu-id="cc97c-174">移轉階段的動作與影響</span><span class="sxs-lookup"><span data-stu-id="cc97c-174">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="cc97c-175">其他預備工作</span><span class="sxs-lookup"><span data-stu-id="cc97c-175">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="cc97c-176">[AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="cc97c-176">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="cc97c-177">雲端應用程式：</span><span class="sxs-lookup"><span data-stu-id="cc97c-177">Cloud apps:</span></span>

- [<span data-ttu-id="cc97c-178">Dynamics 365 的移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="cc97c-178">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="cc97c-179">Power BI 移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="cc97c-179">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="cc97c-180">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc97c-180">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
