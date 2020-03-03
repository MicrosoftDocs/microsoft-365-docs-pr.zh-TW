---
title: 允許成員傳送為 」 或 「 代理群組傳送
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 了解如何讓成員為 Office 365 群組傳送電子郵件] 或 [代理 Office 365 群組傳送電子郵件。
ms.openlocfilehash: 0179dbd2e3093ce80929f6c5f9e689aece845a40
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352754"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="6c135-103">允許成員傳送為 」 或 「 代理群組傳送</span><span class="sxs-lookup"><span data-stu-id="6c135-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="6c135-104">做為群組，或代表群組已授與**傳送為**」 或 **「 代理傳送者 」** 權限的 Office 365 群組的成員現在可以傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6c135-104">A member of an Office 365 Group who has been granted **Send as** or **Send on behalf** permissions can now send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="6c135-105">本主題說明如何為系統管理員可以設定這些權限。</span><span class="sxs-lookup"><span data-stu-id="6c135-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="6c135-106">例如，如果謝良屬於**訓練**的 Office 365 群組擁有 「**傳送為**權限] 群組中，如果曾經傳送一封電子郵件做為群組，它看起來像**訓練**群組傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6c135-106">For example, if Megan Bowen is part of the **Training** Office 365 Group, and has **Send as** permissions on the group, if she sends an email as the Group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="6c135-107">**代理傳送者 」** 權限可讓 Office 365 群組代理傳送電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="6c135-107">The **Send on Behalf** permission lets a user send email on behalf of an Office 365 Group.</span></span> <span data-ttu-id="6c135-108">例如，如果 Alex Wilber 屬於**Marketing** Office 365 群組，具有**代理傳送者 」** 權限並傳送一封電子郵件做為群組、 電子郵件看起來就由**代表行銷 Alex Wilber**所傳送。</span><span class="sxs-lookup"><span data-stu-id="6c135-108">For example, if Alex Wilber is a part of the **Marketing** Office 365 Group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c135-109">您可以指定的使用者，但不能兩者同時設定**傳送為**」 或 **「 代理傳送者 」** 。</span><span class="sxs-lookup"><span data-stu-id="6c135-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="6c135-110">如果您設定兩者，它會預設**為**傳送。</span><span class="sxs-lookup"><span data-stu-id="6c135-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="6c135-111">簽出以從群組電子郵件中[傳送電子郵件從或是代表 Office 365 群組](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)了解如何使用 Outlook 和 outlook 網頁版傳送的步驟。</span><span class="sxs-lookup"><span data-stu-id="6c135-111">Check the out the steps in [Send email from or on behalf of an Office 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a Group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="6c135-112">允許傳送電子郵件做為群組的成員</span><span class="sxs-lookup"><span data-stu-id="6c135-112">Allow members to send email as a Group</span></span>

<span data-ttu-id="6c135-113">本節說明如何允許使用者傳送電子郵件做為群組中[的 Exchange 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104)(EAC) 中 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6c135-113">This section explains how to allow users to send email as a Group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="6c135-114">在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>中，前往 [**收件者** \> **群組**。</span><span class="sxs-lookup"><span data-stu-id="6c135-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="6c135-115">選取 [**編輯**  ![編輯群組圖示](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)上您想要允許使用者傳送為群組。</span><span class="sxs-lookup"><span data-stu-id="6c135-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="6c135-116">選取 [**群組委派**]。</span><span class="sxs-lookup"><span data-stu-id="6c135-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="6c135-117">在 [以下列**傳送**] 區段中，選取 [**+** 新增您想要傳送做為群組的使用者登入。</span><span class="sxs-lookup"><span data-stu-id="6c135-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![選取加號，以新增您想要傳送做為 Office 365 群組的使用者](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="6c135-119">輸入要搜尋或挑選清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="6c135-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="6c135-120">選取 [**確定**] 和 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6c135-120">Select **OK** and **Save**.</span></span>
    
    ![輸入要搜尋或挑選清單中的使用者](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="6c135-122">允許成員代理群組傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="6c135-122">Allow members to send email on behalf of a Group</span></span>

<span data-ttu-id="6c135-123">本節說明如何允許使用者傳送代表群組的電子郵件在 Exchange 系統管理中心 (EAC) 中 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6c135-123">This section explains how to allow users to send email on behalf of a Group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="6c135-124">在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>中，前往 [**收件者** \> **群組**。</span><span class="sxs-lookup"><span data-stu-id="6c135-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="6c135-125">選取 [**編輯**![編輯群組圖示](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)上您想要允許使用者傳送為群組。</span><span class="sxs-lookup"><span data-stu-id="6c135-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="6c135-126">選取 [**群組委派**]。</span><span class="sxs-lookup"><span data-stu-id="6c135-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="6c135-127">在代理傳送者] 區段中，選取 [**+** 以新增您想要傳送做為群組的使用者登入。</span><span class="sxs-lookup"><span data-stu-id="6c135-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![選取加號，以新增您想要傳送做為 Office 365 群組的使用者](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="6c135-129">輸入要搜尋或挑選清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="6c135-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="6c135-130">選取 [**確定**] 和 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6c135-130">Select **OK** and **Save**.</span></span>
    
    ![輸入要搜尋或挑選清單中的使用者](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="6c135-132">相關文章</span><span class="sxs-lookup"><span data-stu-id="6c135-132">Related articles</span></span>

[<span data-ttu-id="6c135-133">深入了解 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="6c135-133">Learn more about Office 365 Groups</span></span>](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[<span data-ttu-id="6c135-134">Add-recipientpermission</span><span class="sxs-lookup"><span data-stu-id="6c135-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="6c135-135">Set-unifiedgroup</span><span class="sxs-lookup"><span data-stu-id="6c135-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
