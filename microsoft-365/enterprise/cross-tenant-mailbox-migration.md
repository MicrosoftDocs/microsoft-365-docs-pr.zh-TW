---
title: 跨租用戶信箱移轉
description: 如何在 Microsoft 365 或 Office 365 承租人之間移動信箱。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 1e2624fea7a93013e4b4de2dd4ede4144000f075
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073080"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="e9e69-103">跨承租人信箱遷移 (預覽) </span><span class="sxs-lookup"><span data-stu-id="e9e69-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="e9e69-104">先前，當 Exchange Online 承租人需要將信箱移至相同 Exchange Online 服務中的其他租使用者時，他們必須將其完全下架至內部部署，然後再將其上架至新的租使用者。</span><span class="sxs-lookup"><span data-stu-id="e9e69-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="e9e69-105">使用新的跨租使用者信箱遷移功能，來源和目標承租人中的租使用者管理員可以在租使用者內部部署系統中的基礎結構相依性之間移動信箱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="e9e69-106">這樣就不再需要下架和板載信箱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-106">This removes the need to offboard and onboard mailboxes.</span></span>

<span data-ttu-id="e9e69-107">通常，在合併或 divestitures 期間，您必須能夠將使用者和內容移至新的承租人。</span><span class="sxs-lookup"><span data-stu-id="e9e69-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="e9e69-108">當目標租使用者管理員執行移動時，它稱為「拉入移動」，類似于雲端上架遷移的內部部署。</span><span class="sxs-lookup"><span data-stu-id="e9e69-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="e9e69-109">租使用者 Exchange 信箱移動可由租使用者系統管理員完全自行服務，其使用的已知介面，可以編寫成將使用者轉換為新組織所需的較大型工作流程。</span><span class="sxs-lookup"><span data-stu-id="e9e69-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="e9e69-110">系統管理員可以使用「 `New-MigrationBatch` 移動信箱」管理角色提供的指令程式，以執行跨承租人移動。</span><span class="sxs-lookup"><span data-stu-id="e9e69-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="e9e69-111">移動程式會在信箱同步處理和完成期間包含租使用者授權檢查。</span><span class="sxs-lookup"><span data-stu-id="e9e69-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="e9e69-112">遷移的使用者必須在目標租使用者 Exchange Online 系統中呈現為 MailUsers，並以特定屬性標示，以啟用跨承租人的移動。</span><span class="sxs-lookup"><span data-stu-id="e9e69-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="e9e69-113">系統會針對未在目標租使用者中正確設定的使用者，移動系統會失敗。</span><span class="sxs-lookup"><span data-stu-id="e9e69-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span> 

<span data-ttu-id="e9e69-114">移動完成後，來源系統信箱會轉換成 MailUser，而且會將 Exchange) 中 ExternalEmailAddress 所顯示的 targetAddress (視為目的地租使用者的路由位址。</span><span class="sxs-lookup"><span data-stu-id="e9e69-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="e9e69-115">此程式會將 MailUser 舊版租使用者保留在來源租使用者中，並允許一段同時存在和郵件路由的情況。</span><span class="sxs-lookup"><span data-stu-id="e9e69-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="e9e69-116">當商務程式允許時，來源租使用者可能會移除來源 MailUser 或將其轉換為郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="e9e69-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="e9e69-117">只有混合或雲端中的承租人或兩者的任何組合，才支援跨承租人 Exchange 信箱遷移。</span><span class="sxs-lookup"><span data-stu-id="e9e69-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="e9e69-118">本文說明跨承租人信箱移動的程式，並提供如何準備內容移動的來源和目標承租人的指導方針。</span><span class="sxs-lookup"><span data-stu-id="e9e69-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span> 

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="e9e69-119">準備來源和目標承租人</span><span class="sxs-lookup"><span data-stu-id="e9e69-119">Preparing source and target tenants</span></span>

<span data-ttu-id="e9e69-120">跨承租人 Exchange 信箱遷移功能需要授權和範圍進行跨承租人遷移。</span><span class="sxs-lookup"><span data-stu-id="e9e69-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="e9e69-121">租使用者使用 Azure Enterprise application 和 Key Vault 儲存解決方案，現在可管理 Exchange Online 信箱從一個承租人遷移至另一個承租人的授權和範圍。</span><span class="sxs-lookup"><span data-stu-id="e9e69-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="e9e69-122">跨承租人信箱移動支援邀請與同意模型，以建立 Azure Active Directory (Azure AD) 應用程式，以供租使用者對間的驗證使用。</span><span class="sxs-lookup"><span data-stu-id="e9e69-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="e9e69-123">也需要其他元件（例如，組織關聯性和遷移端點）。</span><span class="sxs-lookup"><span data-stu-id="e9e69-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="e9e69-124">本節不包含準備目標目錄中 MailUser 使用者物件所需的特定步驟，也不會包含用於提交遷移批次的範例命令。</span><span class="sxs-lookup"><span data-stu-id="e9e69-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="e9e69-125">請參閱 [準備目標使用者物件以供遷移](#prepare-target-user-objects-for-migration) 以取得此資訊。</span><span class="sxs-lookup"><span data-stu-id="e9e69-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9e69-126">必要條件</span><span class="sxs-lookup"><span data-stu-id="e9e69-126">Prerequisites</span></span>

<span data-ttu-id="e9e69-127">跨承租人信箱移動功能需要 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) 才能建立租使用者對特定的 Azure 應用程式，以安全地儲存和存取憑證/機密，以供從一個租使用者對另一個租使用者進行驗證及授權，並移除在承租人間共用憑證/機密的任何需求。</span><span class="sxs-lookup"><span data-stu-id="e9e69-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="e9e69-128">開始之前，請確定您具備執行部署腳本所需的許可權，才能設定 Azure Key Vault、移動信箱應用程式、EXO 遷移端點，以及 EXO 組織關聯性。</span><span class="sxs-lookup"><span data-stu-id="e9e69-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="e9e69-129">通常，全域管理員具有執行所有設定步驟的許可權。</span><span class="sxs-lookup"><span data-stu-id="e9e69-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="e9e69-130">此外，在執行安裝程式之前，必須先在來源租使用者中啟用郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e9e69-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="e9e69-131">這些群組是用來限定可從來源移動的信箱清單，或有時稱為「資源) 租使用者 (目標租使用者。</span><span class="sxs-lookup"><span data-stu-id="e9e69-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="e9e69-132">這可讓來源租使用者管理員限制或限制需要移動的特定信箱集，以防非預期的使用者進行遷移。</span><span class="sxs-lookup"><span data-stu-id="e9e69-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="e9e69-133">不支援嵌套的群組。</span><span class="sxs-lookup"><span data-stu-id="e9e69-133">Nested groups are not supported.</span></span>

<span data-ttu-id="e9e69-134">您也需要與您信任的協力廠商公司 (進行通訊，以供您將信箱移動) 取得其 Microsoft 365 租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="e9e69-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="e9e69-135">在 [組織關聯] 欄位中使用此租使用者識別碼 `DomainName` 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="e9e69-136">若要取得訂閱的租使用者識別碼，請登入 Microsoft 365 系統管理中心，然後移至 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="e9e69-137">按一下 [租使用者識別碼] 屬性的複製圖示，將其複製到剪貼簿。</span><span class="sxs-lookup"><span data-stu-id="e9e69-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="e9e69-138">以下是處理常式的運作方式。</span><span class="sxs-lookup"><span data-stu-id="e9e69-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="信箱遷移的租使用者準備。":::

