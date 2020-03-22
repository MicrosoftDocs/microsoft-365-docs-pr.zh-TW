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
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895438"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="cd760-104">Microsoft 安全分數的情況為何？</span><span class="sxs-lookup"><span data-stu-id="cd760-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="cd760-105">若要讓 Microsoft 安全評分為您安全性狀況的更佳代表並提高可用性，我們在近期進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="cd760-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="cd760-106">您的分數和可能的最大分數會變更。</span><span class="sxs-lookup"><span data-stu-id="cd760-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="cd760-107">不過，這不是指安全性狀況的變更。</span><span class="sxs-lookup"><span data-stu-id="cd760-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="cd760-108">若要深入瞭解最近的變更，請參閱[Microsoft Secure 得分的新功能？](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="cd760-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="cd760-109">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="cd760-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="cd760-110">移除不符合可靠度量期望的改進動作，或不提供安全狀況的有用標記法</span><span class="sxs-lookup"><span data-stu-id="cd760-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="cd760-111">為了確保 Microsoft 安全分數有意義，且每個改進動作都有意義且可靠，我們正在移除下列改進動作。</span><span class="sxs-lookup"><span data-stu-id="cd760-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="cd760-112">刪除/封鎖過去30天內未使用的帳戶</span><span class="sxs-lookup"><span data-stu-id="cd760-112">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="cd760-113">指定少於5個全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="cd760-113">Designate fewer than 5 global admins</span></span>
- <span data-ttu-id="cd760-114">將 IRM 保護套用至檔</span><span class="sxs-lookup"><span data-stu-id="cd760-114">Apply IRM protections to documents</span></span>
- <span data-ttu-id="cd760-115">套用資料遺失防護原則</span><span class="sxs-lookup"><span data-stu-id="cd760-115">Apply Data Loss Prevention policies</span></span>

### <a name="adding-additional-control-support-in-the-preview-version"></a><span data-ttu-id="cd760-116">新增預覽版本中的其他控制項支援</span><span class="sxs-lookup"><span data-stu-id="cd760-116">Adding additional control support in the preview version</span></span>
- <span data-ttu-id="cd760-117">不允許使用者將同意授與未受管理的應用程式（目前已發行版本本中提供）</span><span class="sxs-lookup"><span data-stu-id="cd760-117">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a><span data-ttu-id="cd760-118">支援其他 Microsoft Cloud App 安全性改進動作</span><span class="sxs-lookup"><span data-stu-id="cd760-118">Support for additional Microsoft Cloud App Security improvement actions</span></span>
- <span data-ttu-id="cd760-119">停用網域控制站上的幕後列印程式服務</span><span class="sxs-lookup"><span data-stu-id="cd760-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="cd760-120">修改不安全的 Kerberos 委派以防止模仿</span><span class="sxs-lookup"><span data-stu-id="cd760-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="cd760-121">使用 Microsoft LAPS 保護和管理本機系統管理員密碼</span><span class="sxs-lookup"><span data-stu-id="cd760-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="cd760-122">降低橫向移動路徑對機密實體的風險</span><span class="sxs-lookup"><span data-stu-id="cd760-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="cd760-123">移除敏感群組中的睡眠帳戶</span><span class="sxs-lookup"><span data-stu-id="cd760-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="cd760-124">從實體中移除不安全的 SID 歷程記錄屬性</span><span class="sxs-lookup"><span data-stu-id="cd760-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="cd760-125">解決不安全的帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="cd760-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="cd760-126">停止清除文字認證曝光</span><span class="sxs-lookup"><span data-stu-id="cd760-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="cd760-127">停止舊版通訊協定通訊</span><span class="sxs-lookup"><span data-stu-id="cd760-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="cd760-128">停止弱密碼使用</span><span class="sxs-lookup"><span data-stu-id="cd760-128">Stop weak cipher usage</span></span>

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a><span data-ttu-id="cd760-129">支援 Microsoft Defender ATP 威脅 & 漏洞管理（TVM）安全性建議</span><span class="sxs-lookup"><span data-stu-id="cd760-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations</span></span>
- <span data-ttu-id="cd760-130">TVM 所提供的所有發行安全性建議現在也會在 Microsoft 安全分數中提供。</span><span class="sxs-lookup"><span data-stu-id="cd760-130">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
