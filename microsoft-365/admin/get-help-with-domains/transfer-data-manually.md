---
title: 在兩個帳戶間手動傳輸資料
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 尋找當您變更計畫或公司名稱時，如何在兩部 Microsoft 365 帳戶之間手動傳輸資料，或將多個訂閱組合為一個。
ms.openlocfilehash: b7b0bb9c9b95b31d98040ae90632ef87a7fb0e3b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645140"
---
# <a name="transfer-data-manually-between-two-accounts"></a><span data-ttu-id="8d34a-103">在兩個帳戶間手動傳輸資料</span><span class="sxs-lookup"><span data-stu-id="8d34a-103">Transfer data manually between two accounts</span></span>

<span data-ttu-id="8d34a-104">準備逐步 sleeves，並在行事曆中封鎖時間區塊：在兩個 Microsoft 365 帳戶之間傳輸資料是手動、複雜且耗時的處理常式。</span><span class="sxs-lookup"><span data-stu-id="8d34a-104">Prepare to roll up your sleeves and block out a chunk of time on your calendar: transferring data between two Microsoft 365 accounts is a manual, complicated, and time-consuming process.</span></span> <span data-ttu-id="8d34a-105">這不是自動化或支援的處理常式。</span><span class="sxs-lookup"><span data-stu-id="8d34a-105">This is not an automated or supported process.</span></span> <span data-ttu-id="8d34a-106">我們將開始著手。</span><span class="sxs-lookup"><span data-stu-id="8d34a-106">We'll get you started.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8d34a-107">在處理電子郵件、商務用 Skype 和主控于 Microsoft 365 的公用網站時，會發生停機時間。</span><span class="sxs-lookup"><span data-stu-id="8d34a-107">There will be down time during the process where email, Skype for Business and a public website hosted on Microsoft 365 won't work.</span></span> <span data-ttu-id="8d34a-108">使用者將會收到新的使用者名稱和密碼，並將需要重設 Outlook。</span><span class="sxs-lookup"><span data-stu-id="8d34a-108">Users will get new user names and passwords, and they'll need to reset up Outlook.</span></span>

<span data-ttu-id="8d34a-109">**若有下列其中一項適用，請僅使用本主題中的指示手動傳送資料：**</span><span class="sxs-lookup"><span data-stu-id="8d34a-109">**Only transfer data manually using the instructions in this topic if one of the following applies:**</span></span>
  
- <span data-ttu-id="8d34a-110">您必須變更為不同服務系列中的計畫。</span><span class="sxs-lookup"><span data-stu-id="8d34a-110">You need to change to a plan in a different service family.</span></span>

- <span data-ttu-id="8d34a-111">您的公司名稱已變更，您決定建立新的訂閱並遷移您的資料，因為您想要使用不同的初始功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-111">Your company name changed, and you decided to create a new subscription and migrate your data because you want to use different initial domain names.</span></span>

- <span data-ttu-id="8d34a-112">您需要將多個訂閱合併成一個新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-112">You need to combine multiple subscriptions into one new one.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d34a-113">如果您需要 [變更您的訂閱計畫](../../commerce/subscriptions/switch-to-a-different-plan.md) ，而且可以使用 [切換方案] 嚮導; 或者，如果您需要在相同訂閱系列中轉移至新的訂閱計畫，即使 [切換方案] 嚮導無法運作，您不需要手動傳輸資料，也沒有停機時間。</span><span class="sxs-lookup"><span data-stu-id="8d34a-113">If you need to [change your subscription plan](../../commerce/subscriptions/switch-to-a-different-plan.md) and can use the Switch plans wizard, or if you need to transfer to a new subscription plan in the same subscription family even when the Switch plans wizard doesn't work, you don't need to manually transfer your data, and there is no down time.</span></span>

