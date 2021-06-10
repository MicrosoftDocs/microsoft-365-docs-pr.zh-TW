---
title: 使用 Configuration Manager 管理 Microsoft Defender for Endpoint
description: 瞭解如何使用 Configuration Manager 管理 Microsoft Defender for Endpoint
keywords: 遷移後、管理、作業、維護、使用狀況、Configuration Manager、Microsoft Defender for Endpoint、edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 71ad8f52fd9347abdf0146969bb84a19d8883262
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843055"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="39d5a-104">使用 Configuration Manager 管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39d5a-104">Manage Microsoft Defender for Endpoint with Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="39d5a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="39d5a-105">**Applies to:**</span></span>
- [<span data-ttu-id="39d5a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="39d5a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="39d5a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39d5a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="39d5a-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="39d5a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="39d5a-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="39d5a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="39d5a-110">建議使用[Microsoft 端點管理員](/mem)，其中包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) 及[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) ，以管理組織中的裝置威脅防護功能， (也稱為端點) 。</span><span class="sxs-lookup"><span data-stu-id="39d5a-110">We recommend using We recommend using [Microsoft Endpoint Manager](/mem), which includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) and [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> 
- [<span data-ttu-id="39d5a-111">深入瞭解端點管理員</span><span class="sxs-lookup"><span data-stu-id="39d5a-111">Learn more about Endpoint Manager</span></span>](/mem/endpoint-manager-overview)
- [<span data-ttu-id="39d5a-112">使用 Configuration Manager 和 Intune 在 Windows 10 裝置上共同管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39d5a-112">Co-manage Microsoft Defender for Endpoint on Windows 10 devices with Configuration Manager and Intune</span></span>](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="39d5a-113">使用 Configuration Manager 設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39d5a-113">Configure Microsoft Defender for Endpoint with Configuration Manager</span></span>

|<span data-ttu-id="39d5a-114">工作</span><span class="sxs-lookup"><span data-stu-id="39d5a-114">Task</span></span>  |<span data-ttu-id="39d5a-115">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="39d5a-115">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="39d5a-116">若尚未 **安裝 Configuration Manager 主控台**，請將其安裝</span><span class="sxs-lookup"><span data-stu-id="39d5a-116">**Install the Configuration Manager console** if you don't already have it</span></span><br/><br/><span data-ttu-id="39d5a-117">*如果您還沒有設定管理器主控台，請使用這些資源來取得並安裝。*</span><span class="sxs-lookup"><span data-stu-id="39d5a-117">*If you don't already have the Configuration Manger console, use these resources to get the bits and install it.*</span></span> |[<span data-ttu-id="39d5a-118">取得安裝媒體</span><span class="sxs-lookup"><span data-stu-id="39d5a-118">Get the installation media</span></span>](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[<span data-ttu-id="39d5a-119">安裝 Configuration Manager 主控台</span><span class="sxs-lookup"><span data-stu-id="39d5a-119">Install the Configuration Manager console</span></span>](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|<span data-ttu-id="39d5a-120">**使用 Configuration Manager 至** Microsoft Defender for Endpoint 的板載裝置</span><span class="sxs-lookup"><span data-stu-id="39d5a-120">**Use Configuration Manager to onboard devices** to Microsoft Defender for Endpoint</span></span> <br/><br/> <span data-ttu-id="39d5a-121">*如果您有裝置 (或端點) 尚未架至 Microsoft Defender for Endpoint，您可以使用 Configuration Manager 來執行。*</span><span class="sxs-lookup"><span data-stu-id="39d5a-121">*If you have devices (or endpoints) not already onboarded to Microsoft Defender for Endpoint, you can do that with Configuration Manager.*</span></span>   |[<span data-ttu-id="39d5a-122">使用 Configuration Manager 的 Microsoft Defender for Endpoint 的板載</span><span class="sxs-lookup"><span data-stu-id="39d5a-122">Onboard to Microsoft Defender for Endpoint with Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|<span data-ttu-id="39d5a-123">**管理反惡意軟體原則，並 Windows** 用戶端電腦 (端點的防火牆安全性) </span><span class="sxs-lookup"><span data-stu-id="39d5a-123">**Manage antimalware policies and Windows Firewall security** for client computers (endpoints)</span></span><br/><br/><span data-ttu-id="39d5a-124">*設定 endpoint protection 功能（包括 Microsoft Defender for Endpoint、exploit protection、application control、反惡意程式碼、防火牆設定等等）。*</span><span class="sxs-lookup"><span data-stu-id="39d5a-124">*Configure endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*</span></span>  |[<span data-ttu-id="39d5a-125">Configuration Manager： Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="39d5a-125">Configuration Manager: Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|<span data-ttu-id="39d5a-126">選擇在組織裝置上 **更新反惡意軟體更新的方法**</span><span class="sxs-lookup"><span data-stu-id="39d5a-126">**Choose methods for updating antimalware updates** on your organization's devices</span></span> <br/><br/><span data-ttu-id="39d5a-127">*使用 Configuration Manager 中的 Endpoint Protection，您可以選擇數種方式，讓組織裝置上的反惡意軟體定義保持在最新狀態。*</span><span class="sxs-lookup"><span data-stu-id="39d5a-127">*With Endpoint Protection in Configuration Manager, you can choose from several methods to keep antimalware definitions up to date on your organization's devices.*</span></span> |[<span data-ttu-id="39d5a-128">設定 Endpoint Protection 的定義更新</span><span class="sxs-lookup"><span data-stu-id="39d5a-128">Configure definition updates for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[<span data-ttu-id="39d5a-129">使用 Configuration Manager 傳送定義更新</span><span class="sxs-lookup"><span data-stu-id="39d5a-129">Use Configuration Manager to deliver definition updates</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|<span data-ttu-id="39d5a-130">**啟用網路保護** ，以協助防止員工在網際網路上使用惡意內容的應用程式</span><span class="sxs-lookup"><span data-stu-id="39d5a-130">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="39d5a-131">*我們建議您先在測試環境中使用 [審計模式](/microsoft-365/security/defender-endpoint/evaluate-network-protection) ，以查看哪些應用程式會封鎖，然後再進行部署。*</span><span class="sxs-lookup"><span data-stu-id="39d5a-131">*We recommend using [audit mode](/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="39d5a-132">使用 Configuration Manager 開啟網路保護</span><span class="sxs-lookup"><span data-stu-id="39d5a-132">Turn on network protection with Configuration Manager</span></span>](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|<span data-ttu-id="39d5a-133">**設定受管理的資料夾存取** 權以防護勒索軟體</span><span class="sxs-lookup"><span data-stu-id="39d5a-133">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="39d5a-134">*「受管理的資料夾存取」也稱為 antiransomware protection。*</span><span class="sxs-lookup"><span data-stu-id="39d5a-134">*Controlled folder access is also referred to as antiransomware protection.*</span></span>   |[<span data-ttu-id="39d5a-135">Endpoint protection：受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="39d5a-135">Endpoint protection: Controlled folder access</span></span>](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[<span data-ttu-id="39d5a-136">啟用 Microsoft Endpoint Configuration 管理中的受控資料夾存取</span><span class="sxs-lookup"><span data-stu-id="39d5a-136">Enable controlled folder access in Microsoft Endpoint Configuration Manage</span></span>](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="39d5a-137">設定 Microsoft Defender 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="39d5a-137">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="39d5a-138">若尚未這麼做，請 **設定 Microsoft Defender 資訊安全中心** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 以查看提醒、設定威脅防護功能，以及查看組織整體安全性狀況的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="39d5a-138">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="39d5a-139">您也可以設定使用者是否可以在 Microsoft Defender 資訊安全中心中看到使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="39d5a-139">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="39d5a-140">Microsoft Defender 資訊安全中心綜述</span><span class="sxs-lookup"><span data-stu-id="39d5a-140">Overview of the Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="39d5a-141">Endpoint protection： Microsoft Defender 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="39d5a-141">Endpoint protection: Microsoft Defender Security Center</span></span>](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="39d5a-142">後續步驟</span><span class="sxs-lookup"><span data-stu-id="39d5a-142">Next steps</span></span>

- [<span data-ttu-id="39d5a-143">深入瞭解威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="39d5a-143">Get an overview of threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="39d5a-144">流覽 Microsoft Defender 資訊安全中心的安全性運作儀表板</span><span class="sxs-lookup"><span data-stu-id="39d5a-144">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="39d5a-145">使用 Intune 管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39d5a-145">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
