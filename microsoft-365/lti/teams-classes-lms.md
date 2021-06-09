---
title: 使用具有 Blackboard 的 Microsoft Teams 類別
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
description: 整合您的教學管理系統中 Microsoft Teams 類別
ms.openlocfilehash: 287b9f1cadfdcf3adafdca91f4a351865bbcf3bc
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821268"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a><span data-ttu-id="16433-103">使用具有 Blackboard 的 Microsoft Teams 類別</span><span class="sxs-lookup"><span data-stu-id="16433-103">Use Microsoft Teams classes with Blackboard</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16433-104">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="16433-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="16433-105">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="16433-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="16433-106">Microsoft Teams 類別是 (LTI) 應用程式的學習工具互通性，可協助教育者和學生輕鬆流覽其教學管理系統 (LMS) 和 Teams。</span><span class="sxs-lookup"><span data-stu-id="16433-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="16433-107">使用者可以直接從 LMS 中存取與其課程相關聯的類別小組。</span><span class="sxs-lookup"><span data-stu-id="16433-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="16433-108">核准 Microsoft Azure 租使用者中的應用程式</span><span class="sxs-lookup"><span data-stu-id="16433-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="16433-109">下列工作由 Microsoft Office 365 系統管理員所完成，Blackboard 會透過超級系統管理員的身分瞭解。</span><span class="sxs-lookup"><span data-stu-id="16433-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="16433-110">在管理 Blackboard 中的整合之前，Microsoft Office 365 管理員必須核准 Blackboard **MSFT Teams，以瞭解** 機構 Microsoft Azure 承租人的 Ultra Azure 應用程式。</span><span class="sxs-lookup"><span data-stu-id="16433-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="16433-111">尋找您的 Microsoft 租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="16433-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="16433-112">請參閱 [如何尋找租](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)使用者。</span><span class="sxs-lookup"><span data-stu-id="16433-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="16433-113">請根據下列範例重新導向 Microsoft Identity 平臺系統管理員同意端點：</span><span class="sxs-lookup"><span data-stu-id="16433-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="16433-114">以您組織的 Microsoft 租使用者識別碼取代 {承租人}。</span><span class="sxs-lookup"><span data-stu-id="16433-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="16433-115">註冊整合應用程式</span><span class="sxs-lookup"><span data-stu-id="16433-115">Register the integration apps</span></span>

<span data-ttu-id="16433-116">隨著 Blackboard 的瞭解，您必須在測試環境中註冊2個 LTI 1.3 整合應用程式：</span><span class="sxs-lookup"><span data-stu-id="16433-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="16433-117">Blackboard 課程類別 Teams 整合，以支援名單同步處理</span><span class="sxs-lookup"><span data-stu-id="16433-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="16433-118">Microsoft Teams 類別小組 LTI 應用程式</span><span class="sxs-lookup"><span data-stu-id="16433-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="16433-119">請記下這兩個應用程式的 LTI 用戶端 IDs：</span><span class="sxs-lookup"><span data-stu-id="16433-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="16433-120">Blackboard-f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="16433-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="16433-121">Microsoft-027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="16433-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="16433-122">存取系統管理員 **面板，然後在 [** 整合] 下，找到 LTI 工具提供者。</span><span class="sxs-lookup"><span data-stu-id="16433-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![這是 LTI 工具提供者對話方塊會顯示提供者清單](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="16433-124">選取 [ **註冊 lti 1.3/優點工具**]。</span><span class="sxs-lookup"><span data-stu-id="16433-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="16433-125">輸入 (Blackboard 或 Microsoft) 所提供的第一個用戶端 IDs，然後選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="16433-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![具有欄位來輸入用戶端識別碼的 LTI 註冊工具](../media/lti-media/register-tool.png)

