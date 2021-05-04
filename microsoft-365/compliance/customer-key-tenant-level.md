---
title: 租用戶等級的 Microsoft 365 客戶金鑰 (公開預覽)
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
- m365solution-mip
- m365initiative-compliance
description: 瞭解如何在承租人層級的 Microsoft 365 內設定資料的客戶金鑰。
ms.openlocfilehash: 90ad08059d6b71583850368a70e32167b9defe88
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100792"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="f19ce-103"> (公開預覽的承租人層級 Microsoft 365 的客戶金鑰概述) </span><span class="sxs-lookup"><span data-stu-id="f19ce-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="f19ce-104">使用您提供的金鑰，您可以建立資料加密原則 (DEP) 並指派給租使用者。</span><span class="sxs-lookup"><span data-stu-id="f19ce-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="f19ce-105">您建立的租使用者型 DEP 會加密下列資料：</span><span class="sxs-lookup"><span data-stu-id="f19ce-105">The tenant-wide DEP you create encrypts the following data:</span></span>

- <span data-ttu-id="f19ce-106">Teams 聊天訊息 (1:1 聊天、群組交談、會議聊天及通道交談) </span><span class="sxs-lookup"><span data-stu-id="f19ce-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="f19ce-107">Teams 媒體訊息 (影像、程式碼片段、影片郵件、音訊訊息、wiki 影像) </span><span class="sxs-lookup"><span data-stu-id="f19ce-107">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="f19ce-108">Teams 儲存區中儲存的 Teams 通話和會議錄製</span><span class="sxs-lookup"><span data-stu-id="f19ce-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="f19ce-109">Teams 聊天通知</span><span class="sxs-lookup"><span data-stu-id="f19ce-109">Teams chat notifications</span></span>
- <span data-ttu-id="f19ce-110">使用 Cortana Teams 聊天建議</span><span class="sxs-lookup"><span data-stu-id="f19ce-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="f19ce-111">Teams 狀態郵件</span><span class="sxs-lookup"><span data-stu-id="f19ce-111">Teams status messages</span></span>
- <span data-ttu-id="f19ce-112">Exchange Online 的使用者和信號資訊</span><span class="sxs-lookup"><span data-stu-id="f19ce-112">User and signal information for Exchange Online</span></span>
- <span data-ttu-id="f19ce-113">Exchange Online 在應用層級沒有加密客戶金鑰 DEPs 的信箱</span><span class="sxs-lookup"><span data-stu-id="f19ce-113">Exchange Online mailboxes that aren't already encrypted Customer Key DEPs at the application level</span></span>
- <span data-ttu-id="f19ce-114">MIP exact data match (EDM) 資料– (資料檔案架構、規則套件和 salts 用來散列敏感性資料) </span><span class="sxs-lookup"><span data-stu-id="f19ce-114">MIP exact data match (EDM) data – (data file schemas, rule packages, and the salts used to hash the sensitive data)</span></span>

<span data-ttu-id="f19ce-115">針對 Microsoft 資訊保護和 Microsoft Teams，租使用者層級的客戶機碼會從您指派 DEP 給租使用者時，加密新的資料。</span><span class="sxs-lookup"><span data-stu-id="f19ce-115">For Microsoft Information Protection and Microsoft Teams, Customer Key at the tenant level encrypts new data from the time you assign the DEP to the tenant.</span></span> <span data-ttu-id="f19ce-116">公開預覽不支援加密過去的資料。</span><span class="sxs-lookup"><span data-stu-id="f19ce-116">Public preview doesn't support encrypting past data.</span></span> <span data-ttu-id="f19ce-117">針對 Exchange Online，客戶金鑰會加密所有現有和新的資料。</span><span class="sxs-lookup"><span data-stu-id="f19ce-117">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="f19ce-118">您可以為每個租使用者建立多個 DEPs，但一次只能指派一個 DEP。</span><span class="sxs-lookup"><span data-stu-id="f19ce-118">You can create multiple DEPs per tenant but can only assign one DEP at a time.</span></span> <span data-ttu-id="f19ce-119">當您指派 DEP 時，加密會自動開始，但需要一些時間才能完成，具體取決於您的承租人的大小。</span><span class="sxs-lookup"><span data-stu-id="f19ce-119">When you assign the DEP, encryption begins automatically but takes some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="f19ce-120">承租人層級原則新增更多控制至客戶機碼的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f19ce-120">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="f19ce-121">如果您已設定 Exchange Online 和 Sharepoint Online 的客戶機碼，以下是新租使用者層級公開預覽的方式。</span><span class="sxs-lookup"><span data-stu-id="f19ce-121">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="f19ce-122">您建立的承租人層級加密原則會加密 Microsoft Teams 中的所有資料，以及 Microsoft 365 中 Exchange Online 工作負載。</span><span class="sxs-lookup"><span data-stu-id="f19ce-122">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="f19ce-123">不過 Exchange Online，如果您已將客戶金鑰 DEPs 指派給個別信箱，則租使用者層級原則不會覆寫這些 DEPs。</span><span class="sxs-lookup"><span data-stu-id="f19ce-123">However, for Exchange Online, if you have already assigned Customer Key DEPs to individual mailboxes, the tenant-level policy won't override those DEPs.</span></span> <span data-ttu-id="f19ce-124">租使用者層級原則只會加密尚未指定信箱層級客戶金鑰 DEP 的信箱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-124">The tenant-level policy will only encrypt mailboxes that aren't assigned a mailbox level Customer Key DEP already.</span></span> <span data-ttu-id="f19ce-125">當您使用租使用者層級 DEP 加密使用者信箱時，其所有內容都會加密。</span><span class="sxs-lookup"><span data-stu-id="f19ce-125">When you encrypt a user mailbox using a tenant level DEP, all its content gets encrypted.</span></span> <span data-ttu-id="f19ce-126">如需在應用層級使用 DEP 加密的相關資訊，請參閱 [Service encryption With Customer Key](customer-key-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f19ce-126">For information about what gets encrypted with a DEP at the application level, see [Service encryption with Customer Key](customer-key-overview.md).</span></span>

## <a name="data-that-isnt-encrypted-with-customer-key-at-the-tenant-level"></a><span data-ttu-id="f19ce-127">未在租使用者層級使用客戶金鑰加密的資料</span><span class="sxs-lookup"><span data-stu-id="f19ce-127">Data that isn't encrypted with Customer Key at the tenant level</span></span>

