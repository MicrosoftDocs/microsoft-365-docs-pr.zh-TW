---
title: Contoso Corporation 的最大機密專案的隔離團隊
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
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
ms.openlocfilehash: b8794502afcb77a8e597a1b05dfc92acd093f23a
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656064"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="ebf44-103">Contoso Corporation 的最大機密專案的隔離團隊</span><span class="sxs-lookup"><span data-stu-id="ebf44-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="ebf44-104">在執行異地的執行中，Contoso 的 CEO 會定購一套新的產品和服務，並在今後五年中，讓 Contoso 的贏利翻倍。</span><span class="sxs-lookup"><span data-stu-id="ebf44-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="ebf44-105">開發商務、工程及市場計畫的重要專案是「 **專案 2** 」和整個公司的主要人員都是 recruited。</span><span class="sxs-lookup"><span data-stu-id="ebf44-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="ebf44-106">調查和開發的時程表已緊密，這表示共同作業必須有效並提供安全的會議、進行中的交談及檔案儲存。</span><span class="sxs-lookup"><span data-stu-id="ebf44-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="ebf44-107">專案2所產生的可傳送作業是商務計畫、產品及工程規格，以及 Word、Excel 及 PowerPoint 檔案形式的行銷材料和排程。</span><span class="sxs-lookup"><span data-stu-id="ebf44-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="ebf44-108">由於其敏感性，對這些檔案的存取權如下：</span><span class="sxs-lookup"><span data-stu-id="ebf44-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="ebf44-109">限制為 Project 2 小組成員與資深領導。</span><span class="sxs-lookup"><span data-stu-id="ebf44-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="ebf44-110">使用許可權進行加密及保護，只允許存取專案2小組成員和高級領導，即使檔案是在其安全資料夾以外的地方發佈也是一樣。</span><span class="sxs-lookup"><span data-stu-id="ebf44-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="ebf44-111">Contoso IT 人員使用具有專案2的 [安全性隔離的團隊](secure-teams-security-isolation.md) 和這些步驟。</span><span class="sxs-lookup"><span data-stu-id="ebf44-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="ebf44-112">步驟1：建立私人團隊</span><span class="sxs-lookup"><span data-stu-id="ebf44-112">Step 1: Created a private team</span></span>

