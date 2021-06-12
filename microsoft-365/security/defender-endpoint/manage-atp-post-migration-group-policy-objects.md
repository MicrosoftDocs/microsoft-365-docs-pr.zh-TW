---
title: 使用群組原則物件管理 Microsoft Defender for Endpoint
description: 瞭解如何使用群組原則物件管理 Microsoft Defender for Endpoint
keywords: 遷移後、管理、作業、維護、使用狀況、PowerShell、Microsoft Defender for Endpoint、edr
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
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: ce204c1a90e57a651cf9c97974a8b35d405878cc
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908289"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="2401c-104">使用群組原則物件管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2401c-104">Manage Microsoft Defender for Endpoint with Group Policy Objects</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2401c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2401c-105">**Applies to:**</span></span>
- [<span data-ttu-id="2401c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2401c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2401c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2401c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2401c-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="2401c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2401c-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2401c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="2401c-110">建議使用[Microsoft 端點管理員](/mem)來管理組織的威脅防護功能，以供裝置 (也稱為端點) 。</span><span class="sxs-lookup"><span data-stu-id="2401c-110">We recommend using [Microsoft Endpoint Manager](/mem) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> <span data-ttu-id="2401c-111">端點管理員包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="2401c-111">Endpoint Manager includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction).</span></span> <span data-ttu-id="2401c-112">**[深入瞭解端點管理員](/mem/endpoint-manager-overview)**。</span><span class="sxs-lookup"><span data-stu-id="2401c-112">**[Learn more about Endpoint Manager](/mem/endpoint-manager-overview)**.</span></span> 

<span data-ttu-id="2401c-113">您可以在 Azure Active Directory 網域服務中使用群組原則物件，以管理 Microsoft Defender for Endpoint 中的某些設定。</span><span class="sxs-lookup"><span data-stu-id="2401c-113">You can use Group Policy Objects in Azure Active Directory Domain Services to manage some settings in Microsoft Defender for Endpoint.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="2401c-114">使用群組原則物件設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2401c-114">Configure Microsoft Defender for Endpoint with Group Policy Objects</span></span>

<span data-ttu-id="2401c-115">下表列出您可以執行的各項工作，以使用群組原則物件設定 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="2401c-115">The following table lists various tasks you can perform to configure Microsoft Defender for Endpoint with Group Policy Objects.</span></span>

