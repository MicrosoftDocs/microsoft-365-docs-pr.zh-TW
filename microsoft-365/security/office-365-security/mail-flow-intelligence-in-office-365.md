---
title: Office 365 中的郵件流程情報
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 系統管理員可以了解與 Office 365 （也稱為郵件流程情報） 中使用連接器的郵件傳遞相關聯的錯誤碼。
ms.openlocfilehash: ea4fb56f0e303d243af02edf01e5d85b957a6368
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599050"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="c36c7-103">Office 365 中的郵件流程情報</span><span class="sxs-lookup"><span data-stu-id="c36c7-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="c36c7-104">一般而言，您可以使用連接器 Office 365 組織的電子郵件路由傳送至內部部署電子郵件環境。</span><span class="sxs-lookup"><span data-stu-id="c36c7-104">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment.</span></span> <span data-ttu-id="c36c7-105">您也可以使用連接器來路由郵件從 Office 365 到夥伴組織。</span><span class="sxs-lookup"><span data-stu-id="c36c7-105">You might also use a connector to route messages from Office 365 to a partner organization.</span></span> <span data-ttu-id="c36c7-106">當 Office 365 無法傳送這些郵件透過連接器時，他們正在排入佇列中 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c36c7-106">When Office 365 can't deliver these messages via the connector, they're queued in Office 365.</span></span> <span data-ttu-id="c36c7-107">Office 365 會繼續重試 24 小時的每一封郵件的傳遞。</span><span class="sxs-lookup"><span data-stu-id="c36c7-107">Office 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="c36c7-108">24 小時後，已排入佇列的郵件將會到期，與該郵件便會傳回給原始寄件者未傳遞回報 （也稱為 NDR 或彈跳訊息）。</span><span class="sxs-lookup"><span data-stu-id="c36c7-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="c36c7-109">Office 365 會產生錯誤時所使用的連接器無法傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="c36c7-109">Office 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="c36c7-110">最常見的錯誤，其解決方案本主題所述。</span><span class="sxs-lookup"><span data-stu-id="c36c7-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="c36c7-111">統稱，透過連接器傳送的郵件無法傳遞佇列和通知錯誤稱為_郵件流程智慧_。</span><span class="sxs-lookup"><span data-stu-id="c36c7-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="c36c7-112">錯誤碼： 450 4.4.312 DNS 查詢失敗</span><span class="sxs-lookup"><span data-stu-id="c36c7-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="c36c7-113">一般而言，這個錯誤表示 Office 365 嘗試連線至智慧主機連接器，但若要尋找失敗的智慧主機的 IP 位址的 DNS 查詢中所指定。</span><span class="sxs-lookup"><span data-stu-id="c36c7-113">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="c36c7-114">這項錯誤的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="c36c7-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="c36c7-115">沒有您的網域 DNS 主機服務 （合作對象，用於維護您的網域的授權名稱伺服器） 的問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="c36c7-116">您的網域已最近過期，所以無法擷取的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="c36c7-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="c36c7-117">最近已經變更您網域的 MX 記錄，與 Office 365 DNS 伺服器仍有先前快取的 DNS 資訊為您的網域。</span><span class="sxs-lookup"><span data-stu-id="c36c7-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="c36c7-118">如何修正錯誤碼為 450 4.4.312？</span><span class="sxs-lookup"><span data-stu-id="c36c7-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="c36c7-119">搭配 DNS 裝載服務，以找出並修正您的網域的問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="c36c7-120">如果錯誤是來自夥伴組織 （例如，3rd 廠商雲端服務提供者），請連絡您的合作夥伴，若要修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="c36c7-121">錯誤碼： 450 4.4.315 連線逾時</span><span class="sxs-lookup"><span data-stu-id="c36c7-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="c36c7-122">一般而言，這表示 Office 365 無法連線至目的地的電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="c36c7-122">Typically, this means Office 365 can't connect to the destination email server.</span></span> <span data-ttu-id="c36c7-123">錯誤的詳細資料將說明問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-123">The error details will explain the problem.</span></span> <span data-ttu-id="c36c7-124">例如：</span><span class="sxs-lookup"><span data-stu-id="c36c7-124">For example:</span></span>

