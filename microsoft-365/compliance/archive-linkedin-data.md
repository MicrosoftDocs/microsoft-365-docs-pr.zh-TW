---
title: 設定連接器來封存 LinkedIn 資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 管理員可以設定原生連接器，將資料從 LinkedIn 公司] 頁面匯入至 Microsoft 365。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料的合規性。
ms.openlocfilehash: 6b74e6ba8dca810a8a185ae6011207a419c3e79d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943212"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a><span data-ttu-id="7c443-104">設定連接器來封存 LinkedIn 資料</span><span class="sxs-lookup"><span data-stu-id="7c443-104">Set up a connector to archive LinkedIn data</span></span>

<span data-ttu-id="7c443-105">使用 Microsoft 365 規範中心內的連接器，從 LinkedIn 公司頁面匯入及封存資料。</span><span class="sxs-lookup"><span data-stu-id="7c443-105">Use a connector in the Microsoft 365 compliance center to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="7c443-106">在您設定及設定連接器之後，它會每隔24小時連線到特定 LinkedIn 公司] 頁面的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7c443-106">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="7c443-107">連接器會將張貼到公司頁面的郵件轉換為電子郵件，然後將這些專案匯入至 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="7c443-107">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="7c443-108">LinkedIn 公司頁面資料儲存在信箱中之後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋、In-Place 封存、審核和 Microsoft 365 保留原則）套用至 LinkedIn 資料。</span><span class="sxs-lookup"><span data-stu-id="7c443-108">After the LinkedIn Company page data is stored in a mailbox, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="7c443-109">例如，您可以使用內容搜尋來搜尋這些專案，或在高級 eDiscovery 案例中將儲存信箱與保管人建立關聯。</span><span class="sxs-lookup"><span data-stu-id="7c443-109">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="7c443-110">建立連接器，以在 Microsoft 365 中匯入和封存 LinkedIn 資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="7c443-110">Creating a connector to import and archive LinkedIn data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you--begin"></a><span data-ttu-id="7c443-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="7c443-111">Before you  begin</span></span>

