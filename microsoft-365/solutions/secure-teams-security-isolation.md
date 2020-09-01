---
title: 為小組設定安全性隔離
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: 了解如何使用唯一的敏感度標籤來建立小組以獲得安全性。
ms.openlocfilehash: 789e75165339f8a834a73aa3fd0d8a2666285ce9
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308180"
---
# <a name="configure-a-team-with-security-isolation"></a><span data-ttu-id="b04ed-103">為小組設定安全性隔離</span><span class="sxs-lookup"><span data-stu-id="b04ed-103">Configure a team with security isolation</span></span>

<span data-ttu-id="b04ed-104">本文會為您提供一些建議和步驟，讓您在 Microsoft Teams 設定私人小組，並使用唯一的敏感度標籤來加密檔案，以便只有小組成員可以解密檔案。</span><span class="sxs-lookup"><span data-stu-id="b04ed-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams and use a unique sensitivity label to encrypt files so that only team members can decrypt them.</span></span>

<span data-ttu-id="b04ed-105">除了私人存取外，本文還說明如何設定相關聯的 SharePoint 網站 (可從小組頻道的 **[檔案]** 區段來存取)，以獲得所需的額外安全性進而能夠儲存受到高度管制的資料。</span><span class="sxs-lookup"><span data-stu-id="b04ed-105">Beyond the private access, this article describes how to configure the associated SharePoint site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span>

<span data-ttu-id="b04ed-106">具有安全性隔離小組的設定元素如下：</span><span class="sxs-lookup"><span data-stu-id="b04ed-106">The elements of configuration for a team with security isolation are:</span></span>

- <span data-ttu-id="b04ed-107">私人小組</span><span class="sxs-lookup"><span data-stu-id="b04ed-107">A private team</span></span>
- <span data-ttu-id="b04ed-108">小組的相關聯 SharePoint 網站需要的額外安全性有：</span><span class="sxs-lookup"><span data-stu-id="b04ed-108">Additional security on the associated SharePoint site for the team that:</span></span>
  - <span data-ttu-id="b04ed-109">防止網站成員與其他人共用網站。</span><span class="sxs-lookup"><span data-stu-id="b04ed-109">Prevents members of the site from sharing the site with others.</span></span>
  - <span data-ttu-id="b04ed-110">避免非網站成員要求網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="b04ed-110">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="b04ed-111">專門用於此小組的敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="b04ed-111">A sensitivity label specifically for this team that:</span></span>
    - <span data-ttu-id="b04ed-112">防止從未受管理的裝置存取 SharePoint 內容</span><span class="sxs-lookup"><span data-stu-id="b04ed-112">Prevents access to SharePoint content from unmanaged devices</span></span>
    - <span data-ttu-id="b04ed-113">視您的需求而定，允許或拒絕來賓存取小組</span><span class="sxs-lookup"><span data-stu-id="b04ed-113">Allows or denies guest access to the team, depending on your requirements</span></span>
    - <span data-ttu-id="b04ed-114">加密已套用此標籤的文件</span><span class="sxs-lookup"><span data-stu-id="b04ed-114">Encrypts documents to which the label is applied</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b04ed-115">請先確定您已啟用[敏感度標籤以保護 Microsoft Teams、Office 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)，然後再繼續進行本文中的步驟。</span><span class="sxs-lookup"><span data-stu-id="b04ed-115">Be sure you have enabled [sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) before you proceed with the steps in this article.</span></span>

