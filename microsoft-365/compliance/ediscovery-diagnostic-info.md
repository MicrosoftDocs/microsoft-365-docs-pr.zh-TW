---
title: 收集電子文件探索診斷資訊
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解如何收集 Microsoft 支援案例的 eDiscovery 診斷資訊。
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926553"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="f7afc-103">收集電子文件探索診斷資訊</span><span class="sxs-lookup"><span data-stu-id="f7afc-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="f7afc-104">當您開啟與核心 eDiscovery 或 Advanced eDiscovery 相關的支援案例時，偶爾 Microsoft 支援工程師需要您問題的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="f7afc-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="f7afc-105">本文提供如何收集診斷資訊以協助工程師調查和解決問題的指導方針。</span><span class="sxs-lookup"><span data-stu-id="f7afc-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="f7afc-106">一般來說，您不需要先收集此資訊，直到 Microsoft 支援工程師要求您這麼做。</span><span class="sxs-lookup"><span data-stu-id="f7afc-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7afc-107">本文所述的指令程式和診斷資訊輸出可能包含有關組織中訴訟或內部調查的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="f7afc-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="f7afc-108">在將原始診斷資訊傳送至 Microsoft 支援之前，您應該查看資訊，並將任何敏感資訊 (，例如，將其他方的名稱或其他資訊以) 取代，以進行訴訟或調查 `XXXXXXX` 。</span><span class="sxs-lookup"><span data-stu-id="f7afc-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="f7afc-109">使用此方法也會向 Microsoft 支援工程師指出資訊已 redacted。</span><span class="sxs-lookup"><span data-stu-id="f7afc-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="f7afc-110">收集核心 eDiscovery 的診斷資訊</span><span class="sxs-lookup"><span data-stu-id="f7afc-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="f7afc-111">收集核心 eDiscovery 的診斷資訊以 Cmdlet 為基礎，因此您必須使用安全性 & 合規性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f7afc-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="f7afc-112">下列 PowerShell 範例會執行 Cmdlet，然後將輸出儲存至指定的文字檔。</span><span class="sxs-lookup"><span data-stu-id="f7afc-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="f7afc-113">在大多數支援案例中，您只需要執行下列其中一個命令。</span><span class="sxs-lookup"><span data-stu-id="f7afc-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="f7afc-114">若要執行下列 Cmdlet，請連線[至安全性 & 合規性 </span> 中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f7afc-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="f7afc-115">連線之後，請執行下列一或多個命令，並確定以實際的物件名稱取代預留位置。</span><span class="sxs-lookup"><span data-stu-id="f7afc-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="f7afc-116">檢查所產生的文字檔並 redacting 機密資訊之後，將其傳送給 Microsoft 支援工程師，以在您的案例上運作。</span><span class="sxs-lookup"><span data-stu-id="f7afc-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="f7afc-117">您也可以執行本節中的命令來收集 Microsoft 365 規範中心的 **內容搜尋** 頁面上所列之搜尋和匯出的診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="f7afc-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="f7afc-118">收集搜尋的相關資訊</span><span class="sxs-lookup"><span data-stu-id="f7afc-118">Collect information about searches</span></span>

<span data-ttu-id="f7afc-119">下列命令會收集用來調查內容搜尋問題或與核心 eDiscovery 案例相關聯之搜尋時有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="f7afc-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="f7afc-120">收集搜尋動作的相關資訊</span><span class="sxs-lookup"><span data-stu-id="f7afc-120">Collect information about search actions</span></span>

<span data-ttu-id="f7afc-121">下列命令會收集資訊，以調查預覽、匯出或清除內容搜尋結果的問題，或與核心 eDiscovery 案例相關聯的搜尋。</span><span class="sxs-lookup"><span data-stu-id="f7afc-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="f7afc-122">您可以按一下 [ **匯出** ] 索引標籤上所列的匯出，識別搜尋動作的名稱。若要識別預覽和清除動作的名稱，您可以執行 **Get-ComplianceSearchAction** Cmdlet 以顯示所有動作的清單。</span><span class="sxs-lookup"><span data-stu-id="f7afc-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="f7afc-123">搜尋動作名稱的格式是透過附加 `_Preview` 、 `_Export` 或 `_Purge` 對應的搜尋名稱所構造。</span><span class="sxs-lookup"><span data-stu-id="f7afc-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="f7afc-124">收集 eDiscovery 保留的資訊</span><span class="sxs-lookup"><span data-stu-id="f7afc-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="f7afc-125">當核心 eDiscovery 案例相關聯的 eDiscovery 暫止未如期運作時，請執行下列命令來收集有關案例保留原則的資訊，以及 eDiscovery 保留的相關案例保留規則相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f7afc-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="f7afc-126">在下列命令中， *案例保留原則名稱* 與 eDiscovery 保留的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="f7afc-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="f7afc-127">您可以在核心 eDiscovery 案例的 [ **保留** ] 索引標籤中識別此名稱。</span><span class="sxs-lookup"><span data-stu-id="f7afc-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="f7afc-128">收集所有案例資訊</span><span class="sxs-lookup"><span data-stu-id="f7afc-128">Collect all case information</span></span>

<span data-ttu-id="f7afc-129">在某些情況下，Microsoft 支援人員在調查您的問題時，並不會體現出所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="f7afc-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="f7afc-130">在此情況下，您可以收集核心 eDiscovery 案例的所有診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="f7afc-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="f7afc-131">下列命令中的 *核心 eDiscovery 案例名稱*，與 Microsoft 365 規範中心的 **核心 ediscovery** 頁面上顯示之案例的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="f7afc-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="f7afc-132">收集 Advanced eDiscovery 的診斷資訊</span><span class="sxs-lookup"><span data-stu-id="f7afc-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="f7afc-133">Advanced eDiscovery 案例中的 [**設定**] 索引標籤可讓您快速複製案例的診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="f7afc-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="f7afc-134">診斷資訊會儲存至剪貼簿，這樣您就可以將其貼到文字檔，並傳送給 Microsoft 支援人員。</span><span class="sxs-lookup"><span data-stu-id="f7afc-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="f7afc-135">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [ **顯示所有 > EDiscovery > Advanced**。</span><span class="sxs-lookup"><span data-stu-id="f7afc-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="f7afc-136">選取案例，然後按一下 [**設定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f7afc-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="f7afc-137">在 [ **案例資訊**] 下，按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="f7afc-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="f7afc-138">在飛入頁面上，按一下 [ **複製診斷資訊** ]，將資訊複製到剪貼簿。</span><span class="sxs-lookup"><span data-stu-id="f7afc-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="f7afc-139">在記事本) 中開啟文字檔 (，然後貼上文字檔中的資訊。</span><span class="sxs-lookup"><span data-stu-id="f7afc-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="f7afc-140">儲存文字檔，並將其命名 `AeD Diagnostic Info YYYY.MM.DD` 為 (例如) 所示 `AeD Diagnostic Info 2020.11.03` 。</span><span class="sxs-lookup"><span data-stu-id="f7afc-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="f7afc-141">檢查檔案並 redacting 機密資訊之後，將其傳送給 Microsoft 支援工程師，以在您的案例上運作。</span><span class="sxs-lookup"><span data-stu-id="f7afc-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>