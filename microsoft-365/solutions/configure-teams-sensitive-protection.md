---
title: 為團隊設定高敏感性資料保護
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: 了解如何為團隊部署高敏感性資料保護。
ms.openlocfilehash: 3c68e6690d9fdab28a5dd1369876bec5b3fd9bc7
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528191"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="dea7b-103">為團隊設定高敏感性資料保護</span><span class="sxs-lookup"><span data-stu-id="dea7b-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="dea7b-104">在本文中，我們將說明如何為團隊設定敏感度層級的保護。</span><span class="sxs-lookup"><span data-stu-id="dea7b-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="dea7b-105">在按照本文所述的步驟操作之前，請確定您已完成[為團隊部署基本保護](configure-teams-baseline-protection.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="dea7b-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="dea7b-106">敏感性層級可提供基準層所未提供的下列額外保護：</span><span class="sxs-lookup"><span data-stu-id="dea7b-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="dea7b-107">適用於團隊的敏感度標籤可讓您開啟或關閉來賓共用，並將未受管理裝置的 SharePoint 內容存取權限制為僅限網頁。</span><span class="sxs-lookup"><span data-stu-id="dea7b-107">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices.</span></span> <span data-ttu-id="dea7b-108">此標籤也可用來分類檔案。</span><span class="sxs-lookup"><span data-stu-id="dea7b-108">This label can also be used to classify files.</span></span>
- <span data-ttu-id="dea7b-109">限制更多的預設共用連結類型</span><span class="sxs-lookup"><span data-stu-id="dea7b-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="dea7b-110">只有團隊擁有者可以建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="dea7b-110">Only team owners can create private channels.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="dea7b-111">來賓共用</span><span class="sxs-lookup"><span data-stu-id="dea7b-111">Guest sharing</span></span>

<span data-ttu-id="dea7b-112">視貴公司的業務性質而定，您不一定會想要為包含敏感性資料的團隊啟用來賓共用。</span><span class="sxs-lookup"><span data-stu-id="dea7b-112">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="dea7b-113">如果您打算在團隊內與組織外的人員共同作業，建議您啟用來賓共用。</span><span class="sxs-lookup"><span data-stu-id="dea7b-113">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="dea7b-114">Microsoft 365 有各種安全性與合規性功能可協助您安全地共用敏感內容。</span><span class="sxs-lookup"><span data-stu-id="dea7b-114">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="dea7b-115">一般來說，這個選項的安全性高過直接用電子郵件將內容傳送給組織外的人員。</span><span class="sxs-lookup"><span data-stu-id="dea7b-115">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="dea7b-116">如需如何安全地與來賓共用的詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="dea7b-116">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="dea7b-117">在與組織外的人員共用檔案時，限制資訊意外暴露</span><span class="sxs-lookup"><span data-stu-id="dea7b-117">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="dea7b-118">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="dea7b-118">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="dea7b-119">為了允許或封鎖來賓共用，我們會使用敏感度標籤 (適用於團隊) 和網站層級共用控制 (適用於相關聯的 SharePoint 網站) 的組合，後面會有這兩種機制的討論。</span><span class="sxs-lookup"><span data-stu-id="dea7b-119">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="dea7b-120">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="dea7b-120">Sensitivity labels</span></span>

<span data-ttu-id="dea7b-121">為了獲得敏感度層級的保護，我們會使用敏感度標籤來分類團隊。</span><span class="sxs-lookup"><span data-stu-id="dea7b-121">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="dea7b-122">此標籤也可用來分類此團隊或其他團隊中的個別檔案，或是其他檔案位置 (例如 SharePoint 或 OneDrive) 中的個別檔案。</span><span class="sxs-lookup"><span data-stu-id="dea7b-122">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="dea7b-123">首先，您必須為 Teams 啟用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="dea7b-123">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="dea7b-124">如需詳細資訊，請參閱[使用敏感度標籤來保護 Microsoft Teams、Office 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="dea7b-124">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) for details.</span></span>

