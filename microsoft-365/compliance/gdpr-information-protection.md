---
title: 資訊保護
description: 為一般資料保護規定 (GDPR) 瞭解 Microsoft 365 中的資訊保護功能。
keywords: Microsoft 365、Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02dbb22ad47fbacf964308d2b4a989f34b6d6c9d
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307680"
---
# <a name="information-protection-for-gdpr-with-microsoft-365-capabilities"></a><span data-ttu-id="c3215-104">使用 Microsoft 365 功能實現 GDPR 資訊保護</span><span class="sxs-lookup"><span data-stu-id="c3215-104">Information protection for GDPR with Microsoft 365 capabilities</span></span>

<span data-ttu-id="c3215-p101">Microsoft 365 提供了豐富的功能組合，可協助您達成一般資料保護規定 (GDPR) 的合規性。本文摘要說明建議的功能並提供詳細資訊連結。</span><span class="sxs-lookup"><span data-stu-id="c3215-p101">Microsoft 365 provides a rich set of capabilities to help you achieve compliance with the General Data Protection Regulation (GDPR). This article summarizes recommended capabilities with links to more information.</span></span>

<span data-ttu-id="c3215-107">如需 Microsoft 如何協助您使用 GDPR 的詳細資訊，請參閱服務信任入口網站中的[快速入門：GDPR 責任支援](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)。</span><span class="sxs-lookup"><span data-stu-id="c3215-107">For more information about how Microsoft can help you with the GDPR, see [Get Started: Support for GDPR Accountability](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) in the Service Trust Portal.</span></span>

## <a name="information-protection"></a><span data-ttu-id="c3215-108">資訊保護</span><span class="sxs-lookup"><span data-stu-id="c3215-108">Information protection</span></span>

