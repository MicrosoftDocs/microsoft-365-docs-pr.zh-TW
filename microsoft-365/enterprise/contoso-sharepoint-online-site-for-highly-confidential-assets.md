---
title: Contoso Corporation 高度機密數位資產的 SharePoint 網站
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
description: 摘要： Contoso 如何針對高管制資料執行 SharePoint 網站，以更輕鬆地在其資訊檢索小組之間合作。
ms.openlocfilehash: 0a4bc2f685cf015611da62ebbed000218f37f31e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634249"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="1bc04-103">Contoso Corporation 高度機密數位資產的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="1bc04-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="1bc04-104">Contoso 最有價值的資產是其智慧財產權，其形式為商業機密（如專有製造技術）和開發中產品的設計規格。</span><span class="sxs-lookup"><span data-stu-id="1bc04-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="1bc04-105">這些資產是以數位格式，最初儲存為 SharePoint Server 2016 網站上的檔案。</span><span class="sxs-lookup"><span data-stu-id="1bc04-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="1bc04-106">當 Contoso 部署 Microsoft 365 企業版時，他們想要將其內部部署數位資產轉變為雲端，以便在巴黎、莫斯科、紐約、北京和 Bangalore 中，跨研究小組輕鬆存取和更開啟的共同作業。</span><span class="sxs-lookup"><span data-stu-id="1bc04-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="1bc04-107">不過，由於其敏感性，對這些檔案的存取權必須是：</span><span class="sxs-lookup"><span data-stu-id="1bc04-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="1bc04-108">限制于允許其存取的一組人員。</span><span class="sxs-lookup"><span data-stu-id="1bc04-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="1bc04-109">使用資料遺失防護（DLP）原則加以保護，以防止使用者在網站外散佈。</span><span class="sxs-lookup"><span data-stu-id="1bc04-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="1bc04-110">以防止未授權使用者存取其內容的許可權進行加密及保護，即使這些使用者是在網站外發佈。</span><span class="sxs-lookup"><span data-stu-id="1bc04-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="1bc04-111">Contoso IT 部門的安全性和 SharePoint 管理員決定[針對高管制資料使用 SharePoint 網站](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="1bc04-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="1bc04-112">Contoso 使用這些步驟來建立及保護其研究小組的 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="1bc04-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="1bc04-113">步驟1：建立私人 SharePoint 小組網站</span><span class="sxs-lookup"><span data-stu-id="1bc04-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="1bc04-114">為了保護 SharePoint 網站的存取權，Contoso IT 已設定[建議的 SharePoint 存取原則](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1bc04-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="1bc04-115">接下來，Contoso IT 管理員為位於巴黎、莫斯科、紐約、北京和 Bangalore 辦事處中的研究人員，編譯器中的使用者帳戶清單。</span><span class="sxs-lookup"><span data-stu-id="1bc04-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="1bc04-116">接下來，Contoso IT 系統管理員建立一個名為「**調查**」的新私人小組網站，並新增其調查人員的所有使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1bc04-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="1bc04-117">然後，他們為網站設定其他許可權設定，以防止研究人員共用網站的存取權，以及防止非工作人員要求存取網站。</span><span class="sxs-lookup"><span data-stu-id="1bc04-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="1bc04-118">步驟2：設定適用于限制性 DLP 原則的網站</span><span class="sxs-lookup"><span data-stu-id="1bc04-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="1bc04-119">首先，Contoso 系統管理員會將現有的**高度機密**保留標籤套用至「**資訊檢索**」網站的 Documents 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1bc04-119">First, Contoso admins applied the existing **Highly Confidential** retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="1bc04-120">接下來，他們建立名為「**調查**」的新 DLP 原則：</span><span class="sxs-lookup"><span data-stu-id="1bc04-120">Next, they created a new DLP policy named **Research** that:</span></span>

- <span data-ttu-id="1bc04-121">使用**高度機密**保留標籤。</span><span class="sxs-lookup"><span data-stu-id="1bc04-121">Uses the **Highly Confidential** retention label.</span></span> 
- <span data-ttu-id="1bc04-122">當使用者嘗試在 Contoso 以外的**調研**網站上共用數位資產時，封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="1bc04-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="1bc04-123">如需設定詳細資料，請參閱[使用保留標籤和 DLP 保護 SharePoint](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)檔案。</span><span class="sxs-lookup"><span data-stu-id="1bc04-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-3-created-a-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="1bc04-124">步驟3：建立網站的靈敏度 sublabel</span><span class="sxs-lookup"><span data-stu-id="1bc04-124">Step 3: Created a sensitivity sublabel for the site</span></span>

<span data-ttu-id="1bc04-125">Contoso admins 為**高度機密**標籤的「**調查小組**」建立了新的靈敏度 sublabel，其為下列專案：</span><span class="sxs-lookup"><span data-stu-id="1bc04-125">Contoso admins created a new sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="1bc04-126">需要加密。</span><span class="sxs-lookup"><span data-stu-id="1bc04-126">Requires encryption.</span></span>
- <span data-ttu-id="1bc04-127">允許用於**調查**Microsoft 365 群組的共同撰寫許可權</span><span class="sxs-lookup"><span data-stu-id="1bc04-127">Allows Co-Author permissions for the **Research** Microsoft 365 group</span></span>
- <span data-ttu-id="1bc04-128">適用于**調查**Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="1bc04-128">Applies to the **Research** Microsoft 365 group</span></span>

<span data-ttu-id="1bc04-129">以下是高度機密資產之**研究**小組網站的結果設定。</span><span class="sxs-lookup"><span data-stu-id="1bc04-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![針對高度機密資產的「調查小組網站」所產生的設定](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="1bc04-131">「**調查**網站」資料夾中的檔案受到下列保護：</span><span class="sxs-lookup"><span data-stu-id="1bc04-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="1bc04-132">網站許可權，只允許存取「**調查**」 Microsoft 365 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1bc04-132">The site permissions, which only allow access to members of the **Research** Microsoft 365 group.</span></span>
- <span data-ttu-id="1bc04-133">「**調查**DLP」原則，其使用**高度機密**保留標籤和設定，以防止與外部使用者共用檔案。</span><span class="sxs-lookup"><span data-stu-id="1bc04-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="1bc04-134">「**研究小組**敏感度」 sublabel，其會在移動或複製到**資訊檢索**網站時，與檔案一起旅行的加密和許可權。</span><span class="sxs-lookup"><span data-stu-id="1bc04-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="1bc04-135">以下是以「調查**小組**敏感度 sublabel 指派」儲存在「**資訊檢索**」網站中的檔案範例。</span><span class="sxs-lookup"><span data-stu-id="1bc04-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![針對高度機密資產的「調查小組網站」所產生的設定](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="1bc04-137">步驟4：遷移內部部署 SharePoint 研究資料</span><span class="sxs-lookup"><span data-stu-id="1bc04-137">Step 4: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="1bc04-138">Contoso admins 會將內部部署 SharePoint Server 2016 網站中的所有內部部署調查檔案，移至新「**調研**SharePoint」網站中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="1bc04-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-5-trained-their-researchers"></a><span data-ttu-id="1bc04-139">步驟5：訓練其研究員</span><span class="sxs-lookup"><span data-stu-id="1bc04-139">Step 5: Trained their researchers</span></span>

<span data-ttu-id="1bc04-140">Contoso 安全性人員會在必要的課程中訓練**調查**Microsoft 365 群組的成員：</span><span class="sxs-lookup"><span data-stu-id="1bc04-140">Contoso security staff trained the members of the **Research** Microsoft 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="1bc04-141">如何存取新的**調研**網站及其現有的檔案。</span><span class="sxs-lookup"><span data-stu-id="1bc04-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="1bc04-142">如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。</span><span class="sxs-lookup"><span data-stu-id="1bc04-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="1bc04-143">示範「**調查**DLP」原則如何封鎖外部共用檔案。</span><span class="sxs-lookup"><span data-stu-id="1bc04-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="1bc04-144">如何使用「**研究小組**敏感度」 sublabel 為檔案加上標籤。</span><span class="sxs-lookup"><span data-stu-id="1bc04-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="1bc04-145">示範「**調研組**」子標籤如何保護檔案，甚至是在該檔案從網站洩漏時。</span><span class="sxs-lookup"><span data-stu-id="1bc04-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="1bc04-146">最終結果是一種安全的環境，在此環境中，研究人員可以在包含調研資訊之檔案的安全環境中，于 Contoso 間共同作業。</span><span class="sxs-lookup"><span data-stu-id="1bc04-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="1bc04-147">如果使用「**調查小組**」的調研檔 sublabel 出「**調查**網站」，它會加密，而且只能存取使用有效使用者帳號憑證的「**調查**Microsoft 365 群組」的成員。</span><span class="sxs-lookup"><span data-stu-id="1bc04-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Microsoft 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="1bc04-148">下一步</span><span class="sxs-lookup"><span data-stu-id="1bc04-148">Next step</span></span>

<span data-ttu-id="1bc04-149">[部署](deploy-microsoft-365-enterprise.md)您組織中的 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="1bc04-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bc04-150">請參閱</span><span class="sxs-lookup"><span data-stu-id="1bc04-150">See also</span></span>

<span data-ttu-id="1bc04-151">[Microsoft 365 生產力資源庫](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="1bc04-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
