---
title: Office 365 群組命名原則
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
description: 瞭解如何建立 Office 365 群組的命名原則。
ms.openlocfilehash: 4325a5e0a1de0c3a83be71220abd256c204ec07d
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894620"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="e18ac-103">Office 365 群組命名原則</span><span class="sxs-lookup"><span data-stu-id="e18ac-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="e18ac-104">您可以使用群組命名原則，針對組織中使用者所建立的群組強制執行一致的命名策略。</span><span class="sxs-lookup"><span data-stu-id="e18ac-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="e18ac-105">命名原則可協助您和您的使用者識別群組、成員資格、地理區域的功能，或群組的建立者。</span><span class="sxs-lookup"><span data-stu-id="e18ac-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="e18ac-106">命名原則也可協助分類通訊錄中的群組。</span><span class="sxs-lookup"><span data-stu-id="e18ac-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="e18ac-107">您可以使用原則來封鎖群組名稱和別名中所用的特定字詞。</span><span class="sxs-lookup"><span data-stu-id="e18ac-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="e18ac-108">命名原則會套用至所有群組工作負載（如 Outlook、Microsoft 團隊、SharePoint、Planner、Yammer 等）上建立的群組。</span><span class="sxs-lookup"><span data-stu-id="e18ac-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="e18ac-109">它會套用至群組名稱和群組別名。</span><span class="sxs-lookup"><span data-stu-id="e18ac-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="e18ac-110">當使用者建立群組，以及為現有的群組編輯群組名稱或別名時，便會套用此方式。</span><span class="sxs-lookup"><span data-stu-id="e18ac-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="e18ac-111">Office 365 群組命名原則只適用于 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="e18ac-111">An Office 365 group naming policy only applies to Office 365 groups.</span></span> <span data-ttu-id="e18ac-112">這不適用於 Exchange Online 中所建立的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="e18ac-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="e18ac-113">若要建立通訊群組的命名原則，請參閱[建立通訊群組命名原則](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="e18ac-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="e18ac-114">群組命名原則包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="e18ac-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="e18ac-115">**前置詞尾碼命名原則**：您可以使用首碼或尾碼來定義群組的命名慣例（例如：「US\_My Group\_工程」）。</span><span class="sxs-lookup"><span data-stu-id="e18ac-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="e18ac-116">首碼/尾碼可以是固定字串或像是 [部門] 的使用者屬性，會根據建立群組的使用者進行取代。</span><span class="sxs-lookup"><span data-stu-id="e18ac-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="e18ac-117">**自訂封鎖的字**：您可以上傳組織中特定的封鎖文字集合，這些文字會在使用者建立的群組中封鎖。</span><span class="sxs-lookup"><span data-stu-id="e18ac-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="e18ac-118">（例如： "CEO，工資表，HR"）。</span><span class="sxs-lookup"><span data-stu-id="e18ac-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="e18ac-119">授權需求</span><span class="sxs-lookup"><span data-stu-id="e18ac-119">Licensing requirements</span></span>

<span data-ttu-id="e18ac-120">使用適用于 Office 365 群組的 Azure AD 命名原則，您必須擁有但不一定要為屬於一或多個 Office 365 群組成員的每個唯一使用者（包括來賓）指派 Azure Active Directory Premium P1 授權或 Azure AD 基本 EDU 授權。</span><span class="sxs-lookup"><span data-stu-id="e18ac-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>

<span data-ttu-id="e18ac-121">這對於建立群組命名原則的系統管理員也是必要的。</span><span class="sxs-lookup"><span data-stu-id="e18ac-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="e18ac-122">前置詞尾碼命名原則</span><span class="sxs-lookup"><span data-stu-id="e18ac-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="e18ac-123">首碼和尾碼可以是固定字串或使用者屬性。</span><span class="sxs-lookup"><span data-stu-id="e18ac-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="e18ac-124">固定字串</span><span class="sxs-lookup"><span data-stu-id="e18ac-124">Fixed strings</span></span>

<span data-ttu-id="e18ac-125">您可以使用簡短字串，協助您區分 GAL 中的群組和群組工作負載的左側導覽。</span><span class="sxs-lookup"><span data-stu-id="e18ac-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="e18ac-126">部分常見的首碼尾碼為 "Grp\_Name"、"\#name"、"\_name" 等關鍵字</span><span class="sxs-lookup"><span data-stu-id="e18ac-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="e18ac-127">屬性</span><span class="sxs-lookup"><span data-stu-id="e18ac-127">Attributes</span></span>

<span data-ttu-id="e18ac-128">您可以使用屬性來識別建立群組的人員，例如 [部門]，以及從 [Country] 建立群組的位置。</span><span class="sxs-lookup"><span data-stu-id="e18ac-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e18ac-129">**範例**</span><span class="sxs-lookup"><span data-stu-id="e18ac-129">**Examples**</span></span>|<span data-ttu-id="e18ac-130">Policy = "GRP [GroupName] [部門]"</span><span class="sxs-lookup"><span data-stu-id="e18ac-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="e18ac-131">使用者的部門 = 工程</span><span class="sxs-lookup"><span data-stu-id="e18ac-131">User's department = Engineering</span></span>|
||<span data-ttu-id="e18ac-132">建立的組名 = "GRP My Group 工程"</span><span class="sxs-lookup"><span data-stu-id="e18ac-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="e18ac-133">支援的 Azure Active Directory （Azure AD）屬性為 [部門]、[公司]、[Office]、[StateOrProvince]、[CountryOrRegion] 和 [Title]。</span><span class="sxs-lookup"><span data-stu-id="e18ac-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="e18ac-134">不支援的使用者屬性被視為固定字串。</span><span class="sxs-lookup"><span data-stu-id="e18ac-134">Unsupported user attributes are considered as fixed strings.</span></span> <span data-ttu-id="e18ac-135">舉例來說.</span><span class="sxs-lookup"><span data-stu-id="e18ac-135">E.g.</span></span> <span data-ttu-id="e18ac-136">"[郵遞區號]"</span><span class="sxs-lookup"><span data-stu-id="e18ac-136">"[postalCode]"</span></span>

- <span data-ttu-id="e18ac-137">不支援擴充屬性和自訂屬性。</span><span class="sxs-lookup"><span data-stu-id="e18ac-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="e18ac-138">建議您使用為組織中所有使用者填寫值的屬性，而不要使用具有較長值的屬性。</span><span class="sxs-lookup"><span data-stu-id="e18ac-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="e18ac-139">要查看的專案</span><span class="sxs-lookup"><span data-stu-id="e18ac-139">Things to look out for</span></span>

- <span data-ttu-id="e18ac-140">在建立原則時，總的首碼和尾碼字串長度限制為53個字元。</span><span class="sxs-lookup"><span data-stu-id="e18ac-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="e18ac-141">首碼和尾碼可以包含組名和群組別名中支援的特殊字元。</span><span class="sxs-lookup"><span data-stu-id="e18ac-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="e18ac-142">當前綴和尾碼包含不允許在群組別名中使用的特殊字元時，它們只適用于組名。</span><span class="sxs-lookup"><span data-stu-id="e18ac-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="e18ac-143">因此，在此情況下，套用至群組名稱的首碼和尾碼會與套用至群組別名的首碼和尾碼不同。</span><span class="sxs-lookup"><span data-stu-id="e18ac-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="e18ac-144">如果您使用 Yammer Office 365 連接的群組，請避免在您的命名原則中使用下列字元： \#@ \[、 \] \<、、、 \>、和。</span><span class="sxs-lookup"><span data-stu-id="e18ac-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="e18ac-145">如果這些字元是在命名原則中，一般 Yammer 使用者將無法建立群組。</span><span class="sxs-lookup"><span data-stu-id="e18ac-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="e18ac-146">自訂封鎖的字詞</span><span class="sxs-lookup"><span data-stu-id="e18ac-146">Custom blocked words</span></span>

<span data-ttu-id="e18ac-147">您可以輸入將會在群組名稱和別名中封鎖的封鎖文字，以逗號分隔的清單。</span><span class="sxs-lookup"><span data-stu-id="e18ac-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="e18ac-148">不會執行任何子字串搜尋;具體說來，使用者輸入名稱和自訂封鎖字詞之間的完全相符，會觸發失敗。</span><span class="sxs-lookup"><span data-stu-id="e18ac-148">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="e18ac-149">不會執行子字串搜尋，因此使用者可以使用一些像是 "Class" 的常見文字，即使 ' ass ' 是封鎖的字詞。</span><span class="sxs-lookup"><span data-stu-id="e18ac-149">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="e18ac-150">**要查看的專案**：</span><span class="sxs-lookup"><span data-stu-id="e18ac-150">**Things to look out for**:</span></span>

- <span data-ttu-id="e18ac-151">封鎖的文字不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="e18ac-151">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="e18ac-152">當使用者輸入封鎖的單字時，群組用戶端將會以封鎖的字詞顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="e18ac-152">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="e18ac-153">使用的封鎖字中沒有字元限制。</span><span class="sxs-lookup"><span data-stu-id="e18ac-153">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="e18ac-154">5000個字的限制可設為封鎖字。</span><span class="sxs-lookup"><span data-stu-id="e18ac-154">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="e18ac-155">管理員覆寫</span><span class="sxs-lookup"><span data-stu-id="e18ac-155">Admin override</span></span>

<span data-ttu-id="e18ac-156">選擇性管理員會從這些原則中免除所有群組的工作負載和端點，讓他們可以使用這些封鎖的字和其所需的命名慣例來建立群組。</span><span class="sxs-lookup"><span data-stu-id="e18ac-156">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="e18ac-157">以下是免除群組命名原則之系統管理員角色的清單。</span><span class="sxs-lookup"><span data-stu-id="e18ac-157">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="e18ac-158">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="e18ac-158">Global admin</span></span>

- <span data-ttu-id="e18ac-159">合作夥伴第1層支援</span><span class="sxs-lookup"><span data-stu-id="e18ac-159">Partner Tier 1 Support</span></span>

- <span data-ttu-id="e18ac-160">合作夥伴第2層支援</span><span class="sxs-lookup"><span data-stu-id="e18ac-160">Partner Tier 2 Support</span></span>

- <span data-ttu-id="e18ac-161">使用者帳戶管理員</span><span class="sxs-lookup"><span data-stu-id="e18ac-161">User account admin</span></span>

- <span data-ttu-id="e18ac-162">目錄編寫者</span><span class="sxs-lookup"><span data-stu-id="e18ac-162">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="e18ac-163">如何設定命名原則</span><span class="sxs-lookup"><span data-stu-id="e18ac-163">How to set up the naming policy</span></span>

<span data-ttu-id="e18ac-164">若要設定命名原則：</span><span class="sxs-lookup"><span data-stu-id="e18ac-164">To set up a naming policy:</span></span>

1. <span data-ttu-id="e18ac-165">在[Azure Active Directory](https://aad.portal.azure.com)的 [**管理**] 下，按一下 [**群組**]。</span><span class="sxs-lookup"><span data-stu-id="e18ac-165">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="e18ac-166">在 [**設定**] 底下，按一下 [**命名原則**]。</span><span class="sxs-lookup"><span data-stu-id="e18ac-166">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="e18ac-167">選擇 [**群組命名原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e18ac-167">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="e18ac-168">在 [**目前原則**] 底下，選擇您是否要要求前置詞或尾碼或兩者，然後選取適當的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e18ac-168">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="e18ac-169">選擇每一行的**屬性**及**字串**，然後指定屬性或字串。</span><span class="sxs-lookup"><span data-stu-id="e18ac-169">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="e18ac-170">當您已新增所需的首碼和尾碼後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e18ac-170">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Azure Active Directory 中群組命名原則設定的螢幕擷取畫面](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> <span data-ttu-id="e18ac-172">StaffHub 小組不遵循命名原則，但底層的 Office 365 群組卻這麼做。</span><span class="sxs-lookup"><span data-stu-id="e18ac-172">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="e18ac-173">StaffHub 小組名稱不會套用首碼和尾碼，也不會檢查自訂的封鎖字。</span><span class="sxs-lookup"><span data-stu-id="e18ac-173">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="e18ac-174">但 StaffHub 會套用首碼和尾碼，並移除基礎 Office 365 群組中封鎖的字。</span><span class="sxs-lookup"><span data-stu-id="e18ac-174">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="e18ac-175">更多有關命名原則的文章</span><span class="sxs-lookup"><span data-stu-id="e18ac-175">More articles on naming policy</span></span>

[<span data-ttu-id="e18ac-176">在 Azure Active Directory 中強制執行 Office 365 群組的命名原則</span><span class="sxs-lookup"><span data-stu-id="e18ac-176">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="e18ac-177">用於設定群組設定的 Azure Active Directory Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e18ac-177">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