5. <span data-ttu-id="16433-127">請複查預先填入的設定，並確定工具狀態標示為 [已核准]。</span><span class="sxs-lookup"><span data-stu-id="16433-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="16433-128">向下移動至下方，然後選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="16433-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="16433-129">重複上述步驟，在您的環境內註冊第二個 LTI 應用程式。</span><span class="sxs-lookup"><span data-stu-id="16433-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="16433-130">設定 REST 應用程式和跨原始資源分享</span><span class="sxs-lookup"><span data-stu-id="16433-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="16433-131">Blackboard 會以超級管理員的身分瞭解，也需要設定 REST 應用程式和跨原始資源分享設定。</span><span class="sxs-lookup"><span data-stu-id="16433-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="16433-132">完成下列設定 REST 應用程式</span><span class="sxs-lookup"><span data-stu-id="16433-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="16433-133">存取「學習管理」工具，然後 **從 [整合**] 區段中選取 [ **REST API** 整合]。</span><span class="sxs-lookup"><span data-stu-id="16433-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="16433-134">選取 [**建立** 整合]，然後輸入您為 Blackboard 瞭解類別 Teams 整合 LTI 工具輸入的相同應用程式/用戶端識別碼。</span><span class="sxs-lookup"><span data-stu-id="16433-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="16433-135">輸入「瞭解使用者 (這可能是您自己的學習管理使用者名稱) ，或選取 **[流覽]** 以尋找。</span><span class="sxs-lookup"><span data-stu-id="16433-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="16433-136">針對 **使用者存取** 選取 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="16433-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="16433-137">選取 **[是]** 以取得 **使用者的授權**</span><span class="sxs-lookup"><span data-stu-id="16433-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="16433-138">選取 [完成後 **提交** ]。</span><span class="sxs-lookup"><span data-stu-id="16433-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="16433-139">設定跨原始資源分享</span><span class="sxs-lookup"><span data-stu-id="16433-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="16433-140">存取「學習管理」工具，然後 **選取 [整合**] 區段中的 [**跨原始資源分享**]。</span><span class="sxs-lookup"><span data-stu-id="16433-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="16433-141">選取 [ **建立** 設定]。</span><span class="sxs-lookup"><span data-stu-id="16433-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="16433-142">輸入 `https://bb-ms-teams-ultra-ext.api.blackboard.com` 來源。</span><span class="sxs-lookup"><span data-stu-id="16433-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="16433-143">在 **允許的標頭** 中新增 word **授權**。</span><span class="sxs-lookup"><span data-stu-id="16433-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="16433-144">設定 **為** **[是]**。</span><span class="sxs-lookup"><span data-stu-id="16433-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="16433-145">選取 [完成後 **提交** ]。</span><span class="sxs-lookup"><span data-stu-id="16433-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="16433-146">在 Blackboard 瞭解中啟用類別 Teams</span><span class="sxs-lookup"><span data-stu-id="16433-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="16433-147">一旦您啟用 LTI 工具，下一個步驟就是設定 Microsoft 類別 Teams 與您自己 Microsoft Office 365 租使用者的整合。</span><span class="sxs-lookup"><span data-stu-id="16433-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="16433-148">若要執行此動作，請遵循下列步驟，將「Blackboard」瞭解為「超級管理員」。</span><span class="sxs-lookup"><span data-stu-id="16433-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="16433-149">在 [**瞭解系統管理**  >  **工具和公用程式**] 中，選取 [ **Microsoft Teams Integration Admin**]。</span><span class="sxs-lookup"><span data-stu-id="16433-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![包含可用工具清單的 [工具及實用程式] 對話方塊](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="16433-151">選取 [**啟用 Microsoft Teams**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="16433-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="16433-152">依照 Microsoft O365 系統管理員底下的區段中所述，輸入您的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="16433-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="16433-153">您將無法儲存設定，直到 O365 系統管理員核准應用程式為止。請參閱[核准 Microsoft Azure 租使用者中的應用程式](#approve-the-app-in-the-microsoft-azure-tenant)。</span><span class="sxs-lookup"><span data-stu-id="16433-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="16433-154">當全域 O365 系統管理員已核准您的 Microsoft 租使用者中的 Blackboard Teams 應用程式時，請選取 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="16433-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
