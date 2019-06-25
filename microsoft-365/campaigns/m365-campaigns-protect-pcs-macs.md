---
title: 保護未受管理的 Windows 10 電腦和 Mac
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 使用 Microsoft 365 的市場活動來防禦網路釣魚和其他攻擊。
ms.openlocfilehash: 8b83fa9c145f2c17347fc4c2983c64d4003f46c8
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183254"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="18da4-103">保護未受管理的 Windows 10 電腦和 Mac</span><span class="sxs-lookup"><span data-stu-id="18da4-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="18da4-104">您可以使用 Microsoft Intune 來管理 Windows 10 電腦和 Mac, 這可讓您在存取環境中的資料之前, 先確保這些電腦的健康和安全。</span><span class="sxs-lookup"><span data-stu-id="18da4-104">You can manage Windows 10 PCs and Macs by enrolling these into Microsoft Intune, which allows you to ensure these are healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="18da4-105">不過, 許多行銷活動和小型企業包含的人員會攜帶自己的裝置 (byod), 而該組織不會管理這些裝置。</span><span class="sxs-lookup"><span data-stu-id="18da4-105">However, many campaigns and small businesses include staff that bring their own devices (byod) which will not be managed by the organization.</span></span> <span data-ttu-id="18da4-106">針對這些未受管理的電腦和 Mac, 請使用本文來確保設定最基本的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="18da4-106">For these unmanaged PCs and Macs, use this article to ensure minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="18da4-107">保護執行 Windows 10 或 Mac 版的電腦</span><span class="sxs-lookup"><span data-stu-id="18da4-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="18da4-108">如果您的組織不會管理您的 Windows 10 電腦或 Mac, 請務必設定這些安全性功能。</span><span class="sxs-lookup"><span data-stu-id="18da4-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10tabwindows10"></a>[<span data-ttu-id="18da4-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="18da4-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="18da4-110">**開啟裝置加密**</span><span class="sxs-lookup"><span data-stu-id="18da4-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="18da4-111">裝置加密在各種 Windows 裝置上都可以使用, 並可加密資料以協助保護您的資料。</span><span class="sxs-lookup"><span data-stu-id="18da4-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="18da4-112">如果您開啟裝置加密, 只有授權的個人才能存取您的裝置和資料。</span><span class="sxs-lookup"><span data-stu-id="18da4-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="18da4-113">請參閱[開啟裝置加密](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption)以取得指示。</span><span class="sxs-lookup"><span data-stu-id="18da4-113">See [turn on device encryption](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="18da4-114">如果裝置上無法使用裝置加密, 您可以改為開啟標準的[BitLocker 加密](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption)。</span><span class="sxs-lookup"><span data-stu-id="18da4-114">If device encryption is not available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="18da4-115">(BitLocker 在 Windows 10 首頁版上無法使用。)</span><span class="sxs-lookup"><span data-stu-id="18da4-115">(BitLocker is not available on Windows 10 Home edition.)</span></span> 



<span data-ttu-id="18da4-116">**使用 Windows 安全性保護您的裝置**</span><span class="sxs-lookup"><span data-stu-id="18da4-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="18da4-117">如果您有 Windows 10, 您可以使用 Windows 安全性取得最新的病毒防護。</span><span class="sxs-lookup"><span data-stu-id="18da4-117">If you have Windows 10, you’ll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="18da4-118">當您第一次啟動 Windows 10 時, Windows 安全性就會開啟, 並積極協助您掃描惡意程式碼 (惡意軟體)、病毒和安全性威脅, 以保護您的電腦。</span><span class="sxs-lookup"><span data-stu-id="18da4-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="18da4-119">Windows 安全性使用即時保護來掃描您下載或在您的電腦上執行的所有專案。</span><span class="sxs-lookup"><span data-stu-id="18da4-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="18da4-120">Windows Update 會自動下載 Windows 安全性的更新, 以協助保護您的電腦安全性並防止威脅。</span><span class="sxs-lookup"><span data-stu-id="18da4-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="18da4-121">如果您有舊版的 Windows, 且使用 Microsoft 安全性基本版, 則最好移至 Windows 安全性。</span><span class="sxs-lookup"><span data-stu-id="18da4-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it’s a good idea to move to Windows Security.</span></span> <span data-ttu-id="18da4-122">如需詳細資訊, 請參閱[協助保護我的裝置與 Windows 安全性](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security)。</span><span class="sxs-lookup"><span data-stu-id="18da4-122">See [help protect my device with Windows Security](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security) for more information.</span></span>

<span data-ttu-id="18da4-123">**開啟 Windows 防火牆**</span><span class="sxs-lookup"><span data-stu-id="18da4-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="18da4-124">即使已開啟另一個防火牆, 您也應該始終執行 Windows 防火牆。</span><span class="sxs-lookup"><span data-stu-id="18da4-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="18da4-125">關閉 Windows 防火牆可能會讓您的裝置 (和您的網路) 更容易受到未經授權的存取。</span><span class="sxs-lookup"><span data-stu-id="18da4-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="18da4-126">請參閱[開啟或關閉 Windows 防火牆](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)以取得指示</span><span class="sxs-lookup"><span data-stu-id="18da4-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mactabmac"></a>[<span data-ttu-id="18da4-127">Mac</span><span class="sxs-lookup"><span data-stu-id="18da4-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="18da4-128">**使用 FileVault 來加密您的 Mac 磁片**</span><span class="sxs-lookup"><span data-stu-id="18da4-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="18da4-129">磁片加密會在裝置遺失或被盜時, 保護資料。</span><span class="sxs-lookup"><span data-stu-id="18da4-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="18da4-130">FileVault 完整磁片加密有助於防止未經授權的存取啟動磁片上的資訊。</span><span class="sxs-lookup"><span data-stu-id="18da4-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="18da4-131">如需相關指示, 請參閱[使用 FileVault 加密 Mac 上的開機磁片](https://support.apple.com/HT204837)。</span><span class="sxs-lookup"><span data-stu-id="18da4-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="18da4-132">**保護 mac 免遭惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="18da4-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="18da4-133">Microsoft 建議您在 Mac 上安裝和使用可靠的防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="18da4-133">Microsoft recommends you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="18da4-134">如需選項清單, 請參閱下列文章:[最佳 Mac 防病毒 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。</span><span class="sxs-lookup"><span data-stu-id="18da4-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="18da4-135">您也可以只從可靠的來源使用軟體, 來減少惡意程式碼的風險。</span><span class="sxs-lookup"><span data-stu-id="18da4-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="18da4-136">安全性 & 隱私權偏好設定中的設定可讓您指定 Mac 上所安裝之軟體的來源。</span><span class="sxs-lookup"><span data-stu-id="18da4-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="18da4-137">如需詳細資訊, 請參閱[保護您的 Mac 免受惡意軟體的攻擊](https://support.apple.com/kb/PH25087)。</span><span class="sxs-lookup"><span data-stu-id="18da4-137">See [protect your Mac from malware](https://support.apple.com/kb/PH25087) for more information.</span></span>

<span data-ttu-id="18da4-138">**開啟防火牆保護**</span><span class="sxs-lookup"><span data-stu-id="18da4-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="18da4-139">當您連線至網際網路或網路時, 使用防火牆設定來保護您的 Mac 免受其他電腦所初始化的不需要連絡人。</span><span class="sxs-lookup"><span data-stu-id="18da4-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you’re connected to the Internet or a network.</span></span> <span data-ttu-id="18da4-140">若沒有此保護, 您的 Mac 可能更容易受到未經授權的存取。</span><span class="sxs-lookup"><span data-stu-id="18da4-140">Without this protection your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="18da4-141">如需相關指示, 請參閱[相關應用程式防火牆](https://support.apple.com/HT201642)。</span><span class="sxs-lookup"><span data-stu-id="18da4-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
