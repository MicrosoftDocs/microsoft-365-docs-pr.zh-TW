---
title: 適用於 Office 365 的 TLS 1.0 和 1.1 淘汰
description: 說明 Office 365 的 TLS 1.0 和1.1 棄用。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777053"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="82a4f-103">適用於 Office 365 的 TLS 1.0 和 1.1 淘汰</span><span class="sxs-lookup"><span data-stu-id="82a4f-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="82a4f-104">由於 COVID-19，我們暫時停用了 TLS 1.0 和1.1 對用戶端客戶的取代取代，但隨著供貨鏈的調整和某些國家/地區的開啟，我們會將 TLS 強制重設為從10年10月 15 2020 日開始，並在下列星期和各個月繼續進行。</span><span class="sxs-lookup"><span data-stu-id="82a4f-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to COVID-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to begin October 15, 2020, and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="82a4f-105">從2018年10月31日到，Office 365 服務的傳輸層安全性 (TLS) 1.0 和1.1 通訊協定已被取代。</span><span class="sxs-lookup"><span data-stu-id="82a4f-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="82a4f-106">對使用者的影響預計會降至最低。</span><span class="sxs-lookup"><span data-stu-id="82a4f-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="82a4f-107">這項變更已于兩年內公佈，第一次公開宣告于12月2017。</span><span class="sxs-lookup"><span data-stu-id="82a4f-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="82a4f-108">本文僅適用于與 Office 365 服務相關的 Office 365 本地用戶端，但是也可以套用至 Office 和 Office Online Server/Office Web Apps 的內部部署 TLS 問題。</span><span class="sxs-lookup"><span data-stu-id="82a4f-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="82a4f-109">Office 和 TLS 概述</span><span class="sxs-lookup"><span data-stu-id="82a4f-109">Office and TLS overview</span></span>

<span data-ttu-id="82a4f-110">Office 用戶端依賴 Windows web 服務 (WINHTTP) 以透過 TLS 通訊協定傳送及接收流量。</span><span class="sxs-lookup"><span data-stu-id="82a4f-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="82a4f-111">如果本機電腦的 web 服務可以使用 TLS 1.2，則 Office 用戶端可以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="82a4f-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="82a4f-112">所有 Office 用戶端都可以使用 TLS 通訊協定，因為 TLS 和 SSL 通訊協定都是作業系統的一部分，而不是 Office 用戶端特有的。</span><span class="sxs-lookup"><span data-stu-id="82a4f-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="82a4f-113">在 Windows 8 和更新版本上</span><span class="sxs-lookup"><span data-stu-id="82a4f-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="82a4f-114">根據預設，如果沒有網路裝置設定為拒絕 TLS 1.2 流量，則可以使用 TLS 1.2 和1.1 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="82a4f-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="82a4f-115">在 Windows 7</span><span class="sxs-lookup"><span data-stu-id="82a4f-115">On Windows 7</span></span>