<span data-ttu-id="f19ce-128">客戶機碼不會加密租使用者層級的下列資料類型。</span><span class="sxs-lookup"><span data-stu-id="f19ce-128">Customer Key doesn't encrypt the following types of data at the tenant level.</span></span> <span data-ttu-id="f19ce-129">相反地，Microsoft 365 會使用其他類型的加密來保護此資料。</span><span class="sxs-lookup"><span data-stu-id="f19ce-129">Instead, Microsoft 365 uses other types of encryption to protect this data.</span></span>

- <span data-ttu-id="f19ce-130">在應用層級上，使用客戶金鑰 DEP 已加密的線上信箱 Exchange。</span><span class="sxs-lookup"><span data-stu-id="f19ce-130">Exchange online mailboxes that you've already encrypted using a Customer Key DEP at the application level.</span></span> <span data-ttu-id="f19ce-131">未指派客戶金鑰 DEP 的信箱將會以租使用者層級 DEP 加密。</span><span class="sxs-lookup"><span data-stu-id="f19ce-131">Mailboxes that don't have a Customer Key DEP assigned to them will be encrypted using the tenant level DEP.</span></span> <span data-ttu-id="f19ce-132">這種相片順序表示您可以使用租使用者層級 DEP 來加密某些信箱，並使用應用層級 DEPs 加密某些信箱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-132">This arrangement means that you may have some mailboxes encrypted with a tenant level DEP and some mailboxes encrypted with application level DEPs.</span></span>
- <span data-ttu-id="f19ce-133">SharePoint 和商務用 OneDrive 在應用層級使用客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-133">SharePoint and OneDrive for Business use Customer Key at the application level.</span></span> <span data-ttu-id="f19ce-134">單一 DEP 會為單一地理位置的 SharePoint 加密內容。</span><span class="sxs-lookup"><span data-stu-id="f19ce-134">A single DEP encrypts content in SharePoint for a single geo.</span></span>
- <span data-ttu-id="f19ce-135">商務用 OneDrive 和 SharePoint 中儲存的 Microsoft Teams 檔案和部分 Teams 呼叫和會議錄製，都是由 SharePoint 線上 DEP 加密。</span><span class="sxs-lookup"><span data-stu-id="f19ce-135">Microsoft Teams files and some Teams call and meeting recordings saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span>

<span data-ttu-id="f19ce-136">Microsoft 365 之客戶機碼目前不支援的任何工作負載或案例。</span><span class="sxs-lookup"><span data-stu-id="f19ce-136">Any workloads or scenarios that aren't currently supported by Customer Key for Microsoft 365.</span></span>

- <span data-ttu-id="f19ce-137">其他 Microsoft 365 工作負載，例如 Yammer、Planner 等等。</span><span class="sxs-lookup"><span data-stu-id="f19ce-137">Other Microsoft 365 workloads such as Yammer, Planner, and so on.</span></span>
- <span data-ttu-id="f19ce-138">TeamsLive 事件和 Q&即時事件。</span><span class="sxs-lookup"><span data-stu-id="f19ce-138">Teams Live Events and Q&A in Live Events.</span></span> <span data-ttu-id="f19ce-139">針對 Teams，此案例是唯一不是由租使用者機碼在租使用者層級加密的案例。</span><span class="sxs-lookup"><span data-stu-id="f19ce-139">For Teams, this scenario is the only one that isn't encrypted by Customer Key at the tenant level.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="f19ce-140">在承租人層級設定客戶機碼 (公開預覽) </span><span class="sxs-lookup"><span data-stu-id="f19ce-140">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="f19ce-141">這些步驟類似，但與在應用層級設定客戶機碼的步驟並不相同。</span><span class="sxs-lookup"><span data-stu-id="f19ce-141">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="f19ce-142">請只搭配測試承租人中的測試資料使用此公開預覽。</span><span class="sxs-lookup"><span data-stu-id="f19ce-142">Only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="f19ce-143">請勿在生產資料或您的實際執行環境中使用此版本。</span><span class="sxs-lookup"><span data-stu-id="f19ce-143">Don't use this release with production data or in your production environment.</span></span> <span data-ttu-id="f19ce-144">如果您已具備客戶金鑰的實際執行部署，請使用下列步驟，在測試環境中的承租人層級設定客戶機碼。</span><span class="sxs-lookup"><span data-stu-id="f19ce-144">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span> <span data-ttu-id="f19ce-145">在您將租使用者層級 DEP 指派給租使用者之後，您可以開始驗證程式並與 m365ck@microsoft.com 聯繫，以提出任何問題或考慮。</span><span class="sxs-lookup"><span data-stu-id="f19ce-145">Once you've assigned a tenant level DEP to your tenant, you can start the validation process and contact m365ck@microsoft.com with any questions or concerns.</span></span> <span data-ttu-id="f19ce-146">您也可以在公開預覽中，在[Microsoft 365 的靜態資料加密的驗證指示](https://aka.ms/CustomerKey/PublicPreviewValidation)中，找到已記錄的驗證步驟。</span><span class="sxs-lookup"><span data-stu-id="f19ce-146">You can also find documented validation steps in the public preview of [Validation Instructions for Data-at-rest Encryption for Microsoft 365](https://aka.ms/CustomerKey/PublicPreviewValidation).</span></span>

<span data-ttu-id="f19ce-147">您可以遠端連線至 Azure PowerShell，以完成大部分的工作。</span><span class="sxs-lookup"><span data-stu-id="f19ce-147">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="f19ce-148">為了獲得最佳結果，請使用 Azure PowerShell 版本4.4.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="f19ce-148">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="f19ce-149">開始之前：</span><span class="sxs-lookup"><span data-stu-id="f19ce-149">Before you begin:</span></span>

- <span data-ttu-id="f19ce-150">您必須使用具有合規性系統管理員角色的工作或學校帳戶，以在租使用者層級設定客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-150">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="f19ce-151">確定您的組織有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="f19ce-151">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="f19ce-152">使用 Enterprise 合約或雲端服務提供者，以支付已開發票的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-152">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="f19ce-153">客戶機碼不支援使用「隨付」方案或信用卡使用信用卡購買的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-153">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="f19ce-154">從2020年4月1日起，在 Office 365 中提供客戶金鑰 Office 365 E5、Microsoft 365 E5、Microsoft 365 E5 合規性及 Microsoft 365 E5 資訊保護 & 控管 SKUs。</span><span class="sxs-lookup"><span data-stu-id="f19ce-154">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance, and Microsoft 365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="f19ce-155">Office 365 進階合規性SKU 已不再提供新的授權。</span><span class="sxs-lookup"><span data-stu-id="f19ce-155">Office 365 Advanced Compliance SKU is no longer available for new licenses.</span></span> <span data-ttu-id="f19ce-156">將繼續支援現有的 Office 365 進階合規性授權。</span><span class="sxs-lookup"><span data-stu-id="f19ce-156">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="f19ce-157">雖然租使用者必須至少有一個適當授權的使用者才能啟用服務，但您仍然應該確定所有從服務受益的使用者都有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="f19ce-157">While the service can be enabled with a minimum of one appropriately licensed user under the tenant, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="f19ce-158">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="f19ce-158">Create two new Azure subscriptions</span></span>

