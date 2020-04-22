---
title: 使用敏感度標籤保護小組中的檔案
f1.keywords:
- NOCSH
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
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 摘要：套用敏感度標籤以保護高度機密小組中的檔案。
ms.openlocfilehash: c36daef7f28ad8bd3306fd7f3f7f1558a3594e68
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637613"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="43a71-103">使用敏感度標籤保護小組中的檔案</span><span class="sxs-lookup"><span data-stu-id="43a71-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="43a71-104">適用於高度管制資料的敏感度標籤可讓任何人套用至任何檔案，但是高度機密小組不同，他們需要自己的標籤或子標籤，使指派的檔案能夠：</span><span class="sxs-lookup"><span data-stu-id="43a71-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a highly confidential team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="43a71-105">進行個別加密。</span><span class="sxs-lookup"><span data-stu-id="43a71-105">Are individually encrypted.</span></span>
- <span data-ttu-id="43a71-106">包含自訂權限，使其只能由小組成員開啟。</span><span class="sxs-lookup"><span data-stu-id="43a71-106">Contain custom permissions so that only members of the team can open it.</span></span>

<span data-ttu-id="43a71-107">若要為儲存在小組的基礎 SharePoint 網站中的檔案達成這個額外的安全性層級，您必須設定自訂的敏感度標籤，而此標籤可以是單獨的標籤，或是高度管制資料之一般標籤的子標籤。</span><span class="sxs-lookup"><span data-stu-id="43a71-107">To accomplish this additional level of security for files stored in the underlying SharePoint site of a team, you must configure a customized sensitivity label that is either its own label or a sublabel of the general label for highly regulated data.</span></span> <span data-ttu-id="43a71-108">只有小組成員才可在其標籤清單中看到自訂標籤或子標籤。</span><span class="sxs-lookup"><span data-stu-id="43a71-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="43a71-109">當您需要少量標籤、可同時用於全域使用和個別的私人小組時，請使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="43a71-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="43a71-110">當您有大量標籤，或想要將高度機密小組的標籤整理到高度管制標籤之下時，請使用敏感度子標籤。</span><span class="sxs-lookup"><span data-stu-id="43a71-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for highly confidential teams under the highly regulated label.</span></span>

<span data-ttu-id="43a71-111">依照[下列指示](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)，設定具有下列設定的不同標籤或子標籤：</span><span class="sxs-lookup"><span data-stu-id="43a71-111">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="43a71-112">標籤或子標籤的名稱中包含小組的名稱</span><span class="sxs-lookup"><span data-stu-id="43a71-112">The name of the label or sublabel contains the name of the team</span></span>
- <span data-ttu-id="43a71-113">已啟用加密</span><span class="sxs-lookup"><span data-stu-id="43a71-113">Encryption is enabled</span></span>
- <span data-ttu-id="43a71-114">小組的 Microsoft 365 群組具有共同撰寫權限</span><span class="sxs-lookup"><span data-stu-id="43a71-114">The Microsoft 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="43a71-115">建立之後，請為您的使用者發佈新的標籤或子標籤，讓他們能夠在檔案上傳至小組前先在本機的檔案套用標籤，或等到檔案儲存至小組時再套用。</span><span class="sxs-lookup"><span data-stu-id="43a71-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="43a71-116">以下是高度機密小組使用敏感度標籤進行檔案加密和權限授與的設定。</span><span class="sxs-lookup"><span data-stu-id="43a71-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![公開小組的基準層級保護。](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="43a71-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="43a71-118">See Also</span></span>

[<span data-ttu-id="43a71-119">在 Microsoft Teams 中保護檔案</span><span class="sxs-lookup"><span data-stu-id="43a71-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="43a71-120">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="43a71-120">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
