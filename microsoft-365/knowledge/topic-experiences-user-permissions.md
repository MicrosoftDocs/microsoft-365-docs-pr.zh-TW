---
title: 在 Microsoft 365 中管理主題許可權
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何在 Microsoft 365 中管理主題許可權。
ms.openlocfilehash: b42bcf25f7b7516fb2b8b6e6b052d94fa6c4ea94
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668185"
---
# <a name="manage-topic-permissions-in-microsoft-365"></a><span data-ttu-id="53be0-103">在 Microsoft 365 中管理主題許可權</span><span class="sxs-lookup"><span data-stu-id="53be0-103">Manage topic permissions in Microsoft 365</span></span>

<span data-ttu-id="53be0-104">您可以在 [Microsoft 365 admin center](https://admin.microsoft.com)中管理主題許可權設定。</span><span class="sxs-lookup"><span data-stu-id="53be0-104">You can manage topic permissions settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="53be0-105">您必須是全域系統管理員或 SharePoint 管理員，才可執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="53be0-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

<span data-ttu-id="53be0-106">您可以選擇 [主題許可權] 設定：</span><span class="sxs-lookup"><span data-stu-id="53be0-106">With topic permissions settings you can choose:</span></span>

- <span data-ttu-id="53be0-107">哪些使用者可以建立及編輯主題：在探索期間或編輯現有主題詳細資料時，建立未找到的新主題。</span><span class="sxs-lookup"><span data-stu-id="53be0-107">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic details.</span></span>
- <span data-ttu-id="53be0-108">哪些使用者可以管理主題：存取主題管理中心，並查看主題的反應，以及透過生命週期移動主題。</span><span class="sxs-lookup"><span data-stu-id="53be0-108">Which users can manage topics: Access the topic management center and view feedback on topics as well as move topics through the lifecycle.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="53be0-109">若要存取主題管理設定：</span><span class="sxs-lookup"><span data-stu-id="53be0-109">To access topics management settings:</span></span>

1. <span data-ttu-id="53be0-110">在 Microsoft 365 系統管理中心中，按一下 [ **設定**]，然後按一下 [ **組織設定**]。</span><span class="sxs-lookup"><span data-stu-id="53be0-110">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="53be0-111">在 [ **服務** ] 索引標籤上，按一下 [ **知識網路**]。</span><span class="sxs-lookup"><span data-stu-id="53be0-111">On the **Services** tab, click **Knowledge network**.</span></span>

    ![將人員連線至知識](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="53be0-113">選取 [ **主題許可權** ] 索引標籤。請參閱下列各節以取得每個設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="53be0-113">Select the **Topic permissions** tab. See the following sections for information about each setting.</span></span>

    ![知識網路-設定](../media/knowledge-network-settings-topic-permissions.png) 

## <a name="change-who-has-permissions-to-update-topic-details"></a><span data-ttu-id="53be0-115">變更誰有權更新主題詳細資料</span><span class="sxs-lookup"><span data-stu-id="53be0-115">Change who has permissions to update topic details</span></span>

<span data-ttu-id="53be0-116">若要更新誰有權建立及編輯主題：</span><span class="sxs-lookup"><span data-stu-id="53be0-116">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="53be0-117">在 [ **主題許可權** ] 索引標籤的 [ **誰可以建立及編輯主題**] 中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="53be0-117">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span>
2. <span data-ttu-id="53be0-118">您可以在 [ **誰可以建立及編輯主題** ] 頁面上，選取：</span><span class="sxs-lookup"><span data-stu-id="53be0-118">On the **Who can create and edit topics** page, you can select:</span></span>
    - <span data-ttu-id="53be0-119">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="53be0-119">**Everyone in your organization**</span></span>
    - <span data-ttu-id="53be0-120">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="53be0-120">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="53be0-121">**沒人**</span><span class="sxs-lookup"><span data-stu-id="53be0-121">**No one**</span></span>

    ![建立及編輯主題](../media/k-manage-who-can-create-and-edit.png)  

3. <span data-ttu-id="53be0-123">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="53be0-123">Select **Save**.</span></span>

<span data-ttu-id="53be0-124">若要更新誰具有管理主題的許可權：</span><span class="sxs-lookup"><span data-stu-id="53be0-124">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="53be0-125">在 [ **主題許可權** ] 索引標籤的 [ **誰可以管理主題**] 下，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="53be0-125">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span>
2. <span data-ttu-id="53be0-126">您可以在 [ **誰可以管理主題** ] 頁面上，選取：</span><span class="sxs-lookup"><span data-stu-id="53be0-126">On the **Who can manage topics** page, you can select:</span></span>
    - <span data-ttu-id="53be0-127">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="53be0-127">**Everyone in your organization**</span></span>
    - <span data-ttu-id="53be0-128">**選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="53be0-128">**Selected people or security groups**</span></span>

    ![管理主題](../media/k-manage-who-can-manage-topics.png)  

3. <span data-ttu-id="53be0-130">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="53be0-130">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="53be0-131">也請參閱</span><span class="sxs-lookup"><span data-stu-id="53be0-131">See also</span></span>

[<span data-ttu-id="53be0-132">在 Microsoft 365 中管理主題探索</span><span class="sxs-lookup"><span data-stu-id="53be0-132">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="53be0-133">在 Microsoft 365 中管理主題可見度</span><span class="sxs-lookup"><span data-stu-id="53be0-133">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="53be0-134">變更 Microsoft 365 主題中心的名稱</span><span class="sxs-lookup"><span data-stu-id="53be0-134">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
