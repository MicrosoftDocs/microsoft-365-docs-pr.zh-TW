---
title: 步驟 5： 部署遠端工作者生產力應用程式和服務
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 讓您的使用者透過 Teams、Exchange、SharePoint 和其他 Microsoft 365 服務提高生產力。
ms.openlocfilehash: c56deb091078fb1917bc1060aa366da4e18bd176
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050871"
---
# <a name="step-5-deploy-remote-worker-productivity-apps-and-services"></a><span data-ttu-id="06726-104">步驟 5：</span><span class="sxs-lookup"><span data-stu-id="06726-104">Step 5.</span></span> <span data-ttu-id="06726-105">部署遠端工作者生產力應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="06726-105">Deploy remote worker productivity apps and services</span></span>

<span data-ttu-id="06726-106">為提高生產力，人員之間必須能夠溝通並共同作業。</span><span class="sxs-lookup"><span data-stu-id="06726-106">To be productive, people need to communicate and collaborate with one another.</span></span> <span data-ttu-id="06726-107">他們需要開會、透過語音和文字交談、建立新內容、共用資訊和檔案、交換電子郵件，以及管理行事曆和工作。</span><span class="sxs-lookup"><span data-stu-id="06726-107">They need to meet, chat by voice and text, create new content and share information and files, exchange email, and manage calendars and tasks.</span></span> <span data-ttu-id="06726-108">Microsoft 365 為這些關鍵功能提供雲端服務：</span><span class="sxs-lookup"><span data-stu-id="06726-108">Microsoft 365 provides cloud-based services for all of these key functions:</span></span>

| <span data-ttu-id="06726-109">IT 功能</span><span class="sxs-lookup"><span data-stu-id="06726-109">IT function</span></span> | <span data-ttu-id="06726-110">Microsoft 365 元件</span><span class="sxs-lookup"><span data-stu-id="06726-110">Microsoft 365 components</span></span> | <span data-ttu-id="06726-111">描述</span><span class="sxs-lookup"><span data-stu-id="06726-111">Description</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="06726-112">電子郵件服務</span><span class="sxs-lookup"><span data-stu-id="06726-112">Email services</span></span> | <span data-ttu-id="06726-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06726-113">Exchange Online</span></span> | <span data-ttu-id="06726-114">使用 Outlook 用戶端交換電子郵件和管理行事曆、連絡人和工作。</span><span class="sxs-lookup"><span data-stu-id="06726-114">Exchange email and manage calendars, contacts, and tasks with the Outlook client.</span></span> |
| <span data-ttu-id="06726-115">組織聊天、VoIP 和團隊型共同作業</span><span class="sxs-lookup"><span data-stu-id="06726-115">Organizational chat, voice over IP (VOIP), and team-based collaboration</span></span> | <span data-ttu-id="06726-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06726-116">Microsoft Teams</span></span> | <span data-ttu-id="06726-117">利用用於組織、部門以及小型團隊和個人的會議、聊天和檔案儲存的共同通訊中樞，讓人員在不同地方工作時也能保持連絡。</span><span class="sxs-lookup"><span data-stu-id="06726-117">Keep people connected while they work apart with a common hub of communication for meetings, chats, and file storage for the organization, departments, and for small teams and individuals.</span></span> |
| <span data-ttu-id="06726-118">內部網路網站、文件共同作業</span><span class="sxs-lookup"><span data-stu-id="06726-118">Intranet sites, document collaboration</span></span> | <span data-ttu-id="06726-119">SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="06726-119">SharePoint and OneDrive</span></span> | <span data-ttu-id="06726-120">在網頁瀏覽器或 Teams 內儲存和就檔案共同作業。</span><span class="sxs-lookup"><span data-stu-id="06726-120">Store and collaborate on files within a web browser or within Teams.</span></span> |
| <span data-ttu-id="06726-121">桌面和行動裝置 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="06726-121">Desktop and mobile device Office applications</span></span> | <span data-ttu-id="06726-122">Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="06726-122">Microsoft 365 Apps</span></span> | <span data-ttu-id="06726-123">使用安裝在您本機電腦上的 Word、PowerPoint、Excel 和 Outlook 版本，建立新內容或就現有內容共同作業，並持續收到功能和安全性更新。</span><span class="sxs-lookup"><span data-stu-id="06726-123">Create new content or collaborate on existing content with versions of Word, PowerPoint, Excel, and Outlook that are installed on your local computer and receive ongoing feature and security updates.</span></span> |
||||

