---
title: 在多地理位置環境中的使用者體驗
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: 了解 Microsoft 365 多地理位置環境中的 SharePoint、OneDrive 和 Exchange 使用者體驗。
ms.openlocfilehash: c94fc5569a5444ca6361712f57460cf0c977b18e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688415"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="c8a18-103">在多地理位置環境中的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="c8a18-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="c8a18-104">以下是您的使用者在 OneDrive 多地理位置組態中會看到的內容：</span><span class="sxs-lookup"><span data-stu-id="c8a18-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="c8a18-105">Exchange 信箱</span><span class="sxs-lookup"><span data-stu-id="c8a18-105">Exchange mailbox</span></span>

<span data-ttu-id="c8a18-106">使用者的 Exchange 信箱已佈建到慣用的資料位置，當 PDL 變更時將自動重新配置。</span><span class="sxs-lookup"><span data-stu-id="c8a18-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="c8a18-107">使用者可以正常使用 Outlook 與 Outlook 網頁版，在多地理環境中的使用者體驗沒有任何改變。</span><span class="sxs-lookup"><span data-stu-id="c8a18-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="c8a18-108">中樞網站</span><span class="sxs-lookup"><span data-stu-id="c8a18-108">Hub sites</span></span>

<span data-ttu-id="c8a18-109">SharePoint 中樞網站改善了員工對內容的探索和參與，同時建立了完整且一致的專案、部門或區域的表示方式。</span><span class="sxs-lookup"><span data-stu-id="c8a18-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="c8a18-110">在多地理環境中，無論中樞網站的地理位置在哪裡，衛星位置中的網站都能輕鬆與中樞網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="c8a18-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="c8a18-111">無論網站的地理位置在哪裡，使用者都可以透過單一搜尋，在中樞搜尋並獲得結果。</span><span class="sxs-lookup"><span data-stu-id="c8a18-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="c8a18-112">Microsoft 365 應用程式啟動器</span><span class="sxs-lookup"><span data-stu-id="c8a18-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="c8a18-113">應用程式啟動器具有多地理位置感知功能，可將每個磚定導向工作負載的相應地理位置。</span><span class="sxs-lookup"><span data-stu-id="c8a18-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="c8a18-114">SharePoint 和 OneDrive 磚會將使用者指向對應到使用者佈建之地理位置的位置。</span><span class="sxs-lookup"><span data-stu-id="c8a18-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="c8a18-115">這表示使用者在中央位置有OneDrive，他們的 SharePoint 磚會將他們導向中央位置的 SP 首頁，但他們的群組網站將會佈建到對應其 PDL 的位置。</span><span class="sxs-lookup"><span data-stu-id="c8a18-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="c8a18-116">Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="c8a18-116">Office applications</span></span>

<span data-ttu-id="c8a18-117">Office 應用程式 (例如 Word、Excel 及 PowerPoint) 會在每個使用者登入時，自動為他們偵測正確的商務用 OneDrive 地理位置。</span><span class="sxs-lookup"><span data-stu-id="c8a18-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive for Business geo-location for each user when they log in.</span></span> <span data-ttu-id="c8a18-118">使用者不需要輸入他們的 OneDrive 或 SharePoint 網站特定地理位置 URL。</span><span class="sxs-lookup"><span data-stu-id="c8a18-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-for-business-sync-client"></a><span data-ttu-id="c8a18-119">商務用 OneDrive 同步處理用戶端</span><span class="sxs-lookup"><span data-stu-id="c8a18-119">OneDrive for Business Sync Client</span></span>

