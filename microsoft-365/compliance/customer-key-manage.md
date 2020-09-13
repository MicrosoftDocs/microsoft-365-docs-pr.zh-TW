---
title: 管理客戶金鑰
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 在您設定客戶金鑰之後，請瞭解如何透過還原 AKV 機碼來管理它，以及管理許可權和您的資料加密原則。
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547083"
---
# <a name="manage-customer-key"></a><span data-ttu-id="aa0f7-103">管理客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="aa0f7-103">Manage Customer Key</span></span>

<span data-ttu-id="aa0f7-104">在您設定 Office 365 的客戶金鑰之後，您可以依照本文所述管理您的金鑰。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="aa0f7-105">深入瞭解相關主題中的客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="aa0f7-106">還原 Azure 金鑰保存庫金鑰</span><span class="sxs-lookup"><span data-stu-id="aa0f7-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="aa0f7-107">執行還原之前，請使用 soft delete 所提供的復原功能。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="aa0f7-108">所有與客戶金鑰搭配使用的金鑰，都必須啟用 [虛刪除]。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="aa0f7-109">虛刪除的運作方式像是回收站，可在不需要還原的情況下，最多可恢復90天。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="aa0f7-110">只需要在極大或不尋常的情況下進行還原，例如，金鑰或金鑰 vault 遺失。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="aa0f7-111">如果您必須還原金鑰以與客戶金鑰搭配使用，請在 Azure PowerShell 中執行 AzureKeyVaultKey Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="aa0f7-112">例如：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="aa0f7-113">若機碼 vault 已包含具有相同名稱的金鑰，還原作業就會失敗。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="aa0f7-114">Restore-AzKeyVaultKey 會還原機碼的所有重要版本及所有中繼資料（包括金鑰名稱）。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="aa0f7-115">管理主要 vault 許可權</span><span class="sxs-lookup"><span data-stu-id="aa0f7-115">Manage key vault permissions</span></span>