- <span data-ttu-id="7c443-112">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="7c443-112">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="7c443-113">若要同意此要求，請移至[此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Microsoft 365 全域管理員的認證登入，然後接受要求。</span><span class="sxs-lookup"><span data-stu-id="7c443-113">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Microsoft 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="7c443-114">建立 LinkedIn 公司頁面連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="7c443-114">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="7c443-115">在 Microsoft 365 規範中心的 [**資料連線器**] 頁面中新增連接器時，這是必要的。</span><span class="sxs-lookup"><span data-stu-id="7c443-115">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7c443-116">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="7c443-116">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="7c443-117">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="7c443-117">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="7c443-118">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="7c443-118">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="7c443-119">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [[建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)] 區段。</span><span class="sxs-lookup"><span data-stu-id="7c443-119">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="7c443-120">您必須具有 LinkedIn 使用者帳戶的登入認證（電子郵件地址或電話號碼和密碼），該使用者帳戶是您要封存之 LinkedIn 公司] 頁面的管理員。</span><span class="sxs-lookup"><span data-stu-id="7c443-120">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="7c443-121">當您設定連接器時，您可以使用這些認證登入 LinkedIn。</span><span class="sxs-lookup"><span data-stu-id="7c443-121">You use these credentials to sign in to LinkedIn when setting up the connector.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="7c443-122">建立 LinkedIn 連接器</span><span class="sxs-lookup"><span data-stu-id="7c443-122">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="7c443-123">移至<https://compliance.microsoft.com> ，然後按一下 [**資料連線器** > ]**LinkedIn 公司頁面**。</span><span class="sxs-lookup"><span data-stu-id="7c443-123">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **LinkedIn Company pages**.</span></span>

2. <span data-ttu-id="7c443-124">在 [ **LinkedIn 公司頁面**產品] 頁面上，按一下 [**新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="7c443-124">On the **LinkedIn company pages** product page, click **Add connector**.</span></span>

3. <span data-ttu-id="7c443-125">在 [**服務條款**] 頁面上，選取 [**接受**]。</span><span class="sxs-lookup"><span data-stu-id="7c443-125">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="7c443-126">在 [**使用 LinkedIn 登入**] 頁面上，按一下 [以**LinkedIn 登入**]。</span><span class="sxs-lookup"><span data-stu-id="7c443-126">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="7c443-127">隨即會顯示 [LinkedIn 登入] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c443-127">The LinkedIn sign in page is displayed.</span></span>

   ![LinkedIn 登入頁面](../media/LinkedInSigninPage.png)

5. <span data-ttu-id="7c443-129">在 [LinkedIn 登入] 頁面上，輸入與您要封存之公司頁面相關聯之 LinkedIn 帳戶的電子郵件地址（或電話號碼）和密碼，然後按一下 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="7c443-129">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="7c443-130">隨即會顯示一個嚮導頁面，其中列出所有與您登入之帳戶相關聯的 LinkedIn 公司頁面。</span><span class="sxs-lookup"><span data-stu-id="7c443-130">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="7c443-131">只可為一個公司頁面設定連接器。</span><span class="sxs-lookup"><span data-stu-id="7c443-131">A connector can only be configured for one company page.</span></span> <span data-ttu-id="7c443-132">如果您的組織有多個 LinkedIn 公司頁面，您必須為每個頁面建立一個連接器。</span><span class="sxs-lookup"><span data-stu-id="7c443-132">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![隨即會顯示一個包含 LinkedIn 公司頁面清單的頁面](../media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="7c443-134">選取您要封存專案的公司頁面，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7c443-134">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="7c443-135">在 [**設定篩選**] 頁面上，您可以將篩選器最初匯入特定時期的專案。</span><span class="sxs-lookup"><span data-stu-id="7c443-135">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="7c443-136">選取 [年齡]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7c443-136">Select an age, and then click **Next**.</span></span>

8. <span data-ttu-id="7c443-137">在 [**選擇儲存位置**] 頁面上，按一下方塊，選取要匯入 LinkedIn 專案的 Microsoft 365 信箱的電子郵件地址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7c443-137">On the **Choose storage location** page, click in the box, select the email address of an Microsoft 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="7c443-138">將專案匯入此信箱中的 [收件匣] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c443-138">Items are imported to the inbox folder in this mailbox.</span></span>

9. <span data-ttu-id="7c443-139">在 [**提供管理員同意**] 中，按一下 [**提供同意**]，然後依照步驟進行。</span><span class="sxs-lookup"><span data-stu-id="7c443-139">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="7c443-140">您必須是全域系統管理員，才可對您組織中的資料提供 Office 365 匯入服務的同意。</span><span class="sxs-lookup"><span data-stu-id="7c443-140">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

10. <span data-ttu-id="7c443-141">按 **[下一步]** 以查看連接器設定，然後按一下 **[完成]** 以完成連接器設定。</span><span class="sxs-lookup"><span data-stu-id="7c443-141">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

<span data-ttu-id="7c443-142">建立連接器之後，您可以回到 [**資料連線器**] 頁面，以查看新連接器的匯入程式的進度（**如有必要，請選取 [** 重新整理] 以更新連接器清單）。</span><span class="sxs-lookup"><span data-stu-id="7c443-142">After you create the connector, you can go back to the **Data connectors** page to see the progress of the import process for the new connector (select **Refresh** if necessary to update the list of connectors).</span></span> <span data-ttu-id="7c443-143">[**狀態**] 欄中的值正**等候開始**。</span><span class="sxs-lookup"><span data-stu-id="7c443-143">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="7c443-144">開始進行初始匯入程式需要長達24小時的時間。</span><span class="sxs-lookup"><span data-stu-id="7c443-144">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="7c443-145">在連接器第一次執行並匯入 LinkedIn 專案之後，連接器會每隔24小時執行一次，並匯入在前24小時內，在 LinkedIn 公司頁面上建立的任何新專案。</span><span class="sxs-lookup"><span data-stu-id="7c443-145">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="7c443-146">若要查看更多詳細資料，請選取 [**資料連線器**] 頁面上清單中的連接器以顯示飛入頁面。</span><span class="sxs-lookup"><span data-stu-id="7c443-146">To view more details, select the connector in the list on the **Data connectors** page to display the flyout page.</span></span> <span data-ttu-id="7c443-147">在 [**狀態**] 下，顯示的日期範圍會指出建立連接器時所選取的年齡篩選。</span><span class="sxs-lookup"><span data-stu-id="7c443-147">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span> 

## <a name="more-information"></a><span data-ttu-id="7c443-148">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7c443-148">More information</span></span>

<span data-ttu-id="7c443-149">LinkedIn 項會匯入至 Microsoft 365 中儲存信箱收件匣的 LinkedIn 子資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c443-149">LinkedIn items are imported to the LinkedIn subfolder in the inbox of the storage mailbox in Microsoft 365.</span></span> <span data-ttu-id="7c443-150">它們會顯示為電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="7c443-150">They appear as email messages.</span></span>