<span data-ttu-id="f19ce-159">客戶金鑰需要每個資料加密原則 (DEP) 的兩個金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-159">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="f19ce-160">若要建立兩個金鑰，您必須建立兩個 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-160">To create two keys, you must create two Azure subscriptions.</span></span> <span data-ttu-id="f19ce-161">建議的最佳作法是，您組織中的個別成員可以在每個訂閱中設定一個金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-161">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="f19ce-162">請只使用這些 Azure 訂閱來管理 Microsoft 365 的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-162">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="f19ce-163">遵循這些指導方針有助於保護您的組織，以防其中一個操作員意外、故意或惡意刪除，或 mismanages 其負責的金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-163">Following these guidelines helps protect your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="f19ce-164">您可以為組織建立的 Azure 訂閱數目沒有實際的限制。</span><span class="sxs-lookup"><span data-stu-id="f19ce-164">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="f19ce-165">遵循這項最佳作法可協助將「因人」錯誤所造成的影響降至最低，以協助管理客戶金鑰所使用的資源。</span><span class="sxs-lookup"><span data-stu-id="f19ce-165">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="f19ce-166">註冊 Azure 訂閱以使用強制保留期間</span><span class="sxs-lookup"><span data-stu-id="f19ce-166">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="f19ce-167">暫時或永久遺失根加密金鑰的功能可能會造成中斷，甚至可能造成資料遺失。</span><span class="sxs-lookup"><span data-stu-id="f19ce-167">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="f19ce-168">因此，與客戶金鑰搭配使用的資源需要加強保護。</span><span class="sxs-lookup"><span data-stu-id="f19ce-168">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="f19ce-169">與客戶金鑰搭配使用的所有 Azure 資源，除了預設設定之外，還提供保護機制。</span><span class="sxs-lookup"><span data-stu-id="f19ce-169">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="f19ce-170">您可以使用 Azure 訂閱進行標記或註冊，以防止立即和不可撤銷的取消。</span><span class="sxs-lookup"><span data-stu-id="f19ce-170">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="f19ce-171">此程式稱為註冊強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="f19ce-171">This process is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="f19ce-172">在必要保留期間內註冊 Azure 訂閱所需的步驟，必須與 Microsoft 共同作業。</span><span class="sxs-lookup"><span data-stu-id="f19ce-172">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="f19ce-173">此程式最多可長達五個工作日。</span><span class="sxs-lookup"><span data-stu-id="f19ce-173">This process can take up to five business days.</span></span> <span data-ttu-id="f19ce-174">先前，此程式有時稱為「不要取消」。</span><span class="sxs-lookup"><span data-stu-id="f19ce-174">Previously, this process was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="f19ce-175">在聯繫 Microsoft 365 小組之前，您必須針對每個搭配客戶金鑰使用的 Azure 訂閱執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="f19ce-175">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="f19ce-176">開始之前，請確定您已安裝[Azure PowerShell Az](/powershell/azure/new-azureps-module-az)模組。</span><span class="sxs-lookup"><span data-stu-id="f19ce-176">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="f19ce-177">使用 Azure PowerShell 登入。</span><span class="sxs-lookup"><span data-stu-id="f19ce-177">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="f19ce-178">如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="f19ce-178">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="f19ce-179">執行 Register-AzProviderFeature Cmdlet 註冊您的訂閱，以使用強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="f19ce-179">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="f19ce-180">針對每個訂閱執行此動作。</span><span class="sxs-lookup"><span data-stu-id="f19ce-180">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="f19ce-181">請與 Microsoft 聯繫以在 [m365ck@microsoft.com](mailto:m365ck@microsoft.com)完成此程式。</span><span class="sxs-lookup"><span data-stu-id="f19ce-181">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="f19ce-182">在您的電子郵件中包含下列內容：</span><span class="sxs-lookup"><span data-stu-id="f19ce-182">Include the following content in your email:</span></span>

   <span data-ttu-id="f19ce-183">主旨 **：客戶** 金鑰\<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="f19ce-183">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="f19ce-184">**Body**：訂閱 IDs，您想要完成其強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="f19ce-184">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="f19ce-185">每個訂閱的 Get-AzProviderFeature 輸出。</span><span class="sxs-lookup"><span data-stu-id="f19ce-185">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="f19ce-186">完成此程式的服務等級協定 (SLA) 一天之後，Microsoft 會 (通知您已註冊訂閱，) 您已註冊訂閱，以使用強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="f19ce-186">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="f19ce-187">當您收到來自 Microsoft 的通知，表明已完成註冊後，請執行 Get-AzProviderFeature 命令，按下列方式，以確認註冊的狀態。</span><span class="sxs-lookup"><span data-stu-id="f19ce-187">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="f19ce-188">若驗證，Get-AzProviderFeature 命令會傳回登錄 **狀態** 屬性的 **註冊** 值。</span><span class="sxs-lookup"><span data-stu-id="f19ce-188">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="f19ce-189">針對每個訂閱執行此動作。</span><span class="sxs-lookup"><span data-stu-id="f19ce-189">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="f19ce-190">若要完成此程式，請執行 Register-AzResourceProvider 命令。</span><span class="sxs-lookup"><span data-stu-id="f19ce-190">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="f19ce-191">針對每個訂閱執行此動作。</span><span class="sxs-lookup"><span data-stu-id="f19ce-191">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="f19ce-192">在每個訂閱中建立高級 Azure 金鑰 Vault</span><span class="sxs-lookup"><span data-stu-id="f19ce-192">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="f19ce-193">建立主要 vault 的步驟會在[開始使用 Azure key vault](/azure/key-vault/general/overview)時記錄下來，可引導您完成安裝和啟動 Azure PowerShell、連線至 Azure 訂閱、建立資源群組，以及在該資源群組中建立金鑰 vault。</span><span class="sxs-lookup"><span data-stu-id="f19ce-193">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="f19ce-194">當您建立金鑰 vault 時，您必須選擇 SKU： [標準] 或 [進階版]。</span><span class="sxs-lookup"><span data-stu-id="f19ce-194">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="f19ce-195">Standard SKU 允許使用軟體來保護 Azure 金鑰 Vault 金鑰-沒有硬體安全性模組 (HSM) 金鑰保護-而且進階版 SKU 允許使用 Hsm 來保護主要 Vault 金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-195">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="f19ce-196">客戶金鑰可接受使用任一 SKU 的金鑰電子倉庫，但 Microsoft 強烈建議您只使用進階版 sku。</span><span class="sxs-lookup"><span data-stu-id="f19ce-196">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="f19ce-197">使用任何一種類型之機碼的作業成本是相同的，所以每個受 HSM 保護的金鑰只會有每個月的成本差異。</span><span class="sxs-lookup"><span data-stu-id="f19ce-197">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="f19ce-198">如需詳細資訊，請參閱 [主要 Vault 定價](https://azure.microsoft.com/pricing/details/key-vault/) 。</span><span class="sxs-lookup"><span data-stu-id="f19ce-198">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f19ce-199">針對實際執行資料使用進階版 SKU 金鑰保存庫和受保護金鑰的金鑰，只使用標準的 SKU 金鑰保管，以進行測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="f19ce-199">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="f19ce-200">使用主要保管區的一般前置詞，並包含主要 vault 和機碼的使用和範圍的縮寫。</span><span class="sxs-lookup"><span data-stu-id="f19ce-200">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="f19ce-201">例如，針對存放庫在北美的 Contoso 服務，可能的名稱成對為 Contoso-O365-NA-VaultA1 和 Contoso-O365-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="f19ce-201">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="f19ce-202">保存庫名稱是 Azure 內全域唯一的字串，因此，您可能需要嘗試所需名稱的變化，以防其他 Azure 客戶已索取所需的名稱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-202">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="f19ce-203">設定後，就無法變更保存庫名稱，因此最佳作法是設定安裝的書面計畫，然後使用第二個人驗證計畫是否正確執行。</span><span class="sxs-lookup"><span data-stu-id="f19ce-203">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="f19ce-204">如果可能，請在非成對區域中建立您的電子倉庫。</span><span class="sxs-lookup"><span data-stu-id="f19ce-204">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="f19ce-205">配對的 Azure 區域可提供跨服務失敗網域的高可用性。</span><span class="sxs-lookup"><span data-stu-id="f19ce-205">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="f19ce-206">因此，區域配對可以視為彼此的備份區域。</span><span class="sxs-lookup"><span data-stu-id="f19ce-206">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="f19ce-207">位於某個地區的 Azure 資源會透過成對區域自動取得容錯。</span><span class="sxs-lookup"><span data-stu-id="f19ce-207">An Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="f19ce-208">在地區是成對的資料加密原則中，選擇用於兩個電子倉庫的地區，這表示僅有兩個可用區域的可用性。</span><span class="sxs-lookup"><span data-stu-id="f19ce-208">Choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="f19ce-209">大多數地理有兩個地區，所以尚不能選取非成對區域。</span><span class="sxs-lookup"><span data-stu-id="f19ce-209">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="f19ce-210">如有可能，請選擇兩個不成對的區域，以用於資料加密原則的兩個保存庫。</span><span class="sxs-lookup"><span data-stu-id="f19ce-210">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="f19ce-211">此案例的主要優點是共有四個地區的可用性。</span><span class="sxs-lookup"><span data-stu-id="f19ce-211">This scenario benefits from a total of four regions of availability.</span></span> <span data-ttu-id="f19ce-212">如需詳細資訊，請參閱 [Business 持續性和嚴重損壞修復 (BCDR) ： Azure 成對區域](/azure/best-practices-availability-paired-regions) 的目前區域配對清單。</span><span class="sxs-lookup"><span data-stu-id="f19ce-212">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="f19ce-213">將許可權指派給每個金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="f19ce-213">Assign permissions to each key vault</span></span>

