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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: 瞭解如何在 Microsoft 365 中以通訊群組清單形式傳送電子郵件。
ms.openlocfilehash: e9f8e52350dfd27e58ee160ed10f5c45e33391d7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628061"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="c6c66-103">以通訊群組清單傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="c6c66-103">Send email as a distribution list</span></span>

<span data-ttu-id="c6c66-104">在 Microsoft 365 中，您可以傳送電子郵件做為通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c6c66-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="c6c66-105">當通訊群組清單的成員回復傳送至通訊群組清單的郵件時，電子郵件看似來自通訊群組清單，而不是來自個別使用者。</span><span class="sxs-lookup"><span data-stu-id="c6c66-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="c6c66-106">本主題說明如何執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="c6c66-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="c6c66-107">以通訊群組清單傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="c6c66-107">Send email as a distribution list</span></span>

<span data-ttu-id="c6c66-108">在您執行這些步驟之前，請確定您已新增至 Microsoft 365 通訊群組清單，且已被授與您的「傳送為」許可權。</span><span class="sxs-lookup"><span data-stu-id="c6c66-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="c6c66-109">系統**管理員**：請確定您已遵循 [[將 microsoft 365 使用者或連絡人新增至清單](../email/add-user-or-contact-to-distribution-list.md)] 中的步驟，並[允許成員以 Microsoft 365 群組主題傳送電子郵件](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)，並將正確的人員新增至通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c6c66-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="c6c66-110">開啟 Outlook 網頁版，然後移至您的收件匣。</span><span class="sxs-lookup"><span data-stu-id="c6c66-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="c6c66-111">開啟傳送至通訊群組清單的郵件。</span><span class="sxs-lookup"><span data-stu-id="c6c66-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="c6c66-112">選取 [**回復**]。</span><span class="sxs-lookup"><span data-stu-id="c6c66-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="c6c66-113">在郵件的底部，選取 [**其他** \> **顯示來源**]。</span><span class="sxs-lookup"><span data-stu-id="c6c66-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="c6c66-114">![選取 [其他]，然後選擇 [顯示來源]](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="c6c66-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="c6c66-115">在 [寄件者位址-- `Ina@weewalter.me` ] 上按一下滑鼠右鍵，然後選擇 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c6c66-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="c6c66-116">![移除寄件者別名](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="c6c66-116">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="c6c66-117">然後輸入通訊群組清單位址（如 support@contoso.com），然後傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="c6c66-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="c6c66-118">當您下次從通訊群組清單回復時，其位址會顯示為 [**發件**人] 清單中的選項。</span><span class="sxs-lookup"><span data-stu-id="c6c66-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="c6c66-119">![共用信箱的別名會出現](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="c6c66-119">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
  

