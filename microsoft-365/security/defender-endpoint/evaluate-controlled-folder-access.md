---
title: 評估受控資料夾存取權
description: 請參閱控制的資料夾存取可如何協助保護檔案不受惡意應用程式變更。
keywords: Exploit protection，windows 10，windows defender，勒索軟體，保護，評估，測試，示範，嘗試
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 15ea4696052a6c987314e3c7b0dd282a49ed4df8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842911"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="c7cd4-104">評估受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="c7cd4-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c7cd4-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c7cd4-105">**Applies to:**</span></span>
- [<span data-ttu-id="c7cd4-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c7cd4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c7cd4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7cd4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c7cd4-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="c7cd4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c7cd4-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="c7cd4-110">「[受管理的資料夾存取](controlled-folders.md)」是一項功能，可協助您保護檔和檔案，避免遭到可疑或惡意應用程式的修改。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="c7cd4-111">Windows Server 2019 和 Windows 10 用戶端支援受控資料夾存取。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="c7cd4-112">在協助防範 [勒索軟體](https://www.microsoft.com/wdsi/threats/ransomware) ，以嘗試加密檔案並將檔案保留在 hostage 中特別有用。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="c7cd4-113">本文可協助您評估受控資料夾存取。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="c7cd4-114">它說明如何啟用稽核模式，以便您可以直接在組織中測試該功能。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="c7cd4-115">您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範案例網站，確認該功能是否正常運作，並查看其運作方式。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="c7cd4-116">使用稽核模式衡量影響</span><span class="sxs-lookup"><span data-stu-id="c7cd4-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="c7cd4-117">啟用「受管理的資料夾存取」稽核模式，以查看完全啟用 *時所發生的狀況* 記錄。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="c7cd4-118">測試該功能在組織中的運作方式，以確保其不會影響您的企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="c7cd4-119">您也可以瞭解一般會在一段時間內發生的可疑檔案修正嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="c7cd4-120">若要啟用稽核模式，請使用下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c7cd4-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="c7cd4-121">如果您想要完全核查控制的資料夾存取在組織中的運作方式，您必須使用管理工具，將此設定部署至網路中的裝置 (s) 。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="c7cd4-122">您也可以使用「群組原則」、「Intune」、「行動裝置管理」 (MDM) 或 Microsoft 端點管理員來設定及部署設定，如主要的[受控資料夾存取主題](controlled-folders.md)所述。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="c7cd4-123">在 Windows 事件檢視器中檢查受控資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="c7cd4-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="c7cd4-124">下列受控資料夾存取事件會顯示在 [Microsoft/Windows/Windows Defender/Operational] 資料夾底下 Windows 事件檢視器中。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="c7cd4-125">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="c7cd4-125">Event ID</span></span> | <span data-ttu-id="c7cd4-126">描述</span><span class="sxs-lookup"><span data-stu-id="c7cd4-126">Description</span></span>
-|-
 <span data-ttu-id="c7cd4-127">5007</span><span class="sxs-lookup"><span data-stu-id="c7cd4-127">5007</span></span> | <span data-ttu-id="c7cd4-128">設定變更時的事件</span><span class="sxs-lookup"><span data-stu-id="c7cd4-128">Event when settings are changed</span></span>
 <span data-ttu-id="c7cd4-129">1124</span><span class="sxs-lookup"><span data-stu-id="c7cd4-129">1124</span></span> | <span data-ttu-id="c7cd4-130">已審核的受管理資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="c7cd4-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="c7cd4-131">1123</span><span class="sxs-lookup"><span data-stu-id="c7cd4-131">1123</span></span> | <span data-ttu-id="c7cd4-132">封鎖的受管理資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="c7cd4-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="c7cd4-133">您可以設定[Windows 事件轉移訂閱](/windows/win32/wec/setting-up-a-source-initiated-subscription)來集中收集記錄。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-133">You can configure a [Windows Event Forwarding subscription](/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="c7cd4-134">自訂受保護的資料夾和應用程式</span><span class="sxs-lookup"><span data-stu-id="c7cd4-134">Customize protected folders and apps</span></span>

<span data-ttu-id="c7cd4-135">在評估過程中，您可能會想要新增至受保護的資料夾清單，或允許某些應用程式修改檔案。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="c7cd4-136">請參閱使用「管理」工具（包括群組原則、PowerShell 及 MDM 設定服務提供者 (Csp) ）設定功能，以 [保護重要的資料夾存取權](controlled-folders.md) 。</span><span class="sxs-lookup"><span data-stu-id="c7cd4-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7cd4-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c7cd4-137">See also</span></span>

* [<span data-ttu-id="c7cd4-138">使用受控資料夾存取權來保護重要資料夾</span><span class="sxs-lookup"><span data-stu-id="c7cd4-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="c7cd4-139">評估適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c7cd4-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="c7cd4-140">使用稽核模式</span><span class="sxs-lookup"><span data-stu-id="c7cd4-140">Use audit mode</span></span>](audit-windows-defender.md)
