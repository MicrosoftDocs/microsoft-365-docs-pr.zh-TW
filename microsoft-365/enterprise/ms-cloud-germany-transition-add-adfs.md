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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="7f4cd-103">從 Microsoft Cloud Deutschland 進行遷移的 AD FS 遷移步驟</span><span class="sxs-lookup"><span data-stu-id="7f4cd-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="7f4cd-104">在第4階段開始之前，您可以隨時套用此設定變更。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="7f4cd-105">當階段2完成之後，設定變更便可運作，而且您可以登入 Office 365 全域端點，例如 `https://portal.office.com` 。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="7f4cd-106">如果您要在第2階段之前實施設定變更，Office 365 全域端點仍會 _運作_ ，但新的信賴憑證者信任仍是 Active Directory Federation SERVICES (AD FS) 設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="7f4cd-107">若要從 Microsoft Cloud Deutschland 遷移您的 AD FS 伺服器陣列：</span><span class="sxs-lookup"><span data-stu-id="7f4cd-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="7f4cd-108">使用 [下列步驟](#backup)備份您的 AD FS 設定包括 FF 信任資訊。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="7f4cd-109">命名備份 **Microsoft cloud Deutschland_Only** ，以表示它只具有 Microsoft Cloud Deutschland 租使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="7f4cd-110">使用 Microsoft 雲端 Deutschland_Only 備份來測試還原，AD FS 伺服器陣列應該繼續以 Microsoft Cloud Deutschland 的方式運作。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="7f4cd-111">完成並測試 AD FS 備份後，請執行下列步驟，以將新的信賴憑證者信任新增至 ADFS 設定：</span><span class="sxs-lookup"><span data-stu-id="7f4cd-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="7f4cd-112">開啟 AD FS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="7f4cd-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="7f4cd-113">在 ADFS 管理主控台的左窗格中，依次展開 [ **adfs**]、[**信任關係**] 及 [信賴憑證者 **信任**]。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="7f4cd-114">在右窗格中，選取 [**新增信賴憑證者信任 ...** ]。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="7f4cd-115">在 [新增信賴憑證者信任] 嚮導的 [**歡迎**] 頁面上選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="7f4cd-116">在 [ **選取資料來源** ] 頁面上，選取 [匯 **入已發佈線上或本機網路上的信賴憑證者相關資料**]。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="7f4cd-117">**(主機名稱或 URL) 值的同盟中繼資料位址** 必須設定為 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="7f4cd-118">然後按一下 **「下一步」**。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="7f4cd-119">在 [ **選取資料來源** ] 頁面上，輸入顯示名稱，例如「 **全球通用的 Microsoft Office 365 身分識別平臺**」。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="7f4cd-120">然後按一下 **「下一步」**。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="7f4cd-121">在 [嚮導] 頁面 [ **立即設定多重要素驗證？**] 中，根據您的驗證需求選取適當的選項。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="7f4cd-122">如果您堅持使用預設值，請選取 [ **我不想要設定此信賴憑證者信任的多重要素驗證設定**]。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="7f4cd-123">您可以稍後在需要時變更此設定。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="7f4cd-124">在 [**選擇發行授權規則**] 下，保留 [**允許所有使用者存取此信賴憑證方** **] 按 [下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="7f4cd-125">在 [**準備新增信任**] 頁面上，按一下 **[下一步**] 完成該嚮導。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="7f4cd-126">按一下 [**完成]** 頁面上的 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="7f4cd-127">關閉嚮導後，就會建立與 Office 365 泛型服務的信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="7f4cd-128">不過，尚未設定發行轉換規則。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="7f4cd-129">您可以使用 [AD FS 説明](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 產生正確的發行轉換規則。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="7f4cd-130">您可以透過 AD FS 管理主控台或 PowerShell，手動新增以 AD FS 協助所產生的宣告規則。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="7f4cd-131">AD FS 説明會產生必要執行的必要 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="7f4cd-132">Run 在 AD FS 說明上執行 [ **產生宣告** ]，然後使用腳本的右上角的 [ **複製** ] 選項，複製 PowerShell 宣告轉換腳本。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="7f4cd-133">開啟您偏好的文字編輯器，並將 PowerShell 腳本貼到新的文字視窗中。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="7f4cd-134">在步驟2中，將下列 PowerShell 行新增至已貼上腳本的結尾</span><span class="sxs-lookup"><span data-stu-id="7f4cd-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="7f4cd-135">安全並執行 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="7f4cd-136">確認兩個信賴憑證者信任都存在;一個用於 Microsoft Cloud Deutschland，另一個適用于 Office 365 全域服務。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="7f4cd-137">使用 [下列步驟](#backup)備份您的信任。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="7f4cd-138">使用名稱 **FFAndWorldwide** 進行儲存。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="7f4cd-139">完成您的後端遷移，並確認 AD FS 在遷移過程中仍可運作。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="7f4cd-140"> (WID 資料庫) 的 AD FS 災難修復</span><span class="sxs-lookup"><span data-stu-id="7f4cd-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="7f4cd-141">若要在嚴重損壞的 [ad](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) fs 伺服器陣列中還原 ad fs 伺服器陣列，您必須加以利用。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="7f4cd-142">因此，必須先下載工具，並在開始進行遷移之前，必須先建立備份，並安全地儲存備份。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="7f4cd-143">在此範例中 (TAT 環境) 已執行下列命令以備份伺服器陣列：</span><span class="sxs-lookup"><span data-stu-id="7f4cd-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="7f4cd-144">備份 AD FS 伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="7f4cd-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="7f4cd-145">在主要 AD FS 伺服器上安裝 AD FS 快速還原工具。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="7f4cd-146">使用此命令，匯入 PowerShell 會話中的模組。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="7f4cd-147">執行備份命令：</span><span class="sxs-lookup"><span data-stu-id="7f4cd-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="7f4cd-148">將備份安全地儲存在所需的目的地。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="7f4cd-149">還原 AD FS 伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="7f4cd-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="7f4cd-150">如果您的伺服器陣列完全失敗，且無法返回舊的伺服器陣列，請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="7f4cd-151">將先前產生及儲存的備份移至新的主要 AD FS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="7f4cd-152">執行下列 `Restore-ADFS` PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="7f4cd-153">如有必要，請預先匯入 AD FS SSL 憑證。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="7f4cd-154">將新的 DNS 記錄或負載平衡器指向新的 AD FS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="7f4cd-155">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7f4cd-155">More information</span></span>

<span data-ttu-id="7f4cd-156">開始：</span><span class="sxs-lookup"><span data-stu-id="7f4cd-156">Getting started:</span></span>

- [<span data-ttu-id="7f4cd-157">從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務</span><span class="sxs-lookup"><span data-stu-id="7f4cd-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="7f4cd-158">Microsoft Cloud Deutschland 移轉協助</span><span class="sxs-lookup"><span data-stu-id="7f4cd-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="7f4cd-159">如何選擇加入移轉</span><span class="sxs-lookup"><span data-stu-id="7f4cd-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="7f4cd-160">遷移期間的客戶體驗</span><span class="sxs-lookup"><span data-stu-id="7f4cd-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="7f4cd-161">在轉換中移動：</span><span class="sxs-lookup"><span data-stu-id="7f4cd-161">Moving through the transition:</span></span>

- [<span data-ttu-id="7f4cd-162">移轉階段的動作與影響</span><span class="sxs-lookup"><span data-stu-id="7f4cd-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="7f4cd-163">其他預備工作</span><span class="sxs-lookup"><span data-stu-id="7f4cd-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="7f4cd-164">[AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="7f4cd-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="7f4cd-165">雲端應用程式：</span><span class="sxs-lookup"><span data-stu-id="7f4cd-165">Cloud apps:</span></span>

- [<span data-ttu-id="7f4cd-166">Dynamics 365 的移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="7f4cd-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="7f4cd-167">Power BI 移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="7f4cd-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="7f4cd-168">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f4cd-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
