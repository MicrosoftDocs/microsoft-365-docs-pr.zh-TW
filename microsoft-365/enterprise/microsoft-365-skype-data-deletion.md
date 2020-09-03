---
title: Office 365 商務用 Skype 資料刪除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，您可以在商務用 Skype 中尋找資料刪除的說明，包含哪些類型的內容不會保留。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a47df4dd0dfdf5551668f8cafc9baa023bd6db1
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332709"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a><span data-ttu-id="e7158-103">Office 365 中的商務用 Skype 資料刪除</span><span class="sxs-lookup"><span data-stu-id="e7158-103">Skype for Business Data Deletion in Office 365</span></span>

<span data-ttu-id="e7158-104">商務用 Skype 可在會議中提供對等立即訊息、多方立即訊息和內容上傳活動的封存。</span><span class="sxs-lookup"><span data-stu-id="e7158-104">Skype for Business provides archiving of peer-to-peer instant messages, multiparty instant messages, and content upload activities in meetings.</span></span> <span data-ttu-id="e7158-105">封存功能需要 Exchange，且由使用者的 Exchange 信箱 In-Place Hold 屬性所控制，這會同時歸檔電子郵件和商務用 Skype 內容。</span><span class="sxs-lookup"><span data-stu-id="e7158-105">The archiving capability requires Exchange and is controlled by the user's Exchange mailbox In-Place Hold attribute, which archives both email and Skype for Business contents.</span></span>

<span data-ttu-id="e7158-106">商務用 Skype 中的所有封存都會視為「使用者層級封存」，因為您可以為一或多個特定使用者或使用者群組建立、設定及套用使用者層級的封存原則，以針對一或多個特定使用者或使用者群組來啟用或停用該使用者。</span><span class="sxs-lookup"><span data-stu-id="e7158-106">All archiving in Skype for Business is considered "user-level archiving" because you enable or disable it for one or more specific users or groups of users by creating, configuring, and applying a user-level archiving policy for those users.</span></span> <span data-ttu-id="e7158-107">在商務用 Skype 系統管理中心內，無法直接控制封存設定。</span><span class="sxs-lookup"><span data-stu-id="e7158-107">There is no direct control of archiving settings from within the Skype for Business admin center.</span></span>

<span data-ttu-id="e7158-108">在商務用 Skype 中未封存下列類型的內容：</span><span class="sxs-lookup"><span data-stu-id="e7158-108">The following types of content are not archived in Skype for Business:</span></span>

- <span data-ttu-id="e7158-109">對等檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="e7158-109">Peer-to-peer file transfers</span></span>
- <span data-ttu-id="e7158-110">對等立即訊息和會議的音訊/視訊</span><span class="sxs-lookup"><span data-stu-id="e7158-110">Audio/video for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="e7158-111">對等立即訊息與會議的應用程式共用</span><span class="sxs-lookup"><span data-stu-id="e7158-111">Application sharing for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="e7158-112">會議標注</span><span class="sxs-lookup"><span data-stu-id="e7158-112">Conferencing annotations</span></span> 

## <a name="meeting-content-retention"></a><span data-ttu-id="e7158-113">會議內容保留</span><span class="sxs-lookup"><span data-stu-id="e7158-113">Meeting Content Retention</span></span>

<span data-ttu-id="e7158-114">使用商務用 Skype 的客戶可以將內容上傳至商務用 skype 會議，例如 PowerPoint 簡報、OneNote 檔案及其他檔案。</span><span class="sxs-lookup"><span data-stu-id="e7158-114">Customers using Skype for Business can upload content to a Skype for Business meeting as attachments, such as PowerPoint presentations, OneNote files, and other files.</span></span> <span data-ttu-id="e7158-115">上傳至會議的內容有如下的保留期：</span><span class="sxs-lookup"><span data-stu-id="e7158-115">The retention period for content that has been uploaded to a meeting is as follows:</span></span>

