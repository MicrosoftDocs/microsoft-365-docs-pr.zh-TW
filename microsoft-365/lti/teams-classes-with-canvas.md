---
title: 使用具有畫布的 Microsoft Teams 類別
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
description: 將 Microsoft Teams 類別與畫布整合
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454682"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="31ff7-103">使用具有畫布的 Microsoft Teams 類別</span><span class="sxs-lookup"><span data-stu-id="31ff7-103">Use Microsoft Teams classes with Canvas</span></span>

<span data-ttu-id="31ff7-104">Microsoft Teams 類別是 Learning 工具互通性 (LTI) 應用程式，可協助教育者和學生輕鬆流覽其 Learning 管理系統 (LMS) 和 Teams。</span><span class="sxs-lookup"><span data-stu-id="31ff7-104">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="31ff7-105">使用者可以直接從 LMS 中存取與其課程相關聯的類別小組。</span><span class="sxs-lookup"><span data-stu-id="31ff7-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="prerequisites-before-deployment"></a><span data-ttu-id="31ff7-106">部署之前的必要條件</span><span class="sxs-lookup"><span data-stu-id="31ff7-106">Prerequisites Before Deployment</span></span>

> [!NOTE]
> <span data-ttu-id="31ff7-107">目前的類別 Teams LTI 只支援在有限範圍內 Microsoft Azure Active Directory (AAD) 同步處理畫布使用者。</span><span class="sxs-lookup"><span data-stu-id="31ff7-107">The current Class Teams LTI only supports syncing Canvas users with Microsoft Azure Active Directory (AAD) in a limited scope.</span></span> 
> - <span data-ttu-id="31ff7-108">您的租使用者必須在 (電子郵件、使用者識別碼或 SIS 識別碼) 和 Microsoft AAD 中的 UPN 的畫布欄位之間完全符合。</span><span class="sxs-lookup"><span data-stu-id="31ff7-108">Your tenant must have an exact match between a Canvas field (email, user ID, or SIS ID) and the UPN in Microsoft AAD.</span></span> <span data-ttu-id="31ff7-109">我們正在努力展開對同步處理功能的彈性，但是與此同時，在與 AAD 中的 UPN 不相符的任何使用者，也不會將其新增至與 AAD 同步處理的 Teams 類別中。</span><span class="sxs-lookup"><span data-stu-id="31ff7-109">We are working to expand flexibility to the syncing functionality, but in the meantime, any users in Canvas not matched to a UPN in AAD will not be added to the Teams class synced with Canvas.</span></span> 
> - <span data-ttu-id="31ff7-110">只有一個 Microsoft 租使用者可以用於在畫布和 Microsoft 之間對應使用者。</span><span class="sxs-lookup"><span data-stu-id="31ff7-110">Only a single Microsoft tenant can be used for mapping users between Canvas and Microsoft.</span></span>
> - <span data-ttu-id="31ff7-111">您必須先關閉 SDS，才能使用類別 Teams LTI，以避免重複群組。</span><span class="sxs-lookup"><span data-stu-id="31ff7-111">You will have to turn off SDS before using the Class Teams LTI in order to avoid duplication of groups.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="31ff7-112">Microsoft Office 365管理</span><span class="sxs-lookup"><span data-stu-id="31ff7-112">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="31ff7-113">在管理 Instructure 畫布內的 Microsoft Teams 整合之前，請務必在完成 canvas 管理員設定之前，讓您的組織中組織 Microsoft Office 365 系統管理員核准的畫布 Azure 應用程式的 **Microsoft Teams 同步處理畫布** Microsoft Azure。</span><span class="sxs-lookup"><span data-stu-id="31ff7-113">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="31ff7-114">登入畫布。</span><span class="sxs-lookup"><span data-stu-id="31ff7-114">Sign in to Canvas.</span></span>

2. <span data-ttu-id="31ff7-115">選取全域導覽中的 [ **管理** ] 連結，然後選取您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="31ff7-115">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="31ff7-116">在 [系統 **管理] 導覽** 中，選取 [**設定**] 連結，然後選取 [整合] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="31ff7-116">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="31ff7-117">開啟開啟開啟的開啟以啟用 Microsoft Teams 同步處理。</span><span class="sxs-lookup"><span data-stu-id="31ff7-117">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![團隊-同步處理](media/teams-sync.png)

