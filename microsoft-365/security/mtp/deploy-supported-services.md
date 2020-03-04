---
title: 部署 Microsoft 威脅防護所支援的服務
description: 了解可由 Microsoft 威脅防護、 其授權需求，以及部署程序整合的 Microsoft 安全性服務
keywords: 部署、 授權、 支援的服務，佈建，設定 Microsoft 威脅防護，M365，授權資格，Microsoft Defender ATP、 MDATP、 Office 365 ATP、 Azure ATP、 Microsoft Cloud App Security、 MCAS，進階威脅防護，E5、 A5、 EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b19907517f94cc8b6dbf041cccf56f1d8e232f2f
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374201"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="02816-104">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="02816-104">Deploy supported services</span></span>

<span data-ttu-id="02816-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="02816-105">**Applies to:**</span></span>
- <span data-ttu-id="02816-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="02816-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="02816-107">[Microsoft 威脅防護](microsoft-threat-protection.md)整合不同的 Microsoft 安全性服務，以提供集中式的偵測、 預防和複雜的攻擊的調查功能。</span><span class="sxs-lookup"><span data-stu-id="02816-107">[Microsoft Threat Protection](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="02816-108">本文說明支援的服務，其授權需求、 的優點與限制與部署方式您可以完全予以部署個別的一或多個服務，以及連結相關聯。</span><span class="sxs-lookup"><span data-stu-id="02816-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="02816-109">支援的服務</span><span class="sxs-lookup"><span data-stu-id="02816-109">Supported services</span></span>
<span data-ttu-id="02816-110">[Microsoft 365 E5、 E5 安全性、 A5，或 A5 安全性或有效的授權組合](prerequisites.md#licensing-requirements)提供下列存取支援的服務和賦與您在 Microsoft 365 安全性中心中使用 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="02816-110">A [Microsoft 365 E5, E5 Security, A5, or A5 Security or a valid combination of licenses](prerequisites.md#licensing-requirements) provides access to the following supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

| <span data-ttu-id="02816-111">支援的服務</span><span class="sxs-lookup"><span data-stu-id="02816-111">Supported service</span></span> | <span data-ttu-id="02816-112">說明</span><span class="sxs-lookup"><span data-stu-id="02816-112">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="02816-113">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="02816-113">Microsoft Defender ATP</span></span> | <span data-ttu-id="02816-114">內建功能強大的行為感應、 雲端分析和威脅情報周圍的端點保護套件</span><span class="sxs-lookup"><span data-stu-id="02816-114">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
| <span data-ttu-id="02816-115">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="02816-115">Office 365 ATP</span></span> | <span data-ttu-id="02816-116">進階的保護您的應用程式和 Office 365，包括電子郵件和其他協同作業工具中的資料</span><span class="sxs-lookup"><span data-stu-id="02816-116">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="02816-117">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="02816-117">Azure ATP</span></span> | <span data-ttu-id="02816-118">針對進階的威脅、 遭入侵的身分識別及惡意內部人員使用的防護措施相互關聯的 Active Directory 訊號</span><span class="sxs-lookup"><span data-stu-id="02816-118">Safeguard against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="02816-119">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="02816-119">Microsoft Cloud App Security</span></span> | <span data-ttu-id="02816-120">識別並 combats cyberthreats 跨 Microsoft 和協力廠商雲端服務</span><span class="sxs-lookup"><span data-stu-id="02816-120">Identifies and combats cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="02816-121">部署的服務和功能</span><span class="sxs-lookup"><span data-stu-id="02816-121">Deployed services and functionality</span></span>
<span data-ttu-id="02816-122">您在部署更多支援的服務時，Microsoft 威脅防護會提供較佳的可見性、 相互關聯及修復。</span><span class="sxs-lookup"><span data-stu-id="02816-122">Microsoft Threat Protection provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="02816-123">完整部署的優點</span><span class="sxs-lookup"><span data-stu-id="02816-123">Benefits of full deployment</span></span>
<span data-ttu-id="02816-124">若要取得 Microsoft 威脅防護的完整優點，我們建議部署支援的所有服務。</span><span class="sxs-lookup"><span data-stu-id="02816-124">To get the complete benefits of Microsoft Threat Protection, we recommend deploying all supported services.</span></span> <span data-ttu-id="02816-125">以下是一些完整部署的主要優點：</span><span class="sxs-lookup"><span data-stu-id="02816-125">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="02816-126">識別並相互關聯為基礎的警告與從所有可用的感應器與特定服務的分析功能事件訊號事件</span><span class="sxs-lookup"><span data-stu-id="02816-126">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="02816-127">自動化調查並修復 （空調） playbooks 套用不同的實體類型，包括裝置、 信箱及使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="02816-127">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="02816-128">更多進階的狩獵結構描述可以查詢事件及實體資料從裝置、 信箱及其他實體</span><span class="sxs-lookup"><span data-stu-id="02816-128">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="02816-129">有限的部署案例</span><span class="sxs-lookup"><span data-stu-id="02816-129">Limited deployment scenarios</span></span>
<span data-ttu-id="02816-130">每個支援的服務，您將部署提供極豐富的未經處理信號，以及相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="02816-130">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="02816-131">雖然有限的部署不會造成 Microsoft 威脅防護功能關閉，會影響其能夠跨端點、 應用程式、 資料和身分識別提供完整的可見性。</span><span class="sxs-lookup"><span data-stu-id="02816-131">While limited deployment doesn’t cause Microsoft Threat Protection functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="02816-132">在此同時，任何修復功能僅適用於您已部署的服務可管理的實體。</span><span class="sxs-lookup"><span data-stu-id="02816-132">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="02816-133">下表列出每個支援的服務如何提供額外的資料，相互關聯的資料，並更好的補救和回應功能，以取得額外的深入解析的機會。</span><span class="sxs-lookup"><span data-stu-id="02816-133">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="02816-134">服務</span><span class="sxs-lookup"><span data-stu-id="02816-134">Service</span></span> | <span data-ttu-id="02816-135">資料 （訊號 & 相互關聯的資訊）</span><span class="sxs-lookup"><span data-stu-id="02816-135">Data (signals & correlated info)</span></span> | <span data-ttu-id="02816-136">修復 & 回應範圍</span><span class="sxs-lookup"><span data-stu-id="02816-136">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="02816-137">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="02816-137">Microsoft Defender ATP</span></span> | <span data-ttu-id="02816-138">-端點狀態和未經處理的事件</span><span class="sxs-lookup"><span data-stu-id="02816-138">- Endpoint states and raw events</span></span><br /><span data-ttu-id="02816-139">-端點偵測及警示，包括防毒軟體，EDR，來進行攻擊縮減</span><span class="sxs-lookup"><span data-stu-id="02816-139">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="02816-140">-檔案和觀察到的端點上其他實體資訊</span><span class="sxs-lookup"><span data-stu-id="02816-140">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="02816-141">端點</span><span class="sxs-lookup"><span data-stu-id="02816-141">Endpoints</span></span> |
| <span data-ttu-id="02816-142">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="02816-142">Office 365 ATP</span></span> | <span data-ttu-id="02816-143">對郵件的信箱狀態和未經處理的事件</span><span class="sxs-lookup"><span data-stu-id="02816-143">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="02816-144">-電子郵件附件，並將連結偵測</span><span class="sxs-lookup"><span data-stu-id="02816-144">- Email, attachment, and link detections</span></span> | <span data-ttu-id="02816-145">信箱</span><span class="sxs-lookup"><span data-stu-id="02816-145">- Mailboxes</span></span><br /><span data-ttu-id="02816-146">-Office 365 帳戶</span><span class="sxs-lookup"><span data-stu-id="02816-146">- Office 365 accounts</span></span> |
| <span data-ttu-id="02816-147">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="02816-147">Azure ATP</span></span> | <span data-ttu-id="02816-148">-Active Directory 訊號，包括驗證事件</span><span class="sxs-lookup"><span data-stu-id="02816-148">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="02816-149">-身分識別相關的行為偵測</span><span class="sxs-lookup"><span data-stu-id="02816-149">- Identity-related behavioral detections</span></span> | <span data-ttu-id="02816-150">身分識別</span><span class="sxs-lookup"><span data-stu-id="02816-150">Identities</span></span> |
| <span data-ttu-id="02816-151">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="02816-151">Microsoft Cloud App Security</span></span> | <span data-ttu-id="02816-152">-偵測的 unsanctioned 的雲端應用程式 & 服務 （陰影 IT）</span><span class="sxs-lookup"><span data-stu-id="02816-152">- Detection of unsanctioned cloud apps & services (shadow IT)</span></span><br /><span data-ttu-id="02816-153">-洩露到雲端的應用程式的資料</span><span class="sxs-lookup"><span data-stu-id="02816-153">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="02816-154">-威脅活動相關聯的雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="02816-154">- Threat activity associated cloud apps</span></span> | <span data-ttu-id="02816-155">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="02816-155">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="02816-156">部署服務</span><span class="sxs-lookup"><span data-stu-id="02816-156">Deploy the services</span></span>
<span data-ttu-id="02816-157">部署每個服務通常需要對您的租用戶與某些初始設定佈建。</span><span class="sxs-lookup"><span data-stu-id="02816-157">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="02816-158">請參閱下表以了解每個這些服務的部署方式。</span><span class="sxs-lookup"><span data-stu-id="02816-158">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="02816-159">服務</span><span class="sxs-lookup"><span data-stu-id="02816-159">Service</span></span> | <span data-ttu-id="02816-160">佈建的指示</span><span class="sxs-lookup"><span data-stu-id="02816-160">Provisioning instructions</span></span> | <span data-ttu-id="02816-161">初始設定</span><span class="sxs-lookup"><span data-stu-id="02816-161">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="02816-162">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="02816-162">Microsoft Defender ATP</span></span> | [<span data-ttu-id="02816-163">驗證授權佈建和設定的設定完成 Microsoft Defender atp</span><span class="sxs-lookup"><span data-stu-id="02816-163">Validate licensing provisioning and complete set up for Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/licensing) | <span data-ttu-id="02816-164">*請參閱佈建指示*</span><span class="sxs-lookup"><span data-stu-id="02816-164">*See provisioning instructions*</span></span> |
| <span data-ttu-id="02816-165">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="02816-165">Office 365 ATP</span></span> | <span data-ttu-id="02816-166">*無使用 Office 365 佈建*</span><span class="sxs-lookup"><span data-stu-id="02816-166">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="02816-167">設定 ATP 原則</span><span class="sxs-lookup"><span data-stu-id="02816-167">Configure ATP policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="02816-168">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="02816-168">Azure ATP</span></span> | [<span data-ttu-id="02816-169">快速入門： 建立您的 Azure ATP 執行個體</span><span class="sxs-lookup"><span data-stu-id="02816-169">Quickstart: Create your Azure ATP instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="02816-170">*請參閱佈建指示*</span><span class="sxs-lookup"><span data-stu-id="02816-170">*See provisioning instructions*</span></span> |
| <span data-ttu-id="02816-171">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="02816-171">Microsoft Cloud App Security</span></span> | <span data-ttu-id="02816-172">*無*</span><span class="sxs-lookup"><span data-stu-id="02816-172">*None*</span></span> | [<span data-ttu-id="02816-173">快速入門： 開始使用 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="02816-173">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="02816-174">一旦您已部署支援的服務，[開啟 [Microsoft Threat Protection](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="02816-174">Once you’ve deployed the supported services, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="02816-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="02816-175">Related topics</span></span>

- [<span data-ttu-id="02816-176">Microsoft 威脅防護概觀</span><span class="sxs-lookup"><span data-stu-id="02816-176">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="02816-177">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="02816-177">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="02816-178">Microsoft Defender ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="02816-178">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="02816-179">Office 365 ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="02816-179">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="02816-180">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="02816-180">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="02816-181">Azure ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="02816-181">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
