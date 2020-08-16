---
title: 資料移動一般常見問題集
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: 尋找常見問題解答 (FAQs) 將核心資料移至新的 Office 365 datacenter geo。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77d30778ae11865e5d773be4fa64db9b64480e76
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688627"
---
# <a name="data-move-general-faq"></a><span data-ttu-id="08b46-103">資料移動一般常見問題集</span><span class="sxs-lookup"><span data-stu-id="08b46-103">Data move general FAQ</span></span>

<span data-ttu-id="08b46-104">以下是有關將核心資料移至新資料中心地理位置的一般問題的解答。</span><span class="sxs-lookup"><span data-stu-id="08b46-104">Here are answers to general questions about moving core data to a new datacenter geo.</span></span>
  
## <a name="what-customers-are-eligible-to-request-a-move"></a><span data-ttu-id="08b46-105">哪些客戶適合要求移動？</span><span class="sxs-lookup"><span data-stu-id="08b46-105">What customers are eligible to request a move?</span></span>
  
<span data-ttu-id="08b46-106">選取符合新資料中心地理位置之國家/地區的現有 Microsoft 365 商業客戶將可以要求移動。</span><span class="sxs-lookup"><span data-stu-id="08b46-106">Existing Microsoft 365 commercial customers who selected a country eligible for the new datacenter geo will be able to request a move.</span></span>  <span data-ttu-id="08b46-107">此程式僅適用于具有合格國家/地區代碼的承租人指派給 Microsoft 365 租使用者，以便將適用工作負載的核心客戶資料移轉至對應的 Microsoft 365 資料中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="08b46-107">The program exists only for tenants with an eligible country code assigned to the Microsoft 365 tenant to migrate core customer data at rest for eligible workloads to the corresponding Microsoft 365 datacenter geo.</span></span>  <span data-ttu-id="08b46-108">請參閱 how [to 要求資料移動](request-your-data-move.md) 頁面以確認國家資格。</span><span class="sxs-lookup"><span data-stu-id="08b46-108">Please refer to the [How to request your data move](request-your-data-move.md) page to confirm country eligibility.</span></span>   

## <a name="how-do-we-define-core-customer-data"></a><span data-ttu-id="08b46-109">如何定義核心客戶資料？</span><span class="sxs-lookup"><span data-stu-id="08b46-109">How do we define Core Customer Data?</span></span>
 
