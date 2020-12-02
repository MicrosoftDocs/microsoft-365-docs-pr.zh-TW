---
title: 新增 DNS 記錄以連接您的網域
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: 了解如何在 Microsoft 365 的任一 DNS 主機服務提供者上驗證您的網域並建立 DNS 記錄。
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: bc22dbd3a050516f518c9ddc9ccf5a3af9c76f12
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519290"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="2ba7c-103">新增 DNS 記錄以連接您的網域</span><span class="sxs-lookup"><span data-stu-id="2ba7c-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="2ba7c-104">如果您是透過協力廠商主機服務提供者購買網域，您可以更新註冊機構帳戶中的 DNS 記錄，將它連線到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="2ba7c-105">在這些步驟結束時，您的網域將會在您購買網域的主機中持續註冊，但 Microsoft 365 可以將它用於您的電子郵件地址 (例如 user@yourdomain.com) 和其他服務。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="2ba7c-106">如果您沒有新增網域，組織中的人員將會使用 onmicrosoft.com 網域做為其電子郵件地址，直到您新增網域為止。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="2ba7c-107">新增使用者之前，請務必先新增您的網域，這樣您就不需要再設定一次。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="2ba7c-108">若您在下方找不到所需內容，請[查看網域常見問題集](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-108">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="2ba7c-109">步驟 1: 新增 TXT 或 MX 記錄以驗證您擁有該網域</span><span class="sxs-lookup"><span data-stu-id="2ba7c-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="2ba7c-110">建議：使用 TXT 記錄進行驗證</span><span class="sxs-lookup"><span data-stu-id="2ba7c-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="2ba7c-111">首先，您必須證明您擁有要新增至 Microsoft 365 的網域。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="2ba7c-112">登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，然後選取 **[顯示所有]** > **[設定]** > **[網域]**。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="2ba7c-113">在新的瀏覽器索引標籤或視窗中，登入您的 DNS 主機服務提供者，然後尋找您管理 DNS 設定的位置（例如 [區域檔案設定]、[管理網域]、[網域管理員]、[DNS 管理員]）。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="2ba7c-114">移至您提供者的 [DNS 管理員] 頁面，並將系統管理中心所指出的 TXT 記錄新增到您的網域。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="2ba7c-115">新增此記錄不會影響您現有的電子郵件或其他服務，您只要將網域連線至 Microsoft 365，就能安全地將它移除。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="2ba7c-116">範例：</span><span class="sxs-lookup"><span data-stu-id="2ba7c-116">Example:</span></span>
- <span data-ttu-id="2ba7c-117">TXT 名稱: `@`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-117">TXT Name: `@`</span></span>
- <span data-ttu-id="2ba7c-118">TXT 值： MS = ms # # # # # # # # （[系統管理中心] 的唯一識別碼）</span><span class="sxs-lookup"><span data-stu-id="2ba7c-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="2ba7c-119">TTL： `3600‎` （或您的提供者預設值）</span><span class="sxs-lookup"><span data-stu-id="2ba7c-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="2ba7c-120">儲存記錄、返回系統管理中心，然後選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="2ba7c-121">註冊記錄變更通常需要15分鐘的時間，但是有時候會需要更長的時間。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="2ba7c-122">請稍候一段時間，並嘗試挑選變更。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="2ba7c-123">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="2ba7c-124">使用 MX 記錄進行驗證</span><span class="sxs-lookup"><span data-stu-id="2ba7c-124">Verify with an MX record</span></span>

<span data-ttu-id="2ba7c-125">如果您的註冊機構不支援新增 TXT 記錄，您可以新增 MX 記錄以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="2ba7c-126">登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，然後選取 **[顯示所有]** > **[設定]** > **[網域]**。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="2ba7c-127">在新的瀏覽器索引標籤或視窗中，登入您的 DNS 主機服務提供者，然後尋找您管理 DNS 設定的位置（例如 [區域檔案設定]、[管理網域]、[網域管理員]、[DNS 管理員]）。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="2ba7c-128">移至您提供者的 [DNS 管理員] 頁面，並將系統管理中心所指出的 MX 記錄新增到您的網域。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="2ba7c-129">此 MX 記錄的「優先順序」必須是網域所有現有 MX 記錄的最高者。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="2ba7c-130">否則，可能會干擾傳送和接收電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="2ba7c-131">當網域驗證完成後，您應該立即刪除這項記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="2ba7c-132">請確認欄位已設定為下列的值：</span><span class="sxs-lookup"><span data-stu-id="2ba7c-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="2ba7c-133">記錄類型: `MX`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-133">Record Type: `MX`</span></span>
- <span data-ttu-id="2ba7c-134">優先順序: 設定為可用的最高值，通常為 `0`。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="2ba7c-135">主機名稱: `@`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-135">Host Name: `@`</span></span>
- <span data-ttu-id="2ba7c-136">指向 [位址]: 從系統管理中心複製值並貼上。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2ba7c-137">TTL：`3600‎` (或您的提供者預設值)</span><span class="sxs-lookup"><span data-stu-id="2ba7c-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2ba7c-138">在 Microsoft 找到正確的 MX 記錄後，您的網域即完成驗證。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="2ba7c-139">步驟2：新增 DNS 記錄以連結 Microsoft 服務</span><span class="sxs-lookup"><span data-stu-id="2ba7c-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="2ba7c-140">在新的瀏覽器索引標籤或視窗中，登入您的 DNS 主機服務提供者，然後尋找您管理 DNS 設定的位置（例如 [區域檔案設定]、[管理網域]、[網域管理員]、[DNS 管理員]）。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="2ba7c-141">視您要啟用的服務而定，您將新增多種不同類型的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="2ba7c-142">新增電子郵件的 MX 記錄（Outlook、Exchange Online）</span><span class="sxs-lookup"><span data-stu-id="2ba7c-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="2ba7c-143">**開始之前：** 如果使用者已經擁有您網域的電子郵件（例如 user@yourdomain.com），請在設定 MX 記錄前，先在系統管理中心建立其帳戶。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="2ba7c-144">這樣一來，他們就能繼續收到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="2ba7c-145">當您更新網域的 MX 記錄時，使用您網域所有人的所有新電子郵件現在都會傳送至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="2ba7c-146">您已收到的任何電子郵件將會保留在目前的電子郵件主機中，除非您決定[將電子郵件和連絡人移轉至 Microsoft 365](../setup/migrate-email-and-contacts-admin.md)。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="2ba7c-147">您將會從系統管理中心網域設定向導取得 MX 記錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="2ba7c-148">在您的主機提供者的網站上，新增 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="2ba7c-149">請確認欄位已設定為下列的值：</span><span class="sxs-lookup"><span data-stu-id="2ba7c-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="2ba7c-150">記錄類型: `MX`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-150">Record Type: `MX`</span></span>
- <span data-ttu-id="2ba7c-151">優先順序: 設定為可用的最高值，通常為 `0`。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="2ba7c-152">主機名稱: `@`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-152">Host Name: `@`</span></span>
- <span data-ttu-id="2ba7c-153">指向 [位址]: 從系統管理中心複製值並貼上。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2ba7c-154">TTL： `3600‎` （或您的提供者預設值）</span><span class="sxs-lookup"><span data-stu-id="2ba7c-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2ba7c-155">儲存記錄，然後移除任何其他的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="2ba7c-156">新增 CNAME 記錄以連接其他服務 (Teams、Exchange Online、AAD、MDM)</span><span class="sxs-lookup"><span data-stu-id="2ba7c-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="2ba7c-157">您將會從系統管理中心網域設定向導取得 CNAME 記錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="2ba7c-158">在您的宿主提供者的網站上，為您要連線的每個服務新增 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="2ba7c-159">請確認每個欄位皆已設定為下列的值：</span><span class="sxs-lookup"><span data-stu-id="2ba7c-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="2ba7c-160">記錄類型: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="2ba7c-161">主機: 從系統管理中心貼上您複製的值。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="2ba7c-162">指向 [位址]: 從系統管理中心複製值並貼上。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2ba7c-163">TTL： `3600‎` （或您的提供者預設值）</span><span class="sxs-lookup"><span data-stu-id="2ba7c-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="2ba7c-164">新增或編輯 SPF TXT 記錄以協助防範垃圾郵件 (Outlook、Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="2ba7c-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="2ba7c-165">**在您開始之前:** 如果網域已經有 SPF 記錄，請勿為 Microsoft 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="2ba7c-166">請改為將所需的 Microsoft 365 值新增到您主機服務提供者網站的目前記錄中，這樣您就有了一份包含兩組值的 *單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="2ba7c-167">在您的主機提供者網站上，編輯現有 SPF 記錄或建立 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="2ba7c-168">請確認欄位已設定為下列的值：</span><span class="sxs-lookup"><span data-stu-id="2ba7c-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="2ba7c-169">記錄類型: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="2ba7c-170">主機: `@`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-170">Host: `@`</span></span>
- <span data-ttu-id="2ba7c-171">TXT 值: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="2ba7c-172">TTL： `3600‎` （或您的提供者預設值）</span><span class="sxs-lookup"><span data-stu-id="2ba7c-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2ba7c-173">儲存記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-173">Save the record.</span></span>

<span data-ttu-id="2ba7c-174">透過其中一個 [SPF 驗證工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 以驗證您的 SPF 記錄</span><span class="sxs-lookup"><span data-stu-id="2ba7c-174">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="2ba7c-175">SPF 是設計來協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="2ba7c-176">為了防範這些技術，設定 SPF 之後，您也應該為 Microsoft 365 設定 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="2ba7c-177">若要開始使用，請參閱[在 Microsoft 365 中使用 DKIM 驗證從您的網域傳送的外寄電子郵件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) 和 [使用 DMARC 在 Microsoft 365 中驗證電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="2ba7c-178">新增通訊服務的 SRV 記錄 ( Teams、商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="2ba7c-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="2ba7c-179">在您的主機提供者的網站上，為您要連線的每個服務新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="2ba7c-180">請確認每個欄位皆已設定為下列的值：</span><span class="sxs-lookup"><span data-stu-id="2ba7c-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="2ba7c-181">記錄類型: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="2ba7c-182">名稱: `@`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-182">Name: `@`</span></span>
- <span data-ttu-id="2ba7c-183">目標: 從系統管理中心複製值並貼上。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2ba7c-184">通訊協定: 從系統管理中心複製值並貼上。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2ba7c-185">服務: 從系統管理中心複製值並貼上。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2ba7c-186">優先順序: `100`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-186">Priority: `100`</span></span>
- <span data-ttu-id="2ba7c-187">加權: `1`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-187">Weight: `1`</span></span>
- <span data-ttu-id="2ba7c-188">埠：從系統管理中心複製值並貼上。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2ba7c-189">TTL： `3600‎` （或您的提供者預設值）</span><span class="sxs-lookup"><span data-stu-id="2ba7c-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2ba7c-190">儲存記錄。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="2ba7c-191">SRV 記錄欄位限制和因應措施</span><span class="sxs-lookup"><span data-stu-id="2ba7c-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="2ba7c-192">某些主機提供者會限制 SRV 記錄中的欄位值。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="2ba7c-193">以下是這些限制的一些常見因應措施。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="2ba7c-194">姓名</span><span class="sxs-lookup"><span data-stu-id="2ba7c-194">Name</span></span>
<span data-ttu-id="2ba7c-195">如果您的主機服務提供者不允許將此欄位設定為 **@**，請將它保留為空白。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="2ba7c-196">*只有* 當您的 DNS 主機服務者在服務和通訊協定值有不同的欄位時，才能使用此方法。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="2ba7c-197">否則，請參閱下列服務和通訊協定附註。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="2ba7c-198">服務和通訊協定</span><span class="sxs-lookup"><span data-stu-id="2ba7c-198">Service and Protocol</span></span>
<span data-ttu-id="2ba7c-199">如果您的主機提供者不提供這些用於 SRV 記錄的欄位，您必須在記錄的 **[名稱]** 欄位中指定 **[服務]** 和 **[通訊協定]** 值。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="2ba7c-200">(附註：視您的主機提供者而定，**[名稱]** 欄位可能會是其他名稱，例如：**[主機]**、**[主機名稱]** 或 **[子網域]**) 若要新增這些值，您需建立一個字串，並用點分隔值。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="2ba7c-201">範例：`_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="2ba7c-202">優先順序、加權和連接埠</span><span class="sxs-lookup"><span data-stu-id="2ba7c-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="2ba7c-203">如果您的主機服務提供者未提供這些 SRV 記錄欄位，您必須在記錄的 **[目標]** 欄位中指定它們。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="2ba7c-204">(注意: 視您的主機提供者而定，**[目標]** 欄位可能名為其他內容，例如: **[內容]**、**[IP 位址]**，或 **[目標主機]**。)</span><span class="sxs-lookup"><span data-stu-id="2ba7c-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="2ba7c-205">若要新增這些值，請建立一個字串，並以空格分隔值，*有時候會以點* 結尾 (如果您不確定，請向您的提供者詢問)。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="2ba7c-206">這些值必須按照以下列順序：Priority、Weight、Port、Target。</span><span class="sxs-lookup"><span data-stu-id="2ba7c-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="2ba7c-207">範例1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="2ba7c-208">範例2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="2ba7c-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>
