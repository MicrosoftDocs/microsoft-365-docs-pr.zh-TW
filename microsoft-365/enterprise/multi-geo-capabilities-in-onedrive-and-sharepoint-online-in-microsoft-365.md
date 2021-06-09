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
ms.openlocfilehash: 8f42b071abef0602304f1a468190c33700fe3e82
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995906"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="b7be2-103">OneDrive 和 SharePoint Online 中的多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="b7be2-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="b7be2-104">OneDrive 和 SharePoint Online 中的多地理位置功能可讓您控制共用資源，例如 SharePoint 小組網站，以及儲存在全國或地區中的 Microsoft 365 群組信箱。</span><span class="sxs-lookup"><span data-stu-id="b7be2-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a country or region.</span></span>

<span data-ttu-id="b7be2-105">每個使用者、群組信箱和 SharePoint 網站會有慣用的資料位置 (PDL)，這表示儲存相關資料所在的地理位置。</span><span class="sxs-lookup"><span data-stu-id="b7be2-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="b7be2-106">使用者的個人資料 (Exchange 信箱和 OneDrive) 以及他們所建立的任何 Microsoft 365 群組或 SharePoint 網站，可以儲存在指定的地理位置，以滿足資料落地需求。</span><span class="sxs-lookup"><span data-stu-id="b7be2-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="b7be2-107">您可以[為每個地理位置指定不同的系統管理員](add-a-sharepoint-geo-admin.md)。</span><span class="sxs-lookup"><span data-stu-id="b7be2-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="b7be2-108">使用者使用 Microsoft 365 服務，包括 Office 應用程式、OneDrive 及搜尋時，可獲得順暢的體驗。</span><span class="sxs-lookup"><span data-stu-id="b7be2-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="b7be2-109">如需詳細資料，請參閱[多地理位置環境中的使用者體驗](multi-geo-user-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="b7be2-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="b7be2-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="b7be2-110">OneDrive</span></span>

<span data-ttu-id="b7be2-111">每位使用者的 OneDrive 可以佈建在其中或根據使用者的 PDL [由系統管理員移動](move-onedrive-between-geo-locations.md)到衛星位置。</span><span class="sxs-lookup"><span data-stu-id="b7be2-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="b7be2-112">然後個人檔案會保存在該地理位置，不過可以與其他地理位置中的使用者共用這些檔案。</span><span class="sxs-lookup"><span data-stu-id="b7be2-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="b7be2-113">SharePoint 網站與群組</span><span class="sxs-lookup"><span data-stu-id="b7be2-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="b7be2-114">多地理位置功能的管理可透過 SharePoint 管理中心取得。</span><span class="sxs-lookup"><span data-stu-id="b7be2-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="b7be2-115">您可以在[對應的部落格文章](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)中找到詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="b7be2-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="b7be2-116">當使用者建立多重地理環境中 SharePoint 群組連接的網站時，其 PDL 可用來判斷建立網站和其相關聯群組信箱所在的地理位置。</span><span class="sxs-lookup"><span data-stu-id="b7be2-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="b7be2-117">(如果使用者的 PDL 值尚未設定，或是設為尚未設定為衛星位置的地理位置，則會在中央位置建立網站和信箱。)</span><span class="sxs-lookup"><span data-stu-id="b7be2-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="b7be2-118">Exchange、OneDrive 及 SharePoint 以外的 Microsoft 365 服務並非多地理位置。</span><span class="sxs-lookup"><span data-stu-id="b7be2-118">Microsoft 365 services other than Exchange, OneDrive, and SharePoint are not Multi-Geo.</span></span> <span data-ttu-id="b7be2-119">不過，這些服務所建立的 Microsoft 365 群組會加上建立者的 PDL 戳記，並且會在對應的地理位置佈建其 Exchange 群組信箱和 SharePoint O365 群組網站。</span><span class="sxs-lookup"><span data-stu-id="b7be2-119">However, Microsoft 365 Groups that are created by these services will be stamped with the PDL of the creator and their Exchange Group mailbox and SharePoint O365 Group Site provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="b7be2-120">管理多地理環境</span><span class="sxs-lookup"><span data-stu-id="b7be2-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="b7be2-121">您會透過 SharePoint 系統管理中心來設定和管理您的多地理環境。</span><span class="sxs-lookup"><span data-stu-id="b7be2-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![SharePoint 系統管理中心中地理位置頁面的螢幕擷取畫面](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="b7be2-123">(部分動作，例如移動 SharePoint 網站或 OneDrive 網站，需要使用 Microsoft PowerShell。)</span><span class="sxs-lookup"><span data-stu-id="b7be2-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="b7be2-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b7be2-124">See also</span></span>

[<span data-ttu-id="b7be2-125">SharePoint 和 Microsoft 365 群組中的多地理位置</span><span class="sxs-lookup"><span data-stu-id="b7be2-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="b7be2-126">管理多地理位置環境</span><span class="sxs-lookup"><span data-stu-id="b7be2-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="b7be2-127">多地理位置環境中的 SharePoint 儲存空間配額</span><span class="sxs-lookup"><span data-stu-id="b7be2-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="b7be2-128">管理多地理位置環境中的 Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="b7be2-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
