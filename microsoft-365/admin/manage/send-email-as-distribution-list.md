---
title: 以通訊群組清單傳送電子郵件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: 在 Microsoft 365 中以通訊群組清單形式傳送電子郵件，這樣當成員回復郵件時，就會從通訊群組清單中回復。
ms.openlocfilehash: 01bff7e1d2515670c5a6faa199355e7de591f1fb
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624534"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="86c4a-103">以通訊群組清單傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="86c4a-103">Send email as a distribution list</span></span>

<span data-ttu-id="86c4a-104">在 Microsoft 365 中，您可以傳送電子郵件做為通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="86c4a-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="86c4a-105">當通訊群組清單的成員回復傳送至通訊群組清單的郵件時，電子郵件看似來自通訊群組清單，而不是來自個別使用者。</span><span class="sxs-lookup"><span data-stu-id="86c4a-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="86c4a-106">本主題說明如何執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="86c4a-106">This topic shows you how to do this.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="86c4a-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="86c4a-107">Before you begin</span></span>

<span data-ttu-id="86c4a-108">在執行這些步驟之前，請確定您已新增至 Microsoft 365 通訊群組清單，且已被授與您的「傳送為」許可權。</span><span class="sxs-lookup"><span data-stu-id="86c4a-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="86c4a-109">系統 **管理員**：請確定您已遵循 [新增 Microsoft 365 使用者或連絡人清單](../email/add-user-or-contact-to-distribution-list.md)中的步驟，並 [允許成員將電子郵件當做 Microsoft 365 群組主題傳送](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)，並將正確的人員新增至通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="86c4a-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
## <a name="outlook-on-the-web"></a><span data-ttu-id="86c4a-110">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="86c4a-110">Outlook on the web</span></span>

1. <span data-ttu-id="86c4a-111">開啟網頁上的 Outlook，然後移至您的收件匣。</span><span class="sxs-lookup"><span data-stu-id="86c4a-111">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="86c4a-112">開啟傳送至通訊群組清單的郵件。</span><span class="sxs-lookup"><span data-stu-id="86c4a-112">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="86c4a-113">選取 [ **回復**]。</span><span class="sxs-lookup"><span data-stu-id="86c4a-113">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="86c4a-114">在郵件的底部，選取 [ **其他** \> **顯示來源**]。</span><span class="sxs-lookup"><span data-stu-id="86c4a-114">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="86c4a-115">![選取 [其他]，然後選擇 [顯示來源]](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="86c4a-115">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="86c4a-116">在 [寄件者位址--] 上按一下滑鼠右鍵 `Ina@weewalter.me` ，然後選擇 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="86c4a-116">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="86c4a-117">![移除寄件者別名](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="86c4a-117">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="86c4a-118">然後輸入通訊群組清單位址（如 support@contoso.com），然後傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="86c4a-118">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="86c4a-119">當您下次從通訊群組清單回復時，其位址會顯示為 [ **發件** 人] 清單中的選項。</span><span class="sxs-lookup"><span data-stu-id="86c4a-119">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="86c4a-120">![共用信箱的別名會出現](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="86c4a-120">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>

## <a name="outlook"></a><span data-ttu-id="86c4a-121">Outlook</span><span class="sxs-lookup"><span data-stu-id="86c4a-121">Outlook</span></span>

1. <span data-ttu-id="86c4a-122">開啟 Outlook 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="86c4a-122">Open Outlook desktop client.</span></span>

2. <span data-ttu-id="86c4a-123">撰寫新的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="86c4a-123">Compose a New Email.</span></span> <span data-ttu-id="86c4a-124">按一下 [ **寄件者** ] 欄位，然後選取 [ **其他電子郵件地址**]。</span><span class="sxs-lookup"><span data-stu-id="86c4a-124">Click the **From** field and select **Other email address**.</span></span> <span data-ttu-id="86c4a-125">如果您沒有看到 [寄件者] 欄位，請流覽至 [ **選項** ]，然後在 [顯示欄位] 區段中選取 [ **從** ]。</span><span class="sxs-lookup"><span data-stu-id="86c4a-125">If you do not see the From field, navigate to **Options** and select **From** in the Show fields section.</span></span>

3. <span data-ttu-id="86c4a-126">從全域通訊清單中選取 **通訊群組清單** 位址。</span><span class="sxs-lookup"><span data-stu-id="86c4a-126">Select the **Distribution List** address from the Global Address List.</span></span>

4. <span data-ttu-id="86c4a-127">傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="86c4a-127">Send the email.</span></span>

## <a name="related-content"></a><span data-ttu-id="86c4a-128">相關內容</span><span class="sxs-lookup"><span data-stu-id="86c4a-128">Related content</span></span>

<span data-ttu-id="86c4a-129">[在 Microsoft 365 系統管理中心建立、編輯或刪除安全性群組](../email/create-edit-or-delete-a-security-group.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="86c4a-129">[Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md) (article)</span></span>\
<span data-ttu-id="86c4a-130">[電子郵件](../email/email-collaboration.md) 共同作業 (文章) </span><span class="sxs-lookup"><span data-stu-id="86c4a-130">[Email collaboration](../email/email-collaboration.md) (article)</span></span>\
[<span data-ttu-id="86c4a-131">新增使用者或連絡人至通訊群組</span><span class="sxs-lookup"><span data-stu-id="86c4a-131">Add a user or contact to a distribution group</span></span>](../email/add-user-or-contact-to-distribution-list.md)