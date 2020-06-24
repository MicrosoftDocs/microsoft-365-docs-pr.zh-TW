---
title: 允許成員傳送為或代表群組傳送
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 瞭解如何允許成員以 Microsoft 365 群組形式傳送電子郵件，或代表 Microsoft 365 群組傳送電子郵件。
ms.openlocfilehash: 090a5e177ed843c035155cd735e0b7b9560e5631
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844665"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="a4937-103">允許成員傳送為或代表群組傳送</span><span class="sxs-lookup"><span data-stu-id="a4937-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="a4937-104">「以「**代理傳送**」或「**代理傳送**者」許可權授與之 Microsoft 365 群組的成員可以傳送電子郵件給群組，或代表群組傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a4937-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="a4937-105">本主題說明管理員如何設定這些許可權。</span><span class="sxs-lookup"><span data-stu-id="a4937-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="a4937-106">例如，如果 Megan Bowen 是**訓練**Microsoft 365 群組的一部分，且具有群組的 [以該群組**傳送**] 許可權，則當她傳送電子郵件做為群組時，它看起來就像是**訓練**群組傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a4937-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="a4937-107">「**代理傳送**者」許可權可讓使用者代表 Microsoft 365 群組傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a4937-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="a4937-108">例如，如果 Alex Wilber 是**行銷**Microsoft 365 群組的一部分，且具有「**代理傳送**者」許可權並傳送電子郵件做為群組，則電子郵件看起來就像是由**Alex Wilber 代表 Marketing**所傳送。</span><span class="sxs-lookup"><span data-stu-id="a4937-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4937-109">您可以為特定使用者設定「**傳送為**」或「**傳送代理**」，但不能同時為這兩者。</span><span class="sxs-lookup"><span data-stu-id="a4937-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="a4937-110">如果您同時設定兩者，則預設會**傳送為**。</span><span class="sxs-lookup"><span data-stu-id="a4937-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="a4937-111">請參閱[代表 Microsoft 365 群組傳送電子郵件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)，以瞭解如何使用 Outlook 和 outlook 網頁版以從群組傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a4937-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="a4937-112">允許成員以群組形式傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="a4937-112">Allow members to send email as a group</span></span>

<span data-ttu-id="a4937-113">本節說明如何允許使用者在 exchange Online 中以[exchange 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104)（EAC）中的群組形式傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a4937-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="a4937-114">在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>中，**移至 [** 收件者 \> **群組**]。</span><span class="sxs-lookup"><span data-stu-id="a4937-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="a4937-115">**Edit** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 在您要允許使用者傳送的群組上，選取 [編輯編輯群組圖示]。  </span><span class="sxs-lookup"><span data-stu-id="a4937-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="a4937-116">選取 [**群組委派**]。</span><span class="sxs-lookup"><span data-stu-id="a4937-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="a4937-117">在 [**傳送方式**] 區段中，選取要 **+** 新增為群組傳送之使用者的符號。</span><span class="sxs-lookup"><span data-stu-id="a4937-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![選取加號，以新增您要以 Microsoft 365 群組形式傳送的使用者。](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="a4937-119">若要從清單中搜尋或挑選使用者的類型。</span><span class="sxs-lookup"><span data-stu-id="a4937-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="a4937-120">選取 **[確定]** 並**儲存**。</span><span class="sxs-lookup"><span data-stu-id="a4937-120">Select **OK** and **Save**.</span></span>
    
    ![在清單中搜尋或挑選使用者的類型](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="a4937-122">允許成員代表群組傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="a4937-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="a4937-123">本節說明如何允許使用者代表 exchange 系統管理中心（EAC）中的群組傳送電子郵件，在 Exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="a4937-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="a4937-124">在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>中，**移至 [** 收件者 \> **群組**]。</span><span class="sxs-lookup"><span data-stu-id="a4937-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="a4937-125">在**Edit** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 您要允許使用者傳送的群組上，選取 [編輯編輯群組圖示]。</span><span class="sxs-lookup"><span data-stu-id="a4937-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="a4937-126">選取 [**群組委派**]。</span><span class="sxs-lookup"><span data-stu-id="a4937-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="a4937-127">在 [代理傳送者] 區段中，選取要 **+** 新增為群組傳送之使用者的符號。</span><span class="sxs-lookup"><span data-stu-id="a4937-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![選取加號，以新增您要以 Microsoft 365 群組形式傳送的使用者。](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="a4937-129">若要從清單中搜尋或挑選使用者的類型。</span><span class="sxs-lookup"><span data-stu-id="a4937-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="a4937-130">選取 **[確定]** 並**儲存**。</span><span class="sxs-lookup"><span data-stu-id="a4937-130">Select **OK** and **Save**.</span></span>
    
    ![在清單中搜尋或挑選使用者的類型](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
    
> [!NOTE]
> <span data-ttu-id="a4937-132">最多可能需要兩個小時的時間，所做的變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="a4937-132">It may take up to two hours for changes to take effect.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a4937-133">相關文章</span><span class="sxs-lookup"><span data-stu-id="a4937-133">Related articles</span></span>

[<span data-ttu-id="a4937-134">深入瞭解 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="a4937-134">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="a4937-135">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="a4937-135">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="a4937-136">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a4937-136">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
