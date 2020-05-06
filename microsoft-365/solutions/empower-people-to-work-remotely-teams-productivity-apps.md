---
title: 4. 部署遠端工作者生產力應用程式和服務
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: 讓您的使用者透過 Teams、Exchange、SharePoint 和其他 Microsoft 365 服務提高生產力。
ms.openlocfilehash: dddc3cac8a6cb955e8a337eed07279ba75c029aa
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002764"
---
# <a name="4-deploy-remote-worker-productivity-apps-and-services"></a><span data-ttu-id="0e313-103">4. 部署遠端工作者生產力應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="0e313-103">4. Deploy remote worker productivity apps and services</span></span>

<span data-ttu-id="0e313-104">為提高生產力，人員之間必須能夠溝通並共同作業。</span><span class="sxs-lookup"><span data-stu-id="0e313-104">To be productive, people need to communicate and collaborate with one another.</span></span> <span data-ttu-id="0e313-105">他們需要開會、透過語音和文字交談、建立新內容、共用資訊和檔案、交換電子郵件，以及管理行事曆和工作。</span><span class="sxs-lookup"><span data-stu-id="0e313-105">They need to meet, chat by voice and text, create new content and share information and files, exchange email, and manage calendars and tasks.</span></span> <span data-ttu-id="0e313-106">Microsoft 365 為這些關鍵功能提供雲端服務：</span><span class="sxs-lookup"><span data-stu-id="0e313-106">Microsoft 365 provides cloud-based services for all of these key functions:</span></span>

- <span data-ttu-id="0e313-107">若要讓在不同地方工作的人員保持聯繫，請使用 Microsoft Teams，為組織、部門，以及小組和個人，提供適用於會議、交談和檔案儲存的共同交流中心。</span><span class="sxs-lookup"><span data-stu-id="0e313-107">To keep people connected while they work apart, use Microsoft Teams, which provides a common hub of communication for meetings, chats, and file storage for the organization, departments, and for small teams and individuals.</span></span> 
- <span data-ttu-id="0e313-108">若要交換電子郵件及管理行事曆、連絡人和工作，請使用 Exchange Online 和 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="0e313-108">For exchanging email and managing calendars, contacts, and tasks, use Exchange Online and the Outlook client.</span></span>
- <span data-ttu-id="0e313-109">若要儲存及共同處理檔案，請使用 SharePoint 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="0e313-109">For storing and collaborating on files, use SharePoint and OneDrive.</span></span> <span data-ttu-id="0e313-110">您可以搭配網頁瀏覽器或在 Teams 內使用這些服務。</span><span class="sxs-lookup"><span data-stu-id="0e313-110">You can use them with a web browser or within Teams.</span></span>
- <span data-ttu-id="0e313-111">若要建立新內容或共同處理現有內容，Microsoft 365 App 是安裝在您本機電腦上的 Word、PowerPoint、Excel 和 Outlook 版本，而且會收到持續的功能和安全性更新。</span><span class="sxs-lookup"><span data-stu-id="0e313-111">For creating new content or collaborating on existing content, Microsoft 365 Apps are versions of Word, PowerPoint, Excel, and Outlook that are installed on your local computer and receive ongoing feature and security updates.</span></span>

## <a name="keep-people-connected-with-microsoft-teams"></a><span data-ttu-id="0e313-112">讓人員透過 Microsoft Teams 保持聯繫</span><span class="sxs-lookup"><span data-stu-id="0e313-112">Keep people connected with Microsoft Teams</span></span>

<span data-ttu-id="0e313-113">Teams 可讓您在同一個地方交談、開會、通話和共同作業。</span><span class="sxs-lookup"><span data-stu-id="0e313-113">Teams allows you to chat, meet, call, and collaborate all in one place.</span></span> <span data-ttu-id="0e313-114">數百萬個人每天都在 Teams 中完成自己的工作，因為此工具可將您從遠端工作所需的一切都整合到一個中樞，以進行團隊作業。</span><span class="sxs-lookup"><span data-stu-id="0e313-114">Millions of people get their work done in Teams every day because it brings together everything you need to work remotely into a hub for teamwork.</span></span> 