![使用 Teams、Outlook、SharePoint、OneDrive 和 Microsoft 365 應用程式以保持生產力](../media/empower-people-to-work-remotely/remote-workers-productivity-grid.png)

## <a name="keep-people-connected-with-microsoft-teams"></a><span data-ttu-id="06726-125">讓人員透過 Microsoft Teams 保持聯繫</span><span class="sxs-lookup"><span data-stu-id="06726-125">Keep people connected with Microsoft Teams</span></span>

<span data-ttu-id="06726-126">Teams 可讓您在同一個地方交談、開會、通話和共同作業。</span><span class="sxs-lookup"><span data-stu-id="06726-126">Teams allows you to chat, meet, call, and collaborate all in one place.</span></span> <span data-ttu-id="06726-127">數百萬個人每天都在 Teams 中完成自己的工作，因為此工具可將您從遠端工作所需的一切都整合到一個中樞，以進行團隊作業。</span><span class="sxs-lookup"><span data-stu-id="06726-127">Millions of people get their work done in Teams every day because it brings together everything you need to work remotely into a hub for teamwork.</span></span> 

<span data-ttu-id="06726-128">如需詳細指導方針，請參閱[支援使用 Microsoft Teams 的遠端工作者](/microsoftteams/support-remote-work-with-teams)。</span><span class="sxs-lookup"><span data-stu-id="06726-128">For detailed guidance, see [Support remote workers using Microsoft Teams](/microsoftteams/support-remote-work-with-teams).</span></span> 

<span data-ttu-id="06726-129">觀看[使用 Microsoft Teams 啟用混合式工作網路廣播](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/)，以取得將 Teams 用於遠端工作的指導方針和示範。</span><span class="sxs-lookup"><span data-stu-id="06726-129">Watch the [Enabling hybrid work with Microsoft Teams webcasts](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/) for guidance and demos on using Teams for remote work.</span></span>

### <a name="chat-and-conversations"></a><span data-ttu-id="06726-130">聊天和交談</span><span class="sxs-lookup"><span data-stu-id="06726-130">Chat and conversations</span></span>

<span data-ttu-id="06726-131">聊天和往來交談位於 Teams 中央，可支援個別的一對一聊天和群組聊天與交談。</span><span class="sxs-lookup"><span data-stu-id="06726-131">Chat and threaded conversations are at the center of Teams with support for individual 1:1 chats and group chats and conversations.</span></span> <span data-ttu-id="06726-132">遠端工作者可以使用群組聊天或一對一訊息中的 GIF、貼紙和表情圖示來分享資訊、觀點和個性。</span><span class="sxs-lookup"><span data-stu-id="06726-132">Remote workers can share information, opinions, and personality by using gifs, stickers, and emojis in group chats or one-to-one messages.</span></span>

### <a name="meetings-and-conferencing"></a><span data-ttu-id="06726-133">會議和召集會議</span><span class="sxs-lookup"><span data-stu-id="06726-133">Meetings and conferencing</span></span> 

<span data-ttu-id="06726-134">Teams 當然可以協助您維護與遠端工作者之間的溝通與資訊共用，尤其是支援多達 250 人的會議。</span><span class="sxs-lookup"><span data-stu-id="06726-134">Teams can certainly help maintain communications and information sharing with remote workers, especially with meetings that support up to 250 people.</span></span> <span data-ttu-id="06726-135">Teams 會議可與組織內外的人員進行互動式共同作業會議。</span><span class="sxs-lookup"><span data-stu-id="06726-135">Teams meetings enable interactive, collaborative meetings with people inside and outside your organization.</span></span> <span data-ttu-id="06726-136">遠端工作者可以使用 Teams 會議進行日常活動，包括週期性的專案檢查點、跟進同事的進度、集思廣益的會議，以及方便與客戶交談。</span><span class="sxs-lookup"><span data-stu-id="06726-136">Remote workers can use Teams meetings for day-to-day activities including recurring project checkpoints, catching-up with colleagues, brainstorming sessions, and facilitating conversations with customers.</span></span> 

### <a name="calling"></a><span data-ttu-id="06726-137">通話</span><span class="sxs-lookup"><span data-stu-id="06726-137">Calling</span></span>

