---
title: Microsoft 365 Lighthouse 的需求
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 針對受管理的服務提供者 (MSPs) ，取得 Microsoft 365 Lighthouse 使用的需求清單。
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395073"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a><span data-ttu-id="a34c3-103">Microsoft 365 Lighthouse 的需求</span><span class="sxs-lookup"><span data-stu-id="a34c3-103">Requirements for Microsoft 365 Lighthouse</span></span>

> [!NOTE]
> <span data-ttu-id="a34c3-104">本文所述的功能都是在預覽中進行變更，而且只有符合本文所列需求的合作夥伴才能使用。</span><span class="sxs-lookup"><span data-stu-id="a34c3-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the requirements listed in this article.</span></span> <span data-ttu-id="a34c3-105">如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="a34c3-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="a34c3-106">Microsoft 365 Lighthouse 是協助受管理的服務提供者 (MSPs) 安全性及管理裝置、資料和使用者規模，以供小型和中型企業 (SMB) 客戶使用的系統管理員入口網站。</span><span class="sxs-lookup"><span data-stu-id="a34c3-106">Microsoft 365 Lighthouse is an admin portal that helps Managed Service Providers (MSPs) secure and manage devices, data, and users at scale for small- and medium-sized business (SMB) customers.</span></span>  

<span data-ttu-id="a34c3-107">MSPs 必須在雲端解決方案提供者 (CSP) 程式中註冊，以供間接轉銷商或直銷者使用 Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="a34c3-107">MSPs must be enrolled in the Cloud Solution Provider (CSP) program as an Indirect Reseller or Direct Bill partner to use Microsoft 365 Lighthouse.</span></span>  

<span data-ttu-id="a34c3-108">此外，每個 MSP 客戶租使用者必須符合下列需求，才能使用 Microsoft 365 Lighthouse：</span><span class="sxs-lookup"><span data-stu-id="a34c3-108">In addition, each MSP customer tenant must qualify for Microsoft 365 Lighthouse by meeting the following requirements:</span></span> 
 
- <span data-ttu-id="a34c3-109">已委派的系統管理員許可權 (MSP 的) </span><span class="sxs-lookup"><span data-stu-id="a34c3-109">Delegated Admin Privileges (DAP) for the MSP</span></span> 
- <span data-ttu-id="a34c3-110">至少一個 Microsoft 365 商務進階版授權</span><span class="sxs-lookup"><span data-stu-id="a34c3-110">At least one Microsoft 365 Business Premium license</span></span> 
- <span data-ttu-id="a34c3-111">授權的使用者少於500個</span><span class="sxs-lookup"><span data-stu-id="a34c3-111">Fewer than 500 licensed users</span></span>  

## <a name="requirements-for-enablingdevice-management"></a><span data-ttu-id="a34c3-112">啟用裝置管理的需求</span><span class="sxs-lookup"><span data-stu-id="a34c3-112">Requirements for enabling device management</span></span>   

<span data-ttu-id="a34c3-113">若要在裝置管理頁面上查看客戶租使用者裝置，MSP 必須執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="a34c3-113">To view customer tenant devices on the device management pages, a MSP must:</span></span>    

