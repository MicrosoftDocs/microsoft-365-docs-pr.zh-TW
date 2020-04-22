---
title: Contoso Corporation 的機密專案小組
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何對重要專案的高管制資料使用團隊，以開發新的產品和服務套件。
ms.openlocfilehash: 310ef33d4add7d71616aee8808515ca90536d8c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636495"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="6ccfe-103">Contoso Corporation 的機密專案小組</span><span class="sxs-lookup"><span data-stu-id="6ccfe-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="6ccfe-104">在執行異地的執行中，Contoso 的 CEO 會定購一套新的產品和服務，並在今後五年中，讓 Contoso 的贏利翻倍。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="6ccfe-105">開發商務、工程及市場計畫的重要專案是「**專案 2** 」和整個公司的主要人員都是 recruited。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="6ccfe-106">調查和開發的時程表已緊密，這表示共同作業必須有效並提供安全的會議、進行中的交談及檔案儲存。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="6ccfe-107">專案2所產生的可傳送作業是商務計畫、產品及工程規格，以及 Word、Excel 及 PowerPoint 檔案形式的行銷材料和排程。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="6ccfe-108">由於其敏感性，對這些檔案的存取權如下：</span><span class="sxs-lookup"><span data-stu-id="6ccfe-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="6ccfe-109">限制為 Project 2 小組成員。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="6ccfe-110">使用資料遺失防護（DLP）原則進行保護，以避免專案2小組成員在小組外共用這些專案。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="6ccfe-111">以只允許存取專案2小組成員的許可權加密及保護，即使檔案是在 Contoso 以外發佈。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="6ccfe-112">Contoso IT 人員使用專案2和這些步驟的[高管制資料的小組](secure-teams-highly-regulated-data-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="6ccfe-113">步驟1：建立私人團隊並鎖定基礎 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="6ccfe-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="6ccfe-114">為了保護小組的底層 SharePoint 網站的存取權，Contoso IT 管理員設定了[建議的 SharePoint 存取原則](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="6ccfe-115">接下來，Contoso IT 管理員建立一個名為 Project 2 的新私人團隊，並新增專案2個人的使用者帳戶為成員。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="6ccfe-116">接下來，他們設定網站的其他許可權設定，以防止 Project 2 共用網站的存取權，並防止其他人要求存取網站。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="6ccfe-117">如需設定詳細資料，請參閱[SharePoint 高管制小組的設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="6ccfe-118">步驟2：設定保留標籤的 DLP 原則和基礎網站</span><span class="sxs-lookup"><span data-stu-id="6ccfe-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="6ccfe-119">首先，Contoso 系統管理員會將現有的**高度機密**保留標籤套用至專案2小組之基礎 SharePoint 網站的 [**檔**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-119">First, Contoso admins applied the existing **Highly Confidential** retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="6ccfe-120">接下來，他們建立新的 DLP 原則，名稱為**Project 2** ：</span><span class="sxs-lookup"><span data-stu-id="6ccfe-120">Next, they created a new DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="6ccfe-121">使用高度機密保留標籤。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-121">Uses the Highly Confidential retention label.</span></span>
- <span data-ttu-id="6ccfe-122">當使用者嘗試在 Contoso 以外的 Project 2 小組中共用檔案時，封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="6ccfe-123">如需設定詳細資料，請參閱[使用保留標籤和 DLP 保護小組中](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)的檔案。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="6ccfe-124">步驟3：為專案2小組建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="6ccfe-124">Step 3: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="6ccfe-125">Contoso admins 建立一個名為「**專案 2** 」的新敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="6ccfe-125">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="6ccfe-126">需要加密。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-126">Requires encryption.</span></span>
- <span data-ttu-id="6ccfe-127">允許 Project 2X Microsoft 365 群組的共同撰寫許可權。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-127">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="6ccfe-128">以下是專案2小組所產生的設定。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-128">Here is the resulting configuration of the Project 2X team.</span></span>

![專案2小組的產生設定](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="6ccfe-130">基礎專案 2 SharePoint 網站的 [檔] 區段中的檔案受到下列保護：</span><span class="sxs-lookup"><span data-stu-id="6ccfe-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="6ccfe-131">網站許可權，只允許存取 Project 2 之專案 365 2 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-131">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="6ccfe-132">高度機密保留標籤，會自動指派給新的檔案。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="6ccfe-133">一個 DLP 原則，使用高度機密保留標籤和設定，以封鎖檔案與外部使用者共用。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="6ccfe-134">專案2敏感度標籤，其會在移動或複製到網站時，與檔案一起旅行的加密和許可權。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="6ccfe-135">以下是儲存在基礎專案2網站中的檔案範例，具有高管制保留標籤，以及指派 Project 2/2 敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![儲存在基準專案2網站中的檔案範例](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="6ccfe-137">步驟4：訓練有素的專案2小組成員</span><span class="sxs-lookup"><span data-stu-id="6ccfe-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="6ccfe-138">Contoso 安全性人員會在必要課程中訓練專案2小組成員：</span><span class="sxs-lookup"><span data-stu-id="6ccfe-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="6ccfe-139">如何存取新的 Project 2 小組、使用會議和聊天，以及如何在小組檔案上共同作業。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="6ccfe-140">如何在小組中建立新檔案，並上傳在本機建立的新檔案。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="6ccfe-141">有關 DLP 原則如何在外部共用檔案的示範。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="6ccfe-142">如何使用專案2敏感度標籤來標示檔案。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="6ccfe-143">示範 Project 2X 標籤如何保護檔案的示範，甚至是在離開小組時。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="6ccfe-144">最終結果是一種安全的環境，在此環境中，Project 2 小組成員在安全的環境中共同合作，以進行聊天、會議及檔。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="6ccfe-145">在幾個實例中，Project 2 小組成員會將專案2標籤所保護的檔案下載到本機磁片磁碟機，以供離線工作使用。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="6ccfe-146">不過，當您開啟認證時出現要求時，使用者已意識到其錯誤並加以刪除。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="6ccfe-147">由於小組的共同作業環境和 Microsoft 365 的安全性功能，Project 2X 的詳細資料會在專案期間內保密。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="6ccfe-148">Contoso 宣告其計畫，而且正在將新產品及服務推出給其客戶和投資者的愉悅感，以及其競爭者的 chagrin。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="6ccfe-149">下一步</span><span class="sxs-lookup"><span data-stu-id="6ccfe-149">Next step</span></span>

<span data-ttu-id="6ccfe-150">[部署](deploy-microsoft-365-enterprise.md)您組織中的 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="6ccfe-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ccfe-151">請參閱</span><span class="sxs-lookup"><span data-stu-id="6ccfe-151">See also</span></span>

<span data-ttu-id="6ccfe-152">[Microsoft 365 生產力資源庫](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="6ccfe-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