<span data-ttu-id="c3215-p102">Office 365 提供豐富的資料管理功能組合。如需有關尋找、分類、保護及監控個人資料的說明，請參閱 [GDPR 的 Office 365 資訊保護](https://docs.microsoft.com/microsoft-365/compliance/office-365-information-protection-for-gdpr)。</span><span class="sxs-lookup"><span data-stu-id="c3215-p102">Office 365 provides a rich set of data governance capabilities. For help with finding, classifying, protecting, and monitoring personal data, see [Office 365 Information Protection for GDPR](https://docs.microsoft.com/microsoft-365/compliance/office-365-information-protection-for-gdpr).</span></span>

<span data-ttu-id="c3215-111">如需內部部署伺服器的協助，包括檔案共用、SharePoint Server、Exchange Server、商務用 Skype Server、Project Server 和 Office Online Server，請參閱＜[內部部署 Office 伺服器的 GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-for-office-servers)＞。</span><span class="sxs-lookup"><span data-stu-id="c3215-111">For help with on-premises servers, including file shares, SharePoint Server, Exchange Server, Skype for Business Server, Project Server, and Office Online Server, see [GDPR for on-premises Office servers](https://docs.microsoft.com/microsoft-365/compliance/gdpr-for-office-servers).</span></span> 

## <a name="identity-and-access-management"></a><span data-ttu-id="c3215-112">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="c3215-112">Identity and access management</span></span>

<span data-ttu-id="c3215-113">Azure Active Directory 和其他 Microsoft 365 功能提供了豐富的功能組合，以在不同的身分識別與裝置存取資訊時保護存取的安全性：</span><span class="sxs-lookup"><span data-stu-id="c3215-113">Azure Active Directory and other Microsoft 365 capabilities provide a rich set of capabilities to protect access to your data from identities and devices:</span></span>

- <span data-ttu-id="c3215-114">多重要素驗證 (MFA)</span><span class="sxs-lookup"><span data-stu-id="c3215-114">Multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="c3215-115">條件式存取</span><span class="sxs-lookup"><span data-stu-id="c3215-115">Conditional access</span></span>
- <span data-ttu-id="c3215-116">特殊權限身分識別管理</span><span class="sxs-lookup"><span data-stu-id="c3215-116">Privileged identity management</span></span>
- <span data-ttu-id="c3215-117">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="c3215-117">Mobile device management</span></span>
- <span data-ttu-id="c3215-118">行動應用程式管理</span><span class="sxs-lookup"><span data-stu-id="c3215-118">Mobile application management</span></span>
- <span data-ttu-id="c3215-119">硬體保護認證</span><span class="sxs-lookup"><span data-stu-id="c3215-119">Hardware protection for credentials</span></span>

<span data-ttu-id="c3215-120">Microsoft 提供下列建議設定，可作為起點設定：</span><span class="sxs-lookup"><span data-stu-id="c3215-120">Microsoft provides a recommended configuration you can use as a starting point:</span></span>

- <span data-ttu-id="c3215-p103">[身分識別與裝置存取設定](../enterprise/microsoft-365-policies-configurations.md)：可達成三層保護 (基本、機密、高度管制) 的建議原則設定。本指導包含 Exchange Online 和 SharePoint Online (包含商務用 OneDrive) 的建議原則。</span><span class="sxs-lookup"><span data-stu-id="c3215-p103">[Identity and device access configurations](../enterprise/microsoft-365-policies-configurations.md): Recommended policy configurations to achieve three tiers of protection (baseline, sensitive, highly regulated). This guidance includes recommended policies for Exchange Online and SharePoint Online (including OneDrive for Business).</span></span>
- <span data-ttu-id="c3215-123">[政治活動、非營利組織及其他敏捷組織的安全性指導](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o)：這包含同一組原則，但提供 BYOD 環境及 B2B 帳戶的額外指導。</span><span class="sxs-lookup"><span data-stu-id="c3215-123">[Security guidance for political campaigns, nonprofits, and other agile organizations](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o): This includes the same set of policies but provides more guidance for BYOD environments and for B2B accounts.</span></span>

## <a name="threat-protection"></a><span data-ttu-id="c3215-124">威脅防護</span><span class="sxs-lookup"><span data-stu-id="c3215-124">Threat Protection</span></span>

<span data-ttu-id="c3215-p104">威脅防護是跨 Microsoft 365 服務所建置。您可以從以下幾個資源開始著手：</span><span class="sxs-lookup"><span data-stu-id="c3215-p104">Threat protection is built across Microsoft 365 services. Here are a few resources to get you started:</span></span>

- <span data-ttu-id="c3215-p105">[Office 365 安全性藍圖：前 30 天、前 90 天和之後的最高優先順序](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)。此藍圖包含實作功能的建議。</span><span class="sxs-lookup"><span data-stu-id="c3215-p105">[Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap). This roadmap includes recommendations for implementing capabilities.</span></span> 
- <span data-ttu-id="c3215-129">[防範 Office 365 中的威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。</span><span class="sxs-lookup"><span data-stu-id="c3215-129">[Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span> <span data-ttu-id="c3215-130">深入了解您可以在 Microsoft 365 資訊安全中心採取的保護動作。</span><span class="sxs-lookup"><span data-stu-id="c3215-130">Learn about protection actions you can take in the Microsoft 365 security center.</span></span>
- <span data-ttu-id="c3215-p107">[Windows 威脅防護](https://docs.microsoft.com/windows/security/threat-protection/)。深入了解 Windows Defender 進階威脅防護與 Windows 10 的其他功能。</span><span class="sxs-lookup"><span data-stu-id="c3215-p107">[Windows Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/). Learn more about Windows Defender Advanced Threat Protection and other capabilities in Windows 10.</span></span>

## <a name="learn-more"></a><span data-ttu-id="c3215-133">深入了解</span><span class="sxs-lookup"><span data-stu-id="c3215-133">Learn more</span></span>

[<span data-ttu-id="c3215-134">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="c3215-134">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