<span data-ttu-id="06726-138">Teams 支援在使用者甚至是使用同盟的其他組織之間進行直接 VoIP 通話。</span><span class="sxs-lookup"><span data-stu-id="06726-138">Teams supports direct VoIP calling between users and even other organizations using federation.</span></span> <span data-ttu-id="06726-139">其與會議使用相同的轉碼器，且不需要額外的 PSTN 費用，就能在全球提供卓越的音訊。</span><span class="sxs-lookup"><span data-stu-id="06726-139">It uses the same codecs as meetings and provide great audio world-wide without additional PSTN charges.</span></span> <span data-ttu-id="06726-140">不過，有些使用者可能需要專用的電話號碼，才能在遠端工作時撥打外部電話。</span><span class="sxs-lookup"><span data-stu-id="06726-140">However, some users may need a dedicated phone number to take external calls when working remotely.</span></span> <span data-ttu-id="06726-141">Teams 可以為這些使用者快速提供雲端電話服務，撥打及接聽電話。</span><span class="sxs-lookup"><span data-stu-id="06726-141">Teams can quickly provide cloud phone service for these users to make and receive phone calls.</span></span>

### <a name="apps-and-workflows"></a><span data-ttu-id="06726-142">應用程式和工作流程</span><span class="sxs-lookup"><span data-stu-id="06726-142">Apps and workflows</span></span>

<span data-ttu-id="06726-143">Teams 為應用程式和工作流程提供一個平台，您可以從電腦版、網頁版和行動版的 Teams 存取這個平台。</span><span class="sxs-lookup"><span data-stu-id="06726-143">Teams provides a platform for apps and workflows that can be accessed from the desktop, web, and mobile versions of Teams.</span></span> <span data-ttu-id="06726-144">Teams 提供數百個由 Microsoft 發行的應用程式和第三方應用程式，以吸引使用者、支援生產力，並將常用的商務服務整合到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="06726-144">Teams provides hundreds of apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="06726-145">使用者和系統管理員也可以使用低程式碼 Power Apps 和 Power Automate 開發工具，為 Teams 建立自訂的應用程式和自動化的工作流程。</span><span class="sxs-lookup"><span data-stu-id="06726-145">Users and Admins can also create custom apps and automated workflows for Teams using the low-code Power Apps and Power Automate development tools.</span></span>

<span data-ttu-id="06726-146">應用程式和工作流程可以透過收集和共用關鍵資訊、將重複的工作自動化，並允許其與互動式 Bot 交談，讓遠端工作者在 Teams 中更具生產力。</span><span class="sxs-lookup"><span data-stu-id="06726-146">Apps and workflows let remote workers be more productive in Teams, by collecting and sharing critical information, automating repetitive tasks, and allowing them to chat with interactive bot.</span></span> <span data-ttu-id="06726-147">將應用程式釘選到頻道或 Teams 應用程式列，可讓使用者在相關空間中輕鬆存取這些應用程式，而且系統管理員可以釘選應用程式，以便對每個人都應該使用的應用程式，提高其認知度和採用率。</span><span class="sxs-lookup"><span data-stu-id="06726-147">Pinning apps to a channel or the Teams app bar is a great way for users to make these apps easily accessible in a relevant space, and admins can pin apps to drive awareness and adoption of the apps that everyone should be using.</span></span>

## <a name="exchange-email-and-manage-calendars-contacts-and-tasks-with-exchange-online-and-outlook"></a><span data-ttu-id="06726-148">使用 Exchange Online 和 Outlook 交換電子郵件並管理行事曆、連絡人和工作</span><span class="sxs-lookup"><span data-stu-id="06726-148">Exchange email and manage calendars, contacts, and tasks with Exchange Online and Outlook</span></span>

