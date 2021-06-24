---
title: 使用竄改防護來保護安全性設定
ms.reviewer: pahuijbr, hayhov, oogunrinde
manager: dansimp
description: 使用防篡改保護，防止惡意應用程式變更重要的安全性設定。
keywords: 惡意程式碼、defender、防毒程式和防篡改保護
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 06/23/2021
ms.openlocfilehash: 2e0724900de30629292cdcdc055d3ad3a1867b20
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105413"
---
# <a name="protect-security-settings-with-tamper-protection"></a><span data-ttu-id="266d0-104">使用竄改防護來保護安全性設定</span><span class="sxs-lookup"><span data-stu-id="266d0-104">Protect security settings with tamper protection</span></span>

<span data-ttu-id="266d0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="266d0-105">**Applies to:**</span></span>

- [<span data-ttu-id="266d0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="266d0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="266d0-107">在執行下列其中一個 Windows 版本的裝置上，會有防篡改保護：</span><span class="sxs-lookup"><span data-stu-id="266d0-107">Tamper protection is available for devices that are running one of the following versions of Windows:</span></span>

- <span data-ttu-id="266d0-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="266d0-108">Windows 10</span></span>
- <span data-ttu-id="266d0-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="266d0-109">Windows Server 2019</span></span>
- <span data-ttu-id="266d0-110">Windows Server 版本 1803 或更新版本</span><span class="sxs-lookup"><span data-stu-id="266d0-110">Windows Server, version 1803 or later</span></span>
- <span data-ttu-id="266d0-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="266d0-111">Windows Server 2016</span></span>

## <a name="overview"></a><span data-ttu-id="266d0-112">概觀</span><span class="sxs-lookup"><span data-stu-id="266d0-112">Overview</span></span>

<span data-ttu-id="266d0-113">在某些網路攻擊中，不良的演員會嘗試停用電腦上的安全性功能，例如防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="266d0-113">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="266d0-114">不良的演員，例如停用您的安全性功能，以更輕鬆地存取資料、安裝惡意程式碼，或利用您的資料、身分識別及裝置。</span><span class="sxs-lookup"><span data-stu-id="266d0-114">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span> <span data-ttu-id="266d0-115">防篡改保護可協助避免發生這類問題。</span><span class="sxs-lookup"><span data-stu-id="266d0-115">Tamper protection helps prevent these kinds of things from occurring.</span></span>

<span data-ttu-id="266d0-116">使用防篡改保護時，惡意應用程式無法採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="266d0-116">With tamper protection, malicious apps are prevented from taking actions such as:</span></span>

- <span data-ttu-id="266d0-117">停用病毒和威脅防護</span><span class="sxs-lookup"><span data-stu-id="266d0-117">Disabling virus and threat protection</span></span>
- <span data-ttu-id="266d0-118">停用即時保護</span><span class="sxs-lookup"><span data-stu-id="266d0-118">Disabling real-time protection</span></span>
- <span data-ttu-id="266d0-119">關閉行為監控</span><span class="sxs-lookup"><span data-stu-id="266d0-119">Turning off behavior monitoring</span></span>
- <span data-ttu-id="266d0-120">停用防病毒 (例如 IOfficeAntivirus (IOAV) ) </span><span class="sxs-lookup"><span data-stu-id="266d0-120">Disabling antivirus (such as IOfficeAntivirus (IOAV))</span></span>
- <span data-ttu-id="266d0-121">停用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="266d0-121">Disabling cloud-delivered protection</span></span>
- <span data-ttu-id="266d0-122">移除安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="266d0-122">Removing security intelligence updates</span></span>

### <a name="how-it-works"></a><span data-ttu-id="266d0-123">運作方式</span><span class="sxs-lookup"><span data-stu-id="266d0-123">How it works</span></span>

<span data-ttu-id="266d0-124">防篡改保護基本上會鎖定 Microsoft Defender 防毒軟體至其安全、預設值，並防止您的安全性設定透過應用程式和方法進行變更，例如：</span><span class="sxs-lookup"><span data-stu-id="266d0-124">Tamper protection essentially locks Microsoft Defender Antivirus to its secure, default values, and prevents your security settings from being changed through apps and methods such as:</span></span>

- <span data-ttu-id="266d0-125">在 Windows 裝置上設定登錄編輯程式中的設定</span><span class="sxs-lookup"><span data-stu-id="266d0-125">Configuring settings in Registry Editor on your Windows device</span></span>
- <span data-ttu-id="266d0-126">透過 PowerShell Cmdlet 變更設定</span><span class="sxs-lookup"><span data-stu-id="266d0-126">Changing settings through PowerShell cmdlets</span></span>
- <span data-ttu-id="266d0-127">透過群組原則編輯或移除安全性設定</span><span class="sxs-lookup"><span data-stu-id="266d0-127">Editing or removing security settings through Group Policy</span></span>

<span data-ttu-id="266d0-128">防篡改保護不會使您無法查看安全性設定。</span><span class="sxs-lookup"><span data-stu-id="266d0-128">Tamper protection doesn't prevent you from viewing your security settings.</span></span> <span data-ttu-id="266d0-129">而且，篡改保護不會影響協力廠商防病毒應用程式在 Windows 安全性應用程式中註冊的方式。</span><span class="sxs-lookup"><span data-stu-id="266d0-129">And, tamper protection doesn't affect how third-party antivirus apps register with the Windows Security app.</span></span> <span data-ttu-id="266d0-130">如果您的組織使用 Windows 10 企業版 E5，則個別使用者不能變更無法篡改的保護設定。在這種情況下，安全小組會管理防篡改保護。</span><span class="sxs-lookup"><span data-stu-id="266d0-130">If your organization is using Windows 10 Enterprise E5, individual users can't change the tamper protection setting; in those cases, tamper protection is managed by your security team.</span></span>

### <a name="what-do-you-want-to-do"></a><span data-ttu-id="266d0-131">您要執行的工作</span><span class="sxs-lookup"><span data-stu-id="266d0-131">What do you want to do?</span></span>

| <span data-ttu-id="266d0-132">若要執行此工作 .。。</span><span class="sxs-lookup"><span data-stu-id="266d0-132">To perform this task...</span></span> | <span data-ttu-id="266d0-133">請參閱本節 .。。</span><span class="sxs-lookup"><span data-stu-id="266d0-133">See this section...</span></span> |
|:---|:---|
| <span data-ttu-id="266d0-134">管理整個租使用者的防篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-134">Manage tamper protection across your tenant</span></span> <p><span data-ttu-id="266d0-135">使用 Microsoft Defender 資訊安全中心開啟或關閉防篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-135">Use the Microsoft Defender Security Center to turn tamper protection on or off</span></span> | [<span data-ttu-id="266d0-136">使用 Microsoft Defender 資訊安全中心管理組織的篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-136">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| <span data-ttu-id="266d0-137">微調組織中防篡改的保護設定</span><span class="sxs-lookup"><span data-stu-id="266d0-137">Fine-tune tamper protection settings in your organization</span></span> <p><span data-ttu-id="266d0-138">使用 Intune (Microsoft 端點管理員) 開啟或關閉不可篡改的保護。</span><span class="sxs-lookup"><span data-stu-id="266d0-138">Use Intune (Microsoft Endpoint Manager) to turn tamper protection on or off.</span></span> <span data-ttu-id="266d0-139">您可以使用此方法為部分或所有使用者設定無法篡改的保護。</span><span class="sxs-lookup"><span data-stu-id="266d0-139">You can configure tamper protection for some or all users with this method.</span></span> | [<span data-ttu-id="266d0-140">使用 Intune 管理組織的篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-140">Manage tamper protection for your organization using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune) |
| <span data-ttu-id="266d0-141">使用 Configuration Manager 對組織的 (或關閉) 開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-141">Turn tamper protection on (or off) for your organization with Configuration Manager</span></span> | [<span data-ttu-id="266d0-142">使用 Configuration Manager 的承租人附加程式管理組織的篡改保護，版本2006</span><span class="sxs-lookup"><span data-stu-id="266d0-142">Manage tamper protection for your organization using tenant attach with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| <span data-ttu-id="266d0-143">針對個別裝置 (或關閉) 開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-143">Turn tamper protection on (or off) for an individual device</span></span> | [<span data-ttu-id="266d0-144">管理個別裝置上的非篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-144">Manage tamper protection on an individual device</span></span>](#manage-tamper-protection-on-an-individual-device) |
| <span data-ttu-id="266d0-145">在裝置上查看有關篡改嘗試的詳細資料</span><span class="sxs-lookup"><span data-stu-id="266d0-145">View details about tampering attempts on devices</span></span> | [<span data-ttu-id="266d0-146">查看有關篡改嘗試的資訊</span><span class="sxs-lookup"><span data-stu-id="266d0-146">View information about tampering attempts</span></span>](#view-information-about-tampering-attempts) |
| <span data-ttu-id="266d0-147">回顧安全性建議</span><span class="sxs-lookup"><span data-stu-id="266d0-147">Review your security recommendations</span></span> | [<span data-ttu-id="266d0-148">檢查安全性建議</span><span class="sxs-lookup"><span data-stu-id="266d0-148">Review security recommendations</span></span>](#review-your-security-recommendations) |
| <span data-ttu-id="266d0-149">複查 (FAQs 的常見問題解答清單) </span><span class="sxs-lookup"><span data-stu-id="266d0-149">Review the list of frequently asked questions (FAQs)</span></span> | [<span data-ttu-id="266d0-150">流覽 FAQs</span><span class="sxs-lookup"><span data-stu-id="266d0-150">Browse the FAQs</span></span>](#view-information-about-tampering-attempts) |

<span data-ttu-id="266d0-151">根據您用來啟用防篡改保護的方法或管理工具，可能會對雲端提供的保護產生依賴性。</span><span class="sxs-lookup"><span data-stu-id="266d0-151">Depending on the method or management tool you use to enable tamper protection, there might be a dependency on cloud-delivered protection.</span></span> 

<span data-ttu-id="266d0-152">下表提供方法、工具和相依性的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="266d0-152">The following table provides details on the methods, tools, and dependencies.</span></span>

| <span data-ttu-id="266d0-153">啟用防篡改保護的方式</span><span class="sxs-lookup"><span data-stu-id="266d0-153">How tamper protection is enabled</span></span>  | <span data-ttu-id="266d0-154">對雲端傳送保護 (對應的依賴性) </span><span class="sxs-lookup"><span data-stu-id="266d0-154">Dependency on cloud-delivered protection (MAPS)</span></span>    |
|:----|:----|
| <span data-ttu-id="266d0-155">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="266d0-155">Microsoft Intune</span></span>  | <span data-ttu-id="266d0-156">否</span><span class="sxs-lookup"><span data-stu-id="266d0-156">No</span></span> |
| <span data-ttu-id="266d0-157">Microsoft Endpoint Configuration Manager + 租使用者附加</span><span class="sxs-lookup"><span data-stu-id="266d0-157">Microsoft Endpoint Configuration Manager + Tenant Attach</span></span>  |     <span data-ttu-id="266d0-158">否</span><span class="sxs-lookup"><span data-stu-id="266d0-158">No</span></span>  |
| <span data-ttu-id="266d0-159">Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) </span><span class="sxs-lookup"><span data-stu-id="266d0-159">Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>    |     <span data-ttu-id="266d0-160">是</span><span class="sxs-lookup"><span data-stu-id="266d0-160">Yes</span></span> |
| <span data-ttu-id="266d0-161">Microsoft 365 Defender 入口網站 ([https://security.microsoft.com](https://security.microsoft.com)) </span><span class="sxs-lookup"><span data-stu-id="266d0-161">Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com))</span></span>  |     <span data-ttu-id="266d0-162">是</span><span class="sxs-lookup"><span data-stu-id="266d0-162">Yes</span></span>  |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a><span data-ttu-id="266d0-163">使用 Microsoft Defender 資訊安全中心管理組織的篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-163">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>

<span data-ttu-id="266d0-164">您可以使用 Microsoft Defender 資訊安全中心 () 為您的租使用者開啟或關閉不可篡改的保護 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="266d0-164">Tamper protection can be turned on or off for your tenant using the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="266d0-165">以下是一些需要謹記的要點：</span><span class="sxs-lookup"><span data-stu-id="266d0-165">Here are a few points to keep in mind:</span></span>

- <span data-ttu-id="266d0-166">目前，在 Microsoft Defender 資訊安全中心中管理防篡改保護的選項預設是針對新的部署。</span><span class="sxs-lookup"><span data-stu-id="266d0-166">Currently, the option to manage tamper protection in the Microsoft Defender Security Center is on by default for new deployments.</span></span> <span data-ttu-id="266d0-167">針對現有的部署，在自願加入時可使用防篡改保護，其方案可讓您在近期使用預設方法。</span><span class="sxs-lookup"><span data-stu-id="266d0-167">For existing deployments, tamper protection is available on an opt-in basis, with plans to make opting in the default method in the near future.</span></span> <span data-ttu-id="266d0-168"> (若要加入宣告，請在 Microsoft Defender 資訊安全中心中，選擇 [**設定**  >  **高級功能** 未  >  **篡改保護**]。 ) </span><span class="sxs-lookup"><span data-stu-id="266d0-168">(To opt in, in the Microsoft Defender Security Center, choose **Settings** > **Advanced features** > **Tamper protection**.)</span></span> 

- <span data-ttu-id="266d0-169">當您使用 Microsoft Defender 資訊安全中心管理防篡改保護時，您不需要使用 Intune 或租使用者附加方法。</span><span class="sxs-lookup"><span data-stu-id="266d0-169">When you use the Microsoft Defender Security Center to manage tamper protection, you do not have to use either Intune or the tenant attach method.</span></span>

- <span data-ttu-id="266d0-170">當您在 Microsoft Defender 資訊安全中心中管理防篡改保護時，此設定會套用租使用者寬度，影響所有執行 Windows 10、Windows Server 2016 或 Windows Server 2019 的裝置。</span><span class="sxs-lookup"><span data-stu-id="266d0-170">When you manage tamper protection in the Microsoft Defender Security Center, the setting is applied tenant wide, affecting all of your devices that are running Windows 10, Windows Server 2016, or Windows Server 2019.</span></span> <span data-ttu-id="266d0-171">若要微調防篡改保護 (例如對某些裝置進行未篡改的保護，但對某些裝置關閉) 了防篡改保護，請使用 [Intune](#manage-tamper-protection-for-your-organization-using-intune) 或 [Configuration Manager with 承租人 attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)。</span><span class="sxs-lookup"><span data-stu-id="266d0-171">To fine-tune tamper protection (such as having tamper protection on for some devices but off for others), use either [Intune](#manage-tamper-protection-for-your-organization-using-intune) or [Configuration Manager with tenant attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).</span></span>

- <span data-ttu-id="266d0-172">如果您有混合式環境，則在 Intune 中設定的防篡改防護設定會優先于 Microsoft Defender 資訊安全中心中所設定的設定。</span><span class="sxs-lookup"><span data-stu-id="266d0-172">If you have a hybrid environment, tamper protection settings configured in Intune take precedence over settings configured in the Microsoft Defender Security Center.</span></span> 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a><span data-ttu-id="266d0-173">在 Microsoft Defender 資訊安全中心中管理防篡改保護的需求</span><span class="sxs-lookup"><span data-stu-id="266d0-173">Requirements for managing tamper protection in the Microsoft Defender Security Center</span></span>

- <span data-ttu-id="266d0-174">您必須具有適當的 [許可權](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全域管理員、安全性管理員或安全性作業。</span><span class="sxs-lookup"><span data-stu-id="266d0-174">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="266d0-175">您的 Windows 裝置必須執行下列其中一個 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="266d0-175">Your Windows devices must be running one of the following versions of Windows:</span></span>

   - <span data-ttu-id="266d0-176">Windows 10</span><span class="sxs-lookup"><span data-stu-id="266d0-176">Windows 10</span></span>
   - [<span data-ttu-id="266d0-177">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="266d0-177">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
   - <span data-ttu-id="266d0-178">WindowsServer，版本[1803](/windows/release-health/status-windows-10-1803)或更新版本</span><span class="sxs-lookup"><span data-stu-id="266d0-178">Windows Server, version [1803](/windows/release-health/status-windows-10-1803) or later</span></span>
   - [<span data-ttu-id="266d0-179">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="266d0-179">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016)
   - <span data-ttu-id="266d0-180">如需有關版本的詳細資訊，請參閱[Windows 10 版本資訊](/windows/release-health/release-information)。</span><span class="sxs-lookup"><span data-stu-id="266d0-180">For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).</span></span>

- <span data-ttu-id="266d0-181">您的裝置必須 [架至 Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="266d0-181">Your devices must be [onboarded to Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding).</span></span>

- <span data-ttu-id="266d0-182">您的裝置必須使用反惡意程式碼平臺版本 4.18.2010.7 (或以上版本) 和反惡意程式碼引擎版本 1.1.17600.5 (或以上) 。</span><span class="sxs-lookup"><span data-stu-id="266d0-182">Your devices must be using anti-malware platform version 4.18.2010.7 (or above) and anti-malware engine version 1.1.17600.5 (or above).</span></span> <span data-ttu-id="266d0-183"> ([管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="266d0-183">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

- <span data-ttu-id="266d0-184">必須開啟[雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="266d0-184">[Cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be turned on.</span></span>

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a><span data-ttu-id="266d0-185">開啟 Microsoft Defender 資訊安全中心中 (或關閉) 防篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-185">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> 

![在 Microsoft Defender 資訊安全中心中開啟防篡改保護](images/mde-turn-tamperprotect-on.png)

1. <span data-ttu-id="266d0-187">移至 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="266d0-187">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="266d0-188">選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="266d0-188">Choose **Settings**.</span></span>

3. <span data-ttu-id="266d0-189">移至 **[一般**  >  **高級功能**]，然後開啟 [防篡改保護]。</span><span class="sxs-lookup"><span data-stu-id="266d0-189">Go to **General** > **Advanced features**, and then turn tamper protection on.</span></span>

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a><span data-ttu-id="266d0-190">使用 Intune 管理組織的篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-190">Manage tamper protection for your organization using Intune</span></span>

<span data-ttu-id="266d0-191">如果您是組織的安全小組的一部分，且您的訂閱包含[Intune](/intune/fundamentals/what-is-intune)，您可以在 Microsoft 端點管理員系統管理中心 () 中，開啟組織的 (或關閉) 防篡改保護 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="266d0-191">If you are part of your organization's security team, and your subscription includes [Intune](/intune/fundamentals/what-is-intune), you can turn tamper protection on (or off) for your organization in the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)).</span></span> <span data-ttu-id="266d0-192">當您想要微調防篡改防護設定時，請使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="266d0-192">Use Intune when you want to fine-tune tamper protection settings.</span></span> <span data-ttu-id="266d0-193">例如，如果您想要在某些裝置上啟用防篡改保護，但不是全部，請使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="266d0-193">For example, if you want to enable tamper protection on some devices, but not all, use Intune.</span></span>

### <a name="requirements-for-managing-tamper-protection-in-intune"></a><span data-ttu-id="266d0-194">在 Intune 中管理防篡改保護的需求</span><span class="sxs-lookup"><span data-stu-id="266d0-194">Requirements for managing tamper protection in Intune</span></span>

- <span data-ttu-id="266d0-195">您必須具有適當的 [許可權](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全域管理員、安全性管理員或安全性作業。</span><span class="sxs-lookup"><span data-stu-id="266d0-195">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="266d0-196">您的組織使用 [Intune 管理裝置](/intune/fundamentals/what-is-device-management)。</span><span class="sxs-lookup"><span data-stu-id="266d0-196">Your organization uses [Intune to manage devices](/intune/fundamentals/what-is-device-management).</span></span> <span data-ttu-id="266d0-197">需要 ([Intune 授權](/intune/fundamentals/licenses);Intune 包含在 Microsoft 365 E5。 ) </span><span class="sxs-lookup"><span data-stu-id="266d0-197">([Intune licenses](/intune/fundamentals/licenses) are required; Intune is included in Microsoft 365 E5.)</span></span>

- <span data-ttu-id="266d0-198">您的 Windows 裝置必須執行 Windows 10 作業系統[1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)、 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)或更新版本。</span><span class="sxs-lookup"><span data-stu-id="266d0-198">Your Windows devices must be running Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) or later.</span></span> <span data-ttu-id="266d0-199"> (如需有關版本的詳細資訊，請參閱[Windows 10 版本資訊](/windows/release-health/release-information)。 ) </span><span class="sxs-lookup"><span data-stu-id="266d0-199">(For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).)</span></span>

- <span data-ttu-id="266d0-200">您必須使用 Windows 安全性搭配[安全性情報](https://www.microsoft.com/wdsi/definitions)更新為版本 1.287.60.0 (或以上) 。</span><span class="sxs-lookup"><span data-stu-id="266d0-200">You must be using Windows security with [security intelligence](https://www.microsoft.com/wdsi/definitions) updated to version 1.287.60.0 (or above).</span></span>

- <span data-ttu-id="266d0-201">您的裝置必須使用反惡意程式碼平臺版本 4.18.1906.3 (或以上版本) 和反惡意程式碼引擎版本 1.1.15500 (或以上版本) 。</span><span class="sxs-lookup"><span data-stu-id="266d0-201">Your devices must be using anti-malware platform version 4.18.1906.3 (or above) and anti-malware engine version 1.1.15500.X (or above).</span></span> <span data-ttu-id="266d0-202"> ([管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="266d0-202">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

### <a name="turn-tamper-protection-on-or-off-in-intune"></a><span data-ttu-id="266d0-203">在 Intune 中 (或關閉) 開啟防篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-203">Turn tamper protection on (or off) in Intune</span></span>

![使用 Intune 開啟防篡改保護](images/turnontamperprotect-MEM.png)

1. <span data-ttu-id="266d0-205">移至[Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)，並使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="266d0-205">Go to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="266d0-206">選取 [**裝置** 設定  >  **設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="266d0-206">Select **Devices** > **Configuration Profiles**.</span></span>

3. <span data-ttu-id="266d0-207">建立設定檔，其中包含下列設定：</span><span class="sxs-lookup"><span data-stu-id="266d0-207">Create a profile that includes the following settings:</span></span>

    - <span data-ttu-id="266d0-208">**Platform： Windows 10 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="266d0-208">**Platform: Windows 10 and later**</span></span>
    - <span data-ttu-id="266d0-209">**配置檔案類型： Endpoint protection**</span><span class="sxs-lookup"><span data-stu-id="266d0-209">**Profile type: Endpoint protection**</span></span>
    - <span data-ttu-id="266d0-210">**類別： Microsoft Defender 資訊安全中心**</span><span class="sxs-lookup"><span data-stu-id="266d0-210">**Category: Microsoft Defender Security Center**</span></span>
    - <span data-ttu-id="266d0-211">**防篡改保護：已啟用**</span><span class="sxs-lookup"><span data-stu-id="266d0-211">**Tamper Protection: Enabled**</span></span>

4. <span data-ttu-id="266d0-212">將設定檔指派給一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="266d0-212">Assign the profile to one or more groups.</span></span>

### <a name="are-you-using-windows-server-2016-or-windows-version-1709-1803-or-1809"></a><span data-ttu-id="266d0-213">您使用 Windows Server 2016，還是 Windows 版本1709、1803或1809？</span><span class="sxs-lookup"><span data-stu-id="266d0-213">Are you using Windows Server 2016, or Windows version 1709, 1803, or 1809?</span></span>

<span data-ttu-id="266d0-214">如果您使用 Windows Server 2016，請 Windows 10 版本1709、1803或 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)，您將看不到 Windows 安全性應用程式中的 **防篡改保護**。</span><span class="sxs-lookup"><span data-stu-id="266d0-214">If you are using Windows Server 2016, Windows 10 version 1709, 1803, or [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), you won't see **Tamper Protection** in the Windows Security app.</span></span> <span data-ttu-id="266d0-215">相反地，您可以使用 PowerShell 來判斷是否已啟用防篡改保護。</span><span class="sxs-lookup"><span data-stu-id="266d0-215">Instead, you can use PowerShell to determine whether tamper protection is enabled.</span></span> 
   
<span data-ttu-id="266d0-216">在 Windows Server 2016 上，設定應用程式在啟用防篡改保護時，不會準確反映即時保護的狀態。</span><span class="sxs-lookup"><span data-stu-id="266d0-216">On Windows Server 2016, the Settings app will not accurately reflect the status of real-time protection when tamper protection is enabled.</span></span>
   
#### <a name="use-powershell-to-determine-whether-tamper-protection-andor-real-time-protection-are-turned-on"></a><span data-ttu-id="266d0-217">使用 PowerShell 來判斷是否已開啟防篡改保護和/或即時保護</span><span class="sxs-lookup"><span data-stu-id="266d0-217">Use PowerShell to determine whether tamper protection and/or real-time protection are turned on</span></span>

1. <span data-ttu-id="266d0-218">開啟 Windows PowerShell 應用程式。</span><span class="sxs-lookup"><span data-stu-id="266d0-218">Open the Windows PowerShell app.</span></span>

2. <span data-ttu-id="266d0-219">使用 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="266d0-219">Use the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet.</span></span>

3. <span data-ttu-id="266d0-220">在結果清單中，尋找 `IsTamperProtected` 或 `RealTimeProtectionEnabled` 。</span><span class="sxs-lookup"><span data-stu-id="266d0-220">In the list of results, look for `IsTamperProtected` or `RealTimeProtectionEnabled`.</span></span> <span data-ttu-id="266d0-221"> (*true* 值表示已啟用 [未篡改保護]。 ) </span><span class="sxs-lookup"><span data-stu-id="266d0-221">(A value of *true* means tamper protection is enabled.)</span></span>

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a><span data-ttu-id="266d0-222">使用 Configuration Manager 管理組織的篡改保護，版本2006</span><span class="sxs-lookup"><span data-stu-id="266d0-222">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>

<span data-ttu-id="266d0-223">如果您使用 [的是版本2006的 Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)，您可以使用稱為 *租使用者附加* 的方法，在 Windows 10、Windows Server 2016 和 Windows Server 2019 上管理防篡改保護設定。</span><span class="sxs-lookup"><span data-stu-id="266d0-223">If you're using [version 2006 of Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), you can manage tamper protection settings on Windows 10, Windows Server 2016, and Windows Server 2019 by using a method called *tenant attach*.</span></span> <span data-ttu-id="266d0-224">租使用者附加功能可讓您將內部部署的 Configuration Manager 裝置同步處理至 Microsoft 端點管理員系統管理中心，然後將端點安全性設定原則傳送至內部部署集合 & 裝置。</span><span class="sxs-lookup"><span data-stu-id="266d0-224">Tenant attach enables you to sync your on-premises-only Configuration Manager devices into the Microsoft Endpoint Manager admin center, and then deliver endpoint security configuration policies to on-premises collections & devices.</span></span>

:::image type="content" source="images/win-security- exp-policy-endpt-security.png" alt-text="端點管理員中的 Windows 安全性體驗":::

> [!NOTE]
> <span data-ttu-id="266d0-226">您可以使用此程式將對執行 Windows 10 和 Windows 伺服器2019的裝置擴充防篡改保護。</span><span class="sxs-lookup"><span data-stu-id="266d0-226">The procedure can be used to extend tamper protection to devices running Windows 10 and Windows Server 2019.</span></span> <span data-ttu-id="266d0-227">請務必複查此程式所述資源中的必要條件和其他資訊。</span><span class="sxs-lookup"><span data-stu-id="266d0-227">Make sure to review the prerequisites and other information in the resources mentioned in this procedure.</span></span>

1. <span data-ttu-id="266d0-228">設定租使用者附加。</span><span class="sxs-lookup"><span data-stu-id="266d0-228">Set up tenant attach.</span></span> <span data-ttu-id="266d0-229">若要深入瞭解，請參閱[Microsoft 端點管理員租使用者附加裝置：裝置同步處理和裝置動作](/mem/configmgr/tenant-attach/device-sync-actions)。</span><span class="sxs-lookup"><span data-stu-id="266d0-229">To learn more, see [Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).</span></span>

2. <span data-ttu-id="266d0-230">在 [Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，移至 **端點安全性**  >  **防病毒**，然後選擇 [ **+ 建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="266d0-230">In the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Endpoint security** > **Antivirus**, and then choose **+ Create Policy**.</span></span> 

   - <span data-ttu-id="266d0-231">在 [**平臺**] 清單中，選取 [ **Windows 10 和 Windows Server (ConfigMgr])**。</span><span class="sxs-lookup"><span data-stu-id="266d0-231">In the **Platform** list, select **Windows 10 and Windows Server (ConfigMgr)**.</span></span>  
   - <span data-ttu-id="266d0-232">在 [**設定檔**] 清單中，選取 [ **Windows 安全性經驗 (預覽)**]。</span><span class="sxs-lookup"><span data-stu-id="266d0-232">In the **Profile** list, select **Windows Security experience (preview)**.</span></span> <br/>

3. <span data-ttu-id="266d0-233">將原則部署至您的裝置集合。</span><span class="sxs-lookup"><span data-stu-id="266d0-233">Deploy the policy to your device collection.</span></span>

### <a name="need-help-with-this-method"></a><span data-ttu-id="266d0-234">需要此方法的協助嗎？</span><span class="sxs-lookup"><span data-stu-id="266d0-234">Need help with this method?</span></span> 

<span data-ttu-id="266d0-235">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="266d0-235">See the following resources:</span></span>

- [<span data-ttu-id="266d0-236">Microsoft Intune 中 Windows 安全性體驗設定檔的設定</span><span class="sxs-lookup"><span data-stu-id="266d0-236">Settings for the Windows Security experience profile in Microsoft Intune</span></span>](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [<span data-ttu-id="266d0-237">技術 Community 博客：宣佈 Configuration Manager 租使用者附加用戶端的篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-237">Tech Community Blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a><span data-ttu-id="266d0-238">管理個別裝置上的非篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-238">Manage tamper protection on an individual device</span></span>

> [!NOTE]
> <span data-ttu-id="266d0-239">防篡改保護封鎖會嘗試透過登錄修改 Microsoft Defender 防毒軟體設定。</span><span class="sxs-lookup"><span data-stu-id="266d0-239">Tamper protection blocks attempts to modify Microsoft Defender Antivirus settings through the registry.</span></span>
>
> <span data-ttu-id="266d0-240">為了協助確保防篡改保護不會干擾協力廠商的安全性產品或可修改這些設定的企業安裝腳本，請移至 **Windows 安全性**，並將 **安全性情報** 更新為1.287.60.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="266d0-240">To help ensure that tamper protection doesn’t interfere with third-party security products or enterprise installation scripts that modify these settings, go to **Windows Security** and update **Security intelligence** to version 1.287.60.0 or later.</span></span> <span data-ttu-id="266d0-241"> (參閱 [安全性智慧更新](https://www.microsoft.com/wdsi/definitions)。 ) </span><span class="sxs-lookup"><span data-stu-id="266d0-241">(See [Security intelligence updates](https://www.microsoft.com/wdsi/definitions).)</span></span>
>
> <span data-ttu-id="266d0-242">當您完成此更新後，防篡改保護會繼續保護您的登錄設定，而記錄會嘗試修改這些設定，而不會傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="266d0-242">Once you’ve made this update, tamper protection continues to protect your registry settings, and logs attempts to modify them without returning errors.</span></span>

<span data-ttu-id="266d0-243">如果您是家庭使用者，或不受安全性小組所管理的設定的制約，您可以使用 Windows 安全性應用程式來管理無法篡改的保護。</span><span class="sxs-lookup"><span data-stu-id="266d0-243">If you are a home user, or you are not subject to settings managed by a security team, you can use the Windows Security app to manage tamper protection.</span></span> <span data-ttu-id="266d0-244">您必須具備裝置的適當系統管理員許可權，才能執行變更安全性設定，例如防篡改的保護。</span><span class="sxs-lookup"><span data-stu-id="266d0-244">You must have appropriate admin permissions on your device to do change security settings, such as tamper protection.</span></span>

<span data-ttu-id="266d0-245">以下是您在 Windows 安全性應用程式中看到的內容：</span><span class="sxs-lookup"><span data-stu-id="266d0-245">Here's what you see in the Windows Security app:</span></span>

![在 Windows 10 家用版中開啟防篡改保護](images/tamperprotectionturnedon.png)

1. <span data-ttu-id="266d0-247">選取 [ **開始**]，然後開始輸入 *安全性*。</span><span class="sxs-lookup"><span data-stu-id="266d0-247">Select **Start**, and start typing *Security*.</span></span> <span data-ttu-id="266d0-248">在搜尋結果中，選取 [ **Windows 安全性**]。</span><span class="sxs-lookup"><span data-stu-id="266d0-248">In the search results, select **Windows Security**.</span></span>

2. <span data-ttu-id="266d0-249">選取 [**病毒 & 威脅防護**]  >  **病毒 & 威脅防護設定**。</span><span class="sxs-lookup"><span data-stu-id="266d0-249">Select **Virus & threat protection** > **Virus & threat protection settings**.</span></span>

3. <span data-ttu-id="266d0-250">設定 **防篡改保護** 為 **開啟** 或 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="266d0-250">Set **Tamper Protection** to **On** or **Off**.</span></span>

## <a name="view-information-about-tampering-attempts"></a><span data-ttu-id="266d0-251">查看有關篡改嘗試的資訊</span><span class="sxs-lookup"><span data-stu-id="266d0-251">View information about tampering attempts</span></span>

<span data-ttu-id="266d0-252">篡改嘗試通常表示較大的 cyberattacks。</span><span class="sxs-lookup"><span data-stu-id="266d0-252">Tampering attempts typically indicate bigger cyberattacks.</span></span> <span data-ttu-id="266d0-253">不良的演員會嘗試變更安全性設定，以保留並保持未被發現的方式。</span><span class="sxs-lookup"><span data-stu-id="266d0-253">Bad actors try to change security settings as a way to persist and stay undetected.</span></span> <span data-ttu-id="266d0-254">如果您是組織的安全性小組的一部分，您可以查看有關這些嘗試的資訊，然後採取適當的動作來緩解威脅。</span><span class="sxs-lookup"><span data-stu-id="266d0-254">If you're part of your organization's security team, you can view information about such attempts, and then take appropriate actions to mitigate threats.</span></span>

<span data-ttu-id="266d0-255">偵測到篡改嘗試時， [Microsoft Defender 資訊安全中心](/microsoft-365/security/defender-endpoint/portal-overview) () 中會產生警示 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="266d0-255">When a tampering attempt is detected, an alert is raised in the [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

![Microsoft Defender 資訊安全中心](images/tamperattemptalert.png)

<span data-ttu-id="266d0-257">在 Microsoft Defender for Endpoint 中使用 [端點偵測和回應](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 及 [高級搜尋](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) 功能，您的安全性作業小組可以調查並處理此類嘗試。</span><span class="sxs-lookup"><span data-stu-id="266d0-257">Using [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) and [advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) capabilities in Microsoft Defender for Endpoint, your security operations team can investigate and address such attempts.</span></span>

## <a name="review-your-security-recommendations"></a><span data-ttu-id="266d0-258">回顧安全性建議</span><span class="sxs-lookup"><span data-stu-id="266d0-258">Review your security recommendations</span></span>

<span data-ttu-id="266d0-259">防篡改防護會與 [威脅 & 漏洞管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 功能整合。</span><span class="sxs-lookup"><span data-stu-id="266d0-259">Tamper protection integrates with [Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) capabilities.</span></span> <span data-ttu-id="266d0-260">[安全性建議](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 包括確定已開啟防篡改保護。</span><span class="sxs-lookup"><span data-stu-id="266d0-260">[Security recommendations](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) include making sure tamper protection is turned on.</span></span> <span data-ttu-id="266d0-261">例如，您可以搜尋 *篡改*。</span><span class="sxs-lookup"><span data-stu-id="266d0-261">For example, you can search on *tamper*.</span></span> <span data-ttu-id="266d0-262">在結果中，您可以選取 [ **開啟防篡改防護** ] 以深入瞭解及開啟。</span><span class="sxs-lookup"><span data-stu-id="266d0-262">In the results, you can select **Turn on Tamper Protection** to learn more and turn it on.</span></span>

![開啟防篡改保護](images/tamperprotectsecurityrecos.png)

<span data-ttu-id="266d0-264">若要深入瞭解威脅 & 漏洞管理的詳細資訊，請參閱[Microsoft Defender 資訊安全中心中的威脅 & 漏洞管理](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="266d0-264">To learn more about Threat & Vulnerability Management, see [Threat & Vulnerability Management in Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="266d0-265">常見問題集</span><span class="sxs-lookup"><span data-stu-id="266d0-265">Frequently asked questions</span></span>

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a><span data-ttu-id="266d0-266">若要 Windows 作業系統版本設定防篡改保護，是否適用？</span><span class="sxs-lookup"><span data-stu-id="266d0-266">To which Windows OS versions is configuring tamper protection is applicable?</span></span>

<span data-ttu-id="266d0-267">Windows 10作業系統[1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)、 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)或更新版本，與[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)一起使用。</span><span class="sxs-lookup"><span data-stu-id="266d0-267">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), or later together with [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

<span data-ttu-id="266d0-268">如果您使用的是 Configuration Manager，版本2006，使用租使用者附加，可將防篡改保護功能延伸至 Windows Server 2019。</span><span class="sxs-lookup"><span data-stu-id="266d0-268">If you are using Configuration Manager, version 2006, with tenant attach, tamper protection can be extended to Windows Server 2019.</span></span> <span data-ttu-id="266d0-269">請參閱「租使用者」 [：從系統管理中心建立及部署端點安全性防病毒原則 (預覽) ](/mem/configmgr/tenant-attach/deploy-antivirus-policy)。</span><span class="sxs-lookup"><span data-stu-id="266d0-269">See [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).</span></span>

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a><span data-ttu-id="266d0-270">防篡改保護是否會影響協力廠商防病毒註冊？</span><span class="sxs-lookup"><span data-stu-id="266d0-270">Will tamper protection have any impact on third-party antivirus registration?</span></span>

<span data-ttu-id="266d0-271">否。</span><span class="sxs-lookup"><span data-stu-id="266d0-271">No.</span></span> <span data-ttu-id="266d0-272">協力廠商的防病毒產品將繼續向 Windows 安全性的應用程式註冊。</span><span class="sxs-lookup"><span data-stu-id="266d0-272">Third-party antivirus offerings will continue to register with the Windows Security application.</span></span>

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a><span data-ttu-id="266d0-273">如果裝置上的 Microsoft Defender 防毒軟體不在使用中，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="266d0-273">What happens if Microsoft Defender Antivirus is not active on a device?</span></span>

<span data-ttu-id="266d0-274">架至 Microsoft Defender for Endpoint 的裝置會在被動模式中執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="266d0-274">Devices that are onboarded to Microsoft Defender for Endpoint will have Microsoft Defender Antivirus running in passive mode.</span></span> <span data-ttu-id="266d0-275">防篡改保護將繼續保護服務及其功能。</span><span class="sxs-lookup"><span data-stu-id="266d0-275">Tamper protection will continue to protect the service and its features.</span></span> 

### <a name="how-can-i-turn-tamper-protection-onoff"></a><span data-ttu-id="266d0-276">如何開啟/關閉防篡改保護？</span><span class="sxs-lookup"><span data-stu-id="266d0-276">How can I turn tamper protection on/off?</span></span>

<span data-ttu-id="266d0-277">如果您是家庭使用者，請參閱 [管理個別裝置上的非篡改保護](#manage-tamper-protection-on-an-individual-device)。</span><span class="sxs-lookup"><span data-stu-id="266d0-277">If you are a home user, see [Manage tamper protection on an individual device](#manage-tamper-protection-on-an-individual-device).</span></span>

<span data-ttu-id="266d0-278">如果您是使用 [Microsoft Defender For Endpoint 的](/microsoft-365/security/defender-endpoint)組織，您應該可以在 Intune 中管理防篡改保護，類似管理其他 Endpoint protection 功能的方式。</span><span class="sxs-lookup"><span data-stu-id="266d0-278">If you are an organization using [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint), you should be able to manage tamper protection in Intune similar to how you manage other endpoint protection features.</span></span> <span data-ttu-id="266d0-279">請參閱本文的下列各節：</span><span class="sxs-lookup"><span data-stu-id="266d0-279">See the following sections of this article:</span></span> 

- [<span data-ttu-id="266d0-280">使用 Intune 管理防篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-280">Manage tamper protection using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune)
- [<span data-ttu-id="266d0-281">使用 Configuration Manager 管理防篡改保護，版本2006</span><span class="sxs-lookup"><span data-stu-id="266d0-281">Manage tamper protection using Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="266d0-282">使用 Microsoft Defender 資訊安全中心管理無法篡改的保護</span><span class="sxs-lookup"><span data-stu-id="266d0-282">Manage tamper protection using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a><span data-ttu-id="266d0-283">如何在 Intune 中設定防篡改保護，會影響透過「我的群組原則」管理 Microsoft Defender 防毒軟體的方式？</span><span class="sxs-lookup"><span data-stu-id="266d0-283">How does configuring tamper protection in Intune affect how I manage Microsoft Defender Antivirus through my group policy?</span></span>

<span data-ttu-id="266d0-284">您的一般群組原則不會套用到防篡改保護，而且當防篡改保護開啟時，會忽略 Microsoft Defender 防毒軟體設定的變更。</span><span class="sxs-lookup"><span data-stu-id="266d0-284">Your regular group policy doesn’t apply to tamper protection, and changes to Microsoft Defender Antivirus settings are ignored when tamper protection is on.</span></span> 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a><span data-ttu-id="266d0-285">針對 Microsoft Defender for Endpoint，在僅針對整個組織的 Intune 中，是否要設定防篡改保護？</span><span class="sxs-lookup"><span data-stu-id="266d0-285">For Microsoft Defender for Endpoint, is configuring tamper protection in Intune targeted to the entire organization only?</span></span>

<span data-ttu-id="266d0-286">在 Intune 或 Microsoft 端點管理員中設定無法篡改的保護，可成為整個組織及特定裝置和使用者群組的目標。</span><span class="sxs-lookup"><span data-stu-id="266d0-286">Configuring tamper protection in Intune or Microsoft Endpoint Manager can be targeted to your entire organization and to specific devices and user groups.</span></span>

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="266d0-287">我是否可以在 Microsoft Endpoint Configuration Manager 中設定無法篡改的保護？</span><span class="sxs-lookup"><span data-stu-id="266d0-287">Can I configure Tamper Protection in Microsoft Endpoint Configuration Manager?</span></span>

<span data-ttu-id="266d0-288">如果您使用租使用者附加，您可以使用 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="266d0-288">If you are using tenant attach, you can use Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="266d0-289">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="266d0-289">See the following resources:</span></span>
- [<span data-ttu-id="266d0-290">使用 Configuration Manager 管理組織的篡改保護，版本2006</span><span class="sxs-lookup"><span data-stu-id="266d0-290">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="266d0-291">技術 Community 博客：宣佈 Configuration Manager 租使用者附加用戶端的篡改保護</span><span class="sxs-lookup"><span data-stu-id="266d0-291">Tech Community blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a><span data-ttu-id="266d0-292">我有 Windows E3 註冊。</span><span class="sxs-lookup"><span data-stu-id="266d0-292">I have the Windows E3 enrollment.</span></span> <span data-ttu-id="266d0-293">我是否可以在 Intune 中使用設定防篡改保護？</span><span class="sxs-lookup"><span data-stu-id="266d0-293">Can I use configuring tamper protection in Intune?</span></span>

<span data-ttu-id="266d0-294">目前，在 Intune 中設定防篡改保護只適用于具有 [Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint)的客戶。</span><span class="sxs-lookup"><span data-stu-id="266d0-294">Currently, configuring tamper protection in Intune is only available for customers who have [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a><span data-ttu-id="266d0-295">如果在裝置上啟用防篡改保護功能時，嘗試變更 Intune 中的 Microsoft Defender for Endpoint 設定，Microsoft Endpoint Configuration Manager 和 Windows 管理工具時，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="266d0-295">What happens if I try to change Microsoft Defender for Endpoint settings in Intune, Microsoft Endpoint Configuration Manager, and Windows Management Instrumentation when Tamper Protection is enabled on a device?</span></span>

<span data-ttu-id="266d0-296">您將無法變更受到防篡改保護的功能;這類變更要求會被忽略。</span><span class="sxs-lookup"><span data-stu-id="266d0-296">You won’t be able to change the features that are protected by tamper protection; such change requests are ignored.</span></span>

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a><span data-ttu-id="266d0-297">我是企業客戶。</span><span class="sxs-lookup"><span data-stu-id="266d0-297">I’m an enterprise customer.</span></span> <span data-ttu-id="266d0-298">本機系統管理員是否可以變更其裝置上的篡改保護？</span><span class="sxs-lookup"><span data-stu-id="266d0-298">Can local admins change tamper protection on their devices?</span></span>

<span data-ttu-id="266d0-299">否。</span><span class="sxs-lookup"><span data-stu-id="266d0-299">No.</span></span> <span data-ttu-id="266d0-300">本機系統管理員無法變更或修改無法篡改的保護設定。</span><span class="sxs-lookup"><span data-stu-id="266d0-300">Local admins cannot change or modify tamper protection settings.</span></span>

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a><span data-ttu-id="266d0-301">如果我的裝置使用 Microsoft Defender for Endpoint 架，然後進入 boarded 狀態，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="266d0-301">What happens if my device is onboarded with Microsoft Defender for Endpoint and then goes into an off-boarded state?</span></span>

<span data-ttu-id="266d0-302">如果從 Microsoft Defender for Endpoint boarded 裝置，則會開啟防篡改防護，這是非管理裝置的預設狀態。</span><span class="sxs-lookup"><span data-stu-id="266d0-302">If a device is off-boarded from Microsoft Defender for Endpoint, tamper protection is turned on, which is the default state for unmanaged devices.</span></span> 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a><span data-ttu-id="266d0-303">Microsoft Defender 資訊安全中心中的篡改保護狀態變更是否會產生警示？</span><span class="sxs-lookup"><span data-stu-id="266d0-303">Will there be an alert about tamper protection status changing in the Microsoft Defender Security Center?</span></span>

<span data-ttu-id="266d0-304">是的。</span><span class="sxs-lookup"><span data-stu-id="266d0-304">Yes.</span></span> <span data-ttu-id="266d0-305">警示會顯示在 [ [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **警示**] 底下。</span><span class="sxs-lookup"><span data-stu-id="266d0-305">The alert is shown in [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) under **Alerts**.</span></span>

<span data-ttu-id="266d0-306">您的安全性運作小組也可以使用搜尋查詢，例如下列範例：</span><span class="sxs-lookup"><span data-stu-id="266d0-306">Your security operations team can also use hunting queries, such as the following example:</span></span>

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

<span data-ttu-id="266d0-307">[查看有關篡改嘗試的資訊](#view-information-about-tampering-attempts)。</span><span class="sxs-lookup"><span data-stu-id="266d0-307">[View information about tampering attempts](#view-information-about-tampering-attempts).</span></span>

## <a name="see-also"></a><span data-ttu-id="266d0-308">另請參閱</span><span class="sxs-lookup"><span data-stu-id="266d0-308">See also</span></span>

[<span data-ttu-id="266d0-309">使用 Microsoft Intune Endpoint Protection 協助保護 Windows 電腦</span><span class="sxs-lookup"><span data-stu-id="266d0-309">Help secure Windows PCs with Endpoint Protection for Microsoft Intune</span></span>](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[<span data-ttu-id="266d0-310">深入瞭解 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="266d0-310">Get an overview of Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint)

[<span data-ttu-id="266d0-311">相得益彰：Microsoft Defender 防毒軟體與適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="266d0-311">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](why-use-microsoft-defender-antivirus.md)
