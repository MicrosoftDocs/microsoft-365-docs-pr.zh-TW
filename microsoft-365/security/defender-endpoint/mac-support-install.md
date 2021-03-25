---
title: 疑難排解適用于 Mac 的 Microsoft Defender ATP 安裝問題
description: 疑難排解 Microsoft Defender ATP for Mac 中的安裝問題。
keywords: microsoft、defender、atp、mac、安裝
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
ms.openlocfilehash: 888bffdb85adeb7af58504439c1c31c7232cd73b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187622"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="5f751-104">疑難排解適用于 Mac 的 Microsoft Defender 端點安裝問題</span><span class="sxs-lookup"><span data-stu-id="5f751-104">Troubleshoot installation issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5f751-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5f751-105">**Applies to:**</span></span>

- [<span data-ttu-id="5f751-106">Mac 版端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5f751-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="5f751-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5f751-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5f751-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f751-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5f751-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5f751-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5f751-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="5f751-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="5f751-111">安裝失敗</span><span class="sxs-lookup"><span data-stu-id="5f751-111">Installation failed</span></span>

<span data-ttu-id="5f751-112">手動安裝時，安裝精靈的 [摘要] 頁面會說「安裝期間發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="5f751-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="5f751-113">安裝程式發生錯誤，導致安裝失敗。</span><span class="sxs-lookup"><span data-stu-id="5f751-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="5f751-114">請與軟體製造商聯繫以取得協助。」</span><span class="sxs-lookup"><span data-stu-id="5f751-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="5f751-115">針對 MDM 部署，它也會顯示為一般安裝失敗。</span><span class="sxs-lookup"><span data-stu-id="5f751-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="5f751-116">雖然使用者未向使用者顯示確切的錯誤，我們還是會保留記錄檔與安裝進度 `/Library/Logs/Microsoft/mdatp/install.log` 。</span><span class="sxs-lookup"><span data-stu-id="5f751-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="5f751-117">每個安裝會話都會附加到此記錄檔。</span><span class="sxs-lookup"><span data-stu-id="5f751-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="5f751-118">您可以使用 `sed` 僅輸出上一個安裝會話：</span><span class="sxs-lookup"><span data-stu-id="5f751-118">You can use `sed` to output the last installation session only:</span></span>

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

<span data-ttu-id="5f751-119">在此範例中，會將實際原因加上首碼 `[ERROR]` 。</span><span class="sxs-lookup"><span data-stu-id="5f751-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="5f751-120">由於不支援這些版本之間的降級，因此安裝失敗。</span><span class="sxs-lookup"><span data-stu-id="5f751-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="5f751-121">MDATP 安裝記錄遺失或未更新</span><span class="sxs-lookup"><span data-stu-id="5f751-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="5f751-122">在極少的情況下，安裝會在 MDATP 的/Library/Logs/Microsoft/mdatp/install.log 檔案中留下任何追蹤。</span><span class="sxs-lookup"><span data-stu-id="5f751-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="5f751-123">您可以在 MDM 部署中查詢 macOS 的記錄檔，確認安裝發生問題，並分析可能的錯誤 (當沒有用戶端 UI) 時，這會很有説明。</span><span class="sxs-lookup"><span data-stu-id="5f751-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="5f751-124">建議您使用縮小時間的時段執行查詢，並根據記錄處理常式名稱來篩選，因為會有大量的資訊。</span><span class="sxs-lookup"><span data-stu-id="5f751-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