<a name="poster"></a> <span data-ttu-id="b04ed-116">如需此案例的 2 頁式摘要，請參閱[具有安全性隔離的 Microsoft Teams 海報](../downloads/team-security-isolation-poster.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b04ed-116">For a 2-page summary of this scenario, see the [Microsoft Teams with security isolation poster](../downloads/team-security-isolation-poster.pdf).</span></span>

<span data-ttu-id="b04ed-117">[![具有安全性隔離的 Microsoft Teams 海報](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span><span class="sxs-lookup"><span data-stu-id="b04ed-117">[![Microsoft Teams with security isolation poster](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span></span>

<span data-ttu-id="b04ed-118">您也可以用 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) 或 [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pptx) 格式下載此海報，以及用 Letter、Legal 或 Tabloid (11 x 17) 大小的紙張列印此海報。</span><span class="sxs-lookup"><span data-stu-id="b04ed-118">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="b04ed-119">初始保護</span><span class="sxs-lookup"><span data-stu-id="b04ed-119">Initial protections</span></span>

<span data-ttu-id="b04ed-120">為了協助保護對於小組及其基礎 SharePoint 網站的存取，請檢閱下列最佳做法：</span><span class="sxs-lookup"><span data-stu-id="b04ed-120">To help protect access to the team and its underlying SharePoint site, review the following best practices:</span></span>
- [<span data-ttu-id="b04ed-121">身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="b04ed-121">Identity and device access policies</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)
- [<span data-ttu-id="b04ed-122">SharePoint Online 存取原則</span><span class="sxs-lookup"><span data-stu-id="b04ed-122">SharePoint Online access policies</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)
- [<span data-ttu-id="b04ed-123">為小組部署基準保護</span><span class="sxs-lookup"><span data-stu-id="b04ed-123">Deploy teams with baseline protection</span></span>](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a><span data-ttu-id="b04ed-124">來賓共用</span><span class="sxs-lookup"><span data-stu-id="b04ed-124">Guest sharing</span></span>

<span data-ttu-id="b04ed-125">視貴公司的性質而定，您不一定會想要為此小組啟用來賓共用。</span><span class="sxs-lookup"><span data-stu-id="b04ed-125">Depending on the nature of your business, you may or may not want to enable guest sharing for this team.</span></span> <span data-ttu-id="b04ed-126">如果您打算與小組內的非組織內部人員共同作業，請啟用來賓共用。</span><span class="sxs-lookup"><span data-stu-id="b04ed-126">If you do plan to collaborate with people outside your organization in the team, enable guest sharing.</span></span> 

<span data-ttu-id="b04ed-127">如需如何安全地與來賓共用的詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="b04ed-127">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="b04ed-128">在與組織外的人員共用檔案時，限制資訊意外暴露</span><span class="sxs-lookup"><span data-stu-id="b04ed-128">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="b04ed-129">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="b04ed-129">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="b04ed-130">為了允許或封鎖來賓共用，我們會使用敏感度標籤 (適用於小組) 和網站層級共用控制 (適用於相關聯的 SharePoint 網站) 的組合，後面會有這兩種機制的討論。</span><span class="sxs-lookup"><span data-stu-id="b04ed-130">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="create-a-private-team"></a><span data-ttu-id="b04ed-131">建立私人小組</span><span class="sxs-lookup"><span data-stu-id="b04ed-131">Create a private team</span></span>

<span data-ttu-id="b04ed-132">由於我們要建立專門用於此小組的敏感度標籤，所以下一步要建立該小組。</span><span class="sxs-lookup"><span data-stu-id="b04ed-132">Since we are creating a sensitivity label specifically for this team, the next step is to create the team.</span></span> <span data-ttu-id="b04ed-133">如果您擁有現有的小組，則可以使用該小組。</span><span class="sxs-lookup"><span data-stu-id="b04ed-133">If you have an existing team, you can use that.</span></span>

<span data-ttu-id="b04ed-134">為敏感資訊建立小組</span><span class="sxs-lookup"><span data-stu-id="b04ed-134">To create a team for sensitive information</span></span>
1. <span data-ttu-id="b04ed-135">在 Teams 中，按一下應用程式左側的 **[團隊]**，然後按一下團隊清單底部的 **[加入或建立團隊]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-135">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="b04ed-136">按一下 **[建立團隊]** (左上角的第一張卡片)。</span><span class="sxs-lookup"><span data-stu-id="b04ed-136">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="b04ed-137">選擇 **[從頭建置小組]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-137">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="b04ed-138">在 **[敏感度]** 清單中，保留預設值。</span><span class="sxs-lookup"><span data-stu-id="b04ed-138">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="b04ed-139">在 **[隱私權]** 底下，按一下 **[私人]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-139">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="b04ed-140">為與敏感專案相關的小組輸入其名稱。</span><span class="sxs-lookup"><span data-stu-id="b04ed-140">Type a name for the team that is related to your sensitive project.</span></span> <span data-ttu-id="b04ed-141">例如，**土星專案**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-141">For example, **Project Saturn**.</span></span>
7. <span data-ttu-id="b04ed-142">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-142">Click **Create**.</span></span>
8. <span data-ttu-id="b04ed-143">將使用者新增至小組，然後按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-143">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="b04ed-144">私人頻道設定</span><span class="sxs-lookup"><span data-stu-id="b04ed-144">Private channel settings</span></span>

<span data-ttu-id="b04ed-145">建議您限制只有小組擁有者能夠建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="b04ed-145">We recommend restricting creating private channels to team owners.</span></span>

<span data-ttu-id="b04ed-146">限制私人頻道的建立</span><span class="sxs-lookup"><span data-stu-id="b04ed-146">To restrict private channel creation</span></span>
1. <span data-ttu-id="b04ed-147">在該團隊中，按一下 **[更多選項]**，然後按一下 **[管理團隊]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-147">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="b04ed-148">在 **[設定]** 索引標籤上展開 **[成員權限]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-148">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="b04ed-149">清除 **[允許成員建立私人頻道]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b04ed-149">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="b04ed-150">您也可以使用[小組原則](https://docs.microsoft.com/MicrosoftTeams/teams-policies)來控制可以建立私人頻道的人員。</span><span class="sxs-lookup"><span data-stu-id="b04ed-150">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="create-a-sensitivity-label"></a><span data-ttu-id="b04ed-151">建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b04ed-151">Create a sensitivity label</span></span>

<span data-ttu-id="b04ed-152">為了為小組設定安全性隔離，我們會使用專為這個小組建立的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="b04ed-152">To configure a team for security isolation, we'll be using a sensitivity label created specifically for this team.</span></span> <span data-ttu-id="b04ed-153">此標籤會在小組層級使用，以控制來賓共用並封鎖未受管理裝置的存取權。</span><span class="sxs-lookup"><span data-stu-id="b04ed-153">This label is used at the team level to control guest sharing and to block access from unmanaged devices.</span></span> <span data-ttu-id="b04ed-154">其也可用來分類和加密小組中的個別檔案，以便只有小組擁有者和成員可以開啟這些檔案。</span><span class="sxs-lookup"><span data-stu-id="b04ed-154">It can also be used to classify and encrypt individual files in the team so that only team owners and members can open them.</span></span>

<span data-ttu-id="b04ed-155">如果您有內部合作夥伴或專案關係人群組，而他們應該要能夠檢視加密的文件，但不能加以編輯，則可以將這些人新增至具有僅限檢視權限的標籤。</span><span class="sxs-lookup"><span data-stu-id="b04ed-155">If you have an internal partner or stakeholder group who should be able to view encrypted documents but not edit them, you can add them to the label with view-only permissions.</span></span> <span data-ttu-id="b04ed-156">然後，您可以將這些人新增至具有讀者權限的小組 SharePoint 網站，這些人便會擁有文件保存所在網站的唯讀權限，而非擁有小組本身的唯讀權限。</span><span class="sxs-lookup"><span data-stu-id="b04ed-156">You can then add these people to the team's SharePoint site with Reader permissions, and they will have read-only access to the site where the documents are kept, but not the team itself.</span></span>

<span data-ttu-id="b04ed-157">建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b04ed-157">To create a sensitivity label</span></span>
1. <span data-ttu-id="b04ed-158">開啟 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b04ed-158">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="b04ed-159">在 **[解決方案]** 底下，按一下 **[資訊保護]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-159">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="b04ed-160">按一下 **[建立標籤]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-160">Click **Create a label**.</span></span>
4. <span data-ttu-id="b04ed-161">為標籤輸入與小組名稱類似的名稱。</span><span class="sxs-lookup"><span data-stu-id="b04ed-161">Type a name for the label that is similar to your team name.</span></span> <span data-ttu-id="b04ed-162">例如，**高敏感度 - 土星專案**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-162">For example, **Highly sensitive - Project Saturn**.</span></span>
5. <span data-ttu-id="b04ed-163">新增工具提示，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-163">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="b04ed-164">在 **[加密]** 頁面上，於 **[加密]** 下拉式清單中選擇 **[套用]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-164">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="b04ed-165">若要新增小組權限：</span><span class="sxs-lookup"><span data-stu-id="b04ed-165">To add the team permissions:</span></span><br>
  <span data-ttu-id="b04ed-166">a.</span><span class="sxs-lookup"><span data-stu-id="b04ed-166">a.</span></span> <span data-ttu-id="b04ed-167">按一下 **[指派權限]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-167">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="b04ed-168">b.</span><span class="sxs-lookup"><span data-stu-id="b04ed-168">b.</span></span> <span data-ttu-id="b04ed-169">按一下 **[新增使用者或群組]**、選取您所建立的小組，然後按一下 **[新增]**</span><span class="sxs-lookup"><span data-stu-id="b04ed-169">Click **Add users or groups**, select the team that you created, and then click **Add**</span></span><br>
  <span data-ttu-id="b04ed-170">c.</span><span class="sxs-lookup"><span data-stu-id="b04ed-170">c.</span></span> <span data-ttu-id="b04ed-171">按一下 **[選擇權限]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-171">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="b04ed-172">d.</span><span class="sxs-lookup"><span data-stu-id="b04ed-172">d.</span></span> <span data-ttu-id="b04ed-173">從下拉式清單中選擇 **[共同作者]**，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-173">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="b04ed-174">對於具有此標籤的檔案，如果您想要將有其唯讀存取權的使用者或群組包含進來：</span><span class="sxs-lookup"><span data-stu-id="b04ed-174">If you want to include users or groups with read-only access to files with the label:</span></span><br>
  <span data-ttu-id="b04ed-175">a.</span><span class="sxs-lookup"><span data-stu-id="b04ed-175">a.</span></span> <span data-ttu-id="b04ed-176">按一下 **[指派權限]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-176">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="b04ed-177">b.</span><span class="sxs-lookup"><span data-stu-id="b04ed-177">b.</span></span> <span data-ttu-id="b04ed-178">按一下 **[新增使用者或群組]**、選取您要新增的使用者或群組，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-178">Click **Add users or groups**, select the users or groups that you want to add, and then click **Add**.</span></span><br>
  <span data-ttu-id="b04ed-179">c.</span><span class="sxs-lookup"><span data-stu-id="b04ed-179">c.</span></span> <span data-ttu-id="b04ed-180">按一下 **[選擇權限]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-180">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="b04ed-181">d.</span><span class="sxs-lookup"><span data-stu-id="b04ed-181">d.</span></span> <span data-ttu-id="b04ed-182">從下拉式清單中選擇 **[檢視者]**，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-182">Choose **Viewer** from the dropdown list, and then click **Save**.</span></span><br>
  <span data-ttu-id="b04ed-183">e.</span><span class="sxs-lookup"><span data-stu-id="b04ed-183">e.</span></span> <span data-ttu-id="b04ed-184">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-184">Click **Save**.</span></span>
9. <span data-ttu-id="b04ed-185">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-185">Click **Next**.</span></span>
10. <span data-ttu-id="b04ed-186">如果您想要將頁首、頁尾或浮水印自動新增至以此標籤分類的檔案，請在 **[內容標記]** 頁面上開啟內容標記。</span><span class="sxs-lookup"><span data-stu-id="b04ed-186">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
11. <span data-ttu-id="b04ed-187">在 **[網站和群組設定]** 頁面上，將 **[網站和群組設定]** 設為 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-187">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
12. <span data-ttu-id="b04ed-188">在 **[Office 365 群組連線小組網站隱私權]** 下拉式清單中，選擇 **[私人 - 只有成員可以存取網站]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-188">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
13. <span data-ttu-id="b04ed-189">如果您想要允許來賓存取，請選取 **[讓 Office 365 群組擁有者將貴組織外部的人員新增到群組]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b04ed-189">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
14. <span data-ttu-id="b04ed-190">在 **[未受管理的裝置]** 底下，選擇 **[封鎖存取]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-190">Under **Unmanaged devices**, choose **Block access**.</span></span>
15. <span data-ttu-id="b04ed-191">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-191">Click **Next**.</span></span>
16. <span data-ttu-id="b04ed-192">在 **[Office 應用程式的自動加上標籤]** 頁面上按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-192">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
17. <span data-ttu-id="b04ed-193">按一下 **[提交]**，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-193">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="b04ed-194">在建立好標籤後，您必須將標籤發佈給將使用該標籤的使用者。</span><span class="sxs-lookup"><span data-stu-id="b04ed-194">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="b04ed-195">在本案例中，我們只會將標籤提供給小組人員使用。</span><span class="sxs-lookup"><span data-stu-id="b04ed-195">In this case, we'll make the label available only to people in the team.</span></span>

<span data-ttu-id="b04ed-196">發佈敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b04ed-196">To publish a sensitivity label</span></span>
1. <span data-ttu-id="b04ed-197">在 Microsoft 365 合規性中心的 **[資訊保護]** 頁面上，選擇 **[標籤原則]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b04ed-197">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="b04ed-198">按一下 **[發佈標籤]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-198">Click **Publish labels**.</span></span>
3. <span data-ttu-id="b04ed-199">在 **[選擇要發佈的敏感度標籤]** 頁面上，按一下 **[選擇要發佈的敏感度標籤]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-199">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="b04ed-200">選取您所建立的標籤，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-200">Select the label that you created, and then click **Add**.</span></span>
5. <span data-ttu-id="b04ed-201">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-201">Click **Next**.</span></span>
6. <span data-ttu-id="b04ed-202">在 [發佈給使用者與群組] 頁面上，按一下 **[選擇使用者和群組]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-202">On the Publish to users and groups page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="b04ed-203">按一下 **[新增]**，然後選取您建立的小組。</span><span class="sxs-lookup"><span data-stu-id="b04ed-203">Click **Add**, and then select the team that you created.</span></span>
8. <span data-ttu-id="b04ed-204">按一下 **[新增]**，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-204">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="b04ed-205">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-205">Click **Next**.</span></span>
10. <span data-ttu-id="b04ed-206">在 [原則設定] 頁面上，選取 **[使用者必須提供移除標籤或降低分類標籤的理由]** 核取方塊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-206">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="b04ed-207">輸入原則的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-207">Type a name for the policy, and then click **Next**.</span></span>
12. <span data-ttu-id="b04ed-208">按一下 **[提交]**，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-208">Click **Submit** and then click **Done**.</span></span>

## <a name="apply-the-label-to-the-team"></a><span data-ttu-id="b04ed-209">將標籤套用至小組</span><span class="sxs-lookup"><span data-stu-id="b04ed-209">Apply the label to the team</span></span>

<span data-ttu-id="b04ed-210">當標籤發佈之後，您必須將其套用至小組，才能讓來賓共用和受管理的裝置設定生效。</span><span class="sxs-lookup"><span data-stu-id="b04ed-210">Once the label has been published, you must apply it to the team in order for the guest sharing and managed devices settings to take effect.</span></span> <span data-ttu-id="b04ed-211">您可在 SharePoint 系統管理中心完成此操作。</span><span class="sxs-lookup"><span data-stu-id="b04ed-211">This is done in the SharePoint admin center.</span></span> <span data-ttu-id="b04ed-212">請注意，標籤發佈後可能需要一些時間才能使用。</span><span class="sxs-lookup"><span data-stu-id="b04ed-212">Note, it may take some time for the label to become available after it's been published.</span></span>

<span data-ttu-id="b04ed-213">套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b04ed-213">To apply the sensitivity label</span></span>
1. <span data-ttu-id="b04ed-214">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="b04ed-214">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="b04ed-215">在 **[網站]** 底下，按一下 **[使用中網站]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-215">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="b04ed-216">按一下與小組相關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="b04ed-216">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="b04ed-217">在 **[原則]** 索引標籤的 **[敏感度]** 底下，按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-217">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="b04ed-218">選取您所建立的標籤，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-218">Select the label that you created, and then click **Save**.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="b04ed-219">SharePoint 設定</span><span class="sxs-lookup"><span data-stu-id="b04ed-219">SharePoint settings</span></span>

<span data-ttu-id="b04ed-220">您必須在 SharePoint 中執行三個步驟：</span><span class="sxs-lookup"><span data-stu-id="b04ed-220">There are three steps to do in SharePoint:</span></span>

- <span data-ttu-id="b04ed-221">在 SharePoint 系統管理中心內更新網站的來賓共用設定，使其符合您在建立標籤時所選擇的設定，並將預設的共用連結更新為*擁有現有存取權的人員*。</span><span class="sxs-lookup"><span data-stu-id="b04ed-221">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="b04ed-222">更新網站本身的網站共用設定以防止成員共用檔案、資料夾或網站，並關閉存取要求。</span><span class="sxs-lookup"><span data-stu-id="b04ed-222">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>
- <span data-ttu-id="b04ed-223">如果您已將人員或群組新增至具有檢視者權限的標籤，則可以將其新增至具有讀取權限的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="b04ed-223">If you added people or groups to the label with Viewer permissions, you can add them to the SharePoint site with Read permissions.</span></span>

### <a name="sharepoint-guest-settings"></a><span data-ttu-id="b04ed-224">SharePoint 來賓設定</span><span class="sxs-lookup"><span data-stu-id="b04ed-224">SharePoint guest settings</span></span>

<span data-ttu-id="b04ed-225">您在建立標籤時所選擇的來賓共用設定 (這只會影響小組成員資格) 應符合相關聯 SharePoint 網站的來賓共用設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b04ed-225">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="b04ed-226">標籤設定</span><span class="sxs-lookup"><span data-stu-id="b04ed-226">Label setting</span></span>|<span data-ttu-id="b04ed-227">SharePoint 網站設定</span><span class="sxs-lookup"><span data-stu-id="b04ed-227">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="b04ed-228">**已選取 [讓 Office 365 群組擁有者將組織外部人員新增到群組]**</span><span class="sxs-lookup"><span data-stu-id="b04ed-228">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="b04ed-229">**[新的及現有的來賓]** (新團隊的預設值)</span><span class="sxs-lookup"><span data-stu-id="b04ed-229">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="b04ed-230">未選取 **[讓 Office 365 群組擁有者將組織外部人員新增到群組]**</span><span class="sxs-lookup"><span data-stu-id="b04ed-230">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="b04ed-231">**只有貴組織中的人員**</span><span class="sxs-lookup"><span data-stu-id="b04ed-231">**Only people in your organization**</span></span>|

<span data-ttu-id="b04ed-232">我們也會更新預設的共用連結類型，以降低不小心將檔案和資料夾共用給更多非預期對象的風險。</span><span class="sxs-lookup"><span data-stu-id="b04ed-232">We'll also update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

<span data-ttu-id="b04ed-233">更新網站設定</span><span class="sxs-lookup"><span data-stu-id="b04ed-233">To update site settings</span></span>
1. <span data-ttu-id="b04ed-234">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="b04ed-234">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="b04ed-235">在 **[網站]** 底下，按一下 **[使用中網站]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-235">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="b04ed-236">按一下與小組相關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="b04ed-236">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="b04ed-237">在 **[原則]** 索引標籤的 **[外部共用]** 下，按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-237">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="b04ed-238">如果您在建立敏感度標籤時允許來賓共用，請確定您已選取 **[新的及現有的來賓]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-238">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="b04ed-239">如果您在建立標籤時未允許共用，請選擇 **[只有貴組織中的人員]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-239">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="b04ed-240">在 **[預設的共用連結類型] 底下，清除 [與組織層級設定相同]** 核取方塊，然後選取 **[擁有現有存取權的人員]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-240">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="b04ed-241">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-241">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="b04ed-242">私人頻道</span><span class="sxs-lookup"><span data-stu-id="b04ed-242">Private channels</span></span>

<span data-ttu-id="b04ed-243">如果您在小組中新增私人頻道，則每個私人頻道都會使用預設的共用設定建立一個新的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="b04ed-243">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="b04ed-244">這些網站不會顯示在 SharePoint 系統管理中心內，因此您必須使用 [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell Cmdlet 與下列參數來更新來賓共用設定：</span><span class="sxs-lookup"><span data-stu-id="b04ed-244">These sites are not visible in the SharePoint admin center, so you must use the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet with the following parameters to update the guest sharing settings:</span></span>

- <span data-ttu-id="b04ed-245">`-SharingCapability Disabled`，以關閉來賓共用 (預設為開啟)</span><span class="sxs-lookup"><span data-stu-id="b04ed-245">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="b04ed-246">`-DefaultSharingLinkType Internal`，以將預設共用連結變更為 *[特定人員]*</span><span class="sxs-lookup"><span data-stu-id="b04ed-246">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

<span data-ttu-id="b04ed-247">如果您不打算讓小組使用私人頻道，請考慮在[小組設定](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc)中的 **[成員權限]** 底下，關閉可供小組成員建立私人頻道的功能。</span><span class="sxs-lookup"><span data-stu-id="b04ed-247">If you don't plan to use private channels with your team, consider turning off the ability for team members to create them under **Member permissions** in [team settings](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="b04ed-248">網站共用設定</span><span class="sxs-lookup"><span data-stu-id="b04ed-248">Site sharing settings</span></span>

<span data-ttu-id="b04ed-249">為了協助確保 SharePoint 網站不會與非小組成員的人員共用，我們將這種共用功能限制為只有擁有者能使用。</span><span class="sxs-lookup"><span data-stu-id="b04ed-249">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="b04ed-250">我們也會將檔案和資料夾的共用功能限制為只有小組擁有者能使用。</span><span class="sxs-lookup"><span data-stu-id="b04ed-250">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="b04ed-251">這可協助您確保每次有檔案與非小組人員共用時，擁有者都會知情。</span><span class="sxs-lookup"><span data-stu-id="b04ed-251">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="b04ed-252">設定僅限擁有者使用的網站共用功能</span><span class="sxs-lookup"><span data-stu-id="b04ed-252">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="b04ed-253">在 Teams 中，瀏覽至所要更新團隊的 **[一般]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b04ed-253">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="b04ed-254">在小組的工具列中，按一下 **[檔案]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-254">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="b04ed-255">按一下省略符號，然後按一下 **[在 SharePoint 中開啟]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-255">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="b04ed-256">在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 **[網站權限]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-256">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="b04ed-257">在 [網站權限] 窗格的 **[共用設定]** 之下，按一下 **[變更共用設定]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-257">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="b04ed-258">在 **[共用權限]** 之下，選擇 **[只有網站擁有者可以共用檔案、資料夾及網站]**，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-258">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

### <a name="custom-site-permissions"></a><span data-ttu-id="b04ed-259">自訂網站權限</span><span class="sxs-lookup"><span data-stu-id="b04ed-259">Custom site permissions</span></span>

<span data-ttu-id="b04ed-260">如果您已將具有檢視者權限的人員新增至敏感度標籤，則可以將其新增至具有讀取權限的 SharePoint 網站，讓這些人可以輕鬆存取檔案。</span><span class="sxs-lookup"><span data-stu-id="b04ed-260">If you added people with Viewer permissions to the sensitivity label, you can add them to the SharePoint site with Read access so they have easy access to the files.</span></span>

<span data-ttu-id="b04ed-261">將使用者新增至網站</span><span class="sxs-lookup"><span data-stu-id="b04ed-261">To add users to the site</span></span>
1. <span data-ttu-id="b04ed-262">在網站中，按一下 [設定] 圖示，然後按一下 **[網站權限]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-262">In the site, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="b04ed-263">按一下 **[邀請人員]**，然後按一下 **[僅共用網站]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-263">Click **Invite people**, and then click **Share site only**.</span></span>
3. <span data-ttu-id="b04ed-264">輸入所要邀請使用者和群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="b04ed-264">Type the names of the users and groups that you want to invite.</span></span>
4. <span data-ttu-id="b04ed-265">針對您新增的每個人員或群組，將其權限從 **[編輯]** 變更為 **[讀取]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-265">For each person or group that you add, change their permissions from **Edit** to **Read**.</span></span>
5. <span data-ttu-id="b04ed-266">選擇是否要向其傳送含有網站連結的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b04ed-266">Choose if you want to send them an email with a link to the site.</span></span>
6. <span data-ttu-id="b04ed-267">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b04ed-267">Click **Add**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="b04ed-268">其他保護</span><span class="sxs-lookup"><span data-stu-id="b04ed-268">Additional protections</span></span>

<span data-ttu-id="b04ed-269">Microsoft 365 提供了其他方法來保護您的內容。</span><span class="sxs-lookup"><span data-stu-id="b04ed-269">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="b04ed-270">請想想下列選項是否有助於改善貴組織的安全性。</span><span class="sxs-lookup"><span data-stu-id="b04ed-270">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="b04ed-271">讓您的來賓使用者同意[使用規定](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)。</span><span class="sxs-lookup"><span data-stu-id="b04ed-271">Have your guest users agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="b04ed-272">為來賓設定[工作階段逾時原則](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)。</span><span class="sxs-lookup"><span data-stu-id="b04ed-272">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="b04ed-273">建立[敏感資訊類型](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)，並使用[資料外洩防護](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 來設定關於存取敏感資訊的原則。</span><span class="sxs-lookup"><span data-stu-id="b04ed-273">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>
- <span data-ttu-id="b04ed-274">使用 [Azure Active Directory 存取權](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)檢閱來定期檢閱小組的存取權和成員資格。</span><span class="sxs-lookup"><span data-stu-id="b04ed-274">Use [Azure Active Directory access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) reviews to periodically review team access and membership.</span></span>

## <a name="drive-user-adoption-for-team-members"></a><span data-ttu-id="b04ed-275">對小組成員推動使用者採用</span><span class="sxs-lookup"><span data-stu-id="b04ed-275">Drive user adoption for team members</span></span>

<span data-ttu-id="b04ed-276">小組成立後，您就可以開始對小組成員推動採用此小組及其額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="b04ed-276">With the team in place, it's time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="train-your-users"></a><span data-ttu-id="b04ed-277">訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="b04ed-277">Train your users</span></span>

<span data-ttu-id="b04ed-278">小組成員可以存取小組及其所有資源，包括聊天、會議及其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="b04ed-278">Members of the team can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="b04ed-279">從頻道的 **[檔案]** 區段使用檔案時，小組成員應將敏感度標籤指派給其所建立的檔案。</span><span class="sxs-lookup"><span data-stu-id="b04ed-279">When working with files from the **Files** section of a channel, members of the team should assign the sensitivity label to the files they create.</span></span>

<span data-ttu-id="b04ed-280">當標籤套用到檔案時，其會進行加密。</span><span class="sxs-lookup"><span data-stu-id="b04ed-280">When the label gets applied to the file, it is encrypted.</span></span> <span data-ttu-id="b04ed-281">小組成員可以開啟檔案並即時共同作業。</span><span class="sxs-lookup"><span data-stu-id="b04ed-281">Members of the team can open it and collaborate in real time.</span></span> <span data-ttu-id="b04ed-282">如果檔案離開網站並轉寄給惡意使用者，這些使用者必須提供小組成員的使用者帳戶認證，才能開啟檔案並檢視其內容。</span><span class="sxs-lookup"><span data-stu-id="b04ed-282">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the team to open the file and view its contents.</span></span> 

<span data-ttu-id="b04ed-283">訓練您的小組成員：</span><span class="sxs-lookup"><span data-stu-id="b04ed-283">Train your team members:</span></span>

- <span data-ttu-id="b04ed-284">了解使用新的小組進行聊天、會議、檔案和 SharePoint 網站上其他資源的重要性，以及高度管制資料外洩的後果，例如法律後果、法規罰款、勒索軟體或喪失競爭優勢。</span><span class="sxs-lookup"><span data-stu-id="b04ed-284">On the importance of using the new team for chats, meetings, files, and the other resources of the SharePoint site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="b04ed-285">如何存取小組。</span><span class="sxs-lookup"><span data-stu-id="b04ed-285">How to access the team.</span></span>
- <span data-ttu-id="b04ed-286">如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。</span><span class="sxs-lookup"><span data-stu-id="b04ed-286">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="b04ed-287">如何使用適合小組的正確敏感度標籤為檔案加上標籤。</span><span class="sxs-lookup"><span data-stu-id="b04ed-287">How to label files with the correct sensitivity label for the team.</span></span>
- <span data-ttu-id="b04ed-288">標籤如何保護檔案，即使檔案從網站外洩。</span><span class="sxs-lookup"><span data-stu-id="b04ed-288">How the label protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="b04ed-289">此訓練應該包含實際操作練習，讓您的小組成員可以體驗這些功能及其結果。</span><span class="sxs-lookup"><span data-stu-id="b04ed-289">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="b04ed-290">舉辦定期的使用狀況檢閱和處理小組成員的意見反應</span><span class="sxs-lookup"><span data-stu-id="b04ed-290">Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="b04ed-291">在訓練後的幾週內：</span><span class="sxs-lookup"><span data-stu-id="b04ed-291">In the weeks after training:</span></span>

- <span data-ttu-id="b04ed-292">快速處理小組成員的意見反應，並微調原則和設定。</span><span class="sxs-lookup"><span data-stu-id="b04ed-292">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="b04ed-293">分析小組的使用方式，並且與預期使用方式進行比較。</span><span class="sxs-lookup"><span data-stu-id="b04ed-293">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="b04ed-294">確認高度管制檔案已正確地標示敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="b04ed-294">Verify that highly regulated files have been properly labeled with the sensitivity label.</span></span> <span data-ttu-id="b04ed-295">(您可以在 SharePoint 檢視資料夾，然後透過 **[新增欄]** 的 **[顯示/隱藏欄]** 選項新增 **[敏感度]** 欄，查看哪些檔案有被指派標籤。</span><span class="sxs-lookup"><span data-stu-id="b04ed-295">(You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="b04ed-296">視需要重新訓練您的使用者。</span><span class="sxs-lookup"><span data-stu-id="b04ed-296">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="b04ed-297">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b04ed-297">See also</span></span>

[<span data-ttu-id="b04ed-298">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="b04ed-298">Azure AD Privileged Identity Management</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)