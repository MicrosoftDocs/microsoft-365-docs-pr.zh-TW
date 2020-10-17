---
title: 步驟 4： 為您的裝置、電腦和其他端點部署端點管理
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 端點管理員來管理受管理的裝置、電腦及其他端點。
ms.openlocfilehash: b50279166b313742dbfbe8e75dd9788aac6b1daa
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445958"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="6d4e7-104">步驟 4：</span><span class="sxs-lookup"><span data-stu-id="6d4e7-104">Step 4.</span></span> <span data-ttu-id="6d4e7-105">為您的裝置、電腦和其他端點部署端點管理</span><span class="sxs-lookup"><span data-stu-id="6d4e7-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="6d4e7-106">若雇用遠端工作者，您必須支援日益增加的個人裝置。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="6d4e7-107">端點管理是原則型的安全性方法，要求裝置必須符合特定準則，才能獲得存取資源的授權。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="6d4e7-108">[Microsoft 端點管理員] 提供現代化管理功能，保護您的雲端資料及內部檔案的安全。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-108">Microsoft Endpoint Manager delivers modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="6d4e7-109">端點管理員提供可管理行動裝置、電腦、虛擬機器、嵌入式裝置及伺服器的服務和工具，並結合您可能已經知道且正在使用的服務。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-109">Endpoint Manager provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![端點管理元件](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="6d4e7-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6d4e7-111">Microsoft Intune</span></span>

<span data-ttu-id="6d4e7-112">Microsoft Intune 是一種雲端式服務，專門用於 Microsoft 365 隨附的行動裝置管理 (MDM) 和行動應用程式管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-112">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM) that is included with Microsoft 365.</span></span> 

- <span data-ttu-id="6d4e7-113">**MDM：** 針對組織擁有的裝置，您可以執行完全控制功能，包括設定、功能及安全性。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-113">**MDM:** For organization-owned devices, you can exercise full control including settings, features, and security.</span></span> <span data-ttu-id="6d4e7-114">裝置會在 Intune 中「註冊」，並在其中接收 Intune 原則以及規則和設定。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-114">Devices are "enrolled" in Intune where they receive Intune policies with rules and settings.</span></span> <span data-ttu-id="6d4e7-115">例如，您可以設定密碼和 PIN 需求、建立 VPN 連線、設定威脅防護等等。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-115">For example, you can set password and PIN requirements, create a VPN connection, set up threat protection, and more.</span></span>

- <span data-ttu-id="6d4e7-116">**MAM：** 遠端工作者可能不希望您在其個人裝置 (也稱為攜帶您自己的裝置 (BYOD)) 上擁有完全控制權。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-116">**MAM:** Remote workers might not want you to have full control on their personal devices, also known as bring-your-own device (BYOD) devices.</span></span> <span data-ttu-id="6d4e7-117">您可以提供遠端工作者選項，但是仍然保護貴組織。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-117">You can give your remote workers options and still protect your organization.</span></span> <span data-ttu-id="6d4e7-118">例如，如果遠端工作者想要完全存取組織資源，可以註冊其裝置。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-118">For example, remote workers can enroll their devices if they want full access to your organization resources.</span></span> <span data-ttu-id="6d4e7-119">或者，如果這些使用者只想要存取電子郵件或 Microsoft Teams，請使用需要多重要素驗證 (MFA) 的應用程式保護原則來使用這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-119">Or, if these users only want access to email or Microsoft Teams, then use app protection policies that require multi-factor authentication (MFA) to use these apps.</span></span>

<span data-ttu-id="6d4e7-120">如需詳細資訊，請參閱 [Microsoft Intune 概觀](https://docs.microsoft.com/intune/fundamentals/what-is-intune)。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-120">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="6d4e7-121">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6d4e7-121">Configuration Manager</span></span>

<span data-ttu-id="6d4e7-122">Configuration Manager 是一種內部部署管理解決方案，可管理網路或網際網路上的桌上型電腦、伺服器和膝上型電腦。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-122">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="6d4e7-123">使用 Configuration Manager 部署應用程式、軟體更新及作業系統。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-123">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="6d4e7-124">您也可以即時監視合規性、查詢和操作用戶端，以及執行更多動作。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-124">You can also monitor compliance, query and act on clients in real time, and much more.</span></span> <span data-ttu-id="6d4e7-125">您可以在雲端啟用此功能，讓它與 Intune、Azure AD、Microsoft Defender ATP 和其他雲端服務整合。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-125">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender ATP, and other cloud services.</span></span> 

<span data-ttu-id="6d4e7-126">如需詳細資訊，請參閱 [Configuration Manager 概觀](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-126">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="6d4e7-127">共同管理</span><span class="sxs-lookup"><span data-stu-id="6d4e7-127">Co-management</span></span>

<span data-ttu-id="6d4e7-128">共同管理會使用 Intune 和其他 Microsoft 365 雲端服務，將您現有的內部部署 Configuration Manager 投資與雲端結合。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-128">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="6d4e7-129">您可以選擇將 Configuration Manager 或 Intune 設定為不同工作負載的管理單位。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-129">You choose whether Configuration Manager or Intune is the management authority for different workload.</span></span> 

<span data-ttu-id="6d4e7-130">共同管理使用 Intune 型雲端功能，包括條件式存取權和強制執行裝置合規性。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-130">Co-management uses Intune-based cloud features, including Conditional Access and enforcing device compliance.</span></span> <span data-ttu-id="6d4e7-131">您可以將部分工作保留在內部部署中，同時雲端中執行其他工作。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-131">You keep some tasks on-premises, while running other tasks in the cloud.</span></span>

<span data-ttu-id="6d4e7-132">如需詳細資訊，請參閱[共同管理概觀](https://docs.microsoft.com/mem/configmgr/comanage/overview)。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-132">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="6d4e7-133">電腦分析</span><span class="sxs-lookup"><span data-stu-id="6d4e7-133">Desktop Analytics</span></span>

<span data-ttu-id="6d4e7-134">桌面分析是與 Configuration Manager 整合的雲端型服務，可提供深入解析與情報，讓您對 Windows 用戶端做出正確決策。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-134">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="6d4e7-135">它會結合組織的資料，與從連線到 Microsoft 雲端服務的上百萬裝置上彙總的資料。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-135">It combines data from your organization with data aggregated from millions of devices connected to Microsoft cloud services.</span></span> 

<span data-ttu-id="6d4e7-136">使用電腦分析，您可以：</span><span class="sxs-lookup"><span data-stu-id="6d4e7-136">With Desktop Analytics, you can:</span></span>

- <span data-ttu-id="6d4e7-137">建立組織中執行之應用程式的庫存。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-137">Create an inventory of apps running in your organization.</span></span>
- <span data-ttu-id="6d4e7-138">使用最新的 Windows 10 功能更新評估應用程式相容性。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-138">Assess app compatibility with the latest Windows 10 feature updates.</span></span>
- <span data-ttu-id="6d4e7-139">找出相容性問題，並根據啟用雲端的資料深入解析來接收緩解建議。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-139">Identify compatibility issues, and receive mitigation suggestions based on cloud-enabled data insights.</span></span>
- <span data-ttu-id="6d4e7-140">建立試驗組，代表最少裝置集的整個應用程式和驅動程式資源。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-140">Create pilot groups that represent the entire application and driver estate across a minimal set of devices.</span></span>
- <span data-ttu-id="6d4e7-141">將 Windows 10 部署到試驗和生產管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-141">Deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="6d4e7-142">如需詳細資訊，請參閱[桌面分析概觀](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-142">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="6d4e7-143">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="6d4e7-143">Windows Autopilot</span></span>

<span data-ttu-id="6d4e7-144">Windows Autopilot 是一種零觸控、自助式 Windows 部署平台。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-144">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="6d4e7-145">其中包含用來設定和預先設定新裝置的技術集合，讓這些技術可供生產使用。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-145">It includes a collection of technologies used to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="6d4e7-146">您也可以使用 Windows Autopilot 來重設、重新利用和復原裝置。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-146">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> 

<span data-ttu-id="6d4e7-147">Windows Autopilot 能讓 IT 部門透過簡單易行的流程，幾乎不需要管理任何基礎架構即可預先設定裝置。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-147">Windows Autopilot enables an IT department to pre-configure devices with little to no infrastructure to manage, with a process that's easy and simple.</span></span> 

- <span data-ttu-id="6d4e7-148">從使用者的角度來看，只需要幾個簡單的操作就能將裝置準備就緒。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-148">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> 
- <span data-ttu-id="6d4e7-149">從 IT 專業人員的角度，使用者唯一需要進行的互動就是連線網路和驗證認證。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-149">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="6d4e7-150">如需詳細資訊，請參閱 [Windows Autopilot 概觀](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-150">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="6d4e7-151">適用於端點管理的系統管理技術資源</span><span class="sxs-lookup"><span data-stu-id="6d4e7-151">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="6d4e7-152">第 3 部分影片，為遠端工作者適用的 Windows 10 裝置管理</span><span class="sxs-lookup"><span data-stu-id="6d4e7-152">The Part 3 video on managing Windows 10 devices for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="6d4e7-153">第5部分影片，為遠端工作者適用的使用者桌面和瀏覽器管理</span><span class="sxs-lookup"><span data-stu-id="6d4e7-153">The Part 5 video on managing user desktops and browsers for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="6d4e7-154">為 Microsoft 365 部署移動性基礎結構</span><span class="sxs-lookup"><span data-stu-id="6d4e7-154">Deploy a mobility infrastructure for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [<span data-ttu-id="6d4e7-155">如何註冊不同的裝置類型以管理行動裝置</span><span class="sxs-lookup"><span data-stu-id="6d4e7-155">How to enroll different types of devices for mobile device management</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="6d4e7-156">如何向使用者說明 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6d4e7-156">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a><span data-ttu-id="6d4e7-157">步驟 3 的結果</span><span class="sxs-lookup"><span data-stu-id="6d4e7-157">Results of Step 3</span></span>

<span data-ttu-id="6d4e7-158">您正在使用端點管理員功能套件來管理行動裝置、電腦、虛擬機器、嵌入式裝置及伺服器。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-158">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="6d4e7-159">下一步</span><span class="sxs-lookup"><span data-stu-id="6d4e7-159">Next step</span></span>

<span data-ttu-id="6d4e7-160">[![步驟 5：部署遠端工作者生產力應用程式和服務](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span><span class="sxs-lookup"><span data-stu-id="6d4e7-160">[![Step 5: Deploy remote worker productivity apps and services](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span></span>

<span data-ttu-id="6d4e7-161">繼續進行[步驟 5](empower-people-to-work-remotely-teams-productivity-apps.md)，讓您的遠端工作者能使用 Microsoft 365 生產力應用程式，例如 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6d4e7-161">Continue with [Step 5](empower-people-to-work-remotely-teams-productivity-apps.md) to get your remote workers using Microsoft 365 productivity apps such as Microsoft Teams.</span></span>
