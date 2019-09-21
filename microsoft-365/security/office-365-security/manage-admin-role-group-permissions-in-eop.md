---
title: 管理 EOP 中的系統管理員角色群組權限
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 系統管理員可以在 Exchange Online Protection 中了解如何指派或移除 Exchange 系統管理中心 (EAC) 中的權限。
ms.openlocfilehash: 589d979b9a2ed3f262eb8171fe08622c225548ce
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078125"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="5b334-103">管理 EOP 中的系統管理員角色群組權限</span><span class="sxs-lookup"><span data-stu-id="5b334-103">Manage admin role group permissions in EOP</span></span>
  
<span data-ttu-id="5b334-p101">在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 系統管理中心 (EAC)，讓使用者成為角色群組的成員，以為他們指派可用以執行特定管理工作的權限。您也可以使用 EAC 從角色群組中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="5b334-p101">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5b334-106">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="5b334-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5b334-107">預估完成時間：5-10 分鐘</span><span class="sxs-lookup"><span data-stu-id="5b334-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="5b334-108">若要開啟 Exchange 系統管理中心，請參閱[Exchange 系統管理中心在 Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="5b334-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="5b334-p102">您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)主題中的「使用者、連絡人及角色群組」項目。</span><span class="sxs-lookup"><span data-stu-id="5b334-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="5b334-111">適用於此主題中程序的鍵盤快速鍵相關資訊，請參閱[Exchange 系統管理員的鍵盤快速鍵置在 Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="5b334-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="5b334-112">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="5b334-112">Having problems?</span></span> <span data-ttu-id="5b334-113">要求在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)論壇中的協助。</span><span class="sxs-lookup"><span data-stu-id="5b334-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="5b334-114">使用 EAC 將成員指派給系統管理員角色群組</span><span class="sxs-lookup"><span data-stu-id="5b334-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="5b334-115">在 EAC 中，前往 [**權限** \> **系統管理員角色**]，按一下您想要新增的使用者或使用者，角色群組，然後按一下 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="5b334-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="5b334-116">[成員] 下方按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="5b334-116">Under Members, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="5b334-117">[選取成員] 視窗將會出現。</span><span class="sxs-lookup"><span data-stu-id="5b334-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="5b334-118">搜尋您要新增的使用者，或是從清單中加以選取。</span><span class="sxs-lookup"><span data-stu-id="5b334-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="5b334-p105">選好要新增的使用者後，按一下 **[新增]**，然後按一下 **[確定]**。[選取成員] 視窗便會關閉。</span><span class="sxs-lookup"><span data-stu-id="5b334-p105">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>

5. <span data-ttu-id="5b334-p106">您會看到使用者已新增至 **[成員]** 窗格。按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5b334-p106">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5b334-123">使用者可能必須先登出再登入，才能在您於角色群組中新增或移除成員後，看到其系統管理權限的變更。</span><span class="sxs-lookup"><span data-stu-id="5b334-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="5b334-124">使用 EAC 從系統管理員角色群組中移除成員</span><span class="sxs-lookup"><span data-stu-id="5b334-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="5b334-125">在 EAC 中，前往 [**權限** \> **系統管理員角色**]，按一下您想要移除使用者或使用者的角色群組，然後按一下 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="5b334-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="5b334-126">[成員] 下方選取一或多位您想要移除，然後按一下 [**移除**使用者![移除圖示](../media/ITPro-EAC-RemoveIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="5b334-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="5b334-p107">按一下 **[儲存]**，以儲存角色群組的變更，並回到 **[系統管理員角色]** 頁面。若要確認您是否已成功從系統管理員角色群組中移除使用者，請確定在所選角色群組的詳細資料窗格中，[成員] 下已看不到該成員。</span><span class="sxs-lookup"><span data-stu-id="5b334-p107">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5b334-129">使用者可能必須先登出再登入，才能在您於角色群組中新增或移除成員後，看到其系統管理權限的變更。</span><span class="sxs-lookup"><span data-stu-id="5b334-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="5b334-130">相關資訊</span><span class="sxs-lookup"><span data-stu-id="5b334-130">For more information</span></span>

[<span data-ttu-id="5b334-131">EOP 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="5b334-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
