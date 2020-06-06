---
title: 使用 ATP 安全連結設定已封鎖的自訂 URLs 清單
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用 Office 365 進階威脅防護為貴組織設定封鎖的 URL 清單。
ms.openlocfilehash: 9bf4417044dab5488e2945ccea5fa30a7fd4113d
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588141"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="524d3-103">使用 ATP 安全連結設定已封鎖的自訂 URLs 清單</span><span class="sxs-lookup"><span data-stu-id="524d3-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="524d3-104">本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。</span><span class="sxs-lookup"><span data-stu-id="524d3-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="524d3-105">如果您是家用版使用者且正在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="524d3-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="524d3-106">使用 [Office 365 進階威脅防護 ](office-365-atp.md) (ATP)，貴組織即可擁有已封鎖的網站位址 (URL) 自訂清單。</span><span class="sxs-lookup"><span data-stu-id="524d3-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="524d3-107">當 URL 遭到封鎖時，按一下封鎖的 URL 連結人員會被帶到[警告頁面](atp-safe-links-warning-pages.md)，類似下列影像：</span><span class="sxs-lookup"><span data-stu-id="524d3-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span>

![網站已遭封鎖](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="524d3-109">[封鎖的 URLs] 清單是由您組織的 Microsoft 365 商務版安全小組所定義，而該清單適用于 Office 365 ATP 安全連結原則所涵蓋之組織中的所有人。</span><span class="sxs-lookup"><span data-stu-id="524d3-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span>

<span data-ttu-id="524d3-110">請參閱此文章以了解如何為 [Office 365 中的 ATP 安全連結](atp-safe-links.md)設定貴組織的自訂封鎖 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="524d3-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="524d3-111">檢視或編輯自訂封鎖 URL 清單</span><span class="sxs-lookup"><span data-stu-id="524d3-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="524d3-112">[Office 365 中的 ATP 安全連結](atp-safe-links.md)使用多種清單，包含貴組織的自訂封鎖 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="524d3-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="524d3-113">如果您具有必要權限，則可以設定貴組織的自訂清單。</span><span class="sxs-lookup"><span data-stu-id="524d3-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="524d3-114">您可以編輯貴組織的預設安全連結原則來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="524d3-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="524d3-115">若要編輯 (或定義) ATP 原則，您必須獲指派為以下表格所述之其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="524d3-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="524d3-116">角色</span><span class="sxs-lookup"><span data-stu-id="524d3-116">Role</span></span>|<span data-ttu-id="524d3-117">指派位置/條件</span><span class="sxs-lookup"><span data-stu-id="524d3-117">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="524d3-118">全域管理員</span><span class="sxs-lookup"><span data-stu-id="524d3-118">global administrator</span></span>|<span data-ttu-id="524d3-119">簽署購買 Microsoft 365 的人員預設為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="524d3-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="524d3-120">（請參閱[關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)以深入瞭解。）</span><span class="sxs-lookup"><span data-stu-id="524d3-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="524d3-121">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="524d3-121">Security Administrator</span></span>|<span data-ttu-id="524d3-122">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="524d3-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="524d3-123">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="524d3-123">Exchange Online Organization Management</span></span>|<span data-ttu-id="524d3-124">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="524d3-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="524d3-125">或</span><span class="sxs-lookup"><span data-stu-id="524d3-125">or</span></span> <br>  <span data-ttu-id="524d3-126">PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="524d3-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span>|

> [!TIP]
> <span data-ttu-id="524d3-127">若要深入瞭解角色和許可權，請參閱[安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="524d3-127">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="524d3-128">若要檢視或編輯自訂封鎖 URL 清單</span><span class="sxs-lookup"><span data-stu-id="524d3-128">To view or edit a custom blocked URLs list</span></span>

1. <span data-ttu-id="524d3-129">移至 [https://protection.office.com](https://protection.office.com) 然後以您的公司或學校帳戶當入。</span><span class="sxs-lookup"><span data-stu-id="524d3-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="524d3-130">在左側瀏覽中，選擇 [威脅管理] \*\*\*\* 下方的 [原則] \*\*\*\*\>[安全連結]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="524d3-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="524d3-131">在 **套用於整個組織的原則**區段中，選取 [預設] \*\*\*\*，然後選擇 [編輯] \*\*\*\* (編輯按鈕類似鉛筆)。</span><span class="sxs-lookup"><span data-stu-id="524d3-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="524d3-132">![按一下 [編輯] 已編輯安全連結防護預設原則](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="524d3-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="524d3-133">這樣做可讓您檢視封鎖的 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="524d3-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="524d3-134">一開始您可能沒有任何列出的 URL。</span><span class="sxs-lookup"><span data-stu-id="524d3-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="524d3-135">![預設安全連結原則中封鎖的 URL 清單](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="524d3-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>

4. <span data-ttu-id="524d3-136">選取 [輸入有效的 URL] 方塊\*\*\*\*，輸入 URL，然後選擇加號 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="524d3-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span>

5. <span data-ttu-id="524d3-137">完成新增 URL 之後，在螢幕畫面右下角選擇 [儲存] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="524d3-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="524d3-138">謹記幾件事項</span><span class="sxs-lookup"><span data-stu-id="524d3-138">A few things to keep in mind</span></span>

<span data-ttu-id="524d3-139">新增 URL 至清單時，請記住下列要點：</span><span class="sxs-lookup"><span data-stu-id="524d3-139">While you add URLs to your list, keep the following points in mind:</span></span>

- <span data-ttu-id="524d3-140">請勿在 URL 結尾包含斜線 (**/**)。</span><span class="sxs-lookup"><span data-stu-id="524d3-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="524d3-141">例如，輸入 `https://www.contoso.com`，而不是輸入 `https://www.contoso.com/`。</span><span class="sxs-lookup"><span data-stu-id="524d3-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>

- <span data-ttu-id="524d3-142">您可以指定的只有網域的 URL (像是 `contoso.com` 或 `tailspintoys.com`)。</span><span class="sxs-lookup"><span data-stu-id="524d3-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="524d3-143">這會封鎖任何含有網域的 URL 點擊。</span><span class="sxs-lookup"><span data-stu-id="524d3-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="524d3-144">您可以指定子網域 (像是 `toys.contoso.com*`) 而不封鎖完整網域 (像是 `contoso.com`)。</span><span class="sxs-lookup"><span data-stu-id="524d3-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="524d3-145">這將會封鎖含有子網域的任何 URL 點擊，但不會封鎖點擊含有完整網域的 URL。</span><span class="sxs-lookup"><span data-stu-id="524d3-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>

- <span data-ttu-id="524d3-146">每個 URL 最多可以包含三個萬用字元星號 (\*)。</span><span class="sxs-lookup"><span data-stu-id="524d3-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="524d3-147">下表列出您可以輸入的內容範例，以及這些項目的影響。</span><span class="sxs-lookup"><span data-stu-id="524d3-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>

|<span data-ttu-id="524d3-148">範例項目</span><span class="sxs-lookup"><span data-stu-id="524d3-148">Example Entry</span></span>|<span data-ttu-id="524d3-149">功能</span><span class="sxs-lookup"><span data-stu-id="524d3-149">What It Does</span></span>|
|:-----|:-----|
|<span data-ttu-id="524d3-150">`contoso.com` 或 `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="524d3-150">`contoso.com` or `*contoso.com*`</span></span>|<span data-ttu-id="524d3-151">封鎖網域、子網域和路徑，例如 `https://www.contoso.com`、`https://sub.contoso.com` 和 `https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="524d3-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="524d3-152">會封鎖網站 `https://contoso.com/a`，但不會封鎖其他子路徑，像是 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="524d3-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="524d3-153">會封鎖網站 `https://contoso.com/a`和其他子路徑，像是 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="524d3-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="524d3-154">封鎖子網域 (在這個例子中為「玩具」)，但允許按一下其他網域 URL (像是 `https://contoso.com` 或 `https://home.contoso.com`)。</span><span class="sxs-lookup"><span data-stu-id="524d3-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="524d3-155">如何定義組織中特定使用者的例外情況</span><span class="sxs-lookup"><span data-stu-id="524d3-155">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="524d3-156">如果您希望特定群組能夠檢視其他人可能封鎖的 URL，您可以指定可套用至特定收件者的 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="524d3-156">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="524d3-157">請參閱[使用 ATP 安全連結設定自訂「不可覆寫」URL 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) (英文)。</span><span class="sxs-lookup"><span data-stu-id="524d3-157">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