<span data-ttu-id="0e313-115">您可以使用[本文](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams)作為使用 Teams 支援遠端工作者的指導方針。</span><span class="sxs-lookup"><span data-stu-id="0e313-115">You can use [this article](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams) for guidance on supporting your remote workers with Teams.</span></span> 

### <a name="chat-and-conversations"></a><span data-ttu-id="0e313-116">聊天和交談</span><span class="sxs-lookup"><span data-stu-id="0e313-116">Chat and conversations</span></span>

<span data-ttu-id="0e313-117">聊天和往來交談位於 Teams 中央，可支援個別的一對一聊天和群組聊天與交談。</span><span class="sxs-lookup"><span data-stu-id="0e313-117">Chat and threaded conversations are at the center of Teams with support for individual 1:1 chats and group chats and conversations.</span></span> <span data-ttu-id="0e313-118">遠端工作者可以使用群組聊天或一對一訊息中的 GIF、貼紙和表情圖示來分享資訊、觀點和個性。</span><span class="sxs-lookup"><span data-stu-id="0e313-118">Remote workers can share information, opinions, and personality by using gifs, stickers, and emojis in group chats or one-to-one messages.</span></span>

### <a name="meetings-and-conferencing"></a><span data-ttu-id="0e313-119">會議和召集會議</span><span class="sxs-lookup"><span data-stu-id="0e313-119">Meetings and conferencing</span></span> 

<span data-ttu-id="0e313-120">Teams 當然可以協助您維護與遠端工作者之間的溝通與資訊共用，尤其是支援多達 250 人的會議。</span><span class="sxs-lookup"><span data-stu-id="0e313-120">Teams can certainly help maintain communications and information sharing with remote workers, especially with meetings that support up to 250 people.</span></span> <span data-ttu-id="0e313-121">Teams 會議可與組織內外的人員進行互動式共同作業會議。</span><span class="sxs-lookup"><span data-stu-id="0e313-121">Teams meetings enable interactive, collaborative meetings with people inside and outside your organization.</span></span> <span data-ttu-id="0e313-122">遠端工作者可以使用 Teams 會議進行日常活動，包括週期性的專案檢查點、跟進同事的進度、集思廣益的會議，以及方便與客戶交談。</span><span class="sxs-lookup"><span data-stu-id="0e313-122">Remote workers can use Teams meetings for day-to-day activities including recurring project checkpoints, catching-up with colleagues, brainstorming sessions, and facilitating conversations with customers.</span></span> 

### <a name="calling"></a><span data-ttu-id="0e313-123">通話</span><span class="sxs-lookup"><span data-stu-id="0e313-123">Calling</span></span>

<span data-ttu-id="0e313-124">Teams 支援在使用者甚至是使用同盟的其他組織之間進行直接 VoIP 通話。</span><span class="sxs-lookup"><span data-stu-id="0e313-124">Teams supports direct VoIP calling between users and even other organizations using federation.</span></span> <span data-ttu-id="0e313-125">其與會議使用相同的轉碼器，且不需要額外的 PSTN 費用，就能在全球提供卓越的音訊。</span><span class="sxs-lookup"><span data-stu-id="0e313-125">It uses the same codecs as meetings and provide great audio world-wide without additional PSTN charges.</span></span> <span data-ttu-id="0e313-126">不過，有些使用者可能需要專用的電話號碼，才能在遠端工作時撥打外部電話。</span><span class="sxs-lookup"><span data-stu-id="0e313-126">However, some users may need a dedicated phone number to take external calls when working remotely.</span></span> <span data-ttu-id="0e313-127">Teams 可以為這些使用者快速提供雲端電話服務，撥打及接聽電話。</span><span class="sxs-lookup"><span data-stu-id="0e313-127">Teams can quickly provide cloud phone service for these users to make and receive phone calls.</span></span>

### <a name="apps-and-workflows"></a><span data-ttu-id="0e313-128">應用程式和工作流程</span><span class="sxs-lookup"><span data-stu-id="0e313-128">Apps and workflows</span></span>

