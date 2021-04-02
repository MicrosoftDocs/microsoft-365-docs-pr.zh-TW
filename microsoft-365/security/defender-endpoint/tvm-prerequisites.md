---
title: 必要條件 & 許可權-威脅和弱點管理
description: 在您開始使用威脅和弱點管理之前，請確定您有相關的設定和許可權。
keywords: 威脅 & 漏洞管理許可權的必要條件、威脅和弱點管理許可權必要條件、MDATP TVM 許可權必要條件、弱點管理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1d9c3233f72541ccd0463eefef93bde5e7d9900f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499953"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="d4bca-104">必要條件 & 許可權-威脅和弱點管理</span><span class="sxs-lookup"><span data-stu-id="d4bca-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d4bca-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d4bca-105">**Applies to:**</span></span>

- [<span data-ttu-id="d4bca-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d4bca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d4bca-107">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="d4bca-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d4bca-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4bca-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d4bca-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d4bca-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d4bca-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d4bca-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="d4bca-111">確定您的裝置：</span><span class="sxs-lookup"><span data-stu-id="d4bca-111">Ensure that your devices:</span></span>

- <span data-ttu-id="d4bca-112">會架至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d4bca-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="d4bca-113">執行 [支援的作業系統和平臺](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="d4bca-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="d4bca-114">在您的網路中安裝並部署下列必要更新，以提升您的漏洞評估偵測速度：</span><span class="sxs-lookup"><span data-stu-id="d4bca-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="d4bca-115">發行</span><span class="sxs-lookup"><span data-stu-id="d4bca-115">Release</span></span> | <span data-ttu-id="d4bca-116">安全性更新 KB 編號及連結</span><span class="sxs-lookup"><span data-stu-id="d4bca-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="d4bca-117">Windows 10 版本1709</span><span class="sxs-lookup"><span data-stu-id="d4bca-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="d4bca-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) 和 [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="d4bca-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="d4bca-119">Windows 10 版本1803</span><span class="sxs-lookup"><span data-stu-id="d4bca-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="d4bca-120">[KB4493464](https://support.microsoft.com/help/4493464) 和 [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="d4bca-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="d4bca-121">Windows 10 版本1809</span><span class="sxs-lookup"><span data-stu-id="d4bca-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="d4bca-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="d4bca-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="d4bca-123">Windows 10 版本1903</span><span class="sxs-lookup"><span data-stu-id="d4bca-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="d4bca-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="d4bca-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="d4bca-125">會架至 [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 和  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) ，以協助修復威脅和弱點管理所發現的威脅。</span><span class="sxs-lookup"><span data-stu-id="d4bca-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="d4bca-126">如果您使用的是 Configuration Manager，請將主控台更新為最新的版本。</span><span class="sxs-lookup"><span data-stu-id="d4bca-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="d4bca-127">**附注**：如果您已啟用 intune 連線，您可以在建立修復要求時，取得建立 intune 安全性工作的選項。</span><span class="sxs-lookup"><span data-stu-id="d4bca-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="d4bca-128">如果未設定 connection，則不會顯示此選項。</span><span class="sxs-lookup"><span data-stu-id="d4bca-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="d4bca-129">在 [裝置] 頁面中至少有一個可以查看的安全性建議</span><span class="sxs-lookup"><span data-stu-id="d4bca-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="d4bca-130">已標記或標示為共同管理</span><span class="sxs-lookup"><span data-stu-id="d4bca-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="d4bca-131">相關許可權選項</span><span class="sxs-lookup"><span data-stu-id="d4bca-131">Relevant permission options</span></span>

1. <span data-ttu-id="d4bca-132">使用已指派安全性管理員或全域系統管理員角色的帳戶登入 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="d4bca-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="d4bca-133">在功能窗格中，選取 [ **設定] > 角色**。</span><span class="sxs-lookup"><span data-stu-id="d4bca-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="d4bca-134">如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d4bca-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="d4bca-135">查看資料</span><span class="sxs-lookup"><span data-stu-id="d4bca-135">View data</span></span>

- <span data-ttu-id="d4bca-136">**安全性作業** -查看入口網站中的所有安全性作業資料</span><span class="sxs-lookup"><span data-stu-id="d4bca-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="d4bca-137">**威脅和弱點管理** -在入口網站中查看威脅和弱點管理資料</span><span class="sxs-lookup"><span data-stu-id="d4bca-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="d4bca-138">主動修正動作</span><span class="sxs-lookup"><span data-stu-id="d4bca-138">Active remediation actions</span></span>

- <span data-ttu-id="d4bca-139">**安全性作業** -採取回應動作、核准或取消未決修正動作、管理允許/封鎖的自動化和指示器清單</span><span class="sxs-lookup"><span data-stu-id="d4bca-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="d4bca-140">**威脅和弱點管理-例外處理** -建立新的例外狀況及管理作用中的例外狀況</span><span class="sxs-lookup"><span data-stu-id="d4bca-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="d4bca-141">**威脅和弱點管理-修正處理** -提交新的修復要求、建立票證，以及管理現有的修復活動</span><span class="sxs-lookup"><span data-stu-id="d4bca-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="d4bca-142">如需詳細資訊，請參閱 [RBAC 許可權選項](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="d4bca-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="d4bca-143">相關文章</span><span class="sxs-lookup"><span data-stu-id="d4bca-143">Related articles</span></span>

- [<span data-ttu-id="d4bca-144">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="d4bca-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d4bca-145">支援的作業系統和平台</span><span class="sxs-lookup"><span data-stu-id="d4bca-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="d4bca-146">指派裝置值</span><span class="sxs-lookup"><span data-stu-id="d4bca-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="d4bca-147">威脅與弱點管理儀表板</span><span class="sxs-lookup"><span data-stu-id="d4bca-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

