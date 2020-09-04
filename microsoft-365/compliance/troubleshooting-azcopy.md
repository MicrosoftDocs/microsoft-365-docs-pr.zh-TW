---
title: 在高級 eDiscovery 中 AzCopy 疑難排解
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 疑難排解 Azure AzCopy 的錯誤。在 Advanced eDiscovery 中載入非 Office 365 資料以進行錯誤修正時。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 4bf8461cb02ca3601707f248a64d8a8a9741efab
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357703"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="4dea9-103">在高級 eDiscovery 中 AzCopy 疑難排解</span><span class="sxs-lookup"><span data-stu-id="4dea9-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="4dea9-104">在 [Advanced eDiscovery] 中載入非 Microsoft 365 資料或檔以進行錯誤修正時，使用者介面會提供 Azure AzCopy 命令，其中包含了您要上傳的檔案所在位置的參數，以及檔案將要上傳至的 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="4dea9-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="4dea9-105">若要上傳檔，請複製此命令，然後在本機電腦上的命令提示字元中執行它。</span><span class="sxs-lookup"><span data-stu-id="4dea9-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="4dea9-106">下列螢幕擷取畫面顯示 AzCopy 命令的範例：</span><span class="sxs-lookup"><span data-stu-id="4dea9-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![上傳非 Microsoft 365 檔案](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="4dea9-108">通常，當您執行它時，提供的命令會正常運作。</span><span class="sxs-lookup"><span data-stu-id="4dea9-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="4dea9-109">不過，在某些情況下，顯示的命令不會順利執行。</span><span class="sxs-lookup"><span data-stu-id="4dea9-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="4dea9-110">可能的原因有幾個。</span><span class="sxs-lookup"><span data-stu-id="4dea9-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="4dea9-111">本機電腦上未安裝支援的 AzCopy 版本</span><span class="sxs-lookup"><span data-stu-id="4dea9-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="4dea9-112">此時，您必須使用 AzCopy app-v 8.1，在 Advanced eDiscovery 中載入非 Microsoft 365 資料。</span><span class="sxs-lookup"><span data-stu-id="4dea9-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="4dea9-113">如果您不是使用 AzCopy 的第板，則顯示在先前的螢幕擷取畫面所顯示之 [上 **傳** 檔案] 頁面上的 AzCopy 命令會傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="4dea9-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="4dea9-114">若要安裝此版本，請參閱在 [Windows 上使用 AzCopy app-v 8.1 傳輸資料](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="4dea9-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="4dea9-115">本機電腦上未安裝 AzCopy，或其未安裝在預設位置</span><span class="sxs-lookup"><span data-stu-id="4dea9-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="4dea9-116">如果 AzCopy 並未安裝或安裝在預設安裝位置（) 的預設安裝 (位置 `%ProgramFiles(x86)%` ）上，當您執行 AzCopy 命令時，可能會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="4dea9-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="4dea9-117">系統找不到指定的路徑。</span><span class="sxs-lookup"><span data-stu-id="4dea9-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="4dea9-118">如果本機電腦上未安裝 AzCopy，您可以在 [使用 AzCopy 中的「傳送機 8.1](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)」，在 Windows 上尋找傳送資料的安裝資訊。</span><span class="sxs-lookup"><span data-stu-id="4dea9-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="4dea9-119">請務必將其安裝在預設位置。</span><span class="sxs-lookup"><span data-stu-id="4dea9-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="4dea9-120">如果安裝了 AzCopy，但是安裝的位置與預設位置不同，您可以複製命令、將其貼到文字檔，然後將路徑變更至已安裝 AzCopy 的位置。</span><span class="sxs-lookup"><span data-stu-id="4dea9-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="4dea9-121">例如，如果 Azcopy 位於 `%ProgramFiles%` ，您可以將命令的第一個部分變更 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` 為 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 。</span><span class="sxs-lookup"><span data-stu-id="4dea9-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="4dea9-122">進行此變更後，請從文本檔案複製並執行命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="4dea9-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="4dea9-123">如果 AzCopy 安裝在預設安裝位置的另一個位置，請考慮將其卸載，然後在預設位置重新安裝。</span><span class="sxs-lookup"><span data-stu-id="4dea9-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="4dea9-124">這可協助您避免未來發生此問題。</span><span class="sxs-lookup"><span data-stu-id="4dea9-124">This will help prevent this issue in the future.</span></span>