<span data-ttu-id="c8a18-120">商務用 OneDrive 同步處理用戶端 (版本 17.3.6943.0625 和更新版本) 將會自動偵測該使用者的正確商務用 OneDrive 地理位置。</span><span class="sxs-lookup"><span data-stu-id="c8a18-120">The OneDrive for Business Sync Client (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive for Business geo location for the user.</span></span> <span data-ttu-id="c8a18-121">同步處理用戶端支援包含同步處理群組型網站的功能，無論其地理位置如何。</span><span class="sxs-lookup"><span data-stu-id="c8a18-121">Synch client support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="c8a18-122">請注意，多地理位置不支援 Groove 同步處理用戶端。</span><span class="sxs-lookup"><span data-stu-id="c8a18-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-for-business-location"></a><span data-ttu-id="c8a18-123">商務用 OneDrive 的位置</span><span class="sxs-lookup"><span data-stu-id="c8a18-123">OneDrive for Business location</span></span>

<span data-ttu-id="c8a18-p106">使用者會將其商務用 OneDrive 佈建在其慣用的資料位置。如果使用者瀏覽至包含不正確地理位置的 OneDrive URL (例如從先前地理位置的書籤)，系統就會將他們自動重新導向至適當地理位置中的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="c8a18-p106">Users will have their OneDrive for Business provisioned in their preferred data location. If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="c8a18-126">OneDrive iOS 和 Android</span><span class="sxs-lookup"><span data-stu-id="c8a18-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="c8a18-p107">OneDrive iOS 和 Android 的行動裝置應用程式會顯示您的 OneDrive 檔案及與您共用的檔案 (無論其地理位置為何)。透過 OneDrive 行動裝置應用程式的搜尋會顯示來自所有地理位置的相關結果。請下載這些應用程式的最新版本。</span><span class="sxs-lookup"><span data-stu-id="c8a18-p107">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location. Search from the OneDrive mobile apps will show relevant results from all geo locations. Please download the latest version of these apps.</span></span>

<span data-ttu-id="c8a18-130">請參閱使用「[在 iOS 上的 OneDrive](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247)」和「[使用適用於 Android 的 OneDrive](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36)」以了解詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c8a18-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="c8a18-131">OneDrive 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="c8a18-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="c8a18-132">OneDrive 行動用戶端具有多地理位置感知功能，可顯示所有地理位置的相關內容和結果。</span><span class="sxs-lookup"><span data-stu-id="c8a18-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="c8a18-133">Search</span><span class="sxs-lookup"><span data-stu-id="c8a18-133">Search</span></span>

<span data-ttu-id="c8a18-p108">每個地理位置有其專屬的搜尋索引和搜尋中心。當使用者搜尋時，系統會將查詢傳送給所有的地理位置，且傳回的結果會經過合併並加以排名，讓使用者獲得一致的結果。使用者會取得來自所有地理位置的結果 (無論他們自身的地理位置為何)。請參閱[設定適用於商務用 OneDrive 多地理位置的搜尋](configure-search-for-multi-geo.md)以了解詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c8a18-p108">Each geo location has its own search index and Search Center. When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results. Users get results from all geo locations regardless of their own geo location. See [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="c8a18-138">支援以下搜尋用戶端：</span><span class="sxs-lookup"><span data-stu-id="c8a18-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="c8a18-139">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="c8a18-139">OneDrive for Business</span></span>

-   <span data-ttu-id="c8a18-140">Delve</span><span class="sxs-lookup"><span data-stu-id="c8a18-140">Delve</span></span>

-   <span data-ttu-id="c8a18-141">SharePoint 首頁</span><span class="sxs-lookup"><span data-stu-id="c8a18-141">SharePoint Home</span></span>

-   <span data-ttu-id="c8a18-142">搜尋中心</span><span class="sxs-lookup"><span data-stu-id="c8a18-142">The Search Center</span></span>

-   <span data-ttu-id="c8a18-143">使用 SharePoint 搜尋 API 的自訂搜尋應用程式</span><span class="sxs-lookup"><span data-stu-id="c8a18-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="c8a18-144">SharePoint 首頁</span><span class="sxs-lookup"><span data-stu-id="c8a18-144">SharePoint Home</span></span> 

<span data-ttu-id="c8a18-145">在 SharePoint 多地理位置中，您的 SharePoint 首頁裝載於使用者所在的位置，該位置由使用者的商務用 OneDrive 的位置來決定。</span><span class="sxs-lookup"><span data-stu-id="c8a18-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive for business location.</span></span> <span data-ttu-id="c8a18-146">例如，若使用者將 OneDrive 裝載在歐洲衛星位置，則他們的 SharePoint 首頁將從歐洲顯示。</span><span class="sxs-lookup"><span data-stu-id="c8a18-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="c8a18-147">SharePoint 首頁包含使用者的所有相關內容，無論內容的地理位置為何。</span><span class="sxs-lookup"><span data-stu-id="c8a18-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="c8a18-148">**已追蹤網站、來自網站的新聞、最近使用的網站、最常瀏覽的網站，以及建議的網站**</span><span class="sxs-lookup"><span data-stu-id="c8a18-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="c8a18-149">只要使用者擁有這些元件的權限，都能看到這些內容，不管內容裝載的地理位置為何。</span><span class="sxs-lookup"><span data-stu-id="c8a18-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="c8a18-150">**精選連結**</span><span class="sxs-lookup"><span data-stu-id="c8a18-150">**Features Links**</span></span>

<span data-ttu-id="c8a18-151">系統管理員可以根據每個地理位置，在 SharePoint 首頁中設定 [精選連結]。</span><span class="sxs-lookup"><span data-stu-id="c8a18-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="c8a18-152">這可讓系統管理員在每個區域的 SP 首頁中，提供適合該區域使用者的連結。</span><span class="sxs-lookup"><span data-stu-id="c8a18-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="c8a18-153">SharePoint 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="c8a18-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="c8a18-154">SharePoint 行動用戶端具有多地理位置感知功能，可顯示所有地理位置的相關內容和結果。</span><span class="sxs-lookup"><span data-stu-id="c8a18-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="c8a18-155">共用</span><span class="sxs-lookup"><span data-stu-id="c8a18-155">Sharing</span></span>

<span data-ttu-id="c8a18-156">[人員選擇器] 可顯示所有地理位置的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="c8a18-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="c8a18-157">這可讓使用者與相同地理位置的其他使用者共用，或與任何其他租用戶地理位置中的其他使用者共用。</span><span class="sxs-lookup"><span data-stu-id="c8a18-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="c8a18-158">來自不同地理位置的內容將顯示在使用者之商務用 OneDrive 中的 [與我共用]\*\*\*\* 檢視中，無論裝載的地理位置為何，都可透過單一登入經驗來存取這些內容。</span><span class="sxs-lookup"><span data-stu-id="c8a18-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive for Business and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="c8a18-159">小組體驗</span><span class="sxs-lookup"><span data-stu-id="c8a18-159">Teams Experience</span></span>

<span data-ttu-id="c8a18-160">Teams 具有多地理位置感知功能。</span><span class="sxs-lookup"><span data-stu-id="c8a18-160">Teams is multi-geo aware.</span></span> <span data-ttu-id="c8a18-161">無論使用者的地理位置為何，都會顯示 OneDrive 檔案及最近檢視過的檔案。</span><span class="sxs-lookup"><span data-stu-id="c8a18-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="c8a18-162">所有地理位置的使用者都可以使用 @ 提及功能。</span><span class="sxs-lookup"><span data-stu-id="c8a18-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="c8a18-163">使用者設定檔</span><span class="sxs-lookup"><span data-stu-id="c8a18-163">User profiles</span></span>

<span data-ttu-id="c8a18-p113">系統會在使用者地理位置中管理使用者的設定檔資訊。選取使用者時，系統會將您導向至使用者的適當地理位置，您在其中可看到他們完整的設定檔詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c8a18-p113">User profile information is mastered in the user's geo location. When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="c8a18-166">如果將 Delve 關閉，您會在 SharePoint 中看到傳統設定檔經驗，這並不具備地理位置意識。</span><span class="sxs-lookup"><span data-stu-id="c8a18-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


