---
title: 使用群組原則物件管理 Microsoft Defender for Endpoint
description: 瞭解如何使用群組原則物件管理 Microsoft Defender for Endpoint
keywords: 遷移後、管理、運作、維護、使用狀況、PowerShell、windows defender 高級威脅防護、atp、edr
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
ms.openlocfilehash: 6d10bd932d9414f1460076d3fe7ca8dbed8041a6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185649"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="c976f-104">使用群組原則物件管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c976f-104">Manage Microsoft Defender for Endpoint with Group Policy Objects</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c976f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c976f-105">**Applies to:**</span></span>
- [<span data-ttu-id="c976f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c976f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c976f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c976f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c976f-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c976f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c976f-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c976f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="c976f-110">建議使用 [Microsoft 端點管理員](https://docs.microsoft.com/mem) 來管理組織的威脅防護功能，以供裝置 (也稱為端點) 。</span><span class="sxs-lookup"><span data-stu-id="c976f-110">We recommend using [Microsoft Endpoint Manager](https://docs.microsoft.com/mem) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> <span data-ttu-id="c976f-111">端點管理員包括 [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 和 [Microsoft 端點 Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="c976f-111">Endpoint Manager includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span> <span data-ttu-id="c976f-112">**[深入瞭解端點管理員](https://docs.microsoft.com/mem/endpoint-manager-overview)**。</span><span class="sxs-lookup"><span data-stu-id="c976f-112">**[Learn more about Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)**.</span></span> 

<span data-ttu-id="c976f-113">您可以使用 Azure Active Directory 網域服務中的群組原則物件，管理 Microsoft Defender for Endpoint 中的某些設定。</span><span class="sxs-lookup"><span data-stu-id="c976f-113">You can use Group Policy Objects in Azure Active Directory Domain Services to manage some settings in Microsoft Defender for Endpoint.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="c976f-114">使用群組原則物件設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c976f-114">Configure Microsoft Defender for Endpoint with Group Policy Objects</span></span>

<span data-ttu-id="c976f-115">下表列出您可以執行的各項工作，以使用群組原則物件設定 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="c976f-115">The following table lists various tasks you can perform to configure Microsoft Defender for Endpoint with Group Policy Objects.</span></span>

|<span data-ttu-id="c976f-116">工作</span><span class="sxs-lookup"><span data-stu-id="c976f-116">Task</span></span>  |<span data-ttu-id="c976f-117">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="c976f-117">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="c976f-118">**管理使用者和電腦物件的設定**</span><span class="sxs-lookup"><span data-stu-id="c976f-118">**Manage settings for user and computer objects**</span></span> <br/><br/><span data-ttu-id="c976f-119">*自訂內建的群組原則物件，或建立自訂的群組原則物件和組織單位，以符合您的組織需求。*</span><span class="sxs-lookup"><span data-stu-id="c976f-119">*Customize built-in Group Policy Objects, or create custom Group Policy Objects and organizational units to suit your organizational needs.*</span></span>     |[<span data-ttu-id="c976f-120">管理 Azure Active Directory 網域服務受管理網域中的群組原則</span><span class="sxs-lookup"><span data-stu-id="c976f-120">Administer Group Policy in an Azure Active Directory Domain Services managed domain</span></span>](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|<span data-ttu-id="c976f-121">**設定 Microsoft Defender 防毒軟體**</span><span class="sxs-lookup"><span data-stu-id="c976f-121">**Configure Microsoft Defender Antivirus**</span></span> <br/><br/><span data-ttu-id="c976f-122">*設定防病毒功能 & 功能，包括組織裝置上的原則設定、排除、修正及排程的掃描 (也稱為端點) 。*</span><span class="sxs-lookup"><span data-stu-id="c976f-122">*Configure antivirus features & capabilities, including policy settings, exclusions, remediation, and scheduled scans on your organization's devices (also referred to as endpoints).*</span></span>   |[<span data-ttu-id="c976f-123">使用群組原則設定來設定及管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="c976f-123">Use Group Policy settings to configure and manage Microsoft Defender Antivirus</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[<span data-ttu-id="c976f-124">使用群組原則來啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="c976f-124">Use Group Policy to enable cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|<span data-ttu-id="c976f-125">**管理組織的攻擊面減少規則**</span><span class="sxs-lookup"><span data-stu-id="c976f-125">**Manage your organization's attack surface reduction rules**</span></span> <br/><br/><span data-ttu-id="c976f-126">*從 & 資料夾中排除檔案，或將自訂文字新增至使用者裝置上顯示的通知警示，以自訂攻擊面減少規則。*</span><span class="sxs-lookup"><span data-stu-id="c976f-126">*Customize your attack surface reduction rules by excluding files & folders, or by adding custom text to notification alerts that appear on users' devices.*</span></span> |[<span data-ttu-id="c976f-127">使用群組原則物件自訂攻擊面降低規則</span><span class="sxs-lookup"><span data-stu-id="c976f-127">Customize attack surface reduction rules with Group Policy Objects</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|<span data-ttu-id="c976f-128">**管理 exploit protection 設定**</span><span class="sxs-lookup"><span data-stu-id="c976f-128">**Manage exploit protection settings**</span></span><br/><br/><span data-ttu-id="c976f-129">*您可以自訂 exploit protection 設定、匯入設定檔，然後使用「群組原則」來部署該設定檔。*</span><span class="sxs-lookup"><span data-stu-id="c976f-129">*You can customize your exploit protection settings, import a configuration file, and then use Group Policy to deploy that configuration file.*</span></span>  |[<span data-ttu-id="c976f-130">自訂 exploit protection 設定</span><span class="sxs-lookup"><span data-stu-id="c976f-130">Customize exploit protection settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[<span data-ttu-id="c976f-131">匯入、匯出及部署 exploit protection 設定</span><span class="sxs-lookup"><span data-stu-id="c976f-131">Import, export, and deploy exploit protection configurations</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[<span data-ttu-id="c976f-132">使用群組原則來散佈設定</span><span class="sxs-lookup"><span data-stu-id="c976f-132">Use Group Policy to distribute the configuration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|<span data-ttu-id="c976f-133">**啟用網路保護** ，以協助防止員工在網際網路上使用惡意內容的應用程式</span><span class="sxs-lookup"><span data-stu-id="c976f-133">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="c976f-134">*我們建議您先在測試環境中使用 [審計模式](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) ，以查看哪些應用程式會封鎖，然後再進行部署。*</span><span class="sxs-lookup"><span data-stu-id="c976f-134">*We recommend using [audit mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="c976f-135">使用群組原則開啟網路保護</span><span class="sxs-lookup"><span data-stu-id="c976f-135">Turn on network protection using Group Policy</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|<span data-ttu-id="c976f-136">**設定受管理的資料夾存取** 權以防護勒索軟體</span><span class="sxs-lookup"><span data-stu-id="c976f-136">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="c976f-137">*「[受管理的資料夾存取](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders)」也稱為 antiransomware protection。*</span><span class="sxs-lookup"><span data-stu-id="c976f-137">*[Controlled folder access](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) is also referred to as antiransomware protection.*</span></span>  |[<span data-ttu-id="c976f-138">使用群組原則啟用受控資料夾存取</span><span class="sxs-lookup"><span data-stu-id="c976f-138">Enable controlled folder access using Group Policy</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|<span data-ttu-id="c976f-139">**設定 Microsoft Defender SmartScreen** 以防範網際網路上的惡意網站和檔案。</span><span class="sxs-lookup"><span data-stu-id="c976f-139">**Configure Microsoft Defender SmartScreen** to protect against malicious sites and files on the internet.</span></span>  |[<span data-ttu-id="c976f-140">使用群組原則設定 Microsoft Defender SmartScreen 群組原則和行動裝置管理 (MDM) 設定</span><span class="sxs-lookup"><span data-stu-id="c976f-140">Configure Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings using Group Policy</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|<span data-ttu-id="c976f-141">**設定加密和 BitLocker** 以保護組織裝置執行 Windows 的資訊</span><span class="sxs-lookup"><span data-stu-id="c976f-141">**Configure encryption and BitLocker** to protect information on your organization's devices running Windows</span></span> |[<span data-ttu-id="c976f-142">BitLocker 群組原則設定</span><span class="sxs-lookup"><span data-stu-id="c976f-142">BitLocker Group Policy settings</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|<span data-ttu-id="c976f-143">**設定 Microsoft Defender Credential Guard** 以防護認證盜竊攻擊</span><span class="sxs-lookup"><span data-stu-id="c976f-143">**Configure Microsoft Defender Credential Guard** to protect against credential theft attacks</span></span> |[<span data-ttu-id="c976f-144">使用群組原則啟用 Windows Defender 身分憑證防護</span><span class="sxs-lookup"><span data-stu-id="c976f-144">Enable Windows Defender Credential Guard by using Group Policy</span></span>](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="c976f-145">設定您的 Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="c976f-145">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="c976f-146">若尚未這麼做，請 **將您的 Microsoft Defender 安全中心設定** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 以查看提醒、設定威脅防護功能，以及查看組織整體安全性狀況的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c976f-146">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="c976f-147">您也可以設定使用者是否可以在 Microsoft Defender Security Center 中看到哪些功能。</span><span class="sxs-lookup"><span data-stu-id="c976f-147">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="c976f-148">Microsoft Defender 安全中心概述</span><span class="sxs-lookup"><span data-stu-id="c976f-148">Overview of the Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="c976f-149">Endpoint protection： Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="c976f-149">Endpoint protection: Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="c976f-150">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c976f-150">Next steps</span></span>

- [<span data-ttu-id="c976f-151">取得威脅和弱點管理的概述</span><span class="sxs-lookup"><span data-stu-id="c976f-151">Get an overview of threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="c976f-152">流覽 Microsoft Defender Security Center security operations 儀表板</span><span class="sxs-lookup"><span data-stu-id="c976f-152">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="c976f-153">使用 Intune 管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c976f-153">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
