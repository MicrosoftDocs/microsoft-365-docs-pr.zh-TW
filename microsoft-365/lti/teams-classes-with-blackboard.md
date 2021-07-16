---
title: 整合具有 Blackboard 的 Microsoft Teams 類別瞭解超
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 整合具有 Blackboard 的 Microsoft Teams 類別瞭解超
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314486"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="2610f-103">使用具有 Blackboard 的 Microsoft Teams 類別瞭解超</span><span class="sxs-lookup"><span data-stu-id="2610f-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="2610f-104">團隊合作是在每個現代組織的核心。</span><span class="sxs-lookup"><span data-stu-id="2610f-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="2610f-105">透過鼓勵共同作業，它是定義每個成功之機構的特性。</span><span class="sxs-lookup"><span data-stu-id="2610f-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="2610f-106">您可以加強 Blackboard 的所有功能，並將其與 Microsoft Teams 類別配對。</span><span class="sxs-lookup"><span data-stu-id="2610f-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="2610f-107">您的類別可能包括即時交談、影片會議或非同步互動。</span><span class="sxs-lookup"><span data-stu-id="2610f-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="2610f-108">您可以在一個地方新增學生的檔案共用和 cocreation 體驗。</span><span class="sxs-lookup"><span data-stu-id="2610f-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="2610f-109">使用「學習」的 Microsoft Teams 類別會以「大量重新定義教學」和有效學習的意義。</span><span class="sxs-lookup"><span data-stu-id="2610f-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2610f-110">確定您已在學生資訊系統 (SIS 中成功設定機構電子郵件欄位) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span><span class="sxs-lookup"><span data-stu-id="2610f-110">Ensure that you have successfully set up the Institution Email field in your Student Information System (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span></span>
>
><span data-ttu-id="2610f-111">Microsoft Teams 類別整合依賴您 SIS 中的「機構電子郵件」欄位，以對應至正確的 Microsoft Azure Active Directory (AAD) 使用者主體名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="2610f-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) User Principal Name (UPN).</span></span> <span data-ttu-id="2610f-112">若尚未布建任何機構電子郵件，這將會預設為現有的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2610f-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="2610f-113">建議您為每位使用者設定此欄位，以確保其資料同步處理，且 Microsoft AAD 和 Blackboard 間的電子郵件資料沒有衝突。</span><span class="sxs-lookup"><span data-stu-id="2610f-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between Microsoft AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="2610f-114">如果您未在 SIS 對應中適當地設定此欄位，整合將繼續運作，但使用者可能不會出現在所建立的 Teams 類別中，而且可能會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="2610f-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="2610f-115">支援機構資料對應–機構電子郵件 SIS 欄位</span><span class="sxs-lookup"><span data-stu-id="2610f-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="2610f-116">當您使用雲端提供者整合的一部分演變時，Blackboard 會透過「學生資訊系統架構整合」和「公用 REST」 APIs 等方式，在 Blackboard 中建立新的 **機構電子郵件** 欄位，讓組織能夠在 Blackboard 上有效地管理資料同步處理常式。</span><span class="sxs-lookup"><span data-stu-id="2610f-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and Microsoft AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="2610f-117">機構的電子郵件含義為何？</span><span class="sxs-lookup"><span data-stu-id="2610f-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="2610f-118">「 **機構電子郵件** 」欄位允許用戶端外部支援的資料來源與 Blackboard 的自訂欄位對應。</span><span class="sxs-lookup"><span data-stu-id="2610f-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="2610f-119">如果資料來源是雲端提供者（例如 Microsoft），則使用者主體名稱 (UPN) 是由 UPN 首碼組成的每一位使用者的主要唯一識別碼 (使用者的帳戶名稱) 及 UPN 尾碼， (使用 @ 符號加入的 DNS 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="2610f-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="2610f-120">這會為 Microsoft Azure Active Directory 中的每個特定使用者建立唯一的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2610f-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="2610f-121">為了確保資料在 Blackboard 中的準確性和註冊或成員資格可正確地取得，且可正確地取得 Microsoft Teams 類別，使用者的電子郵件地址必須符合兩個系統之間的條件。</span><span class="sxs-lookup"><span data-stu-id="2610f-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="2610f-122">在 Blackboard 中，使用者可以在使用者介面中變更或覆寫其現有的電子郵件地址，這可能會導致同步處理錯誤，以及使用者未正確加入類別小組。</span><span class="sxs-lookup"><span data-stu-id="2610f-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="2610f-123">使用者可以使用「 **電子郵件** 欄位對應」功能來正確管理此層級的安全性和驗證檢查，不論使用者是否已變更 Blackboard 中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2610f-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="2610f-124">當兩個電子郵件地址不同時，請執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="2610f-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="2610f-125">您必須進行決策，使其具有優先權，並將其當作人員和機構電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2610f-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="2610f-126">或</span><span class="sxs-lookup"><span data-stu-id="2610f-126">Or</span></span>
- <span data-ttu-id="2610f-127">機構可以在其機構電子郵件中設定自訂欄位對應，這樣可以解決可能的衝突。</span><span class="sxs-lookup"><span data-stu-id="2610f-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="2610f-128">「**機構電子郵件** 欄位對應」現在可用於「**高級設定設定** 的所有現有 SIS 整合類型  >  。使用者會 **瞭解物件類型**  >  **欄位對應**。</span><span class="sxs-lookup"><span data-stu-id="2610f-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="2610f-129">請務必注意，根據預設， **機構電子郵件** 會設定為所有 SIS 格式的 **電子郵件** ，且每個人都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2610f-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="2610f-130">所有已設定並執行的現有整合都會就地進行此資料對應，因為當電子郵件重複時，SIS 會無法匯入使用者。</span><span class="sxs-lookup"><span data-stu-id="2610f-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="2610f-131">如果機構需要將機構電子郵件變更為 [**自訂**]，他們必須透過 SIS 中的「**高級設定設定** 來管理這項功能。</span><span class="sxs-lookup"><span data-stu-id="2610f-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="2610f-132">需求</span><span class="sxs-lookup"><span data-stu-id="2610f-132">Requirements</span></span>

