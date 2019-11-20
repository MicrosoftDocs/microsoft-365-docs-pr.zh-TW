---
title: 適用於商務用 Skype Server 的 GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: 深入了解如何在內部部署商務用 Skype Server 和 Lync Server 中解決 GDPR 需求。
ms.openlocfilehash: fb3789a6835a367d415e5c32eeec043add150724
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "38749679"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a><span data-ttu-id="7dadc-103">適用於商務用 Skype Server 和 Lync Server 的 GDPR</span><span class="sxs-lookup"><span data-stu-id="7dadc-103">GDPR for Skype for Business Server and Lync Server</span></span>

<span data-ttu-id="7dadc-p101">商務用 Skype Server 和 Lync Server 的大部分資料會儲存在 Exchange Server 中，包括：</span><span class="sxs-lookup"><span data-stu-id="7dadc-p101">Most Skype for Business Server and Lync Server data is stored in Exchange Server. This includes:</span></span>

-   <span data-ttu-id="7dadc-106">交談歷程記錄</span><span class="sxs-lookup"><span data-stu-id="7dadc-106">Conversation history</span></span>

-   <span data-ttu-id="7dadc-107">語音信箱通知和抄錄</span><span class="sxs-lookup"><span data-stu-id="7dadc-107">Voicemail notifications and transcriptions</span></span>

-   <span data-ttu-id="7dadc-108">會議邀請</span><span class="sxs-lookup"><span data-stu-id="7dadc-108">Meeting invites</span></span>

<span data-ttu-id="7dadc-109">使用[適用於 Exchange Server 的 GDPR](gdpr-for-exchange-server.md) 中概述的程序，以針對 GDPR 要求尋找、匯出或刪除這些類型的資料。</span><span class="sxs-lookup"><span data-stu-id="7dadc-109">Use the procedures outlined for [GDPR for Exchange Server](gdpr-for-exchange-server.md) to find, export, or delete these types of data for GDPR requests.</span></span>

<span data-ttu-id="7dadc-p102">連絡人清單會儲存在 SQL Server 資料庫中。他們可以透過下列方式匯出：</span><span class="sxs-lookup"><span data-stu-id="7dadc-p102">Contact lists are stored in the SQL Server database. They can be exported in the following ways:</span></span>

-   <span data-ttu-id="7dadc-p103">使用者可以自行匯出連絡人，方法是以滑鼠右鍵按一下群組標頭，然後選取 [複製]。這樣會將該群組中的所有連絡人複製到剪貼簿，然後貼入任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="7dadc-p103">End users themselves can export the contacts by right clicking the group header and selecting Copy. This will copy all the contacts in that group into the clipboard, which can then be pasted into any app.</span></span>

-   <span data-ttu-id="7dadc-114">您可以使用 [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) Cmdlet 來匯出此資料。</span><span class="sxs-lookup"><span data-stu-id="7dadc-114">You can use the [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>

<span data-ttu-id="7dadc-p104">上傳至會議的內容 (例如 PowerPoint 檔案或講義) 或會議中產生的內容 (例如白板、投票或 Q/A) 會儲存在檔案管理工具中。如果使用者重新登入未過期的任何會議並且下載任何已上傳內容，或者擷取已產生內容的螢幕擷取畫面，那麼這個項目也可以匯出。</span><span class="sxs-lookup"><span data-stu-id="7dadc-p104">Content uploaded into meetings (such as PowerPoint files or handouts) or content generated in a meeting (such as whiteboard, polls, or Q/A) is stored in the filer. This can also be exported if end users log back into any meeting that has not expired and download any uploaded content or take screenshots in the case of generated content.</span></span>

<span data-ttu-id="7dadc-p105">不在 Exchange 行事曆和連絡人清單和連絡人權限 (家人、同事等等) 的 MeetNow 會議是在使用者資料庫中。在 Lync Server 2013 及更新版本中，您可以使用 [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) Cmdlet 來匯出此資料。</span><span class="sxs-lookup"><span data-stu-id="7dadc-p105">MeetNow meetings that are not in the Exchange Calendar and Contact List and contact rights (family, co-worker, etc.) are in the User Database. In Lync Server 2013 and later, you can use the [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>
