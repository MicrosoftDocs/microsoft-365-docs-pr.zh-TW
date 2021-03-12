---
title: 租用戶等級的 Microsoft 365 客戶金鑰 (公開預覽)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/17/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: 瞭解如何為您的 Microsoft 365 租使用者中的所有資料設定客戶金鑰。
ms.openlocfilehash: 7ffa9a8148a8ae699711b62da48cd2c856d48cac
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727476"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="1a41a-103">在承租人層級 (公開預覽的 Microsoft 365 客戶金鑰概述) </span><span class="sxs-lookup"><span data-stu-id="1a41a-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="1a41a-104">使用您提供的金鑰，您可以建立資料加密原則 (DEP) 並指派給租使用者。</span><span class="sxs-lookup"><span data-stu-id="1a41a-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="1a41a-105">DEP 會針對這些工作負載在租使用者上進行資料加密：</span><span class="sxs-lookup"><span data-stu-id="1a41a-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="1a41a-106">小組聊天訊息 (1:1 聊天、群組交談、會議聊天及通道交談) </span><span class="sxs-lookup"><span data-stu-id="1a41a-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="1a41a-107">小組媒體郵件 (影像、程式碼片段、影片郵件、音訊訊息、wiki 影像) </span><span class="sxs-lookup"><span data-stu-id="1a41a-107">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="1a41a-108">小組儲存中儲存的小組通話和會議錄製</span><span class="sxs-lookup"><span data-stu-id="1a41a-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="1a41a-109">小組聊天通知</span><span class="sxs-lookup"><span data-stu-id="1a41a-109">Teams chat notifications</span></span>
- <span data-ttu-id="1a41a-110">小娜的小組聊天建議</span><span class="sxs-lookup"><span data-stu-id="1a41a-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="1a41a-111">小組狀態郵件</span><span class="sxs-lookup"><span data-stu-id="1a41a-111">Teams status messages</span></span>
- <span data-ttu-id="1a41a-112">Exchange Online 的使用者和信號資訊</span><span class="sxs-lookup"><span data-stu-id="1a41a-112">User and signal information for Exchange Online</span></span>
- <span data-ttu-id="1a41a-113">Exchange Online 信箱，但在應用層級尚未加密客戶金鑰 DEPs</span><span class="sxs-lookup"><span data-stu-id="1a41a-113">Exchange Online mailboxes that aren't already encrypted Customer Key DEPs at the application level</span></span>

<span data-ttu-id="1a41a-114">針對 Microsoft 小組，租使用者層級的客戶機碼會從 DEP 指派給租使用者時，加密新的資料。</span><span class="sxs-lookup"><span data-stu-id="1a41a-114">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="1a41a-115">公開預覽不支援加密過去的資料。</span><span class="sxs-lookup"><span data-stu-id="1a41a-115">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="1a41a-116">針對 Exchange Online，客戶金鑰會加密所有現有和新的資料。</span><span class="sxs-lookup"><span data-stu-id="1a41a-116">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="1a41a-117">您可以為每個租使用者建立多個 DEPs，但在任何時間點都只能指定一個 DEP。</span><span class="sxs-lookup"><span data-stu-id="1a41a-117">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="1a41a-118">當您指派 DEP 時，系統會自動開始加密，但可能需要一些時間才能完成，具體取決於您的承租人的大小。</span><span class="sxs-lookup"><span data-stu-id="1a41a-118">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="1a41a-119">承租人層級原則新增更多控制至 Microsoft 365 的客戶機碼</span><span class="sxs-lookup"><span data-stu-id="1a41a-119">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="1a41a-120">如果您已設定 Exchange Online 和 Sharepoint Online 的客戶金鑰，以下是新租使用者層級公開預覽的方式。</span><span class="sxs-lookup"><span data-stu-id="1a41a-120">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="1a41a-121">您建立的承租人層級加密原則會加密 microsoft 團隊和 Microsoft 365 中的 Exchange Online 工作負載的所有資料。</span><span class="sxs-lookup"><span data-stu-id="1a41a-121">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="1a41a-122">不過，對於 Exchange Online，如果您已將客戶金鑰 DEPs 指派給個別信箱，則租使用者層級原則不會覆寫這些 DEPs。</span><span class="sxs-lookup"><span data-stu-id="1a41a-122">However, for Exchange Online, if you have already assigned Customer Key DEPs to individual mailboxes, the tenant-level policy won't override those DEPs.</span></span> <span data-ttu-id="1a41a-123">租使用者層級原則只會加密尚未指定信箱層級客戶金鑰 DEP 的信箱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-123">The tenant-level policy will only encrypt mailboxes that aren't assigned a mailbox level Customer Key DEP already.</span></span>

<span data-ttu-id="1a41a-124">例如，Microsoft 小組檔案和部分小組的呼叫和會議錄製會儲存在商務用 OneDrive 中，SharePoint 是由 SharePoint 線上 DEP 加密。</span><span class="sxs-lookup"><span data-stu-id="1a41a-124">For example, Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="1a41a-125">單一 SharePoint 線上 DEP 會加密單一地理位置內的內容。</span><span class="sxs-lookup"><span data-stu-id="1a41a-125">A single SharePoint Online DEP encrypts content within a single geo.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="1a41a-126">在承租人層級設定客戶機碼 (公開預覽) </span><span class="sxs-lookup"><span data-stu-id="1a41a-126">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="1a41a-127">這些步驟類似，但與在應用層級設定客戶機碼的步驟並不相同。</span><span class="sxs-lookup"><span data-stu-id="1a41a-127">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="1a41a-128">您應只對測試承租人中的測試資料使用此公開預覽。</span><span class="sxs-lookup"><span data-stu-id="1a41a-128">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="1a41a-129">請勿在生產資料或您的實際執行環境中使用此版本。</span><span class="sxs-lookup"><span data-stu-id="1a41a-129">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="1a41a-130">如果您已具備客戶金鑰的實際執行部署，請使用下列步驟，在測試環境中的承租人層級設定客戶機碼。</span><span class="sxs-lookup"><span data-stu-id="1a41a-130">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span>

