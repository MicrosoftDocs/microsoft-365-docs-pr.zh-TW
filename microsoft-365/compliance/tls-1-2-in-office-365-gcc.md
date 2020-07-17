---
title: 取代 TLS 1.0 和 1.1 in Office 365 GCC 高和 DoD
description: 討論 Microsoft 如何將日期向前移動，以停止支援在 Office 365 中的 GCC 高端和 DoD 環境中的 TLS 1.1 和1.0，並準備使用 TLS 1.2。
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024817"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="0efc9-103">取代 TLS 1.0 和 1.1 in Office 365 GCC 高和 DoD</span><span class="sxs-lookup"><span data-stu-id="0efc9-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0efc9-104">世界正處於疫情大爆發中，Microsoft 公司也意識到了這對客戶與合作夥伴的影響。</span><span class="sxs-lookup"><span data-stu-id="0efc9-104">The world is in the middle of a pandemic, and we at Microsoft are aware of the impact on our customers and partners.</span></span> <span data-ttu-id="0efc9-105">為了減輕商業客戶負擔，我們暫時停止了 TLS 1.0和1.1 的取代執法。</span><span class="sxs-lookup"><span data-stu-id="0efc9-105">To lighten the burden on our commercial customers, we have temporarily halted any deprecation enforcement of TLS 1.0 and 1.1.</span></span> <span data-ttu-id="0efc9-106">當前危機穩定後，將會依照修訂後的時間表發送更新。</span><span class="sxs-lookup"><span data-stu-id="0efc9-106">An update will be sent on a revised timeline after the current crisis stabilizes.</span></span> <span data-ttu-id="0efc9-107">（本文已進行修訂以反映變更。）</span><span class="sxs-lookup"><span data-stu-id="0efc9-107">(This article is revised to reflect the change.)</span></span>

## <a name="summary"></a><span data-ttu-id="0efc9-108">摘要</span><span class="sxs-lookup"><span data-stu-id="0efc9-108">Summary</span></span>

<span data-ttu-id="0efc9-109">為了遵守聯邦風險和授權管理計畫（FedRAMP）的最新符合性標準，我們在 Microsoft Office 365 中，移至取代 Transport Layer Security （TLS）版本1.1 和1.0，以供 GCC 高和 DoD 環境使用。</span><span class="sxs-lookup"><span data-stu-id="0efc9-109">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are moving to deprecate Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="0efc9-110">這項變更先前是透過 Microsoft 支援宣告的，以 [準備在 Office 365 中強制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="0efc9-110">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="0efc9-111">我們知道您的資料安全性很重要，我們承諾對可能影響服務使用的變更進行透明性。</span><span class="sxs-lookup"><span data-stu-id="0efc9-111">We understand that the security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="0efc9-112">雖然[MICROSOFT TLS 1.0 的執行](https://support.microsoft.com/help/3117336)沒有已知的安全性弱點，但仍然會繼續致力於 FedRAMP 規範標準。</span><span class="sxs-lookup"><span data-stu-id="0efc9-112">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="0efc9-113">因此，我們會在從1.1 年1月15日開始2020，取代環境 DoD 中的 Office 365 中，TLS 和1.0。</span><span class="sxs-lookup"><span data-stu-id="0efc9-113">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="0efc9-114">如需如何移除 TLS 1.1 和1.0 相依性的相關資訊，請參閱下列白皮書：</span><span class="sxs-lookup"><span data-stu-id="0efc9-114">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="0efc9-115">解決 TLS 1.0 問題</span><span class="sxs-lookup"><span data-stu-id="0efc9-115">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="0efc9-116">在準備 TLS 1.1 和1.0 的此變更時，建議您改用 TLS 版本1.2。</span><span class="sxs-lookup"><span data-stu-id="0efc9-116">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="0efc9-117">如需詳細資訊，請參閱[在 Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="0efc9-117">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="0efc9-118">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0efc9-118">More information</span></span>

<span data-ttu-id="0efc9-119">從2020年1月15日開始，在 GCC 高端和 DoD 環境中的 Office 365 會取代 TLS 1.1 及1.0。</span><span class="sxs-lookup"><span data-stu-id="0efc9-119">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="0efc9-120">在2020年1月15日，所有用戶端伺服器與瀏覽器伺服器的組合都應該使用 TLS 版本1.2 （或更新版本），以確保所有連線都不會有任何問題給 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="0efc9-120">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="0efc9-121">這可能需要更新用戶端伺服器與瀏覽器伺服器的某些組合。</span><span class="sxs-lookup"><span data-stu-id="0efc9-121">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="0efc9-122">如果您未更新至 TLS 版本1.2 （或更新版本）于1月 15 2020 日，當您嘗試連線到 Office 365 時，您會遇到問題。</span><span class="sxs-lookup"><span data-stu-id="0efc9-122">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="0efc9-123">此外，您還必須更新至 TLS 1.2 （或更新版本），以作為解決方法的一部分。</span><span class="sxs-lookup"><span data-stu-id="0efc9-123">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="0efc9-124">我們知道下列用戶端無法使用 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="0efc9-124">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="0efc9-125">Android 4.3 和舊版</span><span class="sxs-lookup"><span data-stu-id="0efc9-125">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="0efc9-126">Firefox 5.0 和舊版</span><span class="sxs-lookup"><span data-stu-id="0efc9-126">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="0efc9-127">Internet Explorer 8 – 10 on Windows 7 及更早版本</span><span class="sxs-lookup"><span data-stu-id="0efc9-127">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="0efc9-128">Windows Phone 8.0 上的 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="0efc9-128">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="0efc9-129">Safari 6.0.4/OS X 10.8.4 及更早版本</span><span class="sxs-lookup"><span data-stu-id="0efc9-129">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="0efc9-130">建議您更新用戶端，以確保您維護 Office 365 GCC 高和 DoD 的不間斷存取。</span><span class="sxs-lookup"><span data-stu-id="0efc9-130">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="0efc9-131">[！附注] 目前對 Microsoft Online services 連線的分析顯示，大部分的服務和端點請參閱極少的 TLS 1.1 和1.0 使用量，我們會提供這項變更的通知，讓您在支援 TLS 1.1 和1.0 結束之前，依照需要更新任何受影響的用戶端或伺服器。</span><span class="sxs-lookup"><span data-stu-id="0efc9-131">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="0efc9-132">如果您正在使用任何內部部署基礎結構的混合式案例或 Active Directory Federation Services （AD FS），請確定基礎結構可以支援使用 TLS 1.2 （或更新版本）的輸入和輸出連線。</span><span class="sxs-lookup"><span data-stu-id="0efc9-132">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="0efc9-133">除了當您使用無法使用 TLS 1.2 的列出用戶端時，您可能會遇到的停機情形，移除 TLS 1.1 及1.0 將會使您無法使用下列 Microsoft 產品：</span><span class="sxs-lookup"><span data-stu-id="0efc9-133">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="0efc9-134">Lync phone</span><span class="sxs-lookup"><span data-stu-id="0efc9-134">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="0efc9-135">參考</span><span class="sxs-lookup"><span data-stu-id="0efc9-135">References</span></span>

<span data-ttu-id="0efc9-136">下列支援文章說明的指導方針與參考，可協助確保用戶端使用 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="0efc9-136">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="0efc9-137">在 Office 365 中準備 TLS 1.2 的強制使用</span><span class="sxs-lookup"><span data-stu-id="0efc9-137">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