<span data-ttu-id="e9e69-140">[請參閱較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。</span><span class="sxs-lookup"><span data-stu-id="e9e69-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="e9e69-141">準備承租人</span><span class="sxs-lookup"><span data-stu-id="e9e69-141">Prepare tenants</span></span>

<span data-ttu-id="e9e69-142">在高層次上執行安裝程式腳本時，會進行下列設定動作。</span><span class="sxs-lookup"><span data-stu-id="e9e69-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="e9e69-143">準備目標租使用者：</span><span class="sxs-lookup"><span data-stu-id="e9e69-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="e9e69-144">若未提供現有的 Azure 資源群組，則會在 (SCRIPT) 中建立一個新的 Azure 資源群組。</span><span class="sxs-lookup"><span data-stu-id="e9e69-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="e9e69-145">若未提供現有的 Key Vault， (腳本) 中建立新的按鍵 Vault。</span><span class="sxs-lookup"><span data-stu-id="e9e69-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="e9e69-146">為 Office 365 Exchange Online 信箱遷移應用程式建立新的訪問原則 (腳本) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="e9e69-147">如果指定) 將機密保存到遷移應用程式 (腳本) ，就會建立新的憑證 (或現有憑證。</span><span class="sxs-lookup"><span data-stu-id="e9e69-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="e9e69-148"> (SCRIPT) 中建立新的 Azure AD 應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9e69-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="e9e69-149">憑證/機密會上傳至遷移應用程式 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="e9e69-150">信箱遷移許可權會指派給應用程式 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="e9e69-151">部署腳本會暫停，直到 target admin consents 至自己的應用程式 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="e9e69-152">目標承租人系統管理員 consents 指定給應用程式 (手動) 的許可權。</span><span class="sxs-lookup"><span data-stu-id="e9e69-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="e9e69-153">組織關聯建立到目標租使用者 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="e9e69-154">會建立遷移端點，將信箱拉入目標租使用者 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="e9e69-155">準備來源租使用者：</span><span class="sxs-lookup"><span data-stu-id="e9e69-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="e9e69-156">來源租使用者管理員接受來自目標租使用者 (手動) 的信箱遷移應用程式邀請。</span><span class="sxs-lookup"><span data-stu-id="e9e69-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="e9e69-157">來源租使用者系統管理員會在其承租人中建立擁有郵件功能的安全性群組，以包含允許遷移應用程式移動的信箱清單 (手動) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="e9e69-158">組織關聯性建立于目標承租人，指定信箱遷移應用程式應該用於 OAuth 驗證，以接受 (腳本) 的移動要求。</span><span class="sxs-lookup"><span data-stu-id="e9e69-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="e9e69-159">目標承租人管理員的逐步指示</span><span class="sxs-lookup"><span data-stu-id="e9e69-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="e9e69-160">從 [GitHub 存放庫](https://github.com/microsoft/cross-tenant/releases/tag/Preview)下載目標租使用者安裝程式的 SetupCrossTenantRelationshipForTargetTenant.ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="e9e69-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="e9e69-161">將腳本 ( # A0) 儲存至您要執行腳本的電腦。</span><span class="sxs-lookup"><span data-stu-id="e9e69-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="e9e69-162">建立與 Exchange Online 目標租使用者的遠端 PowerShell 連線。</span><span class="sxs-lookup"><span data-stu-id="e9e69-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="e9e69-163">此外，請務必具備執行部署腳本所需的許可權，才能設定 Azure 金鑰 Vault 儲存和憑證、移動信箱應用程式、EXO 遷移端點，以及 EXO 組織關聯性。</span><span class="sxs-lookup"><span data-stu-id="e9e69-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="e9e69-164">將檔資料夾目錄變更為腳本位置，或確認腳本目前已儲存至遠端 PowerShell 會話中的目前位置。</span><span class="sxs-lookup"><span data-stu-id="e9e69-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="e9e69-165">使用下列參數和值執行腳本。</span><span class="sxs-lookup"><span data-stu-id="e9e69-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="e9e69-166">參數</span><span class="sxs-lookup"><span data-stu-id="e9e69-166">Parameter</span></span> | <span data-ttu-id="e9e69-167">值</span><span class="sxs-lookup"><span data-stu-id="e9e69-167">Value</span></span> | <span data-ttu-id="e9e69-168">必要或選用</span><span class="sxs-lookup"><span data-stu-id="e9e69-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="e9e69-169">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="e9e69-169">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="e9e69-170">來源租使用者網域，例如 fabrikam \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="e9e69-170">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="e9e69-171">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-171">Required</span></span> |
    | <span data-ttu-id="e9e69-172">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="e9e69-172">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="e9e69-173">來源承租人管理員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e9e69-173">Source tenant admin’s email address.</span></span> <span data-ttu-id="e9e69-174">這是來源承租人系統管理員，會同意使用從目標系統管理員傳送的信箱遷移應用程式。這是將會收到該應用程式之電子郵件邀請的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="e9e69-174">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="e9e69-175">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-175">Required</span></span> |
    | <span data-ttu-id="e9e69-176">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="e9e69-176">-TargetTenantDomain</span></span>                         | <span data-ttu-id="e9e69-177">目標租使用者網域，例如 contoso \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="e9e69-177">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="e9e69-178">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-178">Required</span></span> |
    | <span data-ttu-id="e9e69-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="e9e69-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="e9e69-180">來源承租人組織識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="e9e69-181">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-181">Required</span></span> |
    | <span data-ttu-id="e9e69-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="e9e69-182">-SubscriptionId</span></span>                             | <span data-ttu-id="e9e69-183">用於建立資源的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="e9e69-184">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-184">Required</span></span> |
    | <span data-ttu-id="e9e69-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="e9e69-185">-ResourceGroup</span></span>                              | <span data-ttu-id="e9e69-186">包含或將要包含金鑰存放區之 Azure 資源組名稱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="e9e69-187">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-187">Required</span></span> |
    | <span data-ttu-id="e9e69-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="e9e69-188">-KeyVaultName</span></span>                               | <span data-ttu-id="e9e69-189">Azure Key Vault 實例，用來儲存您的信箱遷移應用程式憑證/機密。</span><span class="sxs-lookup"><span data-stu-id="e9e69-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="e9e69-190">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-190">Required</span></span> |
    | <span data-ttu-id="e9e69-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="e9e69-191">-CertificateName</span></span>                            | <span data-ttu-id="e9e69-192">在金鑰保管中產生或搜尋憑證時的憑證名稱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="e9e69-193">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-193">Required</span></span> |
    | <span data-ttu-id="e9e69-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="e9e69-194">-CertificateSubject</span></span>                         | <span data-ttu-id="e9e69-195">Azure 金鑰保存庫憑證主體名稱，例如 CN = contoso_fabrikam。</span><span class="sxs-lookup"><span data-stu-id="e9e69-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="e9e69-196">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-196">Required</span></span> |
    | <span data-ttu-id="e9e69-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="e9e69-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="e9e69-198">若已建立郵件遷移應用程式，則使用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9e69-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="e9e69-199">選用</span><span class="sxs-lookup"><span data-stu-id="e9e69-199">Optional</span></span> |
    | <span data-ttu-id="e9e69-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="e9e69-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="e9e69-201">指定給信箱遷移應用程式所需的許可權，例如 Exchange 或 Msgraph-sdk-ios-nxoauth2-adapter (Exchange 以移動信箱，Msgraph-sdk-ios-nxoauth2-adapter 用於使用此應用程式，將同意連結邀請傳送至資源租使用者) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="e9e69-202">必要</span><span class="sxs-lookup"><span data-stu-id="e9e69-202">Required</span></span> |
    | <span data-ttu-id="e9e69-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="e9e69-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="e9e69-204">使用為遷移所建立的應用程式來傳送對來源承租人系統管理員的「同意」連結邀請的參數。如果不存在，將會提示目標管理員的認證連線至 Azure 邀請管理員，並以目標系統管理員身分傳送邀請。</span><span class="sxs-lookup"><span data-stu-id="e9e69-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="e9e69-205">選用</span><span class="sxs-lookup"><span data-stu-id="e9e69-205">Optional</span></span> |
    | <span data-ttu-id="e9e69-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="e9e69-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="e9e69-207">儲存主要存放區之審核記錄的儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="e9e69-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="e9e69-208">選用</span><span class="sxs-lookup"><span data-stu-id="e9e69-208">Optional</span></span> |
    | <span data-ttu-id="e9e69-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="e9e69-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="e9e69-210">包含儲存金鑰 Vault 審核記錄的儲存帳戶的資源群組。</span><span class="sxs-lookup"><span data-stu-id="e9e69-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="e9e69-211">選用</span><span class="sxs-lookup"><span data-stu-id="e9e69-211">Optional</span></span> |
    ||||

6. <span data-ttu-id="e9e69-212">腳本會暫停，並要求您接受或同意在此程式期間建立的 Exchange 信箱遷移應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9e69-212">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="e9e69-213">範例如下。</span><span class="sxs-lookup"><span data-stu-id="e9e69-213">Here is an example.</span></span>

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ``` 

7. <span data-ttu-id="e9e69-214">會在遠端 PowerShell 會話中顯示 URL。</span><span class="sxs-lookup"><span data-stu-id="e9e69-214">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="e9e69-215">複製為您的租使用者同意所提供的連結，並將其貼到網頁瀏覽器中。</span><span class="sxs-lookup"><span data-stu-id="e9e69-215">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="e9e69-216">使用您的全域系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="e9e69-216">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="e9e69-217">當顯示下列畫面時，請選取 [ **接受** ]。</span><span class="sxs-lookup"><span data-stu-id="e9e69-217">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="[接受許可權] 對話方塊":::
    
9. <span data-ttu-id="e9e69-219">切換回遠端 PowerShell 會話，然後按 Enter 繼續。</span><span class="sxs-lookup"><span data-stu-id="e9e69-219">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="e9e69-220">腳本會設定其餘的安裝物件。</span><span class="sxs-lookup"><span data-stu-id="e9e69-220">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="e9e69-221">範例如下。</span><span class="sxs-lookup"><span data-stu-id="e9e69-221">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="e9e69-222">目標系統管理員設定現在已完成！</span><span class="sxs-lookup"><span data-stu-id="e9e69-222">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="e9e69-223">來源承租人管理員的逐步指示</span><span class="sxs-lookup"><span data-stu-id="e9e69-223">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="e9e69-224">在設定期間，以目標系統管理員所指定的-ResourceTenantAdminEmail 登入您的信箱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-224">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="e9e69-225">尋找來自目標租使用者的電子郵件邀請，然後選取 [ **快速入門** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e9e69-225">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="[您已被邀請] 對話方塊":::

2. <span data-ttu-id="e9e69-227">選取 [ **接受** ] 以接受邀請。</span><span class="sxs-lookup"><span data-stu-id="e9e69-227">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="接受許可權的對話方塊":::

   > [!NOTE]
   > <span data-ttu-id="e9e69-229">如果您未收到這封電子郵件或找不到，則目標租使用者管理員會提供直接 URL，可供您用來接受邀請。</span><span class="sxs-lookup"><span data-stu-id="e9e69-229">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="e9e69-230">URL 應在目標租使用者 admin 的遠端 PowerShell 會話的成績單中。</span><span class="sxs-lookup"><span data-stu-id="e9e69-230">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="e9e69-231">在 Microsoft 365 系統管理中心或遠端 PowerShell 會話中，建立一或多個擁有郵件功能的安全性群組，以控制目標租使用者所允許的信箱清單，以拉 (從來源租使用者) 移至目標租使用者。</span><span class="sxs-lookup"><span data-stu-id="e9e69-231">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="e9e69-232">您不需要事先填入此群組，但必須至少提供一個群組，才能執行安裝步驟 (script) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-232">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="e9e69-233">不支援嵌套群組。</span><span class="sxs-lookup"><span data-stu-id="e9e69-233">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="e9e69-234">從 GitHub [存放庫的](https://github.com/microsoft/cross-tenant/releases/tag/Preview)存放庫中，下載來源承租人安裝程式的 SetupCrossTenantRelationshipForTargetResource.ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="e9e69-234">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository [here](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="e9e69-235">使用您的 Exchange 系統管理員許可權，建立與來源承租人的遠端 PowerShell 連線。</span><span class="sxs-lookup"><span data-stu-id="e9e69-235">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="e9e69-236">若要設定來源租使用者，則不需要全域系統管理員許可權，因為 Azure 應用程式的建立程式是由目標租使用者所組成。</span><span class="sxs-lookup"><span data-stu-id="e9e69-236">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="e9e69-237">將目錄變更為腳本位置，或確認腳本目前已儲存至遠端 PowerShell 會話中的目前位置。</span><span class="sxs-lookup"><span data-stu-id="e9e69-237">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="e9e69-238">使用下列必要的參數和值，執行腳本。</span><span class="sxs-lookup"><span data-stu-id="e9e69-238">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="e9e69-239">參數</span><span class="sxs-lookup"><span data-stu-id="e9e69-239">Parameter</span></span> | <span data-ttu-id="e9e69-240">值</span><span class="sxs-lookup"><span data-stu-id="e9e69-240">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="e9e69-241">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="e9e69-241">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="e9e69-242">來源租使用者為屬於遷移範圍內之身分識別/信箱所建立的已啟用郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e9e69-242">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="e9e69-243">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="e9e69-243">-ResourceTenantDomain</span></span> | <span data-ttu-id="e9e69-244">來源租使用者功能變數名稱，例如 fabrikam \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="e9e69-244">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="e9e69-245">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="e9e69-245">-TargetTenantDomain</span></span> | <span data-ttu-id="e9e69-246">目標租使用者功能變數名稱，例如 contoso \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="e9e69-246">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="e9e69-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="e9e69-247">-ApplicationId</span></span> | <span data-ttu-id="e9e69-248">用於遷移之應用程式的 Azure 應用程式識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="e9e69-249">可透過 Azure 入口網站取得的應用程式識別碼 (Azure AD、企業應用程式、應用程式名稱、應用程式識別碼) 或包含在您的邀請電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="e9e69-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="e9e69-250">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="e9e69-250">-TargetTenantId</span></span> | <span data-ttu-id="e9e69-251">目標租使用者的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="e9e69-251">Tenant ID of the target tenant.</span></span> <span data-ttu-id="e9e69-252">例如，contoso onmicrosoft.com 租使用者的 Azure AD 租使用者識別碼 \. 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-252">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||
    
    <span data-ttu-id="e9e69-253">範例如下。</span><span class="sxs-lookup"><span data-stu-id="e9e69-253">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="e9e69-254">來源系統管理員設定現在已完成！</span><span class="sxs-lookup"><span data-stu-id="e9e69-254">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="e9e69-255">驗證安裝程式</span><span class="sxs-lookup"><span data-stu-id="e9e69-255">Verify setup</span></span>

<span data-ttu-id="e9e69-256">請確認已成功建立目標中的來源與目標承租人及遷移端點中的組織關聯性。</span><span class="sxs-lookup"><span data-stu-id="e9e69-256">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="e9e69-257">目標租使用者</span><span class="sxs-lookup"><span data-stu-id="e9e69-257">Target tenant</span></span>

<span data-ttu-id="e9e69-258">**組織關聯性**</span><span class="sxs-lookup"><span data-stu-id="e9e69-258">**Organization relationship**</span></span>

<span data-ttu-id="e9e69-259">使用此命令，確認已建立及設定組織關聯性物件。</span><span class="sxs-lookup"><span data-stu-id="e9e69-259">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="e9e69-260">範例如下：</span><span class="sxs-lookup"><span data-stu-id="e9e69-260">Here is an example:</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="e9e69-261">**遷移端點**</span><span class="sxs-lookup"><span data-stu-id="e9e69-261">**Migration endpoint**</span></span>

<span data-ttu-id="e9e69-262">使用此命令，確認已建立並設定遷移端點物件。</span><span class="sxs-lookup"><span data-stu-id="e9e69-262">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="e9e69-263">範例如下。</span><span class="sxs-lookup"><span data-stu-id="e9e69-263">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="e9e69-264">來源租使用者</span><span class="sxs-lookup"><span data-stu-id="e9e69-264">Source tenant</span></span>

<span data-ttu-id="e9e69-265">**組織關聯性**</span><span class="sxs-lookup"><span data-stu-id="e9e69-265">**Organization relationship**</span></span>

<span data-ttu-id="e9e69-266">使用此命令，確認已建立及設定組織關聯性物件。</span><span class="sxs-lookup"><span data-stu-id="e9e69-266">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
<span data-ttu-id="e9e69-267">範例如下。</span><span class="sxs-lookup"><span data-stu-id="e9e69-267">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="e9e69-268">將信箱移回原始來源</span><span class="sxs-lookup"><span data-stu-id="e9e69-268">Move mailboxes back to the original source</span></span>

<span data-ttu-id="e9e69-269">若要將信箱移回原始來源租使用者，必須在新的來源和新的目標承租人中執行相同的一組步驟和腳本。</span><span class="sxs-lookup"><span data-stu-id="e9e69-269">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="e9e69-270">將會更新或新增現有的組織關聯性物件，而不會重新建立。</span><span class="sxs-lookup"><span data-stu-id="e9e69-270">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="e9e69-271">為遷移準備目標使用者物件</span><span class="sxs-lookup"><span data-stu-id="e9e69-271">Prepare target user objects for migration</span></span>

<span data-ttu-id="e9e69-272">遷移的使用者必須存在於目標承租人和 Exchange Online 系統 (中，MailUsers) 會以特定屬性標示以啟用跨承租人的移動）。</span><span class="sxs-lookup"><span data-stu-id="e9e69-272">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="e9e69-273">系統會針對未在目標租使用者中正確設定的使用者，移動系統會失敗。</span><span class="sxs-lookup"><span data-stu-id="e9e69-273">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="e9e69-274">下列各節將詳細說明目標租使用者的 MailUser 物件需求。</span><span class="sxs-lookup"><span data-stu-id="e9e69-274">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e9e69-275">必要條件</span><span class="sxs-lookup"><span data-stu-id="e9e69-275">Prerequisites</span></span>
  
<span data-ttu-id="e9e69-276">您必須確定在目標群組織中設定下列物件和屬性。</span><span class="sxs-lookup"><span data-stu-id="e9e69-276">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="e9e69-277">對於從來源組織移動的任何信箱，您必須在目標群組織中布建 MailUser 物件：</span><span class="sxs-lookup"><span data-stu-id="e9e69-277">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 
   - <span data-ttu-id="e9e69-278">目標 MailUser 必須具有來自來源信箱的這些屬性，或是使用新的 User 物件進行指派：</span><span class="sxs-lookup"><span data-stu-id="e9e69-278">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="e9e69-279">ExchangeGUID (從源到目標) 的直接流程–信箱 GUID 必須相符。</span><span class="sxs-lookup"><span data-stu-id="e9e69-279">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="e9e69-280">若目標物件不存在，移動程式將不會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="e9e69-280">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="e9e69-281">ArchiveGUID 從來源到目標)  (直接流程–封存 GUID 必須相符。</span><span class="sxs-lookup"><span data-stu-id="e9e69-281">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="e9e69-282">若目標物件不存在，移動程式將不會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="e9e69-282">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="e9e69-283"> (只有當來源信箱啟用封存) 時，才需要此。</span><span class="sxs-lookup"><span data-stu-id="e9e69-283">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="e9e69-284">LegacyExchangeDN (流向 proxyAddress，"x500： <LegacyExchangeDN> " ) – LegacyExchangeDN 必須存在於目標 MailUser 為 x500： proxyAddress。</span><span class="sxs-lookup"><span data-stu-id="e9e69-284">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="e9e69-285">若目標物件不存在，移動程式將不會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="e9e69-285">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="e9e69-286">UserPrincipalName – UPN 會對應至使用者的新身分識別或目標公司 (例如，user@northwindtraders.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-286">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="e9e69-287">主要 SMTPAddress –主要 SMTP 位址會對應至使用者的新公司 (例如，user@northwind.com) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-287">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="e9e69-288">TargetAddress/ExternalEmailAddress – MailUser 會參考來源承租人中主控的使用者目前信箱 (例如 user@contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-288">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="e9e69-289">指派此值時，請確認您具有/也指派 PrimarySMTPAddress，否則此值會設定 PrimarySMTPAddress 會造成移動失敗。</span><span class="sxs-lookup"><span data-stu-id="e9e69-289">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="e9e69-290">您無法從來源信箱將舊版 smtp proxy 位址新增至目標 MailUser。</span><span class="sxs-lookup"><span data-stu-id="e9e69-290">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="e9e69-291">例如，您無法在 fabrikam.onmicrosoft.com 租使用者物件) 中的 MEU 上維護 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e9e69-291">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="e9e69-292">網域只與一個 Azure AD 或 Exchange Online 租使用者相關聯。</span><span class="sxs-lookup"><span data-stu-id="e9e69-292">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
    <span data-ttu-id="e9e69-293">範例 **目標** MailUser 物件：</span><span class="sxs-lookup"><span data-stu-id="e9e69-293">Example **target** MailUser object:</span></span>
 
    | <span data-ttu-id="e9e69-294">屬性</span><span class="sxs-lookup"><span data-stu-id="e9e69-294">Attribute</span></span>             | <span data-ttu-id="e9e69-295">值</span><span class="sxs-lookup"><span data-stu-id="e9e69-295">Value</span></span>                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="e9e69-296">別名</span><span class="sxs-lookup"><span data-stu-id="e9e69-296">Alias</span></span>                 | <span data-ttu-id="e9e69-297">LaraN</span><span class="sxs-lookup"><span data-stu-id="e9e69-297">LaraN</span></span>                                                                                                                    |
    | <span data-ttu-id="e9e69-298">RecipientType</span><span class="sxs-lookup"><span data-stu-id="e9e69-298">RecipientType</span></span>         | <span data-ttu-id="e9e69-299">MailUser</span><span class="sxs-lookup"><span data-stu-id="e9e69-299">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="e9e69-300">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="e9e69-300">RecipientTypeDetails</span></span>  | <span data-ttu-id="e9e69-301">MailUser</span><span class="sxs-lookup"><span data-stu-id="e9e69-301">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="e9e69-302">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="e9e69-302">UserPrincipalName</span></span>     | <span data-ttu-id="e9e69-303">LaraN@northwintraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e9e69-303">LaraN@northwintraders\.onmicrosoft.com</span></span>                                                                                    |
    | <span data-ttu-id="e9e69-304">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="e9e69-304">PrimarySmtpAddress</span></span>    | <span data-ttu-id="e9e69-305">Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="e9e69-305">Lara\.Newton@northwind.com</span></span>                                                                                                |
    | <span data-ttu-id="e9e69-306">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="e9e69-306">ExternalEmailAddress</span></span>  | <span data-ttu-id="e9e69-307">SMTP： LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e9e69-307">SMTP:LaraN@contoso\.onmicrosoft.com</span></span>                                                                                       |
    | <span data-ttu-id="e9e69-308">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="e9e69-308">ExchangeGuid</span></span>          | <span data-ttu-id="e9e69-309">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="e9e69-309">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
    | <span data-ttu-id="e9e69-310">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="e9e69-310">LegacyExchangeDN</span></span>      | <span data-ttu-id="e9e69-311">/o = First Organization/ou=Exchange 系統管理群組</span><span class="sxs-lookup"><span data-stu-id="e9e69-311">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
    |                       | <span data-ttu-id="e9e69-312"> (FYDIBOHF23SPDLT) /cn = 收件者/cn = 74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="e9e69-312">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
    | <span data-ttu-id="e9e69-313">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="e9e69-313">EmailAddresses</span></span>        | <span data-ttu-id="e9e69-314">x500：/o = First Organization/ou=Exchange 系統管理群組 (FYDIBOHF23SPDLT) /cn = 收件者/cn = d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="e9e69-314">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
    |                       | <span data-ttu-id="e9e69-315">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="e9e69-315">7273f1f9-Lara</span></span>                                                                                                            |
    |                       | <span data-ttu-id="e9e69-316">smtp： LaraN@northwindtraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e9e69-316">smtp:LaraN@northwindtraders\.onmicrosoft.com</span></span>                                                                              |
    |                       | <span data-ttu-id="e9e69-317">SMTP： Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="e9e69-317">SMTP:Lara\.Newton@northwind.com</span></span>                                                                                           |
    |||

   <span data-ttu-id="e9e69-318">**來源** 信箱物件範例：</span><span class="sxs-lookup"><span data-stu-id="e9e69-318">Example **source** Mailbox object:</span></span>

   | <span data-ttu-id="e9e69-319">屬性</span><span class="sxs-lookup"><span data-stu-id="e9e69-319">Attribute</span></span>             | <span data-ttu-id="e9e69-320">值</span><span class="sxs-lookup"><span data-stu-id="e9e69-320">Value</span></span>                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | <span data-ttu-id="e9e69-321">別名</span><span class="sxs-lookup"><span data-stu-id="e9e69-321">Alias</span></span>                 | <span data-ttu-id="e9e69-322">LaraN</span><span class="sxs-lookup"><span data-stu-id="e9e69-322">LaraN</span></span>                                                                    |
   | <span data-ttu-id="e9e69-323">RecipientType</span><span class="sxs-lookup"><span data-stu-id="e9e69-323">RecipientType</span></span>         | <span data-ttu-id="e9e69-324">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="e9e69-324">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="e9e69-325">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="e9e69-325">RecipientTypeDetails</span></span>  | <span data-ttu-id="e9e69-326">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="e9e69-326">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="e9e69-327">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="e9e69-327">UserPrincipalName</span></span>     | <span data-ttu-id="e9e69-328">LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e9e69-328">LaraN@contoso\.onmicrosoft.com</span></span>                                            |
   | <span data-ttu-id="e9e69-329">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="e9e69-329">PrimarySmtpAddress</span></span>    | <span data-ttu-id="e9e69-330">Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9e69-330">Lara\.Newton@contoso.com</span></span>                                                  |
   | <span data-ttu-id="e9e69-331">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="e9e69-331">ExchangeGuid</span></span>          | <span data-ttu-id="e9e69-332">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="e9e69-332">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
   | <span data-ttu-id="e9e69-333">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="e9e69-333">LegacyExchangeDN</span></span>      | <span data-ttu-id="e9e69-334">/o = First Organization/ou=Exchange 系統管理群組</span><span class="sxs-lookup"><span data-stu-id="e9e69-334">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
   |                       | <span data-ttu-id="e9e69-335"> (FYDIBOHF23SPDLT) /cn = 收件者/cn = d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="e9e69-335">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
   | <span data-ttu-id="e9e69-336">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="e9e69-336">EmailAddresses</span></span>        | <span data-ttu-id="e9e69-337">smtp： LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e9e69-337">smtp:LaraN@contoso\.onmicrosoft.com</span></span> 
   |                       | <span data-ttu-id="e9e69-338">SMTP： Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9e69-338">SMTP:Lara\.Newton@contoso.com</span></span>          |
   |||

   - <span data-ttu-id="e9e69-339">其他屬性可能會包含在 Exchange 混合式寫回中。</span><span class="sxs-lookup"><span data-stu-id="e9e69-339">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="e9e69-340">如果不是，則應該包含這些使用者。</span><span class="sxs-lookup"><span data-stu-id="e9e69-340">If not, they should be included.</span></span> 
   - <span data-ttu-id="e9e69-341">msExchBlockedSendersHash –從用戶端向內部部署 Active Directory 中寫入線上安全及封鎖的寄件者資料。</span><span class="sxs-lookup"><span data-stu-id="e9e69-341">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="e9e69-342">msExchSafeRecipientsHash –從用戶端向內部部署 Active Directory 中寫入線上安全及封鎖的寄件者資料。</span><span class="sxs-lookup"><span data-stu-id="e9e69-342">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="e9e69-343">msExchSafeSendersHash –從用戶端向內部部署 Active Directory 中寫入線上安全及封鎖的寄件者資料。</span><span class="sxs-lookup"><span data-stu-id="e9e69-343">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="e9e69-344">如果來源信箱位於 LitigationHold，且來源信箱可復原的專案大小大於我們的資料庫預設值 (30 GB) 中，因為目標配額小於來源信箱大小，所以移動不會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="e9e69-344">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="e9e69-345">您可以更新 target MailUser 物件，將 ELC 信箱旗標從來源環境轉換到目標，這會觸發目標系統將 MailUser 的配額擴充為 100 GB，因此可讓使用者移至目標。</span><span class="sxs-lookup"><span data-stu-id="e9e69-345">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="e9e69-346">這些指示僅適用于執行 Azure AD Connect 的混合式身分識別，因為用於加蓋 ELC 旗標的命令不會公開給租使用者系統管理員。</span><span class="sxs-lookup"><span data-stu-id="e9e69-346">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="e9e69-347">範例–無擔保</span><span class="sxs-lookup"><span data-stu-id="e9e69-347">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="e9e69-348">此腳本會假設同時連線到來源信箱 (以取得來源值) 以及目標內部部署 Active Directory (，以標記 Microsoft.rtc.management.adconnect.schema.aduser 物件) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-348">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="e9e69-349">如果來源已啟用訴訟或單一專案復原，請在目的地帳戶上加以設定。</span><span class="sxs-lookup"><span data-stu-id="e9e69-349">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="e9e69-350">這會將目的地帳戶的暫放大小增加為 100 GB。</span><span class="sxs-lookup"><span data-stu-id="e9e69-350">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. <span data-ttu-id="e9e69-351">非混合式目標租使用者可以在遷移之前，修改 MailUsers 的 [可復原的專案] 資料夾中的配額，方法是執行下列命令，以啟用 MailUser 物件的訴訟暫止，並將配額增加至 100 GB： `Set-MailUser -EnableLitigationHoldForMigration $TRUE` 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-351">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="e9e69-352">附注：這不適用於混合中的承租人。</span><span class="sxs-lookup"><span data-stu-id="e9e69-352">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="e9e69-353">目標群組織中的使用者必須具備適用于組織的適當 Exchange Online 訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="e9e69-353">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="e9e69-354">您可以在信箱移動之前套用授權，但只有在使用 ExchangeGUID 和 proxy 位址正確設定目標 MailUser 之後。</span><span class="sxs-lookup"><span data-stu-id="e9e69-354">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="e9e69-355">在套用 ExchangeGUID 之前套用授權，將會導致目標群組織中布建新的信箱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-355">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="e9e69-356">當您在信箱或 MailUser 物件上套用授權時，會清理所有 SMTP 類型 proxyAddresses，以確保 Exchange EmailAddresses 陣列中只包含已驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="e9e69-356">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="e9e69-357">您必須確定目標 MailUser 沒有與來源 ExchangeGuid 不符的先前 ExchangeGuid。</span><span class="sxs-lookup"><span data-stu-id="e9e69-357">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="e9e69-358">如果目標 MEU 先前已授權 Exchange Online 並已布建信箱，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="e9e69-358">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="e9e69-359">若目標 MailUser 先前授權或具有與來源 ExchangeGuid 不符的 ExchangeGuid，您必須執行雲端 MEU 的清除。</span><span class="sxs-lookup"><span data-stu-id="e9e69-359">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="e9e69-360">針對這些雲端 Meu，您可以執行 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 命令。</span><span class="sxs-lookup"><span data-stu-id="e9e69-360">For these cloud MEUs, you can run the `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` command.</span></span> 

    > [!Caution]
    > <span data-ttu-id="e9e69-361">此程式不可逆。</span><span class="sxs-lookup"><span data-stu-id="e9e69-361">This process is irreversible.</span></span> <span data-ttu-id="e9e69-362">如果物件有 softDeleted 信箱，就無法在此點之後還原。</span><span class="sxs-lookup"><span data-stu-id="e9e69-362">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="e9e69-363">不過，您可以將正確的 ExchangeGuid 與目標物件進行同步處理，MRS 會將來源信箱連線到新建立的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-363">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="e9e69-364"> (在新參數上參照 EHLO 博客。 ) </span><span class="sxs-lookup"><span data-stu-id="e9e69-364">(Reference EHLO blog on the new parameter.)</span></span> 
 
    <span data-ttu-id="e9e69-365">尋找先前使用此命令的信箱的物件。</span><span class="sxs-lookup"><span data-stu-id="e9e69-365">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    <span data-ttu-id="e9e69-366">範例如下。</span><span class="sxs-lookup"><span data-stu-id="e9e69-366">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    <span data-ttu-id="e9e69-367">使用此命令清除虛刪除的信箱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-367">Clear the soft-deleted mailbox using this command.</span></span>

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    <span data-ttu-id="e9e69-368">範例如下。</span><span class="sxs-lookup"><span data-stu-id="e9e69-368">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="e9e69-369">執行信箱遷移</span><span class="sxs-lookup"><span data-stu-id="e9e69-369">Perform mailbox migrations</span></span>

<span data-ttu-id="e9e69-370">跨承租人 Exchange 信箱的遷移會當作從目標租使用者起始的遷移批次提交。</span><span class="sxs-lookup"><span data-stu-id="e9e69-370">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="e9e69-371">這一點類似于從 Exchange 內部部署遷移至 Microsoft 365 時，使用中的遷移批次的運作方式。</span><span class="sxs-lookup"><span data-stu-id="e9e69-371">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="e9e69-372">建立遷移批次</span><span class="sxs-lookup"><span data-stu-id="e9e69-372">Create Migration batches</span></span>

<span data-ttu-id="e9e69-373">以下是開始 off 移動的範例遷移批次 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e9e69-373">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="e9e69-374">CSV 檔案中的電子郵件地址必須是目標租使用者中所指定的位址，而非來源承租人。</span><span class="sxs-lookup"><span data-stu-id="e9e69-374">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="e9e69-375">選取 [跨承租人使用者] 選項時，也支援從新的 Exchange 系統管理中心進行遷移批次提交。</span><span class="sxs-lookup"><span data-stu-id="e9e69-375">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>
 
#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="e9e69-376">更新內部部署 MailUsers</span><span class="sxs-lookup"><span data-stu-id="e9e69-376">Update on-premises MailUsers</span></span>

<span data-ttu-id="e9e69-377">當信箱從來源移至目標之後，您應該確定內部部署郵件使用者（包括來源和目標）已更新為新的 targetAddress。</span><span class="sxs-lookup"><span data-stu-id="e9e69-377">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="e9e69-378">在此範例中，移動中使用的 targetDeliveryDomain 是 **contoso \. onmicrosoft.com** 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-378">In the examples, the targetDeliveryDomain used in the move is **contoso\.onmicrosoft.com**.</span></span> <span data-ttu-id="e9e69-379">使用此 targetAddress 更新郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="e9e69-379">Update the mail users with this targetAddress.</span></span>
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="e9e69-380">常見問題集</span><span class="sxs-lookup"><span data-stu-id="e9e69-380">Frequently asked questions</span></span>
 
<span data-ttu-id="e9e69-381">**在移動之後，我們是否需要更新來源內部部署的 RemoteMailboxes？**</span><span class="sxs-lookup"><span data-stu-id="e9e69-381">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>
 
<span data-ttu-id="e9e69-382">是的，您應該在來源租使用者信箱移至目標租使用者時，更新來源內部部署使用者的 targetAddress (RemoteRoutingAddress/ExternalEmailAddress) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-382">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="e9e69-383">雖然郵件路由可以追蹤多個具有不同 targetAddresses 之郵件使用者的參考，但 Free/Busy 郵件使用者的查閱，都必須以信箱使用者的位置為目標。</span><span class="sxs-lookup"><span data-stu-id="e9e69-383">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="e9e69-384">Free/Busy 查閱將不會跟蹤多個重新導向。</span><span class="sxs-lookup"><span data-stu-id="e9e69-384">Free/Busy lookups will not chase multiple redirects.</span></span> 
 
<span data-ttu-id="e9e69-385">**小組聊天資料夾內容是否要遷移跨承租人？**</span><span class="sxs-lookup"><span data-stu-id="e9e69-385">**Does the Teams chat folder content migrate cross-tenant?**</span></span> 

<span data-ttu-id="e9e69-386">否，小組聊天資料夾內容不會遷移跨承租人。</span><span class="sxs-lookup"><span data-stu-id="e9e69-386">No, the Teams chat folder content does not migrate cross-tenant.</span></span> 
 
<span data-ttu-id="e9e69-387">**如何查看僅限跨承租人移動的移動，不是我的上架和脫離移動？**</span><span class="sxs-lookup"><span data-stu-id="e9e69-387">**How can I see just moves that are cross-tenant moves, not my onboarding and offboarding moves?**</span></span>

<span data-ttu-id="e9e69-388">使用 `-flags` 參數。</span><span class="sxs-lookup"><span data-stu-id="e9e69-388">Use the `-flags` parameter.</span></span> <span data-ttu-id="e9e69-389">範例如下。</span><span class="sxs-lookup"><span data-stu-id="e9e69-389">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
<span data-ttu-id="e9e69-390">**您可以提供範例腳本，以用於複製測試中所用的屬性嗎？**</span><span class="sxs-lookup"><span data-stu-id="e9e69-390">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="e9e69-391">範例–無擔保</span><span class="sxs-lookup"><span data-stu-id="e9e69-391">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="e9e69-392">此腳本會假設同時連線到來源信箱 (以取得來源值) 以及目標內部部署 Active Directory 網域服務 (，以標記 Microsoft.rtc.management.adconnect.schema.aduser 物件) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-392">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="e9e69-393">如果來源已啟用訴訟或單一專案復原，請在目的地帳戶上加以設定。</span><span class="sxs-lookup"><span data-stu-id="e9e69-393">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="e9e69-394">這會將目的地帳戶的暫放大小增加為 100 GB。</span><span class="sxs-lookup"><span data-stu-id="e9e69-394">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="e9e69-395">**移動信箱之後，如何在第1天存取 Outlook？**</span><span class="sxs-lookup"><span data-stu-id="e9e69-395">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="e9e69-396">由於只有一個租使用者可以擁有網域，所以當信箱移動完成時，先前的主要 SMTPAddress 將不會與目標租使用者中的使用者產生關聯。僅限與新租使用者相關聯的網域。</span><span class="sxs-lookup"><span data-stu-id="e9e69-396">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="e9e69-397">Outlook 會使用使用者新的 UPN 向服務進行驗證，而 Outlook 設定檔預期會尋找舊版主要 SMTPAddress，以符合目標系統中的信箱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-397">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="e9e69-398">因為舊版位址不在目標系統中，所以 outlook 設定檔不會連線以尋找新移動的信箱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-398">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="e9e69-399">在此初始部署中，使用者將需要以其新的 UPN、主要 SMTP 位址和重新同步處理 OST 內容來重新建立其設定檔。</span><span class="sxs-lookup"><span data-stu-id="e9e69-399">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="e9e69-400">當您批次使用者完成時，會據以進行規劃。</span><span class="sxs-lookup"><span data-stu-id="e9e69-400">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="e9e69-401">在建立 Outlook 用戶端設定檔，並將後續 OST 和 OAB 檔案下載至用戶端時，您需要考慮網路使用方式和容量。</span><span class="sxs-lookup"><span data-stu-id="e9e69-401">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="e9e69-402">**我需要擁有哪些 Exchange RBAC 角色，才能設定或完成跨租使用者移動？**</span><span class="sxs-lookup"><span data-stu-id="e9e69-402">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="e9e69-403">根據在執行信箱移動時，假設委派的職責，會有一個角色矩陣。</span><span class="sxs-lookup"><span data-stu-id="e9e69-403">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="e9e69-404">目前需要兩個角色：</span><span class="sxs-lookup"><span data-stu-id="e9e69-404">Currently, two roles are required:</span></span>  

- <span data-ttu-id="e9e69-405">第一個角色是針對執行將內容移入或移出承租人/組織界限的一次性設定工作。</span><span class="sxs-lookup"><span data-stu-id="e9e69-405">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="e9e69-406">當您將資料移出組織控制項時，對所有公司而言是一個重要的考慮，我們會選擇為組織管理員 (OrgAdmin) 中的最高指派角色。</span><span class="sxs-lookup"><span data-stu-id="e9e69-406">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="e9e69-407">此角色必須變更或設定定義遠端組織的-MailboxMoveCapability 的新 New-organizationrelationship。</span><span class="sxs-lookup"><span data-stu-id="e9e69-407">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="e9e69-408">只有 OrgAdmin 可以變更 MailboxMoveCapability 設定，而 OrganizationRelationhip 的其他屬性可由同盟共用系統管理員管理。</span><span class="sxs-lookup"><span data-stu-id="e9e69-408">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="e9e69-409">執行實際 move 命令的角色可委派給較低層級的功能。</span><span class="sxs-lookup"><span data-stu-id="e9e69-409">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="e9e69-410">移動信箱的角色會指派使用參數將信箱移入或移出組織的功能 `-RemoteTenant` 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-410">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="e9e69-411">**我們要如何瞄準已轉換的信箱 (上為 targetAddress (所選取的 SMTP 位址 TargetDeliveryDomain) MailUser 轉換) ？**</span><span class="sxs-lookup"><span data-stu-id="e9e69-411">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="e9e69-412">Exchange 信箱使用 MRS 手工 MailUser 建立原始來源信箱上的 targetAddress 時，會將電子郵件地址與目標物件上的電子郵件地址 (proxyAddress) 相符。</span><span class="sxs-lookup"><span data-stu-id="e9e69-412">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="e9e69-413">程式會使用傳入移動命令中的-TargetDeliveryDomain 值，然後在目標端檢查該網域的相符 proxy。</span><span class="sxs-lookup"><span data-stu-id="e9e69-413">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="e9e69-414">當我們找到相符的 proxyAddress 時，會使用對應的設定已轉換信箱上的 ExternalEmailAddress (targetAddress)  (現在 MailUser) 物件。</span><span class="sxs-lookup"><span data-stu-id="e9e69-414">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="e9e69-415">**信箱許可權如何轉換？**</span><span class="sxs-lookup"><span data-stu-id="e9e69-415">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="e9e69-416">信箱許可權包括「代理傳送者」和「信箱存取」：</span><span class="sxs-lookup"><span data-stu-id="e9e69-416">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="e9e69-417">「代理傳送者」 (AD： publicDelegates) 儲存收件者的 DN，以存取使用者的信箱做為代理人。</span><span class="sxs-lookup"><span data-stu-id="e9e69-417">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="e9e69-418">此值儲存在 Active Directory 中，而且目前不會移動做為信箱轉換的一部分。</span><span class="sxs-lookup"><span data-stu-id="e9e69-418">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="e9e69-419">如果來源信箱已設定 publicDelegates，當使用命令的目標環境中的 [MEU 至信箱] 轉換完成時，您必須 restamp 目標信箱上的 publicDelegates `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-419">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment using the `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` command.</span></span> 
 
- <span data-ttu-id="e9e69-420">當主體和代理人都移至目標系統時，信箱中儲存的信箱許可權會隨著信箱一起移動。</span><span class="sxs-lookup"><span data-stu-id="e9e69-420">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="e9e69-421">例如，使用者 TestUser_7 會被授與租使用者 SourceCompany.onmicrosoft.com 中的信箱 TestUser_8 FullAccess。</span><span class="sxs-lookup"><span data-stu-id="e9e69-421">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="e9e69-422">信箱移動完成 TargetCompany.onmicrosoft.com 後，就會在目標目錄中設定相同的許可權。</span><span class="sxs-lookup"><span data-stu-id="e9e69-422">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="e9e69-423">在來源與目標承租人中使用 *Get-MailboxPermission* TestUser_7 的範例如下所示。</span><span class="sxs-lookup"><span data-stu-id="e9e69-423">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="e9e69-424">Exchange Cmdlet 會據此為來源和目標加上首碼。</span><span class="sxs-lookup"><span data-stu-id="e9e69-424">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="e9e69-425">以下是移動之前信箱許可權的輸出範例。</span><span class="sxs-lookup"><span data-stu-id="e9e69-425">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="e9e69-426">以下是移動後的信箱許可權輸出範例。</span><span class="sxs-lookup"><span data-stu-id="e9e69-426">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="e9e69-427">不支援跨租使用者信箱和行事曆許可權。</span><span class="sxs-lookup"><span data-stu-id="e9e69-427">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="e9e69-428">您必須將主體和代理人組織成合併的移動批次，以便從來源租使用者同時從來源租使用者中轉換這些連線的信箱。</span><span class="sxs-lookup"><span data-stu-id="e9e69-428">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 
 
## <a name="known-issues"></a><span data-ttu-id="e9e69-429">已知問題</span><span class="sxs-lookup"><span data-stu-id="e9e69-429">Known issues</span></span> 

-  <span data-ttu-id="e9e69-430">**問題：無法遷移自動擴充的封存。**</span><span class="sxs-lookup"><span data-stu-id="e9e69-430">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="e9e69-431">跨承租人遷移功能支援特定使用者的主要信箱和封存信箱的遷移。</span><span class="sxs-lookup"><span data-stu-id="e9e69-431">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="e9e69-432">如果來源中的使用者有自動展開的封存–表示有一個以上的封存信箱，該功能就無法遷移其他的檔案。</span><span class="sxs-lookup"><span data-stu-id="e9e69-432">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="e9e69-433">**問題：具有非擁有的 smtp proxyAddress block MRS 的雲端 MailUsers 會移動背景。**</span><span class="sxs-lookup"><span data-stu-id="e9e69-433">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="e9e69-434">建立目標租使用者 MailUser 物件時，您必須確定所有 SMTP proxy 位址都屬於目標租使用者組織。</span><span class="sxs-lookup"><span data-stu-id="e9e69-434">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="e9e69-435">如果 SMTP proxyAddress 存在於不屬於本機租使用者的目標郵件使用者上，則會禁止 MailUser 至信箱的轉換。</span><span class="sxs-lookup"><span data-stu-id="e9e69-435">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="e9e69-436">這是因為我們保證信箱物件只會從租使用者授權的網域傳送郵件，而該網域是租使用者) 所宣告的 (網域：</span><span class="sxs-lookup"><span data-stu-id="e9e69-436">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 
- 
   - <span data-ttu-id="e9e69-437">當您從使用 Azure AD Connect 的內部部署同步處理使用者時，您可以在內部部署 MailUser 物件中，ExternalEmailAddress 指向信箱所在的來源承租人， (laran@contoso \. onmicrosoft.com) ，並且將 PrimarySMTPAddress 標記為位於目標租使用者 (Lara.Newton@northwind \. com) 的網域。</span><span class="sxs-lookup"><span data-stu-id="e9e69-437">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso\.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind\.com).</span></span> <span data-ttu-id="e9e69-438">這些值會向外同步處理至租使用者，並已布建適當的郵件使用者，可供遷移。</span><span class="sxs-lookup"><span data-stu-id="e9e69-438">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="e9e69-439">這裡會顯示範例物件。</span><span class="sxs-lookup"><span data-stu-id="e9e69-439">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="e9e69-440">*Name.onmicrosoft.com17 \. com* 位址 *不* 存在於 EmailAddresses/proxyAddresses 陣列中。</span><span class="sxs-lookup"><span data-stu-id="e9e69-440">The *contoso.onmicrosoft\.com* address is *not* present in the EmailAddresses/proxyAddresses array.</span></span>

- <span data-ttu-id="e9e69-441">**問題：將「外部」主要 SMTP 位址的 MailUser 物件修改/重設為「內部」公司所宣告的網域**</span><span class="sxs-lookup"><span data-stu-id="e9e69-441">**Issue: MailUser objects with “external” primary SMTP addresses are modified/reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="e9e69-442">MailUser 物件是指向非本機信箱的指標。</span><span class="sxs-lookup"><span data-stu-id="e9e69-442">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="e9e69-443">在跨租使用者信箱遷移的情況下，我們會使用 MailUser 物件，代表從目標群組織的觀點) 或目標信箱 (來源組織的觀點) 中的來源信箱 (。</span><span class="sxs-lookup"><span data-stu-id="e9e69-443">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="e9e69-444">MailUsers 將會有 ExternalEmailAddress (targetAddress) ，指向實際信箱的 smtp 位址 (ProxyTest \@ fabrikam \. onmicrosoft.com) 和 primarySMTP 位址，表示目錄中信箱使用者的顯示 smtp 位址。</span><span class="sxs-lookup"><span data-stu-id="e9e69-444">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest\@fabrikam\.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="e9e69-445">有些組織會選擇將主要 SMTP 位址顯示為外部的 SMTP 位址，而不是本機租使用者所擁有/驗證的位址 (例如 fabrikam.com，而非 contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="e9e69-445">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="e9e69-446">不過，將 Exchange 服務計畫物件套用至 MailUser 透過授權作業之後，主要 SMTP 位址會修改成顯示為由本機組織 (contoso.com) 驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="e9e69-446">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="e9e69-447">有兩個可能的原因：</span><span class="sxs-lookup"><span data-stu-id="e9e69-447">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="e9e69-448">將任何 Exchange 服務計畫套用至 MailUser 時，Azure AD 程式都會開始強制執行 proxy 清理，以確保本機組織無法從其他租使用者傳送郵件、哄騙或郵件。</span><span class="sxs-lookup"><span data-stu-id="e9e69-448">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="e9e69-449">如果本機組織未驗證位址，將會移除具有這些服務方案之收件者物件上的任何 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="e9e69-449">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="e9e69-450">就像範例中的情況， \. contoso onmicrosoft.com 租使用者不會驗證 Fabikam com 網域 \. ，因此清理會移除該 fabrikam \. com 網域。</span><span class="sxs-lookup"><span data-stu-id="e9e69-450">As is the case in the example, the Fabikam\.com domain is NOT verified by the contoso\.onmicrosoft.com tenant, so the scrubbing removes that fabrikam\.com domain.</span></span> <span data-ttu-id="e9e69-451">如果您想要在遷移或遷移之後的 MailUser 上保留這些外部網域，您必須在移動完成後或移動之前，變更遷移程式，以去除授權，以確保使用者已套用預期的外部品牌。</span><span class="sxs-lookup"><span data-stu-id="e9e69-451">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="e9e69-452">您必須確定信箱物件已正確授權，否則不會影響郵件服務。</span><span class="sxs-lookup"><span data-stu-id="e9e69-452">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="e9e69-453">在 Contoso onmicrosoft.com 租使用者的 MailUser 中移除服務方案的範例腳本 \. ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e9e69-453">An example script to remove the service plans on a MailUser in the Contoso\.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="e9e69-454">ServicePlans 所指派的結果集如下所示。</span><span class="sxs-lookup"><span data-stu-id="e9e69-454">Results in the set of ServicePlans assigned are shown here.</span></span>

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       <span data-ttu-id="e9e69-455">使用者的 PrimarySMTPAddress 不再被清理。</span><span class="sxs-lookup"><span data-stu-id="e9e69-455">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="e9e69-456">Fabrikam.com 網域不是由 contoso.onmicrosoft.com 租使用者所擁有，將會以目錄中顯示的主要 SMTP 位址來保存。</span><span class="sxs-lookup"><span data-stu-id="e9e69-456">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="e9e69-457">範例如下。</span><span class="sxs-lookup"><span data-stu-id="e9e69-457">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="e9e69-458">當 msExchRemoteRecipientType 設定為 8 (DeprovisionMailbox) 時，針對遷移到目標租使用者的內部部署 MailUsers，Azure 中的 proxy 清理邏輯會移除 nonowned 網域，並將 primarySMTP 重設為擁有的網域。</span><span class="sxs-lookup"><span data-stu-id="e9e69-458">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="e9e69-459">清除內部部署 MailUser 中的 [msExchRemoteRecipientType]，便不再套用 proxy 清理邏輯。</span><span class="sxs-lookup"><span data-stu-id="e9e69-459">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="e9e69-460">以下是包括 Exchange Online 之一組可能的完整服務方案。</span><span class="sxs-lookup"><span data-stu-id="e9e69-460">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="e9e69-461">姓名</span><span class="sxs-lookup"><span data-stu-id="e9e69-461">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="e9e69-462">高級 eDiscovery 儲存 (500GB) </span><span class="sxs-lookup"><span data-stu-id="e9e69-462">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="e9e69-463">客戶加密箱</span><span class="sxs-lookup"><span data-stu-id="e9e69-463">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="e9e69-464">資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="e9e69-464">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="e9e69-465">Exchange Enterprise CAL 服務 (EOP、DLP) </span><span class="sxs-lookup"><span data-stu-id="e9e69-465">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="e9e69-466">Exchange 基本版</span><span class="sxs-lookup"><span data-stu-id="e9e69-466">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="e9e69-467">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="e9e69-467">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="e9e69-468">Exchange Online (P1) </span><span class="sxs-lookup"><span data-stu-id="e9e69-468">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="e9e69-469">Exchange Online (計劃 1)</span><span class="sxs-lookup"><span data-stu-id="e9e69-469">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="e9e69-470">Exchange Online (計劃 2)</span><span class="sxs-lookup"><span data-stu-id="e9e69-470">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="e9e69-471">Exchange Online 適用的 Exchange Online 封存</span><span class="sxs-lookup"><span data-stu-id="e9e69-471">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="e9e69-472">Exchange Server 適用的 Exchange Online 封存</span><span class="sxs-lookup"><span data-stu-id="e9e69-472">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="e9e69-473">Exchange Online 非使用中使用者附加元件</span><span class="sxs-lookup"><span data-stu-id="e9e69-473">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="e9e69-474">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="e9e69-474">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="e9e69-475">Exchange Online 多地理位置</span><span class="sxs-lookup"><span data-stu-id="e9e69-475">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="e9e69-476">Exchange Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="e9e69-476">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="e9e69-477">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="e9e69-477">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="e9e69-478">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e9e69-478">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="e9e69-479">資訊障礙</span><span class="sxs-lookup"><span data-stu-id="e9e69-479">Information Barriers</span></span>                              |
   | <span data-ttu-id="e9e69-480">Office 365 的資訊保護-精品</span><span class="sxs-lookup"><span data-stu-id="e9e69-480">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="e9e69-481">Office 365 的資訊保護-標準</span><span class="sxs-lookup"><span data-stu-id="e9e69-481">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="e9e69-482">透過 MyAnalytics 的真知灼見</span><span class="sxs-lookup"><span data-stu-id="e9e69-482">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="e9e69-483">Microsoft 365 高級審核</span><span class="sxs-lookup"><span data-stu-id="e9e69-483">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="e9e69-484">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="e9e69-484">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="e9e69-485">Microsoft 商務中心</span><span class="sxs-lookup"><span data-stu-id="e9e69-485">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="e9e69-486">Microsoft MyAnalytics (完整) </span><span class="sxs-lookup"><span data-stu-id="e9e69-486">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="e9e69-487">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="e9e69-487">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="e9e69-488">Microsoft Defender for Office 365 (方案 1) </span><span class="sxs-lookup"><span data-stu-id="e9e69-488">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="e9e69-489">Microsoft Defender for Office 365 (方案 2) </span><span class="sxs-lookup"><span data-stu-id="e9e69-489">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="e9e69-490">Office 365 的特殊許可權存取管理</span><span class="sxs-lookup"><span data-stu-id="e9e69-490">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="e9e69-491">Office 365 中的高級加密</span><span class="sxs-lookup"><span data-stu-id="e9e69-491">Premium Encryption in Office 365</span></span>                  |
    
