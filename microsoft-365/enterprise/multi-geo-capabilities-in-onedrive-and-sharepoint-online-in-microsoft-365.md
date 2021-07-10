---
title: OneDrive 和 SharePoint Online 中的多地理位置功能
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: 使用 OneDrive Online 的多地理位置功能，將 Microsoft 365 的目前狀態拓展至多個地理區域。
ms.openlocfilehash: 405f876317a6cec6defdf3f1a49b0dc32ac0add2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362279"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="d1a2f-103">OneDrive 和 SharePoint Online 中的多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="d1a2f-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="d1a2f-104">OneDrive 和 SharePoint Online 中的多地理位置功能可讓您控制共用資源，例如 SharePoint 小組網站，以及儲存在指定地理位置的 Microsoft 365 群組信箱。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a specified geo location.</span></span>

<span data-ttu-id="d1a2f-105">每個使用者、群組信箱和 SharePoint 網站會有慣用的資料位置 (PDL)，這表示儲存相關資料所在的地理位置。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="d1a2f-106">使用者的個人資料 (Exchange 信箱和 OneDrive) 以及他們所建立的任何 Microsoft 365 群組或 SharePoint 網站，可以儲存在指定的地理位置，以滿足資料落地需求。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="d1a2f-107">您可以[為每個地理位置指定不同的系統管理員](add-a-sharepoint-geo-admin.md)。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="d1a2f-108">使用者使用 Microsoft 365 服務，包括 Office 應用程式、OneDrive 及搜尋時，可獲得順暢的體驗。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="d1a2f-109">如需詳細資料，請參閱[多地理位置環境中的使用者體驗](multi-geo-user-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="d1a2f-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d1a2f-110">OneDrive</span></span>

<span data-ttu-id="d1a2f-111">每位使用者的 OneDrive 可以佈建在其中或根據使用者的 PDL [由系統管理員移動](move-onedrive-between-geo-locations.md)到衛星位置。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="d1a2f-112">然後個人檔案會保存在該地理位置，不過可以與其他地理位置中的使用者共用這些檔案。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="d1a2f-113">SharePoint 網站與群組</span><span class="sxs-lookup"><span data-stu-id="d1a2f-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="d1a2f-114">多地理位置功能的管理可透過 SharePoint 管理中心取得。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="d1a2f-115">您可以在[對應的部落格文章](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)中找到詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="d1a2f-116">當使用者建立多重地理環境中 SharePoint 群組連接的網站時，其 PDL 可用來判斷建立網站和其相關聯群組信箱所在的地理位置。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="d1a2f-117">(如果使用者的 PDL 值尚未設定，或是設為尚未設定為衛星位置的地理位置，則會在中央位置建立網站和信箱。)</span><span class="sxs-lookup"><span data-stu-id="d1a2f-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="d1a2f-118">Exchange、OneDrive、SharePoint 及 Teams 以外的 Microsoft 365 服務不是多地理位置。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-118">Microsoft 365 services other than Exchange, OneDrive, SharePoint, and Teams are not Multi-Geo.</span></span> <span data-ttu-id="d1a2f-119">不過，這些服務建立的 Microsoft 365 群組將會以建立者和其 Exchange 群組信箱的 PDL 進行設定，SharePoint 網站會在對應的 geo 中布建。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-119">However, Microsoft 365 Groups that are created by these services will be configured with the PDL of the creator and their Exchange Group mailbox, SharePoint site are provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="d1a2f-120">管理多地理環境</span><span class="sxs-lookup"><span data-stu-id="d1a2f-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="d1a2f-121">您會透過 SharePoint 系統管理中心來設定和管理您的多地理環境。</span><span class="sxs-lookup"><span data-stu-id="d1a2f-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![SharePoint 系統管理中心中地理位置頁面的螢幕擷取畫面](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="d1a2f-123">(部分動作，例如移動 SharePoint 網站或 OneDrive 網站，需要使用 Microsoft PowerShell。)</span><span class="sxs-lookup"><span data-stu-id="d1a2f-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="d1a2f-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d1a2f-124">See also</span></span>

[<span data-ttu-id="d1a2f-125">SharePoint 和 Microsoft 365 群組中的多地理位置</span><span class="sxs-lookup"><span data-stu-id="d1a2f-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="d1a2f-126">管理多地理位置環境</span><span class="sxs-lookup"><span data-stu-id="d1a2f-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="d1a2f-127">多地理位置環境中的 SharePoint 儲存空間配額</span><span class="sxs-lookup"><span data-stu-id="d1a2f-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="d1a2f-128">管理多地理位置環境中的 Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="d1a2f-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
