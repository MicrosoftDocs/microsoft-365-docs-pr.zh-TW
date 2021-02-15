---
title: 停用 Office 365 GCC 高和 DoD 中的 TLS 1.0 和1。1
description: 討論 Microsoft 在 Microsoft 365 中如何停用在 GCC 高和 DoD 環境中，對 TLS 1.1 和1.0 的支援。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: a0b1fecc9991cd7ba4ac915d3d684d43714014af
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233749"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="04efc-103">停用 Office 365 GCC 高和 DoD 中的 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="04efc-103">Disabling TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="04efc-104">摘要</span><span class="sxs-lookup"><span data-stu-id="04efc-104">Summary</span></span>

<span data-ttu-id="04efc-105">為了遵守聯邦風險和授權管理計畫的最新符合性標準 (FedRAMP) ，我們會停用 Microsoft 365 中的傳輸層安全性 (TLS) 版本1.1 和1.0，以供 GCC 高及 DoD 環境使用。</span><span class="sxs-lookup"><span data-stu-id="04efc-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="04efc-106">這項變更先前是透過 Microsoft 支援宣告的，以 [準備在 Office 365 中強制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="04efc-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="04efc-107">您的資料安全性很重要，我們承諾對可能影響服務使用的變更進行透明性。</span><span class="sxs-lookup"><span data-stu-id="04efc-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="04efc-108">雖然 [MICROSOFT TLS 1.0 的執行](https://support.microsoft.com/help/3117336) 沒有已知的安全性弱點，但仍然會繼續致力於 FedRAMP 規範標準。</span><span class="sxs-lookup"><span data-stu-id="04efc-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="04efc-109">因此，我們停用 Office 365 中的 TLS 1.1 和1.0，在2020年1月15日 DoD 環境中。</span><span class="sxs-lookup"><span data-stu-id="04efc-109">Therefore, we disabled TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="04efc-110">如需如何移除 TLS 1.1 和1.0 相依性的相關資訊，請參閱下列白皮書：</span><span class="sxs-lookup"><span data-stu-id="04efc-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="04efc-111">解決 TLS 1.0 問題</span><span class="sxs-lookup"><span data-stu-id="04efc-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="04efc-112">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="04efc-112">More information</span></span>

<span data-ttu-id="04efc-113">從2020年1月15日開始，在 GCC 高端和 DoD 環境中的 Office 365 會取代 TLS 1.1 及1.0。</span><span class="sxs-lookup"><span data-stu-id="04efc-113">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="04efc-114">在2020年1月15日，所有用戶端伺服器與瀏覽器伺服器的組合都應該使用 TLS 版本 1.2 (或更新版本) ，以確保所有連線都不會向 Office 365 服務提出任何問題。</span><span class="sxs-lookup"><span data-stu-id="04efc-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="04efc-115">這可能需要更新用戶端伺服器與瀏覽器伺服器的某些組合。</span><span class="sxs-lookup"><span data-stu-id="04efc-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="04efc-116">如果您未更新為 TLS 版本 1.2 (或更新版本) （2020年1月15日），當您嘗試連線到 Office 365 時，您會遇到問題。</span><span class="sxs-lookup"><span data-stu-id="04efc-116">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="04efc-117">此外，您必須更新為 TLS 1.2 (或更新版本) 做為解決方法的一部分。</span><span class="sxs-lookup"><span data-stu-id="04efc-117">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="04efc-118">您必須更新用戶端電腦，以確保您維護 Office 365 GCC 高和 DoD 的不間斷存取。</span><span class="sxs-lookup"><span data-stu-id="04efc-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="04efc-119">您必須更新透過 TLS 1.0 或 TLS 1.1 呼叫 Microsoft 365 APIs 的應用程式，才能使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="04efc-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="04efc-120">.NET 4.5 的預設值為 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="04efc-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="04efc-121">若要更新您的 .NET 設定，請參閱 [如何在用戶端上啟用傳輸層安全性 (TLS) 1.2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。</span><span class="sxs-lookup"><span data-stu-id="04efc-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="04efc-122">如需詳細資訊，請參閱 [在 Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="04efc-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="04efc-123">我們知道下列用戶端應用程式無法使用 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="04efc-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="04efc-124">Android 4.3 和舊版</span><span class="sxs-lookup"><span data-stu-id="04efc-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="04efc-125">Firefox 5.0 和舊版</span><span class="sxs-lookup"><span data-stu-id="04efc-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="04efc-126">Internet Explorer 8 – 10 on Windows 7 及更早版本</span><span class="sxs-lookup"><span data-stu-id="04efc-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="04efc-127">Windows Phone 8.0 上的 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="04efc-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="04efc-128">Safari 6.0.4/OS X 10.8.4 及更早版本</span><span class="sxs-lookup"><span data-stu-id="04efc-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="04efc-129">[！附注] 目前對 Microsoft Online services 連線的分析顯示，大部分的服務和端點請參閱極少的 TLS 1.1 和1.0 使用量，我們會提供這項變更的通知，讓您在支援 TLS 1.1 和1.0 結束之前，依照需要更新任何受影響的用戶端或伺服器。</span><span class="sxs-lookup"><span data-stu-id="04efc-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="04efc-130">如果您使用任何內部部署基礎結構的混合案例或 Active Directory Federation Services (AD FS) ，請確定基礎結構可以支援使用 TLS 1.2 (或更新版本) 的輸入和輸出連線。</span><span class="sxs-lookup"><span data-stu-id="04efc-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="04efc-131">除了當您使用無法使用 TLS 1.2 的列出用戶端時，您可能會遇到的停機情形，移除 TLS 1.1 及1.0 將會使您無法使用下列 Microsoft 產品：</span><span class="sxs-lookup"><span data-stu-id="04efc-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="04efc-132">Lync phone</span><span class="sxs-lookup"><span data-stu-id="04efc-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="04efc-133">參考</span><span class="sxs-lookup"><span data-stu-id="04efc-133">References</span></span>

<span data-ttu-id="04efc-134">下列支援文章說明的指導方針與參考，可協助確保用戶端使用 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="04efc-134">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="04efc-135">在 Office 365 中準備 TLS 1.2 的強制使用</span><span class="sxs-lookup"><span data-stu-id="04efc-135">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