<span data-ttu-id="dea7b-125">如果組織已部署敏感度標籤，請考慮這個標籤與整體標籤策略的配合程度。</span><span class="sxs-lookup"><span data-stu-id="dea7b-125">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="dea7b-126">您可以視需要變更名稱或設定，以符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="dea7b-126">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="dea7b-127">在為 Teams 啟用敏感度標籤後，下一步是建立標籤。</span><span class="sxs-lookup"><span data-stu-id="dea7b-127">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="dea7b-128">若要建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="dea7b-128">To create a sensitivity label</span></span>
1. <span data-ttu-id="dea7b-129">開啟 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="dea7b-129">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="dea7b-130">在 [解決方案]\*\*\*\* 底下，按一下 [資訊保護]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-130">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="dea7b-131">按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-131">Click **Create a label**.</span></span>
4. <span data-ttu-id="dea7b-132">為標籤命名。</span><span class="sxs-lookup"><span data-stu-id="dea7b-132">Give the label a name.</span></span> <span data-ttu-id="dea7b-133">我們建議命名為**敏感度**，但如果有已經使用的名稱，則可以選擇不同名稱。</span><span class="sxs-lookup"><span data-stu-id="dea7b-133">We suggest **sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="dea7b-134">新增工具提示，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-134">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="dea7b-135">在 [加密]\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-135">On the **Encryption** page, click **Next**.</span></span>
7. <span data-ttu-id="dea7b-136">如果您想要將頁首、頁尾或浮水印自動新增至以此標籤分類的檔案，請在 [內容標記]\*\*\*\* 頁面上開啟內容標記。</span><span class="sxs-lookup"><span data-stu-id="dea7b-136">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
8. <span data-ttu-id="dea7b-137">在 [網站和群組設定]\*\*\*\* 頁面上，將 [網站和群組設定]\*\*\*\* 設為 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-137">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
9. <span data-ttu-id="dea7b-138">在 [Office 365 群組連線小組網站隱私權]\*\*\*\* 下拉式清單中，選擇 [私人 - 只有成員可以存取網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-138">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
10. <span data-ttu-id="dea7b-139">如果您想要允許來賓存取，請選取 [讓 Office 365 群組擁有者將組織外部人員新增到群組]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dea7b-139">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
11. <span data-ttu-id="dea7b-140">在 [未受管理的裝置]\*\*\*\* 下，選擇 [僅允許受限的 Web 存取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-140">Under **Unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
12. <span data-ttu-id="dea7b-141">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-141">Click **Next**.</span></span>
13. <span data-ttu-id="dea7b-142">在 [Office 應用程式的自動加上標籤]\*\*\*\* 頁面上按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-142">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
14. <span data-ttu-id="dea7b-143">按一下 [提交]\*\*\*\*，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-143">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="dea7b-144">在建立標籤完成後，您必須將標籤發佈給將使用該標籤的使用者。</span><span class="sxs-lookup"><span data-stu-id="dea7b-144">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="dea7b-145">為了獲得敏感度保護，我們會將標籤提供給所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="dea7b-145">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="dea7b-146">您可以在 [資訊保護]\*\*\*\* 頁面的 [標籤原則]\*\*\*\* 索引標籤上發佈 Microsoft 365 合規性中心的標籤。</span><span class="sxs-lookup"><span data-stu-id="dea7b-146">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="dea7b-147">如果您有適用於所有使用者的現有原則，請將這個標籤新增至該原則。</span><span class="sxs-lookup"><span data-stu-id="dea7b-147">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="dea7b-148">如果您需要建立新原則，請參閱[建立標籤原則來發佈敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="dea7b-148">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="dea7b-149">建立團隊</span><span class="sxs-lookup"><span data-stu-id="dea7b-149">Create a team</span></span>

<span data-ttu-id="dea7b-150">我們會在與團隊相關聯的 SharePoint 網站中進一步設定敏感度案例，因此下一步是建立團隊。</span><span class="sxs-lookup"><span data-stu-id="dea7b-150">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="dea7b-151">為敏感性資訊建立團隊</span><span class="sxs-lookup"><span data-stu-id="dea7b-151">To create a team for sensitive information</span></span>
1. <span data-ttu-id="dea7b-152">在 Teams 中，按一下應用程式左側的 [團隊]\*\*\*\*，然後按一下團隊清單底部的 [加入或建立團隊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-152">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="dea7b-153">按一下 [建立團隊]\*\*\*\* (左上角的第一張卡片)。</span><span class="sxs-lookup"><span data-stu-id="dea7b-153">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="dea7b-154">選擇 [從頭建立團隊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-154">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="dea7b-155">在 [敏感度]\*\*\*\* 清單中，選擇您剛才建立的 [敏感度]\*\*\*\* 標籤。</span><span class="sxs-lookup"><span data-stu-id="dea7b-155">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="dea7b-156">在 [隱私權]\*\*\*\* 下，按一下 [私人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-156">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="dea7b-157">輸入團隊的名稱，然後按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-157">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="dea7b-158">將使用者新增至團隊，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-158">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="dea7b-159">私人頻道設定</span><span class="sxs-lookup"><span data-stu-id="dea7b-159">Private channel settings</span></span>

<span data-ttu-id="dea7b-160">在這一層中，我們會限制只有團隊擁有者能夠建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="dea7b-160">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="dea7b-161">若要限制私人頻道的建立</span><span class="sxs-lookup"><span data-stu-id="dea7b-161">To restrict private channel creation</span></span>
1. <span data-ttu-id="dea7b-162">在該團隊中，按一下 [更多選項]\*\*\*\*，然後按一下 [管理團隊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-162">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="dea7b-163">在 [設定]\*\*\*\* 索引標籤上展開 [成員權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-163">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="dea7b-164">清除 [允許成員建立私人頻道]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dea7b-164">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="dea7b-165">您也可以使用[團隊原則](https://docs.microsoft.com/MicrosoftTeams/teams-policies)來控制可以建立私人頻道的人員。</span><span class="sxs-lookup"><span data-stu-id="dea7b-165">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="dea7b-166">SharePoint 設定</span><span class="sxs-lookup"><span data-stu-id="dea7b-166">SharePoint settings</span></span>

<span data-ttu-id="dea7b-167">每次使用敏感度標籤建立新的團隊時，都要在 SharePoint 中進行兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="dea7b-167">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="dea7b-168">在 SharePoint 系統管理中心內更新網站的來賓共用設定，使其符合您在建立標籤時所選擇的設定，並將預設的共用連結更新為*特定人員*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-168">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="dea7b-169">更新網站本身的網站共用設定以防止成員共用網站。</span><span class="sxs-lookup"><span data-stu-id="dea7b-169">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-guest-sharing-settings"></a><span data-ttu-id="dea7b-170">網站的來賓共用設定</span><span class="sxs-lookup"><span data-stu-id="dea7b-170">Site guest sharing settings</span></span>

<span data-ttu-id="dea7b-171">您在建立標籤時所選擇的來賓共用設定 (這只會影響團隊成員資格) 應符合相關聯 SharePoint 網站的來賓共用設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dea7b-171">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="dea7b-172">標籤設定</span><span class="sxs-lookup"><span data-stu-id="dea7b-172">Label setting</span></span>|<span data-ttu-id="dea7b-173">SharePoint 網站設定</span><span class="sxs-lookup"><span data-stu-id="dea7b-173">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="dea7b-174">已選取 [讓 Office 365 群組擁有者將組織外部人員新增到群組]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="dea7b-174">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="dea7b-175">[新的及現有的來賓]\*\*\*\* (新團隊的預設值)</span><span class="sxs-lookup"><span data-stu-id="dea7b-175">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="dea7b-176">未選取 [讓 Office 365 群組擁有者將組織外部人員新增到群組]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="dea7b-176">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="dea7b-177">[只有貴組織中的人員]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="dea7b-177">**Only people in your organization**</span></span>|

<span data-ttu-id="dea7b-178">若要更新網站設定</span><span class="sxs-lookup"><span data-stu-id="dea7b-178">To update site settings</span></span>
1. <span data-ttu-id="dea7b-179">開啟 [SharePoint 系統管理中心][](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="dea7b-179">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="dea7b-180">在 [網站]\*\*\*\* 底下，按一下 [使用中網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-180">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="dea7b-181">按一下與團隊相關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="dea7b-181">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="dea7b-182">在 [原則]\*\*\*\* 索引標籤的 [外部共用]\*\*\*\* 下，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-182">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="dea7b-183">如果您在建立敏感度標籤時允許來賓共用，請確定您已選取 [新的及現有的來賓]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-183">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="dea7b-184">如果您在建立標籤時未允許共用，請選擇 [只有貴組織中的人員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-184">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="dea7b-185">在 [預設的共用連結類型] 底下，清除 [與組織層級設定相同]\*\*\*\* 核取方塊，然後選取 [特定人員 (只有使用者指定的人)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-185">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
7. <span data-ttu-id="dea7b-186">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-186">Click **Save**.</span></span>

<span data-ttu-id="dea7b-187">如果您想要將此編寫為團隊建立程序的一部分，則可以使用 [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) 並搭配下列參數：</span><span class="sxs-lookup"><span data-stu-id="dea7b-187">If you want to script this as part of your team creation process, you can use [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) with the following parameters:</span></span>

- <span data-ttu-id="dea7b-188">`-SharingCapability Disabled`，以關閉來賓共用 (預設為開啟)</span><span class="sxs-lookup"><span data-stu-id="dea7b-188">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="dea7b-189">`-DefaultSharingLinkType Internal`，以將預設共用連結變更為 [特定人員]\*\*</span><span class="sxs-lookup"><span data-stu-id="dea7b-189">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

#### <a name="private-channels"></a><span data-ttu-id="dea7b-190">私人頻道</span><span class="sxs-lookup"><span data-stu-id="dea7b-190">Private channels</span></span>

<span data-ttu-id="dea7b-191">如果您在團隊中新增私人頻道，則每個私人頻道都會使用預設的共用設定建立一個新的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="dea7b-191">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="dea7b-192">這些網站不會顯示在 SharePoint 系統管理中心內，因此您必須使用 Set-SPOSite PowerShell Cmdlet 來更新來賓共用設定。</span><span class="sxs-lookup"><span data-stu-id="dea7b-192">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="dea7b-193">網站共用設定</span><span class="sxs-lookup"><span data-stu-id="dea7b-193">Site sharing settings</span></span>

<span data-ttu-id="dea7b-194">為了協助確保 SharePoint 網站不會與非小組成員的人員共用，我們將這種共用功能限制為只有擁有者能使用。</span><span class="sxs-lookup"><span data-stu-id="dea7b-194">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="dea7b-195">若要設定僅限擁有者使用的網站共用功能</span><span class="sxs-lookup"><span data-stu-id="dea7b-195">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="dea7b-196">在 Teams 中，瀏覽至所要更新團隊的 [一般]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dea7b-196">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="dea7b-197">在小組的工具列中，按一下 [檔案]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-197">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="dea7b-198">按一下省略符號，然後按一下 [在 SharePoint 中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-198">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="dea7b-199">在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-199">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="dea7b-200">在 [網站權限] 窗格的 [共用設定]\*\*\*\* 之下，按一下 [變更共用設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-200">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="dea7b-201">在 [共用權限]\*\*\*\* 底下，選擇 [網站擁有者和成員，以及擁有編輯權限的人員可以共用檔案與資料夾，但只有網站擁有者可以共用網站]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea7b-201">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="dea7b-202">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dea7b-202">See Also</span></span>

[<span data-ttu-id="dea7b-203">建立及設定敏感度標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="dea7b-203">Create and configure sensitivity labels and their policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)


