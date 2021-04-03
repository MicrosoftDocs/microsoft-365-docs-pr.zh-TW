---
title: 使用 Microsoft 365 商務版特優管理 Windows 10 專業版裝置原則
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
description: 瞭解如何使用 Microsoft 365 商務版特優管理 Windows 10 專業版的裝置原則。
ms.openlocfilehash: 0f7cfff227e1ab4ea992414b513e341adbd9ef22
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578684"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="f3097-103">管理 Windows 10 專業版裝置原則</span><span class="sxs-lookup"><span data-stu-id="f3097-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="f3097-104">您可以使用 Microsoft 365 商務版，確定 windows 10 裝置上已啟用 Windows Defender 防毒程式，而且 Microsoft 更新會自動下載至使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="f3097-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="f3097-105">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="f3097-105">Try it!</span></span>

1. <span data-ttu-id="f3097-106">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="f3097-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="f3097-107">在 [ **原則**] 底下，選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="f3097-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="f3097-108">在 [**新增原則**] 窗格的 [**原則名稱**] 下，輸入名稱，然後選取 [**原則類型**] 底下的 [ **Windows 10 裝置** 設定]。</span><span class="sxs-lookup"><span data-stu-id="f3097-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="f3097-109">選擇 [ **安全的 Windows 10 裝置** ]，以查看子設定。</span><span class="sxs-lookup"><span data-stu-id="f3097-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="f3097-110">請務必 **使用 Windows Defender 防毒軟體，協助保護電腦免受病毒和其他威脅** ，並 **將 windows 10 裝置自動保持在最** 新狀態。</span><span class="sxs-lookup"><span data-stu-id="f3097-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="f3097-111">在 **誰會取得這些設定？** 預設會選取所有使用者，但您可以選擇 [ **變更** ]，以選取您建立的任何安全性群組。</span><span class="sxs-lookup"><span data-stu-id="f3097-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="f3097-112">若要完成建立原則，請選擇 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="f3097-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="f3097-113">在 [ **新增原則** ] 頁面上，選擇 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f3097-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="f3097-114">在系統管理中心的首頁上，透過選擇 [原則] 並在 [**原則**] 頁面上查看您的 **原則，以** 確認新增原則。</span><span class="sxs-lookup"><span data-stu-id="f3097-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="f3097-115">若要確認原則已生效，請在使用者的 Windows 10 裝置上，移至 [Windows 更新]，選擇 [ **高級選項**]，然後確認設定會變暗。</span><span class="sxs-lookup"><span data-stu-id="f3097-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="f3097-116">然後，按一下 **[選擇如何傳送更新**]，並確認設定會變暗，而且會出現下列訊息： **部分設定是由您的組織隱藏或管理**。</span><span class="sxs-lookup"><span data-stu-id="f3097-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

