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
ms.openlocfilehash: b586e687d6b61873b77fac8586396ab51fd90b9b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898061"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="5d21a-103">保護 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="5d21a-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="5d21a-104">本文適用于 Microsoft 365 商務版 Premium。</span><span class="sxs-lookup"><span data-stu-id="5d21a-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="5d21a-105">您在此進行的設定為預設 Windows 10 裝置原則的一部分。</span><span class="sxs-lookup"><span data-stu-id="5d21a-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="5d21a-106">透過其工作帳戶登入，所有連接 Windows 10 裝置的使用者（包括行動裝置和電腦）都會自動接收這些設定。</span><span class="sxs-lookup"><span data-stu-id="5d21a-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="5d21a-107">建議您在設定時先接受預設原則，並於稍後新增以特定使用者群組為目標的原則。</span><span class="sxs-lookup"><span data-stu-id="5d21a-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="5d21a-108">保護 Windows 10 裝置的設定</span><span class="sxs-lookup"><span data-stu-id="5d21a-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="5d21a-109">所有設定預設為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="5d21a-109">By default all settings are **On**.</span></span> <span data-ttu-id="5d21a-110">下列為可用的設定：</span><span class="sxs-lookup"><span data-stu-id="5d21a-110">The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5d21a-111">設定</span><span class="sxs-lookup"><span data-stu-id="5d21a-111">Setting</span></span>  <br/> |<span data-ttu-id="5d21a-112">描述</span><span class="sxs-lookup"><span data-stu-id="5d21a-112">Description</span></span>  <br/> |
|<span data-ttu-id="5d21a-113">使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害</span><span class="sxs-lookup"><span data-stu-id="5d21a-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="5d21a-114">需要開啟 Windows Defender 防毒軟體，以保護電腦免於遭受連接至網際網路時的安全威脅。</span><span class="sxs-lookup"><span data-stu-id="5d21a-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="5d21a-115">協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅</span><span class="sxs-lookup"><span data-stu-id="5d21a-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="5d21a-116">開啟 Microsoft Edge 中的設定，以協助保護使用者免受惡意網站與下載檔案的威脅。</span><span class="sxs-lookup"><span data-stu-id="5d21a-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="5d21a-117">閒置這段時間之後關閉裝置螢幕</span><span class="sxs-lookup"><span data-stu-id="5d21a-117">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="5d21a-p103">確保使用者閒置時，公司資料已受到保護。使用者可能會在咖啡館等公共場所工作，當使用者暫時離開或是分心時，他們的裝置就容易受到他人任意窺伺。此設定能讓您控制螢幕將於使用者閒置多久之後關閉。</span><span class="sxs-lookup"><span data-stu-id="5d21a-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="5d21a-121">允許使用者從 Microsoft Store 下載 App</span><span class="sxs-lookup"><span data-stu-id="5d21a-121">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="5d21a-122">讓使用者從 Microsoft Store 下載並安裝 App。</span><span class="sxs-lookup"><span data-stu-id="5d21a-122">Lets users download and install apps from the Microsoft Store.</span></span> <span data-ttu-id="5d21a-123">應用程式包括從遊戲到生產力工具的所有專案，因此我們將此設定保留為 **開啟**，但您可以關閉此設定，以進行額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="5d21a-123">Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.</span></span>  <br/> |
|