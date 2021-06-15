---
title: 在 Microsoft Defender 防毒軟體中開啟雲端傳送保護
description: 開啟雲端提供的保護，以利用快速和高級的保護功能。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，cloud，第一次看到封鎖
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: e7b7a0ba5c301829633c27f3add8f7f7daa70dfd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924704"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="86c6f-104">開啟雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="86c6f-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="86c6f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="86c6f-105">**Applies to:**</span></span>

- [<span data-ttu-id="86c6f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="86c6f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="86c6f-107">Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞到網路和端點。</span><span class="sxs-lookup"><span data-stu-id="86c6f-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="86c6f-108">雖然它稱為雲端服務，但不只是保護儲存在雲端中的檔案;相反地，它會使用分散式資源和機器教學，以比傳統的安全性智慧更新速度更快的速率來提供對端點的保護。</span><span class="sxs-lookup"><span data-stu-id="86c6f-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="86c6f-109">Microsoft Defender 防毒軟體會使用多個偵測及防護技術來提供準確、即時和智慧的保護。</span><span class="sxs-lookup"><span data-stu-id="86c6f-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="86c6f-110">[深入瞭解 Microsoft Defender 在第二代端點的核心的高級技術](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="86c6f-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="86c6f-111">您可以多種方式開啟或關閉 Microsoft Defender 防毒軟體雲端提供的保護：</span><span class="sxs-lookup"><span data-stu-id="86c6f-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="86c6f-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="86c6f-112">Microsoft Intune</span></span>
- <span data-ttu-id="86c6f-113">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="86c6f-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="86c6f-114">群組原則</span><span class="sxs-lookup"><span data-stu-id="86c6f-114">Group Policy</span></span>
- <span data-ttu-id="86c6f-115">PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86c6f-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="86c6f-116">您也可以在 Windows 安全性應用程式的個別用戶端中開啟或關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="86c6f-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="86c6f-117">請參閱[使用 Microsoft 雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)，以取得 Microsoft Defender 防毒軟體雲端提供保護的概述。</span><span class="sxs-lookup"><span data-stu-id="86c6f-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="86c6f-118">如需特定網路連線需求的詳細資訊，以確保端點能夠連線至雲端提供的保護服務，請參閱 [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="86c6f-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="86c6f-119">在 Windows 10 中，本主題所述的 **基本** 和 **高級** 報告選項之間沒有任何差異。</span><span class="sxs-lookup"><span data-stu-id="86c6f-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="86c6f-120">這是傳統的區別，而且選擇任一設定會導致相同的雲端傳送層級保護。</span><span class="sxs-lookup"><span data-stu-id="86c6f-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="86c6f-121">共用的資訊類型或數量不會有任何差異。</span><span class="sxs-lookup"><span data-stu-id="86c6f-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="86c6f-122">如需我們收集之專案的詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=521839)。</span><span class="sxs-lookup"><span data-stu-id="86c6f-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="86c6f-123">使用 Intune 開啟雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="86c6f-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="86c6f-124">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="86c6f-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="86c6f-125">在 [ **首頁** ] 窗格中，選取 [裝置設定] **> 設定檔**。</span><span class="sxs-lookup"><span data-stu-id="86c6f-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="86c6f-126">選取您要設定的 **裝置限制** 配置檔案類型。</span><span class="sxs-lookup"><span data-stu-id="86c6f-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="86c6f-127">如果您需要建立新的 **裝置限制** 配置檔案類型，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="86c6f-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="86c6f-128">選取 [**屬性**  >  **設定：編輯**  >  **Microsoft Defender 防毒軟體**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="86c6f-129">在 **雲端提供的保護** 參數上，選取 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="86c6f-130">在 [ **提交範例前提示使用者** ] 下拉式清單中，選取 [ **自動傳送所有資料**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="86c6f-131">如需 Intune 裝置設定檔的詳細資訊，包括如何建立和設定其設定，請參閱[什麼是 Microsoft Intune 裝置設定檔？](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="86c6f-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="86c6f-132">使用 Microsoft 端點管理員開啟雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="86c6f-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="86c6f-133">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="86c6f-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="86c6f-134">選擇 [ **Endpoint security**  >  **防病毒**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="86c6f-135">選取防病毒設定檔。</span><span class="sxs-lookup"><span data-stu-id="86c6f-135">Select an antivirus profile.</span></span> <span data-ttu-id="86c6f-136"> (如果您尚沒有其中一個，或若您想要建立新的設定檔，請參閱[在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="86c6f-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="86c6f-137">選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-137">Select **Properties**.</span></span> <span data-ttu-id="86c6f-138">然後，選擇 [ **設定設定**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="86c6f-139">展開 [ **cloud protection**]，然後在 [ **雲端提供的保護層級** ] 清單中，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="86c6f-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="86c6f-140">**High**：套用強層次的偵測。</span><span class="sxs-lookup"><span data-stu-id="86c6f-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="86c6f-141">**High plus**：使用 **高階** ，套用其他保護措施 (可能會影響用戶端效能) 。</span><span class="sxs-lookup"><span data-stu-id="86c6f-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="86c6f-142">**零容錯**：封鎖所有的未知可執行檔。</span><span class="sxs-lookup"><span data-stu-id="86c6f-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="86c6f-143">選取 [ **複查 + 儲存**]，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="86c6f-144">如需設定 Microsoft Endpoint Configuration Manager 的詳細資訊，請參閱 how [to create and deploy 反惡意程式碼原則： Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。</span><span class="sxs-lookup"><span data-stu-id="86c6f-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="86c6f-145">使用群組原則開啟雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="86c6f-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="86c6f-146">在您的群組原則管理裝置上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="86c6f-147">在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="86c6f-148">選取 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="86c6f-149">展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 對應**</span><span class="sxs-lookup"><span data-stu-id="86c6f-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="86c6f-150">連按兩下 [ **加入 MICROSOFT 地圖**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="86c6f-151">確定已開啟此選項，並將其設定為 [ **基本地圖** ] 或 [ **高級地圖**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="86c6f-152">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="86c6f-152">Select **OK**.</span></span>

6. <span data-ttu-id="86c6f-153">**需要進一步分析時，** 請按兩下 [傳送檔案範例]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="86c6f-154">確定第一個選項設定為 [ **啟用** ]，且其他選項設定為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="86c6f-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="86c6f-155"> (1) **傳送安全的範例**</span><span class="sxs-lookup"><span data-stu-id="86c6f-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="86c6f-156">**將所有範例都傳送** (3) </span><span class="sxs-lookup"><span data-stu-id="86c6f-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="86c6f-157">[ **傳送安全範例** (1) ] 選項表示將會自動傳送大部分的範例。</span><span class="sxs-lookup"><span data-stu-id="86c6f-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="86c6f-158">可能包含個人資訊的檔案仍會出現提示，需要其他確認。</span><span class="sxs-lookup"><span data-stu-id="86c6f-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="86c6f-159">將此選項設定為 **Always Prompt** (0) 會降低裝置的保護狀態。</span><span class="sxs-lookup"><span data-stu-id="86c6f-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="86c6f-160">設定為 **永不傳送** (2) 表示 Microsoft Defender for Endpoint 的「 [區塊第一次看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 」功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="86c6f-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="86c6f-161">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="86c6f-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="86c6f-162">使用 PowerShell Cmdlet 開啟雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="86c6f-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="86c6f-163">下列 Cmdlet 可以開啟雲端提供的保護：</span><span class="sxs-lookup"><span data-stu-id="86c6f-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="86c6f-164">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="86c6f-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="86c6f-165">[原則 CSP-Defender](/windows/client-management/mdm/policy-csp-defender) 也有專用於 [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="86c6f-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="86c6f-166">您也可以將 **SubmitSamplesConsent** 設定為 `SendSafeSamples` (預設設定) 、 `NeverSend` 或 `AlwaysPrompt` 。</span><span class="sxs-lookup"><span data-stu-id="86c6f-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="86c6f-167">此 `SendSafeSamples` 設定表示將會自動傳送大多數的範例。</span><span class="sxs-lookup"><span data-stu-id="86c6f-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="86c6f-168">可能包含個人資訊的檔案仍會出現提示，需要其他確認。</span><span class="sxs-lookup"><span data-stu-id="86c6f-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="86c6f-169">設定 **-SubmitSamplesConsent** 至 `NeverSend` 或 `AlwaysPrompt` 會降低裝置的保護層級。</span><span class="sxs-lookup"><span data-stu-id="86c6f-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="86c6f-170">此外，設定為 `NeverSend` 表示 Microsoft Defender For Endpoint 的「 [區塊第一次看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 」功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="86c6f-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="86c6f-171">使用 Windows 管理指令 (WMI) 開啟雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="86c6f-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="86c6f-172">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/defender/set-msft-mppreference) ：</span><span class="sxs-lookup"><span data-stu-id="86c6f-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="86c6f-173">如需允許參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="86c6f-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="86c6f-174">在 Windows 安全性應用程式的個別用戶端上開啟雲端提供保護</span><span class="sxs-lookup"><span data-stu-id="86c6f-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="86c6f-175">如果設定為 [**將 Microsoft MAPS** 群組原則設定覆寫] 設定為 [**已停** 用]，則 Windows 設定中的 **雲端型保護** 設定會變灰並無法使用。</span><span class="sxs-lookup"><span data-stu-id="86c6f-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="86c6f-176">必須先將透過群組原則物件進行的變更部署到個別端點，才能在 Windows 設定中更新設定。</span><span class="sxs-lookup"><span data-stu-id="86c6f-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="86c6f-177">在工作欄中選取盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="86c6f-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="86c6f-178">在左功能表列上選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後 **& [病毒威脅防護設定** ] 標籤：</span><span class="sxs-lookup"><span data-stu-id="86c6f-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Windows 安全性應用程式中的病毒與威脅防護設定標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="86c6f-180">確認已將 **雲端式保護** 和 **自動範例提交** 切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="86c6f-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="86c6f-181">如果已使用群組原則設定自動範例提交，則設定會變灰並無法使用。</span><span class="sxs-lookup"><span data-stu-id="86c6f-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="86c6f-182">相關文章</span><span class="sxs-lookup"><span data-stu-id="86c6f-182">Related articles</span></span>

- [<span data-ttu-id="86c6f-183">設定雲端封鎖逾時期間</span><span class="sxs-lookup"><span data-stu-id="86c6f-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="86c6f-184">設定初次看到的封鎖</span><span class="sxs-lookup"><span data-stu-id="86c6f-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="86c6f-185">使用 PowerShell Cmdlet 來管理 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="86c6f-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="86c6f-186">[使用 Microsoft Intune] 的 Endpoint Protection 來協助保護 Windows 電腦](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="86c6f-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="86c6f-187">Defender Cmdlet</span><span class="sxs-lookup"><span data-stu-id="86c6f-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="86c6f-188">在 Microsoft Defender 防毒軟體中使用 Microsoft 雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="86c6f-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="86c6f-189">如何建立及部署反惡意程式碼原則： Cloud-protection service</span><span class="sxs-lookup"><span data-stu-id="86c6f-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="86c6f-190">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="86c6f-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
