---
title: 適用於高度管制資料的 Microsoft Teams
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立安全小組來儲存您最重要且最敏感的檔案。
ms.openlocfilehash: c4a7c724b6fbb4515deba1a207eea31902f822e0
ms.sourcegitcommit: 6dfa646b9de30336dedfd0cac7320c57ad74ae11
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37929218"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="bdc17-103">適用於高度管制資料的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bdc17-103">Teams for highly regulated data</span></span>

<span data-ttu-id="bdc17-104">本文提供在 Microsoft Teams 中設定私人小組的建議和步驟，讓您可以鎖定如聊天、會議和檔案等 Microsoft Teams 功能的存取權，僅供小組中 Office 365 群組的成員和擁有者使用。</span><span class="sxs-lookup"><span data-stu-id="bdc17-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="bdc17-105">除了 Office 365 群組基本的私用存取外，本文還說明如何針對儲存高度管制資料所需的額外安全性，設定基礎的私人 SharePoint 小組網站，此網站可透過小組頻道的 [檔案]\*\*\*\* 區段進行存取。</span><span class="sxs-lookup"><span data-stu-id="bdc17-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="bdc17-106">在此 SharePoint 小組網站中，您可以對檔案、頁面、共用行事曆、工作、筆記本和清單進行儲存和共同作業。</span><span class="sxs-lookup"><span data-stu-id="bdc17-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

