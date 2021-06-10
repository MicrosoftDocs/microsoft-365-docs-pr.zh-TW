---
title: 使用資料隱私權規定的身分識別、裝置和威脅防護
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 365 的身分識別、裝置和威脅防護服務，避免個人資料遭到破壞。
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199462"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="8c65e-103">使用資料隱私權規定的身分識別、裝置和威脅防護</span><span class="sxs-lookup"><span data-stu-id="8c65e-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="8c65e-104">Microsoft 365 提供許多身分識別、裝置和威脅防護功能，組織可以採取這些功能來協助遵守資料隱私權相關的相容性法規。</span><span class="sxs-lookup"><span data-stu-id="8c65e-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="8c65e-105">本文說明這些方面的資料隱私權法規所需的內容，並提供相關 Microsoft 365 功能和服務的清單，其中包含可協助您處理實施需求的詳細資訊連結。</span><span class="sxs-lookup"><span data-stu-id="8c65e-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="8c65e-106">身分識別、裝置和威脅防護與資料隱私權規定的關聯方式</span><span class="sxs-lookup"><span data-stu-id="8c65e-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="8c65e-107">資料隱私權規定在其明確的程度上有所不同時，其所呼叫的實質是會包含在 GDPR 的第 5 (1)  (f) 中，這會指出：</span><span class="sxs-lookup"><span data-stu-id="8c65e-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="8c65e-108">個人資料的處理方式是為了確保個人資料的適當安全性，包括防止未經授權或非法處理的保護，以及防止意外遺失、損毀或損毀，使用適當的技術或組織量值 ( ' 誠信和機密性」 ) 。</span><span class="sxs-lookup"><span data-stu-id="8c65e-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="8c65e-109">由於個人資料損損通常是由系統管理或使用者帳戶損損和惡意的系統存取而造成。</span><span class="sxs-lookup"><span data-stu-id="8c65e-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="8c65e-110">例如，系統管理員帳戶的駭客攻擊可能會導致客戶信用卡號碼或其他個人資訊的 exfiltration。</span><span class="sxs-lookup"><span data-stu-id="8c65e-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="8c65e-111">您可能應該實施 Microsoft 365 中所有一般可行的身分識別、裝置和威脅防護，這會反映在合規性管理員中所提供的規範分數。</span><span class="sxs-lookup"><span data-stu-id="8c65e-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="8c65e-112">使用評估工作和合規性管理員的結果</span><span class="sxs-lookup"><span data-stu-id="8c65e-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="8c65e-113">合規性管理員包括使用下列類別的身分識別、裝置和威脅防護：</span><span class="sxs-lookup"><span data-stu-id="8c65e-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="8c65e-114">Identity 會對應至 **控制項存取** 類別</span><span class="sxs-lookup"><span data-stu-id="8c65e-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="8c65e-115">裝置對應于 [ **管理裝置** ] 類別</span><span class="sxs-lookup"><span data-stu-id="8c65e-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="8c65e-116">威脅防護會對應至 [ **防護威脅** ] 類別</span><span class="sxs-lookup"><span data-stu-id="8c65e-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="8c65e-117">如果在我們四個主要資料隱私權法規的範例集中選取這些選項，合規性管理員就會指定90改進動作，大部分的分數為 "27"。</span><span class="sxs-lookup"><span data-stu-id="8c65e-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="8c65e-118">因為這類大型數位是由合規性管理員為這些類別呼叫，所以這裡列出了一些較為常見的數位，供您參考。</span><span class="sxs-lookup"><span data-stu-id="8c65e-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="8c65e-119">使用 [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/)做為身分識別及 **控制存取** 類別，您可以：</span><span class="sxs-lookup"><span data-stu-id="8c65e-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="8c65e-120">實施重新抵禦的驗證 (，以防止「中間人」攻擊) </span><span class="sxs-lookup"><span data-stu-id="8c65e-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="8c65e-121">封鎖舊版驗證。</span><span class="sxs-lookup"><span data-stu-id="8c65e-121">Block legacy authentication.</span></span>
- <span data-ttu-id="8c65e-122">設定使用者風險和使用者登入風險原則。</span><span class="sxs-lookup"><span data-stu-id="8c65e-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="8c65e-123">為系統管理員和非系統管理員啟用條件式存取和多重要素驗證 (MFA) 。</span><span class="sxs-lookup"><span data-stu-id="8c65e-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="8c65e-124">設定並強制執行密碼原則。</span><span class="sxs-lookup"><span data-stu-id="8c65e-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="8c65e-125">使用 Azure AD Privileged Identity Management 限制存取特權帳戶。</span><span class="sxs-lookup"><span data-stu-id="8c65e-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="8c65e-126">在終止時停用存取。</span><span class="sxs-lookup"><span data-stu-id="8c65e-126">Disable access upon termination.</span></span>
- <span data-ttu-id="8c65e-127">審核使用者帳戶和狀態變更。</span><span class="sxs-lookup"><span data-stu-id="8c65e-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="8c65e-128">審閱角色群組和系統管理變更。</span><span class="sxs-lookup"><span data-stu-id="8c65e-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="8c65e-129">使用 [Microsoft 端點管理員](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)用於裝置和 **管理裝置** 類別，您可以：</span><span class="sxs-lookup"><span data-stu-id="8c65e-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="8c65e-130">封鎖越獄中斷及根行動裝置。</span><span class="sxs-lookup"><span data-stu-id="8c65e-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="8c65e-131">設定 Intune 以進行行動裝置管理。</span><span class="sxs-lookup"><span data-stu-id="8c65e-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="8c65e-132">建立 Android、iOS、macOS 和 Windows 裝置的符合性原則。</span><span class="sxs-lookup"><span data-stu-id="8c65e-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="8c65e-133">建立適用于 Android、iOS、macOS 及 Windows 裝置的裝置設定檔。</span><span class="sxs-lookup"><span data-stu-id="8c65e-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="8c65e-134">為 iOS 和 Windows 建立應用程式保護原則。</span><span class="sxs-lookup"><span data-stu-id="8c65e-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="8c65e-135">以鎖定畫面隱藏資訊。</span><span class="sxs-lookup"><span data-stu-id="8c65e-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="8c65e-136">為行動裝置實施密碼原則。</span><span class="sxs-lookup"><span data-stu-id="8c65e-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="8c65e-137">要求行動裝置在非活動狀態時鎖定。</span><span class="sxs-lookup"><span data-stu-id="8c65e-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="8c65e-138">要求行動裝置會在多個登入失敗時擦章。</span><span class="sxs-lookup"><span data-stu-id="8c65e-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="8c65e-139">針對 **威脅防護** 類別使用 [Exchange Online Protection 和 Microsoft Defender 以進行 Office 365](../security/office-365-security/defender-for-office-365.md) ，您可以：</span><span class="sxs-lookup"><span data-stu-id="8c65e-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="8c65e-140">啟用寄件者驗證 (SPF、DMARC 及 DKIM) 。</span><span class="sxs-lookup"><span data-stu-id="8c65e-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="8c65e-141">為 Office 365 的反網路釣魚原則設定 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="8c65e-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="8c65e-142">實施安全附件。</span><span class="sxs-lookup"><span data-stu-id="8c65e-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="8c65e-143">實施安全連結。</span><span class="sxs-lookup"><span data-stu-id="8c65e-143">Implement Safe Links.</span></span>
- <span data-ttu-id="8c65e-144">實施惡意程式碼偵測和回應原則。</span><span class="sxs-lookup"><span data-stu-id="8c65e-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="8c65e-145">實施輸出和輸入的垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="8c65e-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="8c65e-146">引用：</span><span class="sxs-lookup"><span data-stu-id="8c65e-146">References:</span></span>

- [<span data-ttu-id="8c65e-147">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="8c65e-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="8c65e-148">在 Office 365 中防禦威脅</span><span class="sxs-lookup"><span data-stu-id="8c65e-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="8c65e-149">安全附件</span><span class="sxs-lookup"><span data-stu-id="8c65e-149">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)
- [<span data-ttu-id="8c65e-150">安全連結</span><span class="sxs-lookup"><span data-stu-id="8c65e-150">Safe Links</span></span>](../security/office-365-security/safe-links.md)
- [<span data-ttu-id="8c65e-151">安全文件</span><span class="sxs-lookup"><span data-stu-id="8c65e-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
