---
title: 為團隊設定高敏感性資料保護
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: 了解如何為團隊部署高敏感性資料保護。
ms.openlocfilehash: a3f715cb05ad1d5acf3c93c58959f12ebec46978
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788339"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="defc0-103">為團隊設定高敏感性資料保護</span><span class="sxs-lookup"><span data-stu-id="defc0-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="defc0-104">在本文中，我們將說明如何為團隊設定敏感度層級的保護。</span><span class="sxs-lookup"><span data-stu-id="defc0-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="defc0-105">在按照本文所述的步驟操作之前，請確定您已完成[為團隊部署基本保護](configure-teams-baseline-protection.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="defc0-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="defc0-106">敏感性層級可提供基準層所未提供的下列額外保護：</span><span class="sxs-lookup"><span data-stu-id="defc0-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="defc0-p102">適用於團隊的敏感度標籤可讓您開啟或關閉來賓共用，並將未受管理裝置的 SharePoint 內容存取權限制為僅限網頁。此標籤也可用來分類檔案。</span><span class="sxs-lookup"><span data-stu-id="defc0-p102">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices. This label can also be used to classify files.</span></span>
- <span data-ttu-id="defc0-109">限制更多的預設共用連結類型</span><span class="sxs-lookup"><span data-stu-id="defc0-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="defc0-110">只有小組擁有者可以建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="defc0-110">Only team owners can create private channels.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="defc0-111">影片示範</span><span class="sxs-lookup"><span data-stu-id="defc0-111">Video demonstration</span></span>

<span data-ttu-id="defc0-112">請觀看這段影片，以取得本文所述程序的逐步解說。</span><span class="sxs-lookup"><span data-stu-id="defc0-112">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a><span data-ttu-id="defc0-113">來賓共用</span><span class="sxs-lookup"><span data-stu-id="defc0-113">Guest sharing</span></span>

<span data-ttu-id="defc0-114">視貴公司的業務性質而定，您不一定會想要為包含敏感性資料的團隊啟用來賓共用。</span><span class="sxs-lookup"><span data-stu-id="defc0-114">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="defc0-115">如果您打算在團隊內與組織外的人員共同作業，建議您啟用來賓共用。</span><span class="sxs-lookup"><span data-stu-id="defc0-115">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="defc0-116">Microsoft 365 有各種安全性與合規性功能可協助您安全地共用敏感內容。</span><span class="sxs-lookup"><span data-stu-id="defc0-116">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="defc0-117">一般來說，這個選項的安全性高過直接用電子郵件將內容傳送給組織外的人員。</span><span class="sxs-lookup"><span data-stu-id="defc0-117">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="defc0-118">如需如何安全地與來賓共用的詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="defc0-118">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="defc0-119">在與組織外的人員共用檔案時，限制資訊意外暴露</span><span class="sxs-lookup"><span data-stu-id="defc0-119">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="defc0-120">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="defc0-120">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="defc0-121">為了允許或封鎖來賓共用，我們會使用敏感度標籤 (適用於小組) 和網站層級共用控制 (適用於相關聯的 SharePoint 網站) 的組合，後面會有這兩種機制的討論。</span><span class="sxs-lookup"><span data-stu-id="defc0-121">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="defc0-122">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="defc0-122">Sensitivity labels</span></span>

