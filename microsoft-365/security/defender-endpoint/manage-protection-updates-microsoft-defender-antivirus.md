---
title: 管理 Microsoft Defender 防毒軟體接收更新的方式與位置
description: 管理 Microsoft Defender 防毒軟體如何接收保護更新的後備順序。
keywords: 更新，安全性基準，保護，回退順序，ADL，MMPC，UNC，檔案路徑，共用，wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 35873b371e773e793ae966a338150e2e5e256a42
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926028"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a><span data-ttu-id="b4d05-104">管理 Microsoft Defender 防毒軟體保護更新的來源</span><span class="sxs-lookup"><span data-stu-id="b4d05-104">Manage the sources for Microsoft Defender Antivirus protection updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b4d05-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b4d05-105">**Applies to:**</span></span>

- [<span data-ttu-id="b4d05-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b4d05-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

<span data-ttu-id="b4d05-107">保持最新的防防毒保護是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="b4d05-107">Keeping your antivirus protection up to date is critical.</span></span> <span data-ttu-id="b4d05-108">有兩個元件可管理 Microsoft Defender 防毒軟體的保護更新：</span><span class="sxs-lookup"><span data-stu-id="b4d05-108">There are two components to managing protection updates for Microsoft Defender Antivirus:</span></span> 
- <span data-ttu-id="b4d05-109">下載更新的 *位置*;和</span><span class="sxs-lookup"><span data-stu-id="b4d05-109">*Where* the updates are downloaded from; and</span></span> 
- <span data-ttu-id="b4d05-110">下載和套用更新 *時*。</span><span class="sxs-lookup"><span data-stu-id="b4d05-110">*When* updates are downloaded and applied.</span></span> 

<span data-ttu-id="b4d05-111">本文說明如何指定應從何處下載更新 (這也稱為「回退訂單) 」。</span><span class="sxs-lookup"><span data-stu-id="b4d05-111">This article describes how to specify from where updates should be downloaded (this is also known as the fallback order).</span></span> <span data-ttu-id="b4d05-112">請參閱[管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)主題，以取得更新的運作方式，以及如何設定更新的其他方面 (例如排程更新) 。</span><span class="sxs-lookup"><span data-stu-id="b4d05-112">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md) topic for an overview on how updates work, and how to configure other aspects of updates (such as scheduling updates).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4d05-113">Microsoft Defender 防毒軟體安全情報更新是透過 Windows 更新及從2019年10月21日星期一開始，所有的安全性情報更新皆 SHA-2 以獨佔方式簽署。</span><span class="sxs-lookup"><span data-stu-id="b4d05-113">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update and starting Monday, October 21, 2019, all security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="b4d05-114">您的裝置必須更新為支援 SHA-2，才能更新您的安全性情報。</span><span class="sxs-lookup"><span data-stu-id="b4d05-114">Your devices must be updated to support SHA-2 in order to update your security intelligence.</span></span> <span data-ttu-id="b4d05-115">若要深入瞭解，請參閱[2019 SHA-2 Windows 和 WSUS 的代碼簽署支援需求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b4d05-115">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>  


<a id="fallback-order"></a>

## <a name="fallback-order"></a><span data-ttu-id="b4d05-116">後備順序</span><span class="sxs-lookup"><span data-stu-id="b4d05-116">Fallback order</span></span>

<span data-ttu-id="b4d05-117">一般來說，您可以根據網路設定，設定端點以個別的方式從主要來源下載更新，並依照優先順序順序從其他來源開始下載更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-117">Typically, you configure endpoints to individually download updates from a primary source followed by other sources in order of priority, based on your network configuration.</span></span> <span data-ttu-id="b4d05-118">更新是以您指定的順序從來源取得。</span><span class="sxs-lookup"><span data-stu-id="b4d05-118">Updates are obtained from sources in the order you specify.</span></span> <span data-ttu-id="b4d05-119">如果來源無法使用，則會立即使用清單中的下一個來源。</span><span class="sxs-lookup"><span data-stu-id="b4d05-119">If a source is not available, the next source in the list is used immediately.</span></span>

