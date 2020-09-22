---
title: 使用 ATP 安全連結設定自訂的 [不改寫 URLs] 清單
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何為 Office 365 ATP 安全連結原則中的使用者群組，為使用者設定自訂封鎖 URLs，並不重新寫入 URLs 清單。
ms.openlocfilehash: ff2ce18897d7bd1d3890335a237e32bffd1a77e6
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202348"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a><span data-ttu-id="23d1b-103">使用 ATP 安全連結設定自訂的 [不改寫 URLs] 清單</span><span class="sxs-lookup"><span data-stu-id="23d1b-103">Set up a custom do-not-rewrite URLs list using ATP Safe Links</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="23d1b-104">本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。</span><span class="sxs-lookup"><span data-stu-id="23d1b-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="23d1b-105">如果您是家用版使用者且正在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="23d1b-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="23d1b-106">有了 [Office 365 進階威脅防護](office-365-atp.md) (ATP)，貴組織可以擁有[自訂封鎖 URL](set-up-a-custom-blocked-urls-list-atp.md)，這樣一來，當使用者按一下電子郵件訊息中的網址 (URL) 或特定 Office 文件時，系統就不會阻止他們前往這些 URL。</span><span class="sxs-lookup"><span data-stu-id="23d1b-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="23d1b-107">貴組織還可以針對貴組織中的特定群組，擁有自訂「不要重寫」清單。</span><span class="sxs-lookup"><span data-stu-id="23d1b-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="23d1b-108">「不要重寫」清單可讓某些人員造訪 [Office 365 中的 ATP 安全連結](atp-safe-links.md)封鎖的 URL。</span><span class="sxs-lookup"><span data-stu-id="23d1b-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="23d1b-109">本文說明如何指定排除在 ATP 安全連結掃描以外的 URL 清單，以及要注意的一些重點。</span><span class="sxs-lookup"><span data-stu-id="23d1b-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

> [!NOTE]
> <span data-ttu-id="23d1b-110">如果您的組織使用安全連結原則，「不要重新寫入」清單是協力廠商網路釣魚測試唯一支援的方法。</span><span class="sxs-lookup"><span data-stu-id="23d1b-110">If your organization use Safe Links policies, the "do not rewrite" list is the only supported method for third party phishing tests.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="23d1b-111">設定「不要重寫」清單</span><span class="sxs-lookup"><span data-stu-id="23d1b-111">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="23d1b-112">ATP 安全連結保護使用數個清單，包括貴組織的封鎖 URL 清單和例外的「不要重寫」清單。</span><span class="sxs-lookup"><span data-stu-id="23d1b-112">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="23d1b-113">如果您具有必要權限，則可以設定您的自訂「不要重寫」清單。</span><span class="sxs-lookup"><span data-stu-id="23d1b-113">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="23d1b-114">當您新增或編輯適用於貴組織中特定收件者的安全連結原則時，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="23d1b-114">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span>