<span data-ttu-id="1a41a-131">您可以遠端連線至 Azure PowerShell，以完成大部分的工作。</span><span class="sxs-lookup"><span data-stu-id="1a41a-131">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="1a41a-132">為了獲得最佳結果，請使用版本4.4.0 或更新版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1a41a-132">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="1a41a-133">開始之前，請確定下列各項：</span><span class="sxs-lookup"><span data-stu-id="1a41a-133">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="1a41a-134">您必須使用具有合規性系統管理員角色的工作或學校帳戶，以在租使用者層級設定客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-134">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="1a41a-135">確定您的組織有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="1a41a-135">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="1a41a-136">使用企業合約或雲端服務提供者，以支付已開發票的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-136">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="1a41a-137">客戶機碼不支援使用「隨付」方案或信用卡使用信用卡購買的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-137">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="1a41a-138">從 office 365 的2020年4月1日開始，于 office 365 E5，M365 E5，M365 E5 規範，以及 M365 E5 & 控管 SKUs 中提供的資訊保護。</span><span class="sxs-lookup"><span data-stu-id="1a41a-138">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="1a41a-139">Office 365 Advanced 相容性 SKU 已無法再提供購置新的授權。</span><span class="sxs-lookup"><span data-stu-id="1a41a-139">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="1a41a-140">現有的 Office 365 Advanced 相容性授權會繼續受到支援。</span><span class="sxs-lookup"><span data-stu-id="1a41a-140">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="1a41a-141">雖然在具有適當授權的承租人下可以啟用服務，但您仍然應該確定所有從服務受益的使用者都有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="1a41a-141">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="1a41a-142">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="1a41a-142">Create two new Azure subscriptions</span></span>