<span data-ttu-id="82a4f-116">沒有 [KB 3140245](https://support.microsoft.com/help/3140245) 更新，TLS 1.1 和1.2 通訊協定無法使用。</span><span class="sxs-lookup"><span data-stu-id="82a4f-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="82a4f-117">此更新會解決此問題，並新增下列登錄子機碼：</span><span class="sxs-lookup"><span data-stu-id="82a4f-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="82a4f-118">未安裝此更新的 Windows 7 使用者會受到2018年10月31日的影響。</span><span class="sxs-lookup"><span data-stu-id="82a4f-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="82a4f-119">[KB 3140245](https://support.microsoft.com/help/3140245) 具有如何變更 WINHTTP 設定以啟用 TLS 通訊協定的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="82a4f-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="82a4f-120">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="82a4f-120">More information</span></span>

<span data-ttu-id="82a4f-121">知識庫文章描述的 **DefaultSecureProtocols** 登錄機碼值，會決定可以使用的網路通訊協定：</span><span class="sxs-lookup"><span data-stu-id="82a4f-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="82a4f-122">DefaultSecureProtocols 值</span><span class="sxs-lookup"><span data-stu-id="82a4f-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="82a4f-123">已啟用通訊協定</span><span class="sxs-lookup"><span data-stu-id="82a4f-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="82a4f-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="82a4f-124">0x00000008</span></span>|<span data-ttu-id="82a4f-125">預設啟用 SSL 2.0</span><span class="sxs-lookup"><span data-stu-id="82a4f-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="82a4f-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="82a4f-126">0x00000020</span></span>|<span data-ttu-id="82a4f-127">預設啟用 SSL 3.0</span><span class="sxs-lookup"><span data-stu-id="82a4f-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="82a4f-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="82a4f-128">0x00000080</span></span>|<span data-ttu-id="82a4f-129">預設啟用 TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="82a4f-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="82a4f-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="82a4f-130">0x00000200</span></span>|<span data-ttu-id="82a4f-131">預設啟用 TLS 1.1</span><span class="sxs-lookup"><span data-stu-id="82a4f-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="82a4f-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="82a4f-132">0x00000800</span></span>|<span data-ttu-id="82a4f-133">預設啟用 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="82a4f-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="82a4f-134">Office 用戶端和 TLS 登錄機碼</span><span class="sxs-lookup"><span data-stu-id="82a4f-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="82a4f-135">您可以參考 [KB 4057306，準備在 Office 365 中對 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306)。</span><span class="sxs-lookup"><span data-stu-id="82a4f-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="82a4f-136">這是 IT 系統管理員的一般文章，也是有關 TLS 1.2 變更的官方檔。</span><span class="sxs-lookup"><span data-stu-id="82a4f-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="82a4f-137">下表顯示在 2018 10 月31日後，Office 365 用戶端中的適當登錄機碼值。</span><span class="sxs-lookup"><span data-stu-id="82a4f-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="82a4f-138">在2018年10月31日之後啟用 Office 365 服務的通訊協定</span><span class="sxs-lookup"><span data-stu-id="82a4f-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="82a4f-139">十六進位值</span><span class="sxs-lookup"><span data-stu-id="82a4f-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="82a4f-140">TLS 1.0 + 1.1 + 1。2</span><span class="sxs-lookup"><span data-stu-id="82a4f-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="82a4f-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="82a4f-141">0x00000A80</span></span>|
|<span data-ttu-id="82a4f-142">TLS 1.1 + 1。2</span><span class="sxs-lookup"><span data-stu-id="82a4f-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="82a4f-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="82a4f-143">0x00000A00</span></span>|
|<span data-ttu-id="82a4f-144">TLS 1.0 + 1。2</span><span class="sxs-lookup"><span data-stu-id="82a4f-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="82a4f-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="82a4f-145">0x00000880</span></span>|
|<span data-ttu-id="82a4f-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="82a4f-146">TLS 1.2</span></span>|<span data-ttu-id="82a4f-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="82a4f-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="82a4f-148">建議您不要使用 SSL 2.0 和3.0 通訊協定，也可以使用 **DefaultSecureProtocols** 機碼加以設定。</span><span class="sxs-lookup"><span data-stu-id="82a4f-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="82a4f-149">SSL 2.0 和3.0 被視為已被取代的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="82a4f-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="82a4f-150">最佳作法是使用 SSL 2.0 和 SSL 3.0，但決定這項決策最後取決於最符合您產品需求的決策。</span><span class="sxs-lookup"><span data-stu-id="82a4f-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="82a4f-151">如需有關 SSL 3.0 弱點的詳細資訊，請參閱 [KB 3009008](https://support.microsoft.com/help/3009008)。</span><span class="sxs-lookup"><span data-stu-id="82a4f-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="82a4f-152">您可以使用 [程式師模式] 中的預設 Windows 計算機設定相同的參照登錄機碼值。</span><span class="sxs-lookup"><span data-stu-id="82a4f-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="82a4f-153">如需詳細資訊，請參閱 [KB 3140245 更新，以啟用 tls 1.1 和 tls 1.2 做為 Windows WinHTTP 中的預設安全通訊協定](https://support.microsoft.com/help/3140245)。</span><span class="sxs-lookup"><span data-stu-id="82a4f-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="82a4f-154">不論 Windows 7 更新 ([KB 3140245](https://support.microsoft.com/help/3140245)) 是否已安裝，DefaultSecureProtocols 登錄子機碼都不存在，必須手動新增，或透過群組原則物件 (GPO) 。</span><span class="sxs-lookup"><span data-stu-id="82a4f-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="82a4f-155">也就是說，除非您必須自訂已啟用或限制的安全通訊協定，否則不需要此機碼。</span><span class="sxs-lookup"><span data-stu-id="82a4f-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="82a4f-156">您只需要 Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) 更新。</span><span class="sxs-lookup"><span data-stu-id="82a4f-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
