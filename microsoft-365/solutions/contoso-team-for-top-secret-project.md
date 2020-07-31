---
title: Contoso Corporation 的最大機密專案的隔離團隊
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何使用具有安全性隔離的小組進行重要專案，以開發新的產品和服務套件。
ms.openlocfilehash: f7b38a7ef43cdb50b46f3e37f855f490dc32cfdf
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521622"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="4626a-103">Contoso Corporation 的最大機密專案的隔離團隊</span><span class="sxs-lookup"><span data-stu-id="4626a-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="4626a-104">在執行異地的執行中，Contoso 的 CEO 會定購一套新的產品和服務，並在今後五年中，讓 Contoso 的贏利翻倍。</span><span class="sxs-lookup"><span data-stu-id="4626a-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="4626a-105">開發商務、工程及市場計畫的重要專案是「**專案 2** 」和整個公司的主要人員都是 recruited。</span><span class="sxs-lookup"><span data-stu-id="4626a-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="4626a-106">調查和開發的時程表已緊密，這表示共同作業必須有效並提供安全的會議、進行中的交談及檔案儲存。</span><span class="sxs-lookup"><span data-stu-id="4626a-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="4626a-107">專案2所產生的可傳送作業是商務計畫、產品及工程規格，以及 Word、Excel 及 PowerPoint 檔案形式的行銷材料和排程。</span><span class="sxs-lookup"><span data-stu-id="4626a-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="4626a-108">由於其敏感性，對這些檔案的存取權如下：</span><span class="sxs-lookup"><span data-stu-id="4626a-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="4626a-109">限制為 Project 2 小組成員。</span><span class="sxs-lookup"><span data-stu-id="4626a-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="4626a-110">以只允許存取專案2小組成員的許可權進行加密及保護，即使這些檔案是在其安全資料夾以外的地方發佈也是一樣。</span><span class="sxs-lookup"><span data-stu-id="4626a-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="4626a-111">Contoso IT 人員使用具有專案2的[安全性隔離的團隊](secure-teams-security-isolation.md)和這些步驟。</span><span class="sxs-lookup"><span data-stu-id="4626a-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="4626a-112">步驟1：建立私人團隊</span><span class="sxs-lookup"><span data-stu-id="4626a-112">Step 1: Created a private team</span></span>

<span data-ttu-id="4626a-113">首先，為了保護小組的底層 SharePoint 網站的存取權，Contoso IT 管理員設定建議的[SharePoint 存取原則](../enterprise/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4626a-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="4626a-114">接下來，Contoso IT 管理員建立一個名為 Project 2 的新私人團隊，並新增專案2個人的使用者帳戶為成員。</span><span class="sxs-lookup"><span data-stu-id="4626a-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="4626a-115">如需設定詳細資料，請參閱[建立私人團隊](secure-teams-security-isolation.md#create-a-private-team)。</span><span class="sxs-lookup"><span data-stu-id="4626a-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="4626a-116">步驟2：為專案2小組建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="4626a-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="4626a-117">Contoso admins 建立一個名為「**專案 2** 」的新敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="4626a-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="4626a-118">需要加密。</span><span class="sxs-lookup"><span data-stu-id="4626a-118">Requires encryption.</span></span>
- <span data-ttu-id="4626a-119">允許 Project 2X Microsoft 365 群組的共同撰寫許可權。</span><span class="sxs-lookup"><span data-stu-id="4626a-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="4626a-120">基礎專案 2 SharePoint 網站**的 [檔**] 區段中的檔案受到下列保護：</span><span class="sxs-lookup"><span data-stu-id="4626a-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="4626a-121">網站許可權，只允許存取 Project 2 之專案 365 2 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4626a-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="4626a-122">專案2敏感度標籤，其會在移動或複製到網站時，與檔案一起旅行的加密和許可權。</span><span class="sxs-lookup"><span data-stu-id="4626a-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="4626a-123">如需設定詳細資料，請參閱[建立靈敏度標籤](secure-teams-security-isolation.md#create-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="4626a-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="4626a-124">步驟3：設定基礎 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="4626a-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="4626a-125">首先，為了保護小組的底層 SharePoint 網站的存取權，Contoso IT 管理員設定建議的[SharePoint 存取原則](../enterprise/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4626a-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="4626a-126">接下來，他們設定網站的其他許可權設定，以防止 Project 2 共用網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="4626a-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="4626a-127">如需設定詳細資料，請參閱[使用安全隔離的團隊 SharePoint 設定](secure-teams-security-isolation.md#sharepoint-settings)。</span><span class="sxs-lookup"><span data-stu-id="4626a-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="4626a-128">以下是專案2小組所產生的設定。</span><span class="sxs-lookup"><span data-stu-id="4626a-128">Here is the resulting configuration of the Project 2X team.</span></span>

![專案2小組的產生設定](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="4626a-130">步驟4：訓練有素的專案2小組成員</span><span class="sxs-lookup"><span data-stu-id="4626a-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="4626a-131">Contoso 安全性人員會在必要課程中訓練專案2小組成員：</span><span class="sxs-lookup"><span data-stu-id="4626a-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="4626a-132">如何存取新的 Project 2 小組、使用會議和聊天，以及如何在小組檔案上共同作業。</span><span class="sxs-lookup"><span data-stu-id="4626a-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="4626a-133">如何在小組中建立新檔案，並上傳在本機建立的新檔案。</span><span class="sxs-lookup"><span data-stu-id="4626a-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="4626a-134">有關 DLP 原則如何在外部共用檔案的示範。</span><span class="sxs-lookup"><span data-stu-id="4626a-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="4626a-135">如何使用專案2敏感度標籤來標示檔案。</span><span class="sxs-lookup"><span data-stu-id="4626a-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="4626a-136">示範 Project 2X 標籤如何保護檔案的示範，甚至是在離開小組時。</span><span class="sxs-lookup"><span data-stu-id="4626a-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="4626a-137">最終結果是一種安全的環境，在此環境中，Project 2 小組成員在安全的環境中共同合作，以進行聊天、會議及檔。</span><span class="sxs-lookup"><span data-stu-id="4626a-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="4626a-138">以下是儲存在基礎專案2網站中的檔案範例，並指派 Project 2 敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="4626a-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![儲存在基準專案2網站中的檔案範例](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="4626a-140">在幾個實例中，Project 2 小組成員會將專案2標籤所保護的檔案下載到本機磁片磁碟機，以供離線工作使用。</span><span class="sxs-lookup"><span data-stu-id="4626a-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="4626a-141">不過，當您開啟認證時出現要求時，使用者已意識到其錯誤並加以刪除。</span><span class="sxs-lookup"><span data-stu-id="4626a-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="4626a-142">由於小組的共同作業環境和 Microsoft 365 的安全性功能，Project 2X 的詳細資料會在專案期間內保密。</span><span class="sxs-lookup"><span data-stu-id="4626a-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="4626a-143">Contoso 宣告其計畫，而且正在將新產品及服務推出給其客戶和投資者的愉悅感，以及其競爭者的 chagrin。</span><span class="sxs-lookup"><span data-stu-id="4626a-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="4626a-144">下一步</span><span class="sxs-lookup"><span data-stu-id="4626a-144">Next step</span></span>

<span data-ttu-id="4626a-145">在您的組織中[部署具有安全性隔離的團隊](secure-teams-security-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="4626a-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

