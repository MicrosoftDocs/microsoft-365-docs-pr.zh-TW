---
title: 收集診斷資料以取得更新規範和 Windows Defender Microsoft Defender 防毒軟體
description: 使用工具收集資料，以在使用 Microsoft Defender 防毒軟體評估新增時，對更新規範問題進行疑難排解
keywords: 疑難排解，錯誤，修正，更新規範，oms，監視器，報表，Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2aaf3d1c650713a7f6cfb7b9abb9f2232013d6db
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274793"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a><span data-ttu-id="676b7-104">收集 Microsoft Defender AV 評估的更新規範診斷資料</span><span class="sxs-lookup"><span data-stu-id="676b7-104">Collect Update Compliance diagnostic data for Microsoft Defender AV Assessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="676b7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="676b7-105">**Applies to:**</span></span>

- [<span data-ttu-id="676b7-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="676b7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="676b7-107">本文說明如何收集可供 Microsoft 支援人員和工程小組使用的診斷資料，以協助疑難排解在更新規範增益集中使用 Microsoft Defender AV 評估區段時可能會遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="676b7-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender AV Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="676b7-108">嘗試此程式之前，請先確定您已閱讀「[疑難排解 Microsoft Defender 防毒軟體報告](troubleshoot-reporting.md)」、[符合所有需求的必要條件]，並採取任何其他建議的疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="676b7-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="676b7-109">在至少兩部未報告或顯示更新規範的裝置上，採取下列步驟取得 .cab 診斷檔案：</span><span class="sxs-lookup"><span data-stu-id="676b7-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="676b7-110">以下列方式開啟命令提示字元的系統管理員層級版本：</span><span class="sxs-lookup"><span data-stu-id="676b7-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="676b7-111">a.</span><span class="sxs-lookup"><span data-stu-id="676b7-111">a.</span></span> <span data-ttu-id="676b7-112">開啟 [ **開始** ] 功能表。</span><span class="sxs-lookup"><span data-stu-id="676b7-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="676b7-113">b.</span><span class="sxs-lookup"><span data-stu-id="676b7-113">b.</span></span> <span data-ttu-id="676b7-114">輸入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="676b7-114">Type **cmd**.</span></span> <span data-ttu-id="676b7-115">在 **命令提示** 字元上按一下滑鼠右鍵，然後按一下 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="676b7-115">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="676b7-116">c.</span><span class="sxs-lookup"><span data-stu-id="676b7-116">c.</span></span> <span data-ttu-id="676b7-117">輸入系統管理員認證或核准提示。</span><span class="sxs-lookup"><span data-stu-id="676b7-117">Enter administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="676b7-118">流覽至 Windows Defender 目錄。</span><span class="sxs-lookup"><span data-stu-id="676b7-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="676b7-119">此為預設值 `C:\Program Files\Windows Defender` 。</span><span class="sxs-lookup"><span data-stu-id="676b7-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="676b7-120">輸入下列命令，然後按 **enter**</span><span class="sxs-lookup"><span data-stu-id="676b7-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="676b7-121">會產生包含各種診斷記錄的 .cab 檔案。</span><span class="sxs-lookup"><span data-stu-id="676b7-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="676b7-122">會在命令提示字元的輸出中指定檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="676b7-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="676b7-123">根據預設，位置是 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="676b7-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="676b7-124">將這些 .cab 檔複製到可供 Microsoft 支援人員存取的位置。</span><span class="sxs-lookup"><span data-stu-id="676b7-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="676b7-125">例如，您可以將密碼保護的 OneDrive 資料夾與我們共用。</span><span class="sxs-lookup"><span data-stu-id="676b7-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="676b7-126">使用 <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">更新規範支援電子郵件範本</a>傳送電子郵件，並使用下列資訊填寫範本：</span><span class="sxs-lookup"><span data-stu-id="676b7-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="676b7-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="676b7-127">See also</span></span>

- [<span data-ttu-id="676b7-128">Windows Defender Microsoft Defender 防毒軟體報告疑難排解</span><span class="sxs-lookup"><span data-stu-id="676b7-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)