- <span data-ttu-id="a34c3-114">在 Microsoft 端點管理員 (MEM) 中登記所有客戶裝置。</span><span class="sxs-lookup"><span data-stu-id="a34c3-114">Enroll all customer devices in Microsoft Endpoint Manager (MEM).</span></span><span data-ttu-id="a34c3-115">如需詳細資訊，請參閱[在 Microsoft Intune 中註冊裝置](/mem/intune/enrollment/)。</span><span class="sxs-lookup"><span data-stu-id="a34c3-115"> For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>
- <span data-ttu-id="a34c3-116">將規範原則指派給所有客戶裝置。</span><span class="sxs-lookup"><span data-stu-id="a34c3-116">Assign compliance policies to all customer devices.</span></span><span data-ttu-id="a34c3-117">如需詳細資訊，請參閱[Create a 合規性原則 in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="a34c3-117"> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span> 

## <a name="requirements-for-enabling-usermanagement"></a><span data-ttu-id="a34c3-118">啟用使用者管理的需求</span><span class="sxs-lookup"><span data-stu-id="a34c3-118">Requirements for enabling user management</span></span> 

<span data-ttu-id="a34c3-119">若要讓客戶資料顯示在使用者管理頁面（包括危險的使用者、多因素驗證及密碼重設）的報表上，客戶租使用者必須具有 Azure Active Directory 進階版 P1 或更新版本的授權。</span><span class="sxs-lookup"><span data-stu-id="a34c3-119">For customer data to show up in reports on user management pages, including Risky users, Multifactor authentication, and Password reset, customer tenants must have licenses for Azure Active Directory Premium P1 or later.</span></span> <span data-ttu-id="a34c3-120">Microsoft 365 商務進階版附帶 Azure AD Premium P1。</span><span class="sxs-lookup"><span data-stu-id="a34c3-120">Azure AD Premium P1 is included with Microsoft 365 Business Premium.</span></span>   

## <a name="requirements-for-enablingthreat-management"></a><span data-ttu-id="a34c3-121">啟用威脅管理的需求</span><span class="sxs-lookup"><span data-stu-id="a34c3-121">Requirements for enabling threat management</span></span> 

<span data-ttu-id="a34c3-122">若要在威脅管理頁面上查看客戶承租人裝置和威脅，您必須在 Microsoft 端點管理員 (MEM 中登記所有客戶租使用者裝置，並執行 Microsoft Defender 防毒軟體以加以保護) 。</span><span class="sxs-lookup"><span data-stu-id="a34c3-122">To view customer tenant devices and threats on the threat management pages, you must enroll all customer tenant devices in Microsoft Endpoint Manager (MEM) and protect them by running Microsoft Defender Antivirus.</span></span>  

<span data-ttu-id="a34c3-123">如需詳細資訊，請參閱[在 Microsoft Intune 中註冊裝置](/mem/intune/enrollment/)。</span><span class="sxs-lookup"><span data-stu-id="a34c3-123">For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>  

<span data-ttu-id="a34c3-124">Microsoft Defender 防毒軟體是 Windows 作業系統的一部分，且預設會在執行 Windows 10 的裝置上啟用。</span><span class="sxs-lookup"><span data-stu-id="a34c3-124">Microsoft Defender Antivirus is part of the Windows operating system and is enabled by default on devices running Windows 10.</span></span>  

> [!NOTE] 
> <span data-ttu-id="a34c3-125">如果您使用非 Microsoft 防病毒方案，而不是 Microsoft Defender 防毒軟體，則 Microsoft Defender 防毒軟體會自動停用。</span><span class="sxs-lookup"><span data-stu-id="a34c3-125">If you're using a non-Microsoft antivirus solution and not Microsoft Defender Antivirus, Microsoft Defender Antivirus is disabled automatically.</span></span> <span data-ttu-id="a34c3-126">當您卸載非 Microsoft 防病毒解決方案時，會自動啟用 Microsoft Defender 防毒軟體，以保護您的 Windows 裝置免受威脅。</span><span class="sxs-lookup"><span data-stu-id="a34c3-126">When you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus is activated automatically to protect your Windows devices from threats.</span></span>    

## <a name="related-content"></a><span data-ttu-id="a34c3-127">相關內容</span><span class="sxs-lookup"><span data-stu-id="a34c3-127">Related content</span></span>   

<span data-ttu-id="a34c3-128">[設定 Microsoft 365 Lighthouse 入口網站安全性](m365-lighthouse-configure-portal-security.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="a34c3-128">[Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md) (article)</span></span>\
<span data-ttu-id="a34c3-129">[Microsoft 365 Lighthouse 裝置符合性頁面概述](m365-lighthouse-device-compliance-page-overview.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="a34c3-129">[Microsoft 365 Lighthouse Device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="a34c3-130">[Microsoft 365 Lighthouse 使用者] 頁面概述](m365-lighthouse-users-page-overview.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="a34c3-130">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="a34c3-131">[Microsoft 365 Lighthouse 威脅管理頁面概述](m365-lighthouse-threat-management-page-overview.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="a34c3-131">[Microsoft 365 Lighthouse Threat management page overview](m365-lighthouse-threat-management-page-overview.md) (article)</span></span>\
<span data-ttu-id="a34c3-132">[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml)   (篇文章) </span><span class="sxs-lookup"><span data-stu-id="a34c3-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

