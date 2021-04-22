---
title: 在 Linux 上設定及驗證 Microsoft Defender for Endpoint 的排除專案
description: 在 Linux 上提供及驗證 Microsoft Defender for Endpoint 的排除專案。 您可以為檔案、資料夾及處理常式設定排除。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，排除，掃描，防毒程式
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8e861055067a55630da458e87b7376a607dc69c4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934294"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="22789-105">在 Linux 上設定及驗證 Microsoft Defender for Endpoint 的排除專案</span><span class="sxs-lookup"><span data-stu-id="22789-105">Configure and validate exclusions for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="22789-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="22789-106">**Applies to:**</span></span>
- [<span data-ttu-id="22789-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="22789-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22789-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22789-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="22789-109">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="22789-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="22789-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="22789-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="22789-111">本文提供有關如何定義適用于隨選掃描和即時保護和監控之排除的資訊。</span><span class="sxs-lookup"><span data-stu-id="22789-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22789-112">本文所述的排除項不適用於 Linux 功能上的其他 Defender for Endpoint，包括端點偵測和回應 (EDR) 。</span><span class="sxs-lookup"><span data-stu-id="22789-112">The exclusions described in this article don't apply to other Defender for Endpoint on Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="22789-113">使用本文所述方法排除的檔案，仍然可以觸發 EDR 警示及其他偵測。</span><span class="sxs-lookup"><span data-stu-id="22789-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="22789-114">您可以從 Linux 掃描上的「Defender for Endpoint」排除某些檔案、資料夾、處理常式及處理常式開啟的檔案。</span><span class="sxs-lookup"><span data-stu-id="22789-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint on Linux scans.</span></span>

<span data-ttu-id="22789-115">排除在您的組織中，避免對檔或軟體的錯誤偵測非常有用。</span><span class="sxs-lookup"><span data-stu-id="22789-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="22789-116">它們也可用於減輕由 Linux 上的 Defender for Endpoint 所導致的效能問題。</span><span class="sxs-lookup"><span data-stu-id="22789-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint on Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="22789-117">定義排除項會降低在 Linux 上的 Defender for Endpoint 所提供的保護。</span><span class="sxs-lookup"><span data-stu-id="22789-117">Defining exclusions lowers the protection offered by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="22789-118">您應時刻評估與執行排除相關的風險，您應該只排除您確信不會惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="22789-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="22789-119">支援的排除類型</span><span class="sxs-lookup"><span data-stu-id="22789-119">Supported exclusion types</span></span>

<span data-ttu-id="22789-120">下表顯示在 Linux 上的 Defender for Endpoint 所支援的排除類型。</span><span class="sxs-lookup"><span data-stu-id="22789-120">The follow table shows the exclusion types supported by Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="22789-121">排除</span><span class="sxs-lookup"><span data-stu-id="22789-121">Exclusion</span></span> | <span data-ttu-id="22789-122">定義</span><span class="sxs-lookup"><span data-stu-id="22789-122">Definition</span></span> | <span data-ttu-id="22789-123">範例</span><span class="sxs-lookup"><span data-stu-id="22789-123">Examples</span></span>
---|---|---
<span data-ttu-id="22789-124">副檔名</span><span class="sxs-lookup"><span data-stu-id="22789-124">File extension</span></span> | <span data-ttu-id="22789-125">在裝置上的任何位置具有分機的所有檔案</span><span class="sxs-lookup"><span data-stu-id="22789-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="22789-126">檔案</span><span class="sxs-lookup"><span data-stu-id="22789-126">File</span></span> | <span data-ttu-id="22789-127">完整路徑所識別的特定檔案</span><span class="sxs-lookup"><span data-stu-id="22789-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="22789-128">資料夾</span><span class="sxs-lookup"><span data-stu-id="22789-128">Folder</span></span> | <span data-ttu-id="22789-129">指定資料夾底下的所有檔案 (以遞迴方式) </span><span class="sxs-lookup"><span data-stu-id="22789-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="22789-130">程序</span><span class="sxs-lookup"><span data-stu-id="22789-130">Process</span></span> | <span data-ttu-id="22789-131">指定的程式 (會以完整路徑或檔案名指定，也可以是由它所開啟的所有檔案) </span><span class="sxs-lookup"><span data-stu-id="22789-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="22789-132">以上的路徑必須是硬連結，而不是符號連結，才可成功排除。</span><span class="sxs-lookup"><span data-stu-id="22789-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="22789-133">您可以執行，檢查路徑是否為符號連結 `file <path-name>` 。</span><span class="sxs-lookup"><span data-stu-id="22789-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="22789-134">檔案、資料夾及處理常式排除支援下列萬用字元：</span><span class="sxs-lookup"><span data-stu-id="22789-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="22789-135">萬用字元</span><span class="sxs-lookup"><span data-stu-id="22789-135">Wildcard</span></span> | <span data-ttu-id="22789-136">描述</span><span class="sxs-lookup"><span data-stu-id="22789-136">Description</span></span> | <span data-ttu-id="22789-137">範例</span><span class="sxs-lookup"><span data-stu-id="22789-137">Example</span></span> | <span data-ttu-id="22789-138">比賽</span><span class="sxs-lookup"><span data-stu-id="22789-138">Matches</span></span> | <span data-ttu-id="22789-139">不符合</span><span class="sxs-lookup"><span data-stu-id="22789-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="22789-140">符合任何數目的任何字元，包含無 (請注意，當路徑內使用此萬用字元時，它只會取代一個資料夾) </span><span class="sxs-lookup"><span data-stu-id="22789-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="22789-141">?</span><span class="sxs-lookup"><span data-stu-id="22789-141">?</span></span> | <span data-ttu-id="22789-142">符合任何單一字元</span><span class="sxs-lookup"><span data-stu-id="22789-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="22789-143">如何設定排除清單</span><span class="sxs-lookup"><span data-stu-id="22789-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="22789-144">從管理主控台</span><span class="sxs-lookup"><span data-stu-id="22789-144">From the management console</span></span>

<span data-ttu-id="22789-145">如需如何設定 Puppet、Ansible 或其他管理主控台之排除專案的詳細資訊，請參閱 [設定 Linux 上的 Defender For Endpoint 的喜好設定](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="22789-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="22789-146">從命令列</span><span class="sxs-lookup"><span data-stu-id="22789-146">From the command line</span></span>

<span data-ttu-id="22789-147">執行下列命令，以查看管理排除專案時可用的參數：</span><span class="sxs-lookup"><span data-stu-id="22789-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="22789-148">設定包含萬用字元的排除時，請以雙引號括住參數，以防止內括弧。</span><span class="sxs-lookup"><span data-stu-id="22789-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="22789-149">範例：</span><span class="sxs-lookup"><span data-stu-id="22789-149">Examples:</span></span>

- <span data-ttu-id="22789-150">新增副檔名的排除專案：</span><span class="sxs-lookup"><span data-stu-id="22789-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="22789-151">為檔案新增排除專案：</span><span class="sxs-lookup"><span data-stu-id="22789-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="22789-152">為資料夾新增排除專案：</span><span class="sxs-lookup"><span data-stu-id="22789-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="22789-153">為包含萬用字元的資料夾新增排除專案：</span><span class="sxs-lookup"><span data-stu-id="22789-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="22789-154">這只會排除 */var/* 下一個層級的路徑，但不會排除更深層嵌套的資料夾;例如， */var/this-subfolder/but-not-this-subfolder*。</span><span class="sxs-lookup"><span data-stu-id="22789-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="22789-155">這將排除父級為 */var/* 的所有路徑;例如， */var/this-subfolder/and-this-subfolder-as-well*。</span><span class="sxs-lookup"><span data-stu-id="22789-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="22789-156">新增處理常式的排除專案：</span><span class="sxs-lookup"><span data-stu-id="22789-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="22789-157">使用 EICAR.TXT 測試檔案驗證排除清單</span><span class="sxs-lookup"><span data-stu-id="22789-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="22789-158">您可以使用下載測試檔案，驗證您的排除清單是否運作正常 `curl` 。</span><span class="sxs-lookup"><span data-stu-id="22789-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="22789-159">在下列 Bash 程式碼片段中， `test.txt` 以符合您的排除規則的檔案加以取代。</span><span class="sxs-lookup"><span data-stu-id="22789-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="22789-160">例如，如果您已排除該 `.testing` 副檔名，請將其取代 `test.txt` `test.testing` 。</span><span class="sxs-lookup"><span data-stu-id="22789-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="22789-161">若要測試路徑，請確定您在該路徑中執行命令。</span><span class="sxs-lookup"><span data-stu-id="22789-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="22789-162">如果在 Linux 上的 Defender for Endpoint 報告為惡意程式碼，則規則不會正常運作。</span><span class="sxs-lookup"><span data-stu-id="22789-162">If Defender for Endpoint on Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="22789-163">如果沒有惡意程式碼的報表，而且下載的檔案存在，則排除作業正常運作。</span><span class="sxs-lookup"><span data-stu-id="22789-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="22789-164">您可以開啟檔案，確認內容與 [eicar.txt test file 網站](http://2016.eicar.org/86-0-Intended-use.html)上所述的內容相同。</span><span class="sxs-lookup"><span data-stu-id="22789-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="22789-165">如果您沒有網際網路存取權，可以建立您自己的 EICAR.TXT 測試檔案。</span><span class="sxs-lookup"><span data-stu-id="22789-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="22789-166">使用下列 Bash 命令，將 EICAR.TXT 字串寫入新的文字檔：</span><span class="sxs-lookup"><span data-stu-id="22789-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="22789-167">您也可以將字串複製到空白的文字檔中，並嘗試使用檔案名或您嘗試排除的資料夾來儲存。</span><span class="sxs-lookup"><span data-stu-id="22789-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="22789-168">允許威脅</span><span class="sxs-lookup"><span data-stu-id="22789-168">Allow threats</span></span>

<span data-ttu-id="22789-169">除了排除特定內容的掃描之外，您也可以設定產品不要偵測威脅名稱)  (所識別的某些威脅類別。</span><span class="sxs-lookup"><span data-stu-id="22789-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="22789-170">使用此功能時，您應該小心謹慎，因為這會讓您的裝置保持不受保護。</span><span class="sxs-lookup"><span data-stu-id="22789-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="22789-171">若要將威脅名稱新增至允許的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="22789-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="22789-172">您可以使用下列命令取得與裝置偵測相關聯的威脅名稱：</span><span class="sxs-lookup"><span data-stu-id="22789-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="22789-173">例如，若要將 `EICAR-Test-File (not a virus)` eicar.txt 偵測) 相關聯 (威脅名稱新增至允許清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="22789-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
