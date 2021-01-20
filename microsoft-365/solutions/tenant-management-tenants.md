---
title: 步驟 1： 您的 Microsoft 365 for enterprise 承租人
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: 部署及管理單一或多個 Microsoft 365 承租人，包含多地理位置和移動位置的選項。
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908510"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="ec134-104">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="ec134-104">Step 1.</span></span> <span data-ttu-id="ec134-105">您的 Microsoft 365 for enterprise 承租人</span><span class="sxs-lookup"><span data-stu-id="ec134-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="ec134-106">您第一個承租人決策是多少。</span><span class="sxs-lookup"><span data-stu-id="ec134-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="ec134-107">每個 Microsoft 365 租使用者都是獨特且獨特的，並與所有其他 Microsoft 365 承租人分開。</span><span class="sxs-lookup"><span data-stu-id="ec134-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="ec134-108">其對應的 Azure AD 租使用者也是獨特且獨特的，且與所有其他 Microsoft 365 承租人分開。</span><span class="sxs-lookup"><span data-stu-id="ec134-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="ec134-109">單一租使用者</span><span class="sxs-lookup"><span data-stu-id="ec134-109">Single tenant</span></span>
<span data-ttu-id="ec134-110">擁有單一租使用者可簡化貴組織的許多部分使用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ec134-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="ec134-111">單一租使用者代表單一 Azure AD 租使用者搭配一群組帳戶、群組和原則。</span><span class="sxs-lookup"><span data-stu-id="ec134-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="ec134-112">您整個組織中的資源許可權及共用均可透過此中央身分識別提供者進行。</span><span class="sxs-lookup"><span data-stu-id="ec134-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="ec134-113">單一承租人為您的使用者提供功能最豐富且簡化的共同作業和生產力體驗。</span><span class="sxs-lookup"><span data-stu-id="ec134-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="ec134-114">以下是一個範例，顯示 Microsoft 365 租使用者的預設位置和 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="ec134-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![單一 Microsoft 365 租使用者及其 Azure AD 租使用者](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="ec134-116">多個租用戶</span><span class="sxs-lookup"><span data-stu-id="ec134-116">Multiple tenants</span></span>

<span data-ttu-id="ec134-117">您的組織可能有多個承租人的原因有多種：</span><span class="sxs-lookup"><span data-stu-id="ec134-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="ec134-118">系統管理隔離</span><span class="sxs-lookup"><span data-stu-id="ec134-118">Administrative isolation</span></span>
- <span data-ttu-id="ec134-119">分散 IT</span><span class="sxs-lookup"><span data-stu-id="ec134-119">Decentralized IT</span></span>
- <span data-ttu-id="ec134-120">歷史決策</span><span class="sxs-lookup"><span data-stu-id="ec134-120">Historical decisions</span></span>
- <span data-ttu-id="ec134-121">合併、收購或 divestitures</span><span class="sxs-lookup"><span data-stu-id="ec134-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="ec134-122">清除集團組織的品牌分隔</span><span class="sxs-lookup"><span data-stu-id="ec134-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="ec134-123">預先生產、測試或沙箱承租人</span><span class="sxs-lookup"><span data-stu-id="ec134-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="ec134-124">以下是一個組織範例，其中有兩個承租人 (承租人 A 與租使用者 B) 相同的預設資料中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="ec134-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="ec134-125">每個租使用者都是個別 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="ec134-125">Each tenant as a separate Azure AD tenant.</span></span>

![使用自身 Azure AD 承租人的多個 Microsoft 365 承租人](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="ec134-127">當您有多個承租人時，系統會有限制及其他考慮，以加以管理並為使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="ec134-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="ec134-128">租用戶間共同作業</span><span class="sxs-lookup"><span data-stu-id="ec134-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="ec134-129">如果您想要讓您的使用者在安全的情況下更有效率地跨不同的 Microsoft 365 承租人進行共同作業，則租使用者共同作業選項包括使用中心位置來進行檔案與交談、共用行事曆、使用 IM、音訊/視頻通話進行通訊，以及保護資源和應用程式的存取。</span><span class="sxs-lookup"><span data-stu-id="ec134-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="ec134-130">如需詳細資訊，請參閱 [Microsoft 365 內部租使用者共同](../enterprise/microsoft-365-inter-tenant-collaboration.md)作業。</span><span class="sxs-lookup"><span data-stu-id="ec134-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="ec134-131">跨承租人信箱遷移 (預覽) </span><span class="sxs-lookup"><span data-stu-id="ec134-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="ec134-132">在 [) 預覽] 中的跨承租人信箱遷移 (之前，您必須在承租人之間移動 Exchange Online 信箱，以完全下架使用者信箱的目前租使用者， (來源租使用者) 至內部部署，然後再將其上架至新租使用者 (。</span><span class="sxs-lookup"><span data-stu-id="ec134-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="ec134-133">使用新的跨租使用者信箱遷移功能，來源和目標承租人中的租使用者管理員可以在租使用者內部部署系統中的基礎結構相依性之間移動信箱。</span><span class="sxs-lookup"><span data-stu-id="ec134-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="ec134-134">這樣就不再需要離線和上架信箱。</span><span class="sxs-lookup"><span data-stu-id="ec134-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="ec134-135">以下是跨租使用者信箱遷移之前的兩個範例承租人和其信箱。</span><span class="sxs-lookup"><span data-stu-id="ec134-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![多個 Microsoft 365 承租人及其信箱](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="ec134-137">在此圖中，兩個不同的承租人具有自己的網域和 Exchange 信箱集。</span><span class="sxs-lookup"><span data-stu-id="ec134-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="ec134-138">以下是在跨租使用者信箱遷移之後， (租使用者) 的目標租使用者。</span><span class="sxs-lookup"><span data-stu-id="ec134-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![跨承租人信箱遷移之後的目標租使用者](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="ec134-140">在此圖中，單一租使用者同時有兩個網域和兩組 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="ec134-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="ec134-141">如需詳細資訊，請參閱 [跨租使用者信箱遷移](../enterprise/cross-tenant-mailbox-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="ec134-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="ec134-142">租用戶到租用戶的移轉</span><span class="sxs-lookup"><span data-stu-id="ec134-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="ec134-143">合併、收購、divestitures 及其他案例有數種架構方法可能會讓您將現有的 Microsoft 365 租使用者遷移至新的租使用者。</span><span class="sxs-lookup"><span data-stu-id="ec134-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="ec134-144">如需詳細指示，請參閱 [Microsoft 365 租使用者對租使用者遷移](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)。</span><span class="sxs-lookup"><span data-stu-id="ec134-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="ec134-145">承租人的多地理位置</span><span class="sxs-lookup"><span data-stu-id="ec134-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="ec134-146">使用 Microsoft 365 多地理位置，您可以在其他資料中心地理位置中布建和儲存資料，而這些地理位置是您已選擇符合資料派駐要求的位置，同時也會解除對您的工作人員進行現代生產力體驗的全域部署。</span><span class="sxs-lookup"><span data-stu-id="ec134-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="ec134-147">在多地理位置環境中，您的 Microsoft 365 租使用者是由預設或中央位置所組成，您的 Microsoft 365 訂閱最初是建立所在的位置，以及一個或多個衛星位置。</span><span class="sxs-lookup"><span data-stu-id="ec134-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="ec134-148">在多地理位置承租人中，地理位置、群組和使用者資訊的相關資訊，都是在全域 Azure AD 租使用者中使用。</span><span class="sxs-lookup"><span data-stu-id="ec134-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="ec134-149">因為您的承租人資訊已集中集中並同步處理到每個地理位置，所以與您公司的任何人共同作業的共同作業體驗都會在各位置間共用。</span><span class="sxs-lookup"><span data-stu-id="ec134-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="ec134-150">以下是一個組織的範例，其預設位置在歐洲和北美的一個衛星位置。</span><span class="sxs-lookup"><span data-stu-id="ec134-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="ec134-151">這兩個位置都共用單一 Microsoft 365 租使用者的相同全域 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="ec134-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![多地理位置 Microsoft 365 租使用者範例](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="ec134-153">如需詳細資訊，請參閱 [Microsoft 365 多地理位置](../enterprise/microsoft-365-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="ec134-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="ec134-154">將核心資料移至新的資料中心地理位置</span><span class="sxs-lookup"><span data-stu-id="ec134-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="ec134-155">Microsoft 繼續開啟新的資料中心 geos for Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="ec134-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="ec134-156">這些新的資料中心 geos 可增加容量及計算資源，以支援我們持續的客戶需求和使用量成長。</span><span class="sxs-lookup"><span data-stu-id="ec134-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="ec134-157">此外，新的資料中心 geos 提供核心客戶資料的地理位置資料派駐服務。</span><span class="sxs-lookup"><span data-stu-id="ec134-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="ec134-158">雖然開啟新的資料中心地理位置並不會影響您和您的核心資料儲存在現有的資料中心地理位置，但 Microsoft 可讓您要求將組織的核心客戶資料及早遷移至新的資料中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="ec134-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="ec134-159">以下是 Microsoft 365 租使用者從歐盟 (歐盟) 從歐盟地理位置移至英國 (UK) 的範例。</span><span class="sxs-lookup"><span data-stu-id="ec134-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![在資料中心 geos 之間移動 Microsoft 365 承租人的範例](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="ec134-161">如需詳細資訊，請參閱 [將核心資料移至新的 Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="ec134-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="ec134-162">租使用者的產品和授權</span><span class="sxs-lookup"><span data-stu-id="ec134-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="ec134-163">當您購買第一種產品時（例如 Microsoft 365 E3），您的 Microsoft 365 租使用者即會建立。</span><span class="sxs-lookup"><span data-stu-id="ec134-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="ec134-164">除了產品之外，還會收取每月或每年費用的授權。</span><span class="sxs-lookup"><span data-stu-id="ec134-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="ec134-165">然後，系統管理員可以直接或透過群組成員資格，將其中一項產品的可用授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ec134-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="ec134-166">根據組織的業務需求，您可能有一組產品，每個產品都有自己的授權集區。</span><span class="sxs-lookup"><span data-stu-id="ec134-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="ec134-167">若要判斷一組產品以及每個產品的授權數目，必須進行下列規劃：</span><span class="sxs-lookup"><span data-stu-id="ec134-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="ec134-168">確定您有足夠的授權，可供需要高級功能的使用者帳戶使用。</span><span class="sxs-lookup"><span data-stu-id="ec134-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="ec134-169">根據組織中人員的變更，防止您的授權不足或未指派授權的數目。</span><span class="sxs-lookup"><span data-stu-id="ec134-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="ec134-170">步驟 1 的結果</span><span class="sxs-lookup"><span data-stu-id="ec134-170">Results of Step 1</span></span>

<span data-ttu-id="ec134-171">針對您的 Microsoft 365 for enterprise 承租人，您已決定：</span><span class="sxs-lookup"><span data-stu-id="ec134-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="ec134-172">您有多少租使用者或需要多少承租人。</span><span class="sxs-lookup"><span data-stu-id="ec134-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="ec134-173">每個租使用者必須購買的產品和授權。</span><span class="sxs-lookup"><span data-stu-id="ec134-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="ec134-174">承租人是否必須是多地理位置，以符合資料派駐要求。</span><span class="sxs-lookup"><span data-stu-id="ec134-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="ec134-175">您是否需要設定承租人間共同作業。</span><span class="sxs-lookup"><span data-stu-id="ec134-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="ec134-176">是否需要將一個承租人遷移至另一個承租人。</span><span class="sxs-lookup"><span data-stu-id="ec134-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="ec134-177">您是否需要將核心資料從一個資料中心地理位置移至新。</span><span class="sxs-lookup"><span data-stu-id="ec134-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="ec134-178">以下是新租使用者的範例。</span><span class="sxs-lookup"><span data-stu-id="ec134-178">Here is an example of a new tenant.</span></span>

![新租使用者的範例](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="ec134-180">在此圖中，租使用者有：</span><span class="sxs-lookup"><span data-stu-id="ec134-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="ec134-181">與 Microsoft 365 資料中心地理位置相對應的預設位置。</span><span class="sxs-lookup"><span data-stu-id="ec134-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="ec134-182">一組產品和授權。</span><span class="sxs-lookup"><span data-stu-id="ec134-182">A set of products and licenses.</span></span>
- <span data-ttu-id="ec134-183">雲端生產力應用程式的集合，有些專用於產品。</span><span class="sxs-lookup"><span data-stu-id="ec134-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="ec134-184">包含全域管理員帳戶和初始 DNS 功能變數名稱的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="ec134-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="ec134-185">當我們流覽此解決方案的其他步驟時，我們將會培養此圖。</span><span class="sxs-lookup"><span data-stu-id="ec134-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="ec134-186">承租人的持續維護</span><span class="sxs-lookup"><span data-stu-id="ec134-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="ec134-187">您可能需要進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="ec134-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="ec134-188">新增租使用者。</span><span class="sxs-lookup"><span data-stu-id="ec134-188">Add a new tenant.</span></span>
- <span data-ttu-id="ec134-189">使用初始授權數目新增產品至租使用者。</span><span class="sxs-lookup"><span data-stu-id="ec134-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="ec134-190">變更承租人中產品的授權集，以調整員工需求的變更。</span><span class="sxs-lookup"><span data-stu-id="ec134-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="ec134-191">將核心資料從租使用者移至新的資料中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="ec134-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="ec134-192">針對資料派駐服務需求新增多地理位置。</span><span class="sxs-lookup"><span data-stu-id="ec134-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="ec134-193">設定承租人間共同作業。</span><span class="sxs-lookup"><span data-stu-id="ec134-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="ec134-194">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ec134-194">Next step</span></span>

<span data-ttu-id="ec134-195">[![步驟2。為您的網路存取優化您的租使用者](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="ec134-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="ec134-196">繼續 [聯網](tenant-management-networking.md) ，以提供與您的工作人員的最佳網路與 Microsoft 365 雲端服務的連線。</span><span class="sxs-lookup"><span data-stu-id="ec134-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
