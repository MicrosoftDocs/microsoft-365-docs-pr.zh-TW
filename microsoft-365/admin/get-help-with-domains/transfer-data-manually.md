---
title: 兩個 Office 365 帳戶之間手動傳送資料
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 尋找如何在兩個 Office 365 帳戶時變更計劃] 或 [公司名稱，或結合成一個多個訂閱之間手動傳送資料。
ms.openlocfilehash: 004dd586c207678157afdb418e54f3c3b5353304
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251649"
---
# <a name="transfer-data-manually-between-two-office-365-accounts"></a><span data-ttu-id="bd8cf-103">兩個 Office 365 帳戶之間手動傳送資料</span><span class="sxs-lookup"><span data-stu-id="bd8cf-103">Transfer data manually between two Office 365 accounts</span></span>

<span data-ttu-id="bd8cf-104">準備袖子及封鎖時間行事曆中的一串： 兩個 Office 365 帳戶之間傳輸資料是手動、 複雜，且耗時的程序。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-104">Prepare to roll up your sleeves and block out a chunk of time on your calendar: transferring data between two Office 365 accounts is a manual, complicated, and time-consuming process.</span></span> <span data-ttu-id="bd8cf-105">這不是自動化或支援處理程序。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-105">This is not an automated or supported process.</span></span> <span data-ttu-id="bd8cf-106">我們將協助您開始。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-106">We'll get you started.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="bd8cf-107">將會有停機時間期間，將不會在電子郵件、 商務用 Skype 和裝載於 Office 365 公用網站的程序。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-107">There will be down time during the process where email, Skype for Business and a public website hosted on Office 365 won't work.</span></span> <span data-ttu-id="bd8cf-108">使用者會收到新的使用者名稱和密碼，以及他們將需要設定 Outlook 重設。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-108">Users will get new user names and passwords, and they'll need to reset up Outlook.</span></span>

<span data-ttu-id="bd8cf-109">**僅限傳輸資料以手動方式使用下列其中一項適用於本主題中的指示：**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-109">**Only transfer data manually using the instructions in this topic if one of the following applies:**</span></span>
  
- <span data-ttu-id="bd8cf-110">您要變更為不同的服務系列中的計劃。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-110">You need to change to a plan in a different service family.</span></span>

- <span data-ttu-id="bd8cf-111">您的公司名稱變更，而您決定建立新的訂閱，然後移轉您的資料，因為您想要使用不同的初始網域名稱。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-111">Your company name changed, and you decided to create a new subscription and migrate your data because you want to use different initial domain names.</span></span>

- <span data-ttu-id="bd8cf-112">您必須合併到一個新的多個訂閱。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-112">You need to combine multiple subscriptions into one new one.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd8cf-113">如果您需要[變更您訂閱計劃](../../commerce/subscriptions/switch-to-a-different-plan.md)，並可以使用切換方案精靈，或如果您需要移轉至新訂閱計劃在相同的訂閱系列，即使切換方案精靈無法運作，您不需要以手動方式傳送您的資料，且沒有任何停機時間。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-113">If you need to [change your subscription plan](../../commerce/subscriptions/switch-to-a-different-plan.md) and can use the Switch plans wizard, or if you need to transfer to a new subscription plan in the same subscription family even when the Switch plans wizard doesn't work, you don't need to manually transfer your data, and there is no down time.</span></span>

|<span data-ttu-id="bd8cf-114">**Tasks**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-114">**Tasks**</span></span>|<span data-ttu-id="bd8cf-115">**Steps**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-115">**Steps**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bd8cf-116">購買您想要將移至的計劃。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-116">Purchase the plan you want to move to.</span></span>  <br/> |<span data-ttu-id="bd8cf-117">當您註冊時，您會指定要使用的初始網域名稱中的公司名稱： *yourcompany* 。 onmicrosoft.com、 *yourcompany* -public.sharepoint.com 和*yourcompany* 。 sharepoint.com。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-117">When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com.</span></span> <span data-ttu-id="bd8cf-118">您需要使用不同的*yourcompany*名稱比您沒有任何現有的訂閱。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-118">You need to use a different  *yourcompany*  name than you did for any existing subscriptions.</span></span>  <br/> <span data-ttu-id="bd8cf-119">> [!NOTE]它通常採用之後取消訂閱發行的初始網域名稱，使用*yourcompany*從我們系統的幾個月內至少要有 # C0。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-119">> [!NOTE]>  It typically takes a minimum of several months after cancelling a subscription to release the initial domain names that use  *yourcompany*  from our systems.</span></span> <span data-ttu-id="bd8cf-120">即使您計劃以儲存您的所有資料從您舊的 Office 365 訂閱，並取消該訂閱，舊的*yourcompany*值不是立即適用於新訂閱。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-120">Even if you plan to save all your data from your old Office 365 subscription, and cancel that subscription, the old  *yourcompany*  value is not immediately available for use in a new subscription.</span></span>           |
|<span data-ttu-id="bd8cf-121">從舊的 Office 365 訂閱中移除您的自訂網域。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-121">Remove your custom domain from your old Office 365 subscription.</span></span>  <br/> | <span data-ttu-id="bd8cf-122">請依照下列[所需的步驟，然後再移除網域](remove-a-domain.md)來移除使用者電子郵件地址的網域名稱，並移除電子郵件的 DNS 記錄和 Lync for 自訂的網域。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-122">Follow the [required steps before you remove a domain](remove-a-domain.md) to remove the domain name from user email addresses and remove DNS records for email and Lync for the custom domain.</span></span> <span data-ttu-id="bd8cf-123">如果您裝載於 Office 365 公用網站，您也需要移除指向它的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-123">If you host your public website on Office 365, you'll also need to remove the CNAME record that points to it.</span></span>  <br/> <span data-ttu-id="bd8cf-124">> [!IMPORTANT]> 之後移除路由電子郵件到這個自訂的網域、 電子郵件，將會停止工作，直到您新增網域至您的新帳戶，MX 記錄設定新的 MX 記錄，並設定您的使用者。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-124">> [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users.</span></span> <span data-ttu-id="bd8cf-125">當您移除的 DNS 記錄 lync 時，Lync 會停止運作。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-125">When you remove the DNS records for Lync, Lync will stop working.</span></span> <span data-ttu-id="bd8cf-126">與您移除的 CNAME 記錄，指向您的公用網站之後，它將無法使用。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-126">And after you remove the CNAME record that points to your public website, it will not be available.</span></span>           <span data-ttu-id="bd8cf-127">[移除網域](remove-a-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-127">[Remove the domain](remove-a-domain.md) .</span></span>  <br/> |
|<span data-ttu-id="bd8cf-128">設定自訂網域用於新訂閱，並設定您的使用者。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-128">Set up your custom domain for your new subscription, and set up your users.</span></span>  <br/> | <span data-ttu-id="bd8cf-129">設定新訂閱，包括建立必要的 DNS 記錄的自訂網域。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-129">Set up your new subscription, including creating the required DNS records for your custom domain.</span></span>  <br/>  <span data-ttu-id="bd8cf-130">建立您的使用者，您的自訂網域的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-130">Create your users, with email addresses on your custom domain.</span></span>  <br/> |
|<span data-ttu-id="bd8cf-131">將資料從您的舊訂閱傳輸至新訂閱。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-131">Transfer data from your old subscription to your new subscription.</span></span>  <br/> | <span data-ttu-id="bd8cf-132">登入這兩個不同的瀏覽器視窗中的帳戶：</span><span class="sxs-lookup"><span data-stu-id="bd8cf-132">Sign in to both accounts in separate browser windows:</span></span>  <br/>  <span data-ttu-id="bd8cf-133">以滑鼠右鍵按一下 [Internet Explorer] 圖示，並開啟兩個 InPrivate 瀏覽器視窗。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-133">Right-click the Internet Explorer icon, and open two InPrivate browser windows.</span></span> <span data-ttu-id="bd8cf-134">您可以使用兩個視窗中的不同的認證來登入這兩個帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-134">You can use different credentials in the two windows to sign in on both accounts.</span></span>  <br/> [<span data-ttu-id="bd8cf-135">訂閱之間傳送的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="bd8cf-135">Transfer administrative settings between subscriptions</span></span>](#email) <br/> [<span data-ttu-id="bd8cf-136">小組網站結構與資料傳輸</span><span class="sxs-lookup"><span data-stu-id="bd8cf-136">Transfer team site structure and data</span></span>](#transfer-team-site-structure-and-data) <br/> [<span data-ttu-id="bd8cf-137">訂閱之間傳送的公用網站</span><span class="sxs-lookup"><span data-stu-id="bd8cf-137">Transfer a public website between subscriptions</span></span>](#transfer-a-public-website-between-subscriptions) <br/> [<span data-ttu-id="bd8cf-138">訂閱之間傳送的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="bd8cf-138">Transfer administrative settings between subscriptions</span></span>](#email) <br/> |
|<span data-ttu-id="bd8cf-139">您必須取消訂閱大功告成與藉由呼叫 Microsoft 支援服務運作的 Office 365 計劃。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-139">Cancel the subscription for the plan you're done with by calling Microsoft Support for Office 365.</span></span>  <br/> | <span data-ttu-id="bd8cf-140">確認您的新訂閱正常運作，且已傳送的所有資料。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-140">Verify that your new subscription is working and all data has been transferred.</span></span>  <br/>  <span data-ttu-id="bd8cf-141">取消舊訂閱請[連絡客戶支援](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-141">[Contact customer support](../contact-support-for-business-products.md) to cancel your old subscription.</span></span>  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a><span data-ttu-id="bd8cf-142">訂閱之間傳送的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="bd8cf-142">Transfer administrative settings between subscriptions</span></span>

<span data-ttu-id="bd8cf-143">移至下列頁面上每個帳戶，and set up 舊的帳戶設定為基礎的新帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-143">Go to the following pages on each account, and set up the new account based on the old account's settings.</span></span>
  
<span data-ttu-id="bd8cf-144">如果您傳送的資料從 Office 365 Office 365 中型企業版或 Office 365 企業版，會以不同方式結構化的系統管理頁面。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-144">If you are transferring data from Office 365 to Office 365 Midsize Business or Office 365 Enterprise, the admin pages are structured differently.</span></span> <span data-ttu-id="bd8cf-145">監看[影片： 介紹 Office 365 企業版](https://support.office.com/article/11f7b4a0-1294-4e94-9238-beaae26efa9c.aspx)，並移至下列位置，查看 [系統設定。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-145">Watch a [Video: Introducing Office 365 Enterprise](https://support.office.com/article/11f7b4a0-1294-4e94-9238-beaae26efa9c.aspx), and go to the following places to look at admin settings.</span></span>
  
<span data-ttu-id="bd8cf-146">Office 365 企業版和 Office 365 中型企業版：</span><span class="sxs-lookup"><span data-stu-id="bd8cf-146">For Office 365 Enterprise and Office 365 Midsize Business:</span></span>
  
|<span data-ttu-id="bd8cf-147">**位置**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-147">**Location**</span></span>|<span data-ttu-id="bd8cf-148">**用途**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-148">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bd8cf-149">**系統管理員** \> **Office 365** \> **服務設定**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-149">**Admin** \> **Office 365** \> **Service settings**</span></span> <br/> |<span data-ttu-id="bd8cf-150">選取郵件、 網站、 Lync、 使用者軟體、 密碼、 社群、 版權管理和行動裝置設定每個索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-150">Select each tab for settings for mail, sites, Lync, user software, passwords, community, rights management, and mobile.</span></span>  <br/> |
|<span data-ttu-id="bd8cf-151">**系統管理員** \> **Exchange**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-151">**Admin** \> **Exchange**</span></span> <br/> | <span data-ttu-id="bd8cf-152">Exchange Online 設定</span><span class="sxs-lookup"><span data-stu-id="bd8cf-152">Exchange Online settings</span></span>  <br/> |
|<span data-ttu-id="bd8cf-153">**系統管理員** \> **SharePoint**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-153">**Admin** \> **SharePoint**</span></span> <br/> | <span data-ttu-id="bd8cf-154">SharePoint Online 設定</span><span class="sxs-lookup"><span data-stu-id="bd8cf-154">SharePoint Online settings</span></span>  <br/> |
|<span data-ttu-id="bd8cf-155">**系統管理員** \> **商務用 Skype**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-155">**Admin** \> **Skype for Business**</span></span> <br/> |<span data-ttu-id="bd8cf-156">業務設定其他商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="bd8cf-156">Additional Skype for Business settings</span></span>  <br/> |

<span data-ttu-id="bd8cf-157">適用於 Office 365 小型企業</span><span class="sxs-lookup"><span data-stu-id="bd8cf-157">For Office 365 Small Business</span></span>
  
|<span data-ttu-id="bd8cf-158">**位置**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-158">**Location**</span></span>|<span data-ttu-id="bd8cf-159">**用途**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-159">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bd8cf-160">**系統管理員** \> **管理整個組織的設定**</span><span class="sxs-lookup"><span data-stu-id="bd8cf-160">**Admin** \> **Manage organization-wide settings**</span></span> <br/> |<span data-ttu-id="bd8cf-161">系統管理設定</span><span class="sxs-lookup"><span data-stu-id="bd8cf-161">Administrative settings</span></span>  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a><span data-ttu-id="bd8cf-162">訂閱之間傳送的公用網站</span><span class="sxs-lookup"><span data-stu-id="bd8cf-162">Transfer a public website between subscriptions</span></span>

<span data-ttu-id="bd8cf-163">如果您有裝載於 Office 365 公用網站，您需要將它儲存及重新建立新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-163">If you have a public website hosted on Office 365, you need to save it and re-create it on your new subscription.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd8cf-164">如果您的公用網站架設在 DNS 主機服務提供者，不不需要任何變更。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-164">If your public website is hosted at a DNS hosting provider, no changes are required.</span></span> <span data-ttu-id="bd8cf-165">它將不會受到轉換。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-165">It will not be affected by your transition.</span></span>
  
<span data-ttu-id="bd8cf-166">若要從 SharePoint Online 環境儲存文件庫或清單內容的檔案共用或本機電腦，請參閱[手動移轉的 SharePoint Online 的內容](https://go.microsoft.com/fwlink/p/?LinkId=402910)。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-166">To save a document library or list content from a SharePoint Online environment to file shares or to a local computer, see [Manual migration of SharePoint Online content](https://go.microsoft.com/fwlink/p/?LinkId=402910).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd8cf-167">公用網站移轉應用程式不能將資料傳送至不同的訂閱。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-167">The Public site migration app can't transfer data to a different subscription.</span></span>
  
## <a name="transfer-team-site-structure-and-data"></a><span data-ttu-id="bd8cf-168">小組網站結構與資料傳輸</span><span class="sxs-lookup"><span data-stu-id="bd8cf-168">Transfer team site structure and data</span></span>

<span data-ttu-id="bd8cf-169">有幾種方式可以儲存資料或傳輸小組網站：</span><span class="sxs-lookup"><span data-stu-id="bd8cf-169">There are several ways to save or transfer team site data:</span></span>
  
- <span data-ttu-id="bd8cf-170">您可以儲存舊網站為範本，並將此範本匯入新的網站。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-170">You can save the old site as a template and import the template into the new site.</span></span>

- <span data-ttu-id="bd8cf-171">若要傳輸文件，先手動重新建立您階層，新的網站。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-171">To transfer documents, first manually recreate your hierarchy on the new site.</span></span> <span data-ttu-id="bd8cf-172">然後您可以同時開啟這兩個 SharePoint 小組網站、 使用 Windows 檔案總管] 中，開啟這兩個文件庫和複製並貼文件。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-172">Then you can open both SharePoint team sites at the same time, open both document libraries with Windows Explorer, and copy and paste the documents.</span></span> <span data-ttu-id="bd8cf-173">請參閱[影片： 複製或移動文件庫檔案使用檔案總管中開啟](https://support.office.com/article/c27bc6f3-7b38-4c29-b947-5d00c7153384.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-173">See [Video: Copy or move library files by using Open with Explorer](https://support.office.com/article/c27bc6f3-7b38-4c29-b947-5d00c7153384.aspx).</span></span>

- <span data-ttu-id="bd8cf-174">若要傳輸清單資料，將[清單範本](https://support.office.com/article/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393.aspx)，儲存並使用儲存的範本重新建立新的網站上的清單。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-174">To transfer list data, save a [list template](https://support.office.com/article/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393.aspx), and use the saved template to re-create the list on the new site.</span></span>

- <span data-ttu-id="bd8cf-175">若要儲存文件庫或清單內容從 SharePoint Online 環境 (商務用 OneDrive 或小組網站)，檔案共用或本機電腦，請參閱[手動移轉的 SharePoint Online 內容的相關資訊](https://support.microsoft.com/kb/2783484)。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-175">To save a document library or list content from a SharePoint Online environment (OneDrive for Business or team sites) to file shares or to a local computer, see [Information about manual migration of SharePoint Online content](https://support.microsoft.com/kb/2783484).</span></span>

## <a name="transfer-users-data-between-subscriptions"></a><span data-ttu-id="bd8cf-176">訂閱之間傳送使用者的資料</span><span class="sxs-lookup"><span data-stu-id="bd8cf-176">Transfer users' data between subscriptions</span></span>

### <a name="email"></a><span data-ttu-id="bd8cf-177">電子郵件：</span><span class="sxs-lookup"><span data-stu-id="bd8cf-177">Email:</span></span>

<span data-ttu-id="bd8cf-178">設定新訂閱之後，請要求使用者將[移動他們的電子郵件、 連絡人、 工作和行事曆資訊](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-178">Ask users to [move their email, contacts, tasks, and calendar information](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx) after you set up your new subscription.</span></span> <span data-ttu-id="bd8cf-179">他們可以使用其初始的使用者名稱，例如 sue@contoso.onmicrosoft.com 取得其舊的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-179">They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.</span></span>
  
### <a name="onedrive-for-business-data"></a><span data-ttu-id="bd8cf-180">商務用 OneDrive 的資料：</span><span class="sxs-lookup"><span data-stu-id="bd8cf-180">OneDrive For Business data:</span></span>

<span data-ttu-id="bd8cf-181">要求使用者在複製/同步處理[商務用 OneDrive 內容至其電腦](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)，並再將其新增至其新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="bd8cf-181">Ask users to Copy/Sync [OneDrive for Business content to their computer](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx), and then add it back to their new subscription.</span></span>