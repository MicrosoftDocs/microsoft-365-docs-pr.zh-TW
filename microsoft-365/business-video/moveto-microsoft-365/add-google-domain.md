---
title: 新增 Google Workspace 網域
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將網域從 Google Workspace 移至 Microsoft 365 for business。
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578768"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="6eef7-103">將 Google Workspace 網域新增至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6eef7-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="6eef7-104">將您的 Google Workspace 網域新增至 Microsoft 365 供商務使用，這樣您就可以繼續使用您的商務電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6eef7-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="6eef7-105">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="6eef7-105">Try it!</span></span>

1. <span data-ttu-id="6eef7-106">移至[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="6eef7-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="6eef7-107">在 Microsoft 365 系統管理中心的左側導覽中，選取 [**全部顯示**]、[**設定**] 和 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="6eef7-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="6eef7-108">選擇 [ **新增網域**]，輸入您的功能變數名稱，然後選取 [ **使用此網域**]。</span><span class="sxs-lookup"><span data-stu-id="6eef7-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="6eef7-109">選擇、 **將 txt 記錄新增至網域的 DNS 記錄** 中，選取 [ **繼續**]，然後複製 TXT 值。</span><span class="sxs-lookup"><span data-stu-id="6eef7-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="6eef7-110">請回到 Google 系統 [管理主控台](https://admin.google.com)、選擇 [ **網域**]、[ **管理網域**]、[ **查看詳細資料**]、[ **網域**]、[ **DNS**]，然後向下滾動至 **自訂資源記錄**。</span><span class="sxs-lookup"><span data-stu-id="6eef7-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="6eef7-111">開啟 [記錄類型] 下拉式清單，選擇 [ **txt**]，貼上您複製的 TXT 值，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6eef7-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="6eef7-112">更新通常會在幾分鐘內取得，但可能需要長達48小時。</span><span class="sxs-lookup"><span data-stu-id="6eef7-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="6eef7-113">回到 Microsoft 365 系統管理中心，選取 [**驗證**]，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6eef7-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="6eef7-114">若要將您的網域設為使用者的主要電子郵件，請在左側流覽中選取 [**使用者** 作用中  >  **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="6eef7-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="6eef7-115">選擇使用者，選取 [ **管理使用者名稱和電子郵件**]，[ **編輯**]，從下拉式清單中選取您的網域，然後選取 [ **完成** ] 並 **儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="6eef7-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="6eef7-116">針對每個使用者重複此程式。</span><span class="sxs-lookup"><span data-stu-id="6eef7-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="6eef7-117">當您完成時，您就可以安裝 Office 應用程式，並將您的電子郵件和行事曆專案遷移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6eef7-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 