---
title: LTI 應用程式的簡介
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman, sovaish
ms.date: 06/15/2021
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- M365-modern-desktop
localization_priority: None
description: 瞭解 Learning 工具互通性 (LTI) M365 中的 LTI Office 應用程式，以及如何在將 Office 應用程式整合至 Learning 管理系統 (LMS) 時，協助進行教育。
ms.openlocfilehash: 34956eac57a7e3af44ca1c8cf8ae2714327e3e96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322338"
---
# <a name="integrating-microsoft-products-with-your-learning-management-system-lms"></a><span data-ttu-id="ae726-103">將 Microsoft 產品與您的 Learning 管理系統整合 (LMS) </span><span class="sxs-lookup"><span data-stu-id="ae726-103">Integrating Microsoft products with your Learning Management System (LMS)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae726-104">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="ae726-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ae726-105">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="ae726-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

- [<span data-ttu-id="ae726-106">OneDrive具有畫布的 LTI</span><span class="sxs-lookup"><span data-stu-id="ae726-106">OneDrive LTI with Canvas</span></span>](#onedrive-lti-with-canvas)
- [<span data-ttu-id="ae726-107">Teams使用畫布的會議</span><span class="sxs-lookup"><span data-stu-id="ae726-107">Teams Meetings LTI with Canvas</span></span>](#teams-meetings-lti-with-canvas)
- [<span data-ttu-id="ae726-108">Teams類 LTI</span><span class="sxs-lookup"><span data-stu-id="ae726-108">Teams Classes LTI</span></span>](#teams-classes-lti)

<span data-ttu-id="ae726-109">Microsoft 教育和協力廠商合作夥伴會瞭解教授和教學的流量與方案界限的交叉。</span><span class="sxs-lookup"><span data-stu-id="ae726-109">Microsoft Education and our third-party partners understand that the flow of teaching and learning invariably crosses solution boundaries.</span></span> <span data-ttu-id="ae726-110">我們正在努力提供更順暢的體驗，讓教育人員和學員專注于目標，而不需要 juggle 工具。</span><span class="sxs-lookup"><span data-stu-id="ae726-110">We're working on providing more seamless experiences, keeping educators and learners focused on their goals, rather than having to juggle tools.</span></span> <span data-ttu-id="ae726-111">我們會在教學及教學中的地方整合 Microsoft 產品，包括 Learning 管理系統 (LMS) 。</span><span class="sxs-lookup"><span data-stu-id="ae726-111">We're integrating Microsoft products wherever teaching and learning occurs, including within and alongside Learning Management Systems (LMS).</span></span> <span data-ttu-id="ae726-112">我們已與 LMS 協力廠商合作，使用[Learning 工具互通性 (LTI) standard](https://www.imsglobal.org/activity/learning-tools-interoperability) ，建立工具套件，使 Microsoft 直接融入您的 LMS。</span><span class="sxs-lookup"><span data-stu-id="ae726-112">We've worked with our LMS partners to create a suite of tools using the [Learning Tools Interoperability (LTI) standard](https://www.imsglobal.org/activity/learning-tools-interoperability) that brings the best of Microsoft directly into your LMS.</span></span>

<span data-ttu-id="ae726-113">這些工具組括新的 OneDrive LTI 應用程式、新的 Teams 會議 lti 應用程式，以及新的類別 Teams LTI 應用程式。</span><span class="sxs-lookup"><span data-stu-id="ae726-113">These tools include a new OneDrive LTI app, a new Teams Meetings LTI app, and a new Class Teams LTI app.</span></span> <span data-ttu-id="ae726-114">這些新工具非常安全，而且完全相容 LTI 1.3 和 LTI 優勢標準。</span><span class="sxs-lookup"><span data-stu-id="ae726-114">These new tools are highly secure and fully compatible with LTI 1.3 and LTI Advantage standards.</span></span> <span data-ttu-id="ae726-115">OneDrive LTI 應用程式可讓教師和學生將 OneDrive 雲端儲存區和 Office 365 檔案直接移至 LMS 中的工作分派和內容建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="ae726-115">The OneDrive LTI app allows educators and students to bring OneDrive cloud storage and Office 365 files directly into assignment and content creation workflows within an LMS.</span></span> <span data-ttu-id="ae726-116">Teams 會議 LTI 應用程式可讓教師和學生從其 LMS 中的會議中心管理、排程和存取其 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="ae726-116">The Teams Meetings LTI app allows educators and students to manage, schedule, and access their Teams Meetings from within a meetings hub in their LMS.</span></span> <span data-ttu-id="ae726-117">Class Teams LTI 應用程式可讓教師使用 lms 課程包含每日名單更新，在 lms 內為其課程建立小組。</span><span class="sxs-lookup"><span data-stu-id="ae726-117">The Class Teams LTI app allows educators to create a team for their course within their LMS using the LMS course roster with daily roster updates.</span></span> <span data-ttu-id="ae726-118">然後，學員可以從 LMS 中存取小組許可權。</span><span class="sxs-lookup"><span data-stu-id="ae726-118">Students can then access the team right from within the LMS.</span></span> <span data-ttu-id="ae726-119">我們很喜歡將這些新工具帶入客戶，並根據您的意見反應繼續改進我們的解決方案。</span><span class="sxs-lookup"><span data-stu-id="ae726-119">We are excited to bring these new tools to customers and continue to improve our solutions according to your feedback.</span></span>

## <a name="onedrive-lti-with-canvas"></a><span data-ttu-id="ae726-120">OneDrive具有畫布的 LTI</span><span class="sxs-lookup"><span data-stu-id="ae726-120">OneDrive LTI with Canvas</span></span>

<span data-ttu-id="ae726-121">若要深入瞭解，請參閱使用 Microsoft OneDrive 與 Learning 管理系統 (LMS) 。</span><span class="sxs-lookup"><span data-stu-id="ae726-121">Learn more about using Microsoft OneDrive with your Learning Management System (LMS).</span></span>

- <span data-ttu-id="ae726-122">**將 Microsoft Office 365 直接帶入您的工作流程中**</span><span class="sxs-lookup"><span data-stu-id="ae726-122">**Brings Microsoft Office 365 directly into your workflows**</span></span>

<span data-ttu-id="ae726-123">Microsoft OneDrive LTI 應用程式會與您的 LMS 整合，以將 Microsoft OneDrive 和 Microsoft Office 365 直接移至最重要的工作流程中，包括：</span><span class="sxs-lookup"><span data-stu-id="ae726-123">The Microsoft OneDrive LTI app integrates with your LMS to bring Microsoft OneDrive and Microsoft Office 365 directly into your most important workflows that include:</span></span>

- <span data-ttu-id="ae726-124">附加資源及組織內容。</span><span class="sxs-lookup"><span data-stu-id="ae726-124">Attaching resources and organizing content.</span></span>
- <span data-ttu-id="ae726-125">啟動共同作業檔。</span><span class="sxs-lookup"><span data-stu-id="ae726-125">Starting collaborative documents.</span></span>
- <span data-ttu-id="ae726-126">建立及評分工作分派。</span><span class="sxs-lookup"><span data-stu-id="ae726-126">Creating and grading assignments.</span></span>

- <span data-ttu-id="ae726-127">**安全且完全符合最新的 LTI 標準**</span><span class="sxs-lookup"><span data-stu-id="ae726-127">**Secure and fully compliant with latest LTI standards**</span></span>

<span data-ttu-id="ae726-128">Microsoft OneDrive lti 應用程式與 lti 1.3 和 lti 優勢相容。</span><span class="sxs-lookup"><span data-stu-id="ae726-128">The Microsoft OneDrive LTI App is compatible with LTI 1.3 and LTI Advantage.</span></span> <span data-ttu-id="ae726-129">這種優點可提供高安全性和緊密整合的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="ae726-129">This advantage allows for a highly secure and tightly integrated user experience.</span></span>

- <span data-ttu-id="ae726-130">**新式和豐富的使用者體驗**</span><span class="sxs-lookup"><span data-stu-id="ae726-130">**Modern and Rich User Experience**</span></span>

<span data-ttu-id="ae726-131">Microsoft OneDrive LTI 應用程式會將 Microsoft 的最佳許可權帶入您的 LMS 體驗。</span><span class="sxs-lookup"><span data-stu-id="ae726-131">The Microsoft OneDrive LTI App brings the best of Microsoft right into your LMS experience.</span></span> <span data-ttu-id="ae726-132">在您的 LMS 中，我們會透過提供更現代的使用者體驗，以改善您的 LMS 中現有的 Office 365 整合，並以全新且展開的 Microsoft OneDrive 檔案選擇器和更豐富的編輯體驗來改善 Office 檔案。</span><span class="sxs-lookup"><span data-stu-id="ae726-132">We're improving upon the existing Office 365 integration in your LMS by delivering a more modern user experience, complete with a new and expanded Microsoft OneDrive file picker and richer editing experiences for Office files.</span></span> <span data-ttu-id="ae726-133">microsoft 也會完全擁有即將進行的 Microsoft OneDrive LTI 應用程式，這表示您將永遠能夠自動從 Microsoft 取得最新和最大的。</span><span class="sxs-lookup"><span data-stu-id="ae726-133">Microsoft will also fully own the Microsoft OneDrive LTI App going forward, which means you’ll always get the latest and greatest from Microsoft automatically.</span></span>

<span data-ttu-id="ae726-134">Microsoft OneDrive LTI 應用程式可讓您：</span><span class="sxs-lookup"><span data-stu-id="ae726-134">The Microsoft OneDrive LTI App allows you to:</span></span>

- <span data-ttu-id="ae726-135">附加 Office 365 檔案（包括 Word 檔、PowerPoint 簡報及從富內容編輯器中 Excel）。</span><span class="sxs-lookup"><span data-stu-id="ae726-135">Attach Office 365 files including Word documents, PowerPoint presentations, and Excel from the Rich Content Editor.</span></span>
- <span data-ttu-id="ae726-136">散佈 Office 365 雲端指派。</span><span class="sxs-lookup"><span data-stu-id="ae726-136">Distribute Office 365 cloud assignments.</span></span>
- <span data-ttu-id="ae726-137">查看和組織您的個人和課程 Microsoft OneDrive 檔案。</span><span class="sxs-lookup"><span data-stu-id="ae726-137">View and organize your personal and course Microsoft OneDrive files.</span></span>
- <span data-ttu-id="ae726-138">建立共同作業：課程成員可以即時在共用檔上共同作業。</span><span class="sxs-lookup"><span data-stu-id="ae726-138">Create collaborations where course members can work together on shared documents in real time.</span></span>
- <span data-ttu-id="ae726-139">存取多個 Microsoft OneDrive 帳戶，包括個人和學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="ae726-139">Access multiple Microsoft OneDrive accounts, including personal and school accounts.</span></span>
- <span data-ttu-id="ae726-140">將 Office 365 檔案與您的課程模組整合。</span><span class="sxs-lookup"><span data-stu-id="ae726-140">Integrate Office 365 files with your course modules.</span></span>
- <span data-ttu-id="ae726-141">使用您的 Microsoft 帳戶進行單一登入與您的 LMS。</span><span class="sxs-lookup"><span data-stu-id="ae726-141">Use your Microsoft account for single sign-on with your LMS.</span></span>

<span data-ttu-id="ae726-142">如需設定步驟，請參閱[Use Microsoft OneDrive LTI with Canvas](use-onedrive-with-lms.md)。</span><span class="sxs-lookup"><span data-stu-id="ae726-142">For configuration steps, see [Use Microsoft OneDrive LTI with Canvas](use-onedrive-with-lms.md).</span></span>

## <a name="teams-lti-apps"></a><span data-ttu-id="ae726-143">TeamsLTI 應用程式</span><span class="sxs-lookup"><span data-stu-id="ae726-143">Teams LTI apps</span></span>

### <a name="teams-meetings-lti-with-canvas"></a><span data-ttu-id="ae726-144">Teams使用畫布的會議</span><span class="sxs-lookup"><span data-stu-id="ae726-144">Teams Meetings LTI with Canvas</span></span>

<span data-ttu-id="ae726-145">Microsoft Teams 會議 LTI 應用程式可協助系統管理員將 Teams 會議納入教育機構的 LMS 課程。</span><span class="sxs-lookup"><span data-stu-id="ae726-145">Microsoft Teams meetings LTI app helps admins incorporate Teams meetings into their educational institution's LMS course.</span></span> <span data-ttu-id="ae726-146">教育版和學生可以查看過去和即將舉行的會議、排程個別或週期性的會議，以及加入課程的相關小組會議，全部都是在 LMS 內。</span><span class="sxs-lookup"><span data-stu-id="ae726-146">Educators and students can view past and upcoming meetings, schedule individual or recurring meetings, and join team meetings related to the course, all from within their LMS.</span></span>

<span data-ttu-id="ae726-147">如需設定步驟，請參閱[Use Microsoft Teams meeting with a Canvas](teams-meetings-with-canvas.md)。</span><span class="sxs-lookup"><span data-stu-id="ae726-147">For configuration steps, see [Use Microsoft Teams meetings with Canvas](teams-meetings-with-canvas.md).</span></span>

### <a name="teams-classes-lti"></a><span data-ttu-id="ae726-148">Teams類 LTI</span><span class="sxs-lookup"><span data-stu-id="ae726-148">Teams Classes LTI</span></span>

<span data-ttu-id="ae726-149">Microsoft Teams 類別 LTI 應用程式可協助教育者和學生流覽其 LMS 和 Teams。</span><span class="sxs-lookup"><span data-stu-id="ae726-149">The Microsoft Teams classes LTI app helps educators and students navigate between their LMS and Teams.</span></span> <span data-ttu-id="ae726-150">使用者可以直接從 LMS 中存取與其課程相關聯的類別小組。</span><span class="sxs-lookup"><span data-stu-id="ae726-150">Users can access their class teams associated with their course directly from within their LMS.</span></span> <span data-ttu-id="ae726-151">您可以在下面找到設定步驟：</span><span class="sxs-lookup"><span data-stu-id="ae726-151">You can find configuration steps below:</span></span>

- <span data-ttu-id="ae726-152">使用 **畫布的 Teams 類別**[使用具有畫布 Microsoft Teams 類別](teams-classes-with-canvas.md)。</span><span class="sxs-lookup"><span data-stu-id="ae726-152">**Teams Classes LTI with Canvas** [Use Microsoft Teams classes with Canvas](teams-classes-with-canvas.md).</span></span>

- <span data-ttu-id="ae726-153">使用 **blackboard 的 Teams 類別**[使用具有 blackboard 的 Microsoft Teams 類別瞭解超](teams-classes-with-blackboard.md)</span><span class="sxs-lookup"><span data-stu-id="ae726-153">**Teams Classes LTI with Blackboard** [Use Microsoft Teams classes with Blackboard Learn Ultra](teams-classes-with-blackboard.md)</span></span>
