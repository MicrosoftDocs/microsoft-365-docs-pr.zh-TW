---
title: Office 365 群組命名原則
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: 了解如何建立 Office 365 群組命名原則。
ms.openlocfilehash: 50ea076e22680a444cb9acf04466a7e7d052bb7a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239226"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="f1841-103">Office 365 群組命名原則</span><span class="sxs-lookup"><span data-stu-id="f1841-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="f1841-104">您可以使用群組命名原則強制執行一致的命名策略，組織中使用者所建立的群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="f1841-105">命名原則可協助您和您的使用者識別群組成員資格、 地理區域的函式或建立群組的人員。</span><span class="sxs-lookup"><span data-stu-id="f1841-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="f1841-106">命名原則也有助於分類在通訊錄中的群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="f1841-107">您可以使用原則來封鎖特定字詞，防止正在使用中群組的名稱和別名。</span><span class="sxs-lookup"><span data-stu-id="f1841-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="f1841-108">命名原則會套用至跨所有群組工作負載 （例如 Outlook、 Microsoft Teams、 SharePoint、 規劃、 Yammer、 等等） 所建立的群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc).</span></span> <span data-ttu-id="f1841-109">它會套用到的群組名稱和群組的別名。</span><span class="sxs-lookup"><span data-stu-id="f1841-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="f1841-110">它會取得套用當使用者建立的群組和群組名稱或別名時為編輯現有的群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="f1841-111">Office 365 群組命名原則僅適用於 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-111">An Office 365 group naming policy only applies to Office 365 Groups.</span></span> <span data-ttu-id="f1841-112">它不會套用至 Exchange Online 中建立的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="f1841-113">若要建立通訊群組命名原則，請參閱[建立通訊群組命名原則](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="f1841-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="f1841-114">群組命名原則包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="f1841-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="f1841-115">**前置詞尾碼命名原則**： 您可以使用前置詞或尾碼至定義群組的命名慣例 (例如: 「 群組\_美國\_我的群組\_工程 」)。</span><span class="sxs-lookup"><span data-stu-id="f1841-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "GRP\_US\_My Group\_Engineering").</span></span> <span data-ttu-id="f1841-116">會取得替代的使用者屬性像是 [部門] 根據建立群組的使用者或首碼/尾碼可以都是固定的字串。</span><span class="sxs-lookup"><span data-stu-id="f1841-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="f1841-117">**自訂封鎖的文字**： 您可以將一組的封鎖特定的文字上傳至其會封鎖使用者所建立的群組中的組織。</span><span class="sxs-lookup"><span data-stu-id="f1841-117">**Custom Blocked Words**: You can upload a set of blocked words specific to their organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="f1841-118">(例如: 「 CEO、 薪資，人力資源 」)。</span><span class="sxs-lookup"><span data-stu-id="f1841-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="f1841-119">授權需求</span><span class="sxs-lookup"><span data-stu-id="f1841-119">Licensing requirements</span></span>

<span data-ttu-id="f1841-120">使用 Azure AD 命名原則之 Office 365 群組需要您擁有，但不是一定是指派給 Azure Active Directory 進階版 P1 授權或 Azure AD 基本教育授權的每個唯一的使用者 （包括訪客） 是一或多個 Office 365 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f1841-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>
<span data-ttu-id="f1841-121">這也是必要的系統管理員所建立的群組命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="f1841-122">前置詞尾碼的命名原則</span><span class="sxs-lookup"><span data-stu-id="f1841-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="f1841-123">首碼和尾碼可以也被固定的字串或使用者屬性。</span><span class="sxs-lookup"><span data-stu-id="f1841-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="f1841-124">固定的字串</span><span class="sxs-lookup"><span data-stu-id="f1841-124">Fixed strings</span></span>

<span data-ttu-id="f1841-125">您可以使用簡短的字串，可協助您區別 GAL] 和 [左導覽中的群組工作負載的群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-125">You can use short strings that can help you differentiate groups in the GAL and Left nav of the group workloads.</span></span> <span data-ttu-id="f1841-126">一些常見前置詞尾碼是類似的關鍵字 '群組\_名稱 '、'\#名稱 '、'\_名稱 '</span><span class="sxs-lookup"><span data-stu-id="f1841-126">Some of the common prefixes suffixes are Keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="f1841-127">屬性</span><span class="sxs-lookup"><span data-stu-id="f1841-127">Attributes</span></span>

<span data-ttu-id="f1841-128">您可以使用屬性，可協助您識別人員建立像是 [部門] 群組，其中它所建立像是 [國家/地區]。</span><span class="sxs-lookup"><span data-stu-id="f1841-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f1841-129">**範例**</span><span class="sxs-lookup"><span data-stu-id="f1841-129">**Examples**</span></span>|<span data-ttu-id="f1841-130">原則 = 」 群組 [群組名稱] [部門]"</span><span class="sxs-lookup"><span data-stu-id="f1841-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="f1841-131">使用者的部門 = 工程</span><span class="sxs-lookup"><span data-stu-id="f1841-131">User's department = Engineering</span></span>|
||<span data-ttu-id="f1841-132">建立群組名稱 ="群組我群組工程 」</span><span class="sxs-lookup"><span data-stu-id="f1841-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="f1841-133">支援的 Azure Active Directory (Azure AD) 屬性為 [部門]、 [公司]、 [Office]、 [StateOrProvince]，[CountryOrRegion]，[標題]</span><span class="sxs-lookup"><span data-stu-id="f1841-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]</span></span>

- <span data-ttu-id="f1841-134">不支援的使用者屬性會被視為固定字串。</span><span class="sxs-lookup"><span data-stu-id="f1841-134">Unsupported user attributes are considered as fixed strings.</span></span> <span data-ttu-id="f1841-135">例如：</span><span class="sxs-lookup"><span data-stu-id="f1841-135">E.g.</span></span> <span data-ttu-id="f1841-136">"[郵遞區號]"</span><span class="sxs-lookup"><span data-stu-id="f1841-136">"[postalCode]"</span></span>

- <span data-ttu-id="f1841-137">不支援延伸的屬性和自訂屬性。</span><span class="sxs-lookup"><span data-stu-id="f1841-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="f1841-138">建議您使用有值填入您的組織中的所有使用者的屬性，而且不使用有較長的值的屬性。</span><span class="sxs-lookup"><span data-stu-id="f1841-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="f1841-139">若要留意的事項</span><span class="sxs-lookup"><span data-stu-id="f1841-139">Things to look out for</span></span>

- <span data-ttu-id="f1841-140">原則建立期間的總首碼和尾碼字串長度只有 53 的字元。</span><span class="sxs-lookup"><span data-stu-id="f1841-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="f1841-141">前置詞和尾碼可以包含群組名稱和群組的別名中支援的特殊字元。</span><span class="sxs-lookup"><span data-stu-id="f1841-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="f1841-142">當首碼和尾碼包含特殊字元。 不可用於群組別名時，他們會移除，並套用至群組的別名。</span><span class="sxs-lookup"><span data-stu-id="f1841-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are removed and applied to the group alias.</span></span> <span data-ttu-id="f1841-143">因此在此情況下，首碼和尾碼套用至群組名稱會是不同於套用至群組的別名。</span><span class="sxs-lookup"><span data-stu-id="f1841-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="f1841-144">如果您使用 Yammer Office 365 的連線群組，避免命名原則中使用下列字元: @， \#、 \[、 \]、 \<，和\>。</span><span class="sxs-lookup"><span data-stu-id="f1841-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="f1841-145">如果這些字元的命名原則中，一般的 Yammer 使用者將無法建立群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="f1841-146">自訂封鎖的文字</span><span class="sxs-lookup"><span data-stu-id="f1841-146">Custom blocked words</span></span>

<span data-ttu-id="f1841-147">您可以輸入封鎖的文字，將會封鎖的逗號分隔清單中群組的名稱和別名。</span><span class="sxs-lookup"><span data-stu-id="f1841-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="f1841-148">[封鎖的文字] 核取是在使用者輸入群組名稱上執行。</span><span class="sxs-lookup"><span data-stu-id="f1841-148">The blocked words check is done on the user entered group name.</span></span> <span data-ttu-id="f1841-149">因此，如果使用者在輸入 'darnit' 和 '前置詞\_' 已命名的原則，' 字首\_darnit' 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="f1841-149">So if user enters 'darnit' and 'Prefix\_' is the naming policy, 'Prefix\_darnit' will fail.</span></span>

<span data-ttu-id="f1841-150">會不執行任何子字串搜尋;具體而言，輸入使用者名稱及自訂封鎖的文字完全相符，才能觸發失敗。</span><span class="sxs-lookup"><span data-stu-id="f1841-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="f1841-151">子字串搜尋未完成，這樣即使 '協助' 是封鎖的字，使用者可以使用一些常見的單字，如同 '類別'。</span><span class="sxs-lookup"><span data-stu-id="f1841-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="f1841-152">**若要留意的事項**：</span><span class="sxs-lookup"><span data-stu-id="f1841-152">**Things to look out for**:</span></span>

- <span data-ttu-id="f1841-153">封鎖的文字不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="f1841-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="f1841-154">當使用者在輸入封鎖的 word 時，群組用戶端會顯示錯誤訊息的已封鎖的字。</span><span class="sxs-lookup"><span data-stu-id="f1841-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="f1841-155">沒有使用封鎖的文字中的字元限制。</span><span class="sxs-lookup"><span data-stu-id="f1841-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="f1841-156">沒有上限 5000 文字的可設定為封鎖的文字。</span><span class="sxs-lookup"><span data-stu-id="f1841-156">There is an upper limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="f1841-157">系統管理員覆寫</span><span class="sxs-lookup"><span data-stu-id="f1841-157">Admin override</span></span>

<span data-ttu-id="f1841-158">選擇性的系統管理員不需要這些原則，跨所有群組工作負載和端點，以便他們可以建立群組，這些封鎖的字詞與對其所需的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="f1841-158">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="f1841-159">以下是系統管理員角色群組命名原則不受的清單。</span><span class="sxs-lookup"><span data-stu-id="f1841-159">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="f1841-160">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f1841-160">Global admin</span></span>

- <span data-ttu-id="f1841-161">合作夥伴第 1 層支援</span><span class="sxs-lookup"><span data-stu-id="f1841-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="f1841-162">合作夥伴第 2 層支援</span><span class="sxs-lookup"><span data-stu-id="f1841-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="f1841-163">使用者帳戶系統管理員</span><span class="sxs-lookup"><span data-stu-id="f1841-163">User account admin</span></span>

- <span data-ttu-id="f1841-164">目錄作者</span><span class="sxs-lookup"><span data-stu-id="f1841-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="f1841-165">如何設定命名原則</span><span class="sxs-lookup"><span data-stu-id="f1841-165">How to set up the naming policy</span></span>

<span data-ttu-id="f1841-166">若要設定的命名原則：</span><span class="sxs-lookup"><span data-stu-id="f1841-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="f1841-167">在[Azure Active Directory](https://aad.portal.azure.com)中，按一下 [**管理**] 下的 [**群組**]。</span><span class="sxs-lookup"><span data-stu-id="f1841-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="f1841-168">在 [**設定**] 下按一下 [**命名原則**]。</span><span class="sxs-lookup"><span data-stu-id="f1841-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="f1841-169">選擇 [**群組命名原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f1841-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="f1841-170">在**目前的原則**] 下選擇 [您是否需要前置詞或尾碼或以上兩者、，然後選取適當的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f1841-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="f1841-171">選擇**屬性**和**字串**之間每一行，然後指定 [屬性] 或 [字串。</span><span class="sxs-lookup"><span data-stu-id="f1841-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="f1841-172">當您已新增首碼和尾碼後，您需要時請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f1841-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![群組命名原則 」 設定 Azure Active Directory 中的螢幕擷取畫面](../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a><span data-ttu-id="f1841-174">不同 Office 365 應用程式的命名原則體驗</span><span class="sxs-lookup"><span data-stu-id="f1841-174">Naming policy experiences across Office 365 apps</span></span>

<span data-ttu-id="f1841-175">已更新的 Office 365 應用程式，以顯示預覽 （含前置詞和尾碼） 的命名原則群組名稱的使用者時輸入群組名稱和別名。</span><span class="sxs-lookup"><span data-stu-id="f1841-175">The Office 365 apps have been updated to show a preview of the naming policy group name (with prefixes and suffixes) when the user types in the group name and alias.</span></span> <span data-ttu-id="f1841-176">當使用者輸入封鎖的文字時，他們會看到一則錯誤訊息，讓他們可以移除封鎖的文字。</span><span class="sxs-lookup"><span data-stu-id="f1841-176">When the user enters blocked words, they'll see an error message so they can remove the blocked words.</span></span>

## <a name="outlook-on-the-web"></a><span data-ttu-id="f1841-177">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="f1841-177">Outlook on the web</span></span>

<span data-ttu-id="f1841-178">當使用者輸入群組名稱或群組的別名 （先前稱為 Outlook Web App 或 OWA） 網頁型 outlook 會顯示命名裝飾的原則名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-178">Outlook on the web (formerly known as Outlook Web App or OWA) shows the naming policy decorated name when the user types a group name or group alias.</span></span> <span data-ttu-id="f1841-179">當使用者輸入自訂的封鎖的 word 時，錯誤訊息所示的封鎖的字以及 UI，讓使用者可以將它移除。</span><span class="sxs-lookup"><span data-stu-id="f1841-179">When an user enters a custom blocked word, an error message is shown in the UI along with the blocked word so that the user can remove it.</span></span> <span data-ttu-id="f1841-180">Outlook web 體驗快照集如下所示。</span><span class="sxs-lookup"><span data-stu-id="f1841-180">Outlook on the web experience snapshots are shown below.</span></span>

![並排檢視的群組命名原則在 Office 365 群組](../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a><span data-ttu-id="f1841-182">Outlook 桌面</span><span class="sxs-lookup"><span data-stu-id="f1841-182">Outlook Desktop</span></span>

<span data-ttu-id="f1841-183">在 Outlook 桌面中建立的群組是相容命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-183">Groups created in Outlook desktop are compliant with naming policy.</span></span> <span data-ttu-id="f1841-184">Outlook 桌面應用程式尚未不會顯示預覽的命名原則，並不會傳回自訂封鎖的 word 錯誤，當使用者輸入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-184">Outlook desktop app doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span> <span data-ttu-id="f1841-185">但是，命名原則會自動套用上選取 [建立/編輯，使用者將會出現錯誤如果有自訂封鎖的文字中的群組名稱或別名。</span><span class="sxs-lookup"><span data-stu-id="f1841-185">However, naming policy will be automatically applied on selecting create/edit and users will be presented with errors if there are custom blocked words in the group name or alias.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="f1841-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1841-186">Microsoft Teams</span></span>

<span data-ttu-id="f1841-187">使用者輸入的小組名稱時，Microsoft Teams 會顯示命名裝飾的原則名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-187">Microsoft Teams shows the naming policy decorated name when the user types a team name.</span></span> <span data-ttu-id="f1841-188">當使用者輸入自訂的封鎖的 word 時，會顯示錯誤訊息以及封鎖的字，讓使用者可以將它移除。</span><span class="sxs-lookup"><span data-stu-id="f1841-188">When a user enters a custom blocked word, an error message is shown along with the blocked word so that the user can remove it.</span></span>

![Microsoft Teams 中的群組命名原則封鎖範例](../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a><span data-ttu-id="f1841-190">SharePoint</span><span class="sxs-lookup"><span data-stu-id="f1841-190">SharePoint</span></span>

<span data-ttu-id="f1841-191">當使用者所輸入網站的名稱或群組電子郵件地址，SharePoint 會顯示命名的原則名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-191">SharePoint shows the naming policy name when the user types a site name or group email address.</span></span> <span data-ttu-id="f1841-192">當使用者在輸入自訂的封鎖的 word，錯誤訊息會顯示，以及封鎖 word，讓使用者可以將它移除。</span><span class="sxs-lookup"><span data-stu-id="f1841-192">When an user enters a custom blocked word, an error message is shown, along with the blocked word so that the user can remove it.</span></span>

![群組命名原則-SharePoint 網站封鎖名稱](../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a><span data-ttu-id="f1841-194">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="f1841-194">Microsoft Stream</span></span>

<span data-ttu-id="f1841-195">使用者輸入群組名稱或群組電子郵件別名時，Microsoft Stream 顯示命名裝飾的原則名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-195">Microsoft Stream shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="f1841-196">當使用者輸入自訂的封鎖的 word 時，錯誤訊息會顯示的已封鎖的字，讓使用者可以將它移除。</span><span class="sxs-lookup"><span data-stu-id="f1841-196">When an user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![群組命名原則會封鎖 Microsoft Stream 範例](../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a><span data-ttu-id="f1841-198">Outlook iOS 和 Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="f1841-198">Outlook iOS and Android App</span></span>

<span data-ttu-id="f1841-199">在 Outlook 應用程式中建立的群組是相容命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-199">Groups created in Outlook apps are compliant with naming policy.</span></span> <span data-ttu-id="f1841-200">輸入群組名稱時，outlook 行動裝置會顯示命名原則預覽]。</span><span class="sxs-lookup"><span data-stu-id="f1841-200">Outlook mobile shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="f1841-201">當使用者輸入自訂的封鎖的 word 時，錯誤訊息會顯示在建立群組，讓使用者可以移除封鎖的單字。</span><span class="sxs-lookup"><span data-stu-id="f1841-201">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="planner"></a><span data-ttu-id="f1841-202">Planner</span><span class="sxs-lookup"><span data-stu-id="f1841-202">Planner</span></span>

<span data-ttu-id="f1841-203">Planner 已符合命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-203">Planner is compliant with naming policy.</span></span> <span data-ttu-id="f1841-204">規劃顯示命名原則預覽時輸入計劃名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-204">Planner shows the naming policy preview when entering the Plan name.</span></span> <span data-ttu-id="f1841-205">當使用者輸入自訂的封鎖的 word 時，會顯示一則錯誤訊息建立計劃，讓使用者可以移除封鎖的單字。</span><span class="sxs-lookup"><span data-stu-id="f1841-205">When a user enters a custom blocked word, an error message is shown on creating the plan, so the user can remove the blocked word.</span></span>

![群組命名原則： 建立新的已封鎖的規劃範例](../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a><span data-ttu-id="f1841-207">Dynamics 365 for Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="f1841-207">Dynamics 365 for Customer Engagement</span></span>

<span data-ttu-id="f1841-208">Dynamics 365 for Customer Engagement 是相容命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-208">Dynamics 365 for Customer Engagement is compliant with naming policy.</span></span> <span data-ttu-id="f1841-209">Dynamics 365 顯示命名裝飾的原則名稱，當使用者輸入群組名稱或群組電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="f1841-209">Dynamics 365 shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="f1841-210">當使用者輸入自訂的封鎖的 word 時，錯誤訊息會顯示的已封鎖的字，讓使用者可以將它移除。</span><span class="sxs-lookup"><span data-stu-id="f1841-210">When the user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Dynamics 365](../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a><span data-ttu-id="f1841-212">學校資料同步 (SDS)</span><span class="sxs-lookup"><span data-stu-id="f1841-212">School Data Sync (SDS)</span></span>

<span data-ttu-id="f1841-213">透過 SDS 建立的群組遵守命名原則，但命名原則不會自動套用。</span><span class="sxs-lookup"><span data-stu-id="f1841-213">Groups created through SDS comply with naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="f1841-214">SDS 系統管理員必須將首碼和尾碼附加到其群組需要建立，然後上傳至 SDS 的類別名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-214">SDS administrators have to append the prefixes and suffixes to class names for which groups need to be created and then upload to SDS.</span></span> <span data-ttu-id="f1841-215">群組建立/編輯否則就會失敗。</span><span class="sxs-lookup"><span data-stu-id="f1841-215">Groups creation/edit would fail otherwise.</span></span>

## <a name="outlook-customer-manager-ocm"></a><span data-ttu-id="f1841-216">Outlook Customer Manager (OCM)</span><span class="sxs-lookup"><span data-stu-id="f1841-216">Outlook Customer Manager (OCM)</span></span>

<span data-ttu-id="f1841-217">Outlook Customer Manager 是相容命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-217">Outlook Customer Manager is compliant with naming policy.</span></span> <span data-ttu-id="f1841-218">命名原則會自動套用至建立 Outlook Customer Manager 中的群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-218">The naming policy gets automatically applied to the group created in Outlook Customer Manager.</span></span> <span data-ttu-id="f1841-219">如果任何內 「 所有銷售小組 」 文字定義為自訂的封鎖 word，將會封鎖 OCM 中的建立群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-219">If any of the words within "All Sales Team" is defined as a custom blocked word, the group creation in OCM will be blocked.</span></span> <span data-ttu-id="f1841-220">使用者將無法建立 OCM 群組，並將無法使用 OCM 應用程式。 」</span><span class="sxs-lookup"><span data-stu-id="f1841-220">The user will not be able to create the OCM group and will be blocked from using the OCM app."</span></span>

## <a name="classroom-app"></a><span data-ttu-id="f1841-221">教室應用程式</span><span class="sxs-lookup"><span data-stu-id="f1841-221">Classroom App</span></span>

<span data-ttu-id="f1841-222">在教室應用程式中建立的群組遵守命名原則，但命名原則不會自動套用，命名原則預覽不會對使用者顯示時輸入教室群組名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-222">Groups created in classroom app comply with naming policy, but the naming policy isn't applied automatically, and the naming policy preview isn't shown to the users while entering a classroom group name.</span></span> <span data-ttu-id="f1841-223">讓使用者必須輸入裝飾的教室的群組名稱具有前置詞和尾碼。</span><span class="sxs-lookup"><span data-stu-id="f1841-223">So users would have to enter the decorated classroom group name with prefixes and suffixes.</span></span> <span data-ttu-id="f1841-224">否則教室群組建立或編輯會失敗，錯誤。</span><span class="sxs-lookup"><span data-stu-id="f1841-224">Otherwise the classroom group create or edit will fail with errors.</span></span>

## <a name="power-bi"></a><span data-ttu-id="f1841-225">Power BI</span><span class="sxs-lookup"><span data-stu-id="f1841-225">Power BI</span></span>

<span data-ttu-id="f1841-226">在 Power BI 工作區中建立的群組遵守命名原則，但命名原則不會自動套用。</span><span class="sxs-lookup"><span data-stu-id="f1841-226">Groups created in Power BI workspaces comply with the naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="f1841-227">並命名原則預覽不會顯示給使用者時使用者輸入的 Power BI 工作區名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-227">And, the naming policy preview isn't shown to users when they enter a Power BI workspace name.</span></span>

<span data-ttu-id="f1841-228">建議的名稱-與套用-命名原則會顯示的錯誤的詳細資訊建立或編輯工作區中。</span><span class="sxs-lookup"><span data-stu-id="f1841-228">The recommended name - with the naming policy applied - is shown in the error details on create or edit workspaces.</span></span> <span data-ttu-id="f1841-229">這表示使用者必須輸入裝飾工作區名稱具有前置詞和尾碼。</span><span class="sxs-lookup"><span data-stu-id="f1841-229">This means users have to enter the decorated workspace name with prefixes and suffixes.</span></span> <span data-ttu-id="f1841-230">否則請在工作區建立或編輯會失敗，錯誤。</span><span class="sxs-lookup"><span data-stu-id="f1841-230">Otherwise the workspace create or edit will fail with errors.</span></span>

## <a name="yammer"></a><span data-ttu-id="f1841-231">Yammer</span><span class="sxs-lookup"><span data-stu-id="f1841-231">Yammer</span></span>

<span data-ttu-id="f1841-232">當使用者與自己的 Azure Active Directory 帳戶登入 Yammer 建立的群組，或編輯群組名稱時，群組名稱會遵守命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-232">When a user signed in to Yammer with their Azure Active Directory account creates a group or edits a group name, the group name will comply with naming policy.</span></span> <span data-ttu-id="f1841-233">這適用於同時連線的 Office 365 群組及所有其他的 Yammer 群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-233">This applies both to Office 365 connected groups and all other Yammer groups.</span></span>

<span data-ttu-id="f1841-234">如果 Office 365 連線的群組命名原則會就地之前建立的群組名稱將不會自動追蹤的命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-234">If an Office 365 connected group was created before the naming policy is in place, the group name will not automatically follow the naming policies.</span></span> <span data-ttu-id="f1841-235">當使用者編輯的群組名稱時，系統會提示他們新增首碼和尾碼。</span><span class="sxs-lookup"><span data-stu-id="f1841-235">When a user edits the group name, they will be prompted to add the prefix and suffix.</span></span>

<span data-ttu-id="f1841-236">如果命名原則包含無法在 Yammer 群組名稱中的字元，僅限系統管理員將能夠在 Yammer 中建立的連線的群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-236">If the naming policy includes characters that can't be in Yammer group names, only admins will be able to create a connected group in Yammer.</span></span>

## <a name="staffhub"></a><span data-ttu-id="f1841-237">StaffHub</span><span class="sxs-lookup"><span data-stu-id="f1841-237">StaffHub</span></span>

<span data-ttu-id="f1841-238">StaffHub teams 不適用的命名原則，但基礎的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="f1841-238">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="f1841-239">StaffHub 小組名稱不適用的首碼和尾碼，而且不會檢查自訂封鎖的文字。</span><span class="sxs-lookup"><span data-stu-id="f1841-239">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="f1841-240">但 StaffHub 並套用首碼和尾碼，並從基礎的 Office 365 群組中移除封鎖的文字。</span><span class="sxs-lookup"><span data-stu-id="f1841-240">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="exchange-powershell"></a><span data-ttu-id="f1841-241">Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1841-241">Exchange PowerShell</span></span>

<span data-ttu-id="f1841-242">Exchange PowerShell cmdlet 是相容命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-242">Exchange PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="f1841-243">如果中的群組名稱和群組的別名不會使用命名慣例，使用者會收到適當的錯誤訊息與建議的首碼和尾碼，以及自訂封鎖的文字。</span><span class="sxs-lookup"><span data-stu-id="f1841-243">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="f1841-244">Azure Active Directory PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="f1841-244">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="f1841-245">Azure Active Directory PowerShell cmdlet 是相容命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-245">Azure Active Directory PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="f1841-246">如果中的群組名稱和群組的別名不會使用命名慣例，使用者會收到適當的錯誤訊息與建議的首碼和尾碼，以及自訂封鎖的文字。</span><span class="sxs-lookup"><span data-stu-id="f1841-246">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="exchange-admin-center"></a><span data-ttu-id="f1841-247">Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="f1841-247">Exchange admin center</span></span>

<span data-ttu-id="f1841-248">在 Exchange 系統管理中心 (EAC) 是相容命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-248">The Exchange admin center (EAC) is compliant with naming policy.</span></span> <span data-ttu-id="f1841-249">在建立或編輯動作，使用者會收到適當的錯誤訊息與建議的首碼和尾碼，以及自訂封鎖的文字，如果中的群組名稱和群組的別名不會使用命名慣例。</span><span class="sxs-lookup"><span data-stu-id="f1841-249">On create or edit actions, users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="microsoft-365-admin-center"></a><span data-ttu-id="f1841-250">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="f1841-250">Microsoft 365 admin center</span></span>

<span data-ttu-id="f1841-251">在 Microsoft 365 系統管理中心是相容命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-251">The Microsoft 365 admin center is compliant with naming policy.</span></span> <span data-ttu-id="f1841-252">在建立或編輯動作，命名原則將會自動套用。</span><span class="sxs-lookup"><span data-stu-id="f1841-252">On create or edit actions, naming policy will automatically get applied.</span></span> <span data-ttu-id="f1841-253">當使用者輸入自訂封鎖的文字時，使用者會收到適當的錯誤。</span><span class="sxs-lookup"><span data-stu-id="f1841-253">Users will get appropriate errors when they enter custom blocked words.</span></span> <span data-ttu-id="f1841-254">在 Microsoft 365 系統管理中心還不會顯示預覽的命名原則，並不會傳回自訂封鎖的 word 錯誤，當使用者輸入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-254">The Microsoft 365 admin center doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span>

## <a name="azure-active-directory-portal"></a><span data-ttu-id="f1841-255">Azure Active Directory 入口網站</span><span class="sxs-lookup"><span data-stu-id="f1841-255">Azure Active Directory portal</span></span>

<span data-ttu-id="f1841-256">在 Azure Active Directory 入口網站是相容命名原則。</span><span class="sxs-lookup"><span data-stu-id="f1841-256">The Azure Active Directory portal is compliant with naming policy.</span></span> <span data-ttu-id="f1841-257">Azure Active Directory 入口網站中顯示的命名原則預覽時輸入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="f1841-257">Azure Active Directory portal shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="f1841-258">當使用者輸入自訂的封鎖的 word 時，錯誤訊息會顯示在建立群組，讓使用者可以移除封鎖的單字。</span><span class="sxs-lookup"><span data-stu-id="f1841-258">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="f1841-259">更多文章命名原則</span><span class="sxs-lookup"><span data-stu-id="f1841-259">More articles on naming policy</span></span>

[<span data-ttu-id="f1841-260">強制執行 Azure Active Directory 中的 Office 365 群組命名原則</span><span class="sxs-lookup"><span data-stu-id="f1841-260">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="f1841-261">設定群組設定 azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="f1841-261">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
