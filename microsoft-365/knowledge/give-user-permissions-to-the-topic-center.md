---
title: 將使用者許可權授與主題中心（預覽）
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何授與使用者在主題中心執行工作的許可權
ms.openlocfilehash: 0e4e05d0addfdb754459e67acfdff3f61c7c812e
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537359"
---
# <a name="give-user-permissions-to-the-topic-center-preview"></a><span data-ttu-id="07ccd-103">將使用者許可權授與主題中心（預覽）</span><span class="sxs-lookup"><span data-stu-id="07ccd-103">Give user permissions to the topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="07ccd-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="07ccd-104">The content in this article is for Project Cortex Private Preview.</span></span> [<span data-ttu-id="07ccd-105">進一步瞭解專案 Cortex</span><span class="sxs-lookup"><span data-stu-id="07ccd-105">Find out more about Project Cortex</span></span>](https://aka.ms/projectcortex) 

<span data-ttu-id="07ccd-106">若要在主題中心內運作，您必須具備必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="07ccd-106">In order to work in the topic center, you need to have the required permissions.</span></span> <span data-ttu-id="07ccd-107">您的系統管理員可以在執行[知識管理設定](set-up-knowledge-network.md)期間，將這些許可權指派給使用者，也可以在以後新增新的使用者。</span><span class="sxs-lookup"><span data-stu-id="07ccd-107">Your admin can assign these permissions to users during [knowledge management setup](set-up-knowledge-network.md), or new users can be added afterwards.</span></span>

<span data-ttu-id="07ccd-108">主題中心使用者可獲得兩組許可權：</span><span class="sxs-lookup"><span data-stu-id="07ccd-108">Topic center users can be given two sets of permissions:</span></span>

- <span data-ttu-id="07ccd-109">**建立及編輯主題**：建立新的主題或更新主題內容，例如描述、檔和相關人員</span><span class="sxs-lookup"><span data-stu-id="07ccd-109">**Create and edit topics**: Create new topics or update topic content such as the description, documents and associated persons</span></span>
- <span data-ttu-id="07ccd-110">**管理主題**：使用主題管理儀表板來查看整個組織中的主題。</span><span class="sxs-lookup"><span data-stu-id="07ccd-110">**Manage topics**: Use the Topic management dashboard to review topics across the organization.</span></span> <span data-ttu-id="07ccd-111">使用者可以執行諸如確認和拒絕未確認主題等動作。</span><span class="sxs-lookup"><span data-stu-id="07ccd-111">Users can perform actions such as confirming and rejecting unconfirmed topics.</span></span>

<span data-ttu-id="07ccd-112">使用者可以指定這兩組許可權，或只有一個使用者需要。</span><span class="sxs-lookup"><span data-stu-id="07ccd-112">A user can be given both sets of permissions, or only one if needed.</span></span> 

<span data-ttu-id="07ccd-113">若使用者沒有在安裝期間獲得許可權，系統管理員可以透過 Microsoft 365 系統管理中心授與使用者許可權：</span><span class="sxs-lookup"><span data-stu-id="07ccd-113">If a user is not given permissions during setup, an admin can do the following give users permissions through the Microsoft 365 admin center:</span></span>

<span data-ttu-id="07ccd-114">若要授與使用者管理主題的許可權：</span><span class="sxs-lookup"><span data-stu-id="07ccd-114">To give a user permissions to manage topics:</span></span>

1. <span data-ttu-id="07ccd-115">在 Microsoft 365 系統管理中心的功能窗格中，選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="07ccd-115">In the Microsoft 365 admin center, in the navigation pane, select **Set up**.</span></span>
2. <span data-ttu-id="07ccd-116">在 [**組織知識**] 區段的 **[連線人員至知識]** 底下，選取 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="07ccd-116">In the **Organizational Knowledge** section, under **Connect people to knowledge**, select **View**.</span></span>
3. <span data-ttu-id="07ccd-117">在 [連線**人員至知識]** 頁面上，選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="07ccd-117">On the **Connect people to knowledge** page, select **Manage**.</span></span>
4. <span data-ttu-id="07ccd-118">在 [**知識網路**] 頁面上，選取 [**主題許可權**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="07ccd-118">On the **Knowledge Network** page, select the **Topic permissions** tab.</span></span>
5. <span data-ttu-id="07ccd-119">在 [**主題許可權**] 索引標籤的 [**誰可以管理主題**] 底下，選取 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="07ccd-119">On the **Topic permissions** tab, under **Who can manage topics**, select **View**.</span></span>
6.  <span data-ttu-id="07ccd-120">在 [**可管理主題的人員**] 頁面上，將使用者新增至 [**僅限選取的使用者或安全性群組**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="07ccd-120">On the **Who can manage topics** page, add the user to the **Only selected users or security groups** box.</span></span>
7. <span data-ttu-id="07ccd-121">新增使用者後，請選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="07ccd-121">After adding your user, select **Add**.</span></span>
3. <span data-ttu-id="07ccd-122">在 [**誰可以建立及編輯主題**] 底下，選取 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="07ccd-122">Under the **Who can create and edit topics**, select **View**.</span></span>
4. <span data-ttu-id="07ccd-123">將使用者新增至 [**只選取的使用者或安全性群組**] 方塊。</span><span class="sxs-lookup"><span data-stu-id="07ccd-123">Add the user to the **Only selected users or security groups** box.</span></span>
5. <span data-ttu-id="07ccd-124">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07ccd-124">Select **Add**.</span></span>

<span data-ttu-id="07ccd-125">若要授與使用者建立及編輯主題的許可權：</span><span class="sxs-lookup"><span data-stu-id="07ccd-125">To give a user permissions to create and edit topics:</span></span>

1. <span data-ttu-id="07ccd-126">在 [**主題許可權**] 索引標籤的 [**誰可以建立及編輯主題**] 中，選取 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="07ccd-126">On the **Topic permissions** tab, under **Who can create and edit topics**, select **View**.</span></span>
2. <span data-ttu-id="07ccd-127">將使用者新增至 [**只選取的使用者或安全性群組**] 方塊。</span><span class="sxs-lookup"><span data-stu-id="07ccd-127">Add the user to the **Only selected users or security groups** box.</span></span>
3. <span data-ttu-id="07ccd-128">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07ccd-128">Select **Add**.</span></span>



## <a name="see-also"></a><span data-ttu-id="07ccd-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="07ccd-129">See Also</span></span>
  
[<span data-ttu-id="07ccd-130">與主題中心的主題搭配使用</span><span class="sxs-lookup"><span data-stu-id="07ccd-130">Work with topics in the Topic Center</span></span>](work-with-topics.md)



