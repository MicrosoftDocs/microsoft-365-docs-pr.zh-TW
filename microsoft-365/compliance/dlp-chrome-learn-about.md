---
title: 瞭解 Microsoft 合規性延伸模組 (預覽)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 合規性延伸模組會將監視並控制檔案活動和保護動作擴充至 Google Chrome 瀏覽器
ms.openlocfilehash: c8a5795b3be8b393fd3a934504449bf6db0c2f01
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113379"
---
# <a name="learn-about-the-microsoft-compliance-extension-preview"></a><span data-ttu-id="17363-103">瞭解 Microsoft 合規性延伸模組 (預覽)</span><span class="sxs-lookup"><span data-stu-id="17363-103">Learn about the Microsoft Compliance Extension (preview)</span></span>

<span data-ttu-id="17363-104">[端點資料外洩防護 (端點 DLP)](endpoint-dlp-learn-about.md)將 [Microsoft 365 資料外洩防護 (DLP)](dlp-learn-about-dlp.md) 的活動監視和保護功能擴充到 Windows 10 裝置上的敏感性項目。</span><span class="sxs-lookup"><span data-stu-id="17363-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="17363-105">將裝置上架至 Microsoft 365 合規性解決方案之後，使用者對敏感度項目所進行動作的相關資訊會顯示在[活動總管](data-classification-activity-explorer.md)中，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)對這些項目強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="17363-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="17363-106">在 Windows 10 裝置上安裝 Microsoft 合規性延伸模組之後，組織就可以在使用者嘗試使用 Google Chrome 存取或上傳敏感性項目至雲端服務時加以監視，並透過 DLP 強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="17363-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="17363-107">您可以監視和採取動作的活動</span><span class="sxs-lookup"><span data-stu-id="17363-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="17363-108">Microsoft 合規性延伸模組可讓您稽核及管理下列類型的活動，而使用者會在執行 Windows 10 的裝置上透過這些活動使用敏感度項目。</span><span class="sxs-lookup"><span data-stu-id="17363-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="17363-109">活動</span><span class="sxs-lookup"><span data-stu-id="17363-109">activity</span></span> |<span data-ttu-id="17363-110">描述</span><span class="sxs-lookup"><span data-stu-id="17363-110">description</span></span>  | <span data-ttu-id="17363-111">支援的原則動作</span><span class="sxs-lookup"><span data-stu-id="17363-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="17363-112">檔案已複製到雲端</span><span class="sxs-lookup"><span data-stu-id="17363-112">file copied to cloud</span></span>  | <span data-ttu-id="17363-113">當使用者嘗試透過 Chrome 瀏覽器將敏感性項目上傳到受限服務網域時偵測。</span><span class="sxs-lookup"><span data-stu-id="17363-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="17363-114">稽核，封鎖</span><span class="sxs-lookup"><span data-stu-id="17363-114">audit, block</span></span>|
|<span data-ttu-id="17363-115">已列印檔案</span><span class="sxs-lookup"><span data-stu-id="17363-115">file printed</span></span>  |<span data-ttu-id="17363-116">當使用者嘗試將 Chrome 瀏覽器中開啟的敏感性項目列印到本地或網路印表機時偵測</span><span class="sxs-lookup"><span data-stu-id="17363-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="17363-117">稽核、透過複寫封鎖、封鎖</span><span class="sxs-lookup"><span data-stu-id="17363-117">audit, block with override, block</span></span>|
|<span data-ttu-id="17363-118">檔案已複製到剪貼簿</span><span class="sxs-lookup"><span data-stu-id="17363-118">file copied to clipboard</span></span> |<span data-ttu-id="17363-119">當使用者嘗試從正於 Chrome 瀏覽器中查看的敏感性項目中複製資訊，然後將其貼上到另一個應用程式、流程或項目中時偵測。</span><span class="sxs-lookup"><span data-stu-id="17363-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="17363-120">稽核、透過複寫封鎖、封鎖</span><span class="sxs-lookup"><span data-stu-id="17363-120">audit, block with override, block</span></span>|
|<span data-ttu-id="17363-121">檔案已複製到卸除式儲存空間</span><span class="sxs-lookup"><span data-stu-id="17363-121">file copied to removable storage</span></span>    | <span data-ttu-id="17363-122">當使用者嘗試從 Chrome 瀏覽器中開啟的敏感性項目中的敏感性項目或資訊複製到卸除式媒體或 USB 裝置時偵測</span><span class="sxs-lookup"><span data-stu-id="17363-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="17363-123">稽核、透過複寫封鎖、封鎖</span><span class="sxs-lookup"><span data-stu-id="17363-123">audit, block with override, block</span></span>|
|<span data-ttu-id="17363-124">檔案已複製到網路共用</span><span class="sxs-lookup"><span data-stu-id="17363-124">file copied to network share</span></span>  |<span data-ttu-id="17363-125">當使用者嘗試從 Chrome 瀏覽器中開啟的敏感性項目中的敏感性項目或資訊複製到網路共用或對應望露磁碟機時偵測。</span><span class="sxs-lookup"><span data-stu-id="17363-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="17363-126">稽核、透過複寫封鎖、封鎖</span><span class="sxs-lookup"><span data-stu-id="17363-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="17363-127">部署程序</span><span class="sxs-lookup"><span data-stu-id="17363-127">Deployment process</span></span>
1. [<span data-ttu-id="17363-128">開始使用端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="17363-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="17363-129">Windows 10 裝置的上線工具及方法</span><span class="sxs-lookup"><span data-stu-id="17363-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="17363-130">在 Windows 10 裝置上安裝擴充功能</span><span class="sxs-lookup"><span data-stu-id="17363-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="17363-131">[建立或編輯 DLP 原則](create-test-tune-dlp-policy.md) 限制上傳到雲端服務，或以不允許的瀏覽器動作存取，並將其套用至您的 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="17363-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="17363-132">後續步驟</span><span class="sxs-lookup"><span data-stu-id="17363-132">Next steps</span></span>

<span data-ttu-id="17363-133">請參閱 [Microsoft 合規性延伸模組](dlp-chrome-get-started.md) 以取得完整的部署程序和案例。</span><span class="sxs-lookup"><span data-stu-id="17363-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="17363-134">請參閱</span><span class="sxs-lookup"><span data-stu-id="17363-134">See also</span></span>

- [<span data-ttu-id="17363-135">開始使用 Microsoft 合規性延伸模組</span><span class="sxs-lookup"><span data-stu-id="17363-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="17363-136">深入瞭解 Microsoft 365 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="17363-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="17363-137">Microsoft 端點資料外洩防護快速入門</span><span class="sxs-lookup"><span data-stu-id="17363-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="17363-138">使用 Microsoft 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="17363-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="17363-139">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="17363-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="17363-140">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="17363-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="17363-141">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="17363-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="17363-142">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="17363-142">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="17363-143">測試人員風險管理</span><span class="sxs-lookup"><span data-stu-id="17363-143">Insider Risk management</span></span>](insider-risk-management.md)
