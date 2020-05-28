---
title: 保護 Windows 10 裝置
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 瞭解設定 Windows 10 裝置在登入其工作或學校帳戶時，可接收之預設裝置原則的設定。
ms.openlocfilehash: 7714a6e47de8a254d836ca2e158b92907b87f8c3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402727"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="6f0ce-103">保護 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="6f0ce-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="6f0ce-104">您在此進行的設定為預設 Windows 10 裝置原則的一部分。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-104">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="6f0ce-105">透過其工作帳戶登入，所有連接 Windows 10 裝置的使用者（包括行動裝置和電腦）都會自動接收這些設定。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-105">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="6f0ce-106">建議您在設定時先接受預設原則，並於稍後新增以特定使用者群組為目標的原則。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-106">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="6f0ce-107">保護 Windows 10 裝置的設定</span><span class="sxs-lookup"><span data-stu-id="6f0ce-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="6f0ce-108">所有設定預設為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-108">By default all settings are **On**.</span></span> <span data-ttu-id="6f0ce-109">下列為可用的設定：</span><span class="sxs-lookup"><span data-stu-id="6f0ce-109">The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6f0ce-110">設定</span><span class="sxs-lookup"><span data-stu-id="6f0ce-110">Setting</span></span>  <br/> |<span data-ttu-id="6f0ce-111">說明</span><span class="sxs-lookup"><span data-stu-id="6f0ce-111">Description</span></span>  <br/> |
|<span data-ttu-id="6f0ce-112">使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害</span><span class="sxs-lookup"><span data-stu-id="6f0ce-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="6f0ce-113">需要開啟 Windows Defender 防毒軟體，以保護電腦免於遭受連接至網際網路時的安全威脅。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="6f0ce-114">協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅</span><span class="sxs-lookup"><span data-stu-id="6f0ce-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="6f0ce-115">開啟 Microsoft Edge 中的設定，以協助保護使用者免受惡意網站與下載檔案的威脅。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="6f0ce-116">閒置這段時間之後關閉裝置螢幕</span><span class="sxs-lookup"><span data-stu-id="6f0ce-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="6f0ce-p103">確保使用者閒置時，公司資料已受到保護。使用者可能會在咖啡館等公共場所工作，當使用者暫時離開或是分心時，他們的裝置就容易受到他人任意窺伺。此設定能讓您控制螢幕將於使用者閒置多久之後關閉。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="6f0ce-120">允許使用者從 Microsoft Store 下載 App</span><span class="sxs-lookup"><span data-stu-id="6f0ce-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="6f0ce-121">讓使用者從 Microsoft Store 下載並安裝 App。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-121">Lets users download and install apps from the Microsoft Store.</span></span> <span data-ttu-id="6f0ce-122">應用程式包括從遊戲到生產力工具的所有專案，因此我們將此設定保留為**開啟**，但您可以關閉此設定，以進行額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-122">Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.</span></span>  <br/> |
|<span data-ttu-id="6f0ce-123">允許使用者存取 Cortana</span><span class="sxs-lookup"><span data-stu-id="6f0ce-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="6f0ce-124">Cortana 非常實用！</span><span class="sxs-lookup"><span data-stu-id="6f0ce-124">Cortana can be very helpful!</span></span> <span data-ttu-id="6f0ce-125">Cortana 可以為您開啟或關閉您的設定、提供行車方案，並確定您已開啟約會時間，因此我們預設會將此設定保留為**開啟**。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-125">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="6f0ce-126">允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告</span><span class="sxs-lookup"><span data-stu-id="6f0ce-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="6f0ce-127">Windows 祕訣相當實用，並且能在新功能推出時引導使用者。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="6f0ce-128">自動讓 Windows 10 裝置保持在最新狀態</span><span class="sxs-lookup"><span data-stu-id="6f0ce-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="6f0ce-129">確保 Windows 10 裝置能自動收到最新的更新。</span><span class="sxs-lookup"><span data-stu-id="6f0ce-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

