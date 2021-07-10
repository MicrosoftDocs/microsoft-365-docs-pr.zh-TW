---
title: Microsoft Teams 中的多地理位置功能
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: 深入瞭解 Teams 如何搭配 Microsoft 365 多地理位置運作。
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362643"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="e0544-103">Microsoft Teams 中的多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="e0544-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="e0544-104">Teams 中的多地理位置功能可讓 Teams 聊天資料儲存在靜止的指定地理位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="e0544-105">聊天室資料是由聊天訊息所組成，包括私人郵件、通道訊息和交談中使用的影像。</span><span class="sxs-lookup"><span data-stu-id="e0544-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="e0544-106">Teams 會使用慣用的資料位置 (PDL) 使用者和群組，以決定儲存資料的位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="e0544-107">如果 PDL 未設定或無效，則會將資料儲存在租使用者的中央位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="e0544-108">使用者聊天</span><span class="sxs-lookup"><span data-stu-id="e0544-108">User chat</span></span>

<span data-ttu-id="e0544-109">使用者聊天包括一對一、一對多及私人會議訊息。。</span><span class="sxs-lookup"><span data-stu-id="e0544-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="e0544-110">當建立新的使用者時，Teams 會讀取使用者的 PDL，並將其所有聊天資料儲存在該地理位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="e0544-111">針對現有使用者，如果系統管理員為使用者新增或修改 PDL，該使用者的聊天資料會新增至遷移佇列中，以移至指定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="e0544-112">「一對一」或「一對多」聊天的儲存位置是根據建立聊天的人員的 PDL。</span><span class="sxs-lookup"><span data-stu-id="e0544-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="e0544-113">如果使用者的 PDL 變更，聊天會遷移至新的地理位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="e0544-114">會議聊天的儲存位置是以會議召集人的 PDL 為基礎。</span><span class="sxs-lookup"><span data-stu-id="e0544-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="e0544-115">若要尋找使用者 Teams 資料的目前位置，請[連接至 Teams PowerShell](/powershell/module/teams/connect-microsoftteams)並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e0544-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="e0544-116">通道郵件</span><span class="sxs-lookup"><span data-stu-id="e0544-116">Channel messages</span></span>

<span data-ttu-id="e0544-117">每個 Microsoft 365 群組都有一個慣用資料位置 (PDL) ，表示要儲存相關資料的地理位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="e0544-118">Teams 會使用隨每個小組相關聯之群組的 PDL，來決定要為該小組儲存通道訊息資料的位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="e0544-119">這包括在管道會議中發生的聊天。</span><span class="sxs-lookup"><span data-stu-id="e0544-119">This includes chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="e0544-120">當使用者建立新的小組時，該使用者的 pdl 會決定指派給 Microsoft 365 群組的 pdl。</span><span class="sxs-lookup"><span data-stu-id="e0544-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="e0544-121">Group PDL 會決定團隊資料的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="e0544-122">如果該使用者的 PDL 稍後變更，則不會變更群組的 PDL。</span><span class="sxs-lookup"><span data-stu-id="e0544-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="e0544-123">針對現有的小組，如果系統管理員為支援小組的 Microsoft 365 群組新增或修改 PDL，該小組的通道郵件資料會新增到遷移佇列中，以移至指定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="e0544-124">變更 Microsoft 365 群組的 PDL 會將 Teams 資料排入佇列，以遷移至選取的位置。</span><span class="sxs-lookup"><span data-stu-id="e0544-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="e0544-125">不過，這不會自動遷移 SharePoint 的網站或與群組相關聯的檔案。</span><span class="sxs-lookup"><span data-stu-id="e0544-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="e0544-126">您必須在[將 SharePoint 網站移至不同的地理位置](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)時，依照下列程式，分別移動網站。</span><span class="sxs-lookup"><span data-stu-id="e0544-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="e0544-127">請務必執行這兩個步驟，以避免針對不同位置的一個群組 Teams 資料和 SharePoint 資料。</span><span class="sxs-lookup"><span data-stu-id="e0544-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="e0544-128">若要尋找小組資料的目前位置，請[連接至 Teams PowerShell](/powershell/module/teams/connect-microsoftteams) ，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e0544-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="e0544-129">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="e0544-129">User Experience</span></span>

<span data-ttu-id="e0544-130">Teams多地理位置對使用者而言是無縫的。</span><span class="sxs-lookup"><span data-stu-id="e0544-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="e0544-131">一旦您變更使用者或群組的 PDL，對應的資料就會排隊進行遷移，而且即使在進行遷移時，也會自動進行遷移，但不會影響使用者或其 Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="e0544-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0544-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e0544-132">See also</span></span>

[<span data-ttu-id="e0544-133">Microsoft 365 多地理位置租用戶組態</span><span class="sxs-lookup"><span data-stu-id="e0544-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="e0544-134">管理多地理位置環境</span><span class="sxs-lookup"><span data-stu-id="e0544-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="e0544-135">管理多地理位置環境中的 Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="e0544-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
