---
title: 保護來自勒索軟體的重要資料夾，使其無法使用可控資料夾存取權加密您的檔案
description: 您可以防止惡意應用程式變更預設資料夾中的檔案。 防止勒索軟體加密您的檔案。
keywords: 受控制的資料夾存取、windows 10、windows defender、勒索軟體、保護、檔案、資料夾
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: cd662dc130adc37b3bf8bd06839242ccc9a49f8e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185966"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="f3896-105">使用受控資料夾存取權來保護重要資料夾</span><span class="sxs-lookup"><span data-stu-id="f3896-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3896-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f3896-106">**Applies to:**</span></span>
- [<span data-ttu-id="f3896-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f3896-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f3896-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3896-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f3896-109">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f3896-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f3896-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f3896-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="f3896-111">何謂受控制的資料夾存取？</span><span class="sxs-lookup"><span data-stu-id="f3896-111">What is controlled folder access?</span></span>

<span data-ttu-id="f3896-112">控制的資料夾存取可協助保護您的重要資料免受惡意應用程式和威脅（例如勒索軟體）的威脅。</span><span class="sxs-lookup"><span data-stu-id="f3896-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="f3896-113">「受管理的資料夾存取」會透過已知的受信任應用程式清單來檢查應用程式，以保護您的資料。</span><span class="sxs-lookup"><span data-stu-id="f3896-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="f3896-114">在 Windows Server 2019 和 Windows 10 用戶端上受支援，可使用受管理裝置的 Windows 安全性 App、Microsoft 端點設定管理員或 Intune (，開啟受控資料夾存取權) 。</span><span class="sxs-lookup"><span data-stu-id="f3896-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="f3896-115">腳本引擎是不受信任的，您無法允許他們存取受控制的受保護資料夾。</span><span class="sxs-lookup"><span data-stu-id="f3896-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="f3896-116">例如，即使您允許使用 [憑證及檔指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)，「受控資料夾存取」也不會信任 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f3896-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="f3896-117">「受管理的資料夾存取」最適合使用 [Microsoft Defender For Endpoint](microsoft-defender-endpoint.md)」，可讓您在一般 [警示調查案例](investigate-alerts.md)中深入報告，以進行受控資料夾存取事件和區塊。</span><span class="sxs-lookup"><span data-stu-id="f3896-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="f3896-118">[受管理的資料夾存取封鎖] 不會在 [ [警示] 佇列](alerts-queue.md)中產生警示。</span><span class="sxs-lookup"><span data-stu-id="f3896-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="f3896-119">不過，您可以在 [裝置時程表視圖](investigate-machines.md)中，使用 [高級搜尋](advanced-hunting-overview.md)或 [自訂偵測規則](custom-detection-rules.md)，查看受控資料夾存取模組的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f3896-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="f3896-120">控制資料夾存取的運作方式？</span><span class="sxs-lookup"><span data-stu-id="f3896-120">How does controlled folder access work?</span></span>

<span data-ttu-id="f3896-121">「受管理的資料夾存取」的運作方式只有允許信任的應用程式存取受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="f3896-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="f3896-122">設定受控制的資料夾存取權時，會指定受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="f3896-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="f3896-123">通常使用的資料夾（如用於檔、圖片、下載專案等的資料夾）會包含在受管理的資料夾清單中。</span><span class="sxs-lookup"><span data-stu-id="f3896-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="f3896-124">「受管理的資料夾存取」可與受信任的應用程式清單搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f3896-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="f3896-125">受信任軟體清單中包含的應用程式如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="f3896-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="f3896-126">未包含在清單中的應用程式，無法對受保護的資料夾內的檔案進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="f3896-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="f3896-127">根據使用者的流行和聲譽，將應用程式新增至清單。</span><span class="sxs-lookup"><span data-stu-id="f3896-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="f3896-128">您整個組織中高度流行且從未顯示任何視為惡意行為的應用程式，都會視為可信。</span><span class="sxs-lookup"><span data-stu-id="f3896-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="f3896-129">這些應用程式會自動新增至清單。</span><span class="sxs-lookup"><span data-stu-id="f3896-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="f3896-130">您也可以使用 Configuration Manager 或 Intune，將應用程式手動新增至信任清單。</span><span class="sxs-lookup"><span data-stu-id="f3896-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="f3896-131">您可以從 [安全性中心] 主控台執行其他動作（例如新增應用程式 [的檔案指標](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) ）。</span><span class="sxs-lookup"><span data-stu-id="f3896-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="f3896-132">控制資料夾存取很重要的原因</span><span class="sxs-lookup"><span data-stu-id="f3896-132">Why controlled folder access is important</span></span>

<span data-ttu-id="f3896-133">在協助保護您的 [勒索軟體](https://www.microsoft.com/wdsi/threats/ransomware)中的檔和資訊時，可控制的資料夾存取特別有用。</span><span class="sxs-lookup"><span data-stu-id="f3896-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="f3896-134">在勒索軟體攻擊中，您的檔案可能會被加密並保留 hostage。</span><span class="sxs-lookup"><span data-stu-id="f3896-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="f3896-135">在就地進行「可控資料夾存取」時，會在應用程式嘗試對受保護資料夾中的檔案進行變更的電腦上顯示通知。</span><span class="sxs-lookup"><span data-stu-id="f3896-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="f3896-136">您可以 [自訂](customize-attack-surface-reduction.md#customize-the-notification) 您公司詳細資料和連絡人資訊的通知。</span><span class="sxs-lookup"><span data-stu-id="f3896-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="f3896-137">您也可以個別啟用規則，以自訂功能所監視的技巧。</span><span class="sxs-lookup"><span data-stu-id="f3896-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="f3896-138">[ [受保護的資料夾](#review-controlled-folder-access-events-in-windows-event-viewer) ] 包括常見的系統資料夾， (包括「開機磁區」) ，而且您可以 [新增更多資料夾](customize-controlled-folders.md#protect-additional-folders)。</span><span class="sxs-lookup"><span data-stu-id="f3896-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="f3896-139">您也可以 [讓應用程式](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) 能夠存取受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="f3896-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="f3896-140">您可以使用 [審計模式](audit-windows-defender.md) ，評估當組織啟用時，受控資料夾存取會如何影響您的組織。</span><span class="sxs-lookup"><span data-stu-id="f3896-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="f3896-141">您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 參觀 Windows Defender Test 基礎網站，確認該功能是否正常運作，並查看其運作方式。</span><span class="sxs-lookup"><span data-stu-id="f3896-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="f3896-142">下列 Windows 版本支援受控制的資料夾存取：</span><span class="sxs-lookup"><span data-stu-id="f3896-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="f3896-143">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 和更新版本</span><span class="sxs-lookup"><span data-stu-id="f3896-143">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="f3896-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f3896-144">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="f3896-145">預設會保護 Windows 系統資料夾</span><span class="sxs-lookup"><span data-stu-id="f3896-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="f3896-146">Windows 系統資料夾預設會受到保護，另外還有其他一些資料夾：</span><span class="sxs-lookup"><span data-stu-id="f3896-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="f3896-147">您可以將其他資料夾設定為受保護，但您無法移除預設會受保護的 Windows 系統資料夾。</span><span class="sxs-lookup"><span data-stu-id="f3896-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="f3896-148">受控資料夾存取的需求</span><span class="sxs-lookup"><span data-stu-id="f3896-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="f3896-149">受控制的資料夾存取需要啟用 [Microsoft Defender 防病毒即時保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="f3896-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="f3896-150">在 Microsoft Defender 安全中心檢查受控資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="f3896-150">Review controlled folder access events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="f3896-151">當事件和區塊成為其 [警示調查案例](investigate-alerts.md)的一部分時，它會提供端點的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="f3896-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="f3896-152">您可以使用 [ [高級搜尋](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)] 查詢 Microsoft Defender 的端點資料。</span><span class="sxs-lookup"><span data-stu-id="f3896-152">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="f3896-153">如果您使用的是「 [審核」模式](audit-windows-defender.md)，您可以使用 [高級搜尋](advanced-hunting-overview.md) 查看受控制的資料夾存取設定如何影響環境（如果已啟用）。</span><span class="sxs-lookup"><span data-stu-id="f3896-153">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="f3896-154">例如查詢：</span><span class="sxs-lookup"><span data-stu-id="f3896-154">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="f3896-155">在 Windows 事件檢視器中檢查受控資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="f3896-155">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="f3896-156">您可以查看 Windows 事件記錄檔，以查看當控制的資料夾存取封鎖 (或) 應用程式進行審核時所建立的事件：</span><span class="sxs-lookup"><span data-stu-id="f3896-156">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="f3896-157">下載 [評估套件](https://aka.ms/mp7z2w) ，並將檔案 *cfa-events.xml* 解壓至裝置上易於存取的位置。</span><span class="sxs-lookup"><span data-stu-id="f3896-157">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="f3896-158">在 [開始] 功能表中輸入 **事件檢視器** ，以開啟 Windows 事件檢視器。</span><span class="sxs-lookup"><span data-stu-id="f3896-158">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="f3896-159">在左窗格的 [ **動作**] 下，選取 [匯 **入自訂視圖 ...**]。</span><span class="sxs-lookup"><span data-stu-id="f3896-159">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="f3896-160">流覽至解壓縮 *cfa-events.xml* 的位置，然後選取。</span><span class="sxs-lookup"><span data-stu-id="f3896-160">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="f3896-161">或者， [直接複製 XML](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="f3896-161">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="f3896-162">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="f3896-162">Select **OK**.</span></span>

<span data-ttu-id="f3896-163">下表顯示與受控資料夾存取相關的事件：</span><span class="sxs-lookup"><span data-stu-id="f3896-163">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="f3896-164">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="f3896-164">Event ID</span></span> | <span data-ttu-id="f3896-165">描述</span><span class="sxs-lookup"><span data-stu-id="f3896-165">Description</span></span> |
|:---|:---|
|<span data-ttu-id="f3896-166">5007</span><span class="sxs-lookup"><span data-stu-id="f3896-166">5007</span></span> | <span data-ttu-id="f3896-167">設定變更時的事件</span><span class="sxs-lookup"><span data-stu-id="f3896-167">Event when settings are changed</span></span> |
|<span data-ttu-id="f3896-168">1124</span><span class="sxs-lookup"><span data-stu-id="f3896-168">1124</span></span> | <span data-ttu-id="f3896-169">已審核的受管理資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="f3896-169">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="f3896-170">1123</span><span class="sxs-lookup"><span data-stu-id="f3896-170">1123</span></span> | <span data-ttu-id="f3896-171">封鎖的受管理資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="f3896-171">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="f3896-172">查看或變更受保護的資料夾清單</span><span class="sxs-lookup"><span data-stu-id="f3896-172">View or change the list of protected folders</span></span>

<span data-ttu-id="f3896-173">您可以使用 Windows 安全性應用程式來查看受控制的資料夾存取所保護的資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="f3896-173">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="f3896-174">在您的 Windows 10 裝置上，開啟 [Windows 安全性應用程式]。</span><span class="sxs-lookup"><span data-stu-id="f3896-174">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="f3896-175">選取 [ **病毒 & 威脅防護**]。</span><span class="sxs-lookup"><span data-stu-id="f3896-175">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="f3896-176">在 [ **勒索軟體防護**] 底下，選取 [ **管理勒索軟體防護**]。</span><span class="sxs-lookup"><span data-stu-id="f3896-176">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="f3896-177">如果已關閉受管理的資料夾存取，您必須將其開啟。</span><span class="sxs-lookup"><span data-stu-id="f3896-177">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="f3896-178">選取 [ **受保護的資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="f3896-178">Select **protected folders**.</span></span>
5. <span data-ttu-id="f3896-179">請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="f3896-179">Do one of the following steps:</span></span>
   - <span data-ttu-id="f3896-180">若要新增資料夾，請選取 [ **+ 新增受保護的資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="f3896-180">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="f3896-181">若要移除資料夾，請選取它，然後選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="f3896-181">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="f3896-182">[Windows 系統資料夾](#windows-system-folders-are-protected-by-default) 預設會受到保護，您無法將其從清單中移除。</span><span class="sxs-lookup"><span data-stu-id="f3896-182">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3896-183">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f3896-183">See also</span></span>

- [<span data-ttu-id="f3896-184">評估受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="f3896-184">Evaluate controlled folder access</span></span>](evaluate-controlled-folder-access.md)
- [<span data-ttu-id="f3896-185">自訂受控資料夾存取</span><span class="sxs-lookup"><span data-stu-id="f3896-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
- [<span data-ttu-id="f3896-186">保護更多資料夾</span><span class="sxs-lookup"><span data-stu-id="f3896-186">Protect more folders</span></span>](customize-controlled-folders.md#protect-additional-folders)
