---
title: 部署三種檔案保護層級的小組
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 使用 Microsoft Teams 建立和設定以不同層級為其檔案提供資訊保護的小組。
ms.openlocfilehash: 3b90a1b084f7cd7e56d1d6448d74a7d2c2469a4d
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971821"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="39d02-103">部署三種檔案保護層級的小組</span><span class="sxs-lookup"><span data-stu-id="39d02-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="39d02-104">您可以使用本文中的步驟，來設計及部署基準、敏感和高度機密的小組。</span><span class="sxs-lookup"><span data-stu-id="39d02-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="39d02-105">如需這三種保護層級的詳細資訊，請參閱[在 Microsoft Teams 中保護檔案](secure-files-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="39d02-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="39d02-106">基準小組</span><span class="sxs-lookup"><span data-stu-id="39d02-106">Baseline teams</span></span>

<span data-ttu-id="39d02-107">基準保護包含公開和私人小組。</span><span class="sxs-lookup"><span data-stu-id="39d02-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="39d02-108">公開小組可供組織中的任何人探索及存取。</span><span class="sxs-lookup"><span data-stu-id="39d02-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="39d02-109">私人網站僅供與小組關聯的 Office 365 群組成員探索及存取。</span><span class="sxs-lookup"><span data-stu-id="39d02-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team.</span></span> <span data-ttu-id="39d02-110">這兩種類型的小組都可讓成員與其他人共用網站。</span><span class="sxs-lookup"><span data-stu-id="39d02-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="39d02-111">公用</span><span class="sxs-lookup"><span data-stu-id="39d02-111">Public</span></span>

<span data-ttu-id="39d02-112">依照[本文](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)中的指示操作，以建立具有公用存取和權限的基準小組。</span><span class="sxs-lookup"><span data-stu-id="39d02-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with public access and permissions.</span></span>

<span data-ttu-id="39d02-113">以下是產生的組態。</span><span class="sxs-lookup"><span data-stu-id="39d02-113">Here is your resulting configuration.</span></span>

![公開小組的基準層級保護。](../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="39d02-115">私人</span><span class="sxs-lookup"><span data-stu-id="39d02-115">Private</span></span>

<span data-ttu-id="39d02-116">依照[本文](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)中的指示操作，以建立具有私用存取和權限的基準小組。</span><span class="sxs-lookup"><span data-stu-id="39d02-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with private access and permissions.</span></span>

<span data-ttu-id="39d02-117">以下是產生的組態。</span><span class="sxs-lookup"><span data-stu-id="39d02-117">Here is your resulting configuration.</span></span>

![私人小組的基準層級保護。](../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="39d02-119">敏感小組</span><span class="sxs-lookup"><span data-stu-id="39d02-119">Sensitive teams</span></span>

<span data-ttu-id="39d02-120">對於敏感小組，您必須先[建立私人小組](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)。</span><span class="sxs-lookup"><span data-stu-id="39d02-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="39d02-121">接著，您必須設定基礎 SharePoint 網站以防止小組成員共用。</span><span class="sxs-lookup"><span data-stu-id="39d02-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="39d02-122">在小組的工具列中，按一下 [檔案]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="39d02-123">按一下省略符號，然後按一下 [在 SharePoint 中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="39d02-124">在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="39d02-125">在 [網站權限]\*\*\*\* 窗格的 [共用設定]\*\*\*\* 之下，按一下 [變更共用設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="39d02-126">在 [共用權限]\*\*\*\* 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="39d02-127">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="39d02-127">Here is your resulting configuration.</span></span>

![小組的敏感性保護。](../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="39d02-129">高度機密小組</span><span class="sxs-lookup"><span data-stu-id="39d02-129">Highly confidential teams</span></span>

<span data-ttu-id="39d02-130">對於高度機密小組，您必須先[建立私人小組](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)。</span><span class="sxs-lookup"><span data-stu-id="39d02-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="39d02-131">接著，您必須設定基礎 SharePoint 網站，以防止小組成員共用及非小組成員要求存取。</span><span class="sxs-lookup"><span data-stu-id="39d02-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="39d02-132">在小組的工具列中，按一下 [檔案]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="39d02-133">按一下省略符號，然後按一下 [在 SharePoint 中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="39d02-134">在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="39d02-135">在 [網站權限]\*\*\*\* 窗格的 [共用設定]\*\*\*\* 之下，按一下 [變更共用設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="39d02-136">在 [共用權限]\*\*\*\* 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="39d02-137">關閉 [允許存取要求]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39d02-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="39d02-138">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="39d02-138">Here is your resulting configuration.</span></span>

![小組的高度機密保護。](../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="39d02-140">下一步</span><span class="sxs-lookup"><span data-stu-id="39d02-140">Next step</span></span>

[<span data-ttu-id="39d02-141">使用保留標籤和 DLP 保護小組中的檔案</span><span class="sxs-lookup"><span data-stu-id="39d02-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="39d02-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="39d02-142">See also</span></span>

[<span data-ttu-id="39d02-143">在 Microsoft Teams 中保護檔案</span><span class="sxs-lookup"><span data-stu-id="39d02-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

[<span data-ttu-id="39d02-144">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="39d02-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
