---
title: 設定及驗證 Microsoft Defender ATP for Mac 的排除專案
description: 針對 Mac 提供和驗證 Microsoft Defender ATP 的排除專案。 您可以為檔案、資料夾及處理常式設定排除。
keywords: microsoft、defender、atp、mac、排除、掃描、防毒程式
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0ce77d55ece955fbf97b5c9f32859514b55acb5a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187646"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="fc7c5-105">針對 Mac 設定及驗證 Microsoft Defender for Endpoint 的排除專案</span><span class="sxs-lookup"><span data-stu-id="fc7c5-105">Configure and validate exclusions for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc7c5-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="fc7c5-106">**Applies to:**</span></span>
- [<span data-ttu-id="fc7c5-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fc7c5-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc7c5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc7c5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fc7c5-109">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="fc7c5-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc7c5-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="fc7c5-111">本文提供有關如何定義適用于隨選掃描和即時保護和監控之排除的資訊。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

>[!IMPORTANT]
><span data-ttu-id="fc7c5-112">本文中所述的排除項不適用於 Mac 功能的其他 Defender，包括 (EDR) 的端點偵測和回應。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-112">The exclusions described in this article don't apply to other Defender for Endpoint for Mac capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="fc7c5-113">使用本文所述方法排除的檔案，仍然可以觸發 EDR 警示及其他偵測。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="fc7c5-114">您可以從 Defender for Mac 掃描中排除某些檔案、資料夾、處理常式和以進程開啟的檔案。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Mac scans.</span></span>

<span data-ttu-id="fc7c5-115">排除在您的組織中，避免對檔或軟體的錯誤偵測非常有用。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="fc7c5-116">它們也可用於減輕由 Defender for Mac 所導致的效能問題。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Mac.</span></span>

>[!WARNING]
><span data-ttu-id="fc7c5-117">定義排除項會降低 Defender for Mac 的 Endpoint 所提供的保護。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="fc7c5-118">您應時刻評估與執行排除相關的風險，您應該只排除您確信不會惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="fc7c5-119">支援的排除類型</span><span class="sxs-lookup"><span data-stu-id="fc7c5-119">Supported exclusion types</span></span>

<span data-ttu-id="fc7c5-120">下表顯示適用于 Mac 的 Defender for Endpoint 所支援的排除類型。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-120">The follow table shows the exclusion types supported by Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="fc7c5-121">排除</span><span class="sxs-lookup"><span data-stu-id="fc7c5-121">Exclusion</span></span> | <span data-ttu-id="fc7c5-122">定義</span><span class="sxs-lookup"><span data-stu-id="fc7c5-122">Definition</span></span> | <span data-ttu-id="fc7c5-123">範例</span><span class="sxs-lookup"><span data-stu-id="fc7c5-123">Examples</span></span>
---|---|---
<span data-ttu-id="fc7c5-124">副檔名</span><span class="sxs-lookup"><span data-stu-id="fc7c5-124">File extension</span></span> | <span data-ttu-id="fc7c5-125">電腦上任何位置具有分機號碼的所有檔案</span><span class="sxs-lookup"><span data-stu-id="fc7c5-125">All files with the extension, anywhere on the machine</span></span> | `.test`
<span data-ttu-id="fc7c5-126">檔案</span><span class="sxs-lookup"><span data-stu-id="fc7c5-126">File</span></span> | <span data-ttu-id="fc7c5-127">完整路徑所識別的特定檔案</span><span class="sxs-lookup"><span data-stu-id="fc7c5-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="fc7c5-128">資料夾</span><span class="sxs-lookup"><span data-stu-id="fc7c5-128">Folder</span></span> | <span data-ttu-id="fc7c5-129">指定資料夾底下的所有檔案 (以遞迴方式) </span><span class="sxs-lookup"><span data-stu-id="fc7c5-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="fc7c5-130">程序</span><span class="sxs-lookup"><span data-stu-id="fc7c5-130">Process</span></span> | <span data-ttu-id="fc7c5-131">指定的程式 (會以完整路徑或檔案名指定，也可以是由它所開啟的所有檔案) </span><span class="sxs-lookup"><span data-stu-id="fc7c5-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

<span data-ttu-id="fc7c5-132">檔案、資料夾及處理常式排除支援下列萬用字元：</span><span class="sxs-lookup"><span data-stu-id="fc7c5-132">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="fc7c5-133">萬用字元</span><span class="sxs-lookup"><span data-stu-id="fc7c5-133">Wildcard</span></span> | <span data-ttu-id="fc7c5-134">描述</span><span class="sxs-lookup"><span data-stu-id="fc7c5-134">Description</span></span> | <span data-ttu-id="fc7c5-135">範例</span><span class="sxs-lookup"><span data-stu-id="fc7c5-135">Example</span></span> | <span data-ttu-id="fc7c5-136">比賽</span><span class="sxs-lookup"><span data-stu-id="fc7c5-136">Matches</span></span> | <span data-ttu-id="fc7c5-137">不符合</span><span class="sxs-lookup"><span data-stu-id="fc7c5-137">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="fc7c5-138">符合任何數目的任何字元，包含無 (請注意，當路徑內使用此萬用字元時，它只會取代一個資料夾) </span><span class="sxs-lookup"><span data-stu-id="fc7c5-138">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/*/*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="fc7c5-139">?</span><span class="sxs-lookup"><span data-stu-id="fc7c5-139">?</span></span> | <span data-ttu-id="fc7c5-140">符合任何單一字元</span><span class="sxs-lookup"><span data-stu-id="fc7c5-140">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

>[!NOTE]
><span data-ttu-id="fc7c5-141">當評估排除專案時，產品會嘗試解析 firmlinks。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-141">The product attempts to resolve firmlinks when evaluating exclusions.</span></span> <span data-ttu-id="fc7c5-142">當排除包含萬用字元，或是磁片區) 上的目標檔案 (不存在時，Firmlink 解決方法無法運作 `Data` 。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-142">Firmlink resolution does not work when the exclusion contains wildcards or the target file (on the `Data` volume) does not exist.</span></span>

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="fc7c5-143">如何設定排除清單</span><span class="sxs-lookup"><span data-stu-id="fc7c5-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="fc7c5-144">從管理主控台</span><span class="sxs-lookup"><span data-stu-id="fc7c5-144">From the management console</span></span>

<span data-ttu-id="fc7c5-145">如需如何設定 JAMF、Intune 或其他管理主控台之排除專案的詳細資訊，請參閱 [設定 Mac 版的 Defender For Endpoint 的喜好設定](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-145">For more information on how to configure exclusions from JAMF, Intune, or another management console, see [Set preferences for Defender for Endpoint for Mac](mac-preferences.md).</span></span>

### <a name="from-the-user-interface"></a><span data-ttu-id="fc7c5-146">從使用者介面</span><span class="sxs-lookup"><span data-stu-id="fc7c5-146">From the user interface</span></span>

<span data-ttu-id="fc7c5-147">開啟 Defender for Endpoint 應用程式，並流覽至 [**管理設定**] [  >  **新增或移除排除 ...**]，如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="fc7c5-147">Open the Defender for Endpoint application and navigate to **Manage settings** > **Add or Remove Exclusion...**, as shown in the following screenshot:</span></span>

![管理排除螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-37-exclusions)

<span data-ttu-id="fc7c5-149">選取您要新增的排除類型，然後依照提示進行。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-149">Select the type of exclusion that you wish to add and follow the prompts.</span></span>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="fc7c5-150">使用 EICAR.TXT 測試檔案驗證排除清單</span><span class="sxs-lookup"><span data-stu-id="fc7c5-150">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="fc7c5-151">您可以使用下載測試檔案，驗證您的排除清單是否運作正常 `curl` 。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-151">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="fc7c5-152">在下列 Bash 程式碼片段中， `test.txt` 以符合您的排除規則的檔案加以取代。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-152">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="fc7c5-153">例如，如果您已排除該 `.testing` 副檔名，請將其取代 `test.txt` `test.testing` 。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-153">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="fc7c5-154">若要測試路徑，請確定您在該路徑中執行命令。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-154">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="fc7c5-155">如果 Mac 版 Defender 的 Endpoint 報告惡意程式碼，則規則不會正常運作。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-155">If Defender for Endpoint for Mac reports malware, then the rule is not working.</span></span> <span data-ttu-id="fc7c5-156">如果沒有惡意程式碼的報表，而且下載的檔案存在，則排除作業正常運作。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-156">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="fc7c5-157">您可以開啟檔案，確認內容與 [eicar.txt test file 網站](http://2016.eicar.org/86-0-Intended-use.html)上所述的內容相同。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-157">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="fc7c5-158">如果您沒有網際網路存取權，可以建立您自己的 EICAR.TXT 測試檔案。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-158">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="fc7c5-159">使用下列 Bash 命令，將 EICAR.TXT 字串寫入新的文字檔：</span><span class="sxs-lookup"><span data-stu-id="fc7c5-159">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="fc7c5-160">您也可以將字串複製到空白的文字檔中，並嘗試使用檔案名或您嘗試排除的資料夾來儲存。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-160">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="fc7c5-161">允許威脅</span><span class="sxs-lookup"><span data-stu-id="fc7c5-161">Allow threats</span></span>

<span data-ttu-id="fc7c5-162">除了排除特定內容的掃描之外，您也可以設定產品不要偵測威脅名稱)  (所識別的某些威脅類別。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-162">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="fc7c5-163">使用此功能時，您應該小心謹慎，因為這會讓您的裝置保持不受保護。</span><span class="sxs-lookup"><span data-stu-id="fc7c5-163">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="fc7c5-164">若要將威脅名稱新增至允許的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fc7c5-164">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="fc7c5-165">您可以使用下列命令取得與裝置偵測相關聯的威脅名稱：</span><span class="sxs-lookup"><span data-stu-id="fc7c5-165">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="fc7c5-166">例如，若要將 `EICAR-Test-File (not a virus)` eicar.txt 偵測) 相關聯 (威脅名稱新增至允許清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fc7c5-166">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
