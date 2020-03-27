---
title: 案例研究-Contoso 會快速設定冒犯性語言原則
description: Contoso 的案例研究，以及如何快速設定通訊相容性原則，以監視 Microsoft 團隊和 Exchange Online 通訊中的冒犯性語言
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 6b5ce3b9ca738ddf94edbb035daeb730f5e3f96a
ms.sourcegitcommit: 242f051c4cf3683f8c1a5da20ceca81bde212cfc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982355"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy"></a><span data-ttu-id="24a7c-103">案例研究-Contoso 會快速設定冒犯性語言原則</span><span class="sxs-lookup"><span data-stu-id="24a7c-103">Case study - Contoso quickly configures an offensive language policy</span></span>

<span data-ttu-id="24a7c-104">Microsoft 365 中的通訊法規遵從性，可協助您針對組織中的不適當郵件偵測、捕獲和採取補救措施，以盡可能降低通訊風險。</span><span class="sxs-lookup"><span data-stu-id="24a7c-104">Communication compliance in Microsoft 365 helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="24a7c-105">預先定義和自訂原則可讓您掃描內部及外部通訊的原則符合，以供指定的檢閱者檢查。</span><span class="sxs-lookup"><span data-stu-id="24a7c-105">Pre-defined and custom policies allow you to scan internal and external communications for policy matches so they can be examined by designated reviewers.</span></span> <span data-ttu-id="24a7c-106">檢閱者可以調查組織中已掃描的電子郵件、Microsoft 小組或協力廠商通訊，並採取適當的修正動作，以確保它們符合您組織的郵件標準。</span><span class="sxs-lookup"><span data-stu-id="24a7c-106">Reviewers can investigate scanned email, Microsoft Teams, or third-party communications in your organization and take appropriate remediation actions to make sure they're compliant with your organization's message standards.</span></span>

<span data-ttu-id="24a7c-107">Contoso Corporation 是一種虛構的組織，需要快速設定用來監視冒犯性語言的原則。</span><span class="sxs-lookup"><span data-stu-id="24a7c-107">The Contoso Corporation is a fictional organization that needs to quickly configure a policy to monitor for offensive language.</span></span> <span data-ttu-id="24a7c-108">他們一直使用 Microsoft 365，主要是針對員工的電子郵件和 Microsoft 小組支援，但有新的需求可強制實施公司原則，避免工作場所騷擾。</span><span class="sxs-lookup"><span data-stu-id="24a7c-108">They have been using Microsoft 365 primarily for email and Microsoft Teams support for their employees but have new requirements to enforce company policy around workplace harassment.</span></span> <span data-ttu-id="24a7c-109">Contoso IT 系統管理員和合規性專家對使用 Microsoft 365 的基本概念有基本的瞭解，而且正在尋找如何快速開始使用通訊相容性的端對端指導方針。</span><span class="sxs-lookup"><span data-stu-id="24a7c-109">Contoso IT administrators and compliance specialists have a basic understanding of the fundamentals of working with Microsoft 365 and are looking for end-to-end guidance for how to quickly get started with communication compliance.</span></span>

<span data-ttu-id="24a7c-110">此案例研究將涵蓋快速設定通訊相容性原則，以監視冒犯性語言的通訊的基本概念。</span><span class="sxs-lookup"><span data-stu-id="24a7c-110">This case study will cover the basics for quickly configuring a communication compliance policy to monitor communications for offensive language.</span></span> <span data-ttu-id="24a7c-111">本指南包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="24a7c-111">This guidance includes:</span></span>

- <span data-ttu-id="24a7c-112">步驟 1-規劃通訊合規性</span><span class="sxs-lookup"><span data-stu-id="24a7c-112">Step 1 - Planning for communication compliance</span></span>
- <span data-ttu-id="24a7c-113">步驟 2-存取 Microsoft 365 中的通訊法規遵從性</span><span class="sxs-lookup"><span data-stu-id="24a7c-113">Step 2 - Accessing communication compliance in Microsoft 365</span></span>
- <span data-ttu-id="24a7c-114">步驟 3-設定必要條件及建立通訊合規性原則</span><span class="sxs-lookup"><span data-stu-id="24a7c-114">Step 3 - Configuring prerequisites and creating a communication compliance policy</span></span>
- <span data-ttu-id="24a7c-115">步驟 4-調查和修正警示</span><span class="sxs-lookup"><span data-stu-id="24a7c-115">Step 4 - Investigation and remediation of alerts</span></span>

