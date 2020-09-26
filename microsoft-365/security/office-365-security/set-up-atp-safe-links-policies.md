---
title: 設定 Office 365 ATP 安全連結原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 設定安全連結原則來保護貴組織，以防範 Word、Excel、PowerPoint 和 Visio 檔案，以及電子郵件中的惡意連結。
ms.openlocfilehash: 76d0aba026b96251a64163ef7d7f518fe0b1e1b1
ms.sourcegitcommit: e9f32675061cd1cf4a3e2dada393e10d7c552efe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "48279581"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="aeaa8-103">設定 Office 365 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="aeaa8-103">Set up Office 365 ATP Safe Links policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="aeaa8-104">本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="aeaa8-105">如果您是家用版使用者且正在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="aeaa8-106">[Atp 安全連結](atp-safe-links.md) 是 [Office 365 的「高級威脅](office-365-atp.md))  (防護」中的一項功能，可協助您保護組織免受網路釣魚和其他攻擊中所使用的惡意連結。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-106">[ATP Safe Links](atp-safe-links.md) is a feature in [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) that can help protect your organization from malicious links used in phishing and other attacks.</span></span> <span data-ttu-id="aeaa8-107">如果您擁有 [安全性 & 合規性中心](permissions-in-the-security-and-compliance-center.md)的必要許可權，您可以設定 ATP 安全連結原則，以協助確保當使用者按一下網址 (URLs) 時，您的組織受到保護。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-107">If you have the necessary [permissions for the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected.</span></span> <span data-ttu-id="aeaa8-108">您可以將 ATP 安全連結原則設定為掃描電子郵件中的 URL 和 Office 文件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-108">Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span> <span data-ttu-id="aeaa8-109">ATP 安全連結會掃描內送的電子郵件中是否有已知的惡意超連結和包含惡意程式碼的附件。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-109">ATP Safe Links scans incoming email for known malicious hyperlinks and for attachments containing malware.</span></span> <span data-ttu-id="aeaa8-110">此功能會將掃描的 URLs 寫入 Microsoft 的標準 URL 格式首碼 <https://nam01.safelinks.protection.outlook.com> 。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-110">This feature rewrites scanned URLs to Microsoft’s standard URL format prefix <https://nam01.safelinks.protection.outlook.com>.</span></span> <span data-ttu-id="aeaa8-111">在重新寫入連結後，會針對任何可能的惡意內容進行分析。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-111">Once a link is rewritten, it is analyzed for any potential malicious content.</span></span> <span data-ttu-id="aeaa8-112">啟用 ATP 安全連結後，如果使用者按一下電子郵件中的連結，且該 URL 已被組織的自訂封鎖 URL 清單封鎖，或是該 URL 已確定為惡意的，就會開啟警告頁面。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-112">With ATP Safe Links enabled, if a user clicks on a link in an email and the URL has been blocked by your organization's custom blocked URL list or if the URL is determined to be malicious, a warning page will open.</span></span>

<span data-ttu-id="aeaa8-113">當 ATP 安全連結重新寫入 URL 後，如果郵件是轉寄或回復的，該 URL 就會繼續重新寫入。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-113">Once ATP Safe Links has rewritten a URL, if the message is forwarded or replied to, the URL will remain rewritten.</span></span> <span data-ttu-id="aeaa8-114">新增至正在回復或轉寄之郵件的其他連結將不會被重新寫入。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-114">Additional links added to the message being replied to or forwarded will not be rewritten.</span></span>

<span data-ttu-id="aeaa8-115">[我們會持續將新功能新增至 ATP](office-365-atp.md#new-features-in-office-365-atp)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-115">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="aeaa8-116">新增新功能後，您可能需要調整現有的 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-116">As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="aeaa8-117">處理方式</span><span class="sxs-lookup"><span data-stu-id="aeaa8-117">What to do</span></span>

1. <span data-ttu-id="aeaa8-118">檢閱必要條件。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-118">Review the prerequisites.</span></span>

2. <span data-ttu-id="aeaa8-119">檢閱和編輯每個人都適用的預設 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-119">Review and edit the default ATP Safe Links policy that applies to everyone.</span></span> <span data-ttu-id="aeaa8-120">例如，您可以[設定 ATP 安全連結的自訂封鎖 URL 清單](set-up-a-custom-blocked-urls-list-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-120">For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

3. <span data-ttu-id="aeaa8-121">新增或編輯特定電子郵件收件者的原則，包括[針對 ATP 安全連結設定自訂「不要重寫」URL 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-121">Add or edit policies for specific email recipients, including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>

4. <span data-ttu-id="aeaa8-122">了解 ATP 安全連結原則選項 (在本文中)，包括最近變更的設定。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-122">Learn about ATP Safe Links policy options (in this article), including settings for recent changes.</span></span>

## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="aeaa8-123">步驟 1：檢閱必要條件</span><span class="sxs-lookup"><span data-stu-id="aeaa8-123">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="aeaa8-124">請確認您組織有 [Office 365 進階威脅防護](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-124">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>

- <span data-ttu-id="aeaa8-125">請確定您具有必要權限。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-125">Make sure that you have the necessary permissions.</span></span> <span data-ttu-id="aeaa8-126">若要定義 (或編輯) ATP 原則，您必須獲派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-126">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="aeaa8-127">下表中有一些範例描述：</span><span class="sxs-lookup"><span data-stu-id="aeaa8-127">Some examples are described in the following table:</span></span>

    |<span data-ttu-id="aeaa8-128">角色</span><span class="sxs-lookup"><span data-stu-id="aeaa8-128">Role</span></span>|<span data-ttu-id="aeaa8-129">指派位置/條件</span><span class="sxs-lookup"><span data-stu-id="aeaa8-129">Where/how assigned</span></span>|
    |---|---|
    |<span data-ttu-id="aeaa8-130">全域管理員</span><span class="sxs-lookup"><span data-stu-id="aeaa8-130">global administrator</span></span>|<span data-ttu-id="aeaa8-131">簽署購買 Microsoft 365 的人員預設為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-131">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="aeaa8-132"> (請參閱 [關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 以深入瞭解。 ) </span><span class="sxs-lookup"><span data-stu-id="aeaa8-132">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
    |<span data-ttu-id="aeaa8-133">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="aeaa8-133">Security Administrator</span></span>|<span data-ttu-id="aeaa8-134">Azure Active Directory 系統管理中心 (<https://aad.portal.azure.com>)</span><span class="sxs-lookup"><span data-stu-id="aeaa8-134">Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>|
    |<span data-ttu-id="aeaa8-135">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="aeaa8-135">Exchange Online Organization Management</span></span>|<span data-ttu-id="aeaa8-136">Exchange 系統管理中心 (<https://outlook.office365.com/ecp>)</span><span class="sxs-lookup"><span data-stu-id="aeaa8-136">Exchange admin center (<https://outlook.office365.com/ecp>)</span></span> <br><span data-ttu-id="aeaa8-137">或</span><span class="sxs-lookup"><span data-stu-id="aeaa8-137">or</span></span> <br>  <span data-ttu-id="aeaa8-138">PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="aeaa8-138">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|

    <span data-ttu-id="aeaa8-139">若要深入瞭解角色和許可權，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-139">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="aeaa8-140">確定 Office 用戶端已設定為使用[新式驗證](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016) (這會用於 Office 文件中的 ATP 安全連結保護)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-140">Make sure that Office clients are configured to use [Modern Authentication](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016) (this is for ATP Safe Links protection in Office documents).</span></span>

- <span data-ttu-id="aeaa8-141">[了解 ATP 安全連結原則選項](#step-4-learn-about-atp-safe-links-policy-options) (在本文中)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-141">[Learn about ATP Safe Links policy options](#step-4-learn-about-atp-safe-links-policy-options) (in this article).</span></span>

- <span data-ttu-id="aeaa8-142">最多可允許30分鐘，以將新的或更新的原則散佈至所有 Microsoft 365 資料中心。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-142">Allow up to 30 minutes for your new or updated policy to spread to all Microsoft 365 datacenters.</span></span>

## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="aeaa8-143">步驟2：定義 (或檢閱) 每個人都適用的 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="aeaa8-143">Step 2: Define (or review) the ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="aeaa8-144">當您擁有 [Office 365 進階威脅防護](office-365-atp.md)時，您會有貴組織中每個人都適用的預設 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-144">When you have [Office 365 Advanced Threat Protection](office-365-atp.md), you will have a default ATP Safe Links policy that applies to everyone in your organization.</span></span> <span data-ttu-id="aeaa8-145">請務必檢閱，並視需要編輯預設原則。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-145">Make sure to review, and if needed, edit your default policy.</span></span>

1. <span data-ttu-id="aeaa8-146">移至 <https://protection.office.com> 然後以您的公司或學校帳戶當入。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-146">Go to <https://protection.office.com> and sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeaa8-147">在左側導覽中，選擇 [威脅管理]\*\*\*\* 下方的 [原則]\*\* \> [安全連結]\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-147">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>

3. <span data-ttu-id="aeaa8-148">在 **套用於整個組織的原則**區段中，選取 [預設] \*\*\*\*，然後選擇 [編輯] \*\*\*\* (編輯按鈕類似鉛筆)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-148">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span>

   ![按一下 [編輯] 已編輯安全連結防護預設原則](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)

4. <span data-ttu-id="aeaa8-150">在 [封鎖下列 URL]\*\*\*\* 區段中，指定您想要防止貴組織中的人員造訪的一或多個 URL。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-150">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting.</span></span> <span data-ttu-id="aeaa8-151">(請參閱[使用 ATP 安全連結來設定自訂的封鎖 URL 清單](set-up-a-custom-blocked-urls-list-atp.md)。)</span><span class="sxs-lookup"><span data-stu-id="aeaa8-151">(See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).)</span></span>

5. <span data-ttu-id="aeaa8-152">在 [套用到電子郵件以外內容的設定]\*\*\*\* 區段中，選取 (或清除) 您要使用的選項。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-152">In the **Settings that apply to content except email** section, select (or clear) the options you want to use.</span></span> <span data-ttu-id="aeaa8-153">(建議您選取所有選項。)</span><span class="sxs-lookup"><span data-stu-id="aeaa8-153">(We recommend that you select all the options.)</span></span>

6. <span data-ttu-id="aeaa8-154">選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-154">Choose **Save**.</span></span>
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients"></a><span data-ttu-id="aeaa8-155">步驟3：新增 (或編輯適用于所有或特定電子郵件收件者的) ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="aeaa8-155">Step 3: Add (or edit) ATP Safe Links policies that apply to all or specific email recipients</span></span>

<span data-ttu-id="aeaa8-156">在您已複查 (或編輯) 適用于每個人的預設 ATP 安全連結原則之後，下一步是定義適用于所有或特定電子郵件收件者的其他原則。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-156">After you have reviewed (or edited) the default ATP Safe Links policy that applies to everyone, your next step is to define additional policies that would apply to all or specific email recipients.</span></span> <span data-ttu-id="aeaa8-157">例如，您可以定義其他原則，或為所有員工建立更多細微限制，以指定預設原則的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-157">For example, you can specify exceptions to your default policy by defining an additional policy or create more granular restrictions for all employees.</span></span>
  
1. <span data-ttu-id="aeaa8-158">移至 <https://protection.office.com> 然後以您的公司或學校帳戶當入。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-158">Go to <https://protection.office.com> and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="aeaa8-159">在左側導覽中，選擇 [威脅管理]\*\*\*\* 下方的 [原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-159">In the left navigation, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="aeaa8-160">選擇 [安全連結]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-160">Choose **Safe Links**.</span></span>

4. <span data-ttu-id="aeaa8-161">在 [適用於特定收件者的原則]\*\*\*\* 區段中，選擇 [新增]\*\*\*\* ([新增] 按鈕類似加號 (**+**))。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-161">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span>

   ![選擇 [新增] 以新增特定電子郵件收件者的安全連結原則](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

5. <span data-ttu-id="aeaa8-163">指定原則的名稱、描述及設定。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-163">Specify the name, description, and settings for your policy.</span></span>

   <span data-ttu-id="aeaa8-164">**範例：** 若要設定名為「禁止直接點選」的原則，該原則不允許貴組織中特定群組的人員在沒有 ATP 安全連結保護的情況下點選特定網站，您可以指定下列建議設定：</span><span class="sxs-lookup"><span data-stu-id="aeaa8-164">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span>

   - <span data-ttu-id="aeaa8-165">在 [名稱]\*\*\*\* 方塊中，鍵入「禁止直接點選」。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-165">In the **Name** box, type no direct click through.</span></span>

   - <span data-ttu-id="aeaa8-166">在 [描述]\*\*\*\* 方塊中，鍵入類似以下的描述：禁止特定群組中的人員在未經 ATP 安全連結驗證的情況下點選網站。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-166">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>

   - <span data-ttu-id="aeaa8-167">在 [選取動作]\*\*\*\* 區段中，選擇 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-167">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="aeaa8-168">如果您想要為可疑和指向檔案的 URL 啟用 URL 引爆功能 (建議使用)，請選取 [針對可疑的連結和指向檔案的連結套用即時 URL 掃描]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-168">Select **Apply real-time URL scanning for suspicious links and links that point to files** if you would like to enable URL detonation for suspicious and file-pointing URLs (recommended).</span></span> <span data-ttu-id="aeaa8-169">如果您希望只有在完全掃描 URL 之後才讓使用者接收郵件，則選取 [等到 URL 掃描完成再傳遞郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-169">And select **Wait for URL scanning to complete before delivering the message** if you wish to only have users receive messages after the URLs have been fully scanned.</span></span>

   - <span data-ttu-id="aeaa8-170">如果您想要針對在組織內使用者間傳送的郵件啟用安全連結 (建議使用)，請選取 [將安全連結套用至組織內傳送的郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-170">Select **Apply Safe Links to messages sent within the organization** if you would like to enable Safe Links for messages sent between users within your organization (recommended).</span></span>

   - <span data-ttu-id="aeaa8-171">如果您不希望個別使用者覆寫「進行中的掃描」\*\* 或「已封鎖 URL」\*\* 通知頁面，請選取 [不允許使用者點選原始 URL]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-171">Select **Do not allow user to click through to original URL** if you do not wish the individual users to override a *scan in progress* or *URL blocked* notification pages.</span></span>

   - <span data-ttu-id="aeaa8-172">(選用) 在 [不要重寫下列 URL]\*\*\*\* 區段中，指定一或多個被認為對貴組織很安全的 URL。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-172">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization.</span></span> <span data-ttu-id="aeaa8-173">(請參閱[使用 ATP 安全連結來設定自訂「不要重寫」URL 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span><span class="sxs-lookup"><span data-stu-id="aeaa8-173">(See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>

   - <span data-ttu-id="aeaa8-174">在 [套用至]\*\*\*\* 區段中，選擇 [收件者是以下的成員]\*\*\*\*，然後選擇您想要包含在原則中的群組。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-174">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="aeaa8-175">選擇 [新增]\*\*\*\*，然後選擇 [確認]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-175">Choose **Add**, and then choose **OK**.</span></span>

6. <span data-ttu-id="aeaa8-176">選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-176">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="aeaa8-177">具有較高優先順序的 ATP 安全連結原則將優先執行。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-177">ATP Safe Links policies with higher priority will take precedence.</span></span> <span data-ttu-id="aeaa8-178">如果使用者受制于兩個或多個原則，則只有較高優先順序的原則才能生效。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-178">If a user is subject to two or more policies, only the higher priority policy will take effect.</span></span> <span data-ttu-id="aeaa8-179">若要讓客戶原則優先順序，您必須提高原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-179">If you want the customer policy to take precedence, you need to raise the priority of the policy.</span></span>

## <a name="step-4-learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="aeaa8-180">步驟 4：了解 ATP 安全連結原則選項</span><span class="sxs-lookup"><span data-stu-id="aeaa8-180">Step 4: Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="aeaa8-181">當您設定或編輯 ATP 安全連結原則時，會看到幾個可用的選項。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-181">As you set up or edit your ATP Safe Links policies, will see several options available.</span></span> <span data-ttu-id="aeaa8-182">如果您想知道這些選項的功能，下表會說明有每個選項及其效用。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-182">In case you are wondering what these options are, the following table describes each one and its effect.</span></span> <span data-ttu-id="aeaa8-183">請記住，要定義或編輯的主要 ATP 安全連結原則有兩種：</span><span class="sxs-lookup"><span data-stu-id="aeaa8-183">Remember that there are two main kinds of ATP Safe Links policies to define or edit:</span></span>

- <span data-ttu-id="aeaa8-184">每個人都適用的[預設原則](#default-policy-options)；以及</span><span class="sxs-lookup"><span data-stu-id="aeaa8-184">a [default policy](#default-policy-options) that applies to everyone; and</span></span>
- <span data-ttu-id="aeaa8-185">[特定收件者的其他原則](#policies-that-apply-to-specific-email-recipients)</span><span class="sxs-lookup"><span data-stu-id="aeaa8-185">additional [policies for specific recipients](#policies-that-apply-to-specific-email-recipients)</span></span>

### <a name="default-policy-options"></a><span data-ttu-id="aeaa8-186">預設原則選項</span><span class="sxs-lookup"><span data-stu-id="aeaa8-186">Default policy options</span></span>

<span data-ttu-id="aeaa8-187">預設原則選項適用於貴組織中的每個人。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-187">Default policy options apply to everyone in your organization.</span></span>

****

|<span data-ttu-id="aeaa8-188">此選項</span><span class="sxs-lookup"><span data-stu-id="aeaa8-188">This option</span></span>|<span data-ttu-id="aeaa8-189">執行此動作</span><span class="sxs-lookup"><span data-stu-id="aeaa8-189">Does this</span></span>|
|---|---|
|<span data-ttu-id="aeaa8-190">**封鎖下列 URL**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-190">**Block the following URLs**</span></span>|<span data-ttu-id="aeaa8-191">可讓貴組織擁有自動封鎖的自訂 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-191">Enables your organization to have a custom list of URLs that are automatically blocked.</span></span> <span data-ttu-id="aeaa8-192">使用者按一下此清單中的 URL 後，就會前往說明 URL 為何遭到封鎖的[警告頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-192">When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.</span></span> <span data-ttu-id="aeaa8-193">若要深入了解，請參閱[使用 Office 365 ATP 安全連結來設定自訂封鎖的 URL 清單](set-up-a-custom-blocked-urls-list-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-193">To learn more, see [Set up a custom blocked URLs list using Office 365 ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>|
|<span data-ttu-id="aeaa8-194">**適用于企業的 Microsoft 365 應用程式、Office for iOS 和 Android**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-194">**Microsoft 365 Apps for enterprise, Office for iOS and Android**</span></span>| <span data-ttu-id="aeaa8-195">選取此選項時，ATP 安全連結保護適用于 Word、Excel URLs 及 PowerPoint 檔案中的 Windows 或 Mac 作業系統、Outlook 中的電子郵件、iOS 或 Android 裝置上的 Office 檔、Windows 上的 Visio 2016 檔案，以及在 Office app 的 web 版本中 PowerPoint (開啟的檔案（前提是使用者已登入 Office 365）。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-195">When this option is selected, ATP Safe Links protection is applied to URLs in Word, Excel, and PowerPoint files on Windows or Mac OS, email messages in Outlook, Office documents on iOS or Android devices, Visio 2016 files on Windows, and files open in the web versions of Office apps (Word, PowerPoint, Excel, Outlook, and OneNote), provided the user has signed in to Office 365.</span></span>|
|<span data-ttu-id="aeaa8-196">**當使用者按一下 ATP 安全連結時不要追蹤**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-196">**Don't track when users click ATP Safe Links**</span></span>|<span data-ttu-id="aeaa8-197">選取此選項時，不會儲存 [Word]、[Excel]、[PowerPoint]、[Visio 檔] 及 [Outlook 電子郵件訊息] 中 URLs 的資料。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-197">When this option is selected, click data for URLs in Word, Excel, PowerPoint, Visio documents, and Outlook email messages is not stored.</span></span>|
|<span data-ttu-id="aeaa8-198">**不要讓使用者點選原始 URL 的 ATP 安全連結**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-198">**Don't let users click through ATP Safe Links to original URL**</span></span>|<span data-ttu-id="aeaa8-199">若選取此選項，使用者就無法繼續將[警告頁面](atp-safe-links-warning-pages.md)傳送到被判定是惡意的 URL。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-199">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>|
|

### <a name="policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="aeaa8-200">適用於特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="aeaa8-200">Policies that apply to specific email recipients</span></span>

****

|<span data-ttu-id="aeaa8-201">此選項</span><span class="sxs-lookup"><span data-stu-id="aeaa8-201">This option</span></span>|<span data-ttu-id="aeaa8-202">執行此動作</span><span class="sxs-lookup"><span data-stu-id="aeaa8-202">Does this</span></span>|
|---|---|
|<span data-ttu-id="aeaa8-203">**關閉**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-203">**Off**</span></span>|<span data-ttu-id="aeaa8-204">不要掃描電子郵件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-204">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="aeaa8-205">可讓您定義例外狀況規則，例如以下規則：不要掃描特定收件者群組的電子郵件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-205">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>|
|<span data-ttu-id="aeaa8-206">**開啟**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-206">**On**</span></span>|<span data-ttu-id="aeaa8-207">當使用者按一下電子郵件中的 URL 並啟用 Windows 上 Outlook (C2R) 中的 ATP 安全連結時，重寫 URL 以透過 ATP 安全連結防護路由傳送使用者。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-207">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages and enables ATP Safe Links within Outlook (C2R) on Windows.</span></span>  <br/> <span data-ttu-id="aeaa8-208">如果 URL 沒有令人信服的信譽，則在點選已封鎖或惡意的 URL 清單時檢查 URL，並以非同步方式在背景觸發 URL 引爆。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-208">Checks a URL when clicked against a list of blocked or malicious URLs and triggers a detonation of the URL in the background asynchronously if the URL does not have a valid reputation.</span></span>|
|<span data-ttu-id="aeaa8-209">**針對可疑的連結和指向檔案的連結套用即時 URL 掃描**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-209">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>|<span data-ttu-id="aeaa8-210">若選取此選項，則會掃描指向可下載內容的可疑 URL 和連結。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-210">When this option is selected, suspicious URLs and links that point to downloadable content are scanned.</span></span>|
|<span data-ttu-id="aeaa8-211">**等待 URL 掃描完成再傳遞郵件**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-211">**Wait for URL scanning to complete before delivering the message**</span></span>|<span data-ttu-id="aeaa8-212">若選取此選項，則會保留包含要掃描 URL 的郵件，直到 URL 完成掃描且確認是安全的，才會傳遞這些郵件。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-212">When this option is selected, messages that contain URLs to be scanned will be held until the URLs finish scanning and are confirmed to be safe before the messages are delivered.</span></span>|
|<span data-ttu-id="aeaa8-213">**將安全連結套用至組織內傳送的郵件**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-213">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="aeaa8-214">此選項若可使用並已選取，假設電子郵件帳戶託管於 Office 365，則 ATP 安全連結保護就會套用至在貴組織中的人員間傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-214">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>|
|<span data-ttu-id="aeaa8-215">**不要追蹤使用者點選**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-215">**Do not track user clicks**</span></span>|<span data-ttu-id="aeaa8-216">若選取此選項，則不會儲存來自外部寄件者的電子郵件中 URL 的點選資料。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-216">When this option is selected, click data for URLs in email from external senders is not stored.</span></span> <span data-ttu-id="aeaa8-217">目前不支援追蹤組織內傳送的電子郵件中連結的 URL 點選。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-217">URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>|
|<span data-ttu-id="aeaa8-218">**不允許使用者點選原始 URL**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-218">**Do not allow users to click through to original URL**</span></span>|<span data-ttu-id="aeaa8-219">若選取此選項，使用者就無法繼續將[警告頁面](atp-safe-links-warning-pages.md)傳送到被判定是惡意的 URL。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-219">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>|
|<span data-ttu-id="aeaa8-220">**不要重寫下列 URL**</span><span class="sxs-lookup"><span data-stu-id="aeaa8-220">**Do not rewrite the following URLs**</span></span>|<span data-ttu-id="aeaa8-221">將 URL 保留原樣。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-221">Leaves URLs as they are.</span></span> <span data-ttu-id="aeaa8-222">保留不需要掃描貴組織中特定電子郵件收件者群組的自訂安全 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-222">Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.</span></span> <span data-ttu-id="aeaa8-223">如需詳細資料 (包括支援萬用字元星號 (\*) 的近期變更)，請參閱[使用 ATP 安全連結來設定自訂「不要重寫」URL 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-223">See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="aeaa8-224">後續步驟</span><span class="sxs-lookup"><span data-stu-id="aeaa8-224">Next steps</span></span>

<span data-ttu-id="aeaa8-225">在您的 ATP 安全連結原則就緒後，您就可以透過查看報告，查看 ATP 對您的組織的運作方式。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-225">Once your ATP Safe Links policies are in place, you can see how ATP is working for your organization by viewing reports.</span></span> <span data-ttu-id="aeaa8-226">請參閱下列資源，以深入了解詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="aeaa8-226">See the following resources to learn more:</span></span>

- [<span data-ttu-id="aeaa8-227">檢視 Office 365 進階威脅防護的報告</span><span class="sxs-lookup"><span data-stu-id="aeaa8-227">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="aeaa8-228">使用安全性與合規性中心中的 Explorer</span><span class="sxs-lookup"><span data-stu-id="aeaa8-228">Use Explorer in the Security & Compliance Center</span></span>](threat-explorer.md)

<span data-ttu-id="aeaa8-229">隨時掌握最新的 ATP 功能。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-229">Stay on top of new features coming to ATP.</span></span> <span data-ttu-id="aeaa8-230">瀏覽 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。</span><span class="sxs-lookup"><span data-stu-id="aeaa8-230">visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>
