---
title: 管理客戶金鑰
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
description: 在您設定客戶金鑰之後，請瞭解如何透過還原 AKV 機碼來管理它，以及管理許可權，以及建立和指派資料加密原則。
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345055"
---
# <a name="manage-customer-key"></a><span data-ttu-id="33e1b-103">管理客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="33e1b-103">Manage Customer Key</span></span>

<span data-ttu-id="33e1b-104">在您設定 Office 365 的客戶金鑰之後，您必須建立並指派一或多個資料加密原則 (DEP) 。</span><span class="sxs-lookup"><span data-stu-id="33e1b-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="33e1b-105">一旦您指派 DEPs，您就可以像本文所述的方式來管理您的金鑰。</span><span class="sxs-lookup"><span data-stu-id="33e1b-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="33e1b-106">深入瞭解相關主題中的客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="33e1b-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="33e1b-107">建立 DEP 以搭配所有租使用者的多個工作負載使用</span><span class="sxs-lookup"><span data-stu-id="33e1b-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="33e1b-108">開始之前，請先確定您已完成設定客戶所需的工作。</span><span class="sxs-lookup"><span data-stu-id="33e1b-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="33e1b-109">如需詳細資訊，請參閱 [設定客戶金鑰](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="33e1b-110">若要建立 DEP，您需要在安裝過程中取得的主要 Vault URIs。</span><span class="sxs-lookup"><span data-stu-id="33e1b-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="33e1b-111">如需詳細資訊，請參閱 [取得每個 Azure Key Vault 機碼的 URI](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="33e1b-112">若要建立多工作負載 DEP，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="33e1b-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="33e1b-113">在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="33e1b-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="33e1b-114">若要建立 DEP，請使用 New-M365DataAtRestEncryptionPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="33e1b-115">其中：</span><span class="sxs-lookup"><span data-stu-id="33e1b-115">Where:</span></span>

   - <span data-ttu-id="33e1b-116">*PolicyName* 是您要用於原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="33e1b-117">名稱不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="33e1b-117">Names can't contain spaces.</span></span> <span data-ttu-id="33e1b-118">例如，Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="33e1b-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="33e1b-119">*KeyVaultURI1* 是原則中第一個索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="33e1b-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="33e1b-120">例如，<https://contosoWestUSvault1.vault.azure.net/keys/Key_01>。</span><span class="sxs-lookup"><span data-stu-id="33e1b-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="33e1b-121">*KeyVaultURI2* 是原則中的第二個索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="33e1b-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="33e1b-122">例如，<https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>。</span><span class="sxs-lookup"><span data-stu-id="33e1b-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="33e1b-123">以逗號和空格分隔兩個 URIs。</span><span class="sxs-lookup"><span data-stu-id="33e1b-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="33e1b-124">*原則描述* 是可協助您記起原則之原則的方便使用描述。</span><span class="sxs-lookup"><span data-stu-id="33e1b-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="33e1b-125">您可以在描述中包含空格。</span><span class="sxs-lookup"><span data-stu-id="33e1b-125">You can include spaces in the description.</span></span> <span data-ttu-id="33e1b-126">例如，「承租人中所有使用者的多個工作負載的根原則」。</span><span class="sxs-lookup"><span data-stu-id="33e1b-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="33e1b-127">範例：</span><span class="sxs-lookup"><span data-stu-id="33e1b-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="33e1b-128">指派多工作負載原則</span><span class="sxs-lookup"><span data-stu-id="33e1b-128">Assign multi-workload policy</span></span>

<span data-ttu-id="33e1b-129">使用 Set-M365DataAtRestEncryptionPolicyAssignment Cmdlet 指派 DEP。</span><span class="sxs-lookup"><span data-stu-id="33e1b-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="33e1b-130">一旦您指派原則之後，Microsoft 365 會以 DEP 中識別的金鑰來加密資料。</span><span class="sxs-lookup"><span data-stu-id="33e1b-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="33e1b-131">其中 *PolicyName* 是原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="33e1b-132">例如，Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="33e1b-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="33e1b-133">範例：</span><span class="sxs-lookup"><span data-stu-id="33e1b-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="33e1b-134">建立與 Exchange Online 信箱搭配使用的 DEP</span><span class="sxs-lookup"><span data-stu-id="33e1b-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="33e1b-135">開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。</span><span class="sxs-lookup"><span data-stu-id="33e1b-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="33e1b-136">如需詳細資訊，請參閱 [設定客戶金鑰](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="33e1b-137">使用 Windows PowerShell 以遠端方式連線至 Exchange Online，即可完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="33e1b-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="33e1b-138">DEP 與儲存在 Azure Key Vault 中的一組機碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="33e1b-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="33e1b-139">您為 Microsoft 365 中的信箱指派 DEP。</span><span class="sxs-lookup"><span data-stu-id="33e1b-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="33e1b-140">Microsoft 365 會使用原則中識別的金鑰來加密信箱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="33e1b-141">若要建立 DEP，您需要在安裝過程中取得的主要 Vault URIs。</span><span class="sxs-lookup"><span data-stu-id="33e1b-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="33e1b-142">如需詳細資訊，請參閱 [取得每個 Azure Key Vault 機碼的 URI](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="33e1b-143">記得！</span><span class="sxs-lookup"><span data-stu-id="33e1b-143">Remember!</span></span> <span data-ttu-id="33e1b-144">當您建立 DEP 時，您會在兩個不同的 Azure Key 保存庫中指定兩個金鑰。</span><span class="sxs-lookup"><span data-stu-id="33e1b-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="33e1b-145">在兩個不同的 Azure 區域中建立這些機碼，以確保異地冗余。</span><span class="sxs-lookup"><span data-stu-id="33e1b-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="33e1b-146">若要建立與信箱搭配使用的 DEP，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="33e1b-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="33e1b-147">在您的本機電腦上，使用組織內具有全域管理員或 Exchange Online 系統管理員許可權的工作或學校帳戶，在 Windows PowerShell 視窗中連線[至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="33e1b-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="33e1b-148">若要建立 DEP，請輸入下列命令，以使用 New-DataEncryptionPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="33e1b-149">其中：</span><span class="sxs-lookup"><span data-stu-id="33e1b-149">Where:</span></span>

   - <span data-ttu-id="33e1b-150">*PolicyName* 是您要用於原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="33e1b-151">名稱不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="33e1b-151">Names can't contain spaces.</span></span> <span data-ttu-id="33e1b-152">例如，USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="33e1b-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="33e1b-153">*原則描述* 是可協助您記起原則之原則的方便使用描述。</span><span class="sxs-lookup"><span data-stu-id="33e1b-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="33e1b-154">您可以在描述中包含空格。</span><span class="sxs-lookup"><span data-stu-id="33e1b-154">You can include spaces in the description.</span></span> <span data-ttu-id="33e1b-155">例如，「美國信箱的根鍵和其區域」。</span><span class="sxs-lookup"><span data-stu-id="33e1b-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="33e1b-156">*KeyVaultURI1* 是原則中第一個索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="33e1b-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="33e1b-157">例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。</span><span class="sxs-lookup"><span data-stu-id="33e1b-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="33e1b-158">*KeyVaultURI2* 是原則中的第二個索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="33e1b-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="33e1b-159">例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。</span><span class="sxs-lookup"><span data-stu-id="33e1b-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="33e1b-160">以逗號和空格分隔兩個 URIs。</span><span class="sxs-lookup"><span data-stu-id="33e1b-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="33e1b-161">範例：</span><span class="sxs-lookup"><span data-stu-id="33e1b-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="33e1b-162">如需詳細的語法及參數資訊，請參閱 [DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="33e1b-163">將 DEP 指派給信箱</span><span class="sxs-lookup"><span data-stu-id="33e1b-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="33e1b-164">使用 Set-Mailbox Cmdlet 將 DEP 指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="33e1b-165">一旦您指派原則之後，Microsoft 365 便可使用 DEP 中所識別的金鑰來加密信箱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="33e1b-166">其中 *MailboxIdParameter* 指定使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="33e1b-167">如需 Set-Mailbox Cmdlet 的詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="33e1b-168">在混合式環境中，您可以將 DEP 指派給已同步處理至 Exchange Online 租使用者的內部部署信箱資料。</span><span class="sxs-lookup"><span data-stu-id="33e1b-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="33e1b-169">若要將 DEP 指派給此同步處理的信箱資料，您將使用 Set-MailUser Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="33e1b-170">如需混合式環境中信箱資料的詳細資訊，請參閱[使用 Outlook iOS 和 Android 搭配混合式新式驗證的內部部署信箱](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="33e1b-171">其中 *MailUserIdParameter* 指定郵件使用者 (也稱為啟用郵件功能的使用者) 。</span><span class="sxs-lookup"><span data-stu-id="33e1b-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="33e1b-172">如需 Set-MailUser Cmdlet 的詳細資訊，請參閱 [Set-MailUser](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="33e1b-173">建立與 SharePoint 線上、商務用 OneDrive 及 Teams 檔案搭配使用的 DEP</span><span class="sxs-lookup"><span data-stu-id="33e1b-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="33e1b-174">開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。</span><span class="sxs-lookup"><span data-stu-id="33e1b-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="33e1b-175">如需詳細資訊，請參閱 [設定客戶金鑰](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="33e1b-176">若要設定 SharePoint 線上、商務用 OneDrive 和 Teams 檔案的客戶機碼，請透過遠端連線至 SharePoint 線上使用 Windows PowerShell，以完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="33e1b-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="33e1b-177">您可以將 DEP 與儲存在 Azure Key Vault 中的一組機碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="33e1b-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="33e1b-178">您將 DEP 套用到一個地理位置（也稱為地理位置）上的所有資料。</span><span class="sxs-lookup"><span data-stu-id="33e1b-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="33e1b-179">如果您使用 Office 365 的多地理位置功能，您可以為每個地理位置建立一個 DEP，使每個地理位置使用不同的金鑰。</span><span class="sxs-lookup"><span data-stu-id="33e1b-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="33e1b-180">如果您不是使用多地理位置，您可以在組織中建立一個 DEP，以用於 SharePoint 線上、商務用 OneDrive 及 Teams 檔案。</span><span class="sxs-lookup"><span data-stu-id="33e1b-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="33e1b-181">Microsoft 365 會使用 DEP 中識別的金鑰來加密該地理中的資料。</span><span class="sxs-lookup"><span data-stu-id="33e1b-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="33e1b-182">若要建立 DEP，您需要在安裝過程中取得的主要 Vault URIs。</span><span class="sxs-lookup"><span data-stu-id="33e1b-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="33e1b-183">如需詳細資訊，請參閱 [取得每個 Azure Key Vault 機碼的 URI](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="33e1b-184">記得！</span><span class="sxs-lookup"><span data-stu-id="33e1b-184">Remember!</span></span> <span data-ttu-id="33e1b-185">當您建立 DEP 時，您會在兩個不同的 Azure Key 保存庫中指定兩個金鑰。</span><span class="sxs-lookup"><span data-stu-id="33e1b-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="33e1b-186">在兩個不同的 Azure 區域中建立這些機碼，以確保異地冗余。</span><span class="sxs-lookup"><span data-stu-id="33e1b-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="33e1b-187">若要建立 DEP，您必須使用 Windows PowerShell 遠端連線至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="33e1b-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="33e1b-188">在您的本機電腦上，使用組織中具有全域系統管理員許可權的公司或學校帳戶，[連線 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="33e1b-189">在 Microsoft Office SharePoint Online 管理命令介面中，執行 Register-SPODataEncryptionPolicy Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="33e1b-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="33e1b-190">範例：</span><span class="sxs-lookup"><span data-stu-id="33e1b-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="33e1b-191">當您註冊 DEP 時，加密會從 geo 中的資料開始。</span><span class="sxs-lookup"><span data-stu-id="33e1b-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="33e1b-192">加密可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="33e1b-192">Encryption can take some time.</span></span> <span data-ttu-id="33e1b-193">如需使用此參數的詳細資訊，請參閱 [SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="33e1b-194">查看您為 Exchange Online 信箱建立的 DEPs</span><span class="sxs-lookup"><span data-stu-id="33e1b-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="33e1b-195">若要查看您為信箱建立的所有 DEPs 清單，請使用 Get-DataEncryptionPolicy PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="33e1b-196">使用組織中具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="33e1b-197">若要傳回組織中的所有 DEPs，請執行不含任何參數的 Get-DataEncryptionPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="33e1b-198">如需 Get-DataEncryptionPolicy Cmdlet 的詳細資訊，請參閱 [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="33e1b-199">將信箱遷移至雲端之前，請先指派 DEP</span><span class="sxs-lookup"><span data-stu-id="33e1b-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="33e1b-200">當您指派 dep 時，Microsoft 365 會在遷移期間使用指派的 DEP 來加密信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="33e1b-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="33e1b-201">這種處理常式比遷移信箱、指派 DEP，然後等候進行加密更有效率，可能需要數小時或數天。</span><span class="sxs-lookup"><span data-stu-id="33e1b-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="33e1b-202">若要在將 DEP 遷移至 Office 365 之前將其指派給該信箱，請在 Exchange Online 中執行 Set-MailUser Cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="33e1b-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="33e1b-203">使用組織中具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="33e1b-204">執行 Set-MailUser Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="33e1b-205">其中 *GeneralMailboxOrMailUserIdParameter* 指定信箱，且 *DataEncryptionPolicyIdParameter* 是 DEP 的識別碼。</span><span class="sxs-lookup"><span data-stu-id="33e1b-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="33e1b-206">如需 Set-MailUser Cmdlet 的詳細資訊，請參閱 [Set-MailUser](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="33e1b-207">決定指派給信箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="33e1b-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="33e1b-208">若要判斷指派給信箱的 DEP，請使用 Get-MailboxStatistics Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="33e1b-209">Cmdlet 會傳回唯一識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="33e1b-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="33e1b-210">使用組織中具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="33e1b-211">其中 *GeneralMailboxOrMailUserIdParameter* 指定信箱和 DataEncryptionPolicyID 會傳回 DEP 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="33e1b-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="33e1b-212">如需 Get-MailboxStatistics Cmdlet 的詳細資訊，請參閱 [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="33e1b-213">執行 Get-DataEncryptionPolicy Cmdlet，以找出信箱所指派的 DEP 好記名稱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="33e1b-214">其中， *guid* 是上一個步驟中 Get-MailboxStatistics Cmdlet 所傳回的 guid。</span><span class="sxs-lookup"><span data-stu-id="33e1b-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="33e1b-215">確認客戶金鑰已完成加密</span><span class="sxs-lookup"><span data-stu-id="33e1b-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="33e1b-216">不論您是否已滾出客戶金鑰、指派新的 DEP 或遷移的信箱，請使用本節中的步驟，以確保加密完成。</span><span class="sxs-lookup"><span data-stu-id="33e1b-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="33e1b-217">驗證 Exchange Online 信箱的加密是否已完成</span><span class="sxs-lookup"><span data-stu-id="33e1b-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="33e1b-218">加密信箱可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="33e1b-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="33e1b-219">在第一次加密中，信箱也必須完全從一個資料庫移至另一個資料庫，此服務才能加密信箱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="33e1b-220">使用 Get-MailboxStatistics Cmdlet 來判斷信箱是否已加密。</span><span class="sxs-lookup"><span data-stu-id="33e1b-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="33e1b-221">如果信箱已加密，IsEncrypted 屬性會傳回 **true** 值，如果信箱未加密，則傳回 **false** 的值。</span><span class="sxs-lookup"><span data-stu-id="33e1b-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="33e1b-222">完成信箱移動的時間取決於第一次指派 DEP 的信箱數目，以及信箱的大小。</span><span class="sxs-lookup"><span data-stu-id="33e1b-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="33e1b-223">如果信箱在您指派 DEP 的時間之後，一星期內尚未加密，請與 Microsoft 聯繫。</span><span class="sxs-lookup"><span data-stu-id="33e1b-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="33e1b-224">無法再使用 New-MoveRequest Cmdlet 進行本機信箱移動。</span><span class="sxs-lookup"><span data-stu-id="33e1b-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="33e1b-225">如需詳細資訊，請參閱本次 [宣告](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 。</span><span class="sxs-lookup"><span data-stu-id="33e1b-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="33e1b-226">驗證 SharePoint 線上、商務用 OneDrive 及 Teams 檔案的加密是否已完成</span><span class="sxs-lookup"><span data-stu-id="33e1b-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="33e1b-227">執行 Get-SPODataEncryptionPolicy Cmdlet 以檢查加密的狀態，如下所示：</span><span class="sxs-lookup"><span data-stu-id="33e1b-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="33e1b-228">此 Cmdlet 的輸出包含：</span><span class="sxs-lookup"><span data-stu-id="33e1b-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="33e1b-229">Primary key 的 URI。</span><span class="sxs-lookup"><span data-stu-id="33e1b-229">The URI of the primary key.</span></span>

- <span data-ttu-id="33e1b-230">輔助機碼的 URI。</span><span class="sxs-lookup"><span data-stu-id="33e1b-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="33e1b-231">地理位置的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="33e1b-231">The encryption status for the geo.</span></span> <span data-ttu-id="33e1b-232">可能的狀態包括：</span><span class="sxs-lookup"><span data-stu-id="33e1b-232">Possible states include:</span></span>

  - <span data-ttu-id="33e1b-233">取消 **註冊：** 尚未套用客戶金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="33e1b-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="33e1b-234">**註冊：** 已套用客戶金鑰加密，且您的檔案正處於加密過程中。</span><span class="sxs-lookup"><span data-stu-id="33e1b-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="33e1b-235">如果地理位置註冊，您也會顯示地理位置的網站百分比已完成的資訊，讓您可以監視加密進度。</span><span class="sxs-lookup"><span data-stu-id="33e1b-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="33e1b-236">**註冊：** 已套用客戶金鑰加密，且所有網站中的所有檔案都已加密。</span><span class="sxs-lookup"><span data-stu-id="33e1b-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="33e1b-237">**滾動：** 正在進行金鑰擲入。</span><span class="sxs-lookup"><span data-stu-id="33e1b-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="33e1b-238">如果地理位置的機碼正在進行滾動，您也會在網站的多少百分比上顯示完成金鑰滾動作業的資訊，讓您能夠監控進度。</span><span class="sxs-lookup"><span data-stu-id="33e1b-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="33e1b-239">取得與多個工作負載搭配使用的 DEPs 詳細資料</span><span class="sxs-lookup"><span data-stu-id="33e1b-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="33e1b-240">若要取得您已建立以用於多個工作負載之所有 DEPs 的詳細資料，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="33e1b-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="33e1b-241">在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="33e1b-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="33e1b-242">若要傳回組織中所有多工作負荷 DEPs 的清單，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="33e1b-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="33e1b-243">若要傳回特定 DEP 的詳細資料，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="33e1b-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="33e1b-244">此範例會傳回名為 "Contoso_Global" 之 DEP 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="33e1b-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="33e1b-245">取得多工作負載 DEP 指派資訊</span><span class="sxs-lookup"><span data-stu-id="33e1b-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="33e1b-246">若要找出目前指派給租使用者的 DEP，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="33e1b-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="33e1b-247">在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="33e1b-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="33e1b-248">輸入此命令。</span><span class="sxs-lookup"><span data-stu-id="33e1b-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="33e1b-249">停用多工作負載 DEP</span><span class="sxs-lookup"><span data-stu-id="33e1b-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="33e1b-250">在您停用多工作負載 DEP 之前，請從您租使用者中的工作負載取消指派 DEP。</span><span class="sxs-lookup"><span data-stu-id="33e1b-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="33e1b-251">若要停用用於多個工作負載的 DEP，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="33e1b-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="33e1b-252">在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="33e1b-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="33e1b-253">執行 Set-M365DataAtRestEncryptionPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="33e1b-254">其中 *PolicyName* 是原則的名稱或唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="33e1b-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="33e1b-255">例如，Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="33e1b-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="33e1b-256">範例：</span><span class="sxs-lookup"><span data-stu-id="33e1b-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="33e1b-257">還原 Azure 金鑰保存庫金鑰</span><span class="sxs-lookup"><span data-stu-id="33e1b-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="33e1b-258">執行還原之前，請使用 soft delete 所提供的復原功能。</span><span class="sxs-lookup"><span data-stu-id="33e1b-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="33e1b-259">所有與客戶金鑰搭配使用的金鑰，都必須啟用 [虛刪除]。</span><span class="sxs-lookup"><span data-stu-id="33e1b-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="33e1b-260">虛刪除的運作方式像是回收站，可在不需要還原的情況下，最多可恢復90天。</span><span class="sxs-lookup"><span data-stu-id="33e1b-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="33e1b-261">只需要在極大或不尋常的情況下進行還原，例如，金鑰或金鑰 vault 遺失。</span><span class="sxs-lookup"><span data-stu-id="33e1b-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="33e1b-262">如果您必須還原機碼以用於客戶機碼，請在 Azure PowerShell 中執行 Restore-AzureKeyVaultKey Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="33e1b-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="33e1b-263">例如：</span><span class="sxs-lookup"><span data-stu-id="33e1b-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="33e1b-264">若機碼 vault 已包含具有相同名稱的金鑰，還原作業就會失敗。</span><span class="sxs-lookup"><span data-stu-id="33e1b-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="33e1b-265">Restore-AzKeyVaultKey 會還原機碼的所有重要版本及所有中繼資料（包括金鑰名稱）。</span><span class="sxs-lookup"><span data-stu-id="33e1b-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="33e1b-266">管理主要 vault 許可權</span><span class="sxs-lookup"><span data-stu-id="33e1b-266">Manage key vault permissions</span></span>

<span data-ttu-id="33e1b-267">有幾個 Cmdlet 可用，可讓您查看並視需要移除重要 vault 的許可權（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="33e1b-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="33e1b-268">您可能需要移除許可權，例如，當員工離開團隊時。</span><span class="sxs-lookup"><span data-stu-id="33e1b-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="33e1b-269">針對上述每項工作，您將使用 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="33e1b-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="33e1b-270">如需 Azure PowerShell 的相關資訊，請參閱[Azure PowerShell 簡介](/powershell/azure/)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="33e1b-271">若要查看主要 vault 許可權，請執行 Get-AzKeyVault Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="33e1b-272">例如：</span><span class="sxs-lookup"><span data-stu-id="33e1b-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="33e1b-273">若要移除系統管理員的許可權，請執行 Remove-AzKeyVaultAccessPolicy Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="33e1b-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="33e1b-274">例如：</span><span class="sxs-lookup"><span data-stu-id="33e1b-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="33e1b-275">從客戶金鑰回復至 Microsoft 受管理的金鑰</span><span class="sxs-lookup"><span data-stu-id="33e1b-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="33e1b-276">如果您需要回復至 Microsoft 受管理的金鑰，您可以。</span><span class="sxs-lookup"><span data-stu-id="33e1b-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="33e1b-277">當您下架時，會使用每個個別工作負載支援的預設加密來重新加密您的資料。</span><span class="sxs-lookup"><span data-stu-id="33e1b-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="33e1b-278">例如，Exchange Online 支援使用 Microsoft 管理金鑰的預設加密。</span><span class="sxs-lookup"><span data-stu-id="33e1b-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33e1b-279">脫離會與資料清除相同。</span><span class="sxs-lookup"><span data-stu-id="33e1b-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="33e1b-280">資料清除會永久加密-從 Microsoft 365 中刪除組織的資料，而脫離。</span><span class="sxs-lookup"><span data-stu-id="33e1b-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="33e1b-281">您無法執行多個工作負載原則的資料清除。</span><span class="sxs-lookup"><span data-stu-id="33e1b-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="33e1b-282">如果您決定不使用客戶金鑰指派多工作負載 DEPs，您就需要使用客戶金鑰組「下架」的要求與 Microsoft 支援聯繫。</span><span class="sxs-lookup"><span data-stu-id="33e1b-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="33e1b-283">要求支援小組將服務要求與 Microsoft 365 客戶重要小組一起歸檔。</span><span class="sxs-lookup"><span data-stu-id="33e1b-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="33e1b-284">如有任何問題，請移至 m365-ck@service.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="33e1b-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="33e1b-285">如果您不想要再使用信箱層級 DEPs 加密個別的信箱，您可以從所有信箱取消指派信箱等級 DEPs。</span><span class="sxs-lookup"><span data-stu-id="33e1b-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="33e1b-286">若要取消指派信箱 DEPs，請使用 Set-Mailbox PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="33e1b-287">使用組織中具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="33e1b-288">執行 Set-Mailbox Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33e1b-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="33e1b-289">執行此 Cmdlet unassigns 目前指派的 DEP，並使用與預設 Microsoft 管理金鑰相關聯的 DEP 來 reencrypts 信箱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="33e1b-290">您無法取消指派 Microsoft managed 機碼所用的 DEP。</span><span class="sxs-lookup"><span data-stu-id="33e1b-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="33e1b-291">如果您不想使用 Microsoft 受管理的金鑰，您可以將其他客戶金鑰 DEP 指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="33e1b-292">撤銷您的金鑰，並啟動資料清除路徑處理常式</span><span class="sxs-lookup"><span data-stu-id="33e1b-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="33e1b-293">您可以控制所有根機碼（包括可用性機碼）的吊銷。</span><span class="sxs-lookup"><span data-stu-id="33e1b-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="33e1b-294">客戶金鑰可讓您控制法規需求對您的結束規劃方面。</span><span class="sxs-lookup"><span data-stu-id="33e1b-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="33e1b-295">如果您決定撤銷您的金鑰以清除您的資料並退出服務，服務會在資料清除程式完成之後刪除可用性金鑰。</span><span class="sxs-lookup"><span data-stu-id="33e1b-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="33e1b-296">這對於指派給個別信箱的客戶機碼 DEPs 是支援的。</span><span class="sxs-lookup"><span data-stu-id="33e1b-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="33e1b-297">Microsoft 365 審核和驗證資料清除路徑。</span><span class="sxs-lookup"><span data-stu-id="33e1b-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="33e1b-298">如需詳細資訊，請參閱 [服務信任入口網站](https://servicetrust.microsoft.com/)上可用的 SSAE 18 SOC 2 報告。</span><span class="sxs-lookup"><span data-stu-id="33e1b-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="33e1b-299">此外，Microsoft 建議下列檔：</span><span class="sxs-lookup"><span data-stu-id="33e1b-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="33e1b-300">Microsoft Cloud 中金融機構的風險評估與規範指南</span><span class="sxs-lookup"><span data-stu-id="33e1b-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="33e1b-301">O365 退出規劃考慮</span><span class="sxs-lookup"><span data-stu-id="33e1b-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="33e1b-302">Microsoft 365 的客戶機碼不支援清除多工作負載 DEP。</span><span class="sxs-lookup"><span data-stu-id="33e1b-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="33e1b-303">多工作負載 DEP 是用來跨所有租使用者的多個工作負載來加密資料。</span><span class="sxs-lookup"><span data-stu-id="33e1b-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="33e1b-304">清除這類 DEP 會導致無法存取多個工作負載中的資料。</span><span class="sxs-lookup"><span data-stu-id="33e1b-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="33e1b-305">如果您決定完全退出 Microsoft 365 服務，您可以根據已記錄的程式來追蹤租使用者刪除的路徑。</span><span class="sxs-lookup"><span data-stu-id="33e1b-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="33e1b-306">請參閱 how [to delete a 租使用者 In Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="33e1b-307">撤銷您的客戶金鑰和 Exchange Online 及商務用 Skype 的可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="33e1b-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="33e1b-308">當您為 Exchange Online 和商務用 Skype 初始化資料清除路徑時，您會在 DEP 上設定永久的資料清除要求。</span><span class="sxs-lookup"><span data-stu-id="33e1b-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="33e1b-309">這樣做會永久刪除此 DEP 所指派的信箱中的加密資料。</span><span class="sxs-lookup"><span data-stu-id="33e1b-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="33e1b-310">因為您一次只能對一個 DEP 執行 PowerShell Cmdlet，請考慮在您啟動資料清除路徑之前，先將單一 DEP 重新指派給所有信箱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="33e1b-311">請勿使用資料清除路徑來刪除信箱的子集。</span><span class="sxs-lookup"><span data-stu-id="33e1b-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="33e1b-312">此程式僅適用于即將退出服務的客戶。</span><span class="sxs-lookup"><span data-stu-id="33e1b-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="33e1b-313">若要啟動資料清除路徑，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="33e1b-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="33e1b-314">從 Azure Key 保存庫中移除 "O365 Exchange Online" 的自動換行和解包許可權。</span><span class="sxs-lookup"><span data-stu-id="33e1b-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="33e1b-315">在您的組織中使用具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="33e1b-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="33e1b-316">針對包含您要刪除之信箱的每個 DEP，執行 [DataEncryptionPolicy 指令程式](/powershell/module/exchange/set-dataencryptionpolicy) ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="33e1b-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="33e1b-317">若命令失敗，請確定您已從 Azure Key Vault 的兩個金鑰中移除 Exchange Online 許可權（如本工作先前所指定）。</span><span class="sxs-lookup"><span data-stu-id="33e1b-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="33e1b-318">當您使用 Set-DataEncryptionPolicy Cmdlet 設定 PermanentDataPurgeRequested 參數之後，就無法再將此 DEP 指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="33e1b-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="33e1b-319">請與 Microsoft 支援人員聯繫並要求資料清除 eDocument。</span><span class="sxs-lookup"><span data-stu-id="33e1b-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="33e1b-320">在您提出要求時，Microsoft 會傳送您的法律檔，以確認和授權資料刪除。</span><span class="sxs-lookup"><span data-stu-id="33e1b-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="33e1b-321">在上架中，以 FastTrack 提供的核准者簽署的組織中的人員必須簽署此檔。</span><span class="sxs-lookup"><span data-stu-id="33e1b-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="33e1b-322">一般來說，這是公司中執行法律授權的人員或其他指定人員，可代表您的組織簽署書面。</span><span class="sxs-lookup"><span data-stu-id="33e1b-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="33e1b-323">當您的代理人簽署法律檔時，通常會透過 eDoc 簽章) 將其退回 Microsoft (。</span><span class="sxs-lookup"><span data-stu-id="33e1b-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="33e1b-324">Microsoft 收到法律檔之後，Microsoft 會執行 Cmdlet 以觸發資料清除，這會先刪除原則，並將信箱標記為永久刪除，然後刪除可用性金鑰。</span><span class="sxs-lookup"><span data-stu-id="33e1b-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="33e1b-325">資料清除程式完成後，就無法存取已清除的資料、無法存取 Exchange Online，且無法復原。</span><span class="sxs-lookup"><span data-stu-id="33e1b-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="33e1b-326">撤銷您的客戶金鑰和 SharePoint 線上、商務用 OneDrive 及 Teams 檔案的可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="33e1b-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="33e1b-327">若要啟動 SharePoint 線上、商務用 OneDrive 及 Teams 檔案的資料清除路徑，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="33e1b-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="33e1b-328">撤銷 Azure 金鑰 Vault 存取權。</span><span class="sxs-lookup"><span data-stu-id="33e1b-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="33e1b-329">所有的主要 vault 管理員都必須同意撤銷存取權。</span><span class="sxs-lookup"><span data-stu-id="33e1b-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="33e1b-330">您不會在 SharePoint Online 中刪除 Azure 金鑰 Vault。</span><span class="sxs-lookup"><span data-stu-id="33e1b-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="33e1b-331">主要保險共用可以在數個 SharePoint 線上承租人和 DEPs 之間共用。</span><span class="sxs-lookup"><span data-stu-id="33e1b-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="33e1b-332">請與 Microsoft 聯繫以刪除可用性金鑰。</span><span class="sxs-lookup"><span data-stu-id="33e1b-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="33e1b-333">當您與 Microsoft 聯繫以刪除可用性金鑰時，我們會傳送您的法律檔。</span><span class="sxs-lookup"><span data-stu-id="33e1b-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="33e1b-334">在上架中，以 FastTrack 提供的核准者簽署的組織中的人員必須簽署此檔。</span><span class="sxs-lookup"><span data-stu-id="33e1b-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="33e1b-335">一般來說，這是貴公司中的主管人員或其他指定人員，其法律上會有法律授權，代表您的組織簽署書面工作。</span><span class="sxs-lookup"><span data-stu-id="33e1b-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="33e1b-336">當您的代理人簽署法律檔之後，通常會透過 eDoc 的簽章) ，將其退回 Microsoft (。</span><span class="sxs-lookup"><span data-stu-id="33e1b-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="33e1b-337">一旦 Microsoft 收到法律檔，我們便會執行 Cmdlet，以觸發資料清除，該資料清除會執行租使用者金鑰、網站金鑰和所有個別檔金鑰的加密刪除，irrevocably 打破主要階層。</span><span class="sxs-lookup"><span data-stu-id="33e1b-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="33e1b-338">資料清除指令程式完成後，您的資料已清除。</span><span class="sxs-lookup"><span data-stu-id="33e1b-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="33e1b-339">相關文章</span><span class="sxs-lookup"><span data-stu-id="33e1b-339">Related articles</span></span>

- [<span data-ttu-id="33e1b-340">客戶金鑰服務加密</span><span class="sxs-lookup"><span data-stu-id="33e1b-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="33e1b-341">深入瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="33e1b-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="33e1b-342">設定客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="33e1b-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="33e1b-343">滾動或旋轉客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="33e1b-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="33e1b-344">客戶加密箱</span><span class="sxs-lookup"><span data-stu-id="33e1b-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="33e1b-345">服務加密</span><span class="sxs-lookup"><span data-stu-id="33e1b-345">Service Encryption</span></span>](office-365-service-encryption.md)