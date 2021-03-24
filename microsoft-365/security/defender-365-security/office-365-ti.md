---
title: 威脅調查 & 回應功能-Microsoft Defender for Office 365 方案2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解 Microsoft Defender for Office 365 方案中的威脅調查和回應功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9d61da5a12882bef3ffee715bffb37ec96a18fd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058863"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="96a35-103">威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="96a35-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="96a35-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="96a35-104">**Applies To**</span></span>
- [<span data-ttu-id="96a35-105">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="96a35-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="96a35-106">[Microsoft Defender For Office 365](defender-for-office-365.md)中的威脅調查和回應功能可協助安全性分析程式和系統管理員保護組織的 microsoft 365 for business 使用者：</span><span class="sxs-lookup"><span data-stu-id="96a35-106">Threat investigation and response capabilities in [Microsoft Defender for Office 365](defender-for-office-365.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="96a35-107">讓您輕鬆識別、監視和瞭解 cyberattacks</span><span class="sxs-lookup"><span data-stu-id="96a35-107">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="96a35-108">協助快速解決 Exchange Online 中的威脅、SharePoint 線上、商務和 Microsoft 小組 OneDrive</span><span class="sxs-lookup"><span data-stu-id="96a35-108">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="96a35-109">提供真知灼見和知識以協助安全性作業，以防止 cyberattacks 對其組織</span><span class="sxs-lookup"><span data-stu-id="96a35-109">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="96a35-110">針對重要的電子郵件威脅，採用[Office 365 中的自動化調查和回應](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="96a35-110">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="96a35-111">威脅調查和回應功能可讓您深入瞭解安全性 & 規範中心提供的威脅和相關回應動作。</span><span class="sxs-lookup"><span data-stu-id="96a35-111">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Security & Compliance Center.</span></span> <span data-ttu-id="96a35-112">這些洞察力可協助貴組織的安全小組保護使用者免受電子郵件或檔案型的攻擊。</span><span class="sxs-lookup"><span data-stu-id="96a35-112">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="96a35-113">這些功能可協助監控信號，並從多個來源收集資料，例如使用者活動、驗證、電子郵件、受損的電腦及安全性事件。</span><span class="sxs-lookup"><span data-stu-id="96a35-113">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="96a35-114">業務決策者和您的安全作業小組可以使用此資訊來瞭解及回應組織的威脅，並保護您的智慧財產權。</span><span class="sxs-lookup"><span data-stu-id="96a35-114">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="96a35-115">熟悉威脅調查和回應工具</span><span class="sxs-lookup"><span data-stu-id="96a35-115">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="96a35-116">安全性 & 規範中心的威脅調查和回應功能，做為一組工具和回應工作流程，包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="96a35-116">Threat investigation and response capabilities surface in the Security & Compliance Center, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="96a35-117">威脅儀表板</span><span class="sxs-lookup"><span data-stu-id="96a35-117">Threat dashboard</span></span>](#threat-dashboard)
- [<span data-ttu-id="96a35-118">總管</span><span class="sxs-lookup"><span data-stu-id="96a35-118">Explorer</span></span>](#threat-explorer)
- [<span data-ttu-id="96a35-119">事件</span><span class="sxs-lookup"><span data-stu-id="96a35-119">Incidents</span></span>](#incidents)
- [<span data-ttu-id="96a35-120">攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="96a35-120">Attack Simulator</span></span>](#attack-simulator)
- [<span data-ttu-id="96a35-121">自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="96a35-121">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a><span data-ttu-id="96a35-122">威脅儀表板</span><span class="sxs-lookup"><span data-stu-id="96a35-122">Threat dashboard</span></span>

<span data-ttu-id="96a35-123">使用 [威脅儀表板] (這也稱為 [安全性儀表板](security-dashboard.md)) 以快速查看已解決的威脅，以及向業務決策決策者報告 Microsoft 365 服務如何保護您的業務的視覺方式。</span><span class="sxs-lookup"><span data-stu-id="96a35-123">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Microsoft 365 services are securing your business.</span></span>

![威脅儀表板](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

<span data-ttu-id="96a35-125">若要查看和使用此儀表板，請在安全性 & 合規性中心，移至 [ **威脅管理**] \> **儀表板**。</span><span class="sxs-lookup"><span data-stu-id="96a35-125">To view and use this dashboard, in the Security & Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>

### <a name="threat-explorer"></a><span data-ttu-id="96a35-126">威脅總管</span><span class="sxs-lookup"><span data-stu-id="96a35-126">Threat Explorer</span></span>

<span data-ttu-id="96a35-127">使用 [威脅瀏覽器 (和即時偵測) ](threat-explorer.md) 來分析威脅、查看一段時間的攻擊量，以及依威脅系列、攻擊者基礎結構等來分析資料。</span><span class="sxs-lookup"><span data-stu-id="96a35-127">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="96a35-128">威脅瀏覽器 (也稱為 Explorer) 是任何安全分析員調查工作流程的開始位置。</span><span class="sxs-lookup"><span data-stu-id="96a35-128">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![威脅總管](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="96a35-130">若要查看和使用此報告，請在安全性 & 規範中心內，移至 [ **威脅管理** \> **瀏覽器**]。</span><span class="sxs-lookup"><span data-stu-id="96a35-130">To view and use this report, in the Security & Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="96a35-131">事件</span><span class="sxs-lookup"><span data-stu-id="96a35-131">Incidents</span></span>

<span data-ttu-id="96a35-132">使用事件清單 (這也稱為「調查」) ，以查看航班安全性事件的清單。</span><span class="sxs-lookup"><span data-stu-id="96a35-132">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="96a35-133">事件用於追蹤可疑的電子郵件訊息，以及進行進一步調查和修正等威脅。</span><span class="sxs-lookup"><span data-stu-id="96a35-133">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![Office 365 中的目前威脅事件清單](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="96a35-135">若要查看組織目前的事件清單，請在安全性 & 合規性中心，移至 **威脅管理** \> **回顧** \> **事件**。</span><span class="sxs-lookup"><span data-stu-id="96a35-135">To view the list of current incidents for your organization, in the Security & Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>

![在 [安全性 & 規範中心] 中，選擇 [威脅管理 \> 檢查]](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="96a35-137">攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="96a35-137">Attack Simulator</span></span>

<span data-ttu-id="96a35-138">使用攻擊模擬器，在您的組織中設定及執行實際的 cyberattacks，並在實際 cyberattack 影響您的公司之前識別有漏洞的人員。</span><span class="sxs-lookup"><span data-stu-id="96a35-138">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="96a35-139">若要深入瞭解，請參閱 [Office 365 中的攻擊模擬器](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="96a35-139">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="96a35-140">自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="96a35-140">Automated investigation and response</span></span>

<span data-ttu-id="96a35-141">使用自動調查和回應 (AIR) 功能，以儲存組織中威脅帶來的時間與精力，以關聯內容、裝置和人員。</span><span class="sxs-lookup"><span data-stu-id="96a35-141">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="96a35-142">每當觸發特定警示時，或是當您的安全性作業小組開始時，就可以開始空氣處理常式。</span><span class="sxs-lookup"><span data-stu-id="96a35-142">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="96a35-143">若要深入瞭解，請參閱 [Office 365 中的自動化調查和回應](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="96a35-143">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="96a35-144">威脅智慧小元件</span><span class="sxs-lookup"><span data-stu-id="96a35-144">Threat intelligence widgets</span></span>

<span data-ttu-id="96a35-145">在 Microsoft Defender for Office 365 方案2中，安全分析員可以查看已知威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="96a35-145">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="96a35-146">這有助於判斷是否有其他預防措施/步驟可讓使用者保持安全。</span><span class="sxs-lookup"><span data-stu-id="96a35-146">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![顯示最近威脅相關資訊的安全性趨勢](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="96a35-148">如何取得這些功能？</span><span class="sxs-lookup"><span data-stu-id="96a35-148">How do we get these capabilities?</span></span>

<span data-ttu-id="96a35-149">Microsoft 365 威脅調查和回應功能包含在 Microsoft Defender for Office 365 方案2中，該方案包含在企業版 E5 中，或在某些訂閱中為附加元件。</span><span class="sxs-lookup"><span data-stu-id="96a35-149">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="96a35-150">若要深入瞭解，請參閱 [Office 365 的 Defender （方案1）和方案 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。</span><span class="sxs-lookup"><span data-stu-id="96a35-150">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="96a35-151">必要角色和權限</span><span class="sxs-lookup"><span data-stu-id="96a35-151">Required roles and permissions</span></span>

<span data-ttu-id="96a35-152">Microsoft Defender for Office 365 使用以角色為基礎的存取控制。</span><span class="sxs-lookup"><span data-stu-id="96a35-152">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="96a35-153">許可權是透過 Azure Active Directory、Microsoft 365 系統管理中心或安全性 & 規範中心中的特定角色進行指派。</span><span class="sxs-lookup"><span data-stu-id="96a35-153">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Security & Compliance Center.</span></span>

> [!TIP]
> <span data-ttu-id="96a35-154">雖然在安全性 & 規範中心可以指派某些角色（如安全性管理員），但是請改為考慮使用 Microsoft 365 系統管理中心或 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="96a35-154">Although some roles, such as Security Administrator, can be assigned in the Security & Compliance Center, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="96a35-155">如需角色、角色群組和許可權的相關資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="96a35-155">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="96a35-156">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="96a35-156">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
>
> - [<span data-ttu-id="96a35-157">Azure Active Directory 中的系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="96a35-157">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|<span data-ttu-id="96a35-158">活動</span><span class="sxs-lookup"><span data-stu-id="96a35-158">Activity</span></span>|<span data-ttu-id="96a35-159">角色及權限</span><span class="sxs-lookup"><span data-stu-id="96a35-159">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="96a35-160">使用威脅儀表板 (或新的 [安全性儀表板](security-dashboard.md)) </span><span class="sxs-lookup"><span data-stu-id="96a35-160">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span> <p> <span data-ttu-id="96a35-161">查看最近或目前威脅的相關資訊</span><span class="sxs-lookup"><span data-stu-id="96a35-161">View information about recent or current threats</span></span>|<span data-ttu-id="96a35-162">下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="96a35-162">One of the following:</span></span> <ul><li><span data-ttu-id="96a35-163">**全域管理員**</span><span class="sxs-lookup"><span data-stu-id="96a35-163">**Global Administrator**</span></span></li><li><span data-ttu-id="96a35-164">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="96a35-164">**Security Administrator**</span></span></li><li><span data-ttu-id="96a35-165">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="96a35-165">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="96a35-166">您可以在 Azure Active Directory (<https://portal.azure.com>) 或 Microsoft 365 系統管理中心 () 中指派這些角色 <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="96a35-166">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="96a35-167">使用 [威脅瀏覽器 (和即時偵測) ](threat-explorer.md) 來分析威脅</span><span class="sxs-lookup"><span data-stu-id="96a35-167">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="96a35-168">下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="96a35-168">One of the following:</span></span> <ul><li><span data-ttu-id="96a35-169">**全域管理員**</span><span class="sxs-lookup"><span data-stu-id="96a35-169">**Global Administrator**</span></span></li><li><span data-ttu-id="96a35-170">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="96a35-170">**Security Administrator**</span></span></li><li><span data-ttu-id="96a35-171">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="96a35-171">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="96a35-172">您可以在 Azure Active Directory (<https://portal.azure.com>) 或 Microsoft 365 系統管理中心 () 中指派這些角色 <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="96a35-172">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="96a35-173">View 事件 (也稱為「調查」) </span><span class="sxs-lookup"><span data-stu-id="96a35-173">View Incidents (also referred to as Investigations)</span></span> <p> <span data-ttu-id="96a35-174">將電子郵件新增至事件</span><span class="sxs-lookup"><span data-stu-id="96a35-174">Add email messages to an incident</span></span>|<span data-ttu-id="96a35-175">下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="96a35-175">One of the following:</span></span> <ul><li><span data-ttu-id="96a35-176">**全域管理員**</span><span class="sxs-lookup"><span data-stu-id="96a35-176">**Global Administrator**</span></span></li><li><span data-ttu-id="96a35-177">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="96a35-177">**Security Administrator**</span></span></li><li><span data-ttu-id="96a35-178">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="96a35-178">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="96a35-179">您可以在 Azure Active Directory (<https://portal.azure.com>) 或 Microsoft 365 系統管理中心 () 中指派這些角色 <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="96a35-179">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="96a35-180">觸發事件中的電子郵件動作</span><span class="sxs-lookup"><span data-stu-id="96a35-180">Trigger email actions in an incident</span></span> <p> <span data-ttu-id="96a35-181">尋找和刪除可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="96a35-181">Find and delete suspicious email messages</span></span>|<span data-ttu-id="96a35-182">下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="96a35-182">One of the following:</span></span> <ul><li><span data-ttu-id="96a35-183">**全域管理員**</span><span class="sxs-lookup"><span data-stu-id="96a35-183">**Global Administrator**</span></span></li><li><span data-ttu-id="96a35-184">**安全性管理員** 和 **搜尋及清除** 角色</span><span class="sxs-lookup"><span data-stu-id="96a35-184">**Security Administrator** plus the **Search and Purge** role</span></span></li></ul> <p> <span data-ttu-id="96a35-185">**全域管理員** 及 **安全性管理員** 角色可以在 Azure Active Directory (<https://portal.azure.com>) 或 Microsoft 365 系統管理中心 () 中指派 <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="96a35-185">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="96a35-186">您必須在安全性 & 規範中心 () 中指派 **搜尋和清除** 角色 <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="96a35-186">The **Search and Purge** role must be assigned in the Security & Compliance Center (<https://protection.office.com>).</span></span>|
|<span data-ttu-id="96a35-187">整合 Microsoft Defender for Office 365 方案2與 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="96a35-187">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span>  <p> <span data-ttu-id="96a35-188">整合 Microsoft Defender for Office 365 Plan 2 與 SIEM server</span><span class="sxs-lookup"><span data-stu-id="96a35-188">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="96a35-189">在任何 Azure Active Directory (中所指派的 **全域系統管理員** 或 **安全性管理員** 角色 <https://portal.azure.com>) 或 Microsoft 365 系統管理中心 (<https://admin.microsoft.com>) 。</span><span class="sxs-lookup"><span data-stu-id="96a35-189">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="96a35-190">--- **加** --- </span><span class="sxs-lookup"><span data-stu-id="96a35-190">--- **plus** --- </span></span><p> <span data-ttu-id="96a35-191">在其他應用程式中指派的適當角色 (例如 [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) 或您的 SIEM server) 。</span><span class="sxs-lookup"><span data-stu-id="96a35-191">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="96a35-192">後續步驟</span><span class="sxs-lookup"><span data-stu-id="96a35-192">Next steps</span></span>

- [<span data-ttu-id="96a35-193">深入瞭解威脅追蹤程式-新增及值得注意的事項</span><span class="sxs-lookup"><span data-stu-id="96a35-193">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="96a35-194">尋找並調查 (Office 365 威脅調查和回應中傳遞的惡意電子郵件) </span><span class="sxs-lookup"><span data-stu-id="96a35-194">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="96a35-195">整合 Office 365 威脅調查，並使用 Microsoft Defender for Endpoint 進行回應</span><span class="sxs-lookup"><span data-stu-id="96a35-195">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-mde.md)

- [<span data-ttu-id="96a35-196">深入瞭解攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="96a35-196">Learn about Attack Simulator</span></span>](attack-simulator.md)