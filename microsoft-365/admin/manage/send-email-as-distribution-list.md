---
title: 為 Office 365 中的通訊群組清單傳送電子郵件
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
description: 了解如何在 Office 365 中以通訊群組清單的形式傳送電子郵件 (機器翻譯)。
ms.openlocfilehash: f165279cf6cfbedda4f122f453c2321c16f412d3
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251594"
---
# <a name="send-email-as-a-distribution-list-in-office-365"></a><span data-ttu-id="a01bd-103">為 Office 365 中的通訊群組清單傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="a01bd-103">Send email as a distribution list in Office 365</span></span>

<span data-ttu-id="a01bd-104">在 Office 365 中，您可以傳送電子郵件作為通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="a01bd-104">In Office 365, you can send email as a distribution list.</span></span> <span data-ttu-id="a01bd-105">當通訊群組清單成員的人員回覆傳送給通訊群組清單的郵件時，將電子郵件會顯示從通訊群組清單，而不是由個別使用者。</span><span class="sxs-lookup"><span data-stu-id="a01bd-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="a01bd-106">本主題顯示如何進行此作業。</span><span class="sxs-lookup"><span data-stu-id="a01bd-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="a01bd-107">傳送電子郵件作為通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="a01bd-107">Send email as a distribution list</span></span>

<span data-ttu-id="a01bd-108">在執行這些步驟之前，請確定您已新增至 Office 365 通訊群組清單並已獲授與傳送為 」 權限在其上。</span><span class="sxs-lookup"><span data-stu-id="a01bd-108">Before you perform these steps, make sure you've been added to an Office 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="a01bd-109">**系統管理員**： 請確定您已後面的步驟主題中所[新增的 Office 365 使用者或連絡人至清單](../email/add-user-or-contact-to-distribution-list.md)和[允許傳送電子郵件做為 Office 365 群組的成員](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)，且正確的人員新增至通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="a01bd-109">**Admins**: Make sure you've followed the steps in the [Add an Office 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as an Office 365 Group](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="a01bd-110">開啟 outlook 網頁版並移至收件匣。</span><span class="sxs-lookup"><span data-stu-id="a01bd-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="a01bd-111">開啟已傳送至通訊群組清單的郵件。</span><span class="sxs-lookup"><span data-stu-id="a01bd-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="a01bd-112">選取 [**回覆**]。</span><span class="sxs-lookup"><span data-stu-id="a01bd-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="a01bd-113">在郵件的底部，選取 [**更多** \> **顯示的**。</span><span class="sxs-lookup"><span data-stu-id="a01bd-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="a01bd-114">![選取 [其他]，然後選擇 [顯示從](../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="a01bd-114">![Select More and then choose Show From](../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="a01bd-115">以滑鼠右鍵按一下來源地址-例如`Ina@weewalter.me`-選擇 [**移除**。</span><span class="sxs-lookup"><span data-stu-id="a01bd-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="a01bd-116">![移除 FROM 別名](../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="a01bd-116">![Remove the FROM alias](../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="a01bd-117">然後輸入通訊群組清單地址，例如 support@contoso.com，然後傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="a01bd-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="a01bd-118">下次您回覆從通訊群組清單，其地址會顯示為 [**從**] 清單中的選項。</span><span class="sxs-lookup"><span data-stu-id="a01bd-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="a01bd-119">![共用信箱的別名出現](../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="a01bd-119">![Alias of the shared mailbox appears](../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
  