<span data-ttu-id="23d1b-115">若要編輯 (或定義) ATP 原則，您必須獲派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="23d1b-115">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="23d1b-116">下表包括一些範例。</span><span class="sxs-lookup"><span data-stu-id="23d1b-116">The following table includes some examples.</span></span> <span data-ttu-id="23d1b-117">若要深入瞭解，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="23d1b-117">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="23d1b-118">角色</span><span class="sxs-lookup"><span data-stu-id="23d1b-118">Role</span></span>|<span data-ttu-id="23d1b-119">指派位置/條件</span><span class="sxs-lookup"><span data-stu-id="23d1b-119">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="23d1b-120">全域管理員</span><span class="sxs-lookup"><span data-stu-id="23d1b-120">global administrator</span></span>|<span data-ttu-id="23d1b-121">簽署購買 Microsoft 365 的人員預設為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="23d1b-121">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="23d1b-122"> (請參閱 [關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 以深入瞭解。 ) </span><span class="sxs-lookup"><span data-stu-id="23d1b-122">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="23d1b-123">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="23d1b-123">Security Administrator</span></span>|<span data-ttu-id="23d1b-124">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="23d1b-124">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="23d1b-125">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="23d1b-125">Exchange Online Organization Management</span></span>|<span data-ttu-id="23d1b-126">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="23d1b-126">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="23d1b-127">或</span><span class="sxs-lookup"><span data-stu-id="23d1b-127">or</span></span> <br>  <span data-ttu-id="23d1b-128">PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="23d1b-128">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="23d1b-129">若要深入瞭解角色和許可權，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="23d1b-129">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="23d1b-130">若要檢視或編輯自訂「不要重寫」URL 清單</span><span class="sxs-lookup"><span data-stu-id="23d1b-130">To view or edit a custom "do not rewrite" URLs list</span></span>

1. <span data-ttu-id="23d1b-131">移至 [https://protection.office.com](https://protection.office.com) 然後以您的公司或學校帳戶當入。</span><span class="sxs-lookup"><span data-stu-id="23d1b-131">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="23d1b-132">在左側導覽中，選擇 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [安全連結]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="23d1b-132">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="23d1b-133">在 [適用於特定收件者的原則]\*\*\*\* 區段中，選擇 [新增]\*\*\*\* ([新增] 按鈕類似加號 (**+**) 以建立新原則。</span><span class="sxs-lookup"><span data-stu-id="23d1b-133">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="23d1b-134">(或者，您也可以編輯現有的原則。)</span><span class="sxs-lookup"><span data-stu-id="23d1b-134">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="23d1b-135">![選擇 [新增] 以新增特定電子郵件收件者的安全連結原則](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="23d1b-135">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>

4. <span data-ttu-id="23d1b-136">為您的原則指定名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="23d1b-136">Specify a name and description for your policy.</span></span>

5. <span data-ttu-id="23d1b-137">URLs **開啟當** 使用者按一下連結時，將會重新寫入並檢查已知惡意連結的清單。</span><span class="sxs-lookup"><span data-stu-id="23d1b-137">Turn **ON** URLs will be rewritten and checked against a list of known malicious links when user clicks on the link.</span></span>

6. <span data-ttu-id="23d1b-138">在 [ **不要重新寫入下列 URLs** ] 區段中，選取 [ **輸入有效的 url** ] 方塊，輸入 URL，然後選擇加號 (+) 。</span><span class="sxs-lookup"><span data-stu-id="23d1b-138">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, enter a URL, and then choose the plus sign (+).</span></span>

7. <span data-ttu-id="23d1b-139">在 [套用至]\*\*\*\* 區段中，選擇 [收件者是以下的成員]\*\*\*\*，然後選擇您想要包含在原則中的群組。</span><span class="sxs-lookup"><span data-stu-id="23d1b-139">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="23d1b-140">選擇 [新增]\*\*\*\*，然後選擇 [確認]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="23d1b-140">Choose **Add**, and then choose **OK**.</span></span>

8. <span data-ttu-id="23d1b-141">完成新增 URL 之後，在螢幕畫面右下角選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="23d1b-141">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="23d1b-142">請務必檢閱貴組織的自訂已封鎖 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="23d1b-142">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="23d1b-143">請參閱[使用 ATP 安全連結來設定自訂的封鎖 URL 清單](set-up-a-custom-blocked-urls-list-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="23d1b-143">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="23d1b-144">請注意重要要點</span><span class="sxs-lookup"><span data-stu-id="23d1b-144">Important points to keep in mind</span></span>

- <span data-ttu-id="23d1b-145">您在「不要重寫」清單中指定的任何 URL，都會針對您指定的收件者，從 ATP 安全連結掃描中排除。</span><span class="sxs-lookup"><span data-stu-id="23d1b-145">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>

- <span data-ttu-id="23d1b-146">考慮將常用的內部 URLs 新增至「不要重新寫入」清單，以提升使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="23d1b-146">Consider adding commonly used internal URLs to the "do not rewrite" list to improve the user experience.</span></span> <span data-ttu-id="23d1b-147">例如，如果您有內部部署服務（例如商務用 Skype 或 Sharepoint），您可以將其 URLs 新增到清單中，以將其排除在掃描之外。</span><span class="sxs-lookup"><span data-stu-id="23d1b-147">For example, if you have on-premises services, such as Skype for Business or Sharepoint, you can add their URLs to the list to exclude them from scanning.</span></span>

- <span data-ttu-id="23d1b-148">如果您在「不要重寫」清單中已經有 URL 清單，請務必檢閱該清單，並視需要新增萬用字元。</span><span class="sxs-lookup"><span data-stu-id="23d1b-148">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="23d1b-149">例如，如果您的現有清單包含像是 `https://contoso.com/a` 的項目，而您想要在原則中包含類似 `https://contoso.com/a/b` 的子路徑，請在您的項目中新增萬用字元，使它看起來像是 `https://contoso.com/a/*`。</span><span class="sxs-lookup"><span data-stu-id="23d1b-149">For example, if your existing list has an entry like `https://contoso.com/a` and you want to include subpaths like `https://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="23d1b-150">當您為 ATP 安全連結原則指定「不要重新寫入」清單時，最多可以有三個萬用字元 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="23d1b-150">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcards (\*).</span></span> <span data-ttu-id="23d1b-151">萬用字元會明確包含首碼或子域。</span><span class="sxs-lookup"><span data-stu-id="23d1b-151">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="23d1b-152">例如，該專案與 `contoso.com` 不同的專案不同 `*.contoso.com/*` ，因為 `*.contoso.com/*` 允許人員造訪指定網域中的子域和路徑。</span><span class="sxs-lookup"><span data-stu-id="23d1b-152">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

<span data-ttu-id="23d1b-153">下表列出您可以輸入的內容範例，以及這些項目的影響。</span><span class="sxs-lookup"><span data-stu-id="23d1b-153">The following table lists examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="23d1b-154">範例項目</span><span class="sxs-lookup"><span data-stu-id="23d1b-154">Example Entry</span></span>|<span data-ttu-id="23d1b-155">功能</span><span class="sxs-lookup"><span data-stu-id="23d1b-155">What It Does</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="23d1b-156">讓收件者可以造訪 `https://contoso.com`，而不是子網域或路徑。</span><span class="sxs-lookup"><span data-stu-id="23d1b-156">Allows recipients to visit a site like `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="23d1b-157">可讓收件者造訪網域、子域及路徑，例如、 `https://www.contoso.com` 、 `https://www.contoso.com` `https://maps.contoso.com` 或 `https://www.contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="23d1b-157">Allows recipients to visit a domain, subdomains, and paths, such as `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`.</span></span> <br/><br/> <span data-ttu-id="23d1b-158">此專案原本很好 `*contoso.com*` ，因為它不包含可能的詐騙網站，例如 `https://www.falsecontoso.com` 或 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="23d1b-158">This entry is inherently better than `*contoso.com*`, because it doesn't include potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="23d1b-159">讓收件者可以造訪像是 `https://contoso.com/a` 的網站，而不是像是 `https://contoso.com/a/b` 的子路徑。</span><span class="sxs-lookup"><span data-stu-id="23d1b-159">Allows specific recipients to visit a site like `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="23d1b-160">讓收件者可以造訪像是 `https://contoso.com/a` 的網站，以及像是 `https://contoso.com/a/b` 的子路徑。</span><span class="sxs-lookup"><span data-stu-id="23d1b-160">Allows specific recipients to visit a site like `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|
