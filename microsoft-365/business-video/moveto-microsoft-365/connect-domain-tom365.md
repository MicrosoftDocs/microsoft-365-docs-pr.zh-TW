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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將您的網域連接至 Microsoft 365。
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794601"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="cde00-103">將您的網域連線至 Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="cde00-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="cde00-104">當您設定 Microsoft 365 並將電子郵件資料從 Google Workspace 移出後，您就可以將您的網域連線至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="cde00-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="cde00-105">首先，您將需要從 Google 刪除現有的 DNS 記錄，然後我們可以從 Microsoft 365 新增 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="cde00-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="cde00-106">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="cde00-106">Try it!</span></span>

1. <span data-ttu-id="cde00-107">在 [admin.google.com](https://admin.google.com)中登入 Google Workspace 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="cde00-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="cde00-108">選取 [ **網域**]、[ **管理網域**]、[ **查看詳細資料**]、[ **管理網域**] 及左導覽中的 [ **DNS** ]</span><span class="sxs-lookup"><span data-stu-id="cde00-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="cde00-109">向下滾動至 **綜合記錄**，開啟 **Google Workspace**，選取 [ **刪除**]，然後重新 **刪除** 。</span><span class="sxs-lookup"><span data-stu-id="cde00-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="cde00-110">向下滾動至 **自訂資源記錄** ，並刪除任何出現的現有 DNS 記錄，包括您先前針對 Microsoft 365 建立的任何 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="cde00-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="cde00-111">移至 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="cde00-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="cde00-112">在左側導覽中，選擇 [ **全部顯示**]、[ **設定**]、[ **網域**]。</span><span class="sxs-lookup"><span data-stu-id="cde00-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="cde00-113">然後選擇您的預設網域。</span><span class="sxs-lookup"><span data-stu-id="cde00-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="cde00-114">選取 [ **繼續安裝**]，然後按一下 [  **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="cde00-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="cde00-115">向中向左下以查看需要複製到 Google 的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="cde00-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="cde00-116">開啟 **MX 記錄**，然後在 [ **指向位址] 或 [值**] 底下複製記錄。</span><span class="sxs-lookup"><span data-stu-id="cde00-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="cde00-117">回到 Google，然後在 [ **自訂資源記錄** ] 區段中，開啟 [記錄類型] 下拉式清單，然後選取 [ **MX**]。</span><span class="sxs-lookup"><span data-stu-id="cde00-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="cde00-118">在 [ **資料** ] 欄位中，貼上您複製的記錄。</span><span class="sxs-lookup"><span data-stu-id="cde00-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="cde00-119">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="cde00-119">Then select **Add**.</span></span>
1. <span data-ttu-id="cde00-120">針對 CNAME 和 TXT 記錄重複此程式，並在 [Google DNS 管理] 頁面中新增值。</span><span class="sxs-lookup"><span data-stu-id="cde00-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="cde00-121">回到 Microsoft 365 系統管理中心，然後選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="cde00-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="cde00-122">您的網域設定已完成。</span><span class="sxs-lookup"><span data-stu-id="cde00-122">Your domain setup is complete.</span></span>