|<span data-ttu-id="8d34a-114">**Tasks**</span><span class="sxs-lookup"><span data-stu-id="8d34a-114">**Tasks**</span></span>|<span data-ttu-id="8d34a-115">**Steps**</span><span class="sxs-lookup"><span data-stu-id="8d34a-115">**Steps**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8d34a-116">購買您想要移至的計畫。</span><span class="sxs-lookup"><span data-stu-id="8d34a-116">Purchase the plan you want to move to.</span></span>  <br/> |<span data-ttu-id="8d34a-117">當您註冊時，您可以指定要在初始功能變數名稱中使用的公司名稱：  *yourcompany*  onmicrosoft.com、  *yourcompany*  -public.sharepoint.com 及  *yourcompany*  。</span><span class="sxs-lookup"><span data-stu-id="8d34a-117">When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com.</span></span> <span data-ttu-id="8d34a-118">您需要使用與任何現有訂閱相同的  *yourcompany*  名稱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-118">You need to use a different  *yourcompany*  name than you did for any existing subscriptions.</span></span>  <br/> <span data-ttu-id="8d34a-119">> [!NOTE]> 取消訂閱以發行從我們系統中使用  *yourcompany*  的初始功能變數名稱後，一般至少需要數個月。</span><span class="sxs-lookup"><span data-stu-id="8d34a-119">> [!NOTE]>  It typically takes a minimum of several months after cancelling a subscription to release the initial domain names that use  *yourcompany*  from our systems.</span></span> <span data-ttu-id="8d34a-120">即使您計畫將所有資料儲存在舊的 Microsoft 365 訂閱中，並取消該訂閱，舊的  *yourcompany*  值不會立即可用於新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-120">Even if you plan to save all your data from your old Microsoft 365 subscription, and cancel that subscription, the old  *yourcompany*  value is not immediately available for use in a new subscription.</span></span>           |
|<span data-ttu-id="8d34a-121">從舊的 Microsoft 365 訂閱中移除您的自訂網域。</span><span class="sxs-lookup"><span data-stu-id="8d34a-121">Remove your custom domain from your old Microsoft 365 subscription.</span></span>  <br/> | <span data-ttu-id="8d34a-122">在 [您移除網域](remove-a-domain.md) 以從使用者電子郵件地址中移除功能變數名稱和移除自訂網域的電子郵件和 LYNC 的 DNS 記錄之前，請遵循必要的步驟。</span><span class="sxs-lookup"><span data-stu-id="8d34a-122">Follow the [required steps before you remove a domain](remove-a-domain.md) to remove the domain name from user email addresses and remove DNS records for email and Lync for the custom domain.</span></span> <span data-ttu-id="8d34a-123">如果您在 Microsoft 365 上主控公用網站，您也需要移除指向該網站的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="8d34a-123">If you host your public website on Microsoft 365, you'll also need to remove the CNAME record that points to it.</span></span>  <br/> <span data-ttu-id="8d34a-124">> [!IMPORTANT]> 在您移除將電子郵件路由傳送至此自訂網域的 MX 記錄後，電子郵件將停止運作，直到您將網域新增至您的新帳戶、設定新的 MX 記錄，並設定您的使用者。</span><span class="sxs-lookup"><span data-stu-id="8d34a-124">> [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users.</span></span> <span data-ttu-id="8d34a-125">當您移除 Lync 的 DNS 記錄時，Lync 將停止運作。</span><span class="sxs-lookup"><span data-stu-id="8d34a-125">When you remove the DNS records for Lync, Lync will stop working.</span></span> <span data-ttu-id="8d34a-126">移除指向您公用網站的 CNAME 記錄之後，將無法使用此記錄。</span><span class="sxs-lookup"><span data-stu-id="8d34a-126">And after you remove the CNAME record that points to your public website, it will not be available.</span></span>           <span data-ttu-id="8d34a-127">[移除網域](remove-a-domain.md) 。</span><span class="sxs-lookup"><span data-stu-id="8d34a-127">[Remove the domain](remove-a-domain.md) .</span></span>  <br/> |
|<span data-ttu-id="8d34a-128">為您的新訂閱設定您的自訂網域，並設定您的使用者。</span><span class="sxs-lookup"><span data-stu-id="8d34a-128">Set up your custom domain for your new subscription, and set up your users.</span></span>  <br/> | <span data-ttu-id="8d34a-129">設定您的新訂閱，包括為您的自訂網域建立所需的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="8d34a-129">Set up your new subscription, including creating the required DNS records for your custom domain.</span></span>  <br/>  <span data-ttu-id="8d34a-130">建立您的使用者，並在自訂網域上使用電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8d34a-130">Create your users, with email addresses on your custom domain.</span></span>  <br/> |
|<span data-ttu-id="8d34a-131">將舊訂閱中的資料傳送至新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-131">Transfer data from your old subscription to your new subscription.</span></span>  <br/> | <span data-ttu-id="8d34a-132">在不同的瀏覽器視窗中登入這兩個帳戶：</span><span class="sxs-lookup"><span data-stu-id="8d34a-132">Sign in to both accounts in separate browser windows:</span></span>  <br/>  <span data-ttu-id="8d34a-133">以滑鼠右鍵按一下瀏覽器圖示，然後開啟兩個私人瀏覽器視窗。</span><span class="sxs-lookup"><span data-stu-id="8d34a-133">Right-click your browser icon, and open two private browser windows.</span></span> <span data-ttu-id="8d34a-134">您可以在兩個 windows 中使用不同的認證來登入這兩個帳戶。</span><span class="sxs-lookup"><span data-stu-id="8d34a-134">You can use different credentials in the two windows to sign in on both accounts.</span></span>  <br/> [<span data-ttu-id="8d34a-135">在訂閱間傳輸系統管理設定</span><span class="sxs-lookup"><span data-stu-id="8d34a-135">Transfer administrative settings between subscriptions</span></span>](#email) <br/> [<span data-ttu-id="8d34a-136">傳輸小組網站結構和資料</span><span class="sxs-lookup"><span data-stu-id="8d34a-136">Transfer team site structure and data</span></span>](#transfer-team-site-structure-and-data) <br/> [<span data-ttu-id="8d34a-137">在訂閱間傳輸公用網站</span><span class="sxs-lookup"><span data-stu-id="8d34a-137">Transfer a public website between subscriptions</span></span>](#transfer-a-public-website-between-subscriptions) <br/> [<span data-ttu-id="8d34a-138">在訂閱間傳輸系統管理設定</span><span class="sxs-lookup"><span data-stu-id="8d34a-138">Transfer administrative settings between subscriptions</span></span>](#email) <br/> |
|<span data-ttu-id="8d34a-139">呼叫 Microsoft Support for Microsoft 365，以取消所做計畫的訂閱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-139">Cancel the subscription for the plan you're done with by calling Microsoft Support for Microsoft 365.</span></span>  <br/> | <span data-ttu-id="8d34a-140">請確認您的新訂閱是否正常運作，且所有資料都已傳輸。</span><span class="sxs-lookup"><span data-stu-id="8d34a-140">Verify that your new subscription is working and all data has been transferred.</span></span>  <br/>  <span data-ttu-id="8d34a-141">[請與客戶支援部門聯繫](../contact-support-for-business-products.md) 以取消舊的訂閱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-141">[Contact customer support](../contact-support-for-business-products.md) to cancel your old subscription.</span></span>  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a><span data-ttu-id="8d34a-142">在訂閱間傳輸系統管理設定</span><span class="sxs-lookup"><span data-stu-id="8d34a-142">Transfer administrative settings between subscriptions</span></span>