<span data-ttu-id="b4d05-120">發佈更新時，會套用某些邏輯來減少更新的大小。</span><span class="sxs-lookup"><span data-stu-id="b4d05-120">When updates are published, some logic is applied to minimize the size of the update.</span></span> <span data-ttu-id="b4d05-121">在大多數情況下，只有最新的更新和目前安裝的更新之間的差異，也就是下載並套用裝置上的 delta) 所 (。</span><span class="sxs-lookup"><span data-stu-id="b4d05-121">In most cases, only the differences between the latest update and the update that is currently installed (this is referred to as the delta) on the device is downloaded and applied.</span></span> <span data-ttu-id="b4d05-122">不過，差異大小取決於兩個主要因素：</span><span class="sxs-lookup"><span data-stu-id="b4d05-122">However, the size of the delta depends on two main factors:</span></span>
- <span data-ttu-id="b4d05-123">裝置上最後一次更新的年齡;和</span><span class="sxs-lookup"><span data-stu-id="b4d05-123">The age of the last update on the device; and</span></span> 
- <span data-ttu-id="b4d05-124">用於下載及套用更新的來源。</span><span class="sxs-lookup"><span data-stu-id="b4d05-124">The source used to download and apply updates.</span></span> 

<span data-ttu-id="b4d05-125">端點上的更新越舊，下載將會變得較大。</span><span class="sxs-lookup"><span data-stu-id="b4d05-125">The older the updates on an endpoint, the larger the download will be.</span></span> <span data-ttu-id="b4d05-126">不過，您也必須同時考慮下載頻率。</span><span class="sxs-lookup"><span data-stu-id="b4d05-126">However, you must also consider download frequency as well.</span></span> <span data-ttu-id="b4d05-127">較頻繁的更新排程可能會產生更多的網路使用量，但較低的排程可能會導致每次下載較大的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="b4d05-127">A more frequent update schedule can result in more network usage, whereas a less-frequent schedule can result in larger file sizes per download.</span></span> 

<span data-ttu-id="b4d05-128">有五個位置可讓您指定端點應該取得更新的位置：</span><span class="sxs-lookup"><span data-stu-id="b4d05-128">There are five locations where you can specify where an endpoint should obtain updates:</span></span> 

- [<span data-ttu-id="b4d05-129">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="b4d05-129">Microsoft Update</span></span>](https://support.microsoft.com/help/12373/windows-update-faq)
- [<span data-ttu-id="b4d05-130">Windows伺服器更新服務</span><span class="sxs-lookup"><span data-stu-id="b4d05-130">Windows Server Update Service</span></span>](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [<span data-ttu-id="b4d05-131">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b4d05-131">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/core/servers/manage/updates)
- [<span data-ttu-id="b4d05-132">網路檔共用</span><span class="sxs-lookup"><span data-stu-id="b4d05-132">Network file share</span></span>](#unc-share)
- <span data-ttu-id="b4d05-133">[Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性智慧更新](https://www.microsoft.com/en-us/wdsi/defenderupdates) (您的原則及登錄可能會列為 Microsoft 惡意程式碼防護中心 (MMPC) 安全性智慧，其為先前名稱。 ) </span><span class="sxs-lookup"><span data-stu-id="b4d05-133">[Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) (Your policy and registry might have this listed as Microsoft Malware Protection Center (MMPC) security intelligence, its former name.)</span></span>

<span data-ttu-id="b4d05-134">為了確保最佳的保護層級，Microsoft 更新可讓您快速發行，這表示經常下載較小的下載。</span><span class="sxs-lookup"><span data-stu-id="b4d05-134">To ensure the best level of protection, Microsoft Update allows for rapid releases, which means smaller downloads on a frequent basis.</span></span> <span data-ttu-id="b4d05-135">Windows Server Update Service、Microsoft Endpoint Configuration Manager 和 Microsoft security 情報更新來源，會提供較不常用的更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-135">The Windows Server Update Service, Microsoft Endpoint Configuration Manager, and Microsoft security intelligence updates sources deliver less frequent updates.</span></span> <span data-ttu-id="b4d05-136">因此，差異可能會變大，因此會產生較大的下載。</span><span class="sxs-lookup"><span data-stu-id="b4d05-136">Thus, the delta can be larger, resulting in larger downloads.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b4d05-137">如果您已將[Microsoft Security 情報頁面](https://www.microsoft.com/security/portal/definitions/adl.aspx)更新為 Windows Server Update Service 或 Microsoft Update 之後的回退來源，當目前的更新視為過期時，將只從安全性智慧更新下載更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-137">If you have set [Microsoft Security intelligence page](https://www.microsoft.com/security/portal/definitions/adl.aspx) updates as a fallback source after Windows Server Update Service or Microsoft Update, updates are only downloaded from security intelligence updates when the current update is considered out-of-date.</span></span> <span data-ttu-id="b4d05-138"> (預設會連續七天內，不能從 Windows 伺服器更新服務或 Microsoft Update services) 套用更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-138">(By default, this is seven consecutive days of not being able to apply updates from the Windows Server Update Service or Microsoft Update services).</span></span>
> <span data-ttu-id="b4d05-139">不過，您可以 [設定將保護報告為過期前的天數](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)。</span><span class="sxs-lookup"><span data-stu-id="b4d05-139">You can, however, [set the number of days before protection is reported as out-of-date](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span><p>
> <span data-ttu-id="b4d05-140">2019年10月21日當星期一開始，安全性智慧更新將會以獨佔方式 SHA-2。</span><span class="sxs-lookup"><span data-stu-id="b4d05-140">Starting Monday, October 21, 2019, security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="b4d05-141">裝置必須更新為支援 SHA-2，才能取得最新的安全性智慧更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-141">Devices must be updated to support SHA-2 in order to get the latest security intelligence updates.</span></span> <span data-ttu-id="b4d05-142">若要深入瞭解，請參閱[2019 SHA-2 Windows 和 WSUS 的代碼簽署支援需求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b4d05-142">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>

<span data-ttu-id="b4d05-143">每個來源都有一般的案例，取決於您的網路的設定方式，以及其發佈更新的頻率，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="b4d05-143">Each source has typical scenarios that depend on how your network is configured, in addition to how often they publish updates, as described in the following table:</span></span>

|<span data-ttu-id="b4d05-144">位置</span><span class="sxs-lookup"><span data-stu-id="b4d05-144">Location</span></span> | <span data-ttu-id="b4d05-145">範例案例</span><span class="sxs-lookup"><span data-stu-id="b4d05-145">Sample scenario</span></span> |
|---|---|
|<span data-ttu-id="b4d05-146">Windows伺服器更新服務</span><span class="sxs-lookup"><span data-stu-id="b4d05-146">Windows Server Update Service</span></span> | <span data-ttu-id="b4d05-147">您正在使用 Windows Server Update 服務來管理網路的更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-147">You are using Windows Server Update Service to manage updates for your network.</span></span>|
|<span data-ttu-id="b4d05-148">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="b4d05-148">Microsoft Update</span></span> | <span data-ttu-id="b4d05-149">您想要讓端點直接連接至 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="b4d05-149">You want your endpoints to connect directly to Microsoft Update.</span></span> <span data-ttu-id="b4d05-150">這對於未連接到商業網路的不規則端點非常有用，否則您不會使用 Windows Server Update 服務來管理更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-150">This can be useful for endpoints that irregularly connect to your enterprise network, or if you do not use Windows Server Update Service to manage your updates.</span></span>|
|<span data-ttu-id="b4d05-151">檔案共用</span><span class="sxs-lookup"><span data-stu-id="b4d05-151">File share</span></span> | <span data-ttu-id="b4d05-152">您有未連接網際網路的裝置 (例如 Vm) 。</span><span class="sxs-lookup"><span data-stu-id="b4d05-152">You have non-Internet-connected devices (such as VMs).</span></span> <span data-ttu-id="b4d05-153">您可以使用網際網路連線的 VM 主機，將更新下載至網路共用，Vm 便可以從該網路共用取得更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-153">You can use your Internet-connected VM host to download the updates to a network share, from which the VMs can obtain the updates.</span></span> <span data-ttu-id="b4d05-154">請參閱 [vdi 部署指南](deployment-vdi-microsoft-defender-antivirus.md) 瞭解如何在虛擬桌面基礎結構 (vdi) 環境中使用檔共用。</span><span class="sxs-lookup"><span data-stu-id="b4d05-154">See the [VDI deployment guide](deployment-vdi-microsoft-defender-antivirus.md) for how file shares can be used in virtual desktop infrastructure (VDI) environments.</span></span>|
|<span data-ttu-id="b4d05-155">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="b4d05-155">Microsoft Endpoint Manager</span></span> | <span data-ttu-id="b4d05-156">您正在使用 Microsoft 端點管理員來更新您的端點。</span><span class="sxs-lookup"><span data-stu-id="b4d05-156">You are using Microsoft Endpoint Manager to update your endpoints.</span></span>|
|<span data-ttu-id="b4d05-157">Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性情報更新 (先前稱為 MMPC) </span><span class="sxs-lookup"><span data-stu-id="b4d05-157">Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware (formerly referred to as MMPC)</span></span> |<span data-ttu-id="b4d05-158">[請確定您的裝置已更新，以支援 SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b4d05-158">[Make sure your devices are updated to support SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span> <span data-ttu-id="b4d05-159">Microsoft Defender 防毒軟體安全情報更新是透過 Windows 更新，並在星期一的2019年10月21日開始，安全性情報更新將會以獨佔方式 SHA-2 簽署。</span><span class="sxs-lookup"><span data-stu-id="b4d05-159">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update, and starting Monday October 21, 2019 security intelligence updates will be SHA-2 signed exclusively.</span></span> <br/><span data-ttu-id="b4d05-160">因為最近的感染，或為 [VDI 部署](deployment-vdi-microsoft-defender-antivirus.md)提供強基底影像，所以請下載最新的保護更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-160">Download the latest protection updates because of a recent infection or to help provision a strong, base image for [VDI deployment](deployment-vdi-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b4d05-161">此選項一般只會用作最後的回退來源，而非主要來源。</span><span class="sxs-lookup"><span data-stu-id="b4d05-161">This option should generally be used only as a final fallback source, and not the primary source.</span></span> <span data-ttu-id="b4d05-162">只有在[指定的天數](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)無法從 Windows Server update Service 或 Microsoft Update 下載更新時，才會使用此值。</span><span class="sxs-lookup"><span data-stu-id="b4d05-162">It will only be used if updates cannot be downloaded from Windows Server Update Service or Microsoft Update for [a specified number of days](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span>|

<span data-ttu-id="b4d05-163">您可以管理「群組原則」、「Microsoft Endpoint Configuration Manager」、「PowerShell Cmdlet」和 WMI 所用的更新來源的順序。</span><span class="sxs-lookup"><span data-stu-id="b4d05-163">You can manage the order in which update sources are used with Group Policy, Microsoft Endpoint Configuration Manager, PowerShell cmdlets, and WMI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4d05-164">如果您將 Windows Server Update Service 設定為下載位置，則不論您用來指定位置的管理工具為何，都必須核准更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-164">If you set Windows Server Update Service as a download location, you must approve the updates, regardless of the management tool you use to specify the location.</span></span> <span data-ttu-id="b4d05-165">您可以使用 Windows Server Update 服務設定自動核准規則，這在一天內至少有一次的更新到達時，這會很有用。</span><span class="sxs-lookup"><span data-stu-id="b4d05-165">You can set up an automatic approval rule with Windows Server Update Service, which might be useful as updates arrive at least once a day.</span></span> <span data-ttu-id="b4d05-166">若要深入瞭解，請參閱[同步處理 endpoint protection 更新中的獨立 Windows 伺服器更新服務](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="b4d05-166">To learn more, see [synchronize endpoint protection updates in standalone Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

<span data-ttu-id="b4d05-167">本文中的程式會先說明如何設定順序，以及如何設定 [檔案 **共用** ] 選項（如果已啟用的話）。</span><span class="sxs-lookup"><span data-stu-id="b4d05-167">The procedures in this article first describe how to set the order, and then how to set up the **File share** option if you have enabled it.</span></span>

## <a name="use-group-policy-to-manage-the-update-location"></a><span data-ttu-id="b4d05-168">使用群組原則來管理更新位置</span><span class="sxs-lookup"><span data-stu-id="b4d05-168">Use Group Policy to manage the update location</span></span>

1. <span data-ttu-id="b4d05-169">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b4d05-169">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b4d05-170">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="b4d05-170">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b4d05-171">按一下 [ **原則** 然後是系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="b4d05-171">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b4d05-172">展開樹狀目錄，以 **Windows 元件 > Windows Defender >** 簽章更新，並設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="b4d05-172">Expand the tree to **Windows components > Windows Defender > Signature updates** and configure the following settings:</span></span>

   1.  <span data-ttu-id="b4d05-173">按兩下 [ **定義下載安全性情報更新的來源順序** ] 設定，並將此選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="b4d05-173">Double-click the **Define the order of sources for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   2.  <span data-ttu-id="b4d05-174">輸入來源的順序，以單一管道分隔，例如： `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` ，如下列螢幕擷取畫面所示。</span><span class="sxs-lookup"><span data-stu-id="b4d05-174">Enter the order of sources, separated by a single pipe, for example: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`, as shown in the following screenshot.</span></span>

   ![列出來源順序的群組原則設定的螢幕擷取畫面](images/defender/wdav-order-update-sources.png)

   3. <span data-ttu-id="b4d05-176">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="b4d05-176">Click **OK**.</span></span> <span data-ttu-id="b4d05-177">這會設定保護更新來源的順序。</span><span class="sxs-lookup"><span data-stu-id="b4d05-177">This will set the order of protection update sources.</span></span>

   4. <span data-ttu-id="b4d05-178">按兩下 [定義檔案 **共用以下載安全性情報更新** ] 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="b4d05-178">Double-click the **Define file shares for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   5. <span data-ttu-id="b4d05-179">輸入檔案共用來源。</span><span class="sxs-lookup"><span data-stu-id="b4d05-179">Enter the file share source.</span></span> <span data-ttu-id="b4d05-180">如果您有多個來源，請依照應該使用的順序輸入每個來源，並以單一管道分隔。</span><span class="sxs-lookup"><span data-stu-id="b4d05-180">If you have multiple sources, enter each source in the order they should be used, separated by a single pipe.</span></span> <span data-ttu-id="b4d05-181">使用 [標準 UNC 標記法來表示](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) 路徑，例如： `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` 。</span><span class="sxs-lookup"><span data-stu-id="b4d05-181">Use [standard UNC notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) for denoting the path, for example: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`.</span></span>  <span data-ttu-id="b4d05-182">如果您沒有輸入任何路徑，當 VM 下載更新時，將會略過此來源。</span><span class="sxs-lookup"><span data-stu-id="b4d05-182">If you do not enter any paths, then this source will be skipped when the VM downloads updates.</span></span>

   6. <span data-ttu-id="b4d05-183">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="b4d05-183">Click **OK**.</span></span> <span data-ttu-id="b4d05-184">當您在 [ **定義來源的順序** ...] 群組原則設定中參照該來源時，這會設定共用檔共用的順序。</span><span class="sxs-lookup"><span data-stu-id="b4d05-184">This will set the order of file shares when that source is referenced in the **Define the order of sources...** group policy setting.</span></span>

> [!NOTE]
> <span data-ttu-id="b4d05-185">針對 Windows 10，版本1703至（含）1809，原則路徑是 **Windows 元件 > Microsoft Defender 防毒軟體 >** Windows 10 的簽章更新，版本1903，原則路徑是 **Windows 元件 > Microsoft Defender 防毒軟體 > 安全性智慧更新**</span><span class="sxs-lookup"><span data-stu-id="b4d05-185">For Windows 10, versions 1703 up to and including 1809, the policy path is **Windows Components > Microsoft Defender Antivirus > Signature Updates** For Windows 10, version 1903, the policy path is **Windows Components > Microsoft Defender Antivirus > Security Intelligence Updates**</span></span>

## <a name="use-configuration-manager-to-manage-the-update-location"></a><span data-ttu-id="b4d05-186">使用 Configuration Manager 管理更新位置</span><span class="sxs-lookup"><span data-stu-id="b4d05-186">Use Configuration Manager to manage the update location</span></span>

<span data-ttu-id="b4d05-187">請參閱[設定 Endpoint Protection 的安全性情報更新](/configmgr/protect/deploy-use/endpoint-definition-updates)，以取得設定 Microsoft 端點管理員 (目前的分支) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b4d05-187">See [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a><span data-ttu-id="b4d05-188">使用 PowerShell Cmdlet 來管理更新位置</span><span class="sxs-lookup"><span data-stu-id="b4d05-188">Use PowerShell cmdlets to manage the update location</span></span>

<span data-ttu-id="b4d05-189">使用下列 PowerShell Cmdlet 來設定更新順序。</span><span class="sxs-lookup"><span data-stu-id="b4d05-189">Use the following PowerShell cmdlets to set the update order.</span></span>

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
<span data-ttu-id="b4d05-190">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="b4d05-190">See the following articles for more information:</span></span>
- [<span data-ttu-id="b4d05-191">MpPreference-SignatureFallbackOrder</span><span class="sxs-lookup"><span data-stu-id="b4d05-191">Set-MpPreference -SignatureFallbackOrder</span></span>](/powershell/module/defender/set-mppreference)
- [<span data-ttu-id="b4d05-192">MpPreference-SignatureDefinitionUpdateFileSharesSource</span><span class="sxs-lookup"><span data-stu-id="b4d05-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span></span>](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [<span data-ttu-id="b4d05-193">使用 PowerShell Cmdlet 來設定及執行 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="b4d05-193">Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b4d05-194">Defender Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b4d05-194">Defender cmdlets</span></span>](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a><span data-ttu-id="b4d05-195">使用 Windows 管理指令 (WMI) 管理更新位置</span><span class="sxs-lookup"><span data-stu-id="b4d05-195">Use Windows Management Instruction (WMI) to manage the update location</span></span>

<span data-ttu-id="b4d05-196">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="b4d05-196">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

<span data-ttu-id="b4d05-197">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="b4d05-197">See the following articles for more information:</span></span>
- [<span data-ttu-id="b4d05-198">Windows DefenderWMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="b4d05-198">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a><span data-ttu-id="b4d05-199">使用行動裝置管理 (MDM) 管理更新位置</span><span class="sxs-lookup"><span data-stu-id="b4d05-199">Use Mobile Device Management (MDM) to manage the update location</span></span>

<span data-ttu-id="b4d05-200">請參閱 [原則 CSP-Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) 以取得設定 MDM 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b4d05-200">See [Policy CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) for details on configuring MDM.</span></span>

## <a name="what-if-were-using-a-third-party-vendor"></a><span data-ttu-id="b4d05-201">如果我們使用協力廠商廠商，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="b4d05-201">What if we're using a third-party vendor?</span></span>

<span data-ttu-id="b4d05-202">本文說明如何設定及管理 Microsoft Defender 防毒軟體的更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-202">This article describes how to configure and manage updates for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="b4d05-203">不過，協力廠商廠商可用於執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="b4d05-203">However, third-party vendors can be used to perform these tasks.</span></span> 

<span data-ttu-id="b4d05-204">例如，Contoso 已聘用 Fabrikam 以管理其安全性解決方案，其中包括 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="b4d05-204">For example, suppose that Contoso has hired Fabrikam to manage their security solution, which includes Microsoft Defender Antivirus.</span></span> <span data-ttu-id="b4d05-205">Fabrikam 一般使用[Windows 管理工具](./use-wmi-microsoft-defender-antivirus.md)、 [PowerShell Cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md)或[Windows 命令列](./command-line-arguments-microsoft-defender-antivirus.md)來部署修補程式和更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-205">Fabrikam typically uses [Windows Management Instrumentation](./use-wmi-microsoft-defender-antivirus.md), [PowerShell cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md), or [Windows command-line](./command-line-arguments-microsoft-defender-antivirus.md) to deploy patches and updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="b4d05-206">Microsoft 不會測試協力廠商的解決方案來管理 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="b4d05-206">Microsoft does not test third-party solutions for managing Microsoft Defender Antivirus.</span></span>

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a><span data-ttu-id="b4d05-207">建立安全性智慧更新的 UNC 共用</span><span class="sxs-lookup"><span data-stu-id="b4d05-207">Create a UNC share for security intelligence updates</span></span>

<span data-ttu-id="b4d05-208">使用排程任務，設定網路檔案共用 (UNC/已映射的磁片磁碟機) 從 MMPC 網站下載安全性智慧更新。</span><span class="sxs-lookup"><span data-stu-id="b4d05-208">Set up a network file share (UNC/mapped drive) to download security intelligence updates from the MMPC site by using a scheduled task.</span></span>

1. <span data-ttu-id="b4d05-209">在您想要布建共用及下載更新的系統上，建立您要儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="b4d05-209">On the system on which you want to provision the share and download the updates, create a folder to which you will save the script.</span></span>
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. <span data-ttu-id="b4d05-210">建立您將簽章更新儲存至的資料夾。</span><span class="sxs-lookup"><span data-stu-id="b4d05-210">Create the folder to which you will save the signature updates.</span></span>
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. <span data-ttu-id="b4d05-211">從 [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)下載 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="b4d05-211">Download the PowerShell script from [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).</span></span>

4. <span data-ttu-id="b4d05-212">按一下 [ **手動下載**]。</span><span class="sxs-lookup"><span data-stu-id="b4d05-212">Click **Manual Download**.</span></span>

5. <span data-ttu-id="b4d05-213">按一下 **[下載原始 nupkg**] 檔案。</span><span class="sxs-lookup"><span data-stu-id="b4d05-213">Click **Download the raw nupkg file**.</span></span>

6. <span data-ttu-id="b4d05-214">解壓縮檔。</span><span class="sxs-lookup"><span data-stu-id="b4d05-214">Extract the file.</span></span>

7. <span data-ttu-id="b4d05-215">將檔案 SignatureDownloadCustomTask.ps1 複製到您先前建立的資料夾 C:\Tool\PS-Scripts\。</span><span class="sxs-lookup"><span data-stu-id="b4d05-215">Copy the file SignatureDownloadCustomTask.ps1 to the folder you previously created, C:\Tool\PS-Scripts\ .</span></span>

8. <span data-ttu-id="b4d05-216">使用命令列來設定排程的任務。</span><span class="sxs-lookup"><span data-stu-id="b4d05-216">Use the command line to set up the scheduled task.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b4d05-217">有兩種類型的更新：完整和 delta。</span><span class="sxs-lookup"><span data-stu-id="b4d05-217">There are two types of updates: full and delta.</span></span>
   - <span data-ttu-id="b4d05-218">X64 delta：</span><span class="sxs-lookup"><span data-stu-id="b4d05-218">For x64 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="b4d05-219">X64 full：</span><span class="sxs-lookup"><span data-stu-id="b4d05-219">For x64 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="b4d05-220">針對 x86 delta：</span><span class="sxs-lookup"><span data-stu-id="b4d05-220">For x86 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="b4d05-221">若為 x86 已滿：</span><span class="sxs-lookup"><span data-stu-id="b4d05-221">For x86 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

    > [!NOTE]
    > <span data-ttu-id="b4d05-222">建立排程的任務後，您可以在 [Microsoft Windows \ Windows Defender] 下的工作排程器中找到這些工作。</span><span class="sxs-lookup"><span data-stu-id="b4d05-222">When the scheduled tasks are created, you can find these in the Task Scheduler under Microsoft\Windows\Windows Defender</span></span>
9. <span data-ttu-id="b4d05-223">手動執行每項工作，並確認下列資料夾中的資料 (mpam-d.exe、mpam-fe.exe 及 nis_full.exe)  (您可能已選擇不同的位置) ：</span><span class="sxs-lookup"><span data-stu-id="b4d05-223">Run each task manually and verify that you have data (mpam-d.exe, mpam-fe.exe, and nis_full.exe) in the following folders (you might have chosen different locations):</span></span>

   - <span data-ttu-id="b4d05-224">C:\Temp\TempSigs\x86</span><span class="sxs-lookup"><span data-stu-id="b4d05-224">C:\Temp\TempSigs\x86</span></span>
   - <span data-ttu-id="b4d05-225">C:\Temp\TempSigs\x64</span><span class="sxs-lookup"><span data-stu-id="b4d05-225">C:\Temp\TempSigs\x64</span></span>

   <span data-ttu-id="b4d05-226">如果排程的任務失敗，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b4d05-226">If the scheduled task fails, run the following commands:</span></span>

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```
    > [!NOTE]
    > <span data-ttu-id="b4d05-227">問題也可能是因為執行原則。</span><span class="sxs-lookup"><span data-stu-id="b4d05-227">Issues could also be due to execution policy.</span></span>
    
10. <span data-ttu-id="b4d05-228">建立指向 C:\Temp\TempSigs (例如 server\updates) 的共用 \\ 。</span><span class="sxs-lookup"><span data-stu-id="b4d05-228">Create a share pointing to C:\Temp\TempSigs (e.g. \\server\updates).</span></span>
    > [!NOTE]
    > <span data-ttu-id="b4d05-229">驗證的使用者至少必須具有「讀取」存取權。</span><span class="sxs-lookup"><span data-stu-id="b4d05-229">At a minimum, authenticated users must have "Read" access.</span></span>
11. <span data-ttu-id="b4d05-230">將原則中的共用位置設定為共用。</span><span class="sxs-lookup"><span data-stu-id="b4d05-230">Set the share location in the policy to the share.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4d05-231">請勿在路徑中新增 x64 (或 x86) 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b4d05-231">Do not add the x64 (or x86) folder in the path.</span></span> <span data-ttu-id="b4d05-232">mpcmdrun.exe 程式會自動新增此程式。</span><span class="sxs-lookup"><span data-stu-id="b4d05-232">The mpcmdrun.exe process adds it automatically.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b4d05-233">相關文章</span><span class="sxs-lookup"><span data-stu-id="b4d05-233">Related articles</span></span>

- [<span data-ttu-id="b4d05-234">部署 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="b4d05-234">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b4d05-235">管理 Microsoft Defender 防毒軟體更新及套用基準</span><span class="sxs-lookup"><span data-stu-id="b4d05-235">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b4d05-236">管理已過期端點的更新</span><span class="sxs-lookup"><span data-stu-id="b4d05-236">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b4d05-237">管理事件型強制更新</span><span class="sxs-lookup"><span data-stu-id="b4d05-237">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b4d05-238">管理行動裝置和 Vm 的更新</span><span class="sxs-lookup"><span data-stu-id="b4d05-238">Manage updates for mobile devices and VMs</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b4d05-239">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="b4d05-239">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
