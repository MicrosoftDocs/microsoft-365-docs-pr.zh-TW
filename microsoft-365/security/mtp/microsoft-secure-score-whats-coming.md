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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583712"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="48c85-104">Microsoft 安全分數的情況為何？</span><span class="sxs-lookup"><span data-stu-id="48c85-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="48c85-105">若要讓[Microsoft 安全評分](microsoft-secure-score.md)為您安全性狀況的更佳代表並提高可用性，我們在近期進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="48c85-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="48c85-106">您的分數和可能的最大分數會變更。</span><span class="sxs-lookup"><span data-stu-id="48c85-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="48c85-107">不過，這不是指安全性狀況的變更。</span><span class="sxs-lookup"><span data-stu-id="48c85-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="48c85-108">若要深入瞭解最近的變更，請參閱[Microsoft Secure 得分的新功能？](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="48c85-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="48c85-109">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="48c85-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="48c85-110">移除不符合可靠度量期望的改進動作，或不提供安全狀況的有用標記法</span><span class="sxs-lookup"><span data-stu-id="48c85-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="48c85-111">為了確保 Microsoft 安全分數有意義，且每個改進動作都有意義且可靠，我們正在移除下列改進動作。</span><span class="sxs-lookup"><span data-stu-id="48c85-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="48c85-112">將 IRM 保護套用至檔</span><span class="sxs-lookup"><span data-stu-id="48c85-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="48c85-113">套用資料遺失防護原則</span><span class="sxs-lookup"><span data-stu-id="48c85-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-to-preview"></a><span data-ttu-id="48c85-114">將 Azure AD 改進動作新增至預覽</span><span class="sxs-lookup"><span data-stu-id="48c85-114">Adding Azure AD improvement action to preview</span></span>

<span data-ttu-id="48c85-115">將下列 Azure Active Directory 改進動作新增至[Microsoft Secure 得分的預覽版本](microsoft-secure-score-preview.md)：</span><span class="sxs-lookup"><span data-stu-id="48c85-115">Adding the following Azure Active Directory improvement action to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="48c85-116">不允許使用者將同意授與未受管理的應用程式（目前已發行版本本中提供）</span><span class="sxs-lookup"><span data-stu-id="48c85-116">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-to-preview"></a><span data-ttu-id="48c85-117">新增 Azure ATP 改進動作以供預覽</span><span class="sxs-lookup"><span data-stu-id="48c85-117">Adding Azure ATP improvement actions to preview</span></span>

<span data-ttu-id="48c85-118">將下列 Azure 高級威脅防護改進動作新增至[Microsoft Secure 得分的預覽版本](microsoft-secure-score-preview.md)：</span><span class="sxs-lookup"><span data-stu-id="48c85-118">Adding the following Azure Advanced Threat Protection improvement actions to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="48c85-119">停用網域控制站上的幕後列印程式服務</span><span class="sxs-lookup"><span data-stu-id="48c85-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="48c85-120">修改不安全的 Kerberos 委派以防止模仿</span><span class="sxs-lookup"><span data-stu-id="48c85-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="48c85-121">使用 Microsoft LAPS 保護和管理本機系統管理員密碼</span><span class="sxs-lookup"><span data-stu-id="48c85-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="48c85-122">降低橫向移動路徑對機密實體的風險</span><span class="sxs-lookup"><span data-stu-id="48c85-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="48c85-123">移除敏感群組中的睡眠帳戶</span><span class="sxs-lookup"><span data-stu-id="48c85-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="48c85-124">從實體中移除不安全的 SID 歷程記錄屬性</span><span class="sxs-lookup"><span data-stu-id="48c85-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="48c85-125">解決不安全的帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="48c85-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="48c85-126">停止清除文字認證曝光</span><span class="sxs-lookup"><span data-stu-id="48c85-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="48c85-127">停止舊版通訊協定通訊</span><span class="sxs-lookup"><span data-stu-id="48c85-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="48c85-128">停止弱密碼使用</span><span class="sxs-lookup"><span data-stu-id="48c85-128">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a><span data-ttu-id="48c85-129">支援 Microsoft Defender ATP 威脅 & 漏洞管理（TVM）預覽中的安全性建議</span><span class="sxs-lookup"><span data-stu-id="48c85-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in preview</span></span>

<span data-ttu-id="48c85-130">TVM 所提供的所有發行的安全性建議現在也可用於[預覽版本的 Microsoft 安全分數](microsoft-secure-score-preview.md)。</span><span class="sxs-lookup"><span data-stu-id="48c85-130">All released security recommendations supplied by TVM will now also be available the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md).</span></span>
