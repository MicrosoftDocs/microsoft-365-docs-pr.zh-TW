---
title: 滾動或旋轉客戶金鑰或可用性金鑰
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 瞭解如何在與客戶金鑰搭配使用的 Azure Key Vault 中，進行儲存的客戶根機碼的匯總。 服務包括 Exchange Online、商務用 Skype、SharePoint 線上、商務用 OneDrive 及 Teams 檔案。
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345115"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="76e75-104">滾動或旋轉客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="76e75-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="76e75-105">當您的安全性或規範需求規定必須擲上金鑰時，請只擲出您搭配客戶金鑰使用的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="76e75-106">此外，請勿刪除任何或與原則相關聯的機碼。</span><span class="sxs-lookup"><span data-stu-id="76e75-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="76e75-107">當您翻轉機碼時，會使用先前的金鑰來加密內容。</span><span class="sxs-lookup"><span data-stu-id="76e75-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="76e75-108">例如，當作用中的信箱經常會以先前的金鑰加密，而非使用中的信箱或已停用的信箱仍會進行加密。</span><span class="sxs-lookup"><span data-stu-id="76e75-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="76e75-109">SharePoint線上會執行內容的備份，以進行還原及復原，所以可能仍然有已封存的內容使用舊的金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="76e75-110">關於滾動可用性機碼</span><span class="sxs-lookup"><span data-stu-id="76e75-110">About rolling the availability key</span></span>

<span data-ttu-id="76e75-111">Microsoft 不會公開對客戶可用性機碼的直接控制權。</span><span class="sxs-lookup"><span data-stu-id="76e75-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="76e75-112">例如，您只能 (旋轉) 您在 Azure Key Vault 中擁有的金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="76e75-113">Microsoft 365 會以內部定義的排程來擲出可用性機碼。</span><span class="sxs-lookup"><span data-stu-id="76e75-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="76e75-114">這些金鑰擲出的服務層級協定 (SLA) 不具用戶端。</span><span class="sxs-lookup"><span data-stu-id="76e75-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="76e75-115">Microsoft 365 在自動化的非手動程式中使用 Microsoft 365 服務程式代碼來旋轉可用性金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="76e75-116">Microsoft 系統管理員可能會開機磁碟區流程。</span><span class="sxs-lookup"><span data-stu-id="76e75-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="76e75-117">該鍵是使用自動化機制來擲下，不需直接存取機碼存放區。</span><span class="sxs-lookup"><span data-stu-id="76e75-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="76e75-118">未將存取可用性金鑰機密存放區提供給 Microsoft 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="76e75-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="76e75-119">可用性金鑰滾動利用與最初產生機碼時所用的相同機制。</span><span class="sxs-lookup"><span data-stu-id="76e75-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="76e75-120">如需可用性機碼的相關資訊，請參閱 [瞭解可用性金鑰](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="76e75-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76e75-121">建立新的 dep 時，客戶可以有效地展開 Exchange Online 和商務用 Skype 可用性機碼，因為為您建立的每個 DEP 產生唯一的可用性金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="76e75-122">SharePoint 線上、商務用 OneDrive 和 Teams 檔案的可用性機碼都存在於樹系層級，而且會在 DEPs 和客戶之間共用，這表示只會在 Microsoft 內部定義的排程上進行滾動。</span><span class="sxs-lookup"><span data-stu-id="76e75-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="76e75-123">若要降低每次建立新的 dep 時不會擲出可用性機碼的風險，請 SharePoint、OneDrive 及 Teams 滾租使用者中間機碼 (TIK) ，每次建立新的 dep 時，都會依客戶根金鑰和可用性機碼包裝的金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="76e75-124">針對您要進行第一次的現有根機碼要求新版本</span><span class="sxs-lookup"><span data-stu-id="76e75-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="76e75-125">當您滾機碼時，會要求新版本的現有金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="76e75-126">若要要求新版本的現有機碼，您可以使用相同的指令 [程式 AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)，其語法與您在第一個位置建立金鑰時所用的語法相同。</span><span class="sxs-lookup"><span data-stu-id="76e75-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="76e75-127">在您完成所有與資料加密原則相關聯的按鍵 (DEP) 後，您就可以執行另一個 Cmdlet，以確保客戶機碼開始使用新金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="76e75-128">在每個 Azure Key Vault (AKV) 中執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="76e75-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="76e75-129">例如：</span><span class="sxs-lookup"><span data-stu-id="76e75-129">For example:</span></span>

1. <span data-ttu-id="76e75-130">使用 Azure PowerShell 登入您的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="76e75-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="76e75-131">如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="76e75-131">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="76e75-132">如下列範例所示，執行 Add-AzKeyVaultKey Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="76e75-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="76e75-133">在此範例中，由於 **contoso-CK-** CK-NA-Na-VaultA1 vault 中已存在名為 **contoso-na-na** 的金鑰，所以 Cmdlet 會建立新版本的金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-133">In this example, since a key named **Contoso-CK-EX-NA-VaultA1-Key001** exists in the **Contoso-CK-EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="76e75-134">此作業會在金鑰的版本歷程記錄中保留舊的金鑰版本。</span><span class="sxs-lookup"><span data-stu-id="76e75-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="76e75-135">您需要舊的金鑰版本來解密仍加密的資料。</span><span class="sxs-lookup"><span data-stu-id="76e75-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="76e75-136">當您完成所有與 DEP 相關的按鍵之後，請執行額外的指令程式，以確保客戶機碼開始使用新金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="76e75-137">下列各節將更詳細地說明 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76e75-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-keys-for-multi-workload-deps"></a><span data-ttu-id="76e75-138">更新多工作負載 DEPs 的機碼</span><span class="sxs-lookup"><span data-stu-id="76e75-138">Update the keys for multi-workload DEPs</span></span>

