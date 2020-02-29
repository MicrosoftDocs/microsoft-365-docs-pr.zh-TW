---
title: Office 365 的 ATP 安全連結的 Teams，safelinks、 安全連結，封鎖惡意連結，office 365 atp，Teams 安全連結，阻止使用者按下不正確的連結，惡意連結
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: Teams 現在會在您按一下 [時間可以存取安全連結。 您是否正在使用聊天 1 對 1 聊天室、 群組、 之間或通道和索引標籤，如果您有 Office 365 ATP 的訂閱，您必須啟用並使用此安全性功能的能力。
ms.openlocfilehash: ba7ef2ae63b788ec94fbbb15c3c00312177a59d5
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341584"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a><span data-ttu-id="b362b-104">Office 365 小組中的安全連結</span><span class="sxs-lookup"><span data-stu-id="b362b-104">Office 365 Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b362b-105">這項功能是在**公開預覽**中的客戶在 Microsoft Teams 技術採用程式 （點選） 起 2020 年 2 月 28。</span><span class="sxs-lookup"><span data-stu-id="b362b-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="b362b-106">此附註會更廣泛地使用 teams 的安全連結時移除 > 一文。</span><span class="sxs-lookup"><span data-stu-id="b362b-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="b362b-107">Microsoft Teams，Office 365 雲端式應用程式的管理工作，已使用安全附件 （適用於 Office 365)，但它現在能夠存取安全連結在您按一下 [時間。</span><span class="sxs-lookup"><span data-stu-id="b362b-107">Microsoft Teams, an Office 365 Cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="b362b-108">您是否正在使用聊天 1 對 1 聊天室、 群組、 之間或通道和索引標籤，如果您有 Office 365 ATP 的訂閱，您必須啟用並使用此安全措施的能力。</span><span class="sxs-lookup"><span data-stu-id="b362b-108">Whether you’re using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="b362b-109">以下是其運作方式：</span><span class="sxs-lookup"><span data-stu-id="b362b-109">Here’s how it works:</span></span> 

1. <span data-ttu-id="b362b-110">當您啟動 Teams 應用程式時，Office 365 會檢查以確保使用者所屬的組織具有 Office 365 ATP，且使用者是作用中的安全連結原則以啟用 Microsoft teams 其保護的一部分。</span><span class="sxs-lookup"><span data-stu-id="b362b-110">When you start the Teams application, Office 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="b362b-111">如果上述條件為真，然後 Url 將會驗證的同時按一下 [聊天、 群組聊天、 通道，並在索引標籤中，該使用者的。</span><span class="sxs-lookup"><span data-stu-id="b362b-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="b362b-112">項目將使用者體驗？</span><span class="sxs-lookup"><span data-stu-id="b362b-112">What will users experience?</span></span> 

<span data-ttu-id="b362b-113">受保護的所有使用者都必須具有危險物質暴露 Url 此經驗：</span><span class="sxs-lookup"><span data-stu-id="b362b-113">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="b362b-114">如果已從 microsoft Teams 交談，group chat]，按一下連結或通道，從] 頁面上將預設瀏覽器中呈現。</span><span class="sxs-lookup"><span data-stu-id="b362b-114">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="b362b-115">如果按下連結已釘選] 索引標籤中，從 [] 頁面上會出現在小組 GUI 內該索引標籤，並將會停用瀏覽器中開啟的選項，基於安全性考量。</span><span class="sxs-lookup"><span data-stu-id="b362b-115">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="b362b-116">此使用者粗俗繼續進行至 URL 的網站。</span><span class="sxs-lookup"><span data-stu-id="b362b-116">This user will be blocked from proceeding to the URL’s site.</span></span>

<span data-ttu-id="b362b-117">如果傳送連結的使用者不由 Office 365 ATP 受到保護，他或她可以自由地按一下他/她的機器上的 URL，並解決問題的網站。</span><span class="sxs-lookup"><span data-stu-id="b362b-117">If the user who sent the link isn’t protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="b362b-118">這可讓串列重要要注意的 Office 365 系統管理員的人員其受保護的使用者都應該與。</span><span class="sxs-lookup"><span data-stu-id="b362b-118">This makes it doubly important for Office 365 Administrators to be aware of who their protected users are and should be.</span></span>

![報告惡意連結和封鎖] 頁面上的傳輸的小組] 頁面上的安全連結。](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="b362b-120">按一下 [teams 此頁面上的 [*返回*] 按鈕將其關閉 （或可能會導致空白頁面使用者可以關閉）。</span><span class="sxs-lookup"><span data-stu-id="b362b-120">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="b362b-121">不過，再按一下連結會導致上場的站台的信譽，讓此頁面會重新出現。</span><span class="sxs-lookup"><span data-stu-id="b362b-121">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="b362b-122">某些 Office 365 系統管理員將會啟用 [封鎖] 頁面上的，**還是繼續**訊息。</span><span class="sxs-lookup"><span data-stu-id="b362b-122">Some Office 365 Admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="b362b-123">不過，如果安全連結會測量站台的信譽，並更快找到它缺少，沒有進一步點選應該進行。</span><span class="sxs-lookup"><span data-stu-id="b362b-123">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="b362b-124">不建議使用者略過安全措施。</span><span class="sxs-lookup"><span data-stu-id="b362b-124">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="b362b-125">請權衡這您考量啟用仍繼續之前。</span><span class="sxs-lookup"><span data-stu-id="b362b-125">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

