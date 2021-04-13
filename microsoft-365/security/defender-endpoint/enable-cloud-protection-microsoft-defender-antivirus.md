---
title: 在 Microsoft Defender 防毒軟體中開啟雲端提供保護
description: 開啟雲端提供的保護，以利用快速和高級的保護功能。
keywords: Microsoft Defender 防毒程式，反惡意程式碼，安全性，cloud，第一次看到區塊
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: cfaf4563e96568ae26bd990678462836b9202656
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690228"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="c0032-104">開啟雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="c0032-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0032-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c0032-105">**Applies to:**</span></span>

- [<span data-ttu-id="c0032-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c0032-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="c0032-107">Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞到網路和端點。</span><span class="sxs-lookup"><span data-stu-id="c0032-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="c0032-108">雖然它稱為雲端服務，但不只是保護儲存在雲端中的檔案;相反地，它會使用分散式資源和機器教學，以比傳統的安全性智慧更新速度更快的速率來提供對端點的保護。</span><span class="sxs-lookup"><span data-stu-id="c0032-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="c0032-109">Microsoft Defender 防病毒會使用多個偵測及防護技術，提供準確、即時和智慧的保護。</span><span class="sxs-lookup"><span data-stu-id="c0032-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="c0032-110">[深入瞭解 Microsoft Defender 在第二代端點的核心的高級技術](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="c0032-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="c0032-111">![Microsoft Defender AV 引擎清單](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="c0032-111">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="c0032-112">您可以用下列幾種方式，開啟或關閉 Microsoft Defender 防毒軟體雲端提供的保護：</span><span class="sxs-lookup"><span data-stu-id="c0032-112">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="c0032-113">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c0032-113">Microsoft Intune</span></span>
- <span data-ttu-id="c0032-114">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c0032-114">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="c0032-115">群組原則</span><span class="sxs-lookup"><span data-stu-id="c0032-115">Group Policy</span></span>
- <span data-ttu-id="c0032-116">PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c0032-116">PowerShell cmdlets.</span></span>

 <span data-ttu-id="c0032-117">您也可以使用 Windows 安全性應用程式，在個別的用戶端中開啟或關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="c0032-117">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="c0032-118">請參閱 [使用 microsoft 雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md) ，以取得 Microsoft Defender 防病毒雲端提供的保護。</span><span class="sxs-lookup"><span data-stu-id="c0032-118">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="c0032-119">如需特定網路連線需求的詳細資訊，以確保端點能夠連線至雲端提供的保護服務，請參閱 [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="c0032-119">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c0032-120">在 Windows 10 中，本主題所述的 **基本** 和 **高級** 報告選項之間沒有任何差異。</span><span class="sxs-lookup"><span data-stu-id="c0032-120">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="c0032-121">這是傳統的區別，而且選擇任一設定會導致相同的雲端傳送層級保護。</span><span class="sxs-lookup"><span data-stu-id="c0032-121">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="c0032-122">共用的資訊類型或數量不會有任何差異。</span><span class="sxs-lookup"><span data-stu-id="c0032-122">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="c0032-123">如需我們收集之專案的詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=521839)。</span><span class="sxs-lookup"><span data-stu-id="c0032-123">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c0032-124">使用 Intune 開啟雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="c0032-124">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="c0032-125">請移至 Microsoft 端點管理員管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="c0032-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="c0032-126">在 [ **首頁** ] 窗格中，選取 [裝置設定] **> 設定檔**。</span><span class="sxs-lookup"><span data-stu-id="c0032-126">On the **Home** pane, select **Device configuration > Profiles**.</span></span>
3. <span data-ttu-id="c0032-127">選取您要設定的 **裝置限制** 配置檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c0032-127">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="c0032-128">如果您需要建立新的 **裝置限制** 配置檔案類型，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="c0032-128">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="c0032-129">選取 **屬性**  >  **設定：編輯**  >  **Microsoft Defender 防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="c0032-129">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>
5. <span data-ttu-id="c0032-130">在 **雲端提供的保護** 參數上，選取 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-130">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>
6. <span data-ttu-id="c0032-131">在 [ **提交範例前提示使用者** ] 下拉式清單中，選取 [ **自動傳送所有資料**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-131">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="c0032-132">如需 Intune 裝置設定檔的詳細資訊，包括如何建立和設定其設定，請參閱 [什麼是 Microsoft Intune 裝置設定檔？](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="c0032-132">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c0032-133">使用 Microsoft 端點管理員開啟雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="c0032-133">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="c0032-134">請移至 Microsoft 端點管理員管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="c0032-134">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="c0032-135">選擇 [ **Endpoint security**  >  **防病毒**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-135">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="c0032-136">選取防病毒設定檔。</span><span class="sxs-lookup"><span data-stu-id="c0032-136">Select an antivirus profile.</span></span> <span data-ttu-id="c0032-137"> (如果您尚沒有其中一個，或若您想要建立新的設定檔，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="c0032-137">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="c0032-138">選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-138">Select **Properties**.</span></span> <span data-ttu-id="c0032-139">然後，選擇 [ **設定設定**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-139">Then, next to **Configuration settings**, choose **Edit**.</span></span>
5. <span data-ttu-id="c0032-140">展開 [ **cloud protection**]，然後在 [ **雲端提供的保護層級** ] 清單中，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c0032-140">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
    1. <span data-ttu-id="c0032-141">**High**：套用強層次的偵測。</span><span class="sxs-lookup"><span data-stu-id="c0032-141">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="c0032-142">**High plus**：使用 **高階** ，套用其他保護措施 (可能會影響用戶端效能) 。</span><span class="sxs-lookup"><span data-stu-id="c0032-142">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="c0032-143">**零容錯**：封鎖所有的未知可執行檔。</span><span class="sxs-lookup"><span data-stu-id="c0032-143">**Zero tolerance**: Blocks all unknown executables.</span></span>
6. <span data-ttu-id="c0032-144">選取 [ **複查 + 儲存**]，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-144">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="c0032-145">如需設定 Microsoft 端點設定管理員的詳細資訊，請參閱 how [to create and deploy 反惡意程式碼原則： Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。</span><span class="sxs-lookup"><span data-stu-id="c0032-145">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c0032-146">使用群組原則開啟雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="c0032-146">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="c0032-147">在您的群組原則管理裝置上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-147">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="c0032-148">在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="c0032-148">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c0032-149">選取 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-149">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="c0032-150">將樹展開 **> Microsoft Defender 防病毒 > 地圖的 Windows 元件**</span><span class="sxs-lookup"><span data-stu-id="c0032-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="c0032-151">連按兩下 [ **加入 MICROSOFT 地圖**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-151">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="c0032-152">確定已開啟此選項，並將其設定為 [ **基本地圖** ] 或 [ **高級地圖**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-152">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="c0032-153">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c0032-153">Select **OK**.</span></span>

6. <span data-ttu-id="c0032-154">**需要進一步分析時，** 請按兩下 [傳送檔案範例]。</span><span class="sxs-lookup"><span data-stu-id="c0032-154">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="c0032-155">確定第一個選項設定為 [ **啟用** ]，且其他選項設定為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c0032-155">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="c0032-156"> (1) **傳送安全的範例**</span><span class="sxs-lookup"><span data-stu-id="c0032-156">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="c0032-157">**將所有範例都傳送** (3) </span><span class="sxs-lookup"><span data-stu-id="c0032-157">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="c0032-158">[ **傳送安全範例** (1) ] 選項表示將會自動傳送大部分的範例。</span><span class="sxs-lookup"><span data-stu-id="c0032-158">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="c0032-159">可能包含個人資訊的檔案仍會出現提示，需要其他確認。</span><span class="sxs-lookup"><span data-stu-id="c0032-159">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

        > [!WARNING]
        > <span data-ttu-id="c0032-160">將此選項設定為 **Always Prompt** (0) 會降低裝置的保護狀態。</span><span class="sxs-lookup"><span data-stu-id="c0032-160">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="c0032-161">設定為 **永不傳送** (2) 表示 Microsoft Defender for Endpoint 的「 [區塊第一次看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 」功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="c0032-161">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="c0032-162">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c0032-162">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c0032-163">使用 PowerShell Cmdlet 開啟雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="c0032-163">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="c0032-164">下列 Cmdlet 可以開啟雲端提供的保護：</span><span class="sxs-lookup"><span data-stu-id="c0032-164">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="c0032-165">如需如何將 PowerShell 與 Microsoft Defender 防毒軟體搭配使用的詳細資訊，請參閱 [use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="c0032-165">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="c0032-166">[原則 CSP-Defender](/windows/client-management/mdm/policy-csp-defender) 也有專用於 [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c0032-166">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="c0032-167">您也可以將 **SubmitSamplesConsent** 設定為 `SendSafeSamples` (預設設定) 、 `NeverSend` 或 `AlwaysPrompt` 。</span><span class="sxs-lookup"><span data-stu-id="c0032-167">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="c0032-168">此 `SendSafeSamples` 設定表示將會自動傳送大多數的範例。</span><span class="sxs-lookup"><span data-stu-id="c0032-168">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="c0032-169">可能包含個人資訊的檔案仍會出現提示，需要其他確認。</span><span class="sxs-lookup"><span data-stu-id="c0032-169">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="c0032-170">設定 **-SubmitSamplesConsent** 至 `NeverSend` 或 `AlwaysPrompt` 會降低裝置的保護層級。</span><span class="sxs-lookup"><span data-stu-id="c0032-170">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="c0032-171">此外，設定為 `NeverSend` 表示 Microsoft Defender For Endpoint 的「 [區塊第一次看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 」功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="c0032-171">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c0032-172">使用 Windows Management 指令 (WMI) 開啟雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="c0032-172">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="c0032-173">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/defender/set-msft-mppreference) ：</span><span class="sxs-lookup"><span data-stu-id="c0032-173">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="c0032-174">如需允許參數的詳細資訊，請參閱 [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="c0032-174">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="c0032-175">使用 Windows 安全性應用程式在個別用戶端上開啟雲端提供保護</span><span class="sxs-lookup"><span data-stu-id="c0032-175">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="c0032-176">如果設定為 [ **將 MICROSOFT MAPS** 群組原則設定重寫] 設定為 [ **已停用**]，則 [Windows 設定] 中的 **雲端型保護** 設定會變灰且無法使用。</span><span class="sxs-lookup"><span data-stu-id="c0032-176">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="c0032-177">您必須先將透過「群組原則」物件所做的變更部署到個別的端點，然後才會在 [Windows 設定] 中更新設定。</span><span class="sxs-lookup"><span data-stu-id="c0032-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="c0032-178">在工作列上選取盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 [Windows 安全性] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c0032-178">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="c0032-179">在左功能表列上選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後 **& [病毒威脅防護設定** ] 標籤：</span><span class="sxs-lookup"><span data-stu-id="c0032-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Windows 安全性應用程式中的病毒 & 威脅防護設定] 標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="c0032-181">確認已將 **雲端式保護** 和 **自動範例提交** 切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c0032-181">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="c0032-182">如果已使用群組原則設定自動範例提交，則設定會變灰並無法使用。</span><span class="sxs-lookup"><span data-stu-id="c0032-182">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c0032-183">相關文章</span><span class="sxs-lookup"><span data-stu-id="c0032-183">Related articles</span></span>

- [<span data-ttu-id="c0032-184">設定雲端封鎖超時期限</span><span class="sxs-lookup"><span data-stu-id="c0032-184">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c0032-185">設定初次看到的封鎖</span><span class="sxs-lookup"><span data-stu-id="c0032-185">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c0032-186">使用 PowerShell Cmdlet 來管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="c0032-186">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="c0032-187">[使用 Microsoft Intune 的 Endpoint Protection 來協助保護 Windows 電腦](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="c0032-187">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="c0032-188">Defender Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c0032-188">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="c0032-189">在 Microsoft Defender 防毒軟體中使用 Microsoft 雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="c0032-189">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c0032-190">如何建立及部署反惡意程式碼原則： Cloud-protection service</span><span class="sxs-lookup"><span data-stu-id="c0032-190">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="c0032-191">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="c0032-191">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)