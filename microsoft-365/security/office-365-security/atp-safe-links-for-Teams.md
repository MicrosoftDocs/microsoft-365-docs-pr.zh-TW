---
title: 用於小組、safelinks、安全連結、封鎖惡意連結、office 365 atp、小組安全連結的 ATP 安全連結，讓使用者無法按一下 [不良連結]，惡意連結
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 當您按一下時，小組現在可存取安全的連結。 不論您是使用聊天1開聊天、群組還是頻道，以及標籤式，如果您有 Office 365 ATP 的訂閱，您就能夠啟用和使用此安全功能。
ms.openlocfilehash: 07f20f0adf503e4592d2bd3f3bc9857d08a1e433
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2020
ms.locfileid: "43809000"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="8d4f5-104">Teams 中的安全連結</span><span class="sxs-lookup"><span data-stu-id="8d4f5-104">Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d4f5-105">這項功能是針對 Microsoft 小組技術採用計畫（點擊）中的客戶**公開預覽**，在2020年2月28日。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="8d4f5-106">當小組的安全連結更廣泛可用時，就會從文章中移除此附注。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="8d4f5-107">Microsoft 團隊是用來管理工作的 Microsoft 雲端式應用程式，已使用安全附件（適用于 Office 365），但在您按下時，它現在可以存取安全連結。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses Safe Attachments (for Office 365), but it will now have access to Safe Links at the time of your click.</span></span> <span data-ttu-id="8d4f5-108">不論您是使用聊天、群組聊天、頻道或標籤式，如果您有 Office 365 ATP 的訂閱，您就可以啟用和使用此安全措施。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-108">Whether you're using Chats, Group Chats, Channels, or Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span> <span data-ttu-id="8d4f5-109">若要深入了解授權需求，請參閱 [Microsoft 365 租用戶層級服務授權指導方針](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="8d4f5-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

<span data-ttu-id="8d4f5-110">以下為運作方式：</span><span class="sxs-lookup"><span data-stu-id="8d4f5-110">Here's how it works:</span></span> 

1. <span data-ttu-id="8d4f5-111">當您啟動小組應用程式時，Microsoft 365 將會檢查使用者是否屬於具有 Office 365 ATP 的組織，而且使用者屬於使用中安全連結原則的一部分，其保護為 Microsoft 團隊啟用。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-111">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="8d4f5-112">如果上述為 true，則會在聊天、群組聊天、頻道及該使用者的索引標籤中按一下時，驗證 URLs。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-112">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="8d4f5-113">使用者將體驗什麼？</span><span class="sxs-lookup"><span data-stu-id="8d4f5-113">What will users experience?</span></span> 

<span data-ttu-id="8d4f5-114">所有受保護的使用者都會有這種具有危險性的經驗 URLs：</span><span class="sxs-lookup"><span data-stu-id="8d4f5-114">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="8d4f5-115">如果從小組交談、群組聊天或通道按一下連結，則頁面會在預設瀏覽器中呈現。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-115">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="8d4f5-116">如果從固定的索引標籤中按一下連結，該頁面會出現在該索引標籤中的小組 GUI 中，而且會停用在瀏覽器中開啟的選項，以進行安全性用途。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-116">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="8d4f5-117">將會封鎖此使用者以繼續前往 URL 的網站。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-117">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="8d4f5-118">如果傳送連結的使用者未受到 Office 365 ATP 的保護，他或她可以隨意按一下其機器上的 URL，並解決問題網站。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-118">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="8d4f5-119">這使得系統管理員知道誰是受保護的使用者，且應該是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-119">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![「小組的安全連結」頁面報告惡意連結，並封鎖頁面的傳輸。](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="8d4f5-121">按一下小組中此頁面上的 [*上一步*] 按鈕，即可將其關閉（或可能導致空白頁面使用者可以關閉）。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-121">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="8d4f5-122">不過，再次按一下連結會導致網站的信譽 reassessment，讓此頁面重新顯示。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-122">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
> <span data-ttu-id="8d4f5-123">有些 Microsoft 365 系統管理員會在封鎖頁面上啟用 [**繼續**進行] 訊息。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-123">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="8d4f5-124">不過，如果安全連結測量網站的信譽，但找不到，則不應再進行按一下。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-124">However, if Safe Links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="8d4f5-125">不建議使用者略過安全性度量。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-125">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="8d4f5-126">請先將此因素權衡為您的考慮，再啟用繼續。</span><span class="sxs-lookup"><span data-stu-id="8d4f5-126">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 