<span data-ttu-id="ebf44-113">首先，為了保護小組的底層 SharePoint 網站的存取權，Contoso IT 管理員設定建議的 [SharePoint 存取原則](../security/office-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf44-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="ebf44-114">接下來，Contoso IT 管理員建立一個名為 Project 2 的新私人團隊，並新增專案2個人的使用者帳戶為成員。</span><span class="sxs-lookup"><span data-stu-id="ebf44-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="ebf44-115">他們也會設定小組，使只有專案2小組擁有者可以建立專用通道。</span><span class="sxs-lookup"><span data-stu-id="ebf44-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="ebf44-116">如需設定詳細資料，請參閱 [建立私人團隊](secure-teams-security-isolation.md#create-a-private-team)。</span><span class="sxs-lookup"><span data-stu-id="ebf44-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="ebf44-117">步驟2：為專案2小組建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="ebf44-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="ebf44-118">Contoso admins 建立一個名為「 **專案 2** 」的新敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="ebf44-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="ebf44-119">已啟用加密。</span><span class="sxs-lookup"><span data-stu-id="ebf44-119">Enabled encryption.</span></span>
- <span data-ttu-id="ebf44-120">允許 Project 2X Microsoft 365 群組 Co-Author 許可權。</span><span class="sxs-lookup"><span data-stu-id="ebf44-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="ebf44-121">「高層領導」群組允許的檢視器許可權。</span><span class="sxs-lookup"><span data-stu-id="ebf44-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="ebf44-122">封鎖對非管理裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="ebf44-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="ebf44-123">基礎專案 2 SharePoint 網站 **的 [檔** ] 區段中的檔案受到下列保護：</span><span class="sxs-lookup"><span data-stu-id="ebf44-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="ebf44-124">網站許可權，其僅允許對 Project 2/365 2 群組成員的完整許可權，以及對資深領導群組的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="ebf44-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="ebf44-125">專案2敏感度標籤，其會在移動或複製到網站時，與檔案一起旅行的加密和許可權。</span><span class="sxs-lookup"><span data-stu-id="ebf44-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="ebf44-126">如需設定詳細資料，請參閱 [建立靈敏度標籤](secure-teams-security-isolation.md#create-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="ebf44-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="ebf44-127">步驟3：設定基礎 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="ebf44-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="ebf44-128">首先，為了保護小組的底層 SharePoint 網站的存取權，Contoso IT 管理員設定建議的 [SharePoint 存取原則](../security/office-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf44-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="ebf44-129">接下來，他們為網站設定其他許可權設定：</span><span class="sxs-lookup"><span data-stu-id="ebf44-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="ebf44-130">避免專案2群組成員共用網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="ebf44-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="ebf44-131">如需設定詳細資料，請參閱 [使用安全隔離的團隊 SharePoint 設定](secure-teams-security-isolation.md#sharepoint-settings)。</span><span class="sxs-lookup"><span data-stu-id="ebf44-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="ebf44-132">以取得資深領導群組的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="ebf44-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="ebf44-133">接下來，他們設定網站的其他許可權設定，以防止 Project 2X 群組成員共用網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="ebf44-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="ebf44-134">建立專案2的專用通道時，群組擁有者會停用來賓共用，並將預設的共用連結設定為 [ **特定人員** ] 值。</span><span class="sxs-lookup"><span data-stu-id="ebf44-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="ebf44-135">以下是具有安全性隔離之專案2小組所產生的設定。</span><span class="sxs-lookup"><span data-stu-id="ebf44-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![專案2小組的產生設定](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="ebf44-137">步驟4：訓練有素的專案2小組成員</span><span class="sxs-lookup"><span data-stu-id="ebf44-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="ebf44-138">Contoso 安全性人員會在必要課程中訓練專案2小組成員：</span><span class="sxs-lookup"><span data-stu-id="ebf44-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="ebf44-139">如何存取新的 Project 2 小組、使用會議和聊天，以及如何在小組檔案上共同作業。</span><span class="sxs-lookup"><span data-stu-id="ebf44-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="ebf44-140">如何在小組中建立新檔案，並上傳在本機建立的新檔案。</span><span class="sxs-lookup"><span data-stu-id="ebf44-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="ebf44-141">如何使用專案2敏感度標籤來標示檔案。</span><span class="sxs-lookup"><span data-stu-id="ebf44-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="ebf44-142">示範 Project 2X 標籤如何保護檔案的示範，甚至是在離開小組時。</span><span class="sxs-lookup"><span data-stu-id="ebf44-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="ebf44-143">最終結果是一種安全的環境，在此環境中，Project 2 小組成員在安全的環境中共同合作，以進行聊天、會議及檔。</span><span class="sxs-lookup"><span data-stu-id="ebf44-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="ebf44-144">以下是儲存在基礎專案2網站中的檔案範例，並指派 Project 2 敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="ebf44-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![儲存在基準專案2網站中的檔案範例](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="ebf44-146">在幾個實例中，Project 2 小組成員會將專案2標籤所保護的檔案下載到本機磁片磁碟機，以供離線工作使用。</span><span class="sxs-lookup"><span data-stu-id="ebf44-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="ebf44-147">不過，當您開啟認證時出現要求時，使用者已意識到其錯誤並加以刪除。</span><span class="sxs-lookup"><span data-stu-id="ebf44-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="ebf44-148">由於小組的共同作業環境和 Microsoft 365 的安全性功能，Project 2X 的詳細資料會在專案期間內保密。</span><span class="sxs-lookup"><span data-stu-id="ebf44-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="ebf44-149">Contoso 宣告其計畫，而且正在將新產品及服務推出給其客戶和投資者的愉悅感，以及其競爭者的 chagrin。</span><span class="sxs-lookup"><span data-stu-id="ebf44-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="ebf44-150">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ebf44-150">Next step</span></span>

<span data-ttu-id="ebf44-151">在您的組織中[部署具有安全性隔離的團隊](secure-teams-security-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf44-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

