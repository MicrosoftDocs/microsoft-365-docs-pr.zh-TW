---
title: 在 Microsoft Defender for Endpoint 中建立及管理裝置群組
description: 透過 confiring 在群組上套用的規則，建立裝置群組並設定其上的自動修正層級。
keywords: 裝置群組、群組、修正、層級、規則、aad 群組、角色、指派、排名
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: acd24e5c87a74bbb32835ec170a121c5c0b6bb33
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860300"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="f1f84-104">建立及管理裝置群組</span><span class="sxs-lookup"><span data-stu-id="f1f84-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f1f84-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f1f84-105">**Applies to:**</span></span>
- <span data-ttu-id="f1f84-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f1f84-106">Azure Active Directory</span></span>
- <span data-ttu-id="f1f84-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="f1f84-107">Office 365</span></span>

> <span data-ttu-id="f1f84-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="f1f84-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f1f84-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f1f84-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f1f84-110">在企業案例中，一般會為安全性運作小組指派一組裝置。</span><span class="sxs-lookup"><span data-stu-id="f1f84-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="f1f84-111">這些裝置會根據一組屬性（如其網域、電腦名稱稱或指定的標記）組合在一起。</span><span class="sxs-lookup"><span data-stu-id="f1f84-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="f1f84-112">在 Microsoft Defender for Endpoint 中，您可以建立裝置群組，並使用這些群組進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="f1f84-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="f1f84-113">將相關警示和資料的存取許可權制為具有[指派 RBAC 角色](rbac.md)的特定 Azure AD 使用者群組</span><span class="sxs-lookup"><span data-stu-id="f1f84-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="f1f84-114">設定不同裝置組的不同自動修復設定</span><span class="sxs-lookup"><span data-stu-id="f1f84-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="f1f84-115">在自動調查期間指派要套用的特定修正層級</span><span class="sxs-lookup"><span data-stu-id="f1f84-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="f1f84-116">在調查中，請使用 **群組** 篩選，將 [**裝置] 清單** 篩選為 [僅限特定裝置群組]。</span><span class="sxs-lookup"><span data-stu-id="f1f84-116">In an investigation, filter the **Devices list** to just specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="f1f84-117">您可以在以角色為基礎的 access (RBAC) 中建立裝置群組，以控制誰可以採取特定動作或透過將裝置群組指派 (s) 指派給使用者群組，以控制誰可以採取特定動作或查看資訊。</span><span class="sxs-lookup"><span data-stu-id="f1f84-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="f1f84-118">如需詳細資訊，請參閱 [使用以角色為基礎的存取控制管理入口網站存取](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="f1f84-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="f1f84-119">如需 RBAC 應用程式的完整外觀，請參閱： [您的 SOC 是以 rbac 執行平整](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)。</span><span class="sxs-lookup"><span data-stu-id="f1f84-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="f1f84-120">在建立裝置群組的過程中，您會：</span><span class="sxs-lookup"><span data-stu-id="f1f84-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="f1f84-121">設定該群組的自動修正層級。</span><span class="sxs-lookup"><span data-stu-id="f1f84-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="f1f84-122">如需修正層級的詳細資訊，請參閱 [使用自動調查調查和修正威脅](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="f1f84-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="f1f84-123">指定符合規則，判斷哪個裝置群組屬於根據裝置名稱、網域、標籤和 OS 平臺的群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="f1f84-124">如果裝置也符合其他群組，它只會新增至最高排名的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-124">If a device is also matched to other groups, it is added only to the highest ranked device group.</span></span>
- <span data-ttu-id="f1f84-125">選取應該具有裝置群組存取權的 Azure AD 使用者群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="f1f84-126">在建立其他群組之後，對此裝置群組進行排名。</span><span class="sxs-lookup"><span data-stu-id="f1f84-126">Rank the device group relative to other groups after it is created.</span></span>

>[!NOTE]
><span data-ttu-id="f1f84-127">如果您未指派任何 Azure AD 群組，則所有使用者都可以存取裝置群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="f1f84-128">建立裝置群組</span><span class="sxs-lookup"><span data-stu-id="f1f84-128">Create a device group</span></span>

1. <span data-ttu-id="f1f84-129">在功能窗格中，選取 [**設定**  >  **裝置群組**]。</span><span class="sxs-lookup"><span data-stu-id="f1f84-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="f1f84-130">按一下 [ **新增裝置群組**]。</span><span class="sxs-lookup"><span data-stu-id="f1f84-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="f1f84-131">輸入 [組名] 和 [自動化] 設定，並指定用來判斷哪些裝置屬於群組的符合規則。</span><span class="sxs-lookup"><span data-stu-id="f1f84-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="f1f84-132">請參閱 [自動調查的開始方式](automated-investigations.md#how-the-automated-investigation-starts)。</span><span class="sxs-lookup"><span data-stu-id="f1f84-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="f1f84-133">如果您想依組織單位群組裝置，您可以為群組從屬設定登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="f1f84-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="f1f84-134">如需裝置標記的詳細資訊，請參閱 [Create and manage device tags](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="f1f84-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="f1f84-135">預覽數個裝置，此規則將會符合此規則。</span><span class="sxs-lookup"><span data-stu-id="f1f84-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="f1f84-136">如果您對規則滿意，請按一下 [ **使用者存取** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f1f84-136">If you are satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="f1f84-137">指派可以存取您所建立之裝置群組的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f1f84-138">您只可將存取權授與指派給 RBAC 角色的 Azure AD 使用者群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="f1f84-139">按一下 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="f1f84-139">Click **Close**.</span></span> <span data-ttu-id="f1f84-140">設定變更。</span><span class="sxs-lookup"><span data-stu-id="f1f84-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="f1f84-141">管理裝置群組</span><span class="sxs-lookup"><span data-stu-id="f1f84-141">Manage device groups</span></span>

<span data-ttu-id="f1f84-142">您可以提升或降級裝置群組的排名，使其在比對的期間具有較高或較低的優先順序。</span><span class="sxs-lookup"><span data-stu-id="f1f84-142">You can promote or demote the rank of a device group so that it is given higher or lower priority during matching.</span></span> <span data-ttu-id="f1f84-143">當裝置與一個以上的群組相符時，它只會新增至最高排名的群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-143">When a device is matched to more than one group, it is added only to the highest ranked group.</span></span> <span data-ttu-id="f1f84-144">您也可以編輯和刪除群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-144">You can also edit and delete groups.</span></span>

>[!WARNING]
><span data-ttu-id="f1f84-145">刪除裝置群組可能會影響電子郵件通知規則。</span><span class="sxs-lookup"><span data-stu-id="f1f84-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="f1f84-146">如果已在電子郵件通知規則下設定裝置群組，它會從該規則中移除。</span><span class="sxs-lookup"><span data-stu-id="f1f84-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="f1f84-147">如果設備群組是為電子郵件通知設定的唯一群組，則會與裝置群組一起刪除電子郵件通知規則。</span><span class="sxs-lookup"><span data-stu-id="f1f84-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="f1f84-148">依預設，所有具有入口網站存取權的使用者皆可存取裝置群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="f1f84-149">您可以將 Azure AD 使用者群組指派給裝置群組，以變更預設行為。</span><span class="sxs-lookup"><span data-stu-id="f1f84-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="f1f84-150">不符合任何群組的裝置會新增至取消群組裝置 (預設) 群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-150">Devices that are not matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="f1f84-151">您無法變更此群組的排名或加以刪除。</span><span class="sxs-lookup"><span data-stu-id="f1f84-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="f1f84-152">不過，您可以變更此群組的修正層級，並定義可以存取此群組的 Azure AD 使用者群組。</span><span class="sxs-lookup"><span data-stu-id="f1f84-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="f1f84-153">對裝置群組設定套用變更可能需要數分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="f1f84-153">Applying changes to device group configuration may take up to several minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f1f84-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="f1f84-154">Related topics</span></span>

- [<span data-ttu-id="f1f84-155">使用以角色為基礎的存取控制來管理入口網站存取</span><span class="sxs-lookup"><span data-stu-id="f1f84-155">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="f1f84-156">建立及管理裝置標記</span><span class="sxs-lookup"><span data-stu-id="f1f84-156">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="f1f84-157">使用 Graph API 取得租使用者群組的清單</span><span class="sxs-lookup"><span data-stu-id="f1f84-157">Get list of tenant device groups using Graph API</span></span>](https://docs.microsoft.com/graph/api/device-list-memberof)
