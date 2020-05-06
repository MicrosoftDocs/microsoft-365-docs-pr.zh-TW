---
title: 3. 為您的裝置、電腦和其他端點部署端點管理
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: 使用 Microsoft 端點管理員來管理受管理的裝置、電腦及其他端點。
ms.openlocfilehash: 2a5b047aabb95d0b60c46fe3bec339e723adee0e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049578"
---
# <a name="3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="10035-103">3. 為您的裝置、電腦和其他端點部署端點管理</span><span class="sxs-lookup"><span data-stu-id="10035-103">3. Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="10035-104">若雇用遠端工作者，您必須支援日益增加的個人裝置。</span><span class="sxs-lookup"><span data-stu-id="10035-104">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="10035-105">端點管理是原則型的安全性方法，要求裝置必須符合特定準則，才能獲得存取資源的授權。</span><span class="sxs-lookup"><span data-stu-id="10035-105">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="10035-106">Microsoft 端點管理員提供新式的工作場所和新式管理功能，讓您的資料在雲端和內部部署中保持安全。</span><span class="sxs-lookup"><span data-stu-id="10035-106">Microsoft Endpoint Manager delivers a modern workplace and modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="10035-107">端點管理員提供可管理行動裝置、電腦、虛擬機器、嵌入式裝置及伺服器的服務和工具，並結合您可能已經知道且正在使用的服務。</span><span class="sxs-lookup"><span data-stu-id="10035-107">Endpoint Manager provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![端點管理元件](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="10035-109">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="10035-109">Microsoft Intune</span></span>

<span data-ttu-id="10035-110">當您不管理用來存取組織資料的裝置時，Intune 的設計在於協助您保護資料。</span><span class="sxs-lookup"><span data-stu-id="10035-110">Intune is designed to help you safeguard data when you don’t manage the devices used to access organization data.</span></span> <span data-ttu-id="10035-111">與 Azure AD 條件式存取結合的 Intune 應用程式防護原則，可讓您在行動裝置上精細控制資料。</span><span class="sxs-lookup"><span data-stu-id="10035-111">Intune app protection policies combined with Azure AD Conditional Access provide granular control over data on mobile devices.</span></span> <span data-ttu-id="10035-112">Intune 還能讓您定義全面的原則，只允許適當的人員在正確的條件下存取您的公司資料，並在 Office、Outlook 和其他行動裝置應用程式中控制資料的使用方式，確保資料的安全無虞。</span><span class="sxs-lookup"><span data-stu-id="10035-112">Intune also enables you to define comprehensive policies that allow only the right people under the right conditions to access your company data and ensure the data stays protected by controlling how they use it within Office, Outlook and other mobile apps.</span></span>

