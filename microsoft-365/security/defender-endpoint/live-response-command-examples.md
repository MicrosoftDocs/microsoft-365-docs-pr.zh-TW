---
title: 即時回應命令範例
description: 瞭解如何對 Microsoft Defender for Endpoint 執行基本或高級 live 回應命令，並查看其使用方式的範例。
keywords: 範例，command，cli，remote，shell，connection，live，response，real time，command，script，修正，搜尋，匯出，記錄，刪除，下載，檔案
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f08f20753a1f0926abbbce01fe97f20ef1c07f2c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689086"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="295ce-104">即時回應命令範例</span><span class="sxs-lookup"><span data-stu-id="295ce-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="295ce-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="295ce-105">**Applies to:**</span></span>
- [<span data-ttu-id="295ce-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="295ce-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="295ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="295ce-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="295ce-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="295ce-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="295ce-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="295ce-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="295ce-110">深入瞭解 live response 中使用的常見命令，並查看其一般使用方式的範例。</span><span class="sxs-lookup"><span data-stu-id="295ce-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="295ce-111">您可以執行基本或高級 live 回應命令，視授與您的角色而定。</span><span class="sxs-lookup"><span data-stu-id="295ce-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="295ce-112">如需基本及高級命令的詳細資訊，請參閱 [使用即時回應調查裝置上的實體](live-response.md)。</span><span class="sxs-lookup"><span data-stu-id="295ce-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="295ce-113">分析</span><span class="sxs-lookup"><span data-stu-id="295ce-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="295ce-114">連接</span><span class="sxs-lookup"><span data-stu-id="295ce-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="295ce-115">迪爾</span><span class="sxs-lookup"><span data-stu-id="295ce-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="295ce-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="295ce-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="295ce-117">findfile</span><span class="sxs-lookup"><span data-stu-id="295ce-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="295ce-118">getfile</span><span class="sxs-lookup"><span data-stu-id="295ce-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="295ce-119">下列檔案類型 **無法** 從 Live Response 中使用此命令下載：</span><span class="sxs-lookup"><span data-stu-id="295ce-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="295ce-120">重新分析點檔案</span><span class="sxs-lookup"><span data-stu-id="295ce-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="295ce-121">疏鬆檔案</span><span class="sxs-lookup"><span data-stu-id="295ce-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="295ce-122">空白檔</span><span class="sxs-lookup"><span data-stu-id="295ce-122">Empty files</span></span>
> * <span data-ttu-id="295ce-123">虛擬檔案或尚未在本機完全呈現的檔案</span><span class="sxs-lookup"><span data-stu-id="295ce-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="295ce-124">[PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)**支援這些** 檔案類型。</span><span class="sxs-lookup"><span data-stu-id="295ce-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="295ce-125">如果您在 Live Response 中使用此命令有問題，請使用 PowerShell 做為替代方式。</span><span class="sxs-lookup"><span data-stu-id="295ce-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="295ce-126">過程</span><span class="sxs-lookup"><span data-stu-id="295ce-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="295ce-127">putfile</span><span class="sxs-lookup"><span data-stu-id="295ce-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="295ce-128">登錄</span><span class="sxs-lookup"><span data-stu-id="295ce-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="295ce-129">修復</span><span class="sxs-lookup"><span data-stu-id="295ce-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="295ce-130">運行</span><span class="sxs-lookup"><span data-stu-id="295ce-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```
>[!NOTE]
>
> <span data-ttu-id="295ce-131">針對長時間執行命令，例如 "**run**" 或 "**getfile**"，您可能想要在命令的結尾使用 ' **&** ' 符號，以在背景中執行該動作。</span><span class="sxs-lookup"><span data-stu-id="295ce-131">For long running commands such as '**run**' or '**getfile**', you may want to use the '**&**' symbol at the end of the command to perform that action in the background.</span></span>
> <span data-ttu-id="295ce-132">這可讓您繼續調查機器，並在使用 '**fg**' [basic 命令](live-response.md#basic-commands)完成時，回到背景命令。</span><span class="sxs-lookup"><span data-stu-id="295ce-132">This will allow you to continue investigating the machine and return to the background command when done using '**fg**' [basic command](live-response.md#basic-commands).</span></span>
>
## <a name="scheduledtask"></a><span data-ttu-id="295ce-133">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="295ce-133">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="295ce-134">撤銷</span><span class="sxs-lookup"><span data-stu-id="295ce-134">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

