---
title: 使用具有畫布的 Microsoft Teams 類別
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
description: 將 Microsoft Teams 類別與畫布整合
ms.openlocfilehash: 1a16d6a4f5e0cfbb592c335163bb4e33fd3c1301
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821881"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="84576-103">使用具有畫布的 Microsoft Teams 類別</span><span class="sxs-lookup"><span data-stu-id="84576-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84576-104">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="84576-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="84576-105">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="84576-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="84576-106">Microsoft Teams 類別是 (LTI) 應用程式的學習工具互通性，可協助教育者和學生輕鬆流覽其教學管理系統 (LMS) 和 Teams。</span><span class="sxs-lookup"><span data-stu-id="84576-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="84576-107">使用者可以直接從 LMS 中存取與其課程相關聯的類別小組。</span><span class="sxs-lookup"><span data-stu-id="84576-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="84576-108">Microsoft Office 365管理</span><span class="sxs-lookup"><span data-stu-id="84576-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="84576-109">在管理 Instructure 畫布內的 Microsoft Teams 整合之前，請務必在完成 canvas 管理員設定之前，讓您的組織中組織 Microsoft Office 365 系統管理員核准的畫布 Azure 應用程式的 **Microsoft Teams 同步處理畫布** Microsoft Azure。</span><span class="sxs-lookup"><span data-stu-id="84576-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="84576-110">登入畫布。</span><span class="sxs-lookup"><span data-stu-id="84576-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="84576-111">選取全域導覽中的 [ **管理** ] 連結，然後選取您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="84576-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="84576-112">在 [系統 **管理] 導覽** 中，選取 [**設定**] 連結，然後選取 [整合] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="84576-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="84576-113">輸入您的 Microsoft 租使用者名稱和登入屬性。</span><span class="sxs-lookup"><span data-stu-id="84576-113">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="84576-114">login 屬性將用於將 Canvas 使用者與 Azure Active Directory 使用者關聯。</span><span class="sxs-lookup"><span data-stu-id="84576-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

5. <span data-ttu-id="84576-115">選取 [**更新設定** 完畢之後。</span><span class="sxs-lookup"><span data-stu-id="84576-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="84576-116">若要核准對畫布的 **Microsoft Teams-Sync-canvas** Azure app 的存取權，請選取 [**授與承租人存取** 連結]。</span><span class="sxs-lookup"><span data-stu-id="84576-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="84576-117">您將會重新導向至 Microsoft Identity Platform 系統管理員同意端點。</span><span class="sxs-lookup"><span data-stu-id="84576-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![許可權](media/permissions.png)

7. <span data-ttu-id="84576-119">選取 [ **接受**]。</span><span class="sxs-lookup"><span data-stu-id="84576-119">Select **Accept**.</span></span>
 
8. <span data-ttu-id="84576-120">開啟開啟開啟的開啟以啟用 Microsoft Teams 同步處理。</span><span class="sxs-lookup"><span data-stu-id="84576-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![團隊-同步處理](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="84576-122">畫布管理員</span><span class="sxs-lookup"><span data-stu-id="84576-122">Canvas Admin</span></span>

<span data-ttu-id="84576-123">設定 Microsoft Teams LTI 1.3 整合。</span><span class="sxs-lookup"><span data-stu-id="84576-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="84576-124">做為畫布管理員時，您需要在環境內新增 Microsoft Teams 類別 LTI 應用程式。</span><span class="sxs-lookup"><span data-stu-id="84576-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="84576-125">請記下應用程式的 LTI 用戶端識別碼。</span><span class="sxs-lookup"><span data-stu-id="84576-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="84576-126">Microsoft Teams 類別-170000000000570</span><span class="sxs-lookup"><span data-stu-id="84576-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="84576-127">存取 **管理員設定**  >  **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="84576-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="84576-128">選取 [ **+ App** ]，以新增 Teams LTI 應用程式。</span><span class="sxs-lookup"><span data-stu-id="84576-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![外部應用程式](media/external-apps.png)

3. <span data-ttu-id="84576-130">選取 [ **依用戶端識別碼** ] 設定類型。</span><span class="sxs-lookup"><span data-stu-id="84576-130">Select **By Client ID** for configuration type.</span></span>

   ![新增應用程式](media/add-app.png)

4. <span data-ttu-id="84576-132">輸入提供的用戶端識別碼，然後選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="84576-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="84576-133">您會注意到用戶端識別碼的 Microsoft Teams 類別 LTI 應用程式名稱，以確認。</span><span class="sxs-lookup"><span data-stu-id="84576-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="84576-134">選取 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="84576-134">Select **Install**.</span></span>

   <span data-ttu-id="84576-135">Microsoft Teams 類別 LTI 應用程式將會新增至外部應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="84576-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