<span data-ttu-id="8d34a-143">移至每個帳戶的下列頁面，並根據舊帳戶的設定，設定新帳戶。</span><span class="sxs-lookup"><span data-stu-id="8d34a-143">Go to the following pages on each account, and set up the new account based on the old account's settings.</span></span>
  
<span data-ttu-id="8d34a-144">如果您要將資料從 Microsoft 365 轉接至 Microsoft 365 中型企業或 Microsoft 365 企業版，系統管理員頁面會以不同的方式結構化。</span><span class="sxs-lookup"><span data-stu-id="8d34a-144">If you are transferring data from Microsoft 365 to Microsoft 365 Midsize Business or Microsoft 365 Enterprise, the admin pages are structured differently.</span></span> <span data-ttu-id="8d34a-145">觀賞 [影片：介紹 Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)，然後移至下列位置，以查看系統管理設定。</span><span class="sxs-lookup"><span data-stu-id="8d34a-145">Watch a [Video: Introducing Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/), and go to the following places to look at admin settings.</span></span>
  
<span data-ttu-id="8d34a-146">Microsoft 365 企業版和 Microsoft 365 中型企業版：</span><span class="sxs-lookup"><span data-stu-id="8d34a-146">For Microsoft 365 Enterprise and Microsoft 365 Midsize Business:</span></span>
  
