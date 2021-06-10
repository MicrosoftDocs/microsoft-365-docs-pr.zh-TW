---
title: Advanced eDiscovery 中的 AzCopy 疑難排解
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在 Advanced eDiscovery 中為錯誤修正載入非 Office 365 資料時，排查 Azure AzCopy 的錯誤。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919289"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="3a781-103">Advanced eDiscovery 中的 AzCopy 疑難排解</span><span class="sxs-lookup"><span data-stu-id="3a781-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="3a781-104">當您在 Advanced eDiscovery 中載入非 Microsoft 365 資料或檔以進行錯誤修正時，使用者介面會提供 Azure AzCopy 命令，其中包含了您要上傳的檔案所在位置的參數，以及將檔案上傳至 Azure 的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="3a781-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="3a781-105">若要上傳檔，請複製此命令，然後在本機電腦上的命令提示字元中執行它。</span><span class="sxs-lookup"><span data-stu-id="3a781-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="3a781-106">下列螢幕擷取畫面顯示 AzCopy 命令的範例：</span><span class="sxs-lookup"><span data-stu-id="3a781-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Upload 非 Microsoft 365 檔案](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="3a781-108">通常，當您執行它時，提供的命令會正常運作。</span><span class="sxs-lookup"><span data-stu-id="3a781-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="3a781-109">不過，在某些情況下，顯示的命令不會順利執行。</span><span class="sxs-lookup"><span data-stu-id="3a781-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="3a781-110">可能的原因有幾個。</span><span class="sxs-lookup"><span data-stu-id="3a781-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="3a781-111">本機電腦上未安裝支援的 AzCopy 版本</span><span class="sxs-lookup"><span data-stu-id="3a781-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="3a781-112">此時，您必須使用 AzCopy app-v 8.1，以 Advanced eDiscovery 中載入非 Microsoft 365 的資料。</span><span class="sxs-lookup"><span data-stu-id="3a781-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="3a781-113">如果您不是使用 AzCopy 的第板，則在先前的螢幕擷取畫面所顯示的 [ **Upload** 檔案] 頁面上顯示的 AzCopy 命令，會傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="3a781-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="3a781-114">若要安裝此版本，請參閱[使用 AzCopy 的 Windows 傳送資料](/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="3a781-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="3a781-115">本機電腦上未安裝 AzCopy，或其未安裝在預設位置</span><span class="sxs-lookup"><span data-stu-id="3a781-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="3a781-116">如果 AzCopy 並未安裝或安裝在預設安裝位置（) 的預設安裝 (位置 `%ProgramFiles(x86)%` ）上，當您執行 AzCopy 命令時，可能會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="3a781-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="3a781-117">系統找不到指定的路徑。</span><span class="sxs-lookup"><span data-stu-id="3a781-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="3a781-118">如果本機電腦上未安裝 AzCopy，您可以在[Windows 上找到傳輸資料中的「AzCopy 中](/previous-versions/azure/storage/storage-use-azcopy)的安裝資訊」。</span><span class="sxs-lookup"><span data-stu-id="3a781-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="3a781-119">請務必將其安裝在預設位置。</span><span class="sxs-lookup"><span data-stu-id="3a781-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="3a781-120">如果安裝了 AzCopy，但是安裝的位置與預設位置不同，您可以複製命令、將其貼到文字檔，然後將路徑變更至已安裝 AzCopy 的位置。</span><span class="sxs-lookup"><span data-stu-id="3a781-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="3a781-121">例如，如果 Azcopy 位於 `%ProgramFiles%` ，您可以將命令的第一個部分變更 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` 為 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 。</span><span class="sxs-lookup"><span data-stu-id="3a781-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="3a781-122">進行此變更後，請從文本檔案複製並執行命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="3a781-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="3a781-123">如果 AzCopy 安裝在預設安裝位置的另一個位置，請考慮將其卸載，然後在預設位置重新安裝。</span><span class="sxs-lookup"><span data-stu-id="3a781-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="3a781-124">這可協助您避免未來發生此問題。</span><span class="sxs-lookup"><span data-stu-id="3a781-124">This will help prevent this issue in the future.</span></span>