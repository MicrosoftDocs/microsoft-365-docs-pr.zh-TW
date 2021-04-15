---
title: 使用防篡改保護來保護安全性設定
ms.reviewer: shwjha, hayhov
manager: dansimp
description: 使用防篡改保護，防止惡意應用程式變更重要的安全性設定。
keywords: 惡意程式碼、defender、防毒程式和防篡改保護
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 84864965d7a18902a01307c1dcf373fa7c0534e8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765572"
---
# <a name="protect-security-settings-with-tamper-protection"></a><span data-ttu-id="1508a-104">使用防篡改保護來保護安全性設定</span><span class="sxs-lookup"><span data-stu-id="1508a-104">Protect security settings with tamper protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1508a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1508a-105">**Applies to:**</span></span>

- [<span data-ttu-id="1508a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1508a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1508a-107">對執行下列其中一個 Windows 版本的裝置可使用防篡改保護：</span><span class="sxs-lookup"><span data-stu-id="1508a-107">Tamper protection is available for devices that are running one of the following versions of Windows:</span></span>

- <span data-ttu-id="1508a-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1508a-108">Windows 10</span></span>
- <span data-ttu-id="1508a-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="1508a-109">Windows Server 2019</span></span>
- <span data-ttu-id="1508a-110">Windows Server，版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="1508a-110">Windows Server, version 1803 or later</span></span>
- <span data-ttu-id="1508a-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1508a-111">Windows Server 2016</span></span>

## <a name="overview"></a><span data-ttu-id="1508a-112">概觀</span><span class="sxs-lookup"><span data-stu-id="1508a-112">Overview</span></span>

<span data-ttu-id="1508a-113">在某些網路攻擊中，不良的演員會嘗試停用電腦上的安全性功能，例如防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="1508a-113">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="1508a-114">不良的演員，例如停用您的安全性功能，以更輕鬆地存取資料、安裝惡意程式碼，或利用您的資料、身分識別及裝置。</span><span class="sxs-lookup"><span data-stu-id="1508a-114">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span> <span data-ttu-id="1508a-115">防篡改保護可協助避免發生這類問題。</span><span class="sxs-lookup"><span data-stu-id="1508a-115">Tamper protection helps prevent these kinds of things from occurring.</span></span>

<span data-ttu-id="1508a-116">使用防篡改保護時，惡意應用程式無法採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="1508a-116">With tamper protection, malicious apps are prevented from taking actions such as:</span></span>

- <span data-ttu-id="1508a-117">停用病毒和威脅防護</span><span class="sxs-lookup"><span data-stu-id="1508a-117">Disabling virus and threat protection</span></span>
- <span data-ttu-id="1508a-118">停用即時保護</span><span class="sxs-lookup"><span data-stu-id="1508a-118">Disabling real-time protection</span></span>
- <span data-ttu-id="1508a-119">關閉行為監控</span><span class="sxs-lookup"><span data-stu-id="1508a-119">Turning off behavior monitoring</span></span>
- <span data-ttu-id="1508a-120">停用防病毒 (例如 IOfficeAntivirus (IOAV) ) </span><span class="sxs-lookup"><span data-stu-id="1508a-120">Disabling antivirus (such as IOfficeAntivirus (IOAV))</span></span>
- <span data-ttu-id="1508a-121">停用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="1508a-121">Disabling cloud-delivered protection</span></span>
- <span data-ttu-id="1508a-122">移除安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="1508a-122">Removing security intelligence updates</span></span>

### <a name="how-it-works"></a><span data-ttu-id="1508a-123">運作方式</span><span class="sxs-lookup"><span data-stu-id="1508a-123">How it works</span></span>

<span data-ttu-id="1508a-124">防篡改保護基本上會鎖定 Microsoft Defender 防病毒，並防止您的安全性設定透過應用程式和方法加以變更，例如：</span><span class="sxs-lookup"><span data-stu-id="1508a-124">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods such as:</span></span>

- <span data-ttu-id="1508a-125">在 Windows 裝置上設定登錄編輯程式中的設定</span><span class="sxs-lookup"><span data-stu-id="1508a-125">Configuring settings in Registry Editor on your Windows device</span></span>
- <span data-ttu-id="1508a-126">透過 PowerShell Cmdlet 變更設定</span><span class="sxs-lookup"><span data-stu-id="1508a-126">Changing settings through PowerShell cmdlets</span></span>
- <span data-ttu-id="1508a-127">透過「群組原則」編輯或移除安全性設定</span><span class="sxs-lookup"><span data-stu-id="1508a-127">Editing or removing security settings through group policies</span></span>

<span data-ttu-id="1508a-128">防篡改保護不會使您無法查看安全性設定。</span><span class="sxs-lookup"><span data-stu-id="1508a-128">Tamper protection doesn't prevent you from viewing your security settings.</span></span> <span data-ttu-id="1508a-129">而且，篡改保護不會影響協力廠商防病毒應用程式如何在 Windows 安全性應用程式中註冊。</span><span class="sxs-lookup"><span data-stu-id="1508a-129">And, tamper protection doesn't affect how third-party antivirus apps register with the Windows Security app.</span></span> <span data-ttu-id="1508a-130">如果您的組織使用 Windows 10 企業版 E5，個別的使用者就無法變更不可篡改的保護設定。在這種情況下，安全小組會管理防篡改保護。</span><span class="sxs-lookup"><span data-stu-id="1508a-130">If your organization is using Windows 10 Enterprise E5, individual users can't change the tamper protection setting; in those cases, tamper protection is managed by your security team.</span></span>

### <a name="what-do-you-want-to-do"></a><span data-ttu-id="1508a-131">您要執行的工作</span><span class="sxs-lookup"><span data-stu-id="1508a-131">What do you want to do?</span></span>

| <span data-ttu-id="1508a-132">若要執行此工作 .。。</span><span class="sxs-lookup"><span data-stu-id="1508a-132">To perform this task...</span></span> | <span data-ttu-id="1508a-133">請參閱本節 .。。</span><span class="sxs-lookup"><span data-stu-id="1508a-133">See this section...</span></span> |
|:---|:---|
| <span data-ttu-id="1508a-134">在 Microsoft Defender 安全中心的 (或關閉) 開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-134">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> <p><span data-ttu-id="1508a-135">管理整個租使用者的防篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-135">Manage tamper protection across your tenant</span></span> | [<span data-ttu-id="1508a-136">使用 Microsoft Defender 安全中心管理組織的篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-136">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| <span data-ttu-id="1508a-137">使用 Intune 針對所有或部分組織的 (或關閉) 開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-137">Turn tamper protection on (or off) for all or part of your organization using Intune</span></span> <p><span data-ttu-id="1508a-138">微調組織中防篡改的保護設定</span><span class="sxs-lookup"><span data-stu-id="1508a-138">Fine-tune tamper protection settings in your organization</span></span> | [<span data-ttu-id="1508a-139">使用 Intune 管理組織的篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-139">Manage tamper protection for your organization using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune) |
| <span data-ttu-id="1508a-140">使用 Configuration Manager 對組織的 (或關閉) 開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-140">Turn tamper protection on (or off) for your organization with Configuration Manager</span></span> | [<span data-ttu-id="1508a-141">使用 Configuration Manager 的承租人附加程式管理組織的篡改保護，版本2006</span><span class="sxs-lookup"><span data-stu-id="1508a-141">Manage tamper protection for your organization using tenant attach with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| <span data-ttu-id="1508a-142">針對個別裝置 (或關閉) 開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-142">Turn tamper protection on (or off) for an individual device</span></span> | [<span data-ttu-id="1508a-143">管理個別裝置上的非篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-143">Manage tamper protection on an individual device</span></span>](#manage-tamper-protection-on-an-individual-device) |
| <span data-ttu-id="1508a-144">在裝置上查看有關篡改嘗試的詳細資料</span><span class="sxs-lookup"><span data-stu-id="1508a-144">View details about tampering attempts on devices</span></span> | [<span data-ttu-id="1508a-145">查看有關篡改嘗試的資訊</span><span class="sxs-lookup"><span data-stu-id="1508a-145">View information about tampering attempts</span></span>](#view-information-about-tampering-attempts) |
| <span data-ttu-id="1508a-146">回顧安全性建議</span><span class="sxs-lookup"><span data-stu-id="1508a-146">Review your security recommendations</span></span> | [<span data-ttu-id="1508a-147">檢查安全性建議</span><span class="sxs-lookup"><span data-stu-id="1508a-147">Review security recommendations</span></span>](#review-your-security-recommendations) |
| <span data-ttu-id="1508a-148">複查 (FAQs 的常見問題解答清單) </span><span class="sxs-lookup"><span data-stu-id="1508a-148">Review the list of frequently asked questions (FAQs)</span></span> | [<span data-ttu-id="1508a-149">流覽 FAQs</span><span class="sxs-lookup"><span data-stu-id="1508a-149">Browse the FAQs</span></span>](#view-information-about-tampering-attempts) |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a><span data-ttu-id="1508a-150">使用 Microsoft Defender 安全中心管理組織的篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-150">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>

<span data-ttu-id="1508a-151">您可以使用 Microsoft Defender Security Center () ，為您的租使用者開啟或關閉不可篡改的保護 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="1508a-151">Tamper protection can be turned on or off for your tenant using the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="1508a-152">以下是一些需要謹記的要點：</span><span class="sxs-lookup"><span data-stu-id="1508a-152">Here are a few points to keep in mind:</span></span>

- <span data-ttu-id="1508a-153">目前，在 Microsoft Defender Security Center 中管理防篡改保護的選項預設是針對新的部署。</span><span class="sxs-lookup"><span data-stu-id="1508a-153">Currently, the option to manage tamper protection in the Microsoft Defender Security Center is on by default for new deployments.</span></span> <span data-ttu-id="1508a-154">針對現有的部署，可在自願加入時進行防篡改保護，讓計畫在近期使用此預設方法。</span><span class="sxs-lookup"><span data-stu-id="1508a-154">For existing deployments, tamper protection is available on an opt-in basis, with plans to make this the default method in the near future.</span></span> <span data-ttu-id="1508a-155"> (若要自願加入，請在 Microsoft Defender Security Center 中，選擇 [**設定**] [  >  **高級功能** 未  >  **篡改保護**]。 ) </span><span class="sxs-lookup"><span data-stu-id="1508a-155">(To opt in, in the Microsoft Defender Security Center, choose **Settings** > **Advanced features** > **Tamper protection**.)</span></span> 

- <span data-ttu-id="1508a-156">當您使用 Microsoft Defender 安全中心管理防篡改保護時，您不需要使用 Intune 或租使用者附加方法。</span><span class="sxs-lookup"><span data-stu-id="1508a-156">When you use the Microsoft Defender Security Center to manage tamper protection, you do not have to use Intune or the tenant attach method.</span></span>

- <span data-ttu-id="1508a-157">當您在 Microsoft Defender Security Center 中管理防篡改保護時，此設定會套用租使用者寬度，影響所有執行 Windows 10、Windows Server 2016 或 Windows Server 2019 的裝置。</span><span class="sxs-lookup"><span data-stu-id="1508a-157">When you manage tamper protection in the Microsoft Defender Security Center, the setting is applied tenant wide, affecting all of your devices that are running Windows 10, Windows Server 2016, or Windows Server 2019.</span></span> <span data-ttu-id="1508a-158">若要微調防篡改保護 (例如對某些裝置進行未篡改的保護，但對某些裝置關閉) 了防篡改保護，請使用 [Intune](#manage-tamper-protection-for-your-organization-using-intune) 或 [Configuration Manager with 承租人 attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)。</span><span class="sxs-lookup"><span data-stu-id="1508a-158">To fine-tune tamper protection (such as having tamper protection on for some devices but off for others), use either [Intune](#manage-tamper-protection-for-your-organization-using-intune) or [Configuration Manager with tenant attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).</span></span>

- <span data-ttu-id="1508a-159">如果您有混合式環境，則在 Intune 中設定的防篡改防護設定會優先于 Microsoft Defender Security Center 中設定的設定。</span><span class="sxs-lookup"><span data-stu-id="1508a-159">If you have a hybrid environment, tamper protection settings configured in Intune take precedence over settings configured in the Microsoft Defender Security Center.</span></span> 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a><span data-ttu-id="1508a-160">在 Microsoft Defender 安全中心管理防篡改保護的需求</span><span class="sxs-lookup"><span data-stu-id="1508a-160">Requirements for managing tamper protection in the Microsoft Defender Security Center</span></span>

- <span data-ttu-id="1508a-161">您必須具有適當的 [許可權](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全域管理員、安全性管理員或安全性作業。</span><span class="sxs-lookup"><span data-stu-id="1508a-161">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="1508a-162">您的 Windows 裝置必須執行下列其中一個 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="1508a-162">Your Windows devices must be running one of the following versions of Windows:</span></span>
   - <span data-ttu-id="1508a-163">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1508a-163">Windows 10</span></span>
   - [<span data-ttu-id="1508a-164">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="1508a-164">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
   - <span data-ttu-id="1508a-165">Windows Server，版本 [1803](/windows/release-health/status-windows-10-1803) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="1508a-165">Windows Server, version [1803](/windows/release-health/status-windows-10-1803) or later</span></span>
   - [<span data-ttu-id="1508a-166">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1508a-166">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016)
   - <span data-ttu-id="1508a-167">如需有關版本的詳細資訊，請參閱 [Windows 10 版本資訊](/windows/release-health/release-information)。</span><span class="sxs-lookup"><span data-stu-id="1508a-167">For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).</span></span>

- <span data-ttu-id="1508a-168">您的裝置必須 [架至 Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="1508a-168">Your devices must be [onboarded to Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding).</span></span>

- <span data-ttu-id="1508a-169">您的裝置必須使用反惡意程式碼平臺版本 4.18.2010.7 (或以上版本) 和反惡意程式碼引擎版本 1.1.17600.5 (或以上) 。</span><span class="sxs-lookup"><span data-stu-id="1508a-169">Your devices must be using anti-malware platform version 4.18.2010.7 (or above) and anti-malware engine version 1.1.17600.5 (or above).</span></span> <span data-ttu-id="1508a-170"> ([管理 Microsoft Defender 防病毒更新並套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="1508a-170">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

- <span data-ttu-id="1508a-171">必須開啟[雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="1508a-171">[Cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be turned on.</span></span>

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a><span data-ttu-id="1508a-172">在 Microsoft Defender 安全中心的 (或關閉) 開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-172">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> 

![在 Microsoft Defender Security Center 中開啟防篡改保護](images/mde-turn-tamperprotect-on.png)

1. <span data-ttu-id="1508a-174">請移至 Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="1508a-174">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="1508a-175">選擇 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="1508a-175">Choose **Settings**.</span></span>

3. <span data-ttu-id="1508a-176">移至 **[一般**  >  **高級功能**]，然後開啟 [防篡改保護]。</span><span class="sxs-lookup"><span data-stu-id="1508a-176">Go to **General** > **Advanced features**, and then turn tamper protection on.</span></span>

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a><span data-ttu-id="1508a-177">使用 Intune 管理組織的篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-177">Manage tamper protection for your organization using Intune</span></span>

<span data-ttu-id="1508a-178">如果您是組織的安全小組的一部分，且您的訂閱包含 [Intune](/intune/fundamentals/what-is-intune)，您可以在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com) 入口網站的 (或關閉) 中開啟防篡改保護。</span><span class="sxs-lookup"><span data-stu-id="1508a-178">If you are part of your organization's security team, and your subscription includes [Intune](/intune/fundamentals/what-is-intune), you can turn tamper protection on (or off) for your organization in the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) portal.</span></span> <span data-ttu-id="1508a-179">當您想要微調防篡改防護設定時，請使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="1508a-179">Use Intune when you want to fine-tune tamper protection settings.</span></span> <span data-ttu-id="1508a-180">例如，如果您想要在某些裝置上啟用防篡改保護，但不是全部，請使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="1508a-180">For example, if you want to enable tamper protection on some devices, but not all, use Intune.</span></span>

### <a name="requirements-for-managing-tamper-protection-in-intune"></a><span data-ttu-id="1508a-181">在 Intune 中管理防篡改保護的需求</span><span class="sxs-lookup"><span data-stu-id="1508a-181">Requirements for managing tamper protection in Intune</span></span>

- <span data-ttu-id="1508a-182">您必須具有適當的 [許可權](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全域管理員、安全性管理員或安全性作業。</span><span class="sxs-lookup"><span data-stu-id="1508a-182">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="1508a-183">您的組織使用 [Intune 管理裝置](/intune/fundamentals/what-is-device-management)。</span><span class="sxs-lookup"><span data-stu-id="1508a-183">Your organization uses [Intune to manage devices](/intune/fundamentals/what-is-device-management).</span></span> <span data-ttu-id="1508a-184">需要 ([Intune 授權](/intune/fundamentals/licenses) ;Intune 隨附于 Microsoft 365 E5。 ) </span><span class="sxs-lookup"><span data-stu-id="1508a-184">([Intune licenses](/intune/fundamentals/licenses) are required; Intune is included in Microsoft 365 E5.)</span></span>

- <span data-ttu-id="1508a-185">您的 Windows 裝置必須執行 Windows 10 作業系統 [1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)、 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="1508a-185">Your Windows devices must be running Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) or later.</span></span> <span data-ttu-id="1508a-186"> (如需有關版本的詳細資訊，請參閱 [Windows 10 版本資訊](/windows/release-health/release-information)。 ) </span><span class="sxs-lookup"><span data-stu-id="1508a-186">(For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).)</span></span>

- <span data-ttu-id="1508a-187">您必須使用 Windows 安全性搭配 [安全性情報](https://www.microsoft.com/wdsi/definitions) 更新為版本 1.287.60.0 (或以上) 。</span><span class="sxs-lookup"><span data-stu-id="1508a-187">You must be using Windows security with [security intelligence](https://www.microsoft.com/wdsi/definitions) updated to version 1.287.60.0 (or above).</span></span>

- <span data-ttu-id="1508a-188">您的裝置必須使用反惡意程式碼平臺版本 4.18.1906.3 (或以上版本) 和反惡意程式碼引擎版本 1.1.15500 (或以上版本) 。</span><span class="sxs-lookup"><span data-stu-id="1508a-188">Your devices must be using anti-malware platform version 4.18.1906.3 (or above) and anti-malware engine version 1.1.15500.X (or above).</span></span> <span data-ttu-id="1508a-189"> ([管理 Microsoft Defender 防病毒更新並套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="1508a-189">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

### <a name="turn-tamper-protection-on-or-off-in-intune"></a><span data-ttu-id="1508a-190">在 Intune 中 (或關閉) 開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-190">Turn tamper protection on (or off) in Intune</span></span>

![使用 Intune 開啟防篡改保護](images/turnontamperprotect-MEM.png)

1. <span data-ttu-id="1508a-192">請移至 [Microsoft 端點](https://endpoint.microsoft.com) 管理員系統管理中心，並以您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="1508a-192">Go to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="1508a-193">選取 [**裝置** 設定  >  **設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="1508a-193">Select **Devices** > **Configuration Profiles**.</span></span>

3. <span data-ttu-id="1508a-194">建立設定檔，其中包含下列設定：</span><span class="sxs-lookup"><span data-stu-id="1508a-194">Create a profile that includes the following settings:</span></span>
    - <span data-ttu-id="1508a-195">**平臺： Windows 10 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="1508a-195">**Platform: Windows 10 and later**</span></span>
    - <span data-ttu-id="1508a-196">**配置檔案類型： Endpoint protection**</span><span class="sxs-lookup"><span data-stu-id="1508a-196">**Profile type: Endpoint protection**</span></span>
    - <span data-ttu-id="1508a-197">**類別： Microsoft Defender 安全中心**</span><span class="sxs-lookup"><span data-stu-id="1508a-197">**Category: Microsoft Defender Security Center**</span></span>
    - <span data-ttu-id="1508a-198">**防篡改保護：已啟用**</span><span class="sxs-lookup"><span data-stu-id="1508a-198">**Tamper Protection: Enabled**</span></span>

4. <span data-ttu-id="1508a-199">將設定檔指派給一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="1508a-199">Assign the profile to one or more groups.</span></span>

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a><span data-ttu-id="1508a-200">您使用的是 Windows 作業系統1709、1803或1809嗎？</span><span class="sxs-lookup"><span data-stu-id="1508a-200">Are you using Windows OS 1709, 1803, or 1809?</span></span>

<span data-ttu-id="1508a-201">如果您使用的是 Windows 10 作業系統 [1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)或 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)，您將無法在 Windows 安全性應用程式中看到 **防篡改的保護** 。</span><span class="sxs-lookup"><span data-stu-id="1508a-201">If you are using Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), or [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), you won't see **Tamper Protection** in the Windows Security app.</span></span> <span data-ttu-id="1508a-202">相反地，您可以使用 PowerShell 來判斷是否已啟用防篡改保護。</span><span class="sxs-lookup"><span data-stu-id="1508a-202">Instead, you can use PowerShell to determine whether tamper protection is enabled.</span></span>

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a><span data-ttu-id="1508a-203">使用 PowerShell 來判斷是否已開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-203">Use PowerShell to determine whether tamper protection is turned on</span></span>

1. <span data-ttu-id="1508a-204">開啟 [Windows PowerShell] app。</span><span class="sxs-lookup"><span data-stu-id="1508a-204">Open the Windows PowerShell app.</span></span>

2. <span data-ttu-id="1508a-205">使用 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1508a-205">Use the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet.</span></span>

3. <span data-ttu-id="1508a-206">在結果清單中，尋找 `IsTamperProtected` 。</span><span class="sxs-lookup"><span data-stu-id="1508a-206">In the list of results, look for `IsTamperProtected`.</span></span> <span data-ttu-id="1508a-207"> (*true* 值表示已啟用 [未篡改保護]。 ) </span><span class="sxs-lookup"><span data-stu-id="1508a-207">(A value of *true* means tamper protection is enabled.)</span></span>

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a><span data-ttu-id="1508a-208">使用 Configuration Manager 管理組織的篡改保護，版本2006</span><span class="sxs-lookup"><span data-stu-id="1508a-208">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>

<span data-ttu-id="1508a-209">如果您使用 [的是版本2006的 Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)，您可以使用稱為 *租使用者附加* 的方法，管理 Windows 10、Windows Server 2016 及 windows server 2019 上的防篡改保護設定。</span><span class="sxs-lookup"><span data-stu-id="1508a-209">If you're using [version 2006 of Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), you can manage tamper protection settings on Windows 10, Windows Server 2016, and Windows Server 2019 by using a method called *tenant attach*.</span></span> <span data-ttu-id="1508a-210">承租人附加可讓您將內部部署的設定管理員裝置同步處理至 Microsoft 端點管理員系統管理中心，然後將端點安全性設定原則傳送至內部部署集合 & 裝置。</span><span class="sxs-lookup"><span data-stu-id="1508a-210">Tenant attach enables you to sync your on-premises-only Configuration Manager devices into the Microsoft Endpoint Manager admin center, and then deliver endpoint security configuration policies to on-premises collections & devices.</span></span>

![端點管理員的 Windows 安全性體驗](images/win-security- exp-policy-endpt-security.png)

> [!NOTE]
> <span data-ttu-id="1508a-212">此程式可用於將防篡改保護擴充至執行 Windows 10 和 Windows Server 2019 的裝置。</span><span class="sxs-lookup"><span data-stu-id="1508a-212">The procedure can be used to extend tamper protection to devices running Windows 10 and Windows Server 2019.</span></span> <span data-ttu-id="1508a-213">請務必複查此程式所述資源中的必要條件和其他資訊。</span><span class="sxs-lookup"><span data-stu-id="1508a-213">Make sure to review the prerequisites and other information in the resources mentioned in this procedure.</span></span>

1. <span data-ttu-id="1508a-214">設定租使用者附加。</span><span class="sxs-lookup"><span data-stu-id="1508a-214">Set up tenant attach.</span></span> <span data-ttu-id="1508a-215">若要取得此相關說明，請參閱 [Microsoft 端點管理員租使用者附加：裝置同步處理和裝置動作](/mem/configmgr/tenant-attach/device-sync-actions)。</span><span class="sxs-lookup"><span data-stu-id="1508a-215">To get help with this, see [Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).</span></span>

2. <span data-ttu-id="1508a-216">在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心中，移至 **端點安全性**  >  **防病毒**，然後選擇 [ **+ 建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="1508a-216">In the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Endpoint security** > **Antivirus**, and then choose **+ Create Policy**.</span></span><br/> 
   - <span data-ttu-id="1508a-217">在 [ **平臺** ] 清單中，選取 [ **Windows 10 和 windows Server (] ConfigMgr)**]。</span><span class="sxs-lookup"><span data-stu-id="1508a-217">In the **Platform** list, select **Windows 10 and Windows Server (ConfigMgr)**.</span></span>  
   - <span data-ttu-id="1508a-218">在 [ **設定檔** ] 清單中，選取 [ **Windows 安全性體驗 (預覽])**。</span><span class="sxs-lookup"><span data-stu-id="1508a-218">In the **Profile** list, select **Windows Security experience (preview)**.</span></span> <br/>

3. <span data-ttu-id="1508a-219">將原則部署至您的裝置集合。</span><span class="sxs-lookup"><span data-stu-id="1508a-219">Deploy the policy to your device collection.</span></span>

### <a name="need-help-with-this-method"></a><span data-ttu-id="1508a-220">需要此方法的協助嗎？</span><span class="sxs-lookup"><span data-stu-id="1508a-220">Need help with this method?</span></span> 

<span data-ttu-id="1508a-221">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="1508a-221">See the following resources:</span></span>

- [<span data-ttu-id="1508a-222">Microsoft Intune 中 Windows 安全經驗設定檔的設定</span><span class="sxs-lookup"><span data-stu-id="1508a-222">Settings for the Windows Security experience profile in Microsoft Intune</span></span>](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [<span data-ttu-id="1508a-223">技術社區博客：宣佈 Configuration Manager 租使用者附加用戶端的篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-223">Tech Community Blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a><span data-ttu-id="1508a-224">管理個別裝置上的非篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-224">Manage tamper protection on an individual device</span></span>

> [!NOTE]
> <span data-ttu-id="1508a-225">防篡改保護封鎖會嘗試透過登錄修改 Microsoft Defender 防病毒設定。</span><span class="sxs-lookup"><span data-stu-id="1508a-225">Tamper protection blocks attempts to modify Microsoft Defender Antivirus settings through the registry.</span></span>
>
> <span data-ttu-id="1508a-226">為了協助確保防篡改保護不會干擾協力廠商的安全性產品或可修改這些設定的企業安裝腳本，請移至 [ **Windows 安全性** ] 並將 **安全性情報** 更新為版本1.287.60.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="1508a-226">To help ensure that tamper protection doesn’t interfere with third-party security products or enterprise installation scripts that modify these settings, go to **Windows Security** and update **Security intelligence** to version 1.287.60.0 or later.</span></span> <span data-ttu-id="1508a-227"> (參閱 [安全性智慧更新](https://www.microsoft.com/wdsi/definitions)。 ) </span><span class="sxs-lookup"><span data-stu-id="1508a-227">(See [Security intelligence updates](https://www.microsoft.com/wdsi/definitions).)</span></span>
>
> <span data-ttu-id="1508a-228">當您完成此更新後，防篡改保護會繼續保護您的登錄設定，而記錄會嘗試修改這些設定，而不會傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="1508a-228">Once you’ve made this update, tamper protection continues to protect your registry settings, and logs attempts to modify them without returning errors.</span></span>

<span data-ttu-id="1508a-229">如果您是家庭使用者，或不受安全性小組所管理的設定的制約，您可以使用 Windows 安全性應用程式來管理無法篡改的保護。</span><span class="sxs-lookup"><span data-stu-id="1508a-229">If you are a home user, or you are not subject to settings managed by a security team, you can use the Windows Security app to manage tamper protection.</span></span> <span data-ttu-id="1508a-230">您必須具備裝置的適當系統管理員許可權，才能執行變更安全性設定，例如防篡改的保護。</span><span class="sxs-lookup"><span data-stu-id="1508a-230">You must have appropriate admin permissions on your device to do change security settings, such as tamper protection.</span></span>

<span data-ttu-id="1508a-231">以下是您在 Windows 安全性應用程式中看到的內容：</span><span class="sxs-lookup"><span data-stu-id="1508a-231">Here's what you see in the Windows Security app:</span></span>

![在 Windows 10 首頁中開啟防篡改保護](images/tamperprotectionturnedon.png)

1. <span data-ttu-id="1508a-233">選取 [ **開始**]，然後開始輸入 *安全性*。</span><span class="sxs-lookup"><span data-stu-id="1508a-233">Select **Start**, and start typing *Security*.</span></span> <span data-ttu-id="1508a-234">在搜尋結果中，選取 [ **Windows 安全性**]。</span><span class="sxs-lookup"><span data-stu-id="1508a-234">In the search results, select **Windows Security**.</span></span>

2. <span data-ttu-id="1508a-235">選取 [**病毒 & 威脅防護**]  >  **病毒 & 威脅防護設定**。</span><span class="sxs-lookup"><span data-stu-id="1508a-235">Select **Virus & threat protection** > **Virus & threat protection settings**.</span></span>

3. <span data-ttu-id="1508a-236">設定 **防篡改保護** 為 **開啟** 或 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="1508a-236">Set **Tamper Protection** to **On** or **Off**.</span></span>



## <a name="view-information-about-tampering-attempts"></a><span data-ttu-id="1508a-237">查看有關篡改嘗試的資訊</span><span class="sxs-lookup"><span data-stu-id="1508a-237">View information about tampering attempts</span></span>

<span data-ttu-id="1508a-238">篡改嘗試通常表示較大的 cyberattacks。</span><span class="sxs-lookup"><span data-stu-id="1508a-238">Tampering attempts typically indicate bigger cyberattacks.</span></span> <span data-ttu-id="1508a-239">不良的演員會嘗試變更安全性設定，以保留並保持未被發現的方式。</span><span class="sxs-lookup"><span data-stu-id="1508a-239">Bad actors try to change security settings as a way to persist and stay undetected.</span></span> <span data-ttu-id="1508a-240">如果您是組織的安全性小組的一部分，您可以查看有關這些嘗試的資訊，然後採取適當的動作來緩解威脅。</span><span class="sxs-lookup"><span data-stu-id="1508a-240">If you're part of your organization's security team, you can view information about such attempts, and then take appropriate actions to mitigate threats.</span></span>

<span data-ttu-id="1508a-241">偵測到篡改嘗試時，會在 [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) () 中產生警示 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="1508a-241">When a tampering attempt is detected, an alert is raised in the [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

![Microsoft Defender 安全中心](images/tamperattemptalert.png)

<span data-ttu-id="1508a-243">在 Microsoft Defender for Endpoint 中使用 [端點偵測和回應](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 及 [高級搜尋](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) 功能，您的安全性作業小組可以調查並處理此類嘗試。</span><span class="sxs-lookup"><span data-stu-id="1508a-243">Using [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) and [advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) capabilities in Microsoft Defender for Endpoint, your security operations team can investigate and address such attempts.</span></span>

## <a name="review-your-security-recommendations"></a><span data-ttu-id="1508a-244">回顧安全性建議</span><span class="sxs-lookup"><span data-stu-id="1508a-244">Review your security recommendations</span></span>

<span data-ttu-id="1508a-245">防篡改防護會與 [威脅 & 漏洞管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 功能整合。</span><span class="sxs-lookup"><span data-stu-id="1508a-245">Tamper protection integrates with [Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) capabilities.</span></span> <span data-ttu-id="1508a-246">[安全性建議](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 包括確定已開啟防篡改保護。</span><span class="sxs-lookup"><span data-stu-id="1508a-246">[Security recommendations](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) include making sure tamper protection is turned on.</span></span> <span data-ttu-id="1508a-247">例如，您可以搜尋未 *篡改* 的，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="1508a-247">For example, you can search on *tamper*, as shown in the following image:</span></span>

![安全建議中的防篡改保護結果](/images/securityrecs-tamperprotect.jpg)

<span data-ttu-id="1508a-249">在結果中，您可以選取 [ **開啟防篡改防護** ] 以深入瞭解及開啟。</span><span class="sxs-lookup"><span data-stu-id="1508a-249">In the results, you can select **Turn on Tamper Protection** to learn more and turn it on.</span></span>

![開啟防篡改保護](images/tamperprotectsecurityrecos.png)

<span data-ttu-id="1508a-251">若要深入瞭解威脅 & 漏洞管理的相關資訊，請參閱 [Microsoft Defender Security Center 中的威脅 & 漏洞管理](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="1508a-251">To learn more about Threat & Vulnerability Management, see [Threat & Vulnerability Management in Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1508a-252">常見問題集</span><span class="sxs-lookup"><span data-stu-id="1508a-252">Frequently asked questions</span></span>

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a><span data-ttu-id="1508a-253">適用于哪些 Windows 作業系統版本設定防篡改保護？</span><span class="sxs-lookup"><span data-stu-id="1508a-253">To which Windows OS versions is configuring tamper protection is applicable?</span></span>

<span data-ttu-id="1508a-254">Windows 10 作業系統 [1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)、 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)或更新版本，以及 [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="1508a-254">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), or later together with [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

<span data-ttu-id="1508a-255">如果您使用的是 Configuration Manager，版本2006，使用租使用者附加，可將防篡改保護功能延伸至 Windows Server 2019。</span><span class="sxs-lookup"><span data-stu-id="1508a-255">If you are using Configuration Manager, version 2006, with tenant attach, tamper protection can be extended to Windows Server 2019.</span></span> <span data-ttu-id="1508a-256">請參閱「租使用者」 [：從系統管理中心建立及部署端點安全性防病毒原則 (預覽) ](/mem/configmgr/tenant-attach/deploy-antivirus-policy)。</span><span class="sxs-lookup"><span data-stu-id="1508a-256">See [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).</span></span>

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a><span data-ttu-id="1508a-257">防篡改保護是否會影響協力廠商防病毒註冊？</span><span class="sxs-lookup"><span data-stu-id="1508a-257">Will tamper protection have any impact on third-party antivirus registration?</span></span>

<span data-ttu-id="1508a-258">否。</span><span class="sxs-lookup"><span data-stu-id="1508a-258">No.</span></span> <span data-ttu-id="1508a-259">協力廠商的防病毒產品將繼續使用 Windows 安全性應用程式進行註冊。</span><span class="sxs-lookup"><span data-stu-id="1508a-259">Third-party antivirus offerings will continue to register with the Windows Security application.</span></span>

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a><span data-ttu-id="1508a-260">當裝置上的 Microsoft Defender 防毒程式不在使用中時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="1508a-260">What happens if Microsoft Defender Antivirus is not active on a device?</span></span>

<span data-ttu-id="1508a-261">架至 Microsoft Defender for Endpoint 的裝置將會在被動模式下執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="1508a-261">Devices that are onboarded to Microsoft Defender for Endpoint will have Microsoft Defender Antivirus running in passive mode.</span></span> <span data-ttu-id="1508a-262">防篡改保護將繼續保護服務及其功能。</span><span class="sxs-lookup"><span data-stu-id="1508a-262">Tamper protection will continue to protect the service and its features.</span></span> 

### <a name="how-can-i-turn-tamper-protection-onoff"></a><span data-ttu-id="1508a-263">如何開啟/關閉防篡改保護？</span><span class="sxs-lookup"><span data-stu-id="1508a-263">How can I turn tamper protection on/off?</span></span>

<span data-ttu-id="1508a-264">如果您是家庭使用者，請參閱 [管理個別裝置上的非篡改保護](#manage-tamper-protection-on-an-individual-device)。</span><span class="sxs-lookup"><span data-stu-id="1508a-264">If you are a home user, see [Manage tamper protection on an individual device](#manage-tamper-protection-on-an-individual-device).</span></span>

<span data-ttu-id="1508a-265">如果您是使用 [Microsoft Defender For Endpoint 的](/microsoft-365/security/defender-endpoint)組織，您應該可以在 Intune 中管理防篡改保護，類似管理其他 Endpoint protection 功能的方式。</span><span class="sxs-lookup"><span data-stu-id="1508a-265">If you are an organization using [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint), you should be able to manage tamper protection in Intune similar to how you manage other endpoint protection features.</span></span> <span data-ttu-id="1508a-266">請參閱本文的下列各節：</span><span class="sxs-lookup"><span data-stu-id="1508a-266">See the following sections of this article:</span></span> 

- [<span data-ttu-id="1508a-267">使用 Intune 管理防篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-267">Manage tamper protection using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune)
- [<span data-ttu-id="1508a-268">使用 Configuration Manager 管理防篡改保護，版本2006</span><span class="sxs-lookup"><span data-stu-id="1508a-268">Manage tamper protection using Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- <span data-ttu-id="1508a-269">使用目前在預覽中[的 Microsoft Defender Security Center (管理防篡改保護](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center)) </span><span class="sxs-lookup"><span data-stu-id="1508a-269">[Manage tamper protection using the Microsoft Defender Security Center](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) (currently in preview)</span></span>

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a><span data-ttu-id="1508a-270">如何在 Intune 中設定無法篡改的保護，會影響如何透過「我的群組原則」管理 Microsoft Defender 防病毒？</span><span class="sxs-lookup"><span data-stu-id="1508a-270">How does configuring tamper protection in Intune affect how I manage Microsoft Defender Antivirus through my group policy?</span></span>

<span data-ttu-id="1508a-271">您的一般群組原則不會套用到防篡改保護，當防篡改保護開啟時，將會忽略對 Microsoft Defender 防病毒設定所做的變更。</span><span class="sxs-lookup"><span data-stu-id="1508a-271">Your regular group policy doesn’t apply to tamper protection, and changes to Microsoft Defender Antivirus settings are ignored when tamper protection is on.</span></span> 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a><span data-ttu-id="1508a-272">針對 Microsoft Defender for Endpoint，在僅針對整個組織的 Intune 中，是否要設定防篡改保護？</span><span class="sxs-lookup"><span data-stu-id="1508a-272">For Microsoft Defender for Endpoint, is configuring tamper protection in Intune targeted to the entire organization only?</span></span>

<span data-ttu-id="1508a-273">在 Intune 或 Microsoft 端點管理員中設定防篡改保護，可成為整個組織及特定裝置和使用者群組的目標。</span><span class="sxs-lookup"><span data-stu-id="1508a-273">Configuring tamper protection in Intune or Microsoft Endpoint Manager can be targeted to your entire organization and to specific devices and user groups.</span></span>

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="1508a-274">我是否可以在 Microsoft 端點 Configuration Manager 中設定防篡改保護？</span><span class="sxs-lookup"><span data-stu-id="1508a-274">Can I configure Tamper Protection in Microsoft Endpoint Configuration Manager?</span></span>

<span data-ttu-id="1508a-275">如果您使用租使用者附加，您可以使用 Microsoft 端點 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="1508a-275">If you are using tenant attach, you can use Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="1508a-276">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="1508a-276">See the following resources:</span></span>
- [<span data-ttu-id="1508a-277">使用 Configuration Manager 管理組織的篡改保護，版本2006</span><span class="sxs-lookup"><span data-stu-id="1508a-277">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="1508a-278">技術社區博客：宣佈 Configuration Manager 租使用者附加用戶端的篡改保護</span><span class="sxs-lookup"><span data-stu-id="1508a-278">Tech Community blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a><span data-ttu-id="1508a-279">我有 Windows E3 註冊。</span><span class="sxs-lookup"><span data-stu-id="1508a-279">I have the Windows E3 enrollment.</span></span> <span data-ttu-id="1508a-280">我是否可以在 Intune 中使用設定防篡改保護？</span><span class="sxs-lookup"><span data-stu-id="1508a-280">Can I use configuring tamper protection in Intune?</span></span>

<span data-ttu-id="1508a-281">目前，在 Intune 中設定防篡改保護只適用于具有 [Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint)的客戶。</span><span class="sxs-lookup"><span data-stu-id="1508a-281">Currently, configuring tamper protection in Intune is only available for customers who have [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a><span data-ttu-id="1508a-282">如果在裝置上啟用防篡改保護功能時，嘗試變更 Intune、Microsoft Endpoint Configuration Manager 和 Windows Management Instrumentation 中的 Microsoft Defender for Endpoint 設定會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="1508a-282">What happens if I try to change Microsoft Defender for Endpoint settings in Intune, Microsoft Endpoint Configuration Manager, and Windows Management Instrumentation when Tamper Protection is enabled on a device?</span></span>

<span data-ttu-id="1508a-283">您將無法變更受到防篡改保護的功能;這類變更要求會被忽略。</span><span class="sxs-lookup"><span data-stu-id="1508a-283">You won’t be able to change the features that are protected by tamper protection; such change requests are ignored.</span></span>

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a><span data-ttu-id="1508a-284">我是企業客戶。</span><span class="sxs-lookup"><span data-stu-id="1508a-284">I’m an enterprise customer.</span></span> <span data-ttu-id="1508a-285">本機系統管理員是否可以變更其裝置上的篡改保護？</span><span class="sxs-lookup"><span data-stu-id="1508a-285">Can local admins change tamper protection on their devices?</span></span>

<span data-ttu-id="1508a-286">否。</span><span class="sxs-lookup"><span data-stu-id="1508a-286">No.</span></span> <span data-ttu-id="1508a-287">本機系統管理員無法變更或修改無法篡改的保護設定。</span><span class="sxs-lookup"><span data-stu-id="1508a-287">Local admins cannot change or modify tamper protection settings.</span></span>

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a><span data-ttu-id="1508a-288">如果我的裝置使用 Microsoft Defender for Endpoint 架，然後進入 boarded 狀態，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="1508a-288">What happens if my device is onboarded with Microsoft Defender for Endpoint and then goes into an off-boarded state?</span></span>

<span data-ttu-id="1508a-289">如果從 Microsoft Defender for Endpoint boarded 裝置，則會開啟防篡改防護，這是非管理裝置的預設狀態。</span><span class="sxs-lookup"><span data-stu-id="1508a-289">If a device is off-boarded from Microsoft Defender for Endpoint, tamper protection is turned on, which is the default state for unmanaged devices.</span></span> 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a><span data-ttu-id="1508a-290">在 Microsoft Defender Security Center 中是否會產生有關篡改防篡改狀態變更的警示？</span><span class="sxs-lookup"><span data-stu-id="1508a-290">Will there be an alert about tamper protection status changing in the Microsoft Defender Security Center?</span></span>

<span data-ttu-id="1508a-291">是。</span><span class="sxs-lookup"><span data-stu-id="1508a-291">Yes.</span></span> <span data-ttu-id="1508a-292">警示會顯示在 [ [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **警示**] 底下。</span><span class="sxs-lookup"><span data-stu-id="1508a-292">The alert is shown in [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) under **Alerts**.</span></span>

<span data-ttu-id="1508a-293">您的安全性運作小組也可以使用搜尋查詢，例如下列範例：</span><span class="sxs-lookup"><span data-stu-id="1508a-293">Your security operations team can also use hunting queries, such as the following example:</span></span>

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

<span data-ttu-id="1508a-294">[查看有關篡改嘗試的資訊](#view-information-about-tampering-attempts)。</span><span class="sxs-lookup"><span data-stu-id="1508a-294">[View information about tampering attempts](#view-information-about-tampering-attempts).</span></span>

## <a name="see-also"></a><span data-ttu-id="1508a-295">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1508a-295">See also</span></span>

[<span data-ttu-id="1508a-296">使用 Microsoft Intune 的 Endpoint Protection 來協助保護 Windows 電腦</span><span class="sxs-lookup"><span data-stu-id="1508a-296">Help secure Windows PCs with Endpoint Protection for Microsoft Intune</span></span>](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[<span data-ttu-id="1508a-297">深入瞭解 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1508a-297">Get an overview of Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint)

[<span data-ttu-id="1508a-298">更好搭配： Microsoft Defender 防病毒和 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1508a-298">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](why-use-microsoft-defender-antivirus.md)