## <a name="step-1---planning-for-communication-compliance"></a><span data-ttu-id="24a7c-116">步驟 1-規劃通訊合規性</span><span class="sxs-lookup"><span data-stu-id="24a7c-116">Step 1 - Planning for communication compliance</span></span>

<span data-ttu-id="24a7c-117">Contoso IT 系統管理員和合規性專家會參加線上網路研討會365中有關法規遵從性解決方案的相關資訊，決定通訊合規性原則可協助他們符合更新的公司原則需求，以減少工作場所騷擾。</span><span class="sxs-lookup"><span data-stu-id="24a7c-117">Contoso IT administrators and compliance specialists attended online webinars about compliance solutions in Microsoft 365 and decided that communication compliance policies will help them meet the updated corporate policy requirements for reducing workplace harassment.</span></span> <span data-ttu-id="24a7c-118">共同運作，他們已開發好一種計畫，用以為 Exchange Online 中傳送的電子郵件訊息，建立及啟用通訊相容性原則，以監視 Microsoft 小組中所傳送的攻擊性語言。</span><span class="sxs-lookup"><span data-stu-id="24a7c-118">Working together, they've developed a plan to create and enable a communication compliance policy that will monitor for offensive language for chats sent in Microsoft Teams in email messages sent in Exchange Online.</span></span> <span data-ttu-id="24a7c-119">其計畫包含識別：</span><span class="sxs-lookup"><span data-stu-id="24a7c-119">Their plan includes identifying:</span></span>

- <span data-ttu-id="24a7c-120">需要存取通訊規範功能的 IT 管理員。</span><span class="sxs-lookup"><span data-stu-id="24a7c-120">The IT administrators that need access to communication compliance features.</span></span>
- <span data-ttu-id="24a7c-121">需要建立及管理通訊原則的規範專家。</span><span class="sxs-lookup"><span data-stu-id="24a7c-121">The compliance specialists that need to create and manage communication policies.</span></span>
- <span data-ttu-id="24a7c-122">合規性專家和其他部門中的其他同事（人力資源、法律等）需要調查和修正通訊相容性警示。</span><span class="sxs-lookup"><span data-stu-id="24a7c-122">The compliance specialists and other colleague in other departments (Human Resources, Legal, etc.) that need to investigate and remediate communication compliance alerts.</span></span>
- <span data-ttu-id="24a7c-123">將會在通訊相容性冒犯性語言原則範圍內的使用者。</span><span class="sxs-lookup"><span data-stu-id="24a7c-123">The users that will be in-scope for the communication compliance offensive language policy.</span></span>

### <a name="licensing"></a><span data-ttu-id="24a7c-124">授權</span><span class="sxs-lookup"><span data-stu-id="24a7c-124">Licensing</span></span>

<span data-ttu-id="24a7c-125">第一步是確認 Contoso 的 Microsoft 365 授權包含對通訊規範解決方案的支援。</span><span class="sxs-lookup"><span data-stu-id="24a7c-125">The first step is to confirm that Contoso's Microsoft 365 licensing includes support for the communication compliance solution.</span></span> <span data-ttu-id="24a7c-126">若要存取和使用通訊法規遵從性，Contoso IT 管理員必須確認 Contoso 是否具備下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="24a7c-126">To access and use communication compliance, Contoso IT administrators need to verify that Contoso has one of the following:</span></span>

- <span data-ttu-id="24a7c-127">Microsoft 365 E5 訂閱（付費或試用版）</span><span class="sxs-lookup"><span data-stu-id="24a7c-127">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="24a7c-128">Office 365 Enterprise E3 授權與高級規範附加元件</span><span class="sxs-lookup"><span data-stu-id="24a7c-128">Office 365 Enterprise E3 license with the Advanced Compliance add-on</span></span>
- <span data-ttu-id="24a7c-129">Office 365 企業版 E5 訂閱（付費或試用版）</span><span class="sxs-lookup"><span data-stu-id="24a7c-129">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>