<span data-ttu-id="2610f-133">**僅限 Ultra 課程查看課程** 可使用 Microsoft Teams 類別整合。</span><span class="sxs-lookup"><span data-stu-id="2610f-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="2610f-134">您的機構必須完成這些需求才能使用：</span><span class="sxs-lookup"><span data-stu-id="2610f-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="2610f-135">讓 Blackboard 瞭解超深入瞭解 SaaS 啟用超基礎導覽</span><span class="sxs-lookup"><span data-stu-id="2610f-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

- <span data-ttu-id="2610f-136">啟用 LTI 以供課程使用。</span><span class="sxs-lookup"><span data-stu-id="2610f-136">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="2610f-137">a.</span><span class="sxs-lookup"><span data-stu-id="2610f-137">a.</span></span> <span data-ttu-id="2610f-138">移至 **系統管理員面板**  >  **LTI 工具提供者**  >  **管理全域屬性**。</span><span class="sxs-lookup"><span data-stu-id="2610f-138">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="2610f-139">b.</span><span class="sxs-lookup"><span data-stu-id="2610f-139">b.</span></span> <span data-ttu-id="2610f-140">**在課程中選取 LTI 啟用**，並選擇性地選取 [**在組織中啟用**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-140">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="2610f-141">c.</span><span class="sxs-lookup"><span data-stu-id="2610f-141">c.</span></span> <span data-ttu-id="2610f-142">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="2610f-142">Select **Submit**.</span></span>

- <span data-ttu-id="2610f-143">必須設定 LTI</span><span class="sxs-lookup"><span data-stu-id="2610f-143">Must have LTI configured</span></span>

- <span data-ttu-id="2610f-144">新增 Blackboard 瞭解 Ultra Teams 類別 LTI 整合</span><span class="sxs-lookup"><span data-stu-id="2610f-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="2610f-145">新增 Microsoft Teams 類別 LTI 1.3 工具</span><span class="sxs-lookup"><span data-stu-id="2610f-145">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="2610f-146">新增 REST API 工具和跨原始資源分享</span><span class="sxs-lookup"><span data-stu-id="2610f-146">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="2610f-147">設定及核准 Microsoft Teams 類別整合</span><span class="sxs-lookup"><span data-stu-id="2610f-147">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="2610f-148">Add Blackboard 獲知 Ultra Teams 類別 LTI 1.3 工具</span><span class="sxs-lookup"><span data-stu-id="2610f-148">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="2610f-149">從 [ **管理員] 面板** 中，選取 [ **LTI 工具提供者**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-149">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="2610f-150">選取 [ **註冊 LTI 1.3 工具**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-150">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="2610f-151">在 [ **用戶端識別碼** ] 欄位中，輸入或複製並貼上此 ID:</span><span class="sxs-lookup"><span data-stu-id="2610f-151">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="2610f-152">請檢查所有預先填入的設定及 **工具狀態**，然後選取 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-152">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="2610f-153">在 **[機構原則**] 中，選取 [**課程]、[名稱**] 和 [**電子郵件地址**] 中的 [角色]，然後選取 **[是]**</span><span class="sxs-lookup"><span data-stu-id="2610f-153">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="2610f-154">選取 [ **允許評分服務存取** 及 **允許成員資格服務存取**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-154">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="2610f-155">新增 Microsoft Teams 類別 LTI 1.3 工具</span><span class="sxs-lookup"><span data-stu-id="2610f-155">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="2610f-156">從 [ **管理員] 面板** 中，選取 [ **LTI 工具提供者**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-156">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="2610f-157">選取 [ **註冊 LTI 1.3 工具**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-157">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="2610f-158">在 [ **用戶端識別碼** ] 欄位中，輸入或複製並貼上此 ID:</span><span class="sxs-lookup"><span data-stu-id="2610f-158">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="2610f-159">檢查所有預先填入的設定和 [ *工具狀態* ]，然後選取 [ *啟用]。*</span><span class="sxs-lookup"><span data-stu-id="2610f-159">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="2610f-160">在 [**機構原則**] 中，選取 [**課程]、[名稱**] 和 [**電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="2610f-160">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="2610f-161">為這兩者選取 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="2610f-161">Select **Yes** for both.</span></span>

6. <span data-ttu-id="2610f-162">選取 [ **允許評分服務存取** 及 **允許成員資格服務存取**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-162">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="2610f-163">新增 REST API 工具</span><span class="sxs-lookup"><span data-stu-id="2610f-163">Add the REST API tool</span></span>

1. <span data-ttu-id="2610f-164">在 [ **管理員] 面板** 中， **流覽至 [整合]，然後** 選取 [ **Rest API** 整合]。</span><span class="sxs-lookup"><span data-stu-id="2610f-164">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="2610f-165">選取 [ **建立整合**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-165">Select **Create Integration**.</span></span>

3. <span data-ttu-id="2610f-166">在 [ **應用程式識別碼** ] 欄位中，輸入或複製並貼上此 ID:</span><span class="sxs-lookup"><span data-stu-id="2610f-166">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="2610f-167">輸入此整合的使用者。</span><span class="sxs-lookup"><span data-stu-id="2610f-167">Type a user for this integration.</span></span>

   <span data-ttu-id="2610f-168">此使用者將是應用程式所關聯的家鄉 API 存取的使用者。</span><span class="sxs-lookup"><span data-stu-id="2610f-168">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="2610f-169">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="2610f-169">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="2610f-170">新增跨原始資源分享</span><span class="sxs-lookup"><span data-stu-id="2610f-170">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="2610f-171">在 [ **管理員] 面板** 中， **流覽至 [整合]，然後** 選取 [\**跨原始資源分享*]。</span><span class="sxs-lookup"><span data-stu-id="2610f-171">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="2610f-172">選取 [ **建立** 設定]。</span><span class="sxs-lookup"><span data-stu-id="2610f-172">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="2610f-173">在 [ **來源** ] 欄位中，輸入複製及貼上此 URL:</span><span class="sxs-lookup"><span data-stu-id="2610f-173">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="2610f-174">在 [ **允許的標頭** ] 欄位中，輸入 **授權**。</span><span class="sxs-lookup"><span data-stu-id="2610f-174">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="2610f-175">設定 **為** **[是]**。</span><span class="sxs-lookup"><span data-stu-id="2610f-175">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="2610f-176">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="2610f-176">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="2610f-177">設定及核准 Microsoft Teams 類別整合</span><span class="sxs-lookup"><span data-stu-id="2610f-177">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="2610f-178">若要使用 Microsoft Teams 類別成功整合您的 Blackboard，請確定已核准 blackboard 取得超級應用程式，以便在您的 Microsoft Azure 租使用者記憶體取。</span><span class="sxs-lookup"><span data-stu-id="2610f-178">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="2610f-179">這是您的機構 Microsoft 365 全域管理員需要完成的程式。</span><span class="sxs-lookup"><span data-stu-id="2610f-179">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="2610f-180">您可以在您已設定 Blackboard 中的 LTI 應用程式之前或之後，再執行一步。</span><span class="sxs-lookup"><span data-stu-id="2610f-180">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="2610f-181">設定 LTI 應用程式之前</span><span class="sxs-lookup"><span data-stu-id="2610f-181">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="2610f-182">如果您選擇核准 Blackboard 在設定 LTI 整合之前，先向 Azure 應用程式獲知 Ultra Teams 類別，您必須重新導向至 **Microsoft Identity Platform 系統管理員同意端點**。</span><span class="sxs-lookup"><span data-stu-id="2610f-182">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="2610f-183">URL 如下：</span><span class="sxs-lookup"><span data-stu-id="2610f-183">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="2610f-184">您會將 **{租** 使用者更換為您的特定機構 Microsoft Azure 租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="2610f-184">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="2610f-185">設定 LTI 應用程式之後</span><span class="sxs-lookup"><span data-stu-id="2610f-185">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="2610f-186">在 [**系統管理員] 面板** 上，流覽至 [**工具及公用程式**]，然後選取 [ **Microsoft Teams Integration Admin**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-186">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="2610f-187">選取 [**啟用 Microsoft Teams**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-187">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="2610f-188">將您的 **Microsoft 租使用者識別碼** 新增至 [可用] 文字欄位。</span><span class="sxs-lookup"><span data-stu-id="2610f-188">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="2610f-189">選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="2610f-189">Choose one of the following options:</span></span>

   - <span data-ttu-id="2610f-190">如果此應用程式預先同意，它會顯示一個小核取記號。</span><span class="sxs-lookup"><span data-stu-id="2610f-190">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="2610f-191">如果出現核取記號，請選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-191">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="2610f-192">若未經核准，請遵循所述的步驟，以產生同意的 URL，並將其傳送給 Microsoft 365 全域管理員以核准。</span><span class="sxs-lookup"><span data-stu-id="2610f-192">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="2610f-193">確認核准後，請選取 [ **重試** 以確認]，然後選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="2610f-193">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>