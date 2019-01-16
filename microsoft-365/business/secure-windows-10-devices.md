---
title: 保護 Windows 10 裝置
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: '了解預設和安全 Windows 10 裝置的其他設定。 '
ms.openlocfilehash: 0bdf6a56d880cb84f4a4f50550539d97c006ba49
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866677"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="0ec2b-103">保護 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="0ec2b-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="0ec2b-p101">您在此進行的設定為預設 Windows 10 裝置原則的一部分。所有連接至 Windows 10 裝置 (包含行動裝置及電腦) 的使用者，一旦使用其公司帳戶登入後，就會自動接收這些設定。建議您在設定時先接受預設原則，並於稍後新增以特定使用者群組為目標的原則。</span><span class="sxs-lookup"><span data-stu-id="0ec2b-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="0ec2b-107">保護 Windows 10 裝置的設定</span><span class="sxs-lookup"><span data-stu-id="0ec2b-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="0ec2b-p102">根據預設**上**都所有設定。會提供下列設定：</span><span class="sxs-lookup"><span data-stu-id="0ec2b-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0ec2b-110">設定</span><span class="sxs-lookup"><span data-stu-id="0ec2b-110">Setting</span></span>  <br/> |<span data-ttu-id="0ec2b-111">描述</span><span class="sxs-lookup"><span data-stu-id="0ec2b-111">Description</span></span>  <br/> |
|<span data-ttu-id="0ec2b-112">使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害</span><span class="sxs-lookup"><span data-stu-id="0ec2b-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="0ec2b-113">需要開啟 Windows Defender 防毒軟體，以保護電腦免於遭受連接至網際網路時的安全威脅。</span><span class="sxs-lookup"><span data-stu-id="0ec2b-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="0ec2b-114">協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅</span><span class="sxs-lookup"><span data-stu-id="0ec2b-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="0ec2b-115">開啟 Microsoft Edge 中的設定，以協助保護使用者免受惡意網站與下載檔案的威脅。</span><span class="sxs-lookup"><span data-stu-id="0ec2b-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="0ec2b-116">閒置這段時間之後關閉裝置螢幕</span><span class="sxs-lookup"><span data-stu-id="0ec2b-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="0ec2b-p103">確保使用者閒置時，公司資料已受到保護。使用者可能會在咖啡館等公共場所工作，當使用者暫時離開或是分心時，他們的裝置就容易受到他人任意窺伺。此設定能讓您控制螢幕將於使用者閒置多久之後關閉。</span><span class="sxs-lookup"><span data-stu-id="0ec2b-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="0ec2b-120">允許使用者從 Microsoft Store 下載 App</span><span class="sxs-lookup"><span data-stu-id="0ec2b-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="0ec2b-p104">可讓使用者從下載及安裝的應用程式之 Microsoft 存放區。應用程式包含每個項目從遊樂場生產力工具]，讓我們保留**在**此設定，但您可以將它關閉的額外安全性。</span><span class="sxs-lookup"><span data-stu-id="0ec2b-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="0ec2b-123">允許使用者存取 Cortana</span><span class="sxs-lookup"><span data-stu-id="0ec2b-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="0ec2b-p105">Cortana 可以是非常有用 ！她可以設定開啟或關閉您、 授與指示，並請確定您已對時間的約會 （英文），因此我們保留此**上**預設。</span><span class="sxs-lookup"><span data-stu-id="0ec2b-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="0ec2b-126">允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告</span><span class="sxs-lookup"><span data-stu-id="0ec2b-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="0ec2b-127">Windows 祕訣相當實用，並且能在新功能推出時引導使用者。</span><span class="sxs-lookup"><span data-stu-id="0ec2b-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="0ec2b-128">自動讓 Windows 10 裝置保持在最新狀態</span><span class="sxs-lookup"><span data-stu-id="0ec2b-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="0ec2b-129">確保 Windows 10 裝置能自動收到最新的更新。</span><span class="sxs-lookup"><span data-stu-id="0ec2b-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

