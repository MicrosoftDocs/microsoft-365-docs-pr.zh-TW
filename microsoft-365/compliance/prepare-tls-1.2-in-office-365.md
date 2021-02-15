---
title: 在 Office 365 和 Office 365 GCC 中準備 TLS 1.2
description: 停用 TLS 1.0 和 1.1 支援後，如何準備好以便 Office 365 與 Office 365 GCC 中的所有用戶端-伺服器及瀏覽端伺服器組合可以使用 TLS 1.2。
author: kccross
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
- Office 365 Business
ms.openlocfilehash: 8078f5de698adf437e843a423fe9e82c5e4dd8de
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233117"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a><span data-ttu-id="2a4c0-103">在 Office 365 和 Office 365 GCC 中準備 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="2a4c0-103">Preparing for TLS 1.2 in Office 365 and Office 365 GCC</span></span>

## <a name="summary"></a><span data-ttu-id="2a4c0-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2a4c0-104">Summary</span></span>

<span data-ttu-id="2a4c0-105">為了向客戶提供最佳的加密層級，Microsoft 規劃淘汰 Office 365 與 Office 365 GCC 中的傳輸層安全性 (TLS) 1.0 和 1.1 版。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-105">To provide the best-in-class encryption to our customers, Microsoft plans to deprecate Transport Layer Security (TLS) versions 1.0 and 1.1 in Office 365 and Office 365 GCC.</span></span> <span data-ttu-id="2a4c0-106">我們明白資料的安全性很重要，也承諾透明公開可能會影響 TLS 服務使用的變更。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-106">We understand that the security of your data is important, and we're committed to transparency about changes that may affect your use of the TLS service.</span></span>

<span data-ttu-id="2a4c0-107">[Microsoft TLS 1.0 實作](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n)沒有已知的安全性弱點。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-107">The [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) has no known security vulnerabilities.</span></span> <span data-ttu-id="2a4c0-108">但由於未來可能發生通訊協定降級攻擊和其他 TLS 弱點，我們即將終止支援 Microsoft Office 365 與 Office 365 GCC 中的 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-108">But because of the potential for future protocol downgrade attacks and other TLS vulnerabilities, we are discontinuing support for TLS 1.0 and 1.1 in Microsoft Office 365 and Office 365 GCC.</span></span>