<span data-ttu-id="76e75-139">當您滾出與多個工作負載搭配使用的 DEP 相關聯的其中一個 Azure 金鑰保存庫金鑰時，必須更新 DEP 以指向新的機碼。</span><span class="sxs-lookup"><span data-stu-id="76e75-139">When you roll either of the Azure Key Vault keys associated with a DEP used with multiple workloads, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="76e75-140">此處理程式不會旋轉可用性金鑰。</span><span class="sxs-lookup"><span data-stu-id="76e75-140">This process does not rotate the availability key.</span></span>

<span data-ttu-id="76e75-141">若要指示客戶金鑰使用新金鑰來加密多個工作負載，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="76e75-141">To instruct Customer Key to use the new key to encrypt multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="76e75-142">在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="76e75-142">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="76e75-143">執行 Set-M365DataAtRestEncryptionPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76e75-143">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

<span data-ttu-id="76e75-144">其中 *PolicyName* 是原則的名稱或唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="76e75-144">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="76e75-145">例如，Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="76e75-145">For example, Contoso_Global.</span></span>

<span data-ttu-id="76e75-146">範例：</span><span class="sxs-lookup"><span data-stu-id="76e75-146">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a><span data-ttu-id="76e75-147">更新 Exchange Online DEPs 的機碼</span><span class="sxs-lookup"><span data-stu-id="76e75-147">Update the keys for Exchange Online DEPs</span></span>

<span data-ttu-id="76e75-148">當您滾出與 Exchange Online 和商務用 Skype 使用之 DEP 相關聯的其中一個 Azure 金鑰保存庫金鑰時，必須更新 DEP 以指向新的機碼。</span><span class="sxs-lookup"><span data-stu-id="76e75-148">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="76e75-149">這不會旋轉可用性機碼。</span><span class="sxs-lookup"><span data-stu-id="76e75-149">This does not rotate the availability key.</span></span>

<span data-ttu-id="76e75-150">若要指示客戶金鑰使用新金鑰來加密信箱，請執行 Set-DataEncryptionPolicy Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="76e75-150">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="76e75-151">在 Azure PowerShell 中執行 Set-DataEncryptionPolicy Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="76e75-151">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. <span data-ttu-id="76e75-152">若要檢查信箱的 DataEncryptionPolicyID 屬性值，請使用 [決定指派給信箱的 DEP](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="76e75-152">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="76e75-153">此屬性的值會隨著服務套用更新的金鑰而變更。</span><span class="sxs-lookup"><span data-stu-id="76e75-153">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="76e75-154">更新 SharePoint 線上、商務用 OneDrive 及 Teams 檔的機碼</span><span class="sxs-lookup"><span data-stu-id="76e75-154">Update the keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="76e75-155">SharePoint[僅限線上] 可讓您一次滾一個機碼。</span><span class="sxs-lookup"><span data-stu-id="76e75-155">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="76e75-156">如果您想要在 key vault 中同時執行這兩個按鍵，請等候第一個作業完成。</span><span class="sxs-lookup"><span data-stu-id="76e75-156">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="76e75-157">Microsoft 建議您交錯作業，以避免發生此問題。</span><span class="sxs-lookup"><span data-stu-id="76e75-157">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="76e75-158">當您滾出與 SharePoint Online 和商務用 OneDrive 使用之 DEP 相關聯的其中一個 Azure 金鑰保存庫金鑰時，必須更新 DEP 以指向新的機碼。</span><span class="sxs-lookup"><span data-stu-id="76e75-158">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="76e75-159">這不會旋轉可用性機碼。</span><span class="sxs-lookup"><span data-stu-id="76e75-159">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="76e75-160">依下列方式執行 Update-SPODataEncryptionPolicy Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="76e75-160">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="76e75-161">雖然此 Cmdlet 會為線上及商務用 OneDrive 的 SharePoint 啟動金鑰執行，但動作不會立即完成。</span><span class="sxs-lookup"><span data-stu-id="76e75-161">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="76e75-162">若要查看主要卷序作業的進度，請執行 Get-SPODataEncryptionPolicy Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="76e75-162">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="76e75-163">相關文章</span><span class="sxs-lookup"><span data-stu-id="76e75-163">Related articles</span></span>

- [<span data-ttu-id="76e75-164">Office 365 的客戶機碼服務加密</span><span class="sxs-lookup"><span data-stu-id="76e75-164">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="76e75-165">設定 Office 365 客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="76e75-165">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="76e75-166">管理 Office 365 客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="76e75-166">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="76e75-167">深入瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="76e75-167">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)