|<span data-ttu-id="8d34a-147">**位置**</span><span class="sxs-lookup"><span data-stu-id="8d34a-147">**Location**</span></span>|<span data-ttu-id="8d34a-148">**用途**</span><span class="sxs-lookup"><span data-stu-id="8d34a-148">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8d34a-149">系統**管理員** \>**Microsoft 365** \>**服務設定**</span><span class="sxs-lookup"><span data-stu-id="8d34a-149">**Admin** \> **Microsoft 365** \> **Service settings**</span></span> <br/> |<span data-ttu-id="8d34a-150">選取每個索引標籤，以查看郵件、網站、Lync、使用者軟體、密碼、群組、版權管理及行動裝置的設定。</span><span class="sxs-lookup"><span data-stu-id="8d34a-150">Select each tab for settings for mail, sites, Lync, user software, passwords, community, rights management, and mobile.</span></span>  <br/> |
|<span data-ttu-id="8d34a-151">系統**管理員** \>**Exchange**</span><span class="sxs-lookup"><span data-stu-id="8d34a-151">**Admin** \> **Exchange**</span></span> <br/> | <span data-ttu-id="8d34a-152">Exchange Online 設定</span><span class="sxs-lookup"><span data-stu-id="8d34a-152">Exchange Online settings</span></span>  <br/> |
|<span data-ttu-id="8d34a-153">系統**管理員** \>**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="8d34a-153">**Admin** \> **SharePoint**</span></span> <br/> | <span data-ttu-id="8d34a-154">SharePoint 線上設定</span><span class="sxs-lookup"><span data-stu-id="8d34a-154">SharePoint Online settings</span></span>  <br/> |
|<span data-ttu-id="8d34a-155">系統**管理員** \>**商務用 Skype**</span><span class="sxs-lookup"><span data-stu-id="8d34a-155">**Admin** \> **Skype for Business**</span></span> <br/> |<span data-ttu-id="8d34a-156">其他商務用 Skype 設定</span><span class="sxs-lookup"><span data-stu-id="8d34a-156">Additional Skype for Business settings</span></span>  <br/> |

<span data-ttu-id="8d34a-157">適用于 Microsoft 365 Small Business</span><span class="sxs-lookup"><span data-stu-id="8d34a-157">For Microsoft 365 Small Business</span></span>
  
|<span data-ttu-id="8d34a-158">**位置**</span><span class="sxs-lookup"><span data-stu-id="8d34a-158">**Location**</span></span>|<span data-ttu-id="8d34a-159">**用途**</span><span class="sxs-lookup"><span data-stu-id="8d34a-159">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8d34a-160">系統**管理員** \>**管理整個組織的設定**</span><span class="sxs-lookup"><span data-stu-id="8d34a-160">**Admin** \> **Manage organization-wide settings**</span></span> <br/> |<span data-ttu-id="8d34a-161">管理設定</span><span class="sxs-lookup"><span data-stu-id="8d34a-161">Administrative settings</span></span>  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a><span data-ttu-id="8d34a-162">在訂閱間傳輸公用網站</span><span class="sxs-lookup"><span data-stu-id="8d34a-162">Transfer a public website between subscriptions</span></span>

<span data-ttu-id="8d34a-163">如果您的公用網站主控于 Microsoft 365，您必須加以儲存，並在新的訂閱上重新建立。</span><span class="sxs-lookup"><span data-stu-id="8d34a-163">If you have a public website hosted on Microsoft 365, you need to save it and re-create it on your new subscription.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d34a-164">如果您的公用網站主控于 DNS 主機服務提供者，則不需要進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="8d34a-164">If your public website is hosted at a DNS hosting provider, no changes are required.</span></span> <span data-ttu-id="8d34a-165">您的轉換不會影響此方式。</span><span class="sxs-lookup"><span data-stu-id="8d34a-165">It will not be affected by your transition.</span></span>
  
