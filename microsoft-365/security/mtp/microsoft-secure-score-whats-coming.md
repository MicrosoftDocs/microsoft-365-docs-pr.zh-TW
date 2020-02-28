---
title: 什麼 Microsoft 安全分數即將？
description: 說明 Microsoft 安全分數 Microsoft 365 安全性中心、 詳細資料的計算方式，以及安全性系統管理員可以預期。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365，安全分數資訊安全中心、 改進動作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4d445d4c917a46b12592308f599570725ace8e9d
ms.sourcegitcommit: 6c7f6ef98c321c80a9254c10bbbb917895b5c156
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/27/2020
ms.locfileid: "42322562"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="eed10-104">什麼 Microsoft 安全分數即將？</span><span class="sxs-lookup"><span data-stu-id="eed10-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="eed10-105">若要讓 Microsoft 安全分數較佳的安全性狀態代表並改善可用性，我們會在不久的將來進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="eed10-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="eed10-106">您的成績和最大可能分數會變更。</span><span class="sxs-lookup"><span data-stu-id="eed10-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="eed10-107">不過，這並不表示您的安全性狀態變更。</span><span class="sxs-lookup"><span data-stu-id="eed10-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="eed10-108">若要深入了解最近的變更，請參閱[What's new in Microsoft 安全分數？](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="eed10-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="eed10-109">2nd 2020 年 3 月</span><span class="sxs-lookup"><span data-stu-id="eed10-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="eed10-110">從 Intune 移除改進動作</span><span class="sxs-lookup"><span data-stu-id="eed10-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="eed10-111">提供從 Intune Microsoft 安全分數改進動作的評估之後, 我們決定它們並不提供在組織中的裝置安全性狀態的有用表示法。</span><span class="sxs-lookup"><span data-stu-id="eed10-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="eed10-112">而不將重點放在原則，我們正在努力帶來安全性控制的直接評估之裝置的組態狀態。</span><span class="sxs-lookup"><span data-stu-id="eed10-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="eed10-113">會移除下列 Intune 改進動作：</span><span class="sxs-lookup"><span data-stu-id="eed10-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="eed10-114">啟用 Microsoft Intune 行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="eed10-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="eed10-115">Android 版建立 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="eed10-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="eed10-116">建立工作 Android 版的 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="eed10-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="eed10-117">Android 版建立 Microsoft Intune 應用程式防護原則</span><span class="sxs-lookup"><span data-stu-id="eed10-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="eed10-118">建立 iOS 版 Microsoft Intune 應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="eed10-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="eed10-119">標記裝置與指定為不符合任何 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="eed10-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="eed10-120">建立 iOS 版 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="eed10-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="eed10-121">建立 macOS Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="eed10-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="eed10-122">建立 Windows 的 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="eed10-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="eed10-123">Android 版建立 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="eed10-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="eed10-124">建立工作 Android 版的 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="eed10-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="eed10-125">建立 macOS 的 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="eed10-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="eed10-126">建立 iOS 版 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="eed10-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="eed10-127">建立 Windows 的 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="eed10-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="eed10-128">啟用 Microsoft Intune 中的增強型的 jailbreak 偵測</span><span class="sxs-lookup"><span data-stu-id="eed10-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="eed10-129">需要修正的所有裝置、 防毒和防火牆啟用</span><span class="sxs-lookup"><span data-stu-id="eed10-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="eed10-130">啟用 Windows Defender ATP 整合至 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="eed10-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="eed10-131">建立 Microsoft Intune Windows 資訊保護原則</span><span class="sxs-lookup"><span data-stu-id="eed10-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="eed10-132">需要有進階安全性設定的所有裝置</span><span class="sxs-lookup"><span data-stu-id="eed10-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="eed10-133">每週檢閱封鎖的裝置報告</span><span class="sxs-lookup"><span data-stu-id="eed10-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="eed10-134">移除不符合預期可靠的度量單位的改進動作</span><span class="sxs-lookup"><span data-stu-id="eed10-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span> 

<span data-ttu-id="eed10-135">若要確保 Microsoft 安全分數才有意義，以及改進的每一個動作是可以測量且可靠，我們會移除下列改進動作。</span><span class="sxs-lookup"><span data-stu-id="eed10-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="eed10-136">開啟稽核資料記錄</span><span class="sxs-lookup"><span data-stu-id="eed10-136">Turn on audit data recording</span></span>
- <span data-ttu-id="eed10-137">探索風險並不相容的陰影 IT 應用程式</span><span class="sxs-lookup"><span data-stu-id="eed10-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="eed10-138">檢閱權限 & 封鎖風險 OAuth 應用程式連線至您的環境</span><span class="sxs-lookup"><span data-stu-id="eed10-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="eed10-139">在 SharePoint online 的文件庫設定版本設定</span><span class="sxs-lookup"><span data-stu-id="eed10-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="eed10-140">MFA 改進動作更新</span><span class="sxs-lookup"><span data-stu-id="eed10-140">MFA improvement action updates</span></span>

<span data-ttu-id="eed10-141">若要反映適用於企業以確保 upmost 安全性時，套用原則可搭配其業務需求，Microsoft 安全分數會移除三個改進動作圍繞多重要素驗證，並新增兩個。</span><span class="sxs-lookup"><span data-stu-id="eed10-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="eed10-142">會移除三個：</span><span class="sxs-lookup"><span data-stu-id="eed10-142">The three that will be removed:</span></span>

- <span data-ttu-id="eed10-143">登錄所有使用者的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="eed10-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="eed10-144">需要 MFA 的所有使用者</span><span class="sxs-lookup"><span data-stu-id="eed10-144">Require MFA for all users</span></span>
- <span data-ttu-id="eed10-145">需要 MFA 的 Azure AD 特殊權限角色</span><span class="sxs-lookup"><span data-stu-id="eed10-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="eed10-146">新增新的改進動作：</span><span class="sxs-lookup"><span data-stu-id="eed10-146">New improvement actions added:</span></span>

- <span data-ttu-id="eed10-147">確定所有的使用者可以完成的安全存取多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="eed10-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="eed10-148">需要 MFA 的系統管理角色</span><span class="sxs-lookup"><span data-stu-id="eed10-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="eed10-149">這些新的改進動作將會需要透過您的目錄中註冊您的使用者或系統管理員針對多重要素驗證 (MFA)，以及建立正確的一組原則符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="eed10-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="eed10-150">主要目標是有彈性，同時確保所有使用者和系統管理員可以驗證與多重因素或風險式身分識別驗證提示。</span><span class="sxs-lookup"><span data-stu-id="eed10-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="eed10-151">可能需要的表單具有多個範圍的決策或設定安全性的預設值 （即將年 3 月 16），可讓 Microsoft 決定何時 MFA 的挑戰使用者套用的原則。</span><span class="sxs-lookup"><span data-stu-id="eed10-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="eed10-152">移除 「 檢閱 」 改進動作</span><span class="sxs-lookup"><span data-stu-id="eed10-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="eed10-153">之一的安全分數原則是分數應依照標準化預定且更容易與相關。</span><span class="sxs-lookup"><span data-stu-id="eed10-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="eed10-154">具有不是可以測量或可採取行動的改進動作具有已造成混淆。</span><span class="sxs-lookup"><span data-stu-id="eed10-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="eed10-155">一個 Microsoft 安全分數僅合理時的每個建議有清除影響分數。</span><span class="sxs-lookup"><span data-stu-id="eed10-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="eed10-156">檢閱改進動作不會測量至其他改進動作為相同的標準。</span><span class="sxs-lookup"><span data-stu-id="eed10-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="eed10-157">基於這些理由，將會暫時移除所有需要檢閱頻率的改進動作。</span><span class="sxs-lookup"><span data-stu-id="eed10-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="eed10-158">在您的組件上不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="eed10-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="eed10-159">16 2020 年 3 月</span><span class="sxs-lookup"><span data-stu-id="eed10-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="eed10-160">移除不符合預期可靠的度量單位，或沒有提供實用的安全性狀態表示改進動作</span><span class="sxs-lookup"><span data-stu-id="eed10-160">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="eed10-161">若要確保 Microsoft 安全分數才有意義，以及改進的每一個動作是可以測量且可靠，我們會移除下列改進動作。</span><span class="sxs-lookup"><span data-stu-id="eed10-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="eed10-162">商務用 OneDrive 中儲存使用者文件</span><span class="sxs-lookup"><span data-stu-id="eed10-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="eed10-163">設定 Office 365 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="eed10-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="eed10-164">若要確認 Url 設定 Office 365 安全連結</span><span class="sxs-lookup"><span data-stu-id="eed10-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="eed10-165">不允許 [信箱委派]</span><span class="sxs-lookup"><span data-stu-id="eed10-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="eed10-166">允許匿名來賓共用網站和文件的連結</span><span class="sxs-lookup"><span data-stu-id="eed10-166">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="eed10-167">開啟雲端 App 安全性主控台</span><span class="sxs-lookup"><span data-stu-id="eed10-167">Turn on Cloud App Security Console</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="eed10-168">Azure AD 改進動作支援安全的預設值</span><span class="sxs-lookup"><span data-stu-id="eed10-168">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="eed10-169">Microsoft 安全分數會更新改進動作來支援[Azure AD 中預設的安全性](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，方便大家來協助保護您的組織使用的常見的攻擊的預先設定的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="eed10-169">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="eed10-170">它會影響下列改進動作：</span><span class="sxs-lookup"><span data-stu-id="eed10-170">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="eed10-171">確定所有的使用者可以完成的安全存取多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="eed10-171">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="eed10-172">需要 MFA 的系統管理角色</span><span class="sxs-lookup"><span data-stu-id="eed10-172">Require MFA for administrative roles</span></span>
- <span data-ttu-id="eed10-173">啟用原則，以封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="eed10-173">Enable policy to block legacy authentication</span></span>