<span data-ttu-id="0e313-129">Teams 為應用程式和工作流程提供一個平台，您可以從電腦版、網頁版和行動版的 Teams 存取這個平台。</span><span class="sxs-lookup"><span data-stu-id="0e313-129">Teams provides a platform for apps and workflows that can be accessed from the desktop, web, and mobile versions of Teams.</span></span> <span data-ttu-id="0e313-130">Teams 提供數百個由 Microsoft 發行的應用程式和第三方應用程式，以吸引使用者、支援生產力，並將常用的商務服務整合到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="0e313-130">Teams provides hundreds of apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="0e313-131">使用者和系統管理員也可以使用低程式碼 Power Apps 和 Power Automate 開發工具，為 Teams 建立自訂的應用程式和自動化的工作流程。</span><span class="sxs-lookup"><span data-stu-id="0e313-131">Users and Admins can also create custom apps and automated workflows for Teams using the low-code Power Apps and Power Automate development tools.</span></span>

<span data-ttu-id="0e313-132">應用程式和工作流程可以透過收集和共用關鍵資訊、將重複的工作自動化，並允許其與互動式 Bot 交談，讓遠端工作者在 Teams 中更具生產力。</span><span class="sxs-lookup"><span data-stu-id="0e313-132">Apps and workflows let remote workers be more productive in Teams, by collecting and sharing critical information, automating repetitive tasks, and allowing them to chat with interactive bot.</span></span> <span data-ttu-id="0e313-133">將應用程式釘選到頻道或 Teams 應用程式列，可讓使用者在相關空間中輕鬆存取這些應用程式，而且系統管理員可以釘選應用程式，以便對每個人都應該使用的應用程式，提高其認知度和採用率。</span><span class="sxs-lookup"><span data-stu-id="0e313-133">Pinning apps to a channel or the Teams app bar is a great way for users to make these apps easily accessible in a relevant space, and admins can pin apps to drive awareness and adoption of the apps that everyone should be using.</span></span>

## <a name="exchange-email-and-manage-calendars-contacts-and-tasks-with-exchange-online-and-outlook"></a><span data-ttu-id="0e313-134">使用 Exchange Online 和 Outlook 交換電子郵件並管理行事曆、連絡人和工作</span><span class="sxs-lookup"><span data-stu-id="0e313-134">Exchange email and manage calendars, contacts, and tasks with Exchange Online and Outlook</span></span>

<span data-ttu-id="0e313-135">遠端工作者可以透過 Outlook，在同一個地方使用電子郵件、行事曆、連絡人、工作等等，隨時保持聯繫並井井有條。</span><span class="sxs-lookup"><span data-stu-id="0e313-135">With Outlook, remote workers can stay connected and organized with email, calendars, contacts, tasks, and more—together in one place.</span></span> <span data-ttu-id="0e313-136">Outlook 可以根據與您相關的內容，協助您隨時掌握進度並排列優先順序。</span><span class="sxs-lookup"><span data-stu-id="0e313-136">Outlook helps you stay on track and prioritize your day based on what’s relevant to you.</span></span> <span data-ttu-id="0e313-137">Outlook 可讓您直接從 OneDrive 共用附件、規劃並加入 Teams 會議、查看和共用行事曆，以及為其他人提供委派權限。</span><span class="sxs-lookup"><span data-stu-id="0e313-137">Outlook enables you to share attachments right from OneDrive, plan and join Teams meetings, view and share calendars, and provide delegate permissions to others.</span></span> <span data-ttu-id="0e313-138">了解公司和個人承諾中接下來將要發生的事情，以及需要注意的事情，可以協助遠端工作者將重點放在重要的工作上。</span><span class="sxs-lookup"><span data-stu-id="0e313-138">Knowing what’s coming up next across both work and personal commitments and what needs attention can help remote workers focus on what matters.</span></span> <span data-ttu-id="0e313-139">Outlook 可為遠端工作者提供實用的方式來管理其時間，並能輕鬆地找到所需的資訊，包括檔案、組織中的人員等等。</span><span class="sxs-lookup"><span data-stu-id="0e313-139">Outlook provides helpful ways for remote workers to manage their time and to find what they need easily, including files, people in the organization, and more.</span></span> 

## <a name="store-and-collaborate-on-files-with-sharepoint-online-and-onedrive"></a><span data-ttu-id="0e313-140">使用 SharePoint Online 和 OneDrive 儲存和共同處理檔案</span><span class="sxs-lookup"><span data-stu-id="0e313-140">Store and collaborate on files with SharePoint Online and OneDrive</span></span>