<span data-ttu-id="1a41a-143">客戶金鑰需要每個資料加密原則 (DEP) 的兩個金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-143">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="1a41a-144">若要做到這一點，您必須建立兩個 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-144">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="1a41a-145">建議的最佳作法是，您組織中的個別成員可以在每個訂閱中設定一個金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-145">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="1a41a-146">請只使用這些 Azure 訂閱來管理 Microsoft 365 的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-146">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="1a41a-147">這會保護您的組織，以防其中一個操作員意外、故意或惡意刪除，或 mismanages 其負責的金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-147">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="1a41a-148">您可以為組織建立的 Azure 訂閱數目沒有實際的限制。</span><span class="sxs-lookup"><span data-stu-id="1a41a-148">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="1a41a-149">遵循這項最佳作法可協助將「因人」錯誤所造成的影響降至最低，以協助管理客戶金鑰所使用的資源。</span><span class="sxs-lookup"><span data-stu-id="1a41a-149">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="1a41a-150">註冊 Azure 訂閱以使用強制保留期間</span><span class="sxs-lookup"><span data-stu-id="1a41a-150">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="1a41a-151">暫時或永久遺失根加密金鑰的功能可能會造成中斷，甚至可能造成資料遺失。</span><span class="sxs-lookup"><span data-stu-id="1a41a-151">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="1a41a-152">因此，與客戶金鑰搭配使用的資源需要加強保護。</span><span class="sxs-lookup"><span data-stu-id="1a41a-152">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="1a41a-153">與客戶金鑰搭配使用的所有 Azure 資源，除了預設設定之外，還提供保護機制。</span><span class="sxs-lookup"><span data-stu-id="1a41a-153">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="1a41a-154">您可以使用 Azure 訂閱進行標記或註冊，以防止立即和不可撤銷的取消。</span><span class="sxs-lookup"><span data-stu-id="1a41a-154">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="1a41a-155">這稱為註冊強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="1a41a-155">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="1a41a-156">在必要保留期間內註冊 Azure 訂閱所需的步驟，必須與 Microsoft 共同作業。</span><span class="sxs-lookup"><span data-stu-id="1a41a-156">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="1a41a-157">此程式最多可長達五個工作日。</span><span class="sxs-lookup"><span data-stu-id="1a41a-157">This process can take up to five business days.</span></span> <span data-ttu-id="1a41a-158">先前，這有時候稱為「不要取消」。</span><span class="sxs-lookup"><span data-stu-id="1a41a-158">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="1a41a-159">在聯繫 Microsoft 365 團隊之前，您必須針對每個用客戶金鑰使用的 Azure 訂閱執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="1a41a-159">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="1a41a-160">開始之前，請確定您已安裝 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 模組。</span><span class="sxs-lookup"><span data-stu-id="1a41a-160">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="1a41a-161">使用 Azure PowerShell 登入。</span><span class="sxs-lookup"><span data-stu-id="1a41a-161">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="1a41a-162">如需相關指示，請參閱 [使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="1a41a-162">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="1a41a-163">執行 Register-AzProviderFeature Cmdlet 註冊您的訂閱，以使用強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="1a41a-163">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="1a41a-164">針對每個訂閱執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1a41a-164">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="1a41a-165">請與 Microsoft 聯繫以在 [m365ck@microsoft.com](mailto:m365ck@microsoft.com)完成此程式。</span><span class="sxs-lookup"><span data-stu-id="1a41a-165">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="1a41a-166">在您的電子郵件中包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="1a41a-166">Include the following in your email:</span></span>

   <span data-ttu-id="1a41a-167">主旨 **：客戶** 金鑰\<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="1a41a-167">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="1a41a-168">**Body**：訂閱 IDs，您想要完成其強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="1a41a-168">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="1a41a-169">每個訂閱的 Get-AzProviderFeature 輸出。</span><span class="sxs-lookup"><span data-stu-id="1a41a-169">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="1a41a-170">完成此程式的服務等級協定 (SLA) 一天之後，Microsoft 會 (通知您已註冊訂閱，) 您已註冊訂閱，以使用強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="1a41a-170">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="1a41a-171">當您收到來自 Microsoft 的通知，表明已完成註冊後，請執行 Get-AzProviderFeature 命令，按下列方式，以確認註冊的狀態。</span><span class="sxs-lookup"><span data-stu-id="1a41a-171">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="1a41a-172">若驗證，Get-AzProviderFeature 命令會傳回登錄 **狀態** 屬性的 **註冊** 值。</span><span class="sxs-lookup"><span data-stu-id="1a41a-172">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="1a41a-173">針對每個訂閱執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1a41a-173">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="1a41a-174">若要完成此程式，請執行 Register-AzResourceProvider 命令。</span><span class="sxs-lookup"><span data-stu-id="1a41a-174">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="1a41a-175">針對每個訂閱執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1a41a-175">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="1a41a-176">在每個訂閱中建立高級 Azure 金鑰 Vault</span><span class="sxs-lookup"><span data-stu-id="1a41a-176">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="1a41a-177">建立主要 vault 的步驟會在 [開始使用 Azure Key vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)時記錄下來，可引導您安裝及啟動 azure PowerShell、連線至 azure 訂閱、建立資源群組，以及在該資源群組中建立金鑰 vault。</span><span class="sxs-lookup"><span data-stu-id="1a41a-177">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="1a41a-178">當您建立金鑰 vault 時，您必須選擇 SKU： [標準] 或 [特優]。</span><span class="sxs-lookup"><span data-stu-id="1a41a-178">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="1a41a-179">Standard SKU 允許使用軟體來保護 Azure 金鑰 Vault 金鑰-沒有硬體安全性模組 (HSM) 金鑰保護-而且特優 SKU 允許使用 Hsm 來保護主要 Vault 金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-179">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="1a41a-180">客戶金鑰可接受使用任一 SKU 的金鑰電子倉庫，但 Microsoft 強烈建議您只使用特優 SKU。</span><span class="sxs-lookup"><span data-stu-id="1a41a-180">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="1a41a-181">使用任何一種類型之機碼的作業成本是相同的，所以每個受 HSM 保護的金鑰只會有每個月的成本差異。</span><span class="sxs-lookup"><span data-stu-id="1a41a-181">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="1a41a-182">如需詳細資訊，請參閱 [主要 Vault 定價](https://azure.microsoft.com/pricing/details/key-vault/) 。</span><span class="sxs-lookup"><span data-stu-id="1a41a-182">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1a41a-183">針對實際執行資料使用特優 SKU 金鑰保存庫和受版權保護的金鑰，只使用標準的 SKU 金鑰保存庫和金鑰進行測試和驗證。</span><span class="sxs-lookup"><span data-stu-id="1a41a-183">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="1a41a-184">使用主要保管區的一般前置詞，並包含主要 vault 和機碼的使用和範圍的縮寫。</span><span class="sxs-lookup"><span data-stu-id="1a41a-184">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="1a41a-185">例如，針對存放庫在北美的 Contoso 服務，可能的名稱成對為 Contoso-O365-NA-VaultA1 和 Contoso-O365-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="1a41a-185">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="1a41a-186">保存庫名稱是 Azure 內全域唯一的字串，因此，您可能需要嘗試所需名稱的變化，以防其他 Azure 客戶已索取所需的名稱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-186">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="1a41a-187">設定後，就無法變更保存庫名稱，因此最佳作法是設定安裝的書面計畫，然後使用第二個人驗證計畫是否正確執行。</span><span class="sxs-lookup"><span data-stu-id="1a41a-187">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="1a41a-188">如果可能，請在非成對區域中建立您的電子倉庫。</span><span class="sxs-lookup"><span data-stu-id="1a41a-188">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="1a41a-189">配對的 Azure 區域可提供跨服務失敗網域的高可用性。</span><span class="sxs-lookup"><span data-stu-id="1a41a-189">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="1a41a-190">因此，區域配對可以視為彼此的備份區域。</span><span class="sxs-lookup"><span data-stu-id="1a41a-190">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="1a41a-191">這表示位於某個地區的 Azure 資源會透過成對區域自動取得容錯。</span><span class="sxs-lookup"><span data-stu-id="1a41a-191">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="1a41a-192">基於此原因，針對在地區是成對的資料加密原則中所使用的兩個保存庫選擇地區時，只會使用兩個可用區域的可用性。</span><span class="sxs-lookup"><span data-stu-id="1a41a-192">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="1a41a-193">大多數地理有兩個地區，所以尚不能選取非成對區域。</span><span class="sxs-lookup"><span data-stu-id="1a41a-193">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="1a41a-194">如有可能，請選擇兩個不成對的區域，以用於資料加密原則的兩個保存庫。</span><span class="sxs-lookup"><span data-stu-id="1a41a-194">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="1a41a-195">其優點是共有四個地區的可用性。</span><span class="sxs-lookup"><span data-stu-id="1a41a-195">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="1a41a-196">如需詳細資訊，請參閱 [Business 持續性和嚴重損壞修復 (BCDR) ： Azure 成對區域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 的目前區域配對清單。</span><span class="sxs-lookup"><span data-stu-id="1a41a-196">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="1a41a-197">將許可權指派給每個金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="1a41a-197">Assign permissions to each key vault</span></span>

