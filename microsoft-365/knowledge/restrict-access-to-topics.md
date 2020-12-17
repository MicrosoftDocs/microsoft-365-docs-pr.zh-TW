---
title: 限制存取主題
description: 如何排除主題以避免被探索。
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698869"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="2ff8f-103">限制對主題經驗中主題的存取權</span><span class="sxs-lookup"><span data-stu-id="2ff8f-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="2ff8f-104">在主題經驗中，您組織中的專案關係人可能會想要確定沒有探索特定主題，而且不會向您的授權使用者公開。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="2ff8f-105">例如，您可能正在處理不想要公開其相關資訊的專案。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="2ff8f-106">雖然 Office 365 網站、檔案及其他資源的許可權會讓使用者無法在主題中查看機密資訊，但還有其他一些防範措施可以避免探索特定主題。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="2ff8f-107">雖然知識系統管理員會控制知識網路設定，以防止發現主題，但知識管理員及其他專案關係人必須知道這是如何進行的，如此才能協同運作。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="2ff8f-108">本文說明防止主題透過 AI 識別或在您的環境中另存為其他安全性保護的方式。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="2ff8f-109">請務必注意，在主題經驗中，如果使用者不允許透過 Office 365 許可權來存取任何專案，就不允許使用者在該主題中查看任何專案。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="2ff8f-110">即使使用者可以查看主題，但他們的檔案、網站和頁面沒有可供查看的 Office 365 許可權。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="2ff8f-111">確定正確設定敏感檔案的許可權應該是主要的安全性保護。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="2ff8f-112">防止識別主題</span><span class="sxs-lookup"><span data-stu-id="2ff8f-112">Prevent topics from being identified</span></span>

<span data-ttu-id="2ff8f-113">知識管理員可以防止在初始編制索引中找到特定主題的存取權。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="2ff8f-114">有兩種方法可在 Microsoft 365 系統管理中心的 [知識網路系統管理員設定] 中執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="2ff8f-115">[選取要從主題探索中排除的 SharePoint 網站](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)：您可以使用此設定來防止特定 SharePoint 網站在主題中進行編目。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="2ff8f-116">[依名稱排除主題](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)：系統管理員可以使用此設定，以防止名稱探索特定主題。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="2ff8f-117">在 [知識網路系統管理員] 設定中，系統管理員可以上傳要排除在 CSV 檔案中的主題清單。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="2ff8f-118">您可以排除具有主題名稱的確切或部分相符的主題。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="2ff8f-119">防止特定使用者查看主題</span><span class="sxs-lookup"><span data-stu-id="2ff8f-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="2ff8f-120">知識系統管理員也可以 [選擇誰可以查看組織中的主題](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="2ff8f-121">此設定可讓您選取哪些授權的使用者可以查看所有主題。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="2ff8f-122">例如，在試驗環境中，您可能只想讓一小組使用者能夠查看主題。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="2ff8f-123">移除要查看的主題</span><span class="sxs-lookup"><span data-stu-id="2ff8f-123">Remove topics from being viewed</span></span>

<span data-ttu-id="2ff8f-124">知識管理員可以選擇 [移除主題](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) ，讓使用者無法再看到這些主題。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="2ff8f-125">在 **主題中心** 的 [**管理主題**] 頁面上，知識管理員可以選擇拒絕特定主題，以防止其被查看。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="2ff8f-126">您可以移除主題，不論其是否處於建議或確認的狀態。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="2ff8f-127">如有需要，您可以在以後將移除的主題重新加入為可查看的主題。</span><span class="sxs-lookup"><span data-stu-id="2ff8f-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="2ff8f-128">請參閱</span><span class="sxs-lookup"><span data-stu-id="2ff8f-128">See also</span></span>



  