- <span data-ttu-id="e7158-116">**一次性會議** 內容會保留15天，從最後一個人離開會議的時間開始。</span><span class="sxs-lookup"><span data-stu-id="e7158-116">**One-time meeting** - Content is retained for 15 days starting from when the last person leaves the meeting.</span></span>
- <span data-ttu-id="e7158-117">**週期性會議** 內容會在最後一個人離開會議的最後一個會議之後保留15天。</span><span class="sxs-lookup"><span data-stu-id="e7158-117">**Recurring meeting** - Content is retained for 15 days after the last person leaves the last session of the meeting.</span></span> <span data-ttu-id="e7158-118">如果有人在15天內加入相同會議會話，保留計時器便會重設。</span><span class="sxs-lookup"><span data-stu-id="e7158-118">The retention timer resets if someone joins the same meeting session within 15 days.</span></span> <span data-ttu-id="e7158-119">例如，假設商務用 Skype 會議排定一年每週進行一次，並在第一個實例中將檔案上傳至會議。</span><span class="sxs-lookup"><span data-stu-id="e7158-119">For example, assume a Skype for Business meeting is scheduled to occur on a weekly basis for one year, and a file is uploaded to the meeting during the first instance.</span></span> <span data-ttu-id="e7158-120">如果每週至少有一個人員加入會議會話，該檔案會保留在全年的商務用 Skype Online 伺服器中，在最後一個人離開最後一筆會議之後15天加上15天。</span><span class="sxs-lookup"><span data-stu-id="e7158-120">If at least one person joins the meeting session every week, the file is retained in Skype for Business Online servers for the entire year plus 15 days after the last person leaves the last meeting of the series.</span></span>
- <span data-ttu-id="e7158-121">**立即開會會議** 內容會在會議結束時間後的8小時內保留。</span><span class="sxs-lookup"><span data-stu-id="e7158-121">**Meet Now meeting** - Content is retained for 8 hours after the meeting end time.</span></span>

> [!NOTE]
> <span data-ttu-id="e7158-122">如果使用者未獲授權或已停用 (例如，如果 **msRTCSIP msrtcsip-userenabled** 設定為 *False*) ，然後重新獲得授權或重新啟用，則不會保留會議內容。</span><span class="sxs-lookup"><span data-stu-id="e7158-122">If a user is unlicensed or disabled (e.g., if **msRTCSIP-userenabled** is set to *False*), and is then re-licensed or reenabled, meeting content is not retained.</span></span>

## <a name="meeting-expiration"></a><span data-ttu-id="e7158-123">會議到期</span><span class="sxs-lookup"><span data-stu-id="e7158-123">Meeting Expiration</span></span>

<span data-ttu-id="e7158-124">使用者可以在特定會議結束之後存取該會議，但需注意下列到期時段：</span><span class="sxs-lookup"><span data-stu-id="e7158-124">Users can access a specific meeting after the meeting has ended, subject to the following expiration time periods:</span></span>

- <span data-ttu-id="e7158-125">**單一會議** 會議會在排程的會議結束時間後的14天到期。</span><span class="sxs-lookup"><span data-stu-id="e7158-125">**One-time meeting** - Meeting expires 14 days after the scheduled meeting end time.</span></span>
- <span data-ttu-id="e7158-126">**具有結束日期的週期性會議** -會議會在上次會議約會的排程結束時間之後的14天到期。</span><span class="sxs-lookup"><span data-stu-id="e7158-126">**Recurring meeting with end date** - Meeting expires 14 days after the scheduled end time of the last meeting occurrence.</span></span>
- <span data-ttu-id="e7158-127">[**立即開會會議**] 會議會在8小時後到期。</span><span class="sxs-lookup"><span data-stu-id="e7158-127">**Meet Now meeting** - Meeting expires after 8 hours.</span></span>

## <a name="whiteboard-collaboration"></a><span data-ttu-id="e7158-128">白板協同共同作業</span><span class="sxs-lookup"><span data-stu-id="e7158-128">Whiteboard Collaboration</span></span>