<span data-ttu-id="10035-113">如需詳細資訊，請參閱 [Microsoft Intune 概觀](https://docs.microsoft.com/intune/fundamentals/what-is-intune)。</span><span class="sxs-lookup"><span data-stu-id="10035-113">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="10035-114">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="10035-114">Configuration Manager</span></span>

<span data-ttu-id="10035-115">Configuration Manager 是一種內部部署管理解決方案，可管理網路或網際網路上的桌上型電腦、伺服器和膝上型電腦。</span><span class="sxs-lookup"><span data-stu-id="10035-115">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="10035-116">您可以在雲端啟用此功能，讓它與 Intune、Azure AD、Microsoft Defender ATP 和其他雲端服務整合。</span><span class="sxs-lookup"><span data-stu-id="10035-116">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender ATP, and other cloud services.</span></span> <span data-ttu-id="10035-117">使用 Configuration Manager 部署應用程式、軟體更新及作業系統。</span><span class="sxs-lookup"><span data-stu-id="10035-117">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="10035-118">您也可以即時監視合規性、查詢和操作用戶端，以及執行更多動作。</span><span class="sxs-lookup"><span data-stu-id="10035-118">You can also monitor compliance, query and act on clients in real time, and much more.</span></span>

<span data-ttu-id="10035-119">如需詳細資訊，請參閱 [Configuration Manager 概觀](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="10035-119">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="10035-120">共同管理</span><span class="sxs-lookup"><span data-stu-id="10035-120">Co-management</span></span>

<span data-ttu-id="10035-121">共同管理會使用 Intune 和其他 Microsoft 365 雲端服務，將您現有的內部部署 Configuration Manager 投資與雲端結合。</span><span class="sxs-lookup"><span data-stu-id="10035-121">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="10035-122">您可以選擇將 Configuration Manager 或 Intune 設定為七個不同工作負載群組的管理單位。</span><span class="sxs-lookup"><span data-stu-id="10035-122">You choose whether Configuration Manager or Intune is the management authority for the seven different workload groups.</span></span>

<span data-ttu-id="10035-123">共同管理屬於端點管理員中的部分功能，其使用雲端功能，包括條件式存取。</span><span class="sxs-lookup"><span data-stu-id="10035-123">As part of Endpoint Manager, co-management uses cloud features, including Conditional Access.</span></span> <span data-ttu-id="10035-124">您可以將部分工作保留在內部部署中，同時使用 Intune 在雲端中執行其他工作。</span><span class="sxs-lookup"><span data-stu-id="10035-124">You keep some tasks on-premises, while running other tasks in the cloud with Intune.</span></span>

<span data-ttu-id="10035-125">如需詳細資訊，請參閱[共同管理概觀](https://docs.microsoft.com/mem/configmgr/comanage/overview)。</span><span class="sxs-lookup"><span data-stu-id="10035-125">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="10035-126">電腦分析</span><span class="sxs-lookup"><span data-stu-id="10035-126">Desktop Analytics</span></span>

<span data-ttu-id="10035-127">桌面分析是與 Configuration Manager 整合的雲端型服務，可提供深入解析與情報，讓您對 Windows 用戶端做出正確決策。</span><span class="sxs-lookup"><span data-stu-id="10035-127">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="10035-128">它會結合組織的資料，與從連線到 Microsoft 雲端服務的上百萬裝置上彙總的資料。</span><span class="sxs-lookup"><span data-stu-id="10035-128">It combines data from your organization with data aggregated from millions of devices connected to Microsoft cloud services.</span></span> <span data-ttu-id="10035-129">使用桌面分析，您可以建立在組織中執行的應用程式庫存、評估與最新 Windows 10 功能更新的應用程式相容性、找出相容性問題，並收到根據支援雲端的資料深入解析的緩解建議、建立代表最少裝置集的整個應用程式和驅動程式資產的試驗組，並將 Windows 10 部署到試驗和生產管理裝置。</span><span class="sxs-lookup"><span data-stu-id="10035-129">With Desktop Analytics, you can create an inventory of apps running in your organization, assess app compatibility with the latest Windows 10 feature updates, identify compatibility issues, and receive mitigation suggestions based on cloud-enabled data insights, create pilot groups that represent the entire application and driver estate across a minimal set of devices, and deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="10035-130">如需詳細資訊，請參閱[桌面分析概觀](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)。</span><span class="sxs-lookup"><span data-stu-id="10035-130">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="10035-131">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="10035-131">Windows Autopilot</span></span>

<span data-ttu-id="10035-132">Windows Autopilot 是一種零觸控、自助式 Windows 部署平台。</span><span class="sxs-lookup"><span data-stu-id="10035-132">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="10035-133">其中包含用來設定和預先設定新裝置的技術集合，讓這些技術可供生產使用。</span><span class="sxs-lookup"><span data-stu-id="10035-133">It includes a collection of technologies used to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="10035-134">您也可以使用 Windows Autopilot 來重設、重新利用和復原裝置。</span><span class="sxs-lookup"><span data-stu-id="10035-134">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> <span data-ttu-id="10035-135">這個解決方案能讓 IT 部門透過簡單易行的流程，幾乎不需要管理任何基礎架構即可實現上述目標。</span><span class="sxs-lookup"><span data-stu-id="10035-135">This solution enables an IT department to achieve the above with little to no infrastructure to manage, with a process that's easy and simple.</span></span> <span data-ttu-id="10035-136">從使用者的角度來看，只需要幾個簡單的操作就能將裝置準備就緒。</span><span class="sxs-lookup"><span data-stu-id="10035-136">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> <span data-ttu-id="10035-137">從 IT 專業人員的角度，使用者唯一需要進行的互動就是連線網路和驗證認證。</span><span class="sxs-lookup"><span data-stu-id="10035-137">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="10035-138">如需詳細資訊，請參閱 [Windows Autopilot 概觀](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="10035-138">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="10035-139">適用於端點管理的系統管理技術資源</span><span class="sxs-lookup"><span data-stu-id="10035-139">Admin technical resources for endpoint management</span></span>

- <span data-ttu-id="10035-140">[註冊受管理裝置以取得安全性，利用非受管理裝置的應用程式設定，以及使用裝置和應用程式原則](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="10035-140">[Enroll managed devices for security, leverage app settings for unmanaged devices, and use device and app policies](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)</span></span>
- [<span data-ttu-id="10035-141">如何註冊不同類型的裝置，以進行行動裝置管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="10035-141">How to enroll different types of devices for mobile device management (MDM)</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="10035-142">如何向使用者說明 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="10035-142">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a><span data-ttu-id="10035-143">步驟 3 的結果</span><span class="sxs-lookup"><span data-stu-id="10035-143">Results of Step 3</span></span>

<span data-ttu-id="10035-144">您正在使用端點管理員功能套件來管理行動裝置、電腦、虛擬機器、嵌入式裝置及伺服器。</span><span class="sxs-lookup"><span data-stu-id="10035-144">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="10035-145">後續步驟</span><span class="sxs-lookup"><span data-stu-id="10035-145">Next step</span></span>

<span data-ttu-id="10035-146">繼續[步驟 4](empower-people-to-work-remotely-teams-productivity-apps.md)，以為內部部署應用程式和服務提供遠端存取。</span><span class="sxs-lookup"><span data-stu-id="10035-146">Continue with [Step 4](empower-people-to-work-remotely-teams-productivity-apps.md) to provide remote access to on-premises apps and services.</span></span>