<span data-ttu-id="24a7c-130">他們也必須確認已包含在通訊合規性原則中的使用者，必須指派給上述其中一個授權。</span><span class="sxs-lookup"><span data-stu-id="24a7c-130">They must also confirm that users included in communication compliance policies must be assigned to one of the licenses listed above.</span></span>

<span data-ttu-id="24a7c-131">Contoso IT 管理員請採取下列步驟，確認 Contoso 的授權支援：</span><span class="sxs-lookup"><span data-stu-id="24a7c-131">Contoso IT administrators take the following steps to verify the licensing support for Contoso:</span></span>

1. <span data-ttu-id="24a7c-132">IT 管理員登入**microsoft 365 系統管理中心** [（https://admin.microsoft.com) ](https://admin.microsoft.com)並流覽至**microsoft 365 系統管理中心** > **計費** > **授權**。</span><span class="sxs-lookup"><span data-stu-id="24a7c-132">IT administrators sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Billing** > **Licenses**.</span></span>

2. <span data-ttu-id="24a7c-133">在這裡，他們會確認他們有其中一個[授權選項](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin)，其中包含對通訊相容性的支援。</span><span class="sxs-lookup"><span data-stu-id="24a7c-133">Here they confirm that they have one of the [license options](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) that includes support for communication compliance.</span></span>

![通訊規範授權](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a><span data-ttu-id="24a7c-135">通訊相容性的許可權</span><span class="sxs-lookup"><span data-stu-id="24a7c-135">Permissions for communication compliance</span></span>

<span data-ttu-id="24a7c-136">根據預設，全域管理員無法存取通訊規範功能。</span><span class="sxs-lookup"><span data-stu-id="24a7c-136">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="24a7c-137">[必須設定許可權](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#step-1-required-enable-permissions-for-communication-compliance)，以讓 Contoso IT 管理員和合規性專家能夠存取通訊相容性。</span><span class="sxs-lookup"><span data-stu-id="24a7c-137">[Permissions must be configured](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#step-1-required-enable-permissions-for-communication-compliance) so that Contoso IT administrators and compliance specialists have access to communication compliance.</span></span>

1. <span data-ttu-id="24a7c-138">Contoso IT 管理員登入**Office 365 安全性與合規性中心**許可權頁面[（https://protection.office.com/permissions) ](https://protection.office.com/permissions)使用全域系統管理員帳戶的認證，然後選取在 Office 365 中查看及管理角色的連結。</span><span class="sxs-lookup"><span data-stu-id="24a7c-138">Contoso IT administrators sign into the **Office 365 Security and Compliance center** permissions page [(https://protection.office.com/permissions)](https://protection.office.com/permissions) using credentials for a global administrator account and select the link to view and manage roles in Office 365.</span></span>
2. <span data-ttu-id="24a7c-139">選取 [**建立**] 之後，他們會為新的角色群組提供「*通訊相容性*」的易記名稱，然後選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="24a7c-139">After selecting **Create**, they give the new role group a friendly name of "*Communication compliance*" and select **Next**.</span></span>
3. <span data-ttu-id="24a7c-140">它們會選取 **[選擇角色**]，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="24a7c-140">They select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="24a7c-141">他們會選取「*主管審查管理員*」、「*案例管理*」、「*合規性管理員*」及「*複查*」的核取方塊，然後選取 [**新增**]、[**執行** **] 和 [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="24a7c-141">They add the required roles by selecting the checkbox for *Supervisory Review Administrator*, *Case Management*, *Compliance Administrator*, and *Review*, then they select **Add**, **Done,** and **Next**.</span></span>

![通訊相容性角色](../media/communication-compliance-case-roles.png)

4. <span data-ttu-id="24a7c-143">接下來，IT 管理員會選取 **[選擇成員**]，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="24a7c-143">Next, the IT administrators select **Choose members** then select **Add**.</span></span> <span data-ttu-id="24a7c-144">選取要建立原則的所有使用者和群組的核取方塊，並使用原則相符專案來管理郵件。</span><span class="sxs-lookup"><span data-stu-id="24a7c-144">The select the checkbox for all the users and groups that they want to create policies and manage messages with policy matches.</span></span> <span data-ttu-id="24a7c-145">他們會將 IT 系統管理員、合規性專家和其他同事加入最初規劃中所識別的人力資源和法律部門中，然後選取 [**新增**]、[**完成** **] 和 [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="24a7c-145">They add the IT administrators, compliance specialists, and other colleagues in Human Resources and Legal departments that they identified in the initial planning, then select **Add**, **Done**, and **Next**.</span></span>
5. <span data-ttu-id="24a7c-146">若要完成許可權，IT 管理員選取 [**建立角色群組**] 完成。</span><span class="sxs-lookup"><span data-stu-id="24a7c-146">To finalize the permissions, the IT administrators select **Create role group** to finish.</span></span> <span data-ttu-id="24a7c-147">需要30分鐘的時間，角色才會在 Contoso 的 Microsoft 365 服務中生效。</span><span class="sxs-lookup"><span data-stu-id="24a7c-147">It will take about 30 minutes for the roles to be effective in Contoso's Microsoft 365 service.</span></span>

![通訊相容性審查](../media/communication-compliance-case-review.png)

## <a name="step-2---accessing-communication-compliance-in-microsoft-365"></a><span data-ttu-id="24a7c-149">步驟 2-存取 Microsoft 365 中的通訊法規遵從性</span><span class="sxs-lookup"><span data-stu-id="24a7c-149">Step 2 - Accessing communication compliance in Microsoft 365</span></span>

<span data-ttu-id="24a7c-150">設定通訊相容性的許可權之後，新角色群組中所定義的 Contoso IT 系統管理員和合規性專家便可以存取 Microsoft 365 中的通訊規範解決方案。</span><span class="sxs-lookup"><span data-stu-id="24a7c-150">After configuring the permissions for communication compliance, Contoso IT administrators and compliance specialists defined in the new role group can access the communication compliance solution in Microsoft 365.</span></span> <span data-ttu-id="24a7c-151">Contoso IT 系統管理員和合規性專家有數種方式可以存取通訊相容性，並開始建立新的原則：</span><span class="sxs-lookup"><span data-stu-id="24a7c-151">Contoso IT administrators and compliance specialists have several ways to access communication compliance and get started creating a new policy:</span></span>

- <span data-ttu-id="24a7c-152">直接從通訊相容性解決方案開始</span><span class="sxs-lookup"><span data-stu-id="24a7c-152">Starting directly from the communication compliance solution</span></span>
- <span data-ttu-id="24a7c-153">從 Microsoft 365 規範中心開始</span><span class="sxs-lookup"><span data-stu-id="24a7c-153">Starting from the Microsoft 365 compliance center</span></span>
- <span data-ttu-id="24a7c-154">從 Microsoft 365 方案目錄開始</span><span class="sxs-lookup"><span data-stu-id="24a7c-154">Starting from the Microsoft 365 solution catalog</span></span>
- <span data-ttu-id="24a7c-155">從 Microsoft 365 系統管理中心開始</span><span class="sxs-lookup"><span data-stu-id="24a7c-155">Starting from the Microsoft 365 admin center</span></span>

### <a name="starting-directly-from-the-communication-compliance-solution"></a><span data-ttu-id="24a7c-156">直接從通訊相容性解決方案開始</span><span class="sxs-lookup"><span data-stu-id="24a7c-156">Starting directly from the communication compliance solution</span></span>

<span data-ttu-id="24a7c-157">存取解決方案最快的方式是直接登入**通訊規範**（<https://compliance.microsoft.com/supervisoryreview>）解決方案。</span><span class="sxs-lookup"><span data-stu-id="24a7c-157">The quickest way to access the solution is to sign in directly to the **Communication compliance** (<https://compliance.microsoft.com/supervisoryreview>) solution.</span></span> <span data-ttu-id="24a7c-158">使用此連結，Contoso IT 管理員和合規性專家將會被導向至通訊相容性一覽表儀表板，您可以在其中快速查看警示的狀態，並從預先定義的範本中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="24a7c-158">Using this link, Contoso IT administrators and compliance specialists will be directed to the communication compliance Overview dashboard where you can quickly review the status of alerts and create new policies from the pre-defined templates.</span></span>

![通訊相容性概述](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a><span data-ttu-id="24a7c-160">從 Microsoft 365 規範中心開始</span><span class="sxs-lookup"><span data-stu-id="24a7c-160">Starting from the Microsoft 365 compliance center</span></span>

<span data-ttu-id="24a7c-161">Contoso IT 系統管理員和合規性專家存取通訊規範解決方案的另一種簡單方法，就是直接登入**Microsoft 365 規範中心** [（https://compliance.microsoft.com)](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="24a7c-161">Another easy way for Contoso IT administrators and compliance specialists to access the communication compliance solution is to sign in directly to the **Microsoft 365 compliance center** [(https://compliance.microsoft.com)](https://compliance.microsoft.com).</span></span> <span data-ttu-id="24a7c-162">登入之後，使用者只需選取 [**顯示所有**的控制項] 即可顯示所有的相容性解決方案，然後選取要開始的**通訊相容性**解決方案。</span><span class="sxs-lookup"><span data-stu-id="24a7c-162">After signing in, users simply need to select the **Show all** control to display all the compliance solutions and then select the **Communication compliance** solution to get started.</span></span>

![規範中心](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a><span data-ttu-id="24a7c-164">從 Microsoft 365 方案目錄開始</span><span class="sxs-lookup"><span data-stu-id="24a7c-164">Starting from the Microsoft 365 solution catalog</span></span>

<span data-ttu-id="24a7c-165">Contoso IT 系統管理員和合規性專家也可以選擇 Microsoft 365 方案目錄，以存取通訊相容性解決方案。</span><span class="sxs-lookup"><span data-stu-id="24a7c-165">Contoso IT administrators and compliance specialists could also choose to access the communication compliance solution by selecting the Microsoft 365 solution catalog.</span></span> <span data-ttu-id="24a7c-166">在**Microsoft 365 規範中心**的左側導覽中，選取 [**方案**] 區段中的 [**目錄**] 區段，即可開啟列出所有 Microsoft 365 相容性解決方案的方案目錄。</span><span class="sxs-lookup"><span data-stu-id="24a7c-166">By selecting **Catalog** in **Solutions** section of the left navigation while in the **Microsoft 365 compliance center**, they can open the solution catalog listing all Microsoft 365 compliance solutions.</span></span> <span data-ttu-id="24a7c-167">向下滾動至「**內幕人員風險管理**」區段，Contoso IT 系統管理員可以選取要開始的通訊相容性。</span><span class="sxs-lookup"><span data-stu-id="24a7c-167">Scrolling down to the **Insider risk management** section, Contoso IT administrators can select Communication compliance to get started.</span></span> <span data-ttu-id="24a7c-168">Contoso IT 管理員也會決定使用「顯示在導覽」控制項中，將通訊相容性解決方案固定至左功能窗格，以在使用者登入時更快速地進行存取。</span><span class="sxs-lookup"><span data-stu-id="24a7c-168">Contoso IT administrators also decide to use the Show in navigation control to pin the communication compliance solution to the left-navigation pane for quicker access when they sign in going forward.</span></span>

![方案目錄](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a><span data-ttu-id="24a7c-170">從 Microsoft 365 系統管理中心開始</span><span class="sxs-lookup"><span data-stu-id="24a7c-170">Starting from the Microsoft 365 admin center</span></span>

<span data-ttu-id="24a7c-171">若要在從 microsoft 365 系統管理中心開始時存取通訊相容性，Contoso IT 系統管理員和合規性專家會登入 microsoft 365 系統管理中心[（https://admin.microsoft.com) ](https://admin.microsoft.com)並流覽至**microsoft 365 admin center** > **合規性**）。</span><span class="sxs-lookup"><span data-stu-id="24a7c-171">To access communication compliance when starting from the Microsoft 365 admin center, Contoso IT administrators and compliance specialists sign in to the Microsoft 365 admin center [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Compliance**.</span></span>

![通訊符合性連結](../media/communication-compliance-case-compliance-link.png)

<span data-ttu-id="24a7c-173">這會開啟**Office 365 安全性與合規性中心**，而且必須選取頁面頂端的橫幅中所提供的**Microsoft 365 規範中心**連結。</span><span class="sxs-lookup"><span data-stu-id="24a7c-173">This opens the **Office 365 Security and Compliance center**, and they must select the link to the **Microsoft 365 compliance center** provided in the banner at the top of the page.</span></span>

![Office 365 安全性與合規性中心](../media/communication-compliance-case-scc.png)

<span data-ttu-id="24a7c-175">在**Microsoft 365 規範中心**內，Contoso IT 系統管理員會選取 [**全部顯示**]，以顯示完整的規範解決方案清單。</span><span class="sxs-lookup"><span data-stu-id="24a7c-175">Once in the **Microsoft 365 compliance center**, Contoso IT administrators select **Show all** to display the full list of compliance solutions.</span></span>

![通訊符合性功能表](../media/communication-compliance-case-show-all.png)

<span data-ttu-id="24a7c-177">選取 [**全部顯示**] 之後，Contoso IT 管理員可以存取通訊規範解決方案。</span><span class="sxs-lookup"><span data-stu-id="24a7c-177">After selecting **Show all**, the Contoso IT administrators can access the communication compliance solution.</span></span>

![通訊相容性概述](../media/communication-compliance-case-overview.png)

## <a name="step-3---configuring-prerequisites-and-creating-a-communication-compliance-policy"></a><span data-ttu-id="24a7c-179">步驟 3-設定必要條件及建立通訊合規性原則</span><span class="sxs-lookup"><span data-stu-id="24a7c-179">Step 3 - Configuring prerequisites and creating a communication compliance policy</span></span>

<span data-ttu-id="24a7c-180">若要開始使用通訊相容性原則，Contoso IT 管理員必須先設定許多必要條件，再設定用來監視冒犯性語言的新原則。</span><span class="sxs-lookup"><span data-stu-id="24a7c-180">To get started with a communication compliance policy, there are several prerequisites that Contoso IT administrators need to configure before setting up the new policy to monitor for offensive language.</span></span> <span data-ttu-id="24a7c-181">完成這些必要條件之後，Contoso IT 管理員和合規性專業人員可以設定新的原則和合規性專業人員，以開始調查並修正任何產生的警示。</span><span class="sxs-lookup"><span data-stu-id="24a7c-181">After these prerequisites have been completed, Contoso IT administrators and compliance specialists can configure the new policy and compliance specialists can start investigation and remediating any generated alerts.</span></span>

### <a name="enabling-auditing-in-office-365"></a><span data-ttu-id="24a7c-182">啟用 Office 365 中的審計</span><span class="sxs-lookup"><span data-stu-id="24a7c-182">Enabling auditing in Office 365</span></span>

<span data-ttu-id="24a7c-183">通訊合規性需要「審核記錄檔」顯示提醒，並追蹤檢閱者採取的修復動作。</span><span class="sxs-lookup"><span data-stu-id="24a7c-183">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="24a7c-184">「審核記錄檔」是與定義之組織原則相關聯的所有活動摘要，或任何一種通訊合規性原則的變更。</span><span class="sxs-lookup"><span data-stu-id="24a7c-184">The audit logs are a summary of all activities associated with a defined organizational policy or anytime there is a change to a communication compliance policy.</span></span>

<span data-ttu-id="24a7c-185">Contoso IT 系統管理員會檢查並完成[逐步指示](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)來開啟審計。</span><span class="sxs-lookup"><span data-stu-id="24a7c-185">Contoso IT administrators review and complete the [step-by-step instructions](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) to turn on auditing.</span></span> <span data-ttu-id="24a7c-186">在開啟審核後，會顯示一則訊息，指出已準備好審核記錄，而且在準備完成後，可以在數小時內執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="24a7c-186">After they turn on auditing, a message is displayed that says the audit log is being prepared and that they can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="24a7c-187">Contoso IT 管理員只需執行這項動作一次。</span><span class="sxs-lookup"><span data-stu-id="24a7c-187">The Contoso IT administrators only have to do this action once.</span></span>

### <a name="setting-up-a-group-for-in-scope-users"></a><span data-ttu-id="24a7c-188">為範圍內使用者設定群組</span><span class="sxs-lookup"><span data-stu-id="24a7c-188">Setting up a group for in-scope users</span></span>

<span data-ttu-id="24a7c-189">Contoso 合規性專家想要將所有員工新增至會監控冒犯性語言的通訊原則。</span><span class="sxs-lookup"><span data-stu-id="24a7c-189">Contoso compliance specialists want to add all employee to the communication policy that will monitor for offensive language.</span></span> <span data-ttu-id="24a7c-190">他們可以決定個別將每個員工使用者帳戶新增至原則，但他們決定使用此原則使用者的**所有員工**通訊群組，會比較容易。</span><span class="sxs-lookup"><span data-stu-id="24a7c-190">They could decide to add each employee user account to the policy separately, but they've decided it is much easier and saves a lot of time to use an **All Employees** distribution group for the users for this policy.</span></span>

<span data-ttu-id="24a7c-191">他們必須建立新的群組，以包含所有 Contoso 員工，所以他們採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="24a7c-191">They need to create a new group to include all Contoso employees, so they take the following steps:</span></span>

1. <span data-ttu-id="24a7c-192">Contoso it 系統管理員會登入**microsoft 365 系統管理中心** [（https://admin.microsoft.com) ](https://admin.microsoft.com)並流覽至**microsoft 365 系統管理中心** > **Groups** > 群組**群組**。</span><span class="sxs-lookup"><span data-stu-id="24a7c-192">Contoso IT administrators IT sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Groups** > **Groups**.</span></span>
2. <span data-ttu-id="24a7c-193">他們會選取 [**新增群組**]，並完成嚮導，以建立新的*Office 365 群組*或*通訊群組*。</span><span class="sxs-lookup"><span data-stu-id="24a7c-193">They select **Add a group** and complete the wizard to create a new *Office 365 group* or *Distribution group*.</span></span>

![群組](../media/communication-compliance-case-all-employees.png)

3. <span data-ttu-id="24a7c-195">在建立新群組之後，必須將所有 Contoso 使用者新增至新群組。</span><span class="sxs-lookup"><span data-stu-id="24a7c-195">After the new group is created, they need to add all Contoso users to the new group.</span></span> <span data-ttu-id="24a7c-196">他們會開啟**exchange 系統管理中心** [（https://outlook.office365.com/ecp) ](https://outlook.office365.com/ecp)並流覽至**Exchange 系統管理中心** > **recipients** > [收件者]**群組**。</span><span class="sxs-lookup"><span data-stu-id="24a7c-196">They open the **Exchange admin center** [(https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) and navigate to **Exchange admin center** > **recipients** > **groups**.</span></span> <span data-ttu-id="24a7c-197">Contoso IT 管理員會選取 [成員資格] 區域以及他們建立的新 [*所有員工*] 群組，然後選取 [**編輯**] 控制項，將所有 Contoso 員工新增至嚮導中的新群組。</span><span class="sxs-lookup"><span data-stu-id="24a7c-197">The Contoso IT administrators select the Membership area and the new *All Employees* group they created and select the **Edit** control to add all Contoso employees to the new group in the wizard.</span></span>

![Exchange 系統管理中心](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a><span data-ttu-id="24a7c-199">建立用來監視冒犯性語言的原則</span><span class="sxs-lookup"><span data-stu-id="24a7c-199">Creating the policy to monitor for offensive language</span></span>

<span data-ttu-id="24a7c-200">在完成所有必要條件之後，Contoso 的 IT 管理員和規範專家便可設定通訊相容性原則，以監視冒犯性語言。</span><span class="sxs-lookup"><span data-stu-id="24a7c-200">With all the prerequisites completed, the IT administrators and the compliance specialists for Contoso are ready to configure the communication compliance policy to monitor for offensive language.</span></span> <span data-ttu-id="24a7c-201">設定此原則是使用新的冒犯性語言原則範本，這是一種簡單且快速的功能。</span><span class="sxs-lookup"><span data-stu-id="24a7c-201">Using the new offensive language policy template, configuring this policy is simple and quick.</span></span>

1. <span data-ttu-id="24a7c-202">Contoso IT 管理員和合規性專家登入**Microsoft 365 規範中心**，然後從左功能窗格中選取 [**通訊規範**]。</span><span class="sxs-lookup"><span data-stu-id="24a7c-202">The Contoso IT administrators and compliance specialists sign into the **Microsoft 365 compliance center** and select **Communication compliance** from the left navigation pane.</span></span> <span data-ttu-id="24a7c-203">此巨集指令會開啟包含通訊相容性原則範本之快速連結的**概述**儀表板。</span><span class="sxs-lookup"><span data-stu-id="24a7c-203">This action opens the **Overview** dashboard that has quick links for communication compliance policy templates.</span></span> <span data-ttu-id="24a7c-204">他們選擇範本的 [**開始**使用]，**以選擇用於冒犯性語言**範本的監視器。</span><span class="sxs-lookup"><span data-stu-id="24a7c-204">They choose the **Monitor for offensive language** template by selecting **Get started** for the template.</span></span>

![通訊相容性冒犯性語言範本](../media/communication-compliance-case-template.png)

2. <span data-ttu-id="24a7c-206">在 [原則範本] 嚮導上，Contoso IT 管理員和合規性專家可共同完成三個必要的欄位：**原則名稱**、**要監督的使用者或群組**，以及**檢閱者**。</span><span class="sxs-lookup"><span data-stu-id="24a7c-206">On the policy template wizard, the Contoso IT administrators and compliance specialists work together to complete the three required fields: **Policy name**, **Users or groups to supervise**, and **Reviewers**.</span></span>
3. <span data-ttu-id="24a7c-207">因為原則嚮導已建議原則的名稱，IT 系統管理員和合規性專家決定保留建議的名稱，並將重點放在其餘的欄位上。</span><span class="sxs-lookup"><span data-stu-id="24a7c-207">Since the policy wizard has already suggested a name for the policy, the IT administrators and compliance specialists decide to keep the suggested name and focus on the remaining fields.</span></span> <span data-ttu-id="24a7c-208">他們會選取 [*所有員工*] 群組中的 [**要監督的使用者或群組**] 欄位，並選取應調查和修正「**檢閱者**」欄位之原則警示的規範專家。</span><span class="sxs-lookup"><span data-stu-id="24a7c-208">They select the *All employees* group for the **Users or groups to supervise** field and select the compliance specialists that should investigate and remediate policy alerts for the **Reviewers** field.</span></span> <span data-ttu-id="24a7c-209">設定原則及開始收集警示資訊的最後一個步驟，是選取 [**建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="24a7c-209">The last step to configure the policy and start gathering alert information is to select **Create policy**.</span></span>

![通訊相容性冒犯性語言嚮導](../media/communication-compliance-case-wizard.png)

## <a name="step-4--investigate-and-remediate-alerts"></a><span data-ttu-id="24a7c-211">步驟4–調查和修正警示</span><span class="sxs-lookup"><span data-stu-id="24a7c-211">Step 4 – Investigate and remediate alerts</span></span>

<span data-ttu-id="24a7c-212">現在，您已設定用於為冒犯性語言監控的通訊相容性原則，因此 Contoso 合規性專家的下一步是調查並修正原則所產生的任何警示。</span><span class="sxs-lookup"><span data-stu-id="24a7c-212">Now that the communication compliance policy to monitor for offensive language is configured, the next step for the Contoso compliance specialists will be to investigate and remediate any alerts generated by the policy.</span></span> <span data-ttu-id="24a7c-213">原則需要24小時的時間，才能完全處理所有通訊來源通道中的通訊，以及**警示儀表板**中顯示的警示。</span><span class="sxs-lookup"><span data-stu-id="24a7c-213">It will take up to 24 hours for the policy to fully process communications in all the communication source channels and for alerts to show up in the **Alert dashboard**.</span></span>

<span data-ttu-id="24a7c-214">提醒產生之後，Contoso 合規性專家將遵循[工作流程指示](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate)，調查並修正冒犯性語言的問題。</span><span class="sxs-lookup"><span data-stu-id="24a7c-214">After alerts are generated, Contoso compliance specialists will follow the [workflow instructions](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) to investigate and remediate offensive language issues.</span></span>
