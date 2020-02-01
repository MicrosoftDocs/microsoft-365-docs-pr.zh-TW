---
title: 如何報告誤判或漏報中產生 Microsoft 威脅防護中
description: 某個項目已未接或錯誤偵測到的空調中 Microsoft 威脅防護？ 了解如何提交誤判或 false 的負號給 Microsoft 進行分析。
keywords: 自動化，調查、 提醒、 觸發程序、 動作、 修復、 正數，則為 false 誤判
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d9175e78326832a2be874359babae5ae9c689420
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600080"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="10c04-105">如何報告中自動進行調查並回應功能，則為 false positive/負號</span><span class="sxs-lookup"><span data-stu-id="10c04-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="10c04-106">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="10c04-106">**Applies to:**</span></span>
- <span data-ttu-id="10c04-107">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="10c04-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="10c04-108">未[自動的調查及回應功能](mtp-autoir.md)Microsoft 威脅防護中遺漏或錯誤偵測到某個嗎？</span><span class="sxs-lookup"><span data-stu-id="10c04-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="10c04-109">您可以向 Microsoft 報告，或調整您的通知 （如果需要）。</span><span class="sxs-lookup"><span data-stu-id="10c04-109">You can report it to Microsoft or adjust your alerts (if needed).</span></span> <span data-ttu-id="10c04-110">做為指南，請使用下表：</span><span class="sxs-lookup"><span data-stu-id="10c04-110">Use the following table as a guide:</span></span> 


|<span data-ttu-id="10c04-111">項目</span><span class="sxs-lookup"><span data-stu-id="10c04-111">Item</span></span>  |<span data-ttu-id="10c04-112">所偵測到</span><span class="sxs-lookup"><span data-stu-id="10c04-112">Detected by</span></span>  |<span data-ttu-id="10c04-113">如何將其報告</span><span class="sxs-lookup"><span data-stu-id="10c04-113">How to report it</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="10c04-114">電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="10c04-114">Email message</span></span> <br/><span data-ttu-id="10c04-115">電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="10c04-115">Email attachment</span></span> <br/><span data-ttu-id="10c04-116">在 [電子郵件訊息或 Office 檔案的 URL</span><span class="sxs-lookup"><span data-stu-id="10c04-116">URL in an email message or Office file</span></span>      |[<span data-ttu-id="10c04-117">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="10c04-117">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="10c04-118">送出可疑的垃圾郵件、 釣魚程式、 Url 和 microsoft Office 365 掃描的檔案</span><span class="sxs-lookup"><span data-stu-id="10c04-118">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="10c04-119">檔案或裝置上的應用程式</span><span class="sxs-lookup"><span data-stu-id="10c04-119">File or app on a device</span></span>    |[<span data-ttu-id="10c04-120">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="10c04-120">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="10c04-121">提交給 Microsoft 進行惡意程式碼分析的檔案</span><span class="sxs-lookup"><span data-stu-id="10c04-121">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |
|<span data-ttu-id="10c04-122">合法的使用由觸發警示</span><span class="sxs-lookup"><span data-stu-id="10c04-122">Alert triggered by legitimate use</span></span> <br/><span data-ttu-id="10c04-123">不精準的警示</span><span class="sxs-lookup"><span data-stu-id="10c04-123">Inaccurate alert</span></span>    |[<span data-ttu-id="10c04-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="10c04-124">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="10c04-125">或</span><span class="sxs-lookup"><span data-stu-id="10c04-125">or</span></span> <br/>[<span data-ttu-id="10c04-126">Azure 的進階的威脅偵測</span><span class="sxs-lookup"><span data-stu-id="10c04-126">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="10c04-127">管理提醒在 Cloud App Security 入口網站</span><span class="sxs-lookup"><span data-stu-id="10c04-127">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a><span data-ttu-id="10c04-128">後續步驟</span><span class="sxs-lookup"><span data-stu-id="10c04-128">Next steps</span></span>

- [<span data-ttu-id="10c04-129">與自動化調查及回應相關的核准或拒絕動作</span><span class="sxs-lookup"><span data-stu-id="10c04-129">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="10c04-130">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="10c04-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="10c04-131">使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="10c04-131">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