<span data-ttu-id="08b46-110">核心客戶資料是指在 [Microsoft Online Services 條款](https://aka.ms/ost)中所定義之客戶資料的子集的字詞：</span><span class="sxs-lookup"><span data-stu-id="08b46-110">Core customer data is a term that refers to a subset of customer data defined in the [Microsoft Online Services Terms](https://aka.ms/ost):</span></span> 
- <span data-ttu-id="08b46-111">Exchange Online 信箱內容 (電子郵件內文、行事曆專案和電子郵件附件的內容) </span><span class="sxs-lookup"><span data-stu-id="08b46-111">Exchange Online mailbox content (email body, calendar entries, and the content of email attachments)</span></span>
- <span data-ttu-id="08b46-112">SharePoint 線上網站內容和儲存在該網站中的檔案</span><span class="sxs-lookup"><span data-stu-id="08b46-112">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="08b46-113">上傳至商務 OneDrive 的檔案</span><span class="sxs-lookup"><span data-stu-id="08b46-113">Files uploaded to OneDrive for Business</span></span> 

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a><span data-ttu-id="08b46-114">在我的遷移完成時，我的租使用者核心客戶資料已存放在我的新地理位置中？</span><span class="sxs-lookup"><span data-stu-id="08b46-114">At what point is my migration complete so that my tenant's core customer data is being stored at rest in my new geo?</span></span>

<span data-ttu-id="08b46-115">由於 Exchange Online 與 SharePoint 線上/OneDrive 間的共用相依性，在遷移這兩項服務之前，無法將任何遷移視為已完成。</span><span class="sxs-lookup"><span data-stu-id="08b46-115">Due to shared dependencies between Exchange Online and SharePoint Online/OneDrive for Business, any migration cannot be considered completed until both services are migrated.</span></span>  <span data-ttu-id="08b46-116">Exchange Online 和 SharePoint 線上/OneDrive，通常會以不同的時間進行遷移，並彼此獨立地進行遷移。</span><span class="sxs-lookup"><span data-stu-id="08b46-116">Exchange Online and SharePoint Online/OneDrive for Business often migrate at separate times and independently from one another.</span></span>  <span data-ttu-id="08b46-117">租使用者系統管理員會在每次服務遷移完成時于訊息中心接收確認，而且可以隨時查看系統管理中心內的資料位置卡，以確認每個服務的 rest 位置的核心客戶資料。</span><span class="sxs-lookup"><span data-stu-id="08b46-117">Tenant admins receive confirmation in Message Center when each service migration is completed and can view the data location card in the Admin Center at any time to confirm the core customer data at rest location for each service.</span></span>

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a><span data-ttu-id="08b46-118">如何在移動期間保證客戶資料是安全的，而且不會發生停機時間？</span><span class="sxs-lookup"><span data-stu-id="08b46-118">How do you make sure my customer data is safe during the move and that I won't experience downtime?</span></span>
  
<span data-ttu-id="08b46-119">資料移動是後端服務作業，對使用者影響最小。</span><span class="sxs-lookup"><span data-stu-id="08b46-119">Data moves are a back-end service operation with minimal impact to end-users.</span></span> <span data-ttu-id="08b46-120">在 [資料移動期間和之後，](during-and-after-your-data-move.md)會列出受影響的功能。</span><span class="sxs-lookup"><span data-stu-id="08b46-120">Features that can be impacted are listed in [During and after your data move](during-and-after-your-data-move.md).</span></span> <span data-ttu-id="08b46-121">我們遵循 [Microsoft Online Services 服務等級協定 (SLA) ](https://go.microsoft.com/fwlink/p/?LinkId=523897) 以取得可用性，讓客戶無需準備或在移動期間進行監視。</span><span class="sxs-lookup"><span data-stu-id="08b46-121">We adhere to the [Microsoft Online Services Service Level Agreement (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) for availability so there is nothing that customers need to prepare for or to monitor during the move.</span></span> 
  
<span data-ttu-id="08b46-122">所有 Microsoft 365 服務都會在資料中心內執行相同的版本，因此您可以保證一致的功能。</span><span class="sxs-lookup"><span data-stu-id="08b46-122">All Microsoft 365 services run the same versions in the datacenters, so you can be assured of consistent functionality.</span></span> <span data-ttu-id="08b46-123">整個程式都完全支援您的服務。</span><span class="sxs-lookup"><span data-stu-id="08b46-123">Your service is fully supported throughout the process.</span></span>

## <a name="what-is-in-scope-for-teams-migration"></a><span data-ttu-id="08b46-124">團隊遷移的範圍為何？</span><span class="sxs-lookup"><span data-stu-id="08b46-124">What is in scope for Teams migration?</span></span>

<span data-ttu-id="08b46-125">除了 Exchange Online、SharePoint 線上和商務 OneDrive;Microsoft 會將小組資料移轉至本機資料中心。</span><span class="sxs-lookup"><span data-stu-id="08b46-125">In addition to Exchange Online, SharePoint Online, and OneDrive for Business; Microsoft will migrate Teams data to the local datacenter.</span></span>  
- <span data-ttu-id="08b46-126">小組會聊天訊息，包括私人郵件和通道訊息。</span><span class="sxs-lookup"><span data-stu-id="08b46-126">Teams chat messages, including private messages and channel messages.</span></span> 
- <span data-ttu-id="08b46-127">在聊天中使用的小組圖像。</span><span class="sxs-lookup"><span data-stu-id="08b46-127">Teams images used in chats.</span></span> 

<span data-ttu-id="08b46-128">小組檔案會儲存在 SharePoint 線上中，小組聊天檔會儲存在商務 OneDrive 中。</span><span class="sxs-lookup"><span data-stu-id="08b46-128">Teams files are stored in SharePoint Online and Teams chat files are stored in OneDrive for Business.</span></span>  <span data-ttu-id="08b46-129">語音信箱、行事曆、聊天記錄和連絡人會儲存在 Exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="08b46-129">Voicemail, calendar, chat history, and contacts are stored in Exchange Online.</span></span>  <span data-ttu-id="08b46-130">在許多情況下，使用者已在本機資料中心地理位置中使用 Exchange Online、SharePoint 線上和商務 OneDrive，而且也是適用于合格客戶國家/地區的 Microsoft 365 遷移計畫的一部分。</span><span class="sxs-lookup"><span data-stu-id="08b46-130">In many cases, Exchange Online, SharePoint Online and OneDrive for Business are already used by the customer in the local datacenter geo and are also part of the Microsoft 365 migration program for eligible customer countries.</span></span>
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a><span data-ttu-id="08b46-131">不同的服務位於不同的 geos 會有什麼影響？</span><span class="sxs-lookup"><span data-stu-id="08b46-131">What is the impact of having different services located in different geos?</span></span>

<span data-ttu-id="08b46-132">有些 Microsoft 365 服務可能位於不同的 geos 中，供一些現有的客戶及在移動程式中間的客戶。</span><span class="sxs-lookup"><span data-stu-id="08b46-132">Some of the Microsoft 365 services may be located in different geos for some existing customers and for customers that are in the middle of the move process.</span></span> <span data-ttu-id="08b46-133">我們的服務彼此獨立執行，且在這種情況下不會影響使用者的體驗。</span><span class="sxs-lookup"><span data-stu-id="08b46-133">Our services run independently of each other and there is no impact on the user experience if this is the case.</span></span><span data-ttu-id="08b46-134">不過，針對資料派駐服務的目的，在 Exchange Online 和 SharePoint 商務線上/OneDrive 皆遷移至相同的資料中心地理位置之前，無法將租使用者遷移視為完整。</span><span class="sxs-lookup"><span data-stu-id="08b46-134"> However, for data residency purposes, a tenant migration cannot be considered as complete until both Exchange Online and SharePoint Online/OneDrive for Business are migrated to the same datacenter geo.</span></span>
  
## <a name="will-new-microsoft-365-customers-be-automatically-provisioned-in-the-new-datacenter-geos"></a><span data-ttu-id="08b46-135">在新的資料中心 geos 中，是否會自動布建新的 Microsoft 365 客戶？</span><span class="sxs-lookup"><span data-stu-id="08b46-135">Will new Microsoft 365 customers be automatically provisioned in the new datacenter geos?</span></span>
  
<span data-ttu-id="08b46-136">是。</span><span class="sxs-lookup"><span data-stu-id="08b46-136">Yes.</span></span> <span data-ttu-id="08b46-137">新的資料中心地理位置可供使用時，新的 Microsoft 365 客戶若在註冊時選取符合新地理位置的國家/地區，將其核心客戶資料儲存在新的資料中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="08b46-137">Once a new datacenter geo is available, new Microsoft 365 customers who select a country eligible for the new geo as their country during sign-up will have their core customer data stored at rest in the new datacenter geo.</span></span>
  
 ## <a name="where-is-my-core-customer-data-located"></a><span data-ttu-id="08b46-138">我的核心客戶資料位於何處？</span><span class="sxs-lookup"><span data-stu-id="08b46-138">Where is my core customer data located?</span></span>

<span data-ttu-id="08b46-139">租使用者系統管理員可以隨時查看系統管理中心內的資料位置卡，以確認每個服務（特別是針對其租使用者）的核心客戶資料。</span><span class="sxs-lookup"><span data-stu-id="08b46-139">Tenant admins can view the data location card in the Admin Center at any time to confirm the core customer data at rest location for each service, specifically for their tenant.</span></span><span data-ttu-id="08b46-140">我們也會將 office [365 互動式資料中心 ](https://office.com/datamaps) 的資料中心 geos、資料中心和365位置的位置發佈，做為參考，以供新承租人的靜止位置的目前預設核心客戶資料參考。</span><span class="sxs-lookup"><span data-stu-id="08b46-140">  We also publish the location of datacenter geos, datacenters, and location of Office 365 customer data on the [Office 365 interactive datacenter maps ](https://office.com/datamaps) as a reference for the current default core customer data at rest locations for new tenants.</span></span>  <span data-ttu-id="08b46-141">您可以透過 Microsoft 365 系統管理中心中組織設定檔底下的 [資料位置] 區段，確認您的客戶資料在 rest 上的位置。</span><span class="sxs-lookup"><span data-stu-id="08b46-141">You can verify the location of your customer data at rest via the Data Location section under your Organization Profile in the Microsoft 365 Admin Center.</span></span>  
 
## <a name="when-will-i-be-able-to-request-a-move"></a><span data-ttu-id="08b46-142">何時可以要求移動？</span><span class="sxs-lookup"><span data-stu-id="08b46-142">When will I be able to request a move?</span></span>
  
<span data-ttu-id="08b46-143">請參閱 [如何要求資料移動](request-your-data-move.md) 頁面以取得資料中心地理位置支援的時段。</span><span class="sxs-lookup"><span data-stu-id="08b46-143">Please refer to the [How to request your data move](request-your-data-move.md) page for supported timeframes for your datacenter geo.</span></span>
  
## <a name="how-can-i-request-to-be-moved"></a><span data-ttu-id="08b46-144">我可以要求移動的要求為何？</span><span class="sxs-lookup"><span data-stu-id="08b46-144">How can I request to be moved?</span></span>
  
<span data-ttu-id="08b46-145">合格的客戶將會在其 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)看到一頁。</span><span class="sxs-lookup"><span data-stu-id="08b46-145">Eligible customers will see a page in their [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="08b46-146">請參閱 how [to 要求資料移動](request-your-data-move.md) 以取得如何要求移動的指示。</span><span class="sxs-lookup"><span data-stu-id="08b46-146">Please see [How to request your data move](request-your-data-move.md) for instructions on how to request a move.</span></span> 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a><span data-ttu-id="08b46-147">在要求移動之後，是否可以變更我的選取專案？</span><span class="sxs-lookup"><span data-stu-id="08b46-147">Can I change my selection after requesting a move?</span></span>
  
<span data-ttu-id="08b46-148">在您提交要求之後，我們無法將您的程式移除。</span><span class="sxs-lookup"><span data-stu-id="08b46-148">It is not possible for us to remove you from the process after you submit your request.</span></span>
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a><span data-ttu-id="08b46-149">如果我不要求在期限之前移動，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="08b46-149">What happens if I do not request a move before the deadline?</span></span>
  
<span data-ttu-id="08b46-150">我們可能會根據例外情況接受要求，以授與您的租使用者完成移動的承諾期限。</span><span class="sxs-lookup"><span data-stu-id="08b46-150">We may be able to accept requests on an exception basis to grant your tenant a committed deadline to complete the move.</span></span> <span data-ttu-id="08b46-151">請   與 [Microsoft 365 支援](https://go.microsoft.com/fwlink/p/?LinkID=522459) 人員聯繫，以提出要求。</span><span class="sxs-lookup"><span data-stu-id="08b46-151">Please  contact [Microsoft 365 Support](https://go.microsoft.com/fwlink/p/?LinkID=522459) to make the request.</span></span>

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a><span data-ttu-id="08b46-152">如果我想要移動資料以取得更好的網路效能，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="08b46-152">What if I want to move my data in order to get better network performance?</span></span>
  
<span data-ttu-id="08b46-153">與 Microsoft 365 資料中心的實體接近，不會保證更好的網路效能。</span><span class="sxs-lookup"><span data-stu-id="08b46-153">Physical proximity to a Microsoft 365 datacenter is not a guarantee for a better networking performance.</span></span> <span data-ttu-id="08b46-154">有許多因素和元件會影響使用者與 Microsoft 365 服務之間的網路效能。</span><span class="sxs-lookup"><span data-stu-id="08b46-154">There are many factors and components that impact the network performance between the end-user and the Microsoft 365 service.</span></span> <span data-ttu-id="08b46-155">如需此和效能調整的詳細資訊，請參閱 [Microsoft 365 的網路規劃和效能調整](network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="08b46-155">For more information about this and performance tuning see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a><span data-ttu-id="08b46-156">所有服務是否會將其資料在同一天內移動？</span><span class="sxs-lookup"><span data-stu-id="08b46-156">Do all the services move their data on the same day?</span></span>
 
<span data-ttu-id="08b46-157">每個服務都會獨立移動，而且可能會在不同的時間移動其資料。</span><span class="sxs-lookup"><span data-stu-id="08b46-157">Each service moves independently and will likely move their data at different times.</span></span>
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a><span data-ttu-id="08b46-158">我是否可以選擇何時移動資料？</span><span class="sxs-lookup"><span data-stu-id="08b46-158">Can I choose when I want my data to be moved?</span></span>
 
<span data-ttu-id="08b46-159">客戶無法選取特定日期、不能延遲其移動，而且無法共用移動的特定日期或時間範圍。</span><span class="sxs-lookup"><span data-stu-id="08b46-159">Customers are not able to select a specific date, they cannot delay their move, and we cannot share a specific date or timeframe for the moves.</span></span>
  
 ## <a name="can-you-share-when-my-data-will-be-be-moved"></a><span data-ttu-id="08b46-160">您是否可以在移動資料時進行共用？</span><span class="sxs-lookup"><span data-stu-id="08b46-160">Can you share when my data will be be moved?</span></span>
  
<span data-ttu-id="08b46-161">資料移動是後端作業，對使用者的影響最小。</span><span class="sxs-lookup"><span data-stu-id="08b46-161">Data moves are a back-end operation with minimal impact to end-users.</span></span> <span data-ttu-id="08b46-162">複雜性、精確度及規模，我們需要在全域運作及自動環境中執行資料移動，禁止當您的租使用者或任何其他單一租使用者完成資料移動時，無法進行共用。</span><span class="sxs-lookup"><span data-stu-id="08b46-162">The complexity, precision and scale at which we need to perform data moves within a globally operated and automated environment prohibit us from sharing when a data move is expected to complete for your tenant or any other single tenant.</span></span> <span data-ttu-id="08b46-163">當客戶的資料移動完成時，客戶會在訊息中心接收一次確認。</span><span class="sxs-lookup"><span data-stu-id="08b46-163">Customers will receive one confirmation in Message Center per participating service when its data move has completed.</span></span> 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a><span data-ttu-id="08b46-164">如果使用者在資料移動時存取服務，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="08b46-164">What happens if users access services while the data is being moved?</span></span>

<span data-ttu-id="08b46-165">在 [資料移動期間和之後](during-and-after-your-data-move.md) ，請參閱資料移動的完整清單可能會限制，以供每個服務的資料移動部分使用。</span><span class="sxs-lookup"><span data-stu-id="08b46-165">See [During and after your data move](during-and-after-your-data-move.md) for a complete list of features that may be limited during portions of the data move for each service.</span></span> 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a><span data-ttu-id="08b46-166">如何知道移動已完成？</span><span class="sxs-lookup"><span data-stu-id="08b46-166">How do I know the move is complete?</span></span>
  
<span data-ttu-id="08b46-167">觀賞 Microsoft 365 訊息中心，以確認每個服務資料的移動是否已完成。</span><span class="sxs-lookup"><span data-stu-id="08b46-167">Watch the Microsoft 365 Message Center for confirmation that the move of each service's data is complete.</span></span> <span data-ttu-id="08b46-168">當每個服務的資料移動時，我們會發佈一個完成通知，讓您可以取得三個完成通知：一個適用于 Exchange Online、SharePoint 線上和商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="08b46-168">When each service's data is moved, we'll post a completion notice so you'll get three completion notices: one each for Exchange Online, SharePoint Online, and Skype for Business Online.</span></span>  <span data-ttu-id="08b46-169">您也可以透過 Microsoft 365 系統管理中心中組織設定檔底下的 [資料位置] 區段，確認 rest 上的客戶資料的位置。</span><span class="sxs-lookup"><span data-stu-id="08b46-169">You can also verify the location of your customer data at rest via the Data Location section under your Organization Profile in the Microsoft 365 Admin Center.</span></span>  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a><span data-ttu-id="08b46-170">我是在其中一個新的資料中心 geos 中的 Microsoft 365 客戶，但是當我註冊時，我選取不同的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="08b46-170">I am a Microsoft 365 customer in one of the new datacenter geos, but when I signed up, I selected a different country.</span></span> <span data-ttu-id="08b46-171">我可以如何移至新的資料中心地理位置？</span><span class="sxs-lookup"><span data-stu-id="08b46-171">How can I be moved to the new datacenter geo?</span></span>

<span data-ttu-id="08b46-172">您不可能變更與租使用者相關聯的註冊國家/地區。</span><span class="sxs-lookup"><span data-stu-id="08b46-172">It is not possible to change the signup country associated with your tenant.</span></span> <span data-ttu-id="08b46-173">相反地，您必須使用新的訂閱建立新的 Microsoft 365 租使用者，並將使用者和資料手動移至新的租使用者。</span><span class="sxs-lookup"><span data-stu-id="08b46-173">Instead, you need to create a new Microsoft 365 tenant with a new subscription and manually move your users and data to the new tenant.</span></span>
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a><span data-ttu-id="08b46-174">在 Exchange Online 移動期間，如果我們正在將電子郵件資料移轉至 Microsoft 365，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="08b46-174">What happens if we are in process of email data migration to Microsoft 365 during the Exchange Online move?</span></span>

<span data-ttu-id="08b46-175">這是一種非常常見的案例，而且受到完全支援。</span><span class="sxs-lookup"><span data-stu-id="08b46-175">This is a very common scenario and is fully supported.</span></span>  <span data-ttu-id="08b46-176">資料中心 geos 之間的雲端遷移不會干擾任何 on premisis 到雲端信箱遷移。</span><span class="sxs-lookup"><span data-stu-id="08b46-176">Cloud migration between datacenter geos does not interfere with any on-premisis to cloud mailbox migrations.</span></span>
  
 ## <a name="can-i-pilot-some-users"></a><span data-ttu-id="08b46-177">我可以試驗部分使用者嗎？</span><span class="sxs-lookup"><span data-stu-id="08b46-177">Can I pilot some users?</span></span>
  
<span data-ttu-id="08b46-178">您可以建立個別的試用租使用者來測試連線能力，但試用租使用者無法以任何方式結合現有的租使用者。</span><span class="sxs-lookup"><span data-stu-id="08b46-178">You can create a separate trial tenant to test connectivity, but the trial tenant can't be combined in any way with your existing tenant.</span></span>

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a><span data-ttu-id="08b46-179">我不想要等候 Microsoft 移動我的資料。</span><span class="sxs-lookup"><span data-stu-id="08b46-179">I don't want to wait for Microsoft to move my data.</span></span> <span data-ttu-id="08b46-180">我是否可以只建立新租使用者並自行移動？</span><span class="sxs-lookup"><span data-stu-id="08b46-180">Can I just create a new tenant and move myself?</span></span>
  
<span data-ttu-id="08b46-181">是的，不過處理常式不會像 Microsoft 執行資料移動一樣順利。</span><span class="sxs-lookup"><span data-stu-id="08b46-181">Yes, however the process will not be as seamless as if Microsoft were to perform the data move.</span></span>
  
<span data-ttu-id="08b46-182">如果您在新的資料中心地理位置之後建立新租使用者，則新的租使用者將會主控于新的 geo 中。</span><span class="sxs-lookup"><span data-stu-id="08b46-182">If you create a new tenant after the new datacenter geo is available, the new tenant will be hosted in the new geo.</span></span> <span data-ttu-id="08b46-183">這個新租使用者完全不同于您先前的承租人，您會負責移動所有使用者信箱、網站內容、功能變數名稱及其他任何資料。</span><span class="sxs-lookup"><span data-stu-id="08b46-183">This new tenant is completely separate from your previous tenant and you would be responsible for moving all user mailboxes, site content, domain names, and any other data.</span></span> <span data-ttu-id="08b46-184">請注意，您無法將租使用者名稱從一個承租人移至另一個承租人。</span><span class="sxs-lookup"><span data-stu-id="08b46-184">Note that you can't move the tenant name from one tenant to another.</span></span> <span data-ttu-id="08b46-185">建議您等候 Microsoft 所提供的移動程式，因為我們會為您移動使用者的所有設定、資料和訂閱。</span><span class="sxs-lookup"><span data-stu-id="08b46-185">We recommend that you wait for the move program provided by Microsoft as we'll take care of moving all settings, data, and subscriptions for your users.</span></span>
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a><span data-ttu-id="08b46-186">我的客戶資料已經移至新的資料中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="08b46-186">My customer data has already been moved to a new datacenter geo.</span></span> <span data-ttu-id="08b46-187">我可以再移回來嗎？</span><span class="sxs-lookup"><span data-stu-id="08b46-187">Can I move back?</span></span>
 
<span data-ttu-id="08b46-188">否，這是不可能的。</span><span class="sxs-lookup"><span data-stu-id="08b46-188">No, this is not possible.</span></span> <span data-ttu-id="08b46-189">移至新 geo 資料中心的客戶無法移回。</span><span class="sxs-lookup"><span data-stu-id="08b46-189">Customers who have been moved to new geo datacenters cannot be moved back.</span></span> <span data-ttu-id="08b46-190">身為任何地理位置的客戶，您會體驗到相同品質的服務、效能及安全性控制。</span><span class="sxs-lookup"><span data-stu-id="08b46-190">As a customer in any geo, you will experience the same quality of service, performance, and security controls as you did before.</span></span>  <span data-ttu-id="08b46-191">[Microsoft 365 多地理](https://aka.ms/multi-geo) 位置可供部分客戶做為附加元件，並可讓單一租使用者建立多個衛星 geos，並將使用者資料移至具有資料派駐承諾的 geos。</span><span class="sxs-lookup"><span data-stu-id="08b46-191">[Microsoft 365 Multi Geo](https://aka.ms/multi-geo) is available to some customers as an add-on and lets a single tenant create multiple satellite geos and move user data to those geos with data residency commitments.</span></span>
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a><span data-ttu-id="08b46-192">位於新資料中心的 Microsoft 365 租使用者是否可供全國以外的使用者使用？</span><span class="sxs-lookup"><span data-stu-id="08b46-192">Will Microsoft 365 tenants hosted in the new datacenters be available to users outside of the country?</span></span>
  
<span data-ttu-id="08b46-193">是。</span><span class="sxs-lookup"><span data-stu-id="08b46-193">Yes.</span></span> <span data-ttu-id="08b46-194">Microsoft 會在世界各地的35國家/地區內，以超過130個位置的 Internet 服務提供者（ (Isp) 中的對2700等合約來維護具有相關合約的大型全域網路。</span><span class="sxs-lookup"><span data-stu-id="08b46-194">Microsoft maintains a large global network with public Internet connections in more than 130 locations in 35 countries around the world with peering agreements with more than 2,700 Internet Service Providers (ISPs).</span></span> <span data-ttu-id="08b46-195">使用者將能夠從網際網路上的任何地方存取資料中心。</span><span class="sxs-lookup"><span data-stu-id="08b46-195">Users will be able to access the datacenters from wherever they are on the Internet.</span></span>

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a><span data-ttu-id="08b46-196">我的承租人已設定 [多地理位置附加](https://aka.ms/multi-geo)元件。</span><span class="sxs-lookup"><span data-stu-id="08b46-196">My tenant has configured the [Multi Geo add-on](https://aka.ms/multi-geo).</span></span> <span data-ttu-id="08b46-197">我是否可以在 Microsoft 365 移動程式中註冊我的租使用者，以變更我的預設地理位置，並將不在附屬區域中的任何使用者移至新的預設地理位置？</span><span class="sxs-lookup"><span data-stu-id="08b46-197">Can I still enroll in my tenant in the Microsoft 365 Move Program to change my default geo and move any user not in a satellite region to the new default geo?</span></span>

<span data-ttu-id="08b46-198">是的，您的租使用者可供註冊。</span><span class="sxs-lookup"><span data-stu-id="08b46-198">Yes, your tenant is eligible to enroll.</span></span> <span data-ttu-id="08b46-199">我們會將所有 EXO 信箱從您目前的預設地理位置移至新的本機資料中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="08b46-199">We will move all EXO mailboxes from your current default geo to your new local datacenter geo.</span></span>  <span data-ttu-id="08b46-200">我們不會移動在多地理位置衛星區域中設定的任何 EXO 信箱，繼續依照預定的方式，繼續遵循衛星區域資料派駐服務。</span><span class="sxs-lookup"><span data-stu-id="08b46-200">We will not move any EXO mailboxes configured in Multi Geo satellite regions to continue to respect satellite region data residency as you’ve intended.</span></span>  

<span data-ttu-id="08b46-201">SharePoint Online 和商務 OneDrive 若要在移動程式中將其遷移至新的資料中心地理位置，雖然您可以設定商務股 OneDrive，以移至您想透過多地理位置計畫的任何區域。</span><span class="sxs-lookup"><span data-stu-id="08b46-201">SharePoint Online and OneDrive for Business cannot migrate to the new datacenter geo as part of the Move Program, though you can configure OneDrive for Business shares to move to any region you wish via the Multi Geo program.</span></span>

## <a name="related-topics"></a><span data-ttu-id="08b46-202">相關主題</span><span class="sxs-lookup"><span data-stu-id="08b46-202">Related topics</span></span>

[<span data-ttu-id="08b46-203">將核心資料移至新的 Microsoft 365 datacenter geos</span><span class="sxs-lookup"><span data-stu-id="08b46-203">Moving core data to new Microsoft 365 datacenter geos</span></span>](moving-data-to-new-datacenter-geos.md)

[<span data-ttu-id="08b46-204">如何要求資料移動</span><span class="sxs-lookup"><span data-stu-id="08b46-204">How to request your data move</span></span>](request-your-data-move.md)

[<span data-ttu-id="08b46-205">Microsoft 365 多地理位置</span><span class="sxs-lookup"><span data-stu-id="08b46-205">Microsoft 365 Multi Geo</span></span>](https://aka.ms/multi-geo)

[<span data-ttu-id="08b46-206">Microsoft 365 互動式 datacenter 地圖</span><span class="sxs-lookup"><span data-stu-id="08b46-206">Microsoft 365 interactive datacenter map</span></span>](https://office.com/datamaps)

[<span data-ttu-id="08b46-207">Microsoft 365 支援</span><span class="sxs-lookup"><span data-stu-id="08b46-207">Microsoft 365 Support</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[<span data-ttu-id="08b46-208">Microsoft Dynamics CRM Online 的新 datacenter geos</span><span class="sxs-lookup"><span data-stu-id="08b46-208">New datacenter geos for Microsoft Dynamics CRM Online</span></span>](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[<span data-ttu-id="08b46-209">依地區的 Azure 服務</span><span class="sxs-lookup"><span data-stu-id="08b46-209">Azure services by region</span></span>](https://azure.microsoft.com/regions/)