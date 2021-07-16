---
title: 使用畫布的 Microsoft Teams 會議
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 與畫布整合 Microsoft Teams 會議
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454670"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="1048c-103">使用畫布的 Microsoft Teams 會議</span><span class="sxs-lookup"><span data-stu-id="1048c-103">Use Microsoft Teams meetings with Canvas</span></span>

<span data-ttu-id="1048c-104">Microsoft Teams 會議是 Learning 工具互通性 (LTI) 應用程式，可協助教育者和學生輕鬆流覽其 Learning 管理系統 (LMS) 和 Teams。</span><span class="sxs-lookup"><span data-stu-id="1048c-104">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="1048c-105">使用者可以直接從 LMS 中存取與其課程相關聯的類別小組。</span><span class="sxs-lookup"><span data-stu-id="1048c-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="1048c-106">Microsoft Office 365管理</span><span class="sxs-lookup"><span data-stu-id="1048c-106">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="1048c-107">在管理 Instructure 畫布內的 Microsoft Teams 整合之前，請務必在完成 canvas 管理員設定之前，讓您的組織中組織 Microsoft Office 365 系統管理員核准的畫布 Azure 應用程式的 **Microsoft Teams 同步處理畫布** Microsoft Azure。</span><span class="sxs-lookup"><span data-stu-id="1048c-107">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="1048c-108">登入畫布。</span><span class="sxs-lookup"><span data-stu-id="1048c-108">Sign in to Canvas.</span></span>

2. <span data-ttu-id="1048c-109">選取全域導覽中的 [ **管理** ] 連結，然後選取您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1048c-109">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="1048c-110">在 [系統 **管理] 導覽** 中，選取 [**設定**] 連結，然後選取 [整合] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1048c-110">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="1048c-111">輸入您的 Microsoft 租使用者名稱和登入屬性。</span><span class="sxs-lookup"><span data-stu-id="1048c-111">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="1048c-112">login 屬性將用於將 Canvas 使用者與 Azure Active Directory 使用者關聯。</span><span class="sxs-lookup"><span data-stu-id="1048c-112">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="1048c-113">選取 [**更新設定** 完畢之後。</span><span class="sxs-lookup"><span data-stu-id="1048c-113">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="1048c-114">若要核准對畫布的 **Microsoft Teams-Sync-canvas** Azure app 的存取權，請選取 [**授與承租人存取** 連結]。</span><span class="sxs-lookup"><span data-stu-id="1048c-114">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="1048c-115">您將會重新導向至 Microsoft Identity Platform 系統管理員同意端點。</span><span class="sxs-lookup"><span data-stu-id="1048c-115">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![許可權](media/permissions.png)

7. <span data-ttu-id="1048c-117">選取 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="1048c-117">Select **Accept**.</span></span>

8. <span data-ttu-id="1048c-118">開啟開啟開啟的開啟以啟用 Microsoft Teams 同步處理。</span><span class="sxs-lookup"><span data-stu-id="1048c-118">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![團隊-同步處理](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="1048c-120">畫布管理員</span><span class="sxs-lookup"><span data-stu-id="1048c-120">Canvas Admin</span></span>

<span data-ttu-id="1048c-121">設定 Microsoft Teams LTI 1.3 整合。</span><span class="sxs-lookup"><span data-stu-id="1048c-121">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="1048c-122">做為畫布管理員時，您需要在環境內新增 Microsoft Teams 會議 LTI 應用程式。</span><span class="sxs-lookup"><span data-stu-id="1048c-122">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="1048c-123">請記下應用程式的 LTI 用戶端識別碼。</span><span class="sxs-lookup"><span data-stu-id="1048c-123">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="1048c-124">Microsoft Teams 會議-170000000000703</span><span class="sxs-lookup"><span data-stu-id="1048c-124">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="1048c-125">存取 **管理員設定**  >  **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1048c-125">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="1048c-126">選取 [ **+ App** ]，以新增 Teams LTI 應用程式。</span><span class="sxs-lookup"><span data-stu-id="1048c-126">Select **+ App** to add the Teams LTI apps.</span></span>

   ![外部應用程式](media/external-apps.png)

3. <span data-ttu-id="1048c-128">選取 [ **依用戶端識別碼** ] 設定類型。</span><span class="sxs-lookup"><span data-stu-id="1048c-128">Select **By Client ID** for configuration type.</span></span>

   ![新增應用程式](media/add-app.png)

4. <span data-ttu-id="1048c-130">輸入提供的用戶端識別碼，然後選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="1048c-130">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="1048c-131">您會注意到 Microsoft Teams 會議用於用戶端識別碼的 LTI 應用程式名稱，以確認。</span><span class="sxs-lookup"><span data-stu-id="1048c-131">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="1048c-132">選取 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="1048c-132">Select **Install**.</span></span>

   <span data-ttu-id="1048c-133">Microsoft Teams 會議 LTI 應用程式將會新增至外部應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="1048c-133">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="1048c-134">啟用畫布課程</span><span class="sxs-lookup"><span data-stu-id="1048c-134">Enable for Canvas Courses</span></span>

<span data-ttu-id="1048c-135">為了在課程中使用 LTI，Canvas 課程的指導員必須啟用整合同步。每門課程都必須由指導員啟用，以供建立對應的 Teams;Teams 建立功能沒有全域機制。</span><span class="sxs-lookup"><span data-stu-id="1048c-135">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="1048c-136">這是為了避免建立不想要的 Teams 所設計的警告。</span><span class="sxs-lookup"><span data-stu-id="1048c-136">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="1048c-137">請參閱教師的教師 [手冊檔](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) ，以啟用每門課程的 LTI，並完成整合安裝。</span><span class="sxs-lookup"><span data-stu-id="1048c-137">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