5. <span data-ttu-id="31ff7-119">輸入您的 Microsoft 租使用者名稱和登入屬性。</span><span class="sxs-lookup"><span data-stu-id="31ff7-119">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="31ff7-120">login 屬性將用於將 Canvas 使用者與 Azure Active Directory 使用者關聯。</span><span class="sxs-lookup"><span data-stu-id="31ff7-120">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="31ff7-121">選取 [**更新設定** 完畢之後。</span><span class="sxs-lookup"><span data-stu-id="31ff7-121">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="31ff7-122">若要核准對畫布的 **Microsoft Teams-Sync-canvas** Azure app 的存取權，請選取 [**授與承租人存取** 連結]。</span><span class="sxs-lookup"><span data-stu-id="31ff7-122">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="31ff7-123">您將會重新導向至 Microsoft Identity Platform 系統管理員同意端點。</span><span class="sxs-lookup"><span data-stu-id="31ff7-123">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![許可權](media/permissions.png)

8. <span data-ttu-id="31ff7-125">選取 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="31ff7-125">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="31ff7-126">畫布管理員</span><span class="sxs-lookup"><span data-stu-id="31ff7-126">Canvas Admin</span></span>

<span data-ttu-id="31ff7-127">設定 Microsoft Teams LTI 1.3 整合。</span><span class="sxs-lookup"><span data-stu-id="31ff7-127">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="31ff7-128">做為畫布管理員時，您需要在環境內新增 Microsoft Teams 類別 LTI 應用程式。</span><span class="sxs-lookup"><span data-stu-id="31ff7-128">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="31ff7-129">請記下應用程式的 LTI 用戶端識別碼。</span><span class="sxs-lookup"><span data-stu-id="31ff7-129">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="31ff7-130">Microsoft Teams 類別-170000000000570</span><span class="sxs-lookup"><span data-stu-id="31ff7-130">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="31ff7-131">存取 **管理員設定**  >  **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="31ff7-131">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="31ff7-132">選取 [ **+ App** ]，以新增 Teams LTI 應用程式。</span><span class="sxs-lookup"><span data-stu-id="31ff7-132">Select **+ App** to add the Teams LTI apps.</span></span>

   ![外部應用程式](media/external-apps.png)

3. <span data-ttu-id="31ff7-134">選取 [ **依用戶端識別碼** ] 設定類型。</span><span class="sxs-lookup"><span data-stu-id="31ff7-134">Select **By Client ID** for configuration type.</span></span>

   ![新增應用程式](media/add-app.png)

4. <span data-ttu-id="31ff7-136">輸入提供的用戶端識別碼，然後選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="31ff7-136">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="31ff7-137">您會注意到用戶端識別碼的 Microsoft Teams 類別 LTI 應用程式名稱，以確認。</span><span class="sxs-lookup"><span data-stu-id="31ff7-137">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="31ff7-138">選取 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="31ff7-138">Select **Install**.</span></span>

   <span data-ttu-id="31ff7-139">Microsoft Teams 類別 LTI 應用程式將會新增至外部應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="31ff7-139">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a><span data-ttu-id="31ff7-140">為 Canvas 課程啟用 LTI 應用程式</span><span class="sxs-lookup"><span data-stu-id="31ff7-140">Enabling the LTI app for Canvas courses</span></span>

<span data-ttu-id="31ff7-141">若要在課程內使用 LTI 應用程式，Canvas 課程的指導員必須啟用整合同步。每門課程都必須由指導員啟用，以供建立相對應的團隊。小組建立沒有全域機制。</span><span class="sxs-lookup"><span data-stu-id="31ff7-141">To use the LTI app within a course, an instructor of the Canvas course must enable integrations sync. Each course must be enabled by an instructor for a corresponding team to be created; there is no global mechanism for teams creation.</span></span> <span data-ttu-id="31ff7-142">這是設計為防止不想要建立的小組的預防措施。</span><span class="sxs-lookup"><span data-stu-id="31ff7-142">This is designed as a precautionary measure to prevent unwanted teams from being created.</span></span>

<span data-ttu-id="31ff7-143">請參閱教師的教師 [檔](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) ，以針對每門課程啟用 LTI 應用程式，並完成整合安裝。</span><span class="sxs-lookup"><span data-stu-id="31ff7-143">Refer your instructors to the [educator documentation](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI app for each course and completing the integration setup.</span></span>
