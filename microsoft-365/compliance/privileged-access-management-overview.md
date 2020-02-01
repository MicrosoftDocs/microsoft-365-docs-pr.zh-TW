---
title: Office 365 的 Privileged Access Management
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 若要深入了解權限使用本主題存取 Office 365 中的管理
ms.openlocfilehash: 0c9d8ba22f57c7f6a576f1995e8df92be7478073
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597730"
---
# <a name="privileged-access-management-in-office-365"></a><span data-ttu-id="66f83-103">Office 365 的 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="66f83-103">Privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66f83-104">本主題涵蓋功能目前僅適用於 Office 365 E5 和進階合規性 Sku 的部署和設定指導。</span><span class="sxs-lookup"><span data-stu-id="66f83-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="66f83-105">特殊權限存取管理可讓 Office 365 中的特殊權限的系統管理工作更精細的存取控制。</span><span class="sxs-lookup"><span data-stu-id="66f83-105">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="66f83-106">它可以協助保護您的組織使用現有的特殊權限的系統管理員帳戶具有常設存取權的敏感資料或存取重要的組態設定的外洩。</span><span class="sxs-lookup"><span data-stu-id="66f83-106">It can help protect your organization from breaches that use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="66f83-107">特殊權限存取管理需要使用者要求剛時間存取權完成提升權限和特殊權限的工作，透過高範圍及時間包住核准工作流程。</span><span class="sxs-lookup"><span data-stu-id="66f83-107">Privileged access management requires users to request just-in-time access to complete elevated and privileged tasks through a highly scoped and time-bounded approval workflow.</span></span> <span data-ttu-id="66f83-108">這可以讓使用者剛充份-存取執行工作的而不致曝露機密資料或重要的組態設定。</span><span class="sxs-lookup"><span data-stu-id="66f83-108">This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings.</span></span> <span data-ttu-id="66f83-109">啟用 Office 365 中的特殊權限的存取管理可讓您的組織來操作以零常設權限，並提供一層的防禦常設系統管理存取權的弱點。</span><span class="sxs-lookup"><span data-stu-id="66f83-109">Enabling privileged access management in Office 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

<span data-ttu-id="66f83-110">整合式的客戶加密箱和特殊權限的存取管理工作流程的快速概觀，請參閱此[客戶加密箱和 Office 365 影片中的特殊權限的存取管理](https://go.microsoft.com/fwlink/?linkid=2066800)。</span><span class="sxs-lookup"><span data-stu-id="66f83-110">For a quick overview of the integrated Customer Lockbox and privileged access management workflow, see this [Customer Lockbox and privileged access management in Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="66f83-111">保護層級</span><span class="sxs-lookup"><span data-stu-id="66f83-111">Layers of protection</span></span>

<span data-ttu-id="66f83-112">特殊權限存取管理輔助其他資料與存取權的功能保護 Office 365 安全性架構內。</span><span class="sxs-lookup"><span data-stu-id="66f83-112">Privileged access management complements other data and access feature protections within the Office 365 security architecture.</span></span> <span data-ttu-id="66f83-113">包括安全性整合及分層方法的一部分的特殊權限的存取管理提供一種安全性模型，將最大化保護敏感資訊和 Office 365 組態設定。</span><span class="sxs-lookup"><span data-stu-id="66f83-113">Including privileged access management as part of an integrated and layered approach to security provides a security model that maximizes protection of sensitive information and Office 365 configuration settings.</span></span> <span data-ttu-id="66f83-114">此圖中，與原生 Office 365 資料加密和 Office 365 服務的角色型存取控制安全性模型提供的保護特殊權限的存取管理建置所示。</span><span class="sxs-lookup"><span data-stu-id="66f83-114">As shown in the diagram, privileged access management builds on the protection provided with native encryption of Office 365 data and the role-based access control security model of Office 365 services.</span></span> <span data-ttu-id="66f83-115">[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)搭配使用時，這兩項功能會提供與剛-階段存取在不同範圍的存取控制。</span><span class="sxs-lookup"><span data-stu-id="66f83-115">When used with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![在 Office 365 中的分層的保護](media/pam-layered-protection.png)

<span data-ttu-id="66f83-117">特殊權限存取管理 Office 365 中的定義及在**任務**層級設定範圍，而 Azure AD Privileged Identity Management 能夠執行多個任務套用**角色**層級的保護。</span><span class="sxs-lookup"><span data-stu-id="66f83-117">Privileged access management in Office 365 is defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.</span></span> <span data-ttu-id="66f83-118">Azure AD 有權限身分識別管理主要允許管理 AD 角色和角色群組的存取，而特殊權限存取 Office 365 中的管理適用於僅在任務層級。</span><span class="sxs-lookup"><span data-stu-id="66f83-118">Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 applies only at the task level.</span></span>

- <span data-ttu-id="66f83-119">**啟用特殊權限存取 Office 365 中的管理已使用 Azure AD Privileged Identity Management 時：** 在 Office 365 中新增特殊權限的存取管理提供另一個的細微層級的特殊權限存取 Office 365 的資料保護和稽核功能。</span><span class="sxs-lookup"><span data-stu-id="66f83-119">**Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.</span></span>

- <span data-ttu-id="66f83-120">**啟用 Azure AD Privileged Identity Management 時已經在使用特殊權限存取管理 Office 365 中：** 將 Azure AD Privileged Identity Management 新增至權限存取管理 Office 365 中的可以延伸至主要由使用者角色或身分識別所定義的 Office 365 外部資料的特殊權限的存取。</span><span class="sxs-lookup"><span data-stu-id="66f83-120">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by user roles or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="66f83-121">特殊權限的存取管理架構和處理程序流程</span><span class="sxs-lookup"><span data-stu-id="66f83-121">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="66f83-122">下列程序流程的每個大綱架構的特殊權限的存取和 Office 365 substrate、 與 Office 365 稽核]，Exchange 管理 runspace 的互動方式。</span><span class="sxs-lookup"><span data-stu-id="66f83-122">Each of the following process flows outline the architecture of privileged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configure-a-privileged-access-policy"></a><span data-ttu-id="66f83-123">步驟 1： 設定特殊權限的存取原則</span><span class="sxs-lookup"><span data-stu-id="66f83-123">Step 1: Configure a privileged access policy</span></span>