<span data-ttu-id="8d34a-166">若要將文件庫或清單內容從 SharePoint 線上環境儲存至檔案共用或本機電腦，請參閱 [手動遷移 SharePoint 線上內容](https://go.microsoft.com/fwlink/p/?LinkId=402910)。</span><span class="sxs-lookup"><span data-stu-id="8d34a-166">To save a document library or list content from a SharePoint Online environment to file shares or to a local computer, see [Manual migration of SharePoint Online content](https://go.microsoft.com/fwlink/p/?LinkId=402910).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d34a-167">公用網站遷移應用程式無法將資料傳輸至不同的訂閱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-167">The Public site migration app can't transfer data to a different subscription.</span></span>
  
## <a name="transfer-team-site-structure-and-data"></a><span data-ttu-id="8d34a-168">傳輸小組網站結構和資料</span><span class="sxs-lookup"><span data-stu-id="8d34a-168">Transfer team site structure and data</span></span>

<span data-ttu-id="8d34a-169">有幾種方式可以儲存或轉接小組網站資料：</span><span class="sxs-lookup"><span data-stu-id="8d34a-169">There are several ways to save or transfer team site data:</span></span>
  
- <span data-ttu-id="8d34a-170">您可以將舊網站儲存為範本，然後將範本匯入新的網站。</span><span class="sxs-lookup"><span data-stu-id="8d34a-170">You can save the old site as a template and import the template into the new site.</span></span>

- <span data-ttu-id="8d34a-171">若要傳輸檔，請先在新網站上手動重新建立階層。</span><span class="sxs-lookup"><span data-stu-id="8d34a-171">To transfer documents, first manually recreate your hierarchy on the new site.</span></span> <span data-ttu-id="8d34a-172">然後，您可以同時開啟這兩個 SharePoint 小組網站、使用 Windows Explorer 開啟文件庫，以及複製及貼上檔。</span><span class="sxs-lookup"><span data-stu-id="8d34a-172">Then you can open both SharePoint team sites at the same time, open both document libraries with Windows Explorer, and copy and paste the documents.</span></span> <span data-ttu-id="8d34a-173">請參閱 [影片：使用 [以瀏覽器開啟] 複製或移動文件庫](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)檔案。</span><span class="sxs-lookup"><span data-stu-id="8d34a-173">See [Video: Copy or move library files by using Open with Explorer](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).</span></span>

- <span data-ttu-id="8d34a-174">若要傳輸清單資料、儲存 [清單範本](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)，然後使用儲存的範本在新網站上重新建立清單。</span><span class="sxs-lookup"><span data-stu-id="8d34a-174">To transfer list data, save a [list template](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393), and use the saved template to re-create the list on the new site.</span></span>

- <span data-ttu-id="8d34a-175">若要從 SharePoint 線上環境儲存文件庫或清單內容 (OneDrive 為商務或小組網站) 至檔案共用或本機電腦，請參閱 [SharePoint 線上內容之手動遷移的相關資訊](https://support.microsoft.com/kb/2783484)。</span><span class="sxs-lookup"><span data-stu-id="8d34a-175">To save a document library or list content from a SharePoint Online environment (OneDrive for Business or team sites) to file shares or to a local computer, see [Information about manual migration of SharePoint Online content](https://support.microsoft.com/kb/2783484).</span></span>

## <a name="transfer-users-data-between-subscriptions"></a><span data-ttu-id="8d34a-176">在訂閱間傳輸使用者資料</span><span class="sxs-lookup"><span data-stu-id="8d34a-176">Transfer users' data between subscriptions</span></span>

### <a name="email"></a><span data-ttu-id="8d34a-177">電子郵件：</span><span class="sxs-lookup"><span data-stu-id="8d34a-177">Email:</span></span>

<span data-ttu-id="8d34a-178">在您設定新訂閱後，請使用者 [移動電子郵件、連絡人、工作及行事曆資訊](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) 。</span><span class="sxs-lookup"><span data-stu-id="8d34a-178">Ask users to [move their email, contacts, tasks, and calendar information](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) after you set up your new subscription.</span></span> <span data-ttu-id="8d34a-179">他們可以使用初始的使用者名稱（例如 sue@contoso.onmicrosoft.com）來取得舊的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8d34a-179">They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.</span></span>
  
### <a name="onedrive-for-business-data"></a><span data-ttu-id="8d34a-180">商務資料的 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="8d34a-180">OneDrive For Business data:</span></span>

<span data-ttu-id="8d34a-181">要求使用者將 [商務內容的 OneDrive](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)複製/同步處理至其電腦，然後將其新增回其新訂閱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-181">Ask users to Copy/Sync [OneDrive for Business content to their computer](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd), and then add it back to their new subscription.</span></span>

### <a name="onenote"></a><span data-ttu-id="8d34a-182">OneNote</span><span class="sxs-lookup"><span data-stu-id="8d34a-182">OneNote</span></span> 

<span data-ttu-id="8d34a-183">要求使用者 [備份 OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) ，並將 [Notes 從備份還原](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) 至新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="8d34a-183">Ask users to [Back up OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) and to [Restore notes from a backup](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) to their new subscriptions.</span></span>
