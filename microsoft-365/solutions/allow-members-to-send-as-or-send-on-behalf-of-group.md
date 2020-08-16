---
title: 允許成員傳送為或代表群組傳送
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 瞭解如何允許成員以 Microsoft 365 群組形式傳送電子郵件，或代表 Microsoft 365 群組傳送電子郵件。
ms.openlocfilehash: b660131798e60182435a69f479411cdec948bc99
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662527"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="50a70-103">允許成員傳送為或代表群組傳送</span><span class="sxs-lookup"><span data-stu-id="50a70-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="50a70-104">「以「 **代理傳送** 」或「 **代理傳送** 者」許可權授與之 Microsoft 365 群組的成員可以傳送電子郵件給群組，或代表群組傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="50a70-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="50a70-105">本文說明管理員如何設定這些許可權。</span><span class="sxs-lookup"><span data-stu-id="50a70-105">This article explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="50a70-106">例如，如果 Megan Bowen 是 **訓練** Microsoft 365 群組的一部分，且具有群組的 [以該群組 **傳送** ] 許可權，則當她傳送電子郵件做為群組時，它看起來就像是 **訓練** 群組傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="50a70-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="50a70-107">「 **代理傳送** 者」許可權可讓使用者代表 Microsoft 365 群組傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="50a70-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="50a70-108">例如，如果 Alex Wilber 是 **行銷** Microsoft 365 群組的一部分，且具有「 **代理傳送** 者」許可權並傳送電子郵件做為群組，則電子郵件看起來就像是由 **Alex Wilber 代表 Marketing**所傳送。</span><span class="sxs-lookup"><span data-stu-id="50a70-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50a70-109">您可以為特定使用者設定「 **傳送為** 」或「 **傳送代理** 」，但不能同時為這兩者。</span><span class="sxs-lookup"><span data-stu-id="50a70-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="50a70-110">如果您同時設定兩者，則預設會 **傳送為**。</span><span class="sxs-lookup"><span data-stu-id="50a70-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="50a70-111">請參閱 [代表 Microsoft 365 群組傳送電子郵件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) ，以瞭解如何使用 Outlook 和 outlook 網頁版以從群組傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="50a70-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="50a70-112">允許成員以群組形式傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="50a70-112">Allow members to send email as a group</span></span>

<span data-ttu-id="50a70-113">本節說明如何允許使用者以 [exchange 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104) 中的群組形式傳送電子郵件 (EAC) 在 exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="50a70-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="50a70-114">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>中， **移至 [** 收件者 \> **群組**]。</span><span class="sxs-lookup"><span data-stu-id="50a70-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="50a70-115">在**Edit** ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 您要允許使用者傳送的群組上，選取 [編輯編輯群組圖示]。  </span><span class="sxs-lookup"><span data-stu-id="50a70-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="50a70-116">選取 [ **群組委派**]。</span><span class="sxs-lookup"><span data-stu-id="50a70-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="50a70-117">在 [ **傳送方式** ] 區段中，選取要 **+** 新增為群組傳送之使用者的符號。</span><span class="sxs-lookup"><span data-stu-id="50a70-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![選取加號，以新增您要以 Microsoft 365 群組形式傳送的使用者。](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="50a70-119">若要從清單中搜尋或挑選使用者的類型。</span><span class="sxs-lookup"><span data-stu-id="50a70-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="50a70-120">選取 **[確定]** 並 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="50a70-120">Select **OK** and **Save**.</span></span>
    
    ![在清單中搜尋或挑選使用者的類型](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="50a70-122">允許成員代表群組傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="50a70-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="50a70-123">本節說明如何允許使用者代表 Exchange 系統管理中心中的群組傳送電子郵件 (EAC) 在 Exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="50a70-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="50a70-124">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>中， **移至 [** 收件者 \> **群組**]。</span><span class="sxs-lookup"><span data-stu-id="50a70-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="50a70-125">在**Edit** ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 您要允許使用者傳送的群組上，選取 [編輯編輯群組圖示]。</span><span class="sxs-lookup"><span data-stu-id="50a70-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="50a70-126">選取 [ **群組委派**]。</span><span class="sxs-lookup"><span data-stu-id="50a70-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="50a70-127">在 [代理傳送者] 區段中，選取要 **+** 新增為群組傳送之使用者的符號。</span><span class="sxs-lookup"><span data-stu-id="50a70-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![選取加號，以新增您要以 Microsoft 365 群組形式傳送的使用者。](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="50a70-129">若要從清單中搜尋或挑選使用者的類型。</span><span class="sxs-lookup"><span data-stu-id="50a70-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="50a70-130">選取 **[確定]** 並 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="50a70-130">Select **OK** and **Save**.</span></span>
    
    ![在清單中搜尋或挑選使用者的類型](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="50a70-132">相關文章</span><span class="sxs-lookup"><span data-stu-id="50a70-132">Related articles</span></span>

[<span data-ttu-id="50a70-133">深入瞭解 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="50a70-133">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="50a70-134">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="50a70-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="50a70-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="50a70-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)