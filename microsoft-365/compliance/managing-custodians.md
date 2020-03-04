---
title: 使用進階電子文件中的 custodians
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 進階電子文件的 custodian 管理工具可讓您管理的工作流程識別、 保留，以及收集與法律案件感興趣的人員相關聯的資料。
ms.openlocfilehash: 7d8ac1c67b4ddc3395bccb5ab699ce7df63f331d
ms.sourcegitcommit: 9a4084ce2b80bac883412e0ec956b6c0cc18d0f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2020
ms.locfileid: "42400910"
---
# <a name="work-with-custodians-in-advanced-ediscovery"></a><span data-ttu-id="48323-103">使用進階電子文件中的 custodians</span><span class="sxs-lookup"><span data-stu-id="48323-103">Work with custodians in Advanced eDiscovery</span></span>

<span data-ttu-id="48323-104">當組織回應法律調查，周圍識別，工作流程保留，以及收集可能相關的內容根據組織中的人員都 custodians 的相關資料。</span><span class="sxs-lookup"><span data-stu-id="48323-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="48323-105">在 [eDiscovery]，這些人員稱為*資料 custodians* （或只是*custodians*），且會定義為 「 人員擁有管理控制文件或電子檔案 」。</span><span class="sxs-lookup"><span data-stu-id="48323-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="48323-106">例如，電子郵件訊息的 custodian 可能包含相關郵件的信箱擁有者。</span><span class="sxs-lookup"><span data-stu-id="48323-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>  

<span data-ttu-id="48323-107">調查開始時，「 eDiscovery 」 小組必須快速識別所有相關 custodians 和資料來源與案例相關。</span><span class="sxs-lookup"><span data-stu-id="48323-107">When an investigation begins, the eDiscovery team must quickly identify all the relevant custodians and data sources related to the case.</span></span> <span data-ttu-id="48323-108">經過一段時間，custodians 和其資料來源的清單可能會增加或減少。</span><span class="sxs-lookup"><span data-stu-id="48323-108">Over time, the list of custodians and their data sources may increase or decrease.</span></span> <span data-ttu-id="48323-109">因此，組織必須維護識別、 保留，以及收集整個生命週期的情況下 custodial 內容周圍控制程序。</span><span class="sxs-lookup"><span data-stu-id="48323-109">As a result, organizations must maintain a controlled process around identifying, preserving, and collecting custodial content throughout the life cycle of a case.</span></span>

<span data-ttu-id="48323-110">在進階電子文件探索案例中，法務小組可以新增個人 custodians，為其組織中自動識別並保留 custodial 資料來源，例如 Exchange 信箱、 OneDrive 帳戶及 SharePoint 和小組網站。</span><span class="sxs-lookup"><span data-stu-id="48323-110">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="48323-111">使用進階電子文件中內建 custodian 管理工具，組織可以保護以防止不慎 （或蓄意） 刪除的電子儲存的資訊。</span><span class="sxs-lookup"><span data-stu-id="48323-111">By using the built-in custodian management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="48323-112">這可讓您排除的手動不必執行的合法持有處理程序很耗時及出錯程序。</span><span class="sxs-lookup"><span data-stu-id="48323-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span> 

<span data-ttu-id="48323-113">如需使用 custodians 的詳細資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="48323-113">For more information about working with custodians, see the following:</span></span> 

- [<span data-ttu-id="48323-114">將監管人新增至案例</span><span class="sxs-lookup"><span data-stu-id="48323-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="48323-115">管理案例中 custodians</span><span class="sxs-lookup"><span data-stu-id="48323-115">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="48323-116">檢視監管人活動</span><span class="sxs-lookup"><span data-stu-id="48323-116">View custodian activity</span></span>](view-custodian-activity.md)

## <a name="advanced-ediscovery-permissions"></a><span data-ttu-id="48323-117">進階電子文件的權限</span><span class="sxs-lookup"><span data-stu-id="48323-117">Advanced eDiscovery permissions</span></span>

<span data-ttu-id="48323-118">在進階電子文件，您可以使用內建的 eDiscovery 管理員角色群組的必要權限指派給法律現場，讓他們可以管理進階電子文件中的端對端工作流程。</span><span class="sxs-lookup"><span data-stu-id="48323-118">In Advanced eDiscovery, you can use the built-in eDiscovery Manager role group to assign the necessary permissions to legal investigators so they can manage the end-to-end workflow in Advanced eDiscovery.</span></span> <span data-ttu-id="48323-119">或者，您可以建立自訂角色群組之角色的子需要在進階電子文件中的案例中執行特定動作。</span><span class="sxs-lookup"><span data-stu-id="48323-119">Alternatively, you can create custom role groups with a subset of the roles necessary to perform certain actions in a case in Advanced eDiscovery.</span></span> <span data-ttu-id="48323-120">如需 eDiscovery 相關角色的詳細資訊，請參閱[指派安全性 & 合規性中心的 eDiscovery 權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="48323-120">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