<span data-ttu-id="aa0f7-116">有幾個 Cmdlet 可用，可讓您查看並視需要移除重要 vault 的許可權（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="aa0f7-117">您可能需要移除許可權，例如，當員工離開團隊時。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="aa0f7-118">針對上述每項工作，您將使用 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="aa0f7-119">如需 Azure Powershell 的相關資訊，請參閱 [Azure PowerShell 的概述](https://docs.microsoft.com/powershell/azure/)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="aa0f7-120">若要查看主要 vault 許可權，請執行 AzKeyVault Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="aa0f7-121">例如：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="aa0f7-122">若要移除系統管理員的許可權，請執行 AzKeyVaultAccessPolicy Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="aa0f7-123">例如：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="aa0f7-124">使用客戶金鑰 (DEPs) 管理資料加密原則</span><span class="sxs-lookup"><span data-stu-id="aa0f7-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="aa0f7-125">客戶金鑰處理不同服務間的 DEPs 有所不同。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="aa0f7-126">例如，您可以為不同的服務建立不同數目的 DEPs。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="aa0f7-127">**Exchange Online 和商務用 Skype：** 您最多可以建立 50 DEPs。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="aa0f7-128">如需相關指示，請參閱 [Create a data encryption policy (DEP) 以搭配 Exchange Online 和商務用 Skype 使用](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="aa0f7-129">**SharePoint 線上、商務 OneDrive 及小組檔案：** DEP 適用于一個地理位置（也稱為 _地理_位置）中的資料。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="aa0f7-130">如果您使用 Office 365 的多地理位置功能，您可以為每個地理位置建立一個 DEP。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="aa0f7-131">如果您不是使用多地理位置，您可以建立一個 DEP。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="aa0f7-132">一般來說，當您設定客戶金鑰時，您會建立 DEP。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="aa0f7-133">如需相關指示，請參閱為 [商務地區的每一個 SharePoint 線上及 OneDrive 建立資料加密原則 (DEP) ](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="aa0f7-134">查看您為 Exchange Online 和商務用 Skype 建立的 DEPs</span><span class="sxs-lookup"><span data-stu-id="aa0f7-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="aa0f7-135">若要查看您使用 Get-DataEncryptionPolicy PowerShell Cmdlet 為 Exchange Online 和商務用 Skype 建立的所有 DEPs 清單，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="aa0f7-136">使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="aa0f7-137">若要傳回組織中的所有 DEPs，請執行不含任何參數的 Get-DataEncryptionPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="aa0f7-138">如需 Get-DataEncryptionPolicy Cmdlet 的詳細資訊，請參閱 [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="aa0f7-139">將信箱遷移至雲端之前，請先指派 DEP</span><span class="sxs-lookup"><span data-stu-id="aa0f7-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="aa0f7-140">當您指派 DEP 時，Microsoft 365 會在遷移期間使用指派的 DEP 來加密信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="aa0f7-141">這種處理常式比遷移信箱、指派 DEP，然後等候進行加密更有效率，可能需要數小時或數天。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="aa0f7-142">若要在將 DEP 遷移至 Office 365 之前將其指派給該信箱，請在 Exchange Online 中執行 Set-MailUser Cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aa0f7-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="aa0f7-143">使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="aa0f7-144">執行 Set-MailUser Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="aa0f7-145">其中 *GeneralMailboxOrMailUserIdParameter* 指定信箱，且 *DataEncryptionPolicyIdParameter* 是 DEP 的識別碼。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="aa0f7-146">如需 Set-MailUser Cmdlet 的詳細資訊，請參閱 [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="aa0f7-147">決定指派給信箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="aa0f7-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="aa0f7-148">若要判斷指派給信箱的 DEP，請使用 Get-MailboxStatistics Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="aa0f7-149">Cmdlet 會傳回唯一識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="aa0f7-150">使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="aa0f7-151">其中 *GeneralMailboxOrMailUserIdParameter* 指定信箱和 DataEncryptionPolicyID 會傳回 DEP 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="aa0f7-152">如需 Get-MailboxStatistics Cmdlet 的詳細資訊，請參閱 [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="aa0f7-153">執行 Get-DataEncryptionPolicy Cmdlet，以找出信箱所指派的 DEP 好記名稱。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="aa0f7-154">其中， *guid* 是上一個步驟中 Get-MailboxStatistics Cmdlet 所傳回的 guid。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="aa0f7-155">確認客戶金鑰已完成加密</span><span class="sxs-lookup"><span data-stu-id="aa0f7-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="aa0f7-156">不論您是否已滾出客戶金鑰、指派新的 DEP 或遷移的信箱，請使用本節中的步驟，以確保加密完成。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="aa0f7-157">驗證 Exchange Online 和商務用 Skype 的加密是否已完成</span><span class="sxs-lookup"><span data-stu-id="aa0f7-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="aa0f7-158">加密信箱可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="aa0f7-159">建議您先等候72小時，再嘗試在變更 DEP 後，或第一次將 DEP 指派給信箱之後，再嘗試驗證加密。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="aa0f7-160">使用 Get-MailboxStatistics Cmdlet 來判斷信箱是否已加密。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="aa0f7-161">如果信箱已加密，IsEncrypted 屬性會傳回 **true** 值，如果信箱未加密，則傳回 **false** 的值。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="aa0f7-162">完成信箱移動的時間取決於信箱的大小。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="aa0f7-163">若在您指派新的 DEP 後，客戶機碼尚未從72小時內完全加密，請與 Microsoft 支援部門聯繫以尋求協助。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="aa0f7-164">無法再使用 New-MoveRequest Cmdlet 進行本機信箱移動。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="aa0f7-165">如需詳細資訊，請參閱本次 [宣告](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="aa0f7-166">驗證 SharePoint 線上、商務 OneDrive 及小組檔案的加密是否已完成</span><span class="sxs-lookup"><span data-stu-id="aa0f7-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="aa0f7-167">執行 SPODataEncryptionPolicy 指令程式，以檢查加密的狀態，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="aa0f7-168">此 Cmdlet 的輸出包含：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="aa0f7-169">Primary key 的 URI。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-169">The URI of the primary key.</span></span>

- <span data-ttu-id="aa0f7-170">輔助機碼的 URI。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="aa0f7-171">地理位置的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-171">The encryption status for the geo.</span></span> <span data-ttu-id="aa0f7-172">可能的狀態包括：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-172">Possible states include:</span></span>

  - <span data-ttu-id="aa0f7-173">取消**註冊：** 尚未套用客戶金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="aa0f7-174">**註冊：** 已套用客戶金鑰加密，且您的檔案正處於加密過程中。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="aa0f7-175">如果地理位置註冊，您也會顯示地理位置的網站百分比已完成的資訊，讓您可以監視加密進度。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="aa0f7-176">**註冊：** 已套用客戶金鑰加密，且所有網站中的所有檔案都已加密。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="aa0f7-177">**滾動：** 正在進行金鑰擲入。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="aa0f7-178">如果地理位置的機碼正在進行滾動，您也會在網站的多少百分比上顯示完成金鑰滾動作業的資訊，讓您能夠監控進度。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="aa0f7-179">從信箱取消指派 DEP</span><span class="sxs-lookup"><span data-stu-id="aa0f7-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="aa0f7-180">您可以使用 [設定信箱] PowerShell Cmdlet 從信箱取消指派 DEP，並將設定 `DataEncryptionPolicy` 為 `$NULL` 。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="aa0f7-181">執行此 Cmdlet unassigns 目前指派的 DEP，並使用與預設 Microsoft 管理金鑰相關聯的 DEP 來 reencrypts 信箱。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="aa0f7-182">您無法取消指派 Microsoft managed 機碼所用的 DEP。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="aa0f7-183">如果您不想使用 Microsoft 受管理的金鑰，您可以將另一個 DEP 指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="aa0f7-184">若要使用 Set-Mailbox PowerShell Cmdlet 從信箱中取消指派 DEP，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="aa0f7-185">使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="aa0f7-186">執行 Set-Mailbox Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="aa0f7-187">撤銷您的金鑰，並啟動資料清除路徑處理常式</span><span class="sxs-lookup"><span data-stu-id="aa0f7-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="aa0f7-188">您可以控制所有根機碼（包括可用性機碼）的吊銷。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="aa0f7-189">客戶金鑰可讓您控制法規需求對您的結束規劃方面。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="aa0f7-190">如果您決定撤銷您的金鑰以清除您的資料並退出服務，服務會在資料清除程式完成之後刪除可用性金鑰。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="aa0f7-191">Microsoft 365 會審核和驗證資料清除路徑。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="aa0f7-192">如需詳細資訊，請參閱 [服務信任入口網站](https://servicetrust.microsoft.com/)上可用的 SSAE 18 SOC 2 報告。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="aa0f7-193">此外，Microsoft 建議下列檔：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="aa0f7-194">Microsoft Cloud 中金融機構的風險評估與規範指南</span><span class="sxs-lookup"><span data-stu-id="aa0f7-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="aa0f7-195">O365 退出規劃考慮</span><span class="sxs-lookup"><span data-stu-id="aa0f7-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="aa0f7-196">不同的服務之間的資料清除路徑稍有不同。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="aa0f7-197">吊銷您的客戶金鑰和 Exchange Online 和商務用 Skype 的可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="aa0f7-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="aa0f7-198">當您啟動 Exchange Online 和商務用 Skype 的資料清除路徑時，您會在 DEP 上設定永久的資料清除要求。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="aa0f7-199">這樣做會永久刪除此 DEP 所指派的信箱中的加密資料。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="aa0f7-200">因為您一次只能對一個 DEP 執行 PowerShell Cmdlet，請考慮在您啟動資料清除路徑之前，先將單一 DEP 重新指派給所有信箱。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="aa0f7-201">請勿使用資料清除路徑來刪除信箱的子集。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="aa0f7-202">此程式僅適用于即將退出服務的客戶。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="aa0f7-203">若要啟動資料清除路徑，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="aa0f7-204">從 Azure Key 保存庫移除 "O365 Exchange Online" 的自動換行及解出許可權。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="aa0f7-205">使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="aa0f7-206">針對包含您要刪除之信箱的每個 DEP，執行 [DataEncryptionPolicy 指令程式](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="aa0f7-207">若命令失敗，請確定您已從 Azure Key Vault 的兩個金鑰中移除 Exchange Online 許可權（如本工作先前所指定）。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="aa0f7-208">當您使用 DataEncryptionPolicy 指令程式設定 PermanentDataPurgeRequested 參數之後，就無法再將此 DEP 指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="aa0f7-209">請與 Microsoft 支援人員聯繫並要求資料清除 eDocument。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="aa0f7-210">在您提出要求時，Microsoft 會傳送您的法律檔，以確認和授權資料刪除。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="aa0f7-211">在上架中，以 FastTrack 提供的核准者簽署的組織中的人員必須簽署此檔。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="aa0f7-212">一般來說，這是公司中執行法律授權的人員或其他指定人員，可代表您的組織簽署書面。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="aa0f7-213">當您的代理人簽署法律檔時，通常會透過 eDoc 簽章) 將其退回 Microsoft (。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="aa0f7-214">Microsoft 收到法律檔之後，Microsoft 會執行 Cmdlet 以觸發資料清除，這會先刪除原則，並將信箱標記為永久刪除，然後刪除可用性金鑰。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="aa0f7-215">資料清除程式完成後，就無法存取 Exchange Online 中的資料，且無法復原。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="aa0f7-216">吊銷客戶金鑰和 SharePoint 線上、商務 OneDrive 與小組檔案的可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="aa0f7-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="aa0f7-217">若要為 SharePoint 線上、商務用 OneDrive 或小組檔案啟動資料清除路徑，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="aa0f7-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="aa0f7-218">撤銷 Azure 金鑰 Vault 存取權。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="aa0f7-219">所有的主要 vault 管理員都必須同意撤銷存取權。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="aa0f7-220">您不會在 SharePoint Online 中刪除 Azure 金鑰 Vault。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="aa0f7-221">主要保險共用可以在數個 SharePoint 線上承租人和 DEPs 之間共用。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="aa0f7-222">請與 Microsoft 聯繫以刪除可用性金鑰。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="aa0f7-223">當您與 Microsoft 聯繫以刪除可用性金鑰時，我們會傳送您的法律檔。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="aa0f7-224">在上架中，以 FastTrack 提供的核准者簽署的組織中的人員必須簽署此檔。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="aa0f7-225">一般來說，這是貴公司中的主管人員或其他指定人員，其法律上會有法律授權，代表您的組織簽署書面工作。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="aa0f7-226">當您的代理人簽署法律檔之後，通常會透過 eDoc 的簽章) ，將其退回 Microsoft (。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="aa0f7-227">一旦 Microsoft 收到法律檔，我們便會執行 Cmdlet，以觸發資料清除，該資料清除會執行租使用者金鑰、網站金鑰和所有個別檔金鑰的加密刪除，irrevocably 打破主要階層。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="aa0f7-228">資料清除指令程式完成後，您的資料已清除。</span><span class="sxs-lookup"><span data-stu-id="aa0f7-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="aa0f7-229">相關文章</span><span class="sxs-lookup"><span data-stu-id="aa0f7-229">Related articles</span></span>

- [<span data-ttu-id="aa0f7-230">使用客戶金鑰的服務加密</span><span class="sxs-lookup"><span data-stu-id="aa0f7-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="aa0f7-231">深入瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="aa0f7-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="aa0f7-232">設定客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="aa0f7-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="aa0f7-233">滾動或旋轉客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="aa0f7-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="aa0f7-234">客戶加密箱</span><span class="sxs-lookup"><span data-stu-id="aa0f7-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="aa0f7-235">服務加密</span><span class="sxs-lookup"><span data-stu-id="aa0f7-235">Service Encryption</span></span>](office-365-service-encryption.md)