- <span data-ttu-id="c36c7-125">您的內部部署電子郵件伺服器已離線。</span><span class="sxs-lookup"><span data-stu-id="c36c7-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="c36c7-126">有讓 Office 365 會嘗試連線至正確的 IP 位址，請在連接器的智慧主機設定中，會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="c36c7-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="c36c7-127">如何修正錯誤碼為 450 4.4.315？</span><span class="sxs-lookup"><span data-stu-id="c36c7-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="c36c7-128">了解哪些案例適用於您，並進行必要的修正。</span><span class="sxs-lookup"><span data-stu-id="c36c7-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="c36c7-129">例如，如果郵件流程運作正常，且尚未變更連接器設定，您需要檢查內部部署電子郵件環境若要查看如果伺服器是向下，或者已有任何變更至您的網路基礎結構 （例如，您已變更網際網路服務提供者，因此您現在有不同的 IP 位址）。</span><span class="sxs-lookup"><span data-stu-id="c36c7-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="c36c7-130">如果錯誤是來自夥伴組織 （例如，3rd 廠商雲端服務提供者），請連絡您的合作夥伴，若要修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="c36c7-131">錯誤碼： 450 4.4.316 拒絕連線</span><span class="sxs-lookup"><span data-stu-id="c36c7-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="c36c7-132">一般而言，這個錯誤表示 Office 365 遇到連接錯誤，當它嘗試連線至目的地電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="c36c7-132">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="c36c7-133">這項錯誤，可能的原因是您的防火牆會封鎖來自 Office 365 IP 位址的連線。</span><span class="sxs-lookup"><span data-stu-id="c36c7-133">A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses.</span></span> <span data-ttu-id="c36c7-134">或者，這項錯誤可能是經過設計如果您已完全移轉您內部部署到 Office 365 電子郵件系統，並關閉您的內部部署電子郵件環境。</span><span class="sxs-lookup"><span data-stu-id="c36c7-134">Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="c36c7-135">如何修正錯誤碼為 450 4.4.316？</span><span class="sxs-lookup"><span data-stu-id="c36c7-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="c36c7-136">如果您在內部部署環境中有信箱，您需要修改您的防火牆設定，以允許 TCP 連接埠 25 上的 Office 365 IP 位址與您的內部部署電子郵件伺服器的連線。</span><span class="sxs-lookup"><span data-stu-id="c36c7-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="c36c7-137">如需 Office 365 IP 位址的清單，請參閱[Office 365 Url 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="c36c7-137">For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="c36c7-138">如果沒有更多的郵件應該傳遞至內部部署環境中，按一下 [**立即修正**警示中讓 Office 365 可立即拒絕無效收件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="c36c7-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="c36c7-139">這將會降低超過貴組織的配額無效收件者，這可能會影響一般郵件傳遞的風險。</span><span class="sxs-lookup"><span data-stu-id="c36c7-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="c36c7-140">或者，您可以使用下列指示以手動修正此問題：</span><span class="sxs-lookup"><span data-stu-id="c36c7-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="c36c7-141">在[Exchange 系統管理中心 (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)中 Office 365，停用或刪除的連接器，從 Office 365 的電子郵件傳遞至內部部署電子郵件環境：</span><span class="sxs-lookup"><span data-stu-id="c36c7-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="c36c7-142">在 EAC 中，移至 [**郵件流程** \> **連接器**。</span><span class="sxs-lookup"><span data-stu-id="c36c7-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="c36c7-143">選取 [**從**值**Office 365**的連接器和**值**貴組織的電子郵件伺服器\*\*\*\*，然後執行下列其中一個下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c36c7-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="c36c7-144">按一下 [**刪除**] 刪除連接器![移除圖示](../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="c36c7-144">Delete the connector by clicking **Delete** ![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="c36c7-145">按一下 [**編輯**停用連接器![編輯圖示](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)和取消核取**加以開啟**。</span><span class="sxs-lookup"><span data-stu-id="c36c7-145">Disable the connector by clicking **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="c36c7-146">變更**授權**從**內部轉送**您內部部署電子郵件環境與相關聯的 Office 365 中公認的網域。</span><span class="sxs-lookup"><span data-stu-id="c36c7-146">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="c36c7-147">如需相關指示，請參閱[管理公認的網域在 Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="c36c7-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="c36c7-148">**附註**： 一般來說，這些變更與之間所採取 30 分鐘一小時後才會生效。</span><span class="sxs-lookup"><span data-stu-id="c36c7-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="c36c7-149">一個小時之後，請確認不會再收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="c36c7-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="c36c7-150">如果錯誤是從夥伴組織 （例如，3rd 廠商雲端服務提供者），您需要連絡您的合作夥伴，若要修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="c36c7-151">錯誤碼： 450 4.4.317 無法連線至遠端伺服器</span><span class="sxs-lookup"><span data-stu-id="c36c7-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="c36c7-152">一般而言，這個錯誤表示 Office 365 連線至目的地電子郵件伺服器，但伺服器回應立即的錯誤，或不符合的連線需求。</span><span class="sxs-lookup"><span data-stu-id="c36c7-152">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="c36c7-153">錯誤的詳細資料將說明問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-153">The error details will explain the problem.</span></span> <span data-ttu-id="c36c7-154">例如：</span><span class="sxs-lookup"><span data-stu-id="c36c7-154">For example:</span></span>

- <span data-ttu-id="c36c7-155">目的地電子郵件伺服器回應 「 服務無法使用 」 錯誤，這表示伺服器不能維護與 Office 365 之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="c36c7-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="c36c7-156">連接器已設定為需要 TLS，但是在目的地電子郵件伺服器不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="c36c7-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="c36c7-157">如何修正錯誤碼為 450 4.4.317？</span><span class="sxs-lookup"><span data-stu-id="c36c7-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="c36c7-158">確認的 TLS 設定您內部部署電子郵件伺服器上，憑證和連接器上的 TLS 設定。</span><span class="sxs-lookup"><span data-stu-id="c36c7-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="c36c7-159">如果錯誤是從夥伴組織 （例如，3rd 廠商雲端服務提供者），您需要連絡您的合作夥伴，若要修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="c36c7-160">錯誤碼： 450 4.4.318 突然已關閉連線</span><span class="sxs-lookup"><span data-stu-id="c36c7-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="c36c7-161">一般而言，這個錯誤表示 Office 365 通訊時發生困難與內部部署電子郵件環境，因此已中斷連線。</span><span class="sxs-lookup"><span data-stu-id="c36c7-161">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="c36c7-162">這項錯誤的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="c36c7-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="c36c7-163">防火牆會使用 SMTP 封包檢查規則，以及這些規則未正確運作。</span><span class="sxs-lookup"><span data-stu-id="c36c7-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="c36c7-164">您的內部部署電子郵件伺服器不正確 （例如服務停止回應、 損毀或系統資源不足），這會導致逾時時間伺服器的工作，並關閉 Office 365 的連線。</span><span class="sxs-lookup"><span data-stu-id="c36c7-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="c36c7-165">有內部部署環境與 Office 365 之間的網路問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="c36c7-166">如何修正錯誤碼為 450 4.4.318？</span><span class="sxs-lookup"><span data-stu-id="c36c7-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="c36c7-167">了解哪些案例適用於您，並進行必要的修正。</span><span class="sxs-lookup"><span data-stu-id="c36c7-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="c36c7-168">如果您的內部部署環境與 Office 365 之間的網路問題導致問題，請連絡您的網路小組，以疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="c36c7-169">如果錯誤是從夥伴組織 （例如，3rd 廠商雲端服務提供者），您需要連絡您的合作夥伴，若要修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="c36c7-170">錯誤碼： 450 4.7.320 憑證驗證失敗</span><span class="sxs-lookup"><span data-stu-id="c36c7-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="c36c7-171">一般而言，這個錯誤表示 Office 365 嘗試驗證目的地電子郵件伺服器的憑證時遭遇錯誤。</span><span class="sxs-lookup"><span data-stu-id="c36c7-171">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="c36c7-172">錯誤的詳細資料將說明錯誤。</span><span class="sxs-lookup"><span data-stu-id="c36c7-172">The error details will explain the error.</span></span> <span data-ttu-id="c36c7-173">例如：</span><span class="sxs-lookup"><span data-stu-id="c36c7-173">For example:</span></span>

- <span data-ttu-id="c36c7-174">憑證過期</span><span class="sxs-lookup"><span data-stu-id="c36c7-174">Certificate expired</span></span>

- <span data-ttu-id="c36c7-175">憑證主體相符</span><span class="sxs-lookup"><span data-stu-id="c36c7-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="c36c7-176">不再是有效的憑證</span><span class="sxs-lookup"><span data-stu-id="c36c7-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="c36c7-177">如何修正錯誤碼為 450 4.7.320？</span><span class="sxs-lookup"><span data-stu-id="c36c7-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="c36c7-178">修正憑證，或在連接器上的設定，讓 Office 365 中的郵件排入佇列可以傳送。</span><span class="sxs-lookup"><span data-stu-id="c36c7-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="c36c7-179">如果錯誤是從夥伴組織 （例如，3rd 廠商雲端服務提供者），您需要連絡您的合作夥伴，若要修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="c36c7-180">其他的錯誤碼</span><span class="sxs-lookup"><span data-stu-id="c36c7-180">Other error codes</span></span>

<span data-ttu-id="c36c7-181">Office 365 是困難將郵件傳遞至您內部部署或協力廠商電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="c36c7-181">Office 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="c36c7-182">用於**目的地伺服器**資訊的錯誤檢查此問題： 在環境中，或修改連接器，如果沒有設定錯誤。</span><span class="sxs-lookup"><span data-stu-id="c36c7-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="c36c7-183">如果錯誤是從夥伴組織 （例如，3rd 廠商雲端服務提供者），您需要連絡您的合作夥伴，若要修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="c36c7-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