<span data-ttu-id="defc0-123">為了獲得敏感度層級的保護，我們會使用敏感度標籤來分類團隊。</span><span class="sxs-lookup"><span data-stu-id="defc0-123">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="defc0-124">此標籤也可用來分類此團隊或其他團隊中的個別檔案，或是其他檔案位置 (例如 SharePoint 或 OneDrive) 中的個別檔案。</span><span class="sxs-lookup"><span data-stu-id="defc0-124">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="defc0-125">首先，您必須為 Teams 啟用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="defc0-125">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="defc0-126">如需詳細資訊，請參閱[使用敏感度標籤來保護 Microsoft Teams、Office 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="defc0-126">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="defc0-127">如果組織已部署敏感度標籤，請考慮這個標籤與整體標籤策略的配合程度。</span><span class="sxs-lookup"><span data-stu-id="defc0-127">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="defc0-128">您可以視需要變更名稱或設定，以符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="defc0-128">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="defc0-129">在為 Teams 啟用敏感度標籤後，下一步是建立標籤。</span><span class="sxs-lookup"><span data-stu-id="defc0-129">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="defc0-130">建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="defc0-130">To create a sensitivity label</span></span>
1. <span data-ttu-id="defc0-131">開啟 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="defc0-131">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="defc0-132">在 **[解決方案]** 底下，按一下 **[資訊保護]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-132">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="defc0-133">按一下 **[建立標籤]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-133">Click **Create a label**.</span></span>
4. <span data-ttu-id="defc0-134">為標籤命名。</span><span class="sxs-lookup"><span data-stu-id="defc0-134">Give the label a name.</span></span> <span data-ttu-id="defc0-135">我們建議命名為 **敏感度**，但如果該名稱已在使用中，則可以選擇不同名稱。</span><span class="sxs-lookup"><span data-stu-id="defc0-135">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="defc0-136">新增顯示名稱和描述，然後按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-136">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="defc0-137">在 [定義此標籤頁面的範圍 **]** 上，選取 [檔案和電子郵件 **]** 和 [群組和網站 **]**，然後按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-137">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="defc0-138">在 [選擇檔案和電子郵件的保護設定 **]** 頁面上，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-138">On the **Choose protection settings for files and emails** page, click **Next**.</span></span>
8. <span data-ttu-id="defc0-139">在 [自動為檔案和電子郵件加上標籤 *]* 頁面上按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-139">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
9. <span data-ttu-id="defc0-140">在 [定義群組及網站的保護設定 **]** 頁面上，選取 [隱私權和外部使用者存取權設定 **]** 和 [裝置存取權和外部共用設定 **]**，然後按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-140">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
10. <span data-ttu-id="defc0-141">在 [定義隱私權和外部使用者存取權設定 **]** 頁面上，於 [隱私權 **]** 底下選取 [私人 **]** 選項。</span><span class="sxs-lookup"><span data-stu-id="defc0-141">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
11. <span data-ttu-id="defc0-142">如果您想要允許來賓存取，請在 [外部使用者存取權 **]** 底下，選取 [讓 Microsoft 365 群組擁有者將貴組織外部人員新增到群組做為來賓 **]** 群組。</span><span class="sxs-lookup"><span data-stu-id="defc0-142">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
12. <span data-ttu-id="defc0-143">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-143">Click **Next**.</span></span>
13. <span data-ttu-id="defc0-144">在 [定義外部共用和裝置存取權設定 **]** 頁面上，選取 [從已套用標籤的 SharePoint 網站控制外部共用 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-144">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
14. <span data-ttu-id="defc0-145">如果您要允許來賓存取，在 [內容可以與誰共用 **]** 底下，選擇 [新的及現有的來賓 **]**，或如果您不要允許來賓存取，則選擇 [僅限組織中的人員 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-145">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
15. <span data-ttu-id="defc0-146">在 [存取未受管理的裝置 **]** 下，選擇 [允許受限的僅限 Web 存取 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-146">Under **Access from unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
16. <span data-ttu-id="defc0-147">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-147">Click **Next**.</span></span>
17. <span data-ttu-id="defc0-148">在 [為資料庫資料行自動加上標籤 **]** 頁面上，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-148">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
18. <span data-ttu-id="defc0-149">按一下 [建立標籤 **]**，然後按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-149">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="defc0-150">在建立好標籤後，您必須將標籤發佈給將使用該標籤的使用者。</span><span class="sxs-lookup"><span data-stu-id="defc0-150">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="defc0-151">為了獲得敏感度保護，我們會將標籤提供給所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="defc0-151">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="defc0-152">您可以在 **[資訊保護]** 頁面的 **[標籤原則]** 索引標籤上發佈 Microsoft 365 合規性中心的標籤。</span><span class="sxs-lookup"><span data-stu-id="defc0-152">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="defc0-153">如果您有適用於所有使用者的現有原則，請將這個標籤新增至該原則。</span><span class="sxs-lookup"><span data-stu-id="defc0-153">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="defc0-154">如果您需要建立新原則，請參閱[建立標籤原則來發佈敏感度標籤](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="defc0-154">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="defc0-155">建立團隊</span><span class="sxs-lookup"><span data-stu-id="defc0-155">Create a team</span></span>

<span data-ttu-id="defc0-156">我們會在與團隊相關聯的 SharePoint 網站中進一步設定敏感度案例，因此下一步是建立團隊。</span><span class="sxs-lookup"><span data-stu-id="defc0-156">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="defc0-157">為敏感性資訊建立團隊</span><span class="sxs-lookup"><span data-stu-id="defc0-157">To create a team for sensitive information</span></span>
1. <span data-ttu-id="defc0-158">在 Teams 中，按一下應用程式左側的 **[團隊]**，然後按一下團隊清單底部的 **[加入或建立團隊]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-158">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="defc0-159">按一下 **[建立團隊]** (左上角的第一張卡片)。</span><span class="sxs-lookup"><span data-stu-id="defc0-159">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="defc0-160">選擇 **[從頭建立團隊]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-160">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="defc0-161">在 **[敏感度]** 清單中，選擇您剛才建立的 **[敏感度]** 標籤。</span><span class="sxs-lookup"><span data-stu-id="defc0-161">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="defc0-162">在 **[隱私權]** 下，按一下 **[私人]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-162">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="defc0-163">輸入團隊的名稱，然後按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-163">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="defc0-164">將使用者新增至團隊，然後按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-164">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="defc0-165">私人頻道設定</span><span class="sxs-lookup"><span data-stu-id="defc0-165">Private channel settings</span></span>

<span data-ttu-id="defc0-166">在這一層中，我們會限制只有團隊擁有者能夠建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="defc0-166">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="defc0-167">限制私人頻道的建立</span><span class="sxs-lookup"><span data-stu-id="defc0-167">To restrict private channel creation</span></span>
1. <span data-ttu-id="defc0-168">在該團隊中，按一下 **[更多選項]**，然後按一下 **[管理團隊]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-168">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="defc0-169">在 **[設定]** 索引標籤上展開 **[成員權限]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-169">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="defc0-170">清除 **[允許成員建立私人頻道]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="defc0-170">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="defc0-171">您也可以使用[小組原則](/MicrosoftTeams/teams-policies)來控制可以建立私人頻道的人員。</span><span class="sxs-lookup"><span data-stu-id="defc0-171">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="defc0-172">SharePoint 設定</span><span class="sxs-lookup"><span data-stu-id="defc0-172">SharePoint settings</span></span>

<span data-ttu-id="defc0-173">每次使用敏感度標籤建立新的團隊時，都要在 SharePoint 中進行兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="defc0-173">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="defc0-174">在 SharePoint 系統管理中心更新網站的來賓共用設定，以將預設共用連結更新為 *特定人員*。</span><span class="sxs-lookup"><span data-stu-id="defc0-174">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="defc0-175">更新網站本身的網站共用設定以防止成員共用網站。</span><span class="sxs-lookup"><span data-stu-id="defc0-175">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="defc0-176">網站預設的共用連結設定</span><span class="sxs-lookup"><span data-stu-id="defc0-176">Site default sharing link settings</span></span>

<span data-ttu-id="defc0-177">若要更新網站預設的共用連結設定</span><span class="sxs-lookup"><span data-stu-id="defc0-177">To update the site default sharing link type</span></span>

1. <span data-ttu-id="defc0-178">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="defc0-178">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="defc0-179">在 **[網站]** 底下，按一下 **[使用中網站]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-179">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="defc0-180">按一下與小組相關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="defc0-180">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="defc0-181">在 **[原則]** 索引標籤的 **[外部共用]** 底下，按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-181">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="defc0-182">在 **[預設的共用連結類型] 底下，清除 [與組織層級設定相同]** 核取方塊，然後選取 **[特定人員 (只有使用者指定的人)]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-182">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
6. <span data-ttu-id="defc0-183">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-183">Click **Save**.</span></span>

<span data-ttu-id="defc0-184">如果您想要將此編寫為團隊建立程序的一部分，則可以使用 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) 並搭配下列 `-DefaultSharingLinkType Direct` 參數以變更 *特定人員* 的預設共用連結。</span><span class="sxs-lookup"><span data-stu-id="defc0-184">If you want to script this as part of your team creation process, you can use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) with the `-DefaultSharingLinkType Direct` parameter to change the default sharing link to *Specific people*.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="defc0-185">私人頻道</span><span class="sxs-lookup"><span data-stu-id="defc0-185">Private channels</span></span>

<span data-ttu-id="defc0-186">如果您在小組中新增私人頻道，則每個私人頻道都會使用預設的共用設定建立一個新的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="defc0-186">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="defc0-187">這些網站不會顯示在 SharePoint 系統管理中心內，因此您必須使用 Set-SPOSite PowerShell Cmdlet 來更新來賓共用設定。</span><span class="sxs-lookup"><span data-stu-id="defc0-187">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="defc0-188">網站共用設定</span><span class="sxs-lookup"><span data-stu-id="defc0-188">Site sharing settings</span></span>

<span data-ttu-id="defc0-189">為了協助確保 SharePoint 網站不會與非小組成員的人員共用，我們將這種共用功能限制為只有擁有者能使用。</span><span class="sxs-lookup"><span data-stu-id="defc0-189">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="defc0-190">若要設定僅限擁有者使用的網站共用功能</span><span class="sxs-lookup"><span data-stu-id="defc0-190">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="defc0-191">在 Teams 中，瀏覽至所要更新團隊的 **[一般]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="defc0-191">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="defc0-192">在小組的工具列中，按一下 **[檔案]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-192">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="defc0-193">按一下省略符號，然後按一下 **[在 SharePoint 中開啟]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-193">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="defc0-194">在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 **[網站權限]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-194">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="defc0-195">在 **[網站權限]** 窗格的 **[網站共用]** 下，按一下 **[變更成員可以使用的共用方式]**。</span><span class="sxs-lookup"><span data-stu-id="defc0-195">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="defc0-196">在 [共用權限] 底下，選擇 [網站擁有者和成員，以及擁有編輯權限的人員可以共用檔案與資料夾，但只有網站擁有者可以共用網站]，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="defc0-196">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="defc0-197">另請參閱</span><span class="sxs-lookup"><span data-stu-id="defc0-197">See Also</span></span>

[<span data-ttu-id="defc0-198">建立及設定敏感度標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="defc0-198">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
