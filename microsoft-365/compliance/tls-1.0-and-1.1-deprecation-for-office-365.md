---
title: 停用 Microsoft 365 的 TLS 1.0 和1。1
description: 說明 Microsoft 365 的 TLS 1.0 和1.1 的過時和停用。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332675"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="cf326-103">停用 Microsoft 365 的 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="cf326-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf326-104">由於 COVID-19，我們暫時停止停用的 TLS 1.0 和1.1，以供商務客戶用。</span><span class="sxs-lookup"><span data-stu-id="cf326-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="cf326-105">隨著供貨鏈的調整和某些國家的開啟，我們會在10月15日（2020）重新開機 TLS 1.2 強制推出。</span><span class="sxs-lookup"><span data-stu-id="cf326-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="cf326-106">在下列星期數和數月內，首展會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="cf326-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="cf326-107">從2018年10月31日到，Microsoft 365 服務已棄用 (TLS) 1.0 和1.1 通訊協定的傳輸層安全性。</span><span class="sxs-lookup"><span data-stu-id="cf326-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="cf326-108">對使用者的影響很小。</span><span class="sxs-lookup"><span data-stu-id="cf326-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="cf326-109">這項變更已于兩年內公佈，第一次公開宣告于12月2017。</span><span class="sxs-lookup"><span data-stu-id="cf326-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="cf326-110">本文僅適用于與 Office 365 服務相關的 Office 365 本機用戶端，但是也可以套用至 Office 和 Office Online Server/Office Web 應用程式的內部部署 TLS 問題。</span><span class="sxs-lookup"><span data-stu-id="cf326-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="cf326-111">針對 SharePoint 和 OneDrive，您必須更新及設定 .net 以支援 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="cf326-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="cf326-112">如需詳細資訊，請參閱 [如何在用戶端上啟用 TLS 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。</span><span class="sxs-lookup"><span data-stu-id="cf326-112">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="cf326-113">Office 365 和 TLS 概述</span><span class="sxs-lookup"><span data-stu-id="cf326-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="cf326-114">Office 用戶端依靠 Windows web 服務 (WINHTTP) 以透過 TLS 通訊協定傳送及接收流量。</span><span class="sxs-lookup"><span data-stu-id="cf326-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="cf326-115">如果本機電腦的 web 服務可以使用 tls 1.2，則 Office 用戶端可以使用 tls 1.2。</span><span class="sxs-lookup"><span data-stu-id="cf326-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="cf326-116">所有 Office 用戶端都可以使用 tls 通訊協定，因為 tls 和 SSL 通訊協定都是作業系統的一部分，而不是 Office 用戶端特有的。</span><span class="sxs-lookup"><span data-stu-id="cf326-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="cf326-117">在 Windows 8 和更新版本上</span><span class="sxs-lookup"><span data-stu-id="cf326-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="cf326-118">根據預設，如果沒有網路裝置設定為拒絕 TLS 1.2 流量，則可以使用 TLS 1.2 和1.1 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="cf326-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="cf326-119">在 Windows 7</span><span class="sxs-lookup"><span data-stu-id="cf326-119">On Windows 7</span></span>