<span data-ttu-id="e7158-129">在白板上所做的註釋，所有參與者都看得到。</span><span class="sxs-lookup"><span data-stu-id="e7158-129">Annotations made on whiteboards will be seen by all participants.</span></span> <span data-ttu-id="e7158-130">儲存白板時，白板和所有批註將會儲存在商務用 Skype 伺服器上，而且會根據系統管理員設定的會議內容到期原則，保留在伺服器上。</span><span class="sxs-lookup"><span data-stu-id="e7158-130">When saving a whiteboard, the whiteboard and all annotations will be stored on a Skype for Business server, and it will be retained on the server according to meeting content expiration policies set by the administrator.</span></span>

## <a name="audio-test-service"></a><span data-ttu-id="e7158-131">音訊測試服務</span><span class="sxs-lookup"><span data-stu-id="e7158-131">Audio Test Service</span></span>

<span data-ttu-id="e7158-132">在音訊測試服務通話期間，大約有5秒的時間會記錄) 的語音樣本 (。</span><span class="sxs-lookup"><span data-stu-id="e7158-132">A short (approximately 5 seconds) sample of your voice is recorded during the Audio Test Service call.</span></span> <span data-ttu-id="e7158-133">語音範例是用來檢查及/或驗證商務用 Skype 通話的音質，取決於錄製品質。</span><span class="sxs-lookup"><span data-stu-id="e7158-133">The voice sample is used by you to check and/or verify the sound quality of your Skype for Business call based on the quality of the recording.</span></span> <span data-ttu-id="e7158-134">當音訊測試服務通話結束時，語音範例就會被刪除。</span><span class="sxs-lookup"><span data-stu-id="e7158-134">When the Audio Test Service call ends, the voice sample is deleted.</span></span>

## <a name="persistent-group-chat"></a><span data-ttu-id="e7158-135">持續群組聊天</span><span class="sxs-lookup"><span data-stu-id="e7158-135">Persistent Group Chat</span></span>

<span data-ttu-id="e7158-136">持續群組聊天會儲存群組聊天交談的內容。</span><span class="sxs-lookup"><span data-stu-id="e7158-136">Persistent Group Chat stores the content of group chat conversations.</span></span> <span data-ttu-id="e7158-137">若啟用，系統管理員可以控制保留期間、儲存此資訊的伺服器、如果群組聊天記錄已封存以符合合規性或其他目的，以及管理/修改聊天室上的任何屬性。</span><span class="sxs-lookup"><span data-stu-id="e7158-137">If enabled, the administrator can control the retention period, the server on which this information is stored, if Group Chat history is archived for compliance or other purposes, and manage/modify any properties on a room.</span></span> <span data-ttu-id="e7158-138">具有不同角色的使用者具有不同的保存資料存取權，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7158-138">Users with different roles have different access to the persisted data, as follows:</span></span>

- <span data-ttu-id="e7158-139">管理員可以刪除舊的內容 (例如，在特定日期之前發佈的內容) 從任何聊天室，以避免資料庫的大小大幅增加。</span><span class="sxs-lookup"><span data-stu-id="e7158-139">Administrators can delete older content (for example, content posted before a certain date) from any chat room to keep the size of the database from growing greatly.</span></span> <span data-ttu-id="e7158-140">或者，他們可以移除或取代視為對特定聊天室不適當的郵件 (或視為不適當的) 。</span><span class="sxs-lookup"><span data-stu-id="e7158-140">Or, they can remove or replace messages considered inappropriate for a given chat room (or considered unsuitable).</span></span>
- <span data-ttu-id="e7158-141">使用者（包括郵件作者）無法刪除任何聊天室中的內容。</span><span class="sxs-lookup"><span data-stu-id="e7158-141">End-users, including message authors, cannot delete content from any chat room.</span></span>
- <span data-ttu-id="e7158-142">聊天室管理員可以停用會議室，但無法刪除會議室。</span><span class="sxs-lookup"><span data-stu-id="e7158-142">Chat room managers can disable rooms but cannot delete rooms.</span></span> <span data-ttu-id="e7158-143">只有管理員可以在建立聊天室之後刪除聊天室。</span><span class="sxs-lookup"><span data-stu-id="e7158-143">Only administrators can delete a chat room after it is created.</span></span>