>[!Note]
> <span data-ttu-id="bdc17-107">[這裡](teams-sharepoint-online-sites-highly-regulated-data.md)提供使用 SharePoint 的類似案例。</span><span class="sxs-lookup"><span data-stu-id="bdc17-107">A similar scenario using Microsoft Teams is [here](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
>

<span data-ttu-id="bdc17-108">針對高度管制資料，小組需要設定的元素有：</span><span class="sxs-lookup"><span data-stu-id="bdc17-108">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="bdc17-109">私人小組，具有對應的 Office 365 群組，群組中有擁有者和成員使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bdc17-109">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="bdc17-110">小組的基礎 SharePoint 網站需要的額外安全性有：</span><span class="sxs-lookup"><span data-stu-id="bdc17-110">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="bdc17-111">避免網站成員將存取權授與其他使用者。</span><span class="sxs-lookup"><span data-stu-id="bdc17-111">Prevents members of the site from granting access to others.</span></span>
  - <span data-ttu-id="bdc17-112">避免非網站成員要求網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="bdc17-112">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="bdc17-113">基礎 SharePoint 網站的 Office 365 保留標籤，可自動套用到網站上的新檔案，作為定義保留原則的預設方法。</span><span class="sxs-lookup"><span data-stu-id="bdc17-113">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="bdc17-114">資料外洩防護 (DLP) 原則，利用保留標籤封鎖使用者對組織外部共用或傳送檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-114">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="bdc17-115">Office 365 敏感度標籤或高度管制標籤的子標籤，已啟用加密且對小組的 Office 365 群組具有共同撰寫權限。</span><span class="sxs-lookup"><span data-stu-id="bdc17-115">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="bdc17-116">使用者可以從 Word、Excel 和 PowerPoint 的 [敏感度] 功能表列，將標籤或子標籤套用到儲存在小組中 [檔案]\*\*\*\* 區段的檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-116">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="bdc17-117">以下是使用敏感度標籤所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="bdc17-117">Here is the resulting configuration with a sensitivity label.</span></span>

![安全小組案例的組態](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<a name="poster"></a> <span data-ttu-id="bdc17-119">如需此案例的 1 頁式摘要，請參閱[適用於高度管制資料的 Teams 海報](./media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)。</span><span class="sxs-lookup"><span data-stu-id="bdc17-119">For a 1-page summary of this scenario, see the [Teams for highly regulated data poster](./media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="bdc17-120">[![適用於高度管制資料的 Teams 海報](././media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](./media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="bdc17-120">[![Teams for highly regulated data](././media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](./media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="bdc17-121">您也可以用 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) 格式下載此海報，以及用 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。</span><span class="sxs-lookup"><span data-stu-id="bdc17-121">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) or PowerPoint formats and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="bdc17-122">階段 1：針對高度管制資料設定小組</span><span class="sxs-lookup"><span data-stu-id="bdc17-122">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="bdc17-123">端對端的設定包括下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bdc17-123">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="bdc17-124">設定身分識別和裝置存取。</span><span class="sxs-lookup"><span data-stu-id="bdc17-124">Configure identity and device access.</span></span>
2. <span data-ttu-id="bdc17-125">建立私人小組。</span><span class="sxs-lookup"><span data-stu-id="bdc17-125">Create a private team.</span></span>
3. <span data-ttu-id="bdc17-126">設定基礎 SharePoint 網站的額外安全性。</span><span class="sxs-lookup"><span data-stu-id="bdc17-126">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="bdc17-127">建立保留標籤和 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="bdc17-127">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="bdc17-128">建立標籤或高度管制標籤的子標籤。</span><span class="sxs-lookup"><span data-stu-id="bdc17-128">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="bdc17-129">步驟 1：設定身分識別和裝置存取</span><span class="sxs-lookup"><span data-stu-id="bdc17-129">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="bdc17-130">若要保護小組及其基礎 SharePoint 網站的存取權，請確定您已設定[身分識別與裝置存取原則](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)和建議的 [SharePoint Online 存取原則](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="bdc17-130">To protect access to the team and its underlying SharePoint site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the recommended [SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="bdc17-131">步驟 2：建立私人小組</span><span class="sxs-lookup"><span data-stu-id="bdc17-131">Step 2: Create a private team</span></span>

<span data-ttu-id="bdc17-132">利用[以下指示](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)建立私人小組。</span><span class="sxs-lookup"><span data-stu-id="bdc17-132">Use [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private team.</span></span>

<span data-ttu-id="bdc17-133">當您建立私人小組時，預設權限如下：</span><span class="sxs-lookup"><span data-stu-id="bdc17-133">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="bdc17-134">小組的 Office 365 群組 (以下稱「小組群組」) 有群組擁有者和群組成員</span><span class="sxs-lookup"><span data-stu-id="bdc17-134">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="bdc17-135">針對小組的基礎 SharePoint 網站 (以下稱「小組網站」)：</span><span class="sxs-lookup"><span data-stu-id="bdc17-135">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="bdc17-136">網站集合系統管理員會設定為「小組群組」擁有者</span><span class="sxs-lookup"><span data-stu-id="bdc17-136">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="bdc17-137">針對「小組網站」：</span><span class="sxs-lookup"><span data-stu-id="bdc17-137">For the Team Site:</span></span> 
    - <span data-ttu-id="bdc17-138">「小組網站」擁有者的 SharePoint 群組 (具有「完全控制」權限層級) 會設定為「小組群組」擁有者</span><span class="sxs-lookup"><span data-stu-id="bdc17-138">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="bdc17-139">「小組網站」成員的 SharePoint 群組 (具有「編輯」權限層級) 會設定為「小組群組」成員</span><span class="sxs-lookup"><span data-stu-id="bdc17-139">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="bdc17-140">「小組網站」訪客的 SharePoint 群組 (具有「讀取」權限層級) 沒有群組或使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="bdc17-140">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="bdc17-141">以下是「小組網站」的預設權限。</span><span class="sxs-lookup"><span data-stu-id="bdc17-141">Here are the default permissions for the Team Site.</span></span>

![小組網站的預設權限](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="bdc17-143">如果您檢視 \<小組名稱> 擁有者的 SharePoint 群組的「編輯」權限層級，系統不會顯示 \<小組名稱> 擁有者。</span><span class="sxs-lookup"><span data-stu-id="bdc17-143">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="bdc17-144">所產生的權限允許：</span><span class="sxs-lookup"><span data-stu-id="bdc17-144">The resulting permissions allow:</span></span>

- <span data-ttu-id="bdc17-145">「小組群組」擁有者可以管理網站並對網站內容擁有完全控制的權限。</span><span class="sxs-lookup"><span data-stu-id="bdc17-145">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="bdc17-146">「小組群組」成員可以建立和編輯網站上的檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-146">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="bdc17-147">權限的維護與小組成員及擁有者的維護相同。</span><span class="sxs-lookup"><span data-stu-id="bdc17-147">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="bdc17-148">以下是目前所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="bdc17-148">Here’s the resulting configuration so far.</span></span>

![安全小組案例的組態步驟 2](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="bdc17-150">步驟 3：設定基礎 SharePoint 網站的額外安全性</span><span class="sxs-lookup"><span data-stu-id="bdc17-150">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="bdc17-151">從「小組網站」設定這些權限設定。</span><span class="sxs-lookup"><span data-stu-id="bdc17-151">From the Team Site, configure these permission settings.</span></span>

1. <span data-ttu-id="bdc17-152">在工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdc17-152">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="bdc17-153">在 [網站權限]\*\*\*\* 窗格的 [共用設定]\*\*\*\* 之下，按一下 [變更共用設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdc17-153">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="bdc17-154">在 [共用權限]\*\*\*\* 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdc17-154">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="bdc17-155">關閉 [允許存取要求]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdc17-155">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="bdc17-156">透過這些設定，「網站群組」成員要求「小組網站」存取權以與其他成員或非成員共用「小組網站」的功能將會停用。</span><span class="sxs-lookup"><span data-stu-id="bdc17-156">With these settings, the ability for Team Group members to share the Team Site with other members or for non-members to request access to the Team Site is disabled.</span></span>

<span data-ttu-id="bdc17-157">以下是目前所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="bdc17-157">Here’s the resulting configuration so far.</span></span>

![安全小組案例的組態步驟 3](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="bdc17-159">步驟 4：建立保留標籤和 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="bdc17-159">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="bdc17-160">利用[以下指示](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp)：</span><span class="sxs-lookup"><span data-stu-id="bdc17-160">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="bdc17-161">建立和發佈高度管制資料的保留標籤 (如有需要的話)。</span><span class="sxs-lookup"><span data-stu-id="bdc17-161">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="bdc17-162">針對步驟 1 中建立的保留標籤設定「小組網站」。</span><span class="sxs-lookup"><span data-stu-id="bdc17-162">Configure the Team Site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="bdc17-163">使用在步驟 2 中建立的保留標籤建立高度管制資料的 DLP 原則，封鎖使用者對組織外部傳送檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-163">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization.</span></span> <span data-ttu-id="bdc17-164">您也可以 [DLP 原則範本](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates)為基礎，針對其他要求設定原則，例如健康和金融業法規的要求。</span><span class="sxs-lookup"><span data-stu-id="bdc17-164">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="bdc17-165">以下是目前所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="bdc17-165">Here’s the resulting configuration so far.</span></span>

![安全小組案例的組態步驟 4](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="bdc17-167">步驟 5：建立標籤或高度管制標籤的子標籤</span><span class="sxs-lookup"><span data-stu-id="bdc17-167">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="bdc17-168">適用於高度管制資料的敏感度標籤可讓任何人套用至任何檔案，但是安全小組不同，安全小組需要自己的標籤或子標籤，使指派到的檔案都能：</span><span class="sxs-lookup"><span data-stu-id="bdc17-168">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="bdc17-169">受到加密，且加密會隨檔案移動。</span><span class="sxs-lookup"><span data-stu-id="bdc17-169">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="bdc17-170">包含自訂權限，因此只有「小組群組」成員能夠開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-170">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="bdc17-171">若要針對儲存在「小組網站」中的檔案完成這項額外的安全性層級，您必須設定一個新的敏感度標籤，這個標籤不是自有標籤就是一般標籤的子標籤，適用於高度管制檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-171">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="bdc17-172">只有「小組群組」成員可以在標籤清單中看到這個標籤。</span><span class="sxs-lookup"><span data-stu-id="bdc17-172">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="bdc17-173">當您需要少量標籤、可同時用於全域使用和個別的私人小組時，請使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="bdc17-173">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="bdc17-174">當您有大量標籤或想要將私人小組的標籤整理到高度管制標籤之下時，請使用敏感度子標籤。</span><span class="sxs-lookup"><span data-stu-id="bdc17-174">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="bdc17-175">[使用下列指示](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)設定包含下列設定的不同標籤或子標籤：</span><span class="sxs-lookup"><span data-stu-id="bdc17-175">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="bdc17-176">標籤名稱包含有小組名稱</span><span class="sxs-lookup"><span data-stu-id="bdc17-176">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="bdc17-177">已啟用加密</span><span class="sxs-lookup"><span data-stu-id="bdc17-177">Encryption is enabled</span></span>
- <span data-ttu-id="bdc17-178">「小組群組」具有共同撰寫權限</span><span class="sxs-lookup"><span data-stu-id="bdc17-178">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="bdc17-179">以下是新標籤所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="bdc17-179">Here’s the resulting configuration with the new label.</span></span>

![安全小組案例的組態步驟 5](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="bdc17-181">以下是敏感度標籤和「小組群組」之間的關係。</span><span class="sxs-lookup"><span data-stu-id="bdc17-181">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![小組群組和標籤權限之間的關係](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="bdc17-183">如果您將敏感度標籤或子標籤設定為使用者定義的權限或設定有到期日，您將無法從 Microsoft Teams 或 SharePoint 開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-183">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="bdc17-184">您必須使用 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="bdc17-184">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="bdc17-185">自訂權限</span><span class="sxs-lookup"><span data-stu-id="bdc17-185">Custom permissions</span></span>

<span data-ttu-id="bdc17-186">您也可以針對「小組網站」設定自訂 SharePoint 網站權限和對應的敏感度標籤 (如有需要的話)。</span><span class="sxs-lookup"><span data-stu-id="bdc17-186">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="bdc17-187">以下列出兩個範例。</span><span class="sxs-lookup"><span data-stu-id="bdc17-187">Here are two examples.</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="bdc17-188">範例 1：委派 SharePoint 網站的系統管理</span><span class="sxs-lookup"><span data-stu-id="bdc17-188">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="bdc17-189">如果小組擁有者沒有 SharePoint 系統管理經驗或是想要委派「小組網站」的系統管理，小組擁有者可以將 SharePoint 系統管理員的使用者帳戶新增至小組擁有者清單。</span><span class="sxs-lookup"><span data-stu-id="bdc17-189">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="bdc17-190">但是接下來，SharePoint 系統管理員會擁有小組及其所有資源的完整存取權，並且能夠開啟已套用敏感度標籤的檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-190">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="bdc17-191">為防止這種過度授與權限的情況發生，請在網站的進階權限設定中，將 SharePoint 系統管理員的使用者帳戶新增至「小組網站」擁有者的 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="bdc17-191">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="bdc17-192">SharePoint 系統管理員可以管理網站，但是無法存取小組及其任何資源，或是無法開啟已指派敏感度標籤的檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-192">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="bdc17-193">範例 2：允許唯讀存取已加標籤的檔案</span><span class="sxs-lookup"><span data-stu-id="bdc17-193">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="bdc17-194">如果有部分人員只需要查看「小組網站」中已加標籤的檔案內容，請將這些人員的個人使用者帳戶新增至：</span><span class="sxs-lookup"><span data-stu-id="bdc17-194">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="bdc17-195">\<小組名稱> 訪客的 SharePoint 群組，這個群組依預設擁有「讀取」權限層級。</span><span class="sxs-lookup"><span data-stu-id="bdc17-195">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="bdc17-196">具有檢視者權限的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="bdc17-196">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="bdc17-197">以下是標籤上所產生的權限。</span><span class="sxs-lookup"><span data-stu-id="bdc17-197">Here are the resulting permissions on the label.</span></span>

![可檢視已加標籤的檔案的自訂權限範例](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="bdc17-199">網站訪客將可以直接存取「小組網站」，並查看已套用子標籤的檔案內容。</span><span class="sxs-lookup"><span data-stu-id="bdc17-199">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="bdc17-200">但是，由於訪客不是「小組群組」成員，因此訪客無法存取小組或其任何資源。</span><span class="sxs-lookup"><span data-stu-id="bdc17-200">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="bdc17-201">階段 2：對小組成員推動使用者採用</span><span class="sxs-lookup"><span data-stu-id="bdc17-201">Phase 2: Drive user adoption for team members</span></span>

<span data-ttu-id="bdc17-202">小組成立後，您就可以開始對小組成員推動採用此小組及其額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="bdc17-202">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="bdc17-203">步驟 1：訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="bdc17-203">Step 1: Train your users</span></span>

<span data-ttu-id="bdc17-204">「小組群組」成員可以存取小組及其所有資源，包括聊天、會議及其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="bdc17-204">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="bdc17-205">使用頻道中 [檔案]\*\*\*\* 區段的檔案時，「小組群組」成員必須將敏感度標籤或子標籤指派給針對安全小組建立的檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-205">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="bdc17-206">請見以下範例。</span><span class="sxs-lookup"><span data-stu-id="bdc17-206">Here’s an example.</span></span>

![將標籤套用到安全小組的檔案範例](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="bdc17-208">當標籤套用到受保護的檔案時。</span><span class="sxs-lookup"><span data-stu-id="bdc17-208">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="bdc17-209">「小組群組」成員可以在 Microsoft Teams 中開啟，並即時進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="bdc17-209">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="bdc17-210">檔案已加密，且包含有設定給「小組群組」成員的共同撰寫權限。</span><span class="sxs-lookup"><span data-stu-id="bdc17-210">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="bdc17-211">如果檔案離開網站並轉寄給惡意使用者，這些使用者必須提供「小組群組」成員的使用者帳戶認證，才能開啟檔案並檢視其內容。</span><span class="sxs-lookup"><span data-stu-id="bdc17-211">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="bdc17-212">訓練您的小組成員：</span><span class="sxs-lookup"><span data-stu-id="bdc17-212">Train your team members:</span></span>

- <span data-ttu-id="bdc17-213">了解使用新的小組進行聊天、會議、檔案和「小組網站」上其他資源的重要性，以及高度管制資料外洩的後果，例如法律後果、法規罰款、勒索軟體或喪失競爭優勢。</span><span class="sxs-lookup"><span data-stu-id="bdc17-213">On the importance of using the new team for chats, meetings, files, and the other resources of the Team Site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="bdc17-214">如何存取小組。</span><span class="sxs-lookup"><span data-stu-id="bdc17-214">How to access the team.</span></span>
- <span data-ttu-id="bdc17-215">如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-215">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="bdc17-216">DLP 原則如何封鎖他們免於在外部共用檔案。</span><span class="sxs-lookup"><span data-stu-id="bdc17-216">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="bdc17-217">如何為檔案加上小組的自訂標籤或子標籤。</span><span class="sxs-lookup"><span data-stu-id="bdc17-217">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="bdc17-218">標籤或子標籤如何保護檔案，即使檔案從網站外洩。</span><span class="sxs-lookup"><span data-stu-id="bdc17-218">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="bdc17-219">此訓練應該包含實際操作練習，讓您的小組成員可以體驗這些功能及其結果。</span><span class="sxs-lookup"><span data-stu-id="bdc17-219">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="bdc17-220">步驟 2：舉辦定期的使用狀況檢閱和處理小組成員的意見反應</span><span class="sxs-lookup"><span data-stu-id="bdc17-220">Step 2: Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="bdc17-221">在訓練後的幾週內：</span><span class="sxs-lookup"><span data-stu-id="bdc17-221">In the weeks after training:</span></span>

- <span data-ttu-id="bdc17-222">快速處理小組成員的意見反應，並微調原則和設定。</span><span class="sxs-lookup"><span data-stu-id="bdc17-222">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="bdc17-223">分析小組的使用方式，並且與預期使用方式進行比較。</span><span class="sxs-lookup"><span data-stu-id="bdc17-223">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="bdc17-224">確認高度管制檔案已正確地標示自訂的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="bdc17-224">Verify that highly regulated files have been properly labeled with the custom sensitivity label or sublabel.</span></span>

  <span data-ttu-id="bdc17-225">您可以在 SharePoint 檢視資料夾，然後透過 [新增欄]\*\*\*\* 的 [顯示/隱藏欄]\*\*\*\* 選項新增 [敏感度]\*\*\*\* 欄，查看哪些檔案有被指派標籤。</span><span class="sxs-lookup"><span data-stu-id="bdc17-225">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="bdc17-226">視需要重新訓練您的使用者。</span><span class="sxs-lookup"><span data-stu-id="bdc17-226">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdc17-227">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bdc17-227">See also</span></span>

[<span data-ttu-id="bdc17-228">適用於高度管制資料的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="bdc17-228">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="bdc17-229">Microsoft 365 企業版工作負載和案例</span><span class="sxs-lookup"><span data-stu-id="bdc17-229">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="bdc17-230">[Microsoft 365 生產力資源庫](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="bdc17-230">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="bdc17-231">部署指南</span><span class="sxs-lookup"><span data-stu-id="bdc17-231">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