<span data-ttu-id="2a4c0-109">如需如何刪除 TLS 1.0 和 1.1 相依性的詳細資訊，請參閱下列白皮書：[解決 TLS 1.0 問題](https://www.microsoft.com/download/details.aspx?id=55266)。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-109">For information about how to remove TLS 1.0 and 1.1 dependencies, see the following white paper: [Solving the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266).</span></span>

## <a name="more-information"></a><span data-ttu-id="2a4c0-110">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="2a4c0-110">More information</span></span>

<span data-ttu-id="2a4c0-111">自 2020 年 1 月起，我們已經開始淘汰 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-111">We have already begun deprecation of TLS 1.0 and 1.1 as of January 2020.</span></span> <span data-ttu-id="2a4c0-112">不支援透過 DoD 或 GCC High 執行個體中的 TLS 1.0 或 1.1 連線至 Office 365 的任何用戶端、裝置或服務。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-112">Any clients, devices, or services that connect to Office 365 through TLS 1.0 or 1.1 in our DoD or GCC High instances are unsupported.</span></span> <span data-ttu-id="2a4c0-113">對於我們商務用 Office 365 的客戶而言，TLS 1.0 和1.1 的過時會從10月15日開始，2020和推廣會在下列星期和月份繼續進行。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-113">For our commercial customers of Office 365, deprecation of TLS 1.0 and 1.1 will begin October 15, 2020 and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="2a4c0-114">為維持 Office 365 服務連線，我們推薦所有用戶端-伺服器及瀏覽器伺服器組合都使用 TLS 1.2（或更新版本）。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-114">We recommend that all client-server and browser-server combinations use TLS 1.2 (or a later version) in order to maintain connection to Office 365 services.</span></span> <span data-ttu-id="2a4c0-115">您可能必須更新特定的用戶端-伺服器及瀏覽器伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-115">You might have to update certain client-server and browser-server combinations.</span></span>

<span data-ttu-id="2a4c0-116">您必須更新透過 TLS 1.0 或 TLS 1.1 呼叫 Microsoft 365 APIs 的應用程式，才能使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-116">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="2a4c0-117">.NET 4.5 的預設值為 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-117">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="2a4c0-118">若要更新您的 .NET 設定，請參閱 [如何在用戶端上啟用傳輸層安全性 (TLS) 1.2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-118">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="2a4c0-119">已知下列用戶端不能使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-119">The following clients are known to be unable to use TLS 1.2.</span></span> <span data-ttu-id="2a4c0-120">請更新用戶端以確保順利存取服務。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-120">Update these clients to ensure uninterrupted access to the service.</span></span>

- <span data-ttu-id="2a4c0-121">Android 4.3 和舊版</span><span class="sxs-lookup"><span data-stu-id="2a4c0-121">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="2a4c0-122">Firefox 5.0 和舊版</span><span class="sxs-lookup"><span data-stu-id="2a4c0-122">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="2a4c0-123">Windows  7 及舊版中的 Internet Explorer 8-10</span><span class="sxs-lookup"><span data-stu-id="2a4c0-123">Internet Explorer 8-10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="2a4c0-124">Win Phone 8 中的 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="2a4c0-124">Internet Explorer 10 on Windows Phone 8</span></span>
- <span data-ttu-id="2a4c0-125">Safari 6.0.4/OS X10.8.4 和舊版</span><span class="sxs-lookup"><span data-stu-id="2a4c0-125">Safari 6.0.4/OS X10.8.4 and earlier versions</span></span>

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a><span data-ttu-id="2a4c0-126">適用於 Microsoft Teams 會議室和 Surface Hub 的 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="2a4c0-126">TLS 1.2 for Microsoft Teams Rooms and Surface Hub</span></span>

<span data-ttu-id="2a4c0-127">自 2018 年 12 月開始，Microsoft Teams 會議室 (先前稱為 Skype Room System V2 SRS V2) 已經支援 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-127">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) have supported TLS 1.2 since December 2018.</span></span> <span data-ttu-id="2a4c0-128">建議您在會議室裝置安裝 Microsoft Teams 會議室應用程式 4.0.64.0 版或更新版本。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-128">We recommend that Rooms devices have Microsoft Teams Rooms app version 4.0.64.0 or later installed.</span></span> <span data-ttu-id="2a4c0-129">如需詳細資訊，請參閱[版本資訊](https://docs.microsoft.com/microsoftteams/room-systems/srs2-release-note)。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-129">For more information, see the [Release notes](https://docs.microsoft.com/microsoftteams/room-systems/srs2-release-note).</span></span> <span data-ttu-id="2a4c0-130">變更可與舊版和新版相容。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-130">The changes are backward and forward compatible.</span></span>

<span data-ttu-id="2a4c0-131">2019 年 5 月發行的 Surface Hub 支援 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-131">Surface Hub released TLS 1.2 support in May 2019.</span></span>

<span data-ttu-id="2a4c0-132">Microsoft Teams 會議室和 Surface Hub 產品還需要在伺服器端程式碼進行下列變更，才支援 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="2a4c0-132">TLS 1.2 support for Microsoft Teams Rooms and Surface Hub products also requires the following server-side code changes:</span></span>

- <span data-ttu-id="2a4c0-133">商務用 Skype Online 伺服器變更已於 2019 年 4 月上線。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-133">Skype for Business Online server changes were made live in April 2019.</span></span> <span data-ttu-id="2a4c0-134">現在，商務用 Skype Online 支援使用 TLS 1.2 來與 Microsoft Teams 會議室和 Surface Hub 裝置連線。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-134">Now, Skype for Business Online supports connecting Microsoft Teams Rooms and Surface Hub devices by using TLS 1.2.</span></span>
- <span data-ttu-id="2a4c0-135">商務用 Skype Server 客戶必須安裝累積更新 (CU)，才能將 TLS 1.2 用於 Teams 會議室系統和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-135">Skype for Business Server customers must install a cumulative update (CU) to use TLS 1.2 for Teams Rooms Systems and Surface Hub.</span></span>

  - <span data-ttu-id="2a4c0-136">若為商務用 Skype Server 2015，CU9 已於 2019 年 5 月發行。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-136">For Skype for Business Server 2015, CU9 is already released in May 2019.</span></span>
  - <span data-ttu-id="2a4c0-137">若為商務用 Skype Server 2019，CU1 先前規劃在 2019 年 4 月發行，但已延遲到 2019 年 6 月。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-137">For Skype for Business Server 2019, CU1 was previously planned for April 2019 but is delayed to June 2019.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2a4c0-138">商務用 Skype 內部部署客戶在為商務用 Skype Server 安裝特定 CU 之前，不應停用 TLS 1.0/1.1。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-138">Skype for Business on-premises customers should not disable TLS 1.0/1.1 before installing specific CUs for Skype for Business Server.</span></span>

<span data-ttu-id="2a4c0-139">如果您要在混合情節或動態通訊錄聯合服務 (Active Directory Federation Services) 中使用內部基礎結構，請確定該裝置可以同時支援使用 TLS 1.2 的輸入和輸出連線。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-139">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services, make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2.</span></span>

## <a name="references"></a><span data-ttu-id="2a4c0-140">參考</span><span class="sxs-lookup"><span data-stu-id="2a4c0-140">References</span></span>

<span data-ttu-id="2a4c0-141">下列資源提供指引，協助您確定用戶端使用 TLS 1.2 或更新版本及停用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-141">The following resources provide guidance to help make sure that your clients are using TLS 1.2 or a later version and to disable TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="2a4c0-142">對於連線到 Office 365 的 Windows 7 用戶端，請確認 TLS 1.2 是 Windows 中 WinHTTP 的預設安全通訊協定。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-142">For Windows 7 clients that connect to Office 365, make sure that TLS 1.2 is the default secure protocol in WinHTTP in Windows.</span></span> <span data-ttu-id="2a4c0-143">如需詳細資訊，請參閱 [KB 3140245 - 更新為 Windows 中的預設安全通訊協定，以啟用 TLS 1.1 和 TLS 1.2 作為預設安全通訊協定](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-143">For more information see [KB 3140245 - Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).</span></span>
- <span data-ttu-id="2a4c0-144">若要自移除 TLS 1.0 和 1.1 相依性開始改善 TLS 的使用率，請參閱 [Microsoft 的 TLS](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/) 1.2 支援。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-144">To start addressing weak TLS use by removing TLS 1.0 and 1.1 dependencies, see [TLS 1.2 support at Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).</span></span>
- <span data-ttu-id="2a4c0-145">[新的 IIS 功能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) 可讓您更容易使用薄弱安全性通訊協定，在 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 和 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) 上找到連線至服務的用戶端。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-145">[New IIS functionality](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) makes it easier to find clients on [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) and [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) that connect to the service by using weak security protocols.</span></span>
- <span data-ttu-id="2a4c0-146">取得如何 [解決 TLS 1.0 問題的](https://www.microsoft.com/download/details.aspx?id=55266)詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-146">Get more information about how to [solve the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266).</span></span>
- <span data-ttu-id="2a4c0-147">如需關於安全性的一般資訊，請前往 [Office 365信任中心](https://www.microsoft.com/trustcenter/cloudservices/office365)。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-147">For general information about our approach to security, go to the [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365).</span></span>
- [<span data-ttu-id="2a4c0-148">準備 TLS 1.0/1.1 淘汰 – O365 商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="2a4c0-148">Preparing for TLS 1.0/1.1 Deprecation - Office 365 Skype for Business</span></span>](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [<span data-ttu-id="2a4c0-149">Exchange Server TLS 指南，第 1 部分：為 TLS 1.2 做好準備</span><span class="sxs-lookup"><span data-stu-id="2a4c0-149">Exchange Server TLS guidance, part 1: Getting Ready for TLS 1.2</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [<span data-ttu-id="2a4c0-150">Exchange Server TLS 指南，第 2 部分：正在啟用 TLS 1.2 並辨識不使用 TLS 1.2 的用戶端</span><span class="sxs-lookup"><span data-stu-id="2a4c0-150">Exchange Server TLS guidance Part 2: Enabling TLS 1.2 and Identifying Clients Not Using It</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [<span data-ttu-id="2a4c0-151">Exchange Server TLS 指南，第 3 部分：關閉 TLS 1.0/1.1</span><span class="sxs-lookup"><span data-stu-id="2a4c0-151">Exchange Server TLS guidance Part 3: Turning Off TLS 1.0/1.1</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [<span data-ttu-id="2a4c0-152">啟用 Office Online Server 中的 TLS 1.1 和 TLS 1.2 支援</span><span class="sxs-lookup"><span data-stu-id="2a4c0-152">Enable TLS 1.1 and TLS 1.2 support in Office Online Server</span></span>](https://docs.microsoft.com/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