<span data-ttu-id="cf326-120">沒有 [KB 3140245](https://support.microsoft.com/help/3140245) 更新，TLS 1.1 和1.2 通訊協定無法使用。</span><span class="sxs-lookup"><span data-stu-id="cf326-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="cf326-121">此更新會解決此問題，並新增下列登錄子機碼：</span><span class="sxs-lookup"><span data-stu-id="cf326-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="cf326-122">Windows 7 不具備此更新的使用者會受到2018年10月31日的影響。</span><span class="sxs-lookup"><span data-stu-id="cf326-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="cf326-123">[KB 3140245](https://support.microsoft.com/help/3140245) 具有如何變更 WINHTTP 設定以啟用 TLS 通訊協定的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cf326-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="cf326-124">其他資訊</span><span class="sxs-lookup"><span data-stu-id="cf326-124">More information</span></span>

<span data-ttu-id="cf326-125">知識庫文章描述的 **DefaultSecureProtocols** 登錄機碼值，會決定可以使用的網路通訊協定：</span><span class="sxs-lookup"><span data-stu-id="cf326-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="cf326-126">DefaultSecureProtocols 值</span><span class="sxs-lookup"><span data-stu-id="cf326-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="cf326-127">已啟用通訊協定</span><span class="sxs-lookup"><span data-stu-id="cf326-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="cf326-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="cf326-128">0x00000008</span></span>|<span data-ttu-id="cf326-129">預設啟用 SSL 2.0</span><span class="sxs-lookup"><span data-stu-id="cf326-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="cf326-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="cf326-130">0x00000020</span></span>|<span data-ttu-id="cf326-131">預設啟用 SSL 3.0</span><span class="sxs-lookup"><span data-stu-id="cf326-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="cf326-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="cf326-132">0x00000080</span></span>|<span data-ttu-id="cf326-133">預設啟用 TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="cf326-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="cf326-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="cf326-134">0x00000200</span></span>|<span data-ttu-id="cf326-135">預設啟用 TLS 1.1</span><span class="sxs-lookup"><span data-stu-id="cf326-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="cf326-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="cf326-136">0x00000800</span></span>|<span data-ttu-id="cf326-137">預設啟用 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="cf326-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="cf326-138">Office 用戶端和 TLS 登錄機碼</span><span class="sxs-lookup"><span data-stu-id="cf326-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="cf326-139">您可以參考[KB 4057306，準備在 Office 365 中強制使用 TLS 1.2](https://support.microsoft.com/help/4057306)。</span><span class="sxs-lookup"><span data-stu-id="cf326-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="cf326-140">這是 IT 系統管理員的一般文章，也是有關 TLS 1.2 變更的官方檔。</span><span class="sxs-lookup"><span data-stu-id="cf326-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="cf326-141">下表顯示2018年10月31日在 Office 365 用戶端的適當登錄機碼值。</span><span class="sxs-lookup"><span data-stu-id="cf326-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="cf326-142">在2018年10月31日之後，為 Office 365 服務啟用通訊協定</span><span class="sxs-lookup"><span data-stu-id="cf326-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="cf326-143">十六進位值</span><span class="sxs-lookup"><span data-stu-id="cf326-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="cf326-144">TLS 1.0 + 1.1 + 1。2</span><span class="sxs-lookup"><span data-stu-id="cf326-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="cf326-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="cf326-145">0x00000A80</span></span>|
|<span data-ttu-id="cf326-146">TLS 1.1 + 1。2</span><span class="sxs-lookup"><span data-stu-id="cf326-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="cf326-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="cf326-147">0x00000A00</span></span>|
|<span data-ttu-id="cf326-148">TLS 1.0 + 1。2</span><span class="sxs-lookup"><span data-stu-id="cf326-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="cf326-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="cf326-149">0x00000880</span></span>|
|<span data-ttu-id="cf326-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="cf326-150">TLS 1.2</span></span>|<span data-ttu-id="cf326-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="cf326-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="cf326-152">請勿使用 SSL 2.0 和3.0 通訊協定，也可以使用 **DefaultSecureProtocols** 機碼加以設定。</span><span class="sxs-lookup"><span data-stu-id="cf326-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="cf326-153">SSL 2.0 和3.0 被視為過時和不安全的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="cf326-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="cf326-154">最佳作法是使用 SSL 2.0 和 SSL 3.0，但決定這項決策最後取決於最符合您產品需求的決策。</span><span class="sxs-lookup"><span data-stu-id="cf326-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="cf326-155">如需有關 SSL 3.0 弱點的詳細資訊，請參閱 [KB 3009008](https://support.microsoft.com/help/3009008)。</span><span class="sxs-lookup"><span data-stu-id="cf326-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="cf326-156">您可以使用 [程式師模式] 中的預設 Windows 計算機設定相同的參照登錄機碼值。</span><span class="sxs-lookup"><span data-stu-id="cf326-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="cf326-157">如需詳細資訊，請參閱[KB 3140245 更新，以啟用 tls 1.1 和 tls 1.2 為 Windows 中 WinHTTP 的預設安全通訊協定](https://support.microsoft.com/help/3140245)。</span><span class="sxs-lookup"><span data-stu-id="cf326-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="cf326-158">不論是否已安裝 Windows 7 更新 ([KB 3140245](https://support.microsoft.com/help/3140245)) ，DefaultSecureProtocols 登錄子機碼不存在，必須手動新增，或透過「群組原則」物件 (GPO) 。</span><span class="sxs-lookup"><span data-stu-id="cf326-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="cf326-159">也就是說，除非您必須自訂已啟用或限制的安全通訊協定，否則不需要此機碼。</span><span class="sxs-lookup"><span data-stu-id="cf326-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="cf326-160">您只需要 Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) 更新。</span><span class="sxs-lookup"><span data-stu-id="cf326-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="cf326-161">更新及設定 .NET Framework 以支援 TLS 1。2</span><span class="sxs-lookup"><span data-stu-id="cf326-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="cf326-162">您必須更新 Microsoft 365 APIs over tls 1.0 或 TLS 1.1 的應用程式，才能使用 tls 1.2。</span><span class="sxs-lookup"><span data-stu-id="cf326-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="cf326-163">.NET 4.5 的預設值為 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="cf326-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="cf326-164">若要更新您的 .NET 設定，請參閱 [如何在用戶端上啟用傳輸層安全性 (TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。</span><span class="sxs-lookup"><span data-stu-id="cf326-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="cf326-165">其他資訊</span><span class="sxs-lookup"><span data-stu-id="cf326-165">More information</span></span>

<span data-ttu-id="cf326-166">如需詳細資訊，請參閱[在 Office 365 中準備 TLS 1.2 的強制用法](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="cf326-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="references"></a><span data-ttu-id="cf326-167">參考</span><span class="sxs-lookup"><span data-stu-id="cf326-167">References</span></span>

<span data-ttu-id="cf326-168">下列資源提供的指導可協助確保用戶端使用 TLS 1.2 或更新版本，以及停用 TLS 1.0 和1.1：</span><span class="sxs-lookup"><span data-stu-id="cf326-168">The following resources provide guidance to help make sure that your clients are using TLS 1.2 or a later version and to disable TLS 1.0 and 1.1:</span></span>

- <span data-ttu-id="cf326-169">對於連線到 Office 365 的 Windows 7 用戶端，請確認 TLS 1.2 是 Windows 中 WinHTTP 的預設安全通訊協定。</span><span class="sxs-lookup"><span data-stu-id="cf326-169">For Windows 7 clients that connect to Office 365, make sure that TLS 1.2 is the default secure protocol in WinHTTP in Windows.</span></span> <span data-ttu-id="cf326-170">如需詳細資訊，請參閱[KB 3140245-Update 以啟用 tls 1.1 和 tls 1.2 做為 WinHTTP 中 Windows 的預設安全通訊協定](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)。</span><span class="sxs-lookup"><span data-stu-id="cf326-170">For more information, see [KB 3140245 - Update to enable TLS 1.1 and TLS 1.2 as default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).</span></span>
- <span data-ttu-id="cf326-171">若要透過移除 TLS 1.0 和1.1 相依性來處理弱 TLS 使用狀況，請參閱 [Microsoft 的 tls 1.2 支援](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)。</span><span class="sxs-lookup"><span data-stu-id="cf326-171">To address weak TLS usage by removing TLS 1.0 and 1.1 dependencies, see [TLS 1.2 support at Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).</span></span>
- <span data-ttu-id="cf326-172">[新的 IIS 功能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) 可讓您更容易使用薄弱安全性通訊協定，在 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 和 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) 上找到連線至服務的用戶端。</span><span class="sxs-lookup"><span data-stu-id="cf326-172">[New IIS functionality](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) makes it easier to find clients on [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) and [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) that connect to the service by using weak security protocols.</span></span>
- <span data-ttu-id="cf326-173">取得如何 [解決 TLS 1.0 問題的](https://www.microsoft.com/download/details.aspx?id=55266)詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cf326-173">Get more information about how to [solve the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266).</span></span>
- <span data-ttu-id="cf326-174">如需關於安全性的一般資訊，請前往 [Office 365信任中心](https://www.microsoft.com/trustcenter/cloudservices/office365)。</span><span class="sxs-lookup"><span data-stu-id="cf326-174">For general information about our approach to security, go to the [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365).</span></span>
- [<span data-ttu-id="cf326-175">準備 TLS 1.0/1.1 淘汰 – O365 商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="cf326-175">Preparing for TLS 1.0/1.1 Deprecation - Office 365 Skype for Business</span></span>](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [<span data-ttu-id="cf326-176">Exchange Server TLS 指南，第 1 部分：為 TLS 1.2 做好準備</span><span class="sxs-lookup"><span data-stu-id="cf326-176">Exchange Server TLS guidance, part 1: Getting Ready for TLS 1.2</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [<span data-ttu-id="cf326-177">Exchange Server TLS 指南，第 2 部分：正在啟用 TLS 1.2 並辨識不使用 TLS 1.2 的用戶端</span><span class="sxs-lookup"><span data-stu-id="cf326-177">Exchange Server TLS guidance Part 2: Enabling TLS 1.2 and Identifying Clients Not Using It</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [<span data-ttu-id="cf326-178">Exchange Server TLS 指南，第 3 部分：關閉 TLS 1.0/1.1</span><span class="sxs-lookup"><span data-stu-id="cf326-178">Exchange Server TLS guidance Part 3: Turning Off TLS 1.0/1.1</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [<span data-ttu-id="cf326-179">啟用 Office Online Server 中的 TLS 1.1 和 TLS 1.2 支援</span><span class="sxs-lookup"><span data-stu-id="cf326-179">Enable TLS 1.1 and TLS 1.2 support in Office Online Server</span></span>](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

