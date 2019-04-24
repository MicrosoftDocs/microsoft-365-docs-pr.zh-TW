---
title: 保護 Windows 10 裝置
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: '了解預設及其他設定，以保護 Windows 10 裝置。 '
ms.openlocfilehash: 6f06936c2075710210ad9e29ee92905b3b49917a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278050"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="5eb63-103">保護 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="5eb63-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="5eb63-p101">您在此進行的設定為預設 Windows 10 裝置原則的一部分。所有連接至 Windows 10 裝置 (包含行動裝置及電腦) 的使用者，一旦使用其公司帳戶登入後，就會自動接收這些設定。建議您在設定時先接受預設原則，並於稍後新增以特定使用者群組為目標的原則。</span><span class="sxs-lookup"><span data-stu-id="5eb63-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="5eb63-107">保護 Windows 10 裝置的設定</span><span class="sxs-lookup"><span data-stu-id="5eb63-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="5eb63-108">預設所有設定都是**上**。</span><span class="sxs-lookup"><span data-stu-id="5eb63-108">By default all settings are **On**.</span></span> <span data-ttu-id="5eb63-109">下列為可用的設定：</span><span class="sxs-lookup"><span data-stu-id="5eb63-109">The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5eb63-110">設定</span><span class="sxs-lookup"><span data-stu-id="5eb63-110">Setting</span></span>  <br/> |<span data-ttu-id="5eb63-111">說明</span><span class="sxs-lookup"><span data-stu-id="5eb63-111">Description</span></span>  <br/> |
|<span data-ttu-id="5eb63-112">使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害</span><span class="sxs-lookup"><span data-stu-id="5eb63-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="5eb63-113">需要開啟 Windows Defender 防毒軟體，以保護電腦免於遭受連接至網際網路時的安全威脅。</span><span class="sxs-lookup"><span data-stu-id="5eb63-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="5eb63-114">協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅</span><span class="sxs-lookup"><span data-stu-id="5eb63-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="5eb63-115">開啟 Microsoft Edge 中的設定，以協助保護使用者免受惡意網站與下載檔案的威脅。</span><span class="sxs-lookup"><span data-stu-id="5eb63-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="5eb63-116">閒置這段時間之後關閉裝置螢幕</span><span class="sxs-lookup"><span data-stu-id="5eb63-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="5eb63-p103">確保使用者閒置時，公司資料已受到保護。使用者可能會在咖啡館等公共場所工作，當使用者暫時離開或是分心時，他們的裝置就容易受到他人任意窺伺。此設定能讓您控制螢幕將於使用者閒置多久之後關閉。</span><span class="sxs-lookup"><span data-stu-id="5eb63-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="5eb63-120">允許使用者從 Microsoft Store 下載 App</span><span class="sxs-lookup"><span data-stu-id="5eb63-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="5eb63-121">讓使用者從 Microsoft Store 下載並安裝 App。</span><span class="sxs-lookup"><span data-stu-id="5eb63-121">Lets users download and install apps from the Microsoft Store.</span></span> <span data-ttu-id="5eb63-122">應用程式包括所有項目從遊戲生產力工具]，讓我們保留**上**，此設定，但您可以將它關閉額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="5eb63-122">Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.</span></span>  <br/> |
|<span data-ttu-id="5eb63-123">允許使用者存取 Cortana</span><span class="sxs-lookup"><span data-stu-id="5eb63-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="5eb63-124">Cortana 非常實用！</span><span class="sxs-lookup"><span data-stu-id="5eb63-124">Cortana can be very helpful!</span></span> <span data-ttu-id="5eb63-125">她可以開啟設定或關閉您，提供指示，並請確定您已在約會現場，因此我們將此**上**預設。</span><span class="sxs-lookup"><span data-stu-id="5eb63-125">She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.</span></span>  <br/> |
|<span data-ttu-id="5eb63-126">允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告</span><span class="sxs-lookup"><span data-stu-id="5eb63-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="5eb63-127">Windows 祕訣相當實用，並且能在新功能推出時引導使用者。</span><span class="sxs-lookup"><span data-stu-id="5eb63-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="5eb63-128">自動讓 Windows 10 裝置保持在最新狀態</span><span class="sxs-lookup"><span data-stu-id="5eb63-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="5eb63-129">確保 Windows 10 裝置能自動收到最新的更新。</span><span class="sxs-lookup"><span data-stu-id="5eb63-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