<span data-ttu-id="06726-149">遠端工作者可以透過 Outlook，在同一個地方使用電子郵件、行事曆、連絡人、工作等等，隨時保持聯繫並井井有條。</span><span class="sxs-lookup"><span data-stu-id="06726-149">With Outlook, remote workers can stay connected and organized with email, calendars, contacts, tasks, and more—together in one place.</span></span> <span data-ttu-id="06726-150">Outlook 可以根據與您相關的內容，協助您隨時掌握進度並排列優先順序。</span><span class="sxs-lookup"><span data-stu-id="06726-150">Outlook helps you stay on track and prioritize your day based on what’s relevant to you.</span></span> <span data-ttu-id="06726-151">Outlook 可讓您直接從 OneDrive 共用附件、規劃並加入 Teams 會議、查看和共用行事曆，以及為其他人提供委派權限。</span><span class="sxs-lookup"><span data-stu-id="06726-151">Outlook enables you to share attachments right from OneDrive, plan and join Teams meetings, view and share calendars, and provide delegate permissions to others.</span></span> <span data-ttu-id="06726-152">了解公司和個人承諾中接下來將要發生的事情，以及需要注意的事情，可以協助遠端工作者將重點放在重要的工作上。</span><span class="sxs-lookup"><span data-stu-id="06726-152">Knowing what’s coming up next across both work and personal commitments and what needs attention can help remote workers focus on what matters.</span></span> <span data-ttu-id="06726-153">Outlook 可為遠端工作者提供實用的方式來管理其時間，並能輕鬆地找到所需的資訊，包括檔案、組織中的人員等等。</span><span class="sxs-lookup"><span data-stu-id="06726-153">Outlook provides helpful ways for remote workers to manage their time and to find what they need easily, including files, people in the organization, and more.</span></span> 

<span data-ttu-id="06726-154">請參閱 [本文](../security/defender-365-security/secure-email-recommended-policies.md) 以了解資料存取原則所建議使用的身分識別和裝置，並保護支援新式驗證和 [限制存取] 的組織的電子郵件和電子郵件用戶。</span><span class="sxs-lookup"><span data-stu-id="06726-154">See [this article](../security/defender-365-security/secure-email-recommended-policies.md) for the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and Conditional Access.</span></span>

## <a name="store-and-collaborate-on-files-with-sharepoint-and-onedrive"></a><span data-ttu-id="06726-155">使用 SharePoint 和 OneDrive 儲存和共同處理檔案</span><span class="sxs-lookup"><span data-stu-id="06726-155">Store and collaborate on files with SharePoint and OneDrive</span></span>

<span data-ttu-id="06726-156">對於內容共同作業，遠端工作者可以使用 SharePoint 和 OneDrive 資料夾作為雲端中用來儲存和共用檔案、共同撰寫、溝通及共同作業的集中位置。</span><span class="sxs-lookup"><span data-stu-id="06726-156">For content collaboration, remote workers can use SharePoint and OneDrive folders as a central place in the cloud to store and share files, co-author, communicate, and collaborate.</span></span> <span data-ttu-id="06726-157">遠端工作者可以從網頁瀏覽器、Teams 和 Office 應用程式的任何位置安全地工作。</span><span class="sxs-lookup"><span data-stu-id="06726-157">Remote workers can securely work from anywhere from a web browser, from Teams, and from Office apps.</span></span>

<span data-ttu-id="06726-158">您可能必須將文件從以下位置移轉至 SharePoint 或 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="06726-158">You might have to migrate your documents to SharePoint or OneDrive from:</span></span>

- [<span data-ttu-id="06726-159">SharePoint Server 小組網站</span><span class="sxs-lookup"><span data-stu-id="06726-159">SharePoint Server Team Sites</span></span>](/sharepointmigration/sp-teams-sites-migration-guide)
- [<span data-ttu-id="06726-160">MySites</span><span class="sxs-lookup"><span data-stu-id="06726-160">MySites</span></span>](/sharepointmigration/mysites-to-onedrive-migration-guide)
- [<span data-ttu-id="06726-161">檔案共用</span><span class="sxs-lookup"><span data-stu-id="06726-161">File shares</span></span>](/sharepointmigration/fileshare-to-odsp-migration-guide)
- [<span data-ttu-id="06726-162">Box</span><span class="sxs-lookup"><span data-stu-id="06726-162">Box</span></span>](/sharepointmigration/box-to-onedrive-and-sharepoint-migration-guide)

<span data-ttu-id="06726-163">若要保護 SharePoint 和 OneDrive，請參閱[此文章](../security/defender-365-security/sharepoint-file-access-policies.md)的建議身分識別和裝置存取原則。</span><span class="sxs-lookup"><span data-stu-id="06726-163">To protect SharePoint and OneDrive, see [this article](../security/defender-365-security/sharepoint-file-access-policies.md) for the recommended identity and device access policies.</span></span>

## <a name="create-and-collaborate-on-content-with-microsoft-365-apps"></a><span data-ttu-id="06726-164">使用 Microsoft 365 Apps 建立並共同處理內容</span><span class="sxs-lookup"><span data-stu-id="06726-164">Create and collaborate on content with Microsoft 365 Apps</span></span>

