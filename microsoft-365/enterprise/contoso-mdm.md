---
title: Contoso 的行動裝置管理
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 瞭解 Contoso 如何在 Microsoft 365 for enterprise 中使用 Microsoft Intune 來管理其裝置和在其上執行的應用程式。
ms.openlocfilehash: 40d9473bcadfa636f6fd2b2c6c861c27dae8497c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685839"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="d1e39-103">Contoso 的行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="d1e39-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="d1e39-104">適用于企業的 Microsoft 365 包含 Intune 和一組 Azure 服務，以支援行動裝置和應用程式管理及安全性。</span><span class="sxs-lookup"><span data-stu-id="d1e39-104">Microsoft 365 for enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="d1e39-p101">Contoso 有許多使用行動裝置的員工，有些在 Contoso 所在地有辦公室，有些則沒有。Contoso 需要能夠讓員工具備生產力，但保持裝置、儲存在裝置上的 Contoso 公司資料及應用程式行為安全的方法。</span><span class="sxs-lookup"><span data-stu-id="d1e39-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="d1e39-107">計劃</span><span class="sxs-lookup"><span data-stu-id="d1e39-107">Plan</span></span>

<span data-ttu-id="d1e39-108">在 Microsoft 365 for enterprise 的行動裝置管理的分析早期，Contoso 識別出下列 Intune 使用案例：</span><span class="sxs-lookup"><span data-stu-id="d1e39-108">Early in the analysis of mobile device management for Microsoft 365 for enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="d1e39-109">保護 Exchange Online 的電子郵件和資料，讓其可以透過行動裝置安全地存取</span><span class="sxs-lookup"><span data-stu-id="d1e39-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="d1e39-110">為 Contoso 員工實施「帶您自己的裝置」(BYOD) 活動</span><span class="sxs-lookup"><span data-stu-id="d1e39-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="d1e39-111">分配公司手機和受限的共用平板電腦給 Contoso 員工</span><span class="sxs-lookup"><span data-stu-id="d1e39-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="d1e39-112">Contoso 不會使用 Intune 來：</span><span class="sxs-lookup"><span data-stu-id="d1e39-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="d1e39-113">允許員工透過非管理的公用展臺安全地存取 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d1e39-113">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="d1e39-114">由於不再有內部部署 Microsoft Exchange 伺服器，因此用以保護內部部署上的電子郵件和資料，讓其可以由行動裝置安全地存取。</span><span class="sxs-lookup"><span data-stu-id="d1e39-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="d1e39-115">部署</span><span class="sxs-lookup"><span data-stu-id="d1e39-115">Deploy</span></span>

<span data-ttu-id="d1e39-116">這是 Contoso 設定行動裝置管理基礎架構的方式：</span><span class="sxs-lookup"><span data-stu-id="d1e39-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="d1e39-117">將 Intune 設定為行動裝置管理 (MDM) 的授權單位，並在 Azure 上使用 Intune 管理內容及裝置</span><span class="sxs-lookup"><span data-stu-id="d1e39-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="d1e39-118">建立適用於裝置的 Azure AD 群組以進行註冊，並且使用 Intune 設定及以裝置為基礎的條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="d1e39-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="d1e39-119">如需詳細資訊，請參閱 [Contoso 的條件式存取原則](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="d1e39-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="d1e39-120">啟用 Apple 裝置平台以支援員工使用 iPad、iMac、iPhone 及 iPhone 式公司手機</span><span class="sxs-lookup"><span data-stu-id="d1e39-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="d1e39-121">建立 Contoso 特定的條款與條件原則，會在行動裝置安裝 Contoso 公司入口網站時出現</span><span class="sxs-lookup"><span data-stu-id="d1e39-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="d1e39-122">對於未註冊的裝置，一組行動應用程式管理 (MAM) 原則，需要驗證才能存取 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="d1e39-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="d1e39-123">建立 Intune 原則以強制執行：</span><span class="sxs-lookup"><span data-stu-id="d1e39-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="d1e39-124">允許的應用程式</span><span class="sxs-lookup"><span data-stu-id="d1e39-124">Allowed apps</span></span>
  - <span data-ttu-id="d1e39-125">裝置加密以防止未經授權的存取</span><span class="sxs-lookup"><span data-stu-id="d1e39-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="d1e39-126">六位數 PIN 或密碼</span><span class="sxs-lookup"><span data-stu-id="d1e39-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="d1e39-127">閒置等待逾時時間</span><span class="sxs-lookup"><span data-stu-id="d1e39-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="d1e39-128">Windows 10 裝置上的防毒軟體與惡意程式碼防護，以及 Windows Defender 的簽章更新</span><span class="sxs-lookup"><span data-stu-id="d1e39-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="d1e39-129">自動更新 Windows 10 裝置，以包含最新的安全性更新</span><span class="sxs-lookup"><span data-stu-id="d1e39-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="d1e39-130">推送憑證至受管理的裝置</span><span class="sxs-lookup"><span data-stu-id="d1e39-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="d1e39-p102">清楚分隔商務和個人資料。使用者或系統管理員可以選擇性地從裝置清除公司資料，而不影響個人資料，例如圖片、個人電子郵件帳戶及個人檔案。</span><span class="sxs-lookup"><span data-stu-id="d1e39-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="d1e39-p103">一旦部署，Contoso 可透過新增至適當的 Intune 裝置群組註冊電腦及公司智慧型手機和平板電腦，以及推出 BYOD 計畫來讓員工註冊個人裝置。註冊的裝置將會收到 Intune 原則，將裝置和其應用程式納入管理及安全性保護。未註冊的裝置則會使用 Mobile Application Management (MAM) 原則指定允許的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d1e39-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="d1e39-136">以下是 Contoso 的行動裝置管理部署架構。</span><span class="sxs-lookup"><span data-stu-id="d1e39-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Contoso 的行動裝置管理部署基礎結構](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="d1e39-138">下一步</span><span class="sxs-lookup"><span data-stu-id="d1e39-138">Next step</span></span>

<span data-ttu-id="d1e39-139">[瞭解](contoso-info-protect.md) Contoso 如何使用 Microsoft 365 for enterprise 的資訊保護功能，在其整個組織中分類、識別及保護重要的數位資產。</span><span class="sxs-lookup"><span data-stu-id="d1e39-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1e39-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d1e39-140">See also</span></span>

[<span data-ttu-id="d1e39-141">Microsoft 365 裝置管理</span><span class="sxs-lookup"><span data-stu-id="d1e39-141">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="d1e39-142">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="d1e39-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d1e39-143">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="d1e39-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