<span data-ttu-id="1a41a-198">針對每個金鑰保存庫，您必須根據您的實施，為客戶機碼定義三組不同的許可權。</span><span class="sxs-lookup"><span data-stu-id="1a41a-198">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="1a41a-199">例如，您必須為下列各項專案定義一組許可權：</span><span class="sxs-lookup"><span data-stu-id="1a41a-199">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="1a41a-200">**主要 vault 系統管理員** ，會針對您的組織執行重要 vault 的日常管理。</span><span class="sxs-lookup"><span data-stu-id="1a41a-200">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="1a41a-201">這些工作包括備份、建立、取得、匯入、清單及還原。</span><span class="sxs-lookup"><span data-stu-id="1a41a-201">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="1a41a-202">指派給主要 vault 管理員的許可權集不包含刪除金鑰的許可權。</span><span class="sxs-lookup"><span data-stu-id="1a41a-202">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="1a41a-203">這是故意和重要的作法。</span><span class="sxs-lookup"><span data-stu-id="1a41a-203">This is intentional and an important practice.</span></span> <span data-ttu-id="1a41a-204">刪除加密金鑰通常不會這麼做，因為這樣做會永久銷毀資料。</span><span class="sxs-lookup"><span data-stu-id="1a41a-204">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="1a41a-205">根據預設，請勿將此許可權授與主要 vault 管理員的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="1a41a-205">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="1a41a-206">相反地，針對主要 vault 投稿人保留這種情況，而且只要清楚瞭解對結果的瞭解，就只需在短期內將其指派給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="1a41a-206">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="1a41a-207">若要將這些許可權指派給組織中的使用者，請使用 Azure PowerShell 登入您的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-207">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="1a41a-208">如需相關指示，請參閱 [使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="1a41a-208">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="1a41a-209">執行 Set-AzKeyVaultAccessPolicy Cmdlet 指派必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="1a41a-209">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="1a41a-210">例如：</span><span class="sxs-lookup"><span data-stu-id="1a41a-210">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="1a41a-211">可以變更 Azure Key Vault 自身許可權的 **主要 vault 參與者**。</span><span class="sxs-lookup"><span data-stu-id="1a41a-211">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="1a41a-212">您必須變更這些許可權，因為員工離職或加入您的小組，或是主要 vault 管理員合法需要刪除或還原機碼的少數情況。</span><span class="sxs-lookup"><span data-stu-id="1a41a-212">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="1a41a-213">這組重要的 vault 投稿人員必須授與主要 vault 上的投稿人角色。</span><span class="sxs-lookup"><span data-stu-id="1a41a-213">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="1a41a-214">您可以使用 Azure 資源管理員指派此角色。</span><span class="sxs-lookup"><span data-stu-id="1a41a-214">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="1a41a-215">如需詳細步驟，請參閱 [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) ，以管理您的 Azure 訂閱資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="1a41a-215">For detailed steps, see [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="1a41a-216">建立訂閱的系統管理員預設具有這種存取權，以及將其他管理員指派給參與者角色的能力。</span><span class="sxs-lookup"><span data-stu-id="1a41a-216">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="1a41a-217">Microsoft 365 在租使用者層級執行客戶金鑰工作的 **rest 加密服務資料**。</span><span class="sxs-lookup"><span data-stu-id="1a41a-217">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="1a41a-218">若要授與 Microsoft 365 的許可權，請使用下列語法執行 **AzKeyVaultAccessPolicy** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1a41a-218">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="1a41a-219">其中：</span><span class="sxs-lookup"><span data-stu-id="1a41a-219">Where:</span></span>

  - <span data-ttu-id="1a41a-220">*保存庫名稱* 是您建立的主要 vault 名稱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-220">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="1a41a-221">範例：針對靜態加密服務的 Microsoft 365 資料，請將  *microsoft 365 appID* 取代為 `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="1a41a-221">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="1a41a-222">在金鑰保存庫上啟用然後確認虛刪除</span><span class="sxs-lookup"><span data-stu-id="1a41a-222">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="1a41a-223">當您可以快速復原金鑰時，由於意外或惡意刪除的金鑰，您很可能會因意外或惡意刪除的金鑰而經歷長時間的服務中斷。</span><span class="sxs-lookup"><span data-stu-id="1a41a-223">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="1a41a-224">啟用此設定（稱為「虛刪除」），才能搭配客戶機碼使用金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-224">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="1a41a-225">啟用 [虛刪除] 可讓您在刪除90天內復原金鑰或存放庫，而不需要從備份中還原。</span><span class="sxs-lookup"><span data-stu-id="1a41a-225">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="1a41a-226">若要在金鑰保存庫上啟用虛刪除，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1a41a-226">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="1a41a-227">使用 Windows PowerShell 登入您的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-227">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="1a41a-228">如需相關指示，請參閱 [使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="1a41a-228">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="1a41a-229">執行 [AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a41a-229">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="1a41a-230">在此範例中， *保存庫名稱* 是您要啟用 soft delete 之主要 vault 的名稱：</span><span class="sxs-lookup"><span data-stu-id="1a41a-230">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="1a41a-231">執行 **AzKeyVault** 指令程式，確認已為金鑰保存庫設定 soft delete。</span><span class="sxs-lookup"><span data-stu-id="1a41a-231">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="1a41a-232">如果已正確設定 key vault 的 [虛刪除]，則 _Soft Delete Enabled_ 屬性會傳回 **True** 值：</span><span class="sxs-lookup"><span data-stu-id="1a41a-232">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="1a41a-233">透過建立或匯入機碼，將機碼新增到每個機碼 vault</span><span class="sxs-lookup"><span data-stu-id="1a41a-233">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="1a41a-234">有兩種方法可以將機碼新增到 Azure Key Vault;您可以直接在 Key Vault 中建立金鑰，也可以匯入金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-234">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="1a41a-235">直接在 Key Vault 中建立金鑰是不夠複雜的方法，而匯入金鑰會提供如何產生機碼的整體控制權。</span><span class="sxs-lookup"><span data-stu-id="1a41a-235">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="1a41a-236">使用 RSA 機碼。</span><span class="sxs-lookup"><span data-stu-id="1a41a-236">Use the RSA keys.</span></span> <span data-ttu-id="1a41a-237">Azure 金鑰 Vault 不支援使用橢圓曲線鍵進行換行及解換。</span><span class="sxs-lookup"><span data-stu-id="1a41a-237">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="1a41a-238">若要直接在金鑰保存庫中建立金鑰，請執行 AzKeyVaultKey 指令 [程式](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a41a-238">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="1a41a-239">其中：</span><span class="sxs-lookup"><span data-stu-id="1a41a-239">Where:</span></span>

- <span data-ttu-id="1a41a-240">*vault 名稱* 是您要在其中建立機碼的金鑰 vault 名稱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-240">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="1a41a-241">*key name* 是您要給予新機碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-241">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="1a41a-242">使用主要保險檔的上述命名慣例，以前面所述的名稱慣例命名機碼。</span><span class="sxs-lookup"><span data-stu-id="1a41a-242">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="1a41a-243">如此一來，在僅顯示金鑰名稱的工具中，該字串是自我描述的。</span><span class="sxs-lookup"><span data-stu-id="1a41a-243">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="1a41a-244">如果您想要使用 HSM 來保護機碼，請確定您將 **hsm** 指定為 _Destination_ 參數的值，否則請指定 **軟體**。</span><span class="sxs-lookup"><span data-stu-id="1a41a-244">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="1a41a-245">例如：</span><span class="sxs-lookup"><span data-stu-id="1a41a-245">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="1a41a-246">檢查機碼的恢復層級</span><span class="sxs-lookup"><span data-stu-id="1a41a-246">Check the recovery level of your keys</span></span>

<span data-ttu-id="1a41a-247">Microsoft 365 要求 Azure Key Vault 訂閱設定為 [不要取消]，且客戶機碼使用的金鑰已啟用 [虛刪除]。</span><span class="sxs-lookup"><span data-stu-id="1a41a-247">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="1a41a-248">您可以查看金鑰上的復原層級，確認這一點。</span><span class="sxs-lookup"><span data-stu-id="1a41a-248">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="1a41a-249">若要檢查機碼的復原層級，請在 Azure PowerShell 中執行 Get-AzKeyVaultKey Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a41a-249">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="1a41a-250">若 _Recovery Level_ 屬性傳回的值不是可復原的 **+ ProtectedSubscription**，您必須查看這篇文章，並確定您已遵循將訂閱置於 [不要取消] 清單中的所有步驟，以及您已在每個主要存放庫上啟用「虛刪除」。</span><span class="sxs-lookup"><span data-stu-id="1a41a-250">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="1a41a-251">接下來，將電子郵件輸出的螢幕擷取畫面傳送 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` 至 m365ck@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="1a41a-251">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="1a41a-252">備份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="1a41a-252">Back up Azure Key Vault</span></span>

<span data-ttu-id="1a41a-253">立即建立或變更索引鍵，執行備份及儲存備份的備份，不論是線上還是離線。</span><span class="sxs-lookup"><span data-stu-id="1a41a-253">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="1a41a-254">不要將離線副本連線到任何網路。</span><span class="sxs-lookup"><span data-stu-id="1a41a-254">Don't connect offline copies to any network.</span></span> <span data-ttu-id="1a41a-255">請改為將它們儲存在實體安全或商業儲存設施中。</span><span class="sxs-lookup"><span data-stu-id="1a41a-255">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="1a41a-256">至少應有一個備份副本儲存在發生嚴重損壞時可存取的位置。</span><span class="sxs-lookup"><span data-stu-id="1a41a-256">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="1a41a-257">備份 blob 是一種還原重要材料的唯一方法，應永久銷毀主要 Vault 金鑰，否則無法使用。</span><span class="sxs-lookup"><span data-stu-id="1a41a-257">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="1a41a-258">Azure Key Vault 外部的金鑰和匯入到 Azure Key Vault 的金鑰不會做為備份，因為客戶金鑰使用金鑰所需的中繼資料不存在於外部金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-258">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="1a41a-259">只有從 Azure 金鑰保存庫取得的備份可用於使用客戶金鑰進行還原作業。</span><span class="sxs-lookup"><span data-stu-id="1a41a-259">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="1a41a-260">因此，請務必在上載或建立金鑰時進行 Azure 金鑰 Vault 備份。</span><span class="sxs-lookup"><span data-stu-id="1a41a-260">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="1a41a-261">若要建立 Azure Key Vault 機碼的備份，請執行 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a41a-261">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="1a41a-262">確定您的輸出檔案使用尾碼 `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="1a41a-262">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="1a41a-263">由此 Cmdlet 所產生的輸出檔已加密，且無法用於 Azure Key Vault 之外。</span><span class="sxs-lookup"><span data-stu-id="1a41a-263">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="1a41a-264">備份只能還原至執行備份的來源 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-264">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="1a41a-265">例如：</span><span class="sxs-lookup"><span data-stu-id="1a41a-265">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="1a41a-266">驗證 Azure 金鑰 Vault 設定設定</span><span class="sxs-lookup"><span data-stu-id="1a41a-266">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="1a41a-267">在 DEP 中使用金鑰之前執行驗證是選用的，但是強烈建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="1a41a-267">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="1a41a-268">尤其是，如果您使用步驟來設定您的金鑰和保險庫（如本主題所述），您應該先驗證 Azure 金鑰 Vault 資源的健康情況，再設定客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="1a41a-268">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="1a41a-269">若要確認您的機碼已啟用 get、wrapKey 及 unwrapKey 作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1a41a-269">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="1a41a-270">執行 [AzKeyVault 指令程式](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a41a-270">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="1a41a-271">在 [輸出] 中，視需要尋找存取原則及 Microsoft 365 應用程式識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="1a41a-271">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="1a41a-272">所有三個作業、get、wrapKey 及 unwrapKey 都必須顯示在 [索引鍵的許可權] 底下。</span><span class="sxs-lookup"><span data-stu-id="1a41a-272">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="1a41a-273">如果存取原則設定不正確，請執行 Set-AzKeyVaultAccessPolicy Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a41a-273">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="1a41a-274">範例：針對靜態加密服務的 Microsoft 365 資料，請將  *microsoft 365 appID* 取代為 `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="1a41a-274">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="1a41a-275">若要確認沒有為您的金鑰設定到期日，請執行 [AzKeyVaultKey 指令程式](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a41a-275">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="1a41a-276">已到期的金鑰無法由客戶金鑰使用，而且嘗試使用到期金鑰會失敗，而且可能會造成服務中斷。</span><span class="sxs-lookup"><span data-stu-id="1a41a-276">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="1a41a-277">強烈建議使用與客戶金鑰搭配使用的金鑰沒有到期日。</span><span class="sxs-lookup"><span data-stu-id="1a41a-277">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="1a41a-278">到期日一經設定，便無法移除，但可以變更為不同的日期。</span><span class="sxs-lookup"><span data-stu-id="1a41a-278">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="1a41a-279">如果必須使用具有到期日期設定的金鑰，請將 [到期] 值變更為12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="1a41a-279">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="1a41a-280">到期日設定為日期12/31/9999 以外的金鑰將不會通過 Microsoft 365 驗證。</span><span class="sxs-lookup"><span data-stu-id="1a41a-280">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="1a41a-281">若要變更已設定為12/31/9999 以外任何值的到期日，請執行 AzKeyVaultKey 指令 [程式](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a41a-281">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="1a41a-282">取得每個 Azure 金鑰保存庫機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="1a41a-282">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="1a41a-283">當您在 Azure 中完成所有步驟以設定金鑰保存庫並新增金鑰之後，請執行下列命令，以取得每個 key vault 中的金鑰的 URI。</span><span class="sxs-lookup"><span data-stu-id="1a41a-283">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="1a41a-284">當您稍後建立並指派每個 DEP 時，您將需要使用這些 URIs，因此請將此資訊儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="1a41a-284">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="1a41a-285">請記得對每一個按鍵 vault 執行一次此指令。</span><span class="sxs-lookup"><span data-stu-id="1a41a-285">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="1a41a-286">Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1a41a-286">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="1a41a-287">為您的租使用者設定客戶金鑰加密原則</span><span class="sxs-lookup"><span data-stu-id="1a41a-287">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="1a41a-288">您必須已獲指派許可權，才能執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a41a-288">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="1a41a-289">雖然這篇文章列出指令程式的所有參數，但如果不包含在指派給您的許可權中，您可能無法存取某些參數。</span><span class="sxs-lookup"><span data-stu-id="1a41a-289">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="1a41a-290">若要尋找在組織中執行任何 Cmdlet 或參數所需的權限，請參閱 [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)。</span><span class="sxs-lookup"><span data-stu-id="1a41a-290">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="1a41a-291">建立原則</span><span class="sxs-lookup"><span data-stu-id="1a41a-291">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

<span data-ttu-id="1a41a-292">描述：使用兩個 AKV 根機碼，啟用相容性管理員以建立新的資料加密原則 (DEP) 。</span><span class="sxs-lookup"><span data-stu-id="1a41a-292">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="1a41a-293">一旦建立後，便可使用 Set-M365DataAtRestEncryptionPolicyAssignment Cmdlet 指派原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-293">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="1a41a-294">在初次指派按鍵或旋轉按鍵後，新的機碼可能需要長達24小時才會生效。</span><span class="sxs-lookup"><span data-stu-id="1a41a-294">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="1a41a-295">如果新的 DEP 需要24小時以上才能生效，請與 Microsoft 聯繫。</span><span class="sxs-lookup"><span data-stu-id="1a41a-295">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="1a41a-296">範例：</span><span class="sxs-lookup"><span data-stu-id="1a41a-296">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="1a41a-297">參數：</span><span class="sxs-lookup"><span data-stu-id="1a41a-297">Parameters:</span></span>

| <span data-ttu-id="1a41a-298">名稱</span><span class="sxs-lookup"><span data-stu-id="1a41a-298">Name</span></span> | <span data-ttu-id="1a41a-299">描述</span><span class="sxs-lookup"><span data-stu-id="1a41a-299">Description</span></span> | <span data-ttu-id="1a41a-300">選用 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="1a41a-300">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="1a41a-301">姓名</span><span class="sxs-lookup"><span data-stu-id="1a41a-301">Name</span></span>|<span data-ttu-id="1a41a-302">資料加密原則的易記名稱</span><span class="sxs-lookup"><span data-stu-id="1a41a-302">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="1a41a-303">N</span><span class="sxs-lookup"><span data-stu-id="1a41a-303">N</span></span>|
|<span data-ttu-id="1a41a-304">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="1a41a-304">AzureKeyIDs</span></span>|<span data-ttu-id="1a41a-305">指定 Azure Key Vault 機碼的兩個 URI 值，以逗號分隔，以與資料加密原則產生關聯</span><span class="sxs-lookup"><span data-stu-id="1a41a-305">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="1a41a-306">N</span><span class="sxs-lookup"><span data-stu-id="1a41a-306">N</span></span>|
|<span data-ttu-id="1a41a-307">描述</span><span class="sxs-lookup"><span data-stu-id="1a41a-307">Description</span></span>|<span data-ttu-id="1a41a-308">資料加密原則的描述</span><span class="sxs-lookup"><span data-stu-id="1a41a-308">Description of the data encryption policy</span></span>|<span data-ttu-id="1a41a-309">N</span><span class="sxs-lookup"><span data-stu-id="1a41a-309">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="1a41a-310">指派原則</span><span class="sxs-lookup"><span data-stu-id="1a41a-310">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “<Default_PolicyName or Default_PolicyID>”
```

<span data-ttu-id="1a41a-311">描述：此指令程式用於設定預設資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-311">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="1a41a-312">這個原則將用來加密所有支援工作負載中的資料。</span><span class="sxs-lookup"><span data-stu-id="1a41a-312">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="1a41a-313">範例：</span><span class="sxs-lookup"><span data-stu-id="1a41a-313">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “Default_PolicyName”
```

<span data-ttu-id="1a41a-314">參數：</span><span class="sxs-lookup"><span data-stu-id="1a41a-314">Parameters:</span></span>

| <span data-ttu-id="1a41a-315">名稱</span><span class="sxs-lookup"><span data-stu-id="1a41a-315">Name</span></span> | <span data-ttu-id="1a41a-316">描述</span><span class="sxs-lookup"><span data-stu-id="1a41a-316">Description</span></span> | <span data-ttu-id="1a41a-317">選用 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="1a41a-317">Optional (Y/N)</span></span> |
|----------|----------|---------|
<span data-ttu-id="1a41a-318">-DataEncryptionPolicy</span><span class="sxs-lookup"><span data-stu-id="1a41a-318">-DataEncryptionPolicy</span></span>|<span data-ttu-id="1a41a-319">指定需要指派的資料加密原則;請指定原則名稱或原則識別碼。</span><span class="sxs-lookup"><span data-stu-id="1a41a-319">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="1a41a-320">N</span><span class="sxs-lookup"><span data-stu-id="1a41a-320">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="1a41a-321">修改或重新整理原則</span><span class="sxs-lookup"><span data-stu-id="1a41a-321">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="1a41a-322">描述：此 Cmdlet 可用於修改或重新整理現有的原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-322">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="1a41a-323">也可以用來啟用或停用原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-323">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="1a41a-324">在初次指派按鍵或旋轉按鍵後，新的機碼可能需要長達24小時才會生效。</span><span class="sxs-lookup"><span data-stu-id="1a41a-324">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="1a41a-325">如果新的 DEP 需要24小時以上才能生效，請與 Microsoft 聯繫。</span><span class="sxs-lookup"><span data-stu-id="1a41a-325">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="1a41a-326">範例：</span><span class="sxs-lookup"><span data-stu-id="1a41a-326">Examples:</span></span>

<span data-ttu-id="1a41a-327">停用資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-327">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="1a41a-328">重新整理資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-328">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

<span data-ttu-id="1a41a-329">參數：</span><span class="sxs-lookup"><span data-stu-id="1a41a-329">Parameters:</span></span>

| <span data-ttu-id="1a41a-330">名稱</span><span class="sxs-lookup"><span data-stu-id="1a41a-330">Name</span></span> | <span data-ttu-id="1a41a-331">描述</span><span class="sxs-lookup"><span data-stu-id="1a41a-331">Description</span></span> | <span data-ttu-id="1a41a-332">選用 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="1a41a-332">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="1a41a-333">-Identity</span><span class="sxs-lookup"><span data-stu-id="1a41a-333">-Identity</span></span>|<span data-ttu-id="1a41a-334">指定您要修改的資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-334">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="1a41a-335">N</span><span class="sxs-lookup"><span data-stu-id="1a41a-335">N</span></span>|
|<span data-ttu-id="1a41a-336">-重新整理</span><span class="sxs-lookup"><span data-stu-id="1a41a-336">-Refresh</span></span>|<span data-ttu-id="1a41a-337">在您旋轉 Azure Key Vault 中的任何相關機碼之後，請使用重新整理參數來更新資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-337">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="1a41a-338">您不需要使用此參數指定值。</span><span class="sxs-lookup"><span data-stu-id="1a41a-338">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="1a41a-339">Y</span><span class="sxs-lookup"><span data-stu-id="1a41a-339">Y</span></span>|
|<span data-ttu-id="1a41a-340">-已啟用</span><span class="sxs-lookup"><span data-stu-id="1a41a-340">-Enabled</span></span>|<span data-ttu-id="1a41a-341">Enabled 參數會啟用或停用資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-341">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="1a41a-342">停用原則之前，必須先將其指派給您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="1a41a-342">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="1a41a-343">有效值為：</span><span class="sxs-lookup"><span data-stu-id="1a41a-343">Valid values are:</span></span></br > <span data-ttu-id="1a41a-344">$true：已啟用原則</span><span class="sxs-lookup"><span data-stu-id="1a41a-344">$true: The policy is enabled</span></span></br > <span data-ttu-id="1a41a-345">$true：已啟用原則。此為預設值。</span><span class="sxs-lookup"><span data-stu-id="1a41a-345">$false: The policy is disabled.</span></span>|<span data-ttu-id="1a41a-346">Y</span><span class="sxs-lookup"><span data-stu-id="1a41a-346">Y</span></span>|
|<span data-ttu-id="1a41a-347">-名稱</span><span class="sxs-lookup"><span data-stu-id="1a41a-347">-Name</span></span>|<span data-ttu-id="1a41a-348">Name 參數會指定資料加密原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="1a41a-348">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="1a41a-349">Y</span><span class="sxs-lookup"><span data-stu-id="1a41a-349">Y</span></span>|
|<span data-ttu-id="1a41a-350">-描述</span><span class="sxs-lookup"><span data-stu-id="1a41a-350">-Description</span></span>|<span data-ttu-id="1a41a-351">Description 參數會指定資料加密原則的選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="1a41a-351">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="1a41a-352">Y</span><span class="sxs-lookup"><span data-stu-id="1a41a-352">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="1a41a-353">取得原則詳細資料</span><span class="sxs-lookup"><span data-stu-id="1a41a-353">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="1a41a-354">描述：此 Cmdlet 會列出針對租使用者或特定原則的詳細資料所建立的所有 M365DataAtRest 加密原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-354">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="1a41a-355">範例：</span><span class="sxs-lookup"><span data-stu-id="1a41a-355">Examples:</span></span>

<span data-ttu-id="1a41a-356">此範例會傳回組織中 M365DatAtRest 加密原則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="1a41a-356">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="1a41a-357">此範例會傳回名為 "名稱 Policy" 的資料加密原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1a41a-357">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="1a41a-358">參數：</span><span class="sxs-lookup"><span data-stu-id="1a41a-358">Parameters:</span></span>

| <span data-ttu-id="1a41a-359">名稱</span><span class="sxs-lookup"><span data-stu-id="1a41a-359">Name</span></span> | <span data-ttu-id="1a41a-360">描述</span><span class="sxs-lookup"><span data-stu-id="1a41a-360">Description</span></span> | <span data-ttu-id="1a41a-361">選用 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="1a41a-361">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="1a41a-362">-Identity</span><span class="sxs-lookup"><span data-stu-id="1a41a-362">-Identity</span></span>|<span data-ttu-id="1a41a-363">指定您要列出詳細資料的資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-363">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="1a41a-364">Y</span><span class="sxs-lookup"><span data-stu-id="1a41a-364">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="1a41a-365">取得原則指派資訊</span><span class="sxs-lookup"><span data-stu-id="1a41a-365">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="1a41a-366">描述：此 Cmdlet 會列出目前指派給承租人的原則。</span><span class="sxs-lookup"><span data-stu-id="1a41a-366">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="1a41a-367">從客戶金鑰脫離</span><span class="sxs-lookup"><span data-stu-id="1a41a-367">Offboarding from Customer Key</span></span>

<span data-ttu-id="1a41a-368">如果您需要回復至 Microsoft 受管理的金鑰，您可以。</span><span class="sxs-lookup"><span data-stu-id="1a41a-368">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="1a41a-369">當您下架時，會使用每個個別工作負載支援的預設加密來重新加密您的資料。</span><span class="sxs-lookup"><span data-stu-id="1a41a-369">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="1a41a-370">例如，Exchange Online 支援使用 Microsoft 管理金鑰的預設加密。</span><span class="sxs-lookup"><span data-stu-id="1a41a-370">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="1a41a-371">如果您決定在承租人層級從客戶機碼下架租使用者，請透過電子郵件要求 [停用] [m365ck@microsoft.com](mailto:m365ck@microsoft.com)的承租人服務。</span><span class="sxs-lookup"><span data-stu-id="1a41a-371">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to “disable” the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a41a-372">脫離會與資料清除相同。</span><span class="sxs-lookup"><span data-stu-id="1a41a-372">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="1a41a-373">資料清除會永久加密-從 Microsoft 365 刪除您組織的資料，而脫離不會。</span><span class="sxs-lookup"><span data-stu-id="1a41a-373">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="1a41a-374">您無法執行租使用者層級原則的資料清除。</span><span class="sxs-lookup"><span data-stu-id="1a41a-374">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="1a41a-375">如需資料清除路徑的詳細資訊，請參閱 [撤銷您的金鑰及開始資料清除路徑](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)程式。</span><span class="sxs-lookup"><span data-stu-id="1a41a-375">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="1a41a-376">關於可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="1a41a-376">About the availability key</span></span>

<span data-ttu-id="1a41a-377">如需可用性機碼的相關資訊，請參閱 [瞭解可用性金鑰](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="1a41a-377">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="1a41a-378">金鑰輪替</span><span class="sxs-lookup"><span data-stu-id="1a41a-378">Key rotation</span></span>

<span data-ttu-id="1a41a-379">如需隨客戶金鑰使用的旋轉或滾動機碼的相關資訊，請參閱 [滾或輪替客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)。</span><span class="sxs-lookup"><span data-stu-id="1a41a-379">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="1a41a-380">當您更新 DEP 以使用新版本的金鑰時，會執行 Set-M365DataAtRestEncryptionPolicy Cmdlet，如本文稍早所述。</span><span class="sxs-lookup"><span data-stu-id="1a41a-380">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1a41a-381">相關文章：</span><span class="sxs-lookup"><span data-stu-id="1a41a-381">Related articles:</span></span>

- [<span data-ttu-id="1a41a-382">客戶金鑰服務加密</span><span class="sxs-lookup"><span data-stu-id="1a41a-382">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="1a41a-383">滾動或旋轉客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="1a41a-383">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="1a41a-384">深入瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="1a41a-384">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="1a41a-385">服務加密</span><span class="sxs-lookup"><span data-stu-id="1a41a-385">Service Encryption</span></span>](office-365-service-encryption.md)