<span data-ttu-id="66f83-124">當您使用[Microsoft 365 系統管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell 設定特殊權限的存取原則時，並定義原則的特殊權限存取功能程序和 Office 365 substrate 中的原則屬性。</span><span class="sxs-lookup"><span data-stu-id="66f83-124">When you configure a privileged access policy with the [Microsoft 365 admin center](https://admin.microsoft.com) or the Exchange Management PowerShell, you define the policy and the privileged access feature processes and the policy attributes in the Office 365 substrate.</span></span> <span data-ttu-id="66f83-125">活動已登入 Office 365 安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="66f83-125">The activities are logged in the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="66f83-126">原則現已啟用，並準備好處理傳入要求核准。</span><span class="sxs-lookup"><span data-stu-id="66f83-126">The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![步驟 1： 建立原則](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="66f83-128">步驟 2： 存取要求</span><span class="sxs-lookup"><span data-stu-id="66f83-128">Step 2: Access request</span></span>

<span data-ttu-id="66f83-129">在[Microsoft 365 系統管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell，使用者可以要求存取較高權限或特殊權限的工作。</span><span class="sxs-lookup"><span data-stu-id="66f83-129">In the [Microsoft 365 admin center](https://admin.microsoft.com) or with the Exchange Management PowerShell, users can request access to elevated or privileged tasks.</span></span> <span data-ttu-id="66f83-130">特殊權限的存取功能會將要求傳送至已設定特殊權限存取原則和記錄的 Office 365 安全性與合規性中心的記錄檔中的活動的處理 Office 365 substrate。</span><span class="sxs-lookup"><span data-stu-id="66f83-130">The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the Activity in the Office 365 Security and Compliance Center logs.</span></span>

![步驟 2： 存取要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="66f83-132">步驟 3： 存取權核准</span><span class="sxs-lookup"><span data-stu-id="66f83-132">Step 3: Access approval</span></span>

<span data-ttu-id="66f83-133">核准要求就會產生和擱置的要求通知電子郵件傳送至核准者。</span><span class="sxs-lookup"><span data-stu-id="66f83-133">An approval request is generated and the pending request notification is emailed to approvers.</span></span> <span data-ttu-id="66f83-134">如果核准，特殊權限的存取要求處理核准為且工作已完成。</span><span class="sxs-lookup"><span data-stu-id="66f83-134">If approved, the privileged access request is processed as an approval and the task is ready to be completed.</span></span> <span data-ttu-id="66f83-135">如果拒絕時，會封鎖工作並沒有存取權授與給要求者。</span><span class="sxs-lookup"><span data-stu-id="66f83-135">If denied, the task is blocked and no access is granted to the requestor.</span></span> <span data-ttu-id="66f83-136">要求者要求核准或拒絕透過電子郵件訊息的通知。</span><span class="sxs-lookup"><span data-stu-id="66f83-136">The requestor is notified of the request approval or denial via email message.</span></span>

![步驟 3： 存取權核准](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="66f83-138">步驟 4： 存取處理</span><span class="sxs-lookup"><span data-stu-id="66f83-138">Step 4: Access processing</span></span>

<span data-ttu-id="66f83-139">核准要求，會由 Exchange 管理 runspace 處理工作。</span><span class="sxs-lookup"><span data-stu-id="66f83-139">For an approved request, the task is processed by the Exchange Management runspace.</span></span> <span data-ttu-id="66f83-140">核准是針對特殊權限的存取原則檢查，且由 Office 365 substrate 處理。</span><span class="sxs-lookup"><span data-stu-id="66f83-140">The approval is checked against the privileged access policy and processed by the Office 365 substrate.</span></span> <span data-ttu-id="66f83-141">任務的所有活動會都記錄在 Office 365 安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="66f83-141">All activity for the task is logged in the Office 365 Security and Compliance Center.</span></span>

![步驟 4： 存取處理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="66f83-143">常見問題集</span><span class="sxs-lookup"><span data-stu-id="66f83-143">Frequently asked questions</span></span>

### <a name="what-skus-can-use-privileged-access-in-office-365"></a><span data-ttu-id="66f83-144">Sku 可以使用特殊權限存取 Office 365 中？</span><span class="sxs-lookup"><span data-stu-id="66f83-144">What SKUs can use privileged access in Office 365?</span></span>
<span data-ttu-id="66f83-145">特殊權限存取管理功能可供客戶使用 Office 365 E5 和進階合規性 Sku。</span><span class="sxs-lookup"><span data-stu-id="66f83-145">Privileged access management is available for customers with Office 365 E5 and Advanced Compliance SKUs.</span></span>

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a><span data-ttu-id="66f83-146">特殊權限的存取時支援超過 Exchange 的 Office 365 工作負載？</span><span class="sxs-lookup"><span data-stu-id="66f83-146">When will privileged access support Office 365 workloads beyond Exchange?</span></span>
<span data-ttu-id="66f83-147">特殊權限存取管理則可在其他 Office 365 工作負載推出。</span><span class="sxs-lookup"><span data-stu-id="66f83-147">Privileged access management will be available in other Office 365 workloads soon.</span></span> <span data-ttu-id="66f83-148">[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)如需詳細資訊，請造訪。</span><span class="sxs-lookup"><span data-stu-id="66f83-148">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) for more details.</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a><span data-ttu-id="66f83-149">我的組織需要 30 個以上的特殊權限的存取原則，會增加此限制？</span><span class="sxs-lookup"><span data-stu-id="66f83-149">My organization needs more than 30 privileged access policies, will this limit be increased?</span></span>
<span data-ttu-id="66f83-150">是，引發 30 的特殊權限的存取原則，每個 Office 365 組織的目前限制是功能藍圖。</span><span class="sxs-lookup"><span data-stu-id="66f83-150">Yes, raising the current limit of 30 privileged access policies per Office 365 organization is on the feature roadmap.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="66f83-151">是否需要是全域系統管理員來管理 Office 365 中的特殊權限的存取？</span><span class="sxs-lookup"><span data-stu-id="66f83-151">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>
<span data-ttu-id="66f83-152">否，您需要 Exchange 角色管理 」 角色指派給管理特殊權限的存取 Office 365 中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="66f83-152">No, you need the Exchange Role Management role assigned to accounts that manage privileged access in Office 365.</span></span> <span data-ttu-id="66f83-153">如果您不想要設定為獨立的帳戶權限的角色管理角色，全域系統管理員角色此角色包含預設，並可以管理特殊權限的存取。</span><span class="sxs-lookup"><span data-stu-id="66f83-153">If you don’t want to configure the Role Management role as a stand-alone account permission, the Global Administrator role includes this role by default and can manage privileged access.</span></span> <span data-ttu-id="66f83-154">核准者群組中包含的使用者不需要是全域系統管理員或具有 「 角色管理角色指派進行審核及核准要求。</span><span class="sxs-lookup"><span data-stu-id="66f83-154">Users included in an approvers’ group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests.</span></span>

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a><span data-ttu-id="66f83-155">如何為客戶加密箱與相關的 Office 365 中的特殊權限的存取管理？</span><span class="sxs-lookup"><span data-stu-id="66f83-155">How is privileged access management in Office 365 related to Customer Lockbox?</span></span>
<span data-ttu-id="66f83-156">當 Microsoft 存取資料時， [Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)可讓組織的存取控制層級。</span><span class="sxs-lookup"><span data-stu-id="66f83-156">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations when Microsoft accesses data.</span></span> <span data-ttu-id="66f83-157">特殊權限存取 Office 365 中的管理可讓更精細的存取控制組織內部的 Office 365 特殊權限的所有工作。</span><span class="sxs-lookup"><span data-stu-id="66f83-157">Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="66f83-158">準備好要開始了嗎？</span><span class="sxs-lookup"><span data-stu-id="66f83-158">Ready to get started?</span></span>

<span data-ttu-id="66f83-159">啟動 [[設定您的組織特殊權限存取管理](privileged-access-management-configuration.md)]。</span><span class="sxs-lookup"><span data-stu-id="66f83-159">Start [configuring your organization for privileged access management](privileged-access-management-configuration.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="66f83-160">深入了解</span><span class="sxs-lookup"><span data-stu-id="66f83-160">Learn more</span></span>

[<span data-ttu-id="66f83-161">互動式指南： 監視和控制管理員 」 工作與特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="66f83-161">Interactive guide: Monitor and control administrator tasks with privileged access management</span></span>](https://content.cloudguides.com/guides/Privileged%20Access%20Management)