<span data-ttu-id="06726-165">Microsoft 365 Apps 對於企業而言，是最具生產力且安全的 Office 體驗，可讓使用者隨時隨地順利地共同作業。</span><span class="sxs-lookup"><span data-stu-id="06726-165">Microsoft 365 Apps is the most productive and secure Office experience for enterprises, allowing people to work together seamlessly from anywhere, anytime.</span></span> <span data-ttu-id="06726-166">遠端工作者可以同時與多人共同處理文件、即時查看編輯及變更，並與其他人在任何筆記型電腦、電腦或行動裝置上共同撰寫。</span><span class="sxs-lookup"><span data-stu-id="06726-166">Remote workers can collaborate on a document with multiple people simultaneously, see edits and changes in real time, and coauthor with others on any laptop, PC, or mobile device.</span></span>

<span data-ttu-id="06726-167">如需詳細資訊，請參閱 [Microsoft 365 Apps 的部署指南](/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="06726-167">For more information, see the [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

## <a name="admin-technical-resources-for-productivity-apps-and-services"></a><span data-ttu-id="06726-168">適用於生產力應用程式和服務的系統管理技術資源</span><span class="sxs-lookup"><span data-stu-id="06726-168">Admin technical resources for productivity apps and services</span></span>

- [<span data-ttu-id="06726-169">支援使用 Microsoft Teams 的遠端工作者</span><span class="sxs-lookup"><span data-stu-id="06726-169">Support remote workers using Microsoft Teams</span></span>](/microsoftteams/support-remote-work-with-teams)
- [<span data-ttu-id="06726-170">使用 Microsoft Teams 啟用混合式工作網路廣播</span><span class="sxs-lookup"><span data-stu-id="06726-170">Enabling hybrid work with Microsoft Teams webcasts</span></span>](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/)
- [<span data-ttu-id="06726-171">Teams 客戶成功套件下載</span><span class="sxs-lookup"><span data-stu-id="06726-171">Teams Customer Success Kit download</span></span>](https://www.microsoft.com/download/details.aspx?id=54244)
- [<span data-ttu-id="06726-172">推動 Teams 採用的工具</span><span class="sxs-lookup"><span data-stu-id="06726-172">Tools for driving Teams adoption</span></span>](/microsoftteams/adopt-tools-and-downloads) 
- <span data-ttu-id="06726-173">[建立 Microsoft Teams 的變更管理策略](/MicrosoftTeams/change-management-strategy) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="06726-173">[Create a change management strategy for Microsoft Teams](/MicrosoftTeams/change-management-strategy)</span></span>
- [<span data-ttu-id="06726-174">擁有三層防護的 Teams</span><span class="sxs-lookup"><span data-stu-id="06726-174">Teams with three tiers of protection</span></span>](configure-teams-three-tiers-protection.md)

## <a name="user-training-resources-for-productivity-apps-and-services"></a><span data-ttu-id="06726-175">以生產力應用程式和服務作為使用者培訓資源</span><span class="sxs-lookup"><span data-stu-id="06726-175">User training resources for productivity apps and services</span></span>

- [<span data-ttu-id="06726-176">在 Office 和 Microsoft 365 上訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="06726-176">Train your users on Office and Microsoft 365</span></span>](https://support.microsoft.com/office/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c27)
- [<span data-ttu-id="06726-177">使用網頁版 Office</span><span class="sxs-lookup"><span data-stu-id="06726-177">Use Office for the web</span></span>](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)

## <a name="next-step"></a><span data-ttu-id="06726-178">下一步</span><span class="sxs-lookup"><span data-stu-id="06726-178">Next step</span></span>

<span data-ttu-id="06726-179">[![步驟 6：訓練您的使用者並監控其是否成功](../media/empower-people-to-work-remotely/remote-workers-step-grid-6.png)](empower-people-to-work-remotely-train-monitor-usage.md)</span><span class="sxs-lookup"><span data-stu-id="06726-179">[![Step 6: Train your users and monitor their success](../media/empower-people-to-work-remotely/remote-workers-step-grid-6.png)](empower-people-to-work-remotely-train-monitor-usage.md)</span></span>

<span data-ttu-id="06726-180">如需訓練使用者並監視其是否成功，請繼續進行[步驟 6](empower-people-to-work-remotely-train-monitor-usage.md)。</span><span class="sxs-lookup"><span data-stu-id="06726-180">Continue with [Step 6](empower-people-to-work-remotely-train-monitor-usage.md) to train your users and monitor their success.</span></span>