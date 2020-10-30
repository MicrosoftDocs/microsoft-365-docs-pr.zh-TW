---
title: 在 web 上的 Outlook 中取得未找到信箱的錯誤
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 瞭解如何將授權新增至未授權的使用者，以修正未找到信箱的錯誤。
ms.openlocfilehash: bf8ff57704b97c8ef278938675113f5de11849de
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804861"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="aeda9-103">在 web 上的 Outlook 中取得未找到信箱的錯誤？</span><span class="sxs-lookup"><span data-stu-id="aeda9-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="aeda9-104">如果您使用的是網頁型 Outlook，但找不到您要  **的信箱**  ，表示您用來連線至網頁上的 outlook 的帳戶沒有 Exchange Online 授權，因此沒有信箱與帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="aeda9-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> <span data-ttu-id="aeda9-105">您的系統管理員可以遵循下列步驟，將授權指派給您的帳戶：</span><span class="sxs-lookup"><span data-stu-id="aeda9-105">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="aeda9-106">開啟 [Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home#/homepage)，移至 [ **使用者** ] 區段下的 [作用中 **使用者** ]，然後選取看到錯誤的使用者。</span><span class="sxs-lookup"><span data-stu-id="aeda9-106">Open the  [Microsoft 365 admin center](https://portal.office.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
2. <span data-ttu-id="aeda9-107">在開啟的使用者頁面中，移至 [  **授權與應用程式**  ] 區段中，選取適當的  **位置**  值，並指派包含 Exchange Online (的授權，以查看其詳細資料) 。</span><span class="sxs-lookup"><span data-stu-id="aeda9-107">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> <span data-ttu-id="aeda9-108">完成後，按一下 [  **儲存變更** ]。</span><span class="sxs-lookup"><span data-stu-id="aeda9-108">When you're finished, click  **Save changes** .</span></span>