<span data-ttu-id="0e313-141">對於內容共同作業，遠端工作者可以使用 SharePoint Online 和 OneDrive 資料夾作為雲端中用來儲存和共用檔案、共同撰寫、溝通及共同作業的集中位置。</span><span class="sxs-lookup"><span data-stu-id="0e313-141">For content collaboration, remote workers can use SharePoint Online and OneDrive folders as a central place in the cloud to store and share files, co-author, communicate, and collaborate.</span></span> <span data-ttu-id="0e313-142">遠端工作者可以從網頁瀏覽器、Teams 和 Office 應用程式的任何位置安全地工作。</span><span class="sxs-lookup"><span data-stu-id="0e313-142">Remote workers can securely work from anywhere from a web browser, from Teams, and from Office apps.</span></span>

## <a name="create-and-collaborate-on-content-with-microsoft-365-apps"></a><span data-ttu-id="0e313-143">使用 Microsoft 365 Apps 建立並共同處理內容</span><span class="sxs-lookup"><span data-stu-id="0e313-143">Create and collaborate on content with Microsoft 365 Apps</span></span>

<span data-ttu-id="0e313-144">Microsoft 365 Apps 對於企業而言，是最具生產力且最安全的 Office 體驗，可讓使用者隨時隨地順利地共同作業。</span><span class="sxs-lookup"><span data-stu-id="0e313-144">Microsoft 365 Apps is the most productive and most secure Office experience for enterprises, allowing people to work together seamlessly from anywhere, anytime.</span></span> <span data-ttu-id="0e313-145">遠端工作者可以同時與多人共同處理文件、即時查看編輯及變更，並與其他人在任何筆記型電腦、電腦或行動裝置上共同撰寫。</span><span class="sxs-lookup"><span data-stu-id="0e313-145">Remote workers can collaborate on a document with multiple people simultaneously, see edits and changes in real time, and coauthor with others on any laptop, PC, or mobile device.</span></span>

## <a name="admin-technical-resources-for-productivity-apps-and-services"></a><span data-ttu-id="0e313-146">適用於生產力應用程式和服務的系統管理技術資源</span><span class="sxs-lookup"><span data-stu-id="0e313-146">Admin technical resources for productivity apps and services</span></span>

- [<span data-ttu-id="0e313-147">支援使用 Microsoft Teams 的遠端工作者</span><span class="sxs-lookup"><span data-stu-id="0e313-147">Support remote workers using Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams)
- [<span data-ttu-id="0e313-148">Teams 客戶成功套件下載</span><span class="sxs-lookup"><span data-stu-id="0e313-148">Teams Customer Success Kit download</span></span>](https://www.microsoft.com/download/details.aspx?id=54244)
- [<span data-ttu-id="0e313-149">推動 Teams 採用的工具</span><span class="sxs-lookup"><span data-stu-id="0e313-149">Tools for driving Teams adoption</span></span>](https://docs.microsoft.com/microsoftteams/adopt-tools-and-downloads) 
- <span data-ttu-id="0e313-150">[建立 Microsoft Teams 的變更管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="0e313-150">[Create a change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)</span></span>
- [<span data-ttu-id="0e313-151">擁有三層防護的 Teams</span><span class="sxs-lookup"><span data-stu-id="0e313-151">Teams with three tiers of protection</span></span>](configure-teams-three-tiers-protection.md)

- [<span data-ttu-id="0e313-152">在 Office 和 Office 365 上訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="0e313-152">Train your users on Office and Office 365</span></span>](https://support.office.com/article/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c2)
- [<span data-ttu-id="0e313-153">使用網頁版 Office</span><span class="sxs-lookup"><span data-stu-id="0e313-153">Use Office for the web</span></span>](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)

## <a name="next-step"></a><span data-ttu-id="0e313-154">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0e313-154">Next step</span></span>

<span data-ttu-id="0e313-155">繼續進行[步驟 5](empower-people-to-work-remotely-communication-venues.md)建立能夠滿足 COVID-19 危機獨特需求的其他通訊地點。</span><span class="sxs-lookup"><span data-stu-id="0e313-155">Continue with [Step 5](empower-people-to-work-remotely-communication-venues.md) to create additional communication venues that serve the unique requirements of the COVID-19 crisis.</span></span>
