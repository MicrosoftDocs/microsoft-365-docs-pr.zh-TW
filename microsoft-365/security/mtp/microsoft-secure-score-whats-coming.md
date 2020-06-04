---
title: Microsoft 安全分數的情況為何？
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分、如何計算詳細資料，以及安全性管理員可以預期的情況。
keywords: 安全性、惡意程式碼、Microsoft 365、M365、安全分數、安全性中心、改進動作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f9bca47c6a47468d0a5a37b77e4f587745bf619d
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545931"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="c99f8-104">Microsoft 安全分數的情況為何？</span><span class="sxs-lookup"><span data-stu-id="c99f8-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="c99f8-105">若要讓[Microsoft 安全評分](microsoft-secure-score-new.md)為您安全性狀況的更佳代表並提高可用性，我們在近期進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="c99f8-105">To make [Microsoft Secure Score](microsoft-secure-score-new.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="c99f8-106">您的分數和可能的最大分數會變更。</span><span class="sxs-lookup"><span data-stu-id="c99f8-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="c99f8-107">不過，這不是指安全性狀況的變更。</span><span class="sxs-lookup"><span data-stu-id="c99f8-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="c99f8-108">若要深入瞭解最近的變更，請參閱[Microsoft Secure 得分的新功能？](microsoft-secure-score-new.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="c99f8-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score-new.md#whats-new)</span></span>

## <a name="june-2020"></a><span data-ttu-id="c99f8-109">2020年6月</span><span class="sxs-lookup"><span data-stu-id="c99f8-109">June 2020</span></span>

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="c99f8-110">移除 Microsoft Defender 高級威脅防護的改進動作</span><span class="sxs-lookup"><span data-stu-id="c99f8-110">Remove improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="c99f8-111">開啟攻擊面減少規則</span><span class="sxs-lookup"><span data-stu-id="c99f8-111">Turn on Attack Surface Reduction rules</span></span>

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="c99f8-112">新增 Microsoft Defender 高級威脅防護的改進動作</span><span class="sxs-lookup"><span data-stu-id="c99f8-112">Add improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="c99f8-113">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="c99f8-113">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="c99f8-114">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="c99f8-114">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="c99f8-115">封鎖所有 Office 應用程式以建立子流程</span><span class="sxs-lookup"><span data-stu-id="c99f8-115">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="c99f8-116">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="c99f8-116">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="c99f8-117">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="c99f8-117">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="c99f8-118">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="c99f8-118">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="c99f8-119">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="c99f8-119">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="c99f8-120">封鎖 Office communication application 建立子流程</span><span class="sxs-lookup"><span data-stu-id="c99f8-120">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="c99f8-121">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="c99f8-121">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="c99f8-122">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="c99f8-122">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="c99f8-123">封鎖 Office 應用程式將程式碼注入其他程式</span><span class="sxs-lookup"><span data-stu-id="c99f8-123">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="c99f8-124">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="c99f8-124">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="c99f8-125">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="c99f8-125">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="c99f8-126">封鎖從 Windows local security 機關子系統（lsass.exe）偷竊的認證</span><span class="sxs-lookup"><span data-stu-id="c99f8-126">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="c99f8-127">封鎖 Office 宏的 WIN32 API 呼叫</span><span class="sxs-lookup"><span data-stu-id="c99f8-127">Block Win32 API calls from Office macros</span></span>
