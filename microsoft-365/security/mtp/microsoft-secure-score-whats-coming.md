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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541104"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="cae30-104">Microsoft 安全分數的情況為何？</span><span class="sxs-lookup"><span data-stu-id="cae30-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="cae30-105">若要讓 Microsoft 安全評分為您安全性狀況的更佳代表並提高可用性，我們在近期進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="cae30-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="cae30-106">您的分數和可能的最大分數會變更。</span><span class="sxs-lookup"><span data-stu-id="cae30-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="cae30-107">不過，這不是指安全性狀況的變更。</span><span class="sxs-lookup"><span data-stu-id="cae30-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="cae30-108">若要深入瞭解最近的變更，請參閱[Microsoft Secure 得分的新功能？](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="cae30-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="cae30-109">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="cae30-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="cae30-110">移除不符合可靠度量期望的改進動作，或不提供安全狀況的有用標記法</span><span class="sxs-lookup"><span data-stu-id="cae30-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="cae30-111">為了確保 Microsoft 安全分數有意義，且每個改進動作都有意義且可靠，我們正在移除下列改進動作。</span><span class="sxs-lookup"><span data-stu-id="cae30-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="cae30-112">將 IRM 保護套用至檔</span><span class="sxs-lookup"><span data-stu-id="cae30-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="cae30-113">套用資料遺失防護原則</span><span class="sxs-lookup"><span data-stu-id="cae30-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a><span data-ttu-id="cae30-114">在預覽版本中新增 Azure AD 改進動作</span><span class="sxs-lookup"><span data-stu-id="cae30-114">Adding Azure AD improvement action in the preview version</span></span>

- <span data-ttu-id="cae30-115">不允許使用者將同意授與未受管理的應用程式（目前已發行版本本中提供）</span><span class="sxs-lookup"><span data-stu-id="cae30-115">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a><span data-ttu-id="cae30-116">在預覽版本中新增 Azure ATP 改進動作</span><span class="sxs-lookup"><span data-stu-id="cae30-116">Adding Azure ATP improvement actions in the preview version</span></span>

- <span data-ttu-id="cae30-117">停用網域控制站上的幕後列印程式服務</span><span class="sxs-lookup"><span data-stu-id="cae30-117">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="cae30-118">修改不安全的 Kerberos 委派以防止模仿</span><span class="sxs-lookup"><span data-stu-id="cae30-118">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="cae30-119">使用 Microsoft LAPS 保護和管理本機系統管理員密碼</span><span class="sxs-lookup"><span data-stu-id="cae30-119">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="cae30-120">降低橫向移動路徑對機密實體的風險</span><span class="sxs-lookup"><span data-stu-id="cae30-120">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="cae30-121">移除敏感群組中的睡眠帳戶</span><span class="sxs-lookup"><span data-stu-id="cae30-121">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="cae30-122">從實體中移除不安全的 SID 歷程記錄屬性</span><span class="sxs-lookup"><span data-stu-id="cae30-122">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="cae30-123">解決不安全的帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="cae30-123">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="cae30-124">停止清除文字認證曝光</span><span class="sxs-lookup"><span data-stu-id="cae30-124">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="cae30-125">停止舊版通訊協定通訊</span><span class="sxs-lookup"><span data-stu-id="cae30-125">Stop legacy protocols communication</span></span>
- <span data-ttu-id="cae30-126">停止弱密碼使用</span><span class="sxs-lookup"><span data-stu-id="cae30-126">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a><span data-ttu-id="cae30-127">支援 Microsoft Defender ATP 威脅 & 漏洞管理（TVM）預覽版本中的安全性建議</span><span class="sxs-lookup"><span data-stu-id="cae30-127">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in the preview version</span></span>

- <span data-ttu-id="cae30-128">TVM 所提供的所有發行安全性建議現在也會在 Microsoft 安全分數中提供。</span><span class="sxs-lookup"><span data-stu-id="cae30-128">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
