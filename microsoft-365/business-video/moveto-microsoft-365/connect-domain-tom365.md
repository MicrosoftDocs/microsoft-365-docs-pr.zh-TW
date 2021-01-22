---
title: 將您的網域連線到 Microsoft 365
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將您的網域連接至 Microsoft 365。
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925107"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="b7e6e-103">將您的網域連接到商務用 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7e6e-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="b7e6e-104">一旦設定好 Microsoft 365，並移動了來自 Google Workspace 的電子郵件資料，就可以將您的網域連結至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="b7e6e-105">首先，您必須從 Google 刪除現有的 DNS 記錄，然後我們可以從 Microsoft 365 新增 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="b7e6e-106">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="b7e6e-106">Try it!</span></span>

1. <span data-ttu-id="b7e6e-107">在 admin.google.com 上，[請admin.google.com。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="b7e6e-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="b7e6e-108">在 **左側流覽\*\*\*\*中選取網域、管理網域**、**查看** 詳細資料、管理 **網** 域，然後選取 **DNS。**</span><span class="sxs-lookup"><span data-stu-id="b7e6e-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="b7e6e-109">向下卷到 **Records 記錄**，開啟 Google **Workspace，** 選取 **Delete，** 然後再次 **刪除** 。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="b7e6e-110">向下卷到 **自訂資源記錄** ，並刪除任何出現的現有 DNS 記錄，包括您先前可能為 Microsoft 365 建立的任何 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="b7e6e-111">請前往 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="b7e6e-112">在左側 NAV 中，選擇 、顯示 **全部**、**設定、\*\*\*\*網域**。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="b7e6e-113">然後選擇您的預設網域。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="b7e6e-114">選取 **繼續設定**，然後選擇繼續以連接您的  **網域**。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="b7e6e-115">向下卷卷來查看需要複製到 Google 的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="b7e6e-116">開啟 **MX 記錄**，在 **指向位址或值** 下複製記錄。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="b7e6e-117">返回 Google，**在自訂資源** 記錄區段，開啟記錄類型下拉式清單，然後選取 **MX。**</span><span class="sxs-lookup"><span data-stu-id="b7e6e-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="b7e6e-118">在資料 **欄位中** ，貼上您複製的記錄。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="b7e6e-119">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-119">Then select **Add**.</span></span>
1. <span data-ttu-id="b7e6e-120">對 CNAME 和 TXT 記錄重複此程式，並新增 Google DNS 管理頁面上的值。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="b7e6e-121">返回 Microsoft 365 系統管理中心， **然後選取繼續**。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="b7e6e-122">您的網域設定已完成。</span><span class="sxs-lookup"><span data-stu-id="b7e6e-122">Your domain setup is complete.</span></span>