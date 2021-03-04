---
title: 保護 iOS 上的 Office 應用程式
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 瞭解如何使用 Microsoft 365 商務版 Premium 來保護 Office 應用程式 iOS。
ms.openlocfilehash: 197041a4eb9ada65f4b6046d93f2a856cbdfb40d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422108"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="21c38-103">保護 iOS 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="21c38-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="21c38-104">您可以設定使用者存取原則，以要求行動使用者輸入 PIN 或指紋，以登入，也會加密儲存在其裝置上的工作檔。</span><span class="sxs-lookup"><span data-stu-id="21c38-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="21c38-105">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="21c38-105">Try it!</span></span>

1. <span data-ttu-id="21c38-106">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="21c38-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="21c38-107">在 [ **原則**] 底下，選擇 [ **新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="21c38-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="21c38-108">在 [ **新增原則** ] 窗格的 [ **原則名稱**] 下，輸入名稱，然後在 [ **原則類型**] 底下選擇您想要的原則類型。</span><span class="sxs-lookup"><span data-stu-id="21c38-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="21c38-109">開啟 [ **管理使用者如何存取行動裝置上的 Office** 檔案]，然後確定下列三個設定已開啟：</span><span class="sxs-lookup"><span data-stu-id="21c38-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="21c38-110">**需要 PIN 或指紋才能存取 Office App**</span><span class="sxs-lookup"><span data-stu-id="21c38-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="21c38-111">**在裝置遺失或遭竊時保護工作檔**</span><span class="sxs-lookup"><span data-stu-id="21c38-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="21c38-112">**加密工作檔案**</span><span class="sxs-lookup"><span data-stu-id="21c38-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="21c38-113">在 [ **將會保護這些應用程式** 的檔案] 底下，選取您要在行動裝置上保護的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="21c38-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="21c38-114">在 **誰會取得這些設定？** 預設會選取所有使用者，但您可以選擇 [ **變更** ]，以選取您建立的任何安全性群組。</span><span class="sxs-lookup"><span data-stu-id="21c38-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="21c38-115">若要完成建立原則，請選擇 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="21c38-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="21c38-116">在 [ **新增原則** ] 頁面上，選擇 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="21c38-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="21c38-117">在系統管理中心的首頁上，透過選擇 [原則] 並在 [**原則**] 頁面上查看您的 **原則，以** 確認新增原則。</span><span class="sxs-lookup"><span data-stu-id="21c38-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>