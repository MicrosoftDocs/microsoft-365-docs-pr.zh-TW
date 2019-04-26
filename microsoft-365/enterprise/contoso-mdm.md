---
title: Contoso 的行動裝置管理
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 如何在 Microsoft 365 企業版中使用 EMS，來管理裝置和在裝置上執行的應用程式。
ms.openlocfilehash: f47d6a1ee608d33802f1c523d3b954af3771f212
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278039"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="1c0a0-103">Contoso 的行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="1c0a0-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="1c0a0-104">**摘要：** 深入了解 Contoso 如何在 Microsoft 365 企業版中使用 EMS，來管理裝置和在裝置上執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-104">**Summary:** Understand how Contoso uses EMS in Microsoft 365 Enterprise to manage its devices and the apps that run on them.</span></span>

<span data-ttu-id="1c0a0-105">Microsoft 365 企業版的企業行動力 + 安全性 (EMS) 由 Microsoft Intune 和一組 Azure 服務組成，可支援行動裝置和應用程式的管理和安全性。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-105">Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise consists of Microsoft Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="1c0a0-p101">Contoso 有許多使用行動裝置的員工，有些在 Contoso 所在地有辦公室，有些則沒有。Contoso 需要能夠讓員工具備生產力，但保持裝置、儲存在裝置上的 Contoso 公司資料及應用程式行為安全的方法。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="1c0a0-108">計劃</span><span class="sxs-lookup"><span data-stu-id="1c0a0-108">Plan</span></span>

<span data-ttu-id="1c0a0-109">在早期為 Microsoft 365 企業版分析行動裝置管理中，Contoso 識別出下列 Intune 使用案例：</span><span class="sxs-lookup"><span data-stu-id="1c0a0-109">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="1c0a0-110">保護 Exchange Online 的電子郵件和資料，讓其可以透過行動裝置安全地存取</span><span class="sxs-lookup"><span data-stu-id="1c0a0-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="1c0a0-111">為 Contoso 員工實施「帶您自己的裝置」(BYOD) 活動</span><span class="sxs-lookup"><span data-stu-id="1c0a0-111">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="1c0a0-112">分配公司手機和受限的共用平板電腦給 Contoso 員工</span><span class="sxs-lookup"><span data-stu-id="1c0a0-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="1c0a0-113">Contoso 不會使用 Intune 來：</span><span class="sxs-lookup"><span data-stu-id="1c0a0-113">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="1c0a0-114">讓員工從未受管理的公用 Kiosk 安全地存取 Office 365</span><span class="sxs-lookup"><span data-stu-id="1c0a0-114">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="1c0a0-115">由於不再有內部部署 Microsoft Exchange 伺服器，因此用以保護內部部署上的電子郵件和資料，讓其可以由行動裝置安全地存取。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="1c0a0-116">部署</span><span class="sxs-lookup"><span data-stu-id="1c0a0-116">Deploy</span></span>

<span data-ttu-id="1c0a0-117">這是 Contoso 設定行動裝置管理基礎架構的方式：</span><span class="sxs-lookup"><span data-stu-id="1c0a0-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="1c0a0-118">將 Intune 設定為行動裝置管理 (MDM) 的授權單位，並在 Azure 上使用 Intune 管理內容及裝置</span><span class="sxs-lookup"><span data-stu-id="1c0a0-118">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="1c0a0-119">建立適用於 Azure AD 群組的裝置，以進行註冊和使用 Intune 設定及以裝置為基礎的條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="1c0a0-119">Created Azure AD groups for device groups for enrollment and Intune settings and conditional access policies</span></span>

  <span data-ttu-id="1c0a0-120">如需詳細資訊，請參閱 [Contoso 的條件式存取原則](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-120">See [Contoso's conditional access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="1c0a0-121">啟用 Apple 裝置平台以支援員工使用 iPad、iMac、iPhone 及 iPhone 式公司手機</span><span class="sxs-lookup"><span data-stu-id="1c0a0-121">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="1c0a0-122">建立 Contoso 特定的條款與條件原則，會在行動裝置安裝 Contoso 公司入口網站時出現</span><span class="sxs-lookup"><span data-stu-id="1c0a0-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="1c0a0-123">對於未註冊的裝置，則需要一組 Mobile Application Management (MAM) 原則才能授權存取 Office 365 服務</span><span class="sxs-lookup"><span data-stu-id="1c0a0-123">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="1c0a0-124">建立 Intune 原則以強制執行：</span><span class="sxs-lookup"><span data-stu-id="1c0a0-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="1c0a0-125">允許的應用程式</span><span class="sxs-lookup"><span data-stu-id="1c0a0-125">Allowed apps</span></span>
  - <span data-ttu-id="1c0a0-126">裝置加密以防止未經授權的存取</span><span class="sxs-lookup"><span data-stu-id="1c0a0-126">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="1c0a0-127">六位數 PIN 或密碼</span><span class="sxs-lookup"><span data-stu-id="1c0a0-127">A six-digit PIN or password</span></span>
  - <span data-ttu-id="1c0a0-128">閒置等待逾時時間</span><span class="sxs-lookup"><span data-stu-id="1c0a0-128">An inactivity timeout period</span></span>
  - <span data-ttu-id="1c0a0-129">Windows 10 裝置上的防毒軟體與惡意程式碼防護，以及 Windows Defender 的簽章更新</span><span class="sxs-lookup"><span data-stu-id="1c0a0-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="1c0a0-130">自動更新 Windows 10 裝置，以包含最新的安全性更新</span><span class="sxs-lookup"><span data-stu-id="1c0a0-130">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="1c0a0-131">推送憑證至受管理的裝置</span><span class="sxs-lookup"><span data-stu-id="1c0a0-131">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="1c0a0-p102">清楚分隔商務和個人資料。使用者或系統管理員可以選擇性地從裝置清除公司資料，而不影響個人資料，例如圖片、個人電子郵件帳戶及個人檔案。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="1c0a0-p103">一旦部署，Contoso 可透過新增至適當的 Intune 裝置群組註冊電腦及公司智慧型手機和平板電腦，以及推出 BYOD 計畫來讓員工註冊個人裝置。註冊的裝置將會收到 Intune 原則，將裝置和其應用程式納入管理及安全性保護。未註冊的裝置則會使用 Mobile Application Management (MAM) 原則指定允許的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

## <a name="next-step"></a><span data-ttu-id="1c0a0-137">下一步</span><span class="sxs-lookup"><span data-stu-id="1c0a0-137">Next step</span></span>

<span data-ttu-id="1c0a0-138">[深入了解](contoso-info-protect.md) Contoso 如何使用 Microsoft 365 企業版的資訊保護功能，分類、識別及保護組織中的重要數位資產。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-138">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c0a0-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1c0a0-139">See also</span></span>

[<span data-ttu-id="1c0a0-140">Microsoft 365 企業版的行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="1c0a0-140">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="1c0a0-141">部署指南</span><span class="sxs-lookup"><span data-stu-id="1c0a0-141">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1c0a0-142">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="1c0a0-142">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