|<span data-ttu-id="2401c-116">工作</span><span class="sxs-lookup"><span data-stu-id="2401c-116">Task</span></span>  |<span data-ttu-id="2401c-117">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="2401c-117">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="2401c-118">**管理使用者和電腦物件的設定**</span><span class="sxs-lookup"><span data-stu-id="2401c-118">**Manage settings for user and computer objects**</span></span> <br/><br/><span data-ttu-id="2401c-119">*自訂內建的群組原則物件，或建立自訂的群組原則物件和組織單位，以符合您的組織需求。*</span><span class="sxs-lookup"><span data-stu-id="2401c-119">*Customize built-in Group Policy Objects, or create custom Group Policy Objects and organizational units to suit your organizational needs.*</span></span>     |[<span data-ttu-id="2401c-120">管理 Azure Active Directory 網域服務管理網域中的群組原則</span><span class="sxs-lookup"><span data-stu-id="2401c-120">Administer Group Policy in an Azure Active Directory Domain Services managed domain</span></span>](/azure/active-directory-domain-services/manage-group-policy)   |
|<span data-ttu-id="2401c-121">**設定 Microsoft Defender 防毒軟體**</span><span class="sxs-lookup"><span data-stu-id="2401c-121">**Configure Microsoft Defender Antivirus**</span></span> <br/><br/><span data-ttu-id="2401c-122">*設定防病毒功能 & 功能，包括組織裝置上的原則設定、排除、修正及排程的掃描 (也稱為端點) 。*</span><span class="sxs-lookup"><span data-stu-id="2401c-122">*Configure antivirus features & capabilities, including policy settings, exclusions, remediation, and scheduled scans on your organization's devices (also referred to as endpoints).*</span></span>   |[<span data-ttu-id="2401c-123">使用群組原則設定來設定及管理 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="2401c-123">Use Group Policy settings to configure and manage Microsoft Defender Antivirus</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[<span data-ttu-id="2401c-124">使用群組原則來啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="2401c-124">Use Group Policy to enable cloud-delivered protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|<span data-ttu-id="2401c-125">**管理組織的攻擊面減少規則**</span><span class="sxs-lookup"><span data-stu-id="2401c-125">**Manage your organization's attack surface reduction rules**</span></span> <br/><br/><span data-ttu-id="2401c-126">*從 & 資料夾中排除檔案，或將自訂文字新增至使用者裝置上顯示的通知警示，以自訂攻擊面減少規則。*</span><span class="sxs-lookup"><span data-stu-id="2401c-126">*Customize your attack surface reduction rules by excluding files & folders, or by adding custom text to notification alerts that appear on users' devices.*</span></span> |[<span data-ttu-id="2401c-127">使用群組原則物件自訂攻擊面降低規則</span><span class="sxs-lookup"><span data-stu-id="2401c-127">Customize attack surface reduction rules with Group Policy Objects</span></span>](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|<span data-ttu-id="2401c-128">**管理 exploit protection 設定**</span><span class="sxs-lookup"><span data-stu-id="2401c-128">**Manage exploit protection settings**</span></span><br/><br/><span data-ttu-id="2401c-129">*您可以自訂 exploit protection 設定、匯入設定檔，然後使用「群組原則」來部署該設定檔。*</span><span class="sxs-lookup"><span data-stu-id="2401c-129">*You can customize your exploit protection settings, import a configuration file, and then use Group Policy to deploy that configuration file.*</span></span>  |[<span data-ttu-id="2401c-130">自訂 exploit protection 設定</span><span class="sxs-lookup"><span data-stu-id="2401c-130">Customize exploit protection settings</span></span>](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[<span data-ttu-id="2401c-131">匯入、匯出及部署利用保護群組原則</span><span class="sxs-lookup"><span data-stu-id="2401c-131">Import, export, and deploy exploit protection configurations</span></span>](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[<span data-ttu-id="2401c-132">使用群組原則來散佈設定</span><span class="sxs-lookup"><span data-stu-id="2401c-132">Use Group Policy to distribute the configuration</span></span>](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|<span data-ttu-id="2401c-133">**啟用網路保護** ，以協助防止員工在網際網路上使用惡意內容的應用程式</span><span class="sxs-lookup"><span data-stu-id="2401c-133">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="2401c-134">*我們建議您先在測試環境中使用 [審計模式](/microsoft-365/security/defender-endpoint/evaluate-network-protection) ，以查看哪些應用程式會封鎖，然後再進行部署。*</span><span class="sxs-lookup"><span data-stu-id="2401c-134">*We recommend using [audit mode](/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="2401c-135">使用群組原則開啟網路保護</span><span class="sxs-lookup"><span data-stu-id="2401c-135">Turn on network protection using Group Policy</span></span>](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|<span data-ttu-id="2401c-136">**設定受管理的資料夾存取** 權以防護勒索軟體</span><span class="sxs-lookup"><span data-stu-id="2401c-136">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="2401c-137">*「[受管理的資料夾存取](/microsoft-365/security/defender-endpoint/controlled-folders)」也稱為 antiransomware protection。*</span><span class="sxs-lookup"><span data-stu-id="2401c-137">*[Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders) is also referred to as antiransomware protection.*</span></span>  |[<span data-ttu-id="2401c-138">使用群組原則啟用受控資料夾存取</span><span class="sxs-lookup"><span data-stu-id="2401c-138">Enable controlled folder access using Group Policy</span></span>](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|<span data-ttu-id="2401c-139">**設定 Microsoft Defender SmartScreen** 以防範網際網路上的惡意網站和檔案。</span><span class="sxs-lookup"><span data-stu-id="2401c-139">**Configure Microsoft Defender SmartScreen** to protect against malicious sites and files on the internet.</span></span>  |[<span data-ttu-id="2401c-140">使用群組原則設定 Microsoft Defender SmartScreen 群組原則和行動裝置管理 (MDM) 設定</span><span class="sxs-lookup"><span data-stu-id="2401c-140">Configure Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings using Group Policy</span></span>](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|<span data-ttu-id="2401c-141">**設定加密和 BitLocker** ，以保護組織執行 Windows 的裝置資訊</span><span class="sxs-lookup"><span data-stu-id="2401c-141">**Configure encryption and BitLocker** to protect information on your organization's devices running Windows</span></span> |[<span data-ttu-id="2401c-142">BitLocker群組原則設定</span><span class="sxs-lookup"><span data-stu-id="2401c-142">BitLocker Group Policy settings</span></span>](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|<span data-ttu-id="2401c-143">**設定 Microsoft Defender Credential Guard** 以防護認證盜竊攻擊</span><span class="sxs-lookup"><span data-stu-id="2401c-143">**Configure Microsoft Defender Credential Guard** to protect against credential theft attacks</span></span> |[<span data-ttu-id="2401c-144">使用群組原則啟用 Windows Defender Credential Guard</span><span class="sxs-lookup"><span data-stu-id="2401c-144">Enable Windows Defender Credential Guard by using Group Policy</span></span>](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="2401c-145">設定 Microsoft Defender 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="2401c-145">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="2401c-146">若尚未這麼做，請設定 Microsoft 365 Defender 入口網站以查看提醒、設定威脅防護功能，以及查看組織整體安全性狀況的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2401c-146">If you haven't already done so, configure your Microsoft 365 Defender portal to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> <span data-ttu-id="2401c-147">請參閱[Microsoft Defender 資訊安全中心](microsoft-defender-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2401c-147">See [Microsoft Defender Security Center](microsoft-defender-security-center.md).</span></span> <span data-ttu-id="2401c-148">您也可以設定使用者是否可以在 Microsoft 365 Defender 入口網站中看到使用者功能。</span><span class="sxs-lookup"><span data-stu-id="2401c-148">You can also configure whether and what features end users can see in the Microsoft 365 Defender portal.</span></span>

- [<span data-ttu-id="2401c-149">Microsoft Defender 資訊安全中心綜述</span><span class="sxs-lookup"><span data-stu-id="2401c-149">Overview of the Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="2401c-150">Endpoint protection： Microsoft Defender 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="2401c-150">Endpoint protection: Microsoft Defender Security Center</span></span>](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="2401c-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2401c-151">Next steps</span></span>

- [<span data-ttu-id="2401c-152">深入瞭解威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="2401c-152">Get an overview of threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="2401c-153">流覽 Microsoft Defender 資訊安全中心的安全性運作儀表板</span><span class="sxs-lookup"><span data-stu-id="2401c-153">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="2401c-154">使用 Intune 管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2401c-154">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