<span data-ttu-id="f19ce-214">針對每個金鑰保存庫，您必須根據您的實施，為客戶機碼定義三組不同的許可權。</span><span class="sxs-lookup"><span data-stu-id="f19ce-214">For each key vault, you'll need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="f19ce-215">例如，您必須為下列各項定義一組許可權：</span><span class="sxs-lookup"><span data-stu-id="f19ce-215">For example, you'll need to define one set of permissions for each of these:</span></span>
  
- <span data-ttu-id="f19ce-216">**主要 vault 系統管理員** ，會針對您的組織執行重要 vault 的日常管理。</span><span class="sxs-lookup"><span data-stu-id="f19ce-216">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="f19ce-217">這些工作包括備份、建立、取得、匯入、清單及還原。</span><span class="sxs-lookup"><span data-stu-id="f19ce-217">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="f19ce-218">指派給主要 vault 管理員的許可權集不包含刪除金鑰的許可權。</span><span class="sxs-lookup"><span data-stu-id="f19ce-218">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="f19ce-219">這是故意和重要的作法。</span><span class="sxs-lookup"><span data-stu-id="f19ce-219">This is intentional and an important practice.</span></span> <span data-ttu-id="f19ce-220">刪除加密金鑰通常不會這麼做，因為這樣做會永久銷毀資料。</span><span class="sxs-lookup"><span data-stu-id="f19ce-220">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="f19ce-221">根據預設，請勿將此許可權授與主要 vault 管理員的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="f19ce-221">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="f19ce-222">相反地，針對主要 vault 投稿人保留這種情況，而且只要清楚瞭解對結果的瞭解，就只需在短期內將其指派給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f19ce-222">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="f19ce-223">若要將這些許可權指派給組織中的使用者，請使用 Azure PowerShell 登入您的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-223">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="f19ce-224">如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="f19ce-224">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="f19ce-225">執行 Set-AzKeyVaultAccessPolicy Cmdlet 指派必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="f19ce-225">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="f19ce-226">例如:</span><span class="sxs-lookup"><span data-stu-id="f19ce-226">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="f19ce-227">可以變更 Azure Key Vault 自身許可權的 **主要 vault 參與者**。</span><span class="sxs-lookup"><span data-stu-id="f19ce-227">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="f19ce-228">您必須變更這些許可權，因為員工離職或加入您的小組，或是主要 vault 管理員合法需要刪除或還原機碼的少數情況。</span><span class="sxs-lookup"><span data-stu-id="f19ce-228">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="f19ce-229">這組重要的 vault 投稿人員必須授與主要 vault 上的投稿人角色。</span><span class="sxs-lookup"><span data-stu-id="f19ce-229">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="f19ce-230">您可以使用 Azure 資源管理員指派此角色。</span><span class="sxs-lookup"><span data-stu-id="f19ce-230">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="f19ce-231">如需詳細步驟，請參閱 [Use Role-Based Access Control](/azure/active-directory/role-based-access-control-configure) ，以管理您的 Azure 訂閱資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="f19ce-231">For detailed steps, see [Use Role-Based Access Control](/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="f19ce-232">建立訂閱的系統管理員預設具有這種存取權，以及將其他管理員指派給參與者角色的能力。</span><span class="sxs-lookup"><span data-stu-id="f19ce-232">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="f19ce-233">Microsoft 365 在租使用者層級為客戶金鑰運作之 **靜態加密服務的資料**。</span><span class="sxs-lookup"><span data-stu-id="f19ce-233">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="f19ce-234">若要授與 Microsoft 365 的許可權，請使用下列語法執行 **AzKeyVaultAccessPolicy** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f19ce-234">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="f19ce-235">其中：</span><span class="sxs-lookup"><span data-stu-id="f19ce-235">Where:</span></span>

  - <span data-ttu-id="f19ce-236">*保存庫名稱* 是您建立的主要 vault 名稱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-236">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="f19ce-237">範例：針對 Rest 加密服務的 Microsoft 365 資料，取代 *Microsoft 365 appID* 與`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="f19ce-237">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="f19ce-238">在金鑰保存庫上啟用然後確認虛刪除</span><span class="sxs-lookup"><span data-stu-id="f19ce-238">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="f19ce-239">當您可以快速復原金鑰時，由於意外或惡意刪除的金鑰，您很可能會因意外或惡意刪除的金鑰而經歷長時間的服務中斷。</span><span class="sxs-lookup"><span data-stu-id="f19ce-239">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="f19ce-240">啟用此設定（稱為「虛刪除」），才能搭配客戶機碼使用金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-240">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="f19ce-241">啟用 [虛刪除] 可讓您在刪除90天內復原金鑰或存放庫，而不需要從備份中還原。</span><span class="sxs-lookup"><span data-stu-id="f19ce-241">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="f19ce-242">若要在金鑰保存庫上啟用虛刪除，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f19ce-242">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="f19ce-243">使用 Windows PowerShell 登入您的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-243">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="f19ce-244">如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="f19ce-244">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="f19ce-245">執行 [AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f19ce-245">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="f19ce-246">在此範例中， *保存庫名稱* 是您要啟用 soft delete 之主要 vault 的名稱：</span><span class="sxs-lookup"><span data-stu-id="f19ce-246">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="f19ce-247">執行 **AzKeyVault** 指令程式，確認已為金鑰保存庫設定 soft delete。</span><span class="sxs-lookup"><span data-stu-id="f19ce-247">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="f19ce-248">如果已正確設定 key vault 的 [虛刪除]，則 _Soft Delete Enabled_ 屬性會傳回 **True** 值：</span><span class="sxs-lookup"><span data-stu-id="f19ce-248">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="f19ce-249">透過建立或匯入機碼，將機碼新增到每個機碼 vault</span><span class="sxs-lookup"><span data-stu-id="f19ce-249">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="f19ce-250">有兩種方法可以將機碼新增到 Azure Key Vault;您可以直接在 Key Vault 中建立金鑰，也可以匯入金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-250">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="f19ce-251">直接在 Key Vault 中建立金鑰是不夠複雜的方法，而匯入金鑰會提供如何產生機碼的整體控制權。</span><span class="sxs-lookup"><span data-stu-id="f19ce-251">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="f19ce-252">使用 RSA 機碼。</span><span class="sxs-lookup"><span data-stu-id="f19ce-252">Use the RSA keys.</span></span> <span data-ttu-id="f19ce-253">Azure 金鑰 Vault 不支援使用橢圓曲線鍵進行換行及解換。</span><span class="sxs-lookup"><span data-stu-id="f19ce-253">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="f19ce-254">若要直接在金鑰保存庫中建立金鑰，請執行 AzKeyVaultKey 指令 [程式](/powershell/module/az.keyvault/add-azkeyvaultkey) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f19ce-254">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="f19ce-255">其中：</span><span class="sxs-lookup"><span data-stu-id="f19ce-255">Where:</span></span>

- <span data-ttu-id="f19ce-256">*vault 名稱* 是您要在其中建立機碼的金鑰 vault 名稱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-256">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="f19ce-257">*key name* 是您要給予新機碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-257">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="f19ce-258">使用主要保險檔的上述命名慣例，以前面所述的名稱慣例命名機碼。</span><span class="sxs-lookup"><span data-stu-id="f19ce-258">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="f19ce-259">如此一來，在僅顯示金鑰名稱的工具中，該字串是自我描述的。</span><span class="sxs-lookup"><span data-stu-id="f19ce-259">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="f19ce-260">如果您想要使用 HSM 來保護機碼，請確定您將 **hsm** 指定為 _Destination_ 參數的值，否則請指定 **軟體**。</span><span class="sxs-lookup"><span data-stu-id="f19ce-260">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="f19ce-261">例如：</span><span class="sxs-lookup"><span data-stu-id="f19ce-261">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="f19ce-262">檢查機碼的恢復層級</span><span class="sxs-lookup"><span data-stu-id="f19ce-262">Check the recovery level of your keys</span></span>

<span data-ttu-id="f19ce-263">Microsoft 365 要求 Azure Key Vault 訂閱設定為 [請勿取消]，且客戶機碼使用的金鑰已啟用 [虛刪除]。</span><span class="sxs-lookup"><span data-stu-id="f19ce-263">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="f19ce-264">您可以查看金鑰上的復原層級，以確認這些設定。</span><span class="sxs-lookup"><span data-stu-id="f19ce-264">You can confirm these settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="f19ce-265">若要檢查機碼的復原層級，請在 Azure PowerShell 中執行 Get-AzKeyVaultKey Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f19ce-265">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="f19ce-266">若 _Recovery Level_ 屬性傳回的值不是可復原的 **+ ProtectedSubscription**，您必須查看這篇文章，並確定您已遵循將訂閱置於 [不要取消] 清單中的所有步驟，以及您已在每個主要存放庫上啟用「虛刪除」。</span><span class="sxs-lookup"><span data-stu-id="f19ce-266">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="f19ce-267">接下來，將電子郵件輸出的螢幕擷取畫面傳送 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` 至 m365ck@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="f19ce-267">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="f19ce-268">備份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="f19ce-268">Back up Azure Key Vault</span></span>

<span data-ttu-id="f19ce-269">立即建立或變更機碼，然後備份機碼，並在線上及離線的情況下，儲存備份的副本。</span><span class="sxs-lookup"><span data-stu-id="f19ce-269">Immediately following creation or any change to a key, back up the key and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="f19ce-270">不要將離線副本連線到任何網路。</span><span class="sxs-lookup"><span data-stu-id="f19ce-270">Don't connect offline copies to any network.</span></span> <span data-ttu-id="f19ce-271">請改為將它們儲存在實體安全或商業儲存設施中。</span><span class="sxs-lookup"><span data-stu-id="f19ce-271">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="f19ce-272">至少應有一個備份副本儲存在發生嚴重損壞時可存取的位置。</span><span class="sxs-lookup"><span data-stu-id="f19ce-272">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="f19ce-273">備份 blob 是一種還原重要材料的唯一方法，應永久銷毀主要 Vault 金鑰，否則無法使用。</span><span class="sxs-lookup"><span data-stu-id="f19ce-273">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="f19ce-274">Azure Key Vault 外部的金鑰和匯入到 Azure Key Vault 的金鑰，不會做為備份的限制，因為客戶金鑰使用金鑰所需的中繼資料並不存在於外部金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-274">Keys that are external to Azure Key Vault and were imported to Azure Key Vault don't qualify as a backup because the metadata necessary for Customer Key to use the key doesn't exist with the external key.</span></span> <span data-ttu-id="f19ce-275">只有從 Azure 金鑰保存庫取得的備份可用於使用客戶金鑰進行還原作業。</span><span class="sxs-lookup"><span data-stu-id="f19ce-275">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="f19ce-276">所以，您必須在上傳或建立金鑰時進行 Azure 金鑰保存庫備份。</span><span class="sxs-lookup"><span data-stu-id="f19ce-276">So, it's essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="f19ce-277">若要建立 Azure Key Vault 機碼的備份，請執行 [AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f19ce-277">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="f19ce-278">確定您的輸出檔案使用尾碼 `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="f19ce-278">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="f19ce-279">由此 Cmdlet 所產生的輸出檔已加密，且無法用於 Azure Key Vault 之外。</span><span class="sxs-lookup"><span data-stu-id="f19ce-279">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="f19ce-280">備份只能還原至執行備份的來源 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-280">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="f19ce-281">例如:</span><span class="sxs-lookup"><span data-stu-id="f19ce-281">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="f19ce-282">驗證 Azure 金鑰 Vault 設定設定</span><span class="sxs-lookup"><span data-stu-id="f19ce-282">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="f19ce-283">在 DEP 中使用金鑰之前執行驗證是選用的，但是強烈建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="f19ce-283">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="f19ce-284">尤其是，如果您使用步驟來設定您的金鑰和保險庫（如本主題所述），您應該先驗證 Azure 金鑰 Vault 資源的健康情況，再設定客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="f19ce-284">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="f19ce-285">若要確認您的機碼已啟用 get、wrapKey 及 unwrapKey 作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f19ce-285">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="f19ce-286">執行 [AzKeyVault 指令程式](/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f19ce-286">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="f19ce-287">在 [輸出] 中，視需要查看存取原則及 Microsoft 365 應用程式識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="f19ce-287">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="f19ce-288">所有三個作業、get、wrapKey 及 unwrapKey 都必須顯示在 [索引鍵的許可權] 底下。</span><span class="sxs-lookup"><span data-stu-id="f19ce-288">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="f19ce-289">如果存取原則設定不正確，請執行 Set-AzKeyVaultAccessPolicy Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f19ce-289">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="f19ce-290">範例：針對 Rest 加密服務的 Microsoft 365 資料，取代 *Microsoft 365 appID* 與`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="f19ce-290">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="f19ce-291">若要確認沒有為您的金鑰設定到期日，請執行 [AzKeyVaultKey 指令程式](/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f19ce-291">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="f19ce-292">已到期的金鑰無法由客戶金鑰使用，而且嘗試使用到期金鑰會失敗，而且可能會造成服務中斷。</span><span class="sxs-lookup"><span data-stu-id="f19ce-292">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="f19ce-293">強烈建議使用與客戶金鑰搭配使用的金鑰沒有到期日。</span><span class="sxs-lookup"><span data-stu-id="f19ce-293">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="f19ce-294">到期日一經設定，便無法移除，但可以變更為不同的日期。</span><span class="sxs-lookup"><span data-stu-id="f19ce-294">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="f19ce-295">如果必須使用具有到期日期設定的金鑰，請將 [到期] 值變更為12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="f19ce-295">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="f19ce-296">到期日期設定為12/31/9999 以外的日期，將不會通過 Microsoft 365 驗證。</span><span class="sxs-lookup"><span data-stu-id="f19ce-296">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="f19ce-297">若要變更已設定為12/31/9999 以外任何值的到期日，請執行 AzKeyVaultKey 指令 [程式](/powershell/module/az.keyvault/update-azkeyvaultkey) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f19ce-297">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="f19ce-298">取得每個 Azure 金鑰保存庫機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="f19ce-298">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="f19ce-299">當您在 Azure 中完成所有步驟以設定金鑰保存庫並新增金鑰之後，請執行下列命令，以取得每個 key vault 中的金鑰的 URI。</span><span class="sxs-lookup"><span data-stu-id="f19ce-299">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="f19ce-300">當您稍後建立並指派每個 DEP 時，您將需要使用這些 URIs，因此請將此資訊儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="f19ce-300">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="f19ce-301">請記得對每一個按鍵 vault 執行一次此指令。</span><span class="sxs-lookup"><span data-stu-id="f19ce-301">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="f19ce-302">在 Azure PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="f19ce-302">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="f19ce-303">為您的租使用者設定客戶金鑰加密原則</span><span class="sxs-lookup"><span data-stu-id="f19ce-303">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="f19ce-304">您必須已獲指派許可權，才能執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f19ce-304">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="f19ce-305">雖然這篇文章列出指令程式的所有參數，但如果不包含在指派給您的許可權中，您可能無法存取某些參數。</span><span class="sxs-lookup"><span data-stu-id="f19ce-305">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="f19ce-306">若要尋找在組織中執行任何 Cmdlet 或參數所需的權限，請參閱 [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)。</span><span class="sxs-lookup"><span data-stu-id="f19ce-306">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="f19ce-307">建立原則</span><span class="sxs-lookup"><span data-stu-id="f19ce-307">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

<span data-ttu-id="f19ce-308">描述：使用兩個 AKV 根機碼，啟用相容性管理員以建立新的資料加密原則 (DEP) 。</span><span class="sxs-lookup"><span data-stu-id="f19ce-308">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="f19ce-309">一旦建立後，便可使用 Set-M365DataAtRestEncryptionPolicyAssignment Cmdlet 指派原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-309">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="f19ce-310">在初次指派按鍵或旋轉按鍵後，新的機碼可能需要長達24小時才會生效。</span><span class="sxs-lookup"><span data-stu-id="f19ce-310">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="f19ce-311">如果新的 DEP 需要24小時以上才能生效，請與 Microsoft 聯繫。</span><span class="sxs-lookup"><span data-stu-id="f19ce-311">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="f19ce-312">範例：</span><span class="sxs-lookup"><span data-stu-id="f19ce-312">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="f19ce-313">參數：</span><span class="sxs-lookup"><span data-stu-id="f19ce-313">Parameters:</span></span>

| <span data-ttu-id="f19ce-314">名稱</span><span class="sxs-lookup"><span data-stu-id="f19ce-314">Name</span></span> | <span data-ttu-id="f19ce-315">描述</span><span class="sxs-lookup"><span data-stu-id="f19ce-315">Description</span></span> | <span data-ttu-id="f19ce-316">選用 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="f19ce-316">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="f19ce-317">名稱</span><span class="sxs-lookup"><span data-stu-id="f19ce-317">Name</span></span>|<span data-ttu-id="f19ce-318">資料加密原則的易記名稱</span><span class="sxs-lookup"><span data-stu-id="f19ce-318">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="f19ce-319">N</span><span class="sxs-lookup"><span data-stu-id="f19ce-319">N</span></span>|
|<span data-ttu-id="f19ce-320">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="f19ce-320">AzureKeyIDs</span></span>|<span data-ttu-id="f19ce-321">指定 Azure Key Vault 機碼的兩個 URI 值，以逗號分隔，以與資料加密原則產生關聯</span><span class="sxs-lookup"><span data-stu-id="f19ce-321">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="f19ce-322">N</span><span class="sxs-lookup"><span data-stu-id="f19ce-322">N</span></span>|
|<span data-ttu-id="f19ce-323">描述</span><span class="sxs-lookup"><span data-stu-id="f19ce-323">Description</span></span>|<span data-ttu-id="f19ce-324">資料加密原則的描述</span><span class="sxs-lookup"><span data-stu-id="f19ce-324">Description of the data encryption policy</span></span>|<span data-ttu-id="f19ce-325">N</span><span class="sxs-lookup"><span data-stu-id="f19ce-325">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="f19ce-326">指派原則</span><span class="sxs-lookup"><span data-stu-id="f19ce-326">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

<span data-ttu-id="f19ce-327">描述：此指令程式用於設定預設資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-327">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="f19ce-328">這個原則將用來加密所有支援工作負載中的資料。</span><span class="sxs-lookup"><span data-stu-id="f19ce-328">This policy will be used to then encrypt data across all support workloads.</span></span>

<span data-ttu-id="f19ce-329">範例：</span><span class="sxs-lookup"><span data-stu-id="f19ce-329">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

<span data-ttu-id="f19ce-330">參數：</span><span class="sxs-lookup"><span data-stu-id="f19ce-330">Parameters:</span></span>

| <span data-ttu-id="f19ce-331">名稱</span><span class="sxs-lookup"><span data-stu-id="f19ce-331">Name</span></span> | <span data-ttu-id="f19ce-332">描述</span><span class="sxs-lookup"><span data-stu-id="f19ce-332">Description</span></span> | <span data-ttu-id="f19ce-333">選用 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="f19ce-333">Optional (Y/N)</span></span> |
|----------|----------|---------|
<span data-ttu-id="f19ce-334">-DataEncryptionPolicy</span><span class="sxs-lookup"><span data-stu-id="f19ce-334">-DataEncryptionPolicy</span></span>|<span data-ttu-id="f19ce-335">指定需要指派的資料加密原則;請指定原則名稱或原則識別碼。</span><span class="sxs-lookup"><span data-stu-id="f19ce-335">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="f19ce-336">N</span><span class="sxs-lookup"><span data-stu-id="f19ce-336">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="f19ce-337">修改或重新整理原則</span><span class="sxs-lookup"><span data-stu-id="f19ce-337">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="f19ce-338">描述：此 Cmdlet 可用於修改或重新整理現有的原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-338">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="f19ce-339">也可以用來啟用或停用原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-339">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="f19ce-340">在初次指派按鍵或旋轉按鍵後，新的機碼可能需要長達24小時才會生效。</span><span class="sxs-lookup"><span data-stu-id="f19ce-340">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="f19ce-341">如果新的 DEP 需要24小時以上才能生效，請與 Microsoft 聯繫。</span><span class="sxs-lookup"><span data-stu-id="f19ce-341">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="f19ce-342">範例：</span><span class="sxs-lookup"><span data-stu-id="f19ce-342">Examples:</span></span>

<span data-ttu-id="f19ce-343">停用資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-343">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="f19ce-344">重新整理資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-344">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

<span data-ttu-id="f19ce-345">參數：</span><span class="sxs-lookup"><span data-stu-id="f19ce-345">Parameters:</span></span>

| <span data-ttu-id="f19ce-346">名稱</span><span class="sxs-lookup"><span data-stu-id="f19ce-346">Name</span></span> | <span data-ttu-id="f19ce-347">描述</span><span class="sxs-lookup"><span data-stu-id="f19ce-347">Description</span></span> | <span data-ttu-id="f19ce-348">選用 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="f19ce-348">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="f19ce-349">-Identity</span><span class="sxs-lookup"><span data-stu-id="f19ce-349">-Identity</span></span>|<span data-ttu-id="f19ce-350">指定您要修改的資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-350">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="f19ce-351">N</span><span class="sxs-lookup"><span data-stu-id="f19ce-351">N</span></span>|
|<span data-ttu-id="f19ce-352">-重新整理</span><span class="sxs-lookup"><span data-stu-id="f19ce-352">-Refresh</span></span>|<span data-ttu-id="f19ce-353">在您旋轉 Azure Key Vault 中的任何相關機碼之後，請使用重新整理參數來更新資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-353">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="f19ce-354">您不需要使用此參數指定值。</span><span class="sxs-lookup"><span data-stu-id="f19ce-354">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="f19ce-355">Y</span><span class="sxs-lookup"><span data-stu-id="f19ce-355">Y</span></span>|
|<span data-ttu-id="f19ce-356">-已啟用</span><span class="sxs-lookup"><span data-stu-id="f19ce-356">-Enabled</span></span>|<span data-ttu-id="f19ce-357">Enabled 參數會啟用或停用資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-357">The Enabled parameter enables or disables the data encryption policy.</span></span> <span data-ttu-id="f19ce-358">停用原則之前，必須先將其指派給您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="f19ce-358">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="f19ce-359">有效值為：</span><span class="sxs-lookup"><span data-stu-id="f19ce-359">Valid values are:</span></span></br > <span data-ttu-id="f19ce-360">$true：已啟用原則</span><span class="sxs-lookup"><span data-stu-id="f19ce-360">$true: The policy is enabled</span></span></br > <span data-ttu-id="f19ce-361">$true：已啟用原則。此為預設值。</span><span class="sxs-lookup"><span data-stu-id="f19ce-361">$false: The policy is disabled.</span></span>|<span data-ttu-id="f19ce-362">Y</span><span class="sxs-lookup"><span data-stu-id="f19ce-362">Y</span></span>|
|<span data-ttu-id="f19ce-363">-名稱</span><span class="sxs-lookup"><span data-stu-id="f19ce-363">-Name</span></span>|<span data-ttu-id="f19ce-364">Name 參數會指定資料加密原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="f19ce-364">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="f19ce-365">Y</span><span class="sxs-lookup"><span data-stu-id="f19ce-365">Y</span></span>|
|<span data-ttu-id="f19ce-366">-描述</span><span class="sxs-lookup"><span data-stu-id="f19ce-366">-Description</span></span>|<span data-ttu-id="f19ce-367">Description 參數會指定資料加密原則的選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="f19ce-367">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="f19ce-368">Y</span><span class="sxs-lookup"><span data-stu-id="f19ce-368">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="f19ce-369">取得原則詳細資料</span><span class="sxs-lookup"><span data-stu-id="f19ce-369">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="f19ce-370">描述：此 Cmdlet 會列出針對租使用者或特定原則的詳細資料所建立的所有 M365DataAtRest 加密原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-370">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="f19ce-371">範例：</span><span class="sxs-lookup"><span data-stu-id="f19ce-371">Examples:</span></span>

<span data-ttu-id="f19ce-372">此範例會傳回組織中 M365DatAtRest 加密原則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="f19ce-372">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="f19ce-373">此範例會傳回名為 "名稱 Policy" 的資料加密原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f19ce-373">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="f19ce-374">參數：</span><span class="sxs-lookup"><span data-stu-id="f19ce-374">Parameters:</span></span>

| <span data-ttu-id="f19ce-375">名稱</span><span class="sxs-lookup"><span data-stu-id="f19ce-375">Name</span></span> | <span data-ttu-id="f19ce-376">描述</span><span class="sxs-lookup"><span data-stu-id="f19ce-376">Description</span></span> | <span data-ttu-id="f19ce-377">選用 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="f19ce-377">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="f19ce-378">-Identity</span><span class="sxs-lookup"><span data-stu-id="f19ce-378">-Identity</span></span>|<span data-ttu-id="f19ce-379">指定您要列出詳細資料的資料加密原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-379">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="f19ce-380">Y</span><span class="sxs-lookup"><span data-stu-id="f19ce-380">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="f19ce-381">取得原則指派資訊</span><span class="sxs-lookup"><span data-stu-id="f19ce-381">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="f19ce-382">描述：此 Cmdlet 會列出目前指派給承租人的原則。</span><span class="sxs-lookup"><span data-stu-id="f19ce-382">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key-at-the-tenant-level"></a><span data-ttu-id="f19ce-383">從承租人層級的客戶機碼脫離</span><span class="sxs-lookup"><span data-stu-id="f19ce-383">Offboarding from Customer Key at the tenant level</span></span>

<span data-ttu-id="f19ce-384">如果您需要回復至 Microsoft 受管理的金鑰，您可以。</span><span class="sxs-lookup"><span data-stu-id="f19ce-384">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="f19ce-385">當您下架時，會使用每個個別工作負載支援的預設加密來重新加密您的資料。</span><span class="sxs-lookup"><span data-stu-id="f19ce-385">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="f19ce-386">例如，Exchange Online 支援使用 Microsoft 管理金鑰的預設加密。</span><span class="sxs-lookup"><span data-stu-id="f19ce-386">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="f19ce-387">如果您決定從承租人層級的客戶機碼下架您的租使用者，請以電子郵件 [m365ck@microsoft.com](mailto:m365ck@microsoft.com) 要求為「停用」承租人的服務。</span><span class="sxs-lookup"><span data-stu-id="f19ce-387">If you decide to offboard your tenant from Customer Key at the tenant level, email [m365ck@microsoft.com](mailto:m365ck@microsoft.com) with a request to "disable" the service for the tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f19ce-388">脫離會與資料清除相同。</span><span class="sxs-lookup"><span data-stu-id="f19ce-388">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="f19ce-389">資料清除會永久加密-從 Microsoft 365 中刪除組織的資料，而脫離。</span><span class="sxs-lookup"><span data-stu-id="f19ce-389">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="f19ce-390">您無法執行租使用者層級原則的資料清除。</span><span class="sxs-lookup"><span data-stu-id="f19ce-390">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="f19ce-391">如需資料清除路徑的詳細資訊，請參閱 [撤銷您的金鑰及開始資料清除路徑](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)程式。</span><span class="sxs-lookup"><span data-stu-id="f19ce-391">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="f19ce-392">關於可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="f19ce-392">About the availability key</span></span>

<span data-ttu-id="f19ce-393">如需可用性機碼的相關資訊，請參閱 [瞭解可用性金鑰](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="f19ce-393">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="f19ce-394">金鑰輪替</span><span class="sxs-lookup"><span data-stu-id="f19ce-394">Key rotation</span></span>

<span data-ttu-id="f19ce-395">如需使用客戶金鑰旋轉或滾動機碼的相關資訊，請參閱 [滾或輪替客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)。</span><span class="sxs-lookup"><span data-stu-id="f19ce-395">For information about rotating or rolling keys that you use with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="f19ce-396">當您更新 DEP 以使用新版本的金鑰時，會執行 Set-M365DataAtRestEncryptionPolicy Cmdlet，如本文稍早所述。</span><span class="sxs-lookup"><span data-stu-id="f19ce-396">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f19ce-397">相關文章</span><span class="sxs-lookup"><span data-stu-id="f19ce-397">Related articles</span></span>

- [<span data-ttu-id="f19ce-398">客戶金鑰服務加密</span><span class="sxs-lookup"><span data-stu-id="f19ce-398">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="f19ce-399">滾動或旋轉客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="f19ce-399">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="f19ce-400">深入瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="f19ce-400">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="f19ce-401">服務加密</span><span class="sxs-lookup"><span data-stu-id="f19ce-401">Service Encryption</span></span>](office-365-service-encryption.md)
