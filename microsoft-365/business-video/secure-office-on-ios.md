---
title: 保護 iOS 上的 Office 應用程式
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: 瞭解如何使用 Microsoft 365 商務進階版 iOS 保護 Office 上的應用程式。
ms.openlocfilehash: 5a5f52f87fe63fdec6df9611a5ea44a2ecf4466b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580459"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="2b6fc-103">保護 iOS 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="2b6fc-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="2b6fc-104">您可以設定使用者存取原則，以要求行動使用者輸入 PIN 或指紋，以登入，也會加密儲存在其裝置上的工作檔。</span><span class="sxs-lookup"><span data-stu-id="2b6fc-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="2b6fc-105">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="2b6fc-105">Try it!</span></span>

1. <span data-ttu-id="2b6fc-106">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="2b6fc-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="2b6fc-107">在 [ **原則**] 底下，選擇 [ **新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="2b6fc-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="2b6fc-108">在 [ **新增原則** ] 窗格的 [ **原則名稱**] 下，輸入名稱，然後在 [ **原則類型**] 底下選擇您想要的原則類型。</span><span class="sxs-lookup"><span data-stu-id="2b6fc-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="2b6fc-109">開啟 [**管理使用者如何存取行動裝置上的 Office** 檔案]，然後確定下列三個設定已開啟：</span><span class="sxs-lookup"><span data-stu-id="2b6fc-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="2b6fc-110">**需要 PIN 或指紋才能存取 Office App**</span><span class="sxs-lookup"><span data-stu-id="2b6fc-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="2b6fc-111">**在裝置遺失或遭竊時保護工作檔**</span><span class="sxs-lookup"><span data-stu-id="2b6fc-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="2b6fc-112">**加密工作檔案**</span><span class="sxs-lookup"><span data-stu-id="2b6fc-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="2b6fc-113">在 [**將會保護這些應用程式** 的檔案] 底下，選取要在行動裝置上保護的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2b6fc-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="2b6fc-114">在 [**神秘會取得這些設定嗎？** 預設會選取所有使用者，但您可以選擇 [**變更**]，以選取您已建立的任何安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2b6fc-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="2b6fc-115">若要完成建立原則，請選擇 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="2b6fc-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="2b6fc-116">在 [ **新增原則** ] 頁面上，選擇 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="2b6fc-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="2b6fc-117">在系統管理中心的首頁上，透過選擇 [原則] 並在 [**原則**] 頁面上查看您的 **原則，以** 確認新增原則。</span><span class="sxs-lookup"><span data-stu-id="2b6fc-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>