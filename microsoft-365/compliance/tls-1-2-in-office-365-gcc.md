---
title: 取代 TLS 1.0 和 1.1 in Office 365 GCC 高和 DoD
description: 討論 Microsoft 如何將日期向前移動，以停止支援在 Office 365 中的 GCC 高端和 DoD 環境中的 TLS 1.1 和1.0，並準備使用 TLS 1.2。
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
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158878"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="9b448-103">取代 TLS 1.0 和 1.1 in Office 365 GCC 高和 DoD</span><span class="sxs-lookup"><span data-stu-id="9b448-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="9b448-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9b448-104">Summary</span></span>

<span data-ttu-id="9b448-105">為了遵守聯邦風險和授權管理計畫（FedRAMP）的最新符合性標準，我們在 Microsoft Office 365 中取代 Transport Layer Security （TLS）版本1.1 和1.0，以供 GCC 高和 DoD 環境使用。</span><span class="sxs-lookup"><span data-stu-id="9b448-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are deprecating Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="9b448-106">這項變更先前是透過 Microsoft 支援宣告的，以 [準備在 Office 365 中強制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="9b448-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="9b448-107">您的資料安全性很重要，我們承諾對可能影響服務使用的變更進行透明性。</span><span class="sxs-lookup"><span data-stu-id="9b448-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="9b448-108">雖然[MICROSOFT TLS 1.0 的執行](https://support.microsoft.com/help/3117336)沒有已知的安全性弱點，但仍然會繼續致力於 FedRAMP 規範標準。</span><span class="sxs-lookup"><span data-stu-id="9b448-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="9b448-109">因此，我們會在從1.1 年1月15日開始2020，取代環境 DoD 中的 Office 365 中，TLS 和1.0。</span><span class="sxs-lookup"><span data-stu-id="9b448-109">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="9b448-110">如需如何移除 TLS 1.1 和1.0 相依性的相關資訊，請參閱下列白皮書：</span><span class="sxs-lookup"><span data-stu-id="9b448-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="9b448-111">解決 TLS 1.0 問題</span><span class="sxs-lookup"><span data-stu-id="9b448-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="9b448-112">在準備 TLS 1.1 和1.0 的此變更時，建議您改用 TLS 版本1.2。</span><span class="sxs-lookup"><span data-stu-id="9b448-112">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="9b448-113">如需詳細資訊，請參閱[在 Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="9b448-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="9b448-114">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="9b448-114">More information</span></span>

<span data-ttu-id="9b448-115">從2020年1月15日開始，在 GCC 高端和 DoD 環境中的 Office 365 會取代 TLS 1.1 及1.0。</span><span class="sxs-lookup"><span data-stu-id="9b448-115">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="9b448-116">在2020年1月15日，所有用戶端伺服器與瀏覽器伺服器的組合都應該使用 TLS 版本1.2 （或更新版本），以確保所有連線都不會有任何問題給 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="9b448-116">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="9b448-117">這可能需要更新用戶端伺服器與瀏覽器伺服器的某些組合。</span><span class="sxs-lookup"><span data-stu-id="9b448-117">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="9b448-118">如果您未更新至 TLS 版本1.2 （或更新版本）于1月 15 2020 日，當您嘗試連線到 Office 365 時，您會遇到問題。</span><span class="sxs-lookup"><span data-stu-id="9b448-118">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="9b448-119">此外，您還必須更新至 TLS 1.2 （或更新版本），以作為解決方法的一部分。</span><span class="sxs-lookup"><span data-stu-id="9b448-119">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="9b448-120">我們知道下列用戶端無法使用 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="9b448-120">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="9b448-121">Android 4.3 和舊版</span><span class="sxs-lookup"><span data-stu-id="9b448-121">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="9b448-122">Firefox 5.0 和舊版</span><span class="sxs-lookup"><span data-stu-id="9b448-122">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="9b448-123">Internet Explorer 8 – 10 on Windows 7 及更早版本</span><span class="sxs-lookup"><span data-stu-id="9b448-123">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="9b448-124">Windows Phone 8.0 上的 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="9b448-124">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="9b448-125">Safari 6.0.4/OS X 10.8.4 及更早版本</span><span class="sxs-lookup"><span data-stu-id="9b448-125">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="9b448-126">建議您更新用戶端，以確保您維護 Office 365 GCC 高和 DoD 的不間斷存取。</span><span class="sxs-lookup"><span data-stu-id="9b448-126">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="9b448-127">[！附注] 目前對 Microsoft Online services 連線的分析顯示，大部分的服務和端點請參閱極少的 TLS 1.1 和1.0 使用量，我們會提供這項變更的通知，讓您在支援 TLS 1.1 和1.0 結束之前，依照需要更新任何受影響的用戶端或伺服器。</span><span class="sxs-lookup"><span data-stu-id="9b448-127">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="9b448-128">如果您正在使用任何內部部署基礎結構的混合式案例或 Active Directory Federation Services （AD FS），請確定基礎結構可以支援使用 TLS 1.2 （或更新版本）的輸入和輸出連線。</span><span class="sxs-lookup"><span data-stu-id="9b448-128">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="9b448-129">除了當您使用無法使用 TLS 1.2 的列出用戶端時，您可能會遇到的停機情形，移除 TLS 1.1 及1.0 將會使您無法使用下列 Microsoft 產品：</span><span class="sxs-lookup"><span data-stu-id="9b448-129">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="9b448-130">Lync phone</span><span class="sxs-lookup"><span data-stu-id="9b448-130">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="9b448-131">參考</span><span class="sxs-lookup"><span data-stu-id="9b448-131">References</span></span>

<span data-ttu-id="9b448-132">下列支援文章說明的指導方針與參考，可協助確保用戶端使用 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="9b448-132">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="9b448-133">在 Office 365 中準備 TLS 1.2 的強制使用</span><span class="sxs-lookup"><span data-stu-id="9b448-133">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
