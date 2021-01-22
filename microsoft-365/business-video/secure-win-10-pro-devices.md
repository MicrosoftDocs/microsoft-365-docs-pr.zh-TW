---
title: 使用 Microsoft 365 商務進版管理 Windows 10 專業版裝置政策
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: 瞭解如何使用 Microsoft 365 商務進版管理 Windows 10 專業版裝置策略。
ms.openlocfilehash: f42c175543ae16ae645c17997b20ed67aa5d705c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926003"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="101d2-103">管理 Windows 10 專業版裝置策略</span><span class="sxs-lookup"><span data-stu-id="101d2-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="101d2-104">您可以使用 Microsoft 365 商務版來確保 Windows 10 裝置上已啟用 Windows Defender 防毒軟體，而且 Microsoft 更新會自動下載到使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="101d2-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="101d2-105">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="101d2-105">Try it!</span></span>

1. <span data-ttu-id="101d2-106">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="101d2-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="101d2-107">在 **策略下**，選擇新增策略。</span><span class="sxs-lookup"><span data-stu-id="101d2-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="101d2-108">在 **新增** 策略窗格的中，在Policy name下輸入名稱，然後在Windows **10 裝置群組原則** 類型下選取 Windows 10 **裝置組塊**。 </span><span class="sxs-lookup"><span data-stu-id="101d2-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="101d2-109">選擇 **安全 Windows 10 裝置** 以查看子設定。</span><span class="sxs-lookup"><span data-stu-id="101d2-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="101d2-110">請確定使用 **Windows Defender** 防毒軟體協助保護電腦不受病毒與其他威脅的侵害，並自動開啟 Windows **10** 裝置保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="101d2-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="101d2-111">根據 **預設，會選取** 所有使用者，但您可以選擇變更，以選取任何您建立的安全性群組。 </span><span class="sxs-lookup"><span data-stu-id="101d2-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="101d2-112">若要完成建立策略 **，請選擇新增**。</span><span class="sxs-lookup"><span data-stu-id="101d2-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="101d2-113">在新增 **策略頁面上\*\*\*\*，選擇關閉**。</span><span class="sxs-lookup"><span data-stu-id="101d2-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="101d2-114">在系統管理中心首頁上，選擇系統管理中心頁面並校閱您的政策，以確認已新增 **新** 政策。</span><span class="sxs-lookup"><span data-stu-id="101d2-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="101d2-115">若要確認該政策已生效，在使用者的 Windows 10 裝置上，請前往 Windows Update，選擇進階選項，並確認設定為灰色。</span><span class="sxs-lookup"><span data-stu-id="101d2-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="101d2-116">接著，按一下 [ **選擇更新的** 傳遞方式，並確認設定呈現灰色，並出現下列訊息：某些設定為隱藏狀態或 **由您的組織管理**。</span><span class="sxs-lookup"><span data-stu-id="101d2-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

