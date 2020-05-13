---
title: 郵件流程智慧
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
description: 系統管理員可以深入瞭解與使用連接器（也稱為「郵件流程智慧」）郵件傳遞相關聯的錯誤代碼。
ms.openlocfilehash: 55b57e4b487444abb57bcc184ef6fd742ea9dc1d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206613"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="b2ae4-103">EOP 中的郵件流程智慧</span><span class="sxs-lookup"><span data-stu-id="b2ae4-103">Mail flow intelligence in EOP</span></span>

<span data-ttu-id="b2ae4-104">在包含 Exchange Online 或獨立 Exchange online Protection （EOP）組織中信箱的 Microsoft 365 組織中，您通常會使用連接器將電子郵件訊息從 EOP 路由傳送至您的內部部署電子郵件環境。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="b2ae4-105">您也可以使用連接器將來自 Microsoft 365 的郵件路由傳送至夥伴組織。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="b2ae4-106">當 Microsoft 365 無法透過連接器傳遞這些郵件時，他們就會在 Microsoft 365 中佇列。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="b2ae4-107">Microsoft 365 會繼續重試每封郵件24小時的傳遞。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="b2ae4-108">24小時後，佇列中的郵件會到期，而且郵件會傳回給原始寄件者的未傳遞回報（也稱為 NDR 或退回的郵件）。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="b2ae4-109">當無法使用連接器傳遞郵件時，Microsoft 365 會產生錯誤。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="b2ae4-110">本主題說明最常見的錯誤及其解決方案。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="b2ae4-111">透過連接器傳送的未傳遞郵件的排隊和通知錯誤，稱為「_郵件流程智慧_」。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="b2ae4-112">錯誤碼： 450 4.4.312 DNS 查詢失敗</span><span class="sxs-lookup"><span data-stu-id="b2ae4-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="b2ae4-113">一般來說，此錯誤表示 Microsoft 365 嘗試連線至連接器中指定的智慧主機，但 DNS 查詢可尋找智慧主機的 IP 位址失敗。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="b2ae4-114">這種錯誤的可能原因如下：</span><span class="sxs-lookup"><span data-stu-id="b2ae4-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="b2ae4-115">您網域的 DNS 主機服務（為您的網域維護授權名稱伺服器的一方）發生問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="b2ae4-116">您的網域最近到期，所以無法檢索 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="b2ae4-117">您的網域的 MX 記錄最近已變更，而且 DNS 伺服器仍會為您的網域預先快取 DNS 資訊。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="b2ae4-118">如何修正錯誤碼 450 4.4.312？</span><span class="sxs-lookup"><span data-stu-id="b2ae4-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="b2ae4-119">請與您的 DNS 主機服務合作，以找出並修正您網域的問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="b2ae4-120">如果錯誤來自您的夥伴組織（例如，協力廠商雲端服務提供者），請與您的合作夥伴聯繫以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="b2ae4-121">錯誤碼： 450 4.4.315 Connection 超時</span><span class="sxs-lookup"><span data-stu-id="b2ae4-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="b2ae4-122">一般來說，這表示 Microsoft 365 無法連線至目的地電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="b2ae4-123">錯誤詳細資料會說明問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-123">The error details will explain the problem.</span></span> <span data-ttu-id="b2ae4-124">例如：</span><span class="sxs-lookup"><span data-stu-id="b2ae4-124">For example:</span></span>

- <span data-ttu-id="b2ae4-125">您的內部部署電子郵件伺服器已停機。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="b2ae4-126">連接器的智慧主機設定中有錯誤，因此 Microsoft 365 會嘗試連接至錯誤的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="b2ae4-127">如何修正錯誤碼 450 4.4.315？</span><span class="sxs-lookup"><span data-stu-id="b2ae4-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="b2ae4-128">找出哪個案例適用于您，並進行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="b2ae4-129">例如，如果郵件流程運作正常，但尚未變更連接器設定，則需要檢查您的內部部署電子郵件環境，以查看伺服器是否已關機，或網路基礎結構是否有任何變更（例如，您已變更 internet 服務提供者，所以您現在有不同的 IP 位址）。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="b2ae4-130">如果錯誤來自您的夥伴組織（例如，協力廠商雲端服務提供者），請與您的合作夥伴聯繫以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="b2ae4-131">錯誤碼： 450 4.4.316 連接被拒絕</span><span class="sxs-lookup"><span data-stu-id="b2ae4-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="b2ae4-132">一般來說，此錯誤表示 Microsoft 365 嘗試連線至目的地電子郵件伺服器時，發生連線錯誤。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="b2ae4-133">這種錯誤的可能原因是，您的防火牆封鎖的是 Microsoft 365 IP 位址的連線。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="b2ae4-134">或者，如果您已完全將內部部署電子郵件系統移轉至 Microsoft 365 並關閉您的內部部署電子郵件環境，則設計可能會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="b2ae4-135">如何修正錯誤碼 450 4.4.316？</span><span class="sxs-lookup"><span data-stu-id="b2ae4-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="b2ae4-136">如果您的內部部署環境中有信箱，您必須修改防火牆設定，以允許 TCP 埠25上來自 Microsoft 365 IP 位址的連線到您的內部部署電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="b2ae4-137">如需 Microsoft 365 IP 位址的清單，請參閱[microsoft 365 URLs 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="b2ae4-138">若您的內部部署環境中未傳遞任何郵件，請按一下警示中的 [**立即修正**]，讓 Microsoft 365 可以立即拒絕具有無效收件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="b2ae4-139">這會降低超出組織的配額以取得無效收件者的風險，這可能會影響一般郵件傳遞。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="b2ae4-140">或者，您可以使用下列指示以手動修正問題：</span><span class="sxs-lookup"><span data-stu-id="b2ae4-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="b2ae4-141">在[Exchange 系統管理中心（EAC）](https://docs.microsoft.com/Exchange/exchange-admin-center)中，停用或刪除可將電子郵件從 Microsoft 365 傳送至您的內部部署電子郵件環境的連接器：</span><span class="sxs-lookup"><span data-stu-id="b2ae4-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="b2ae4-142">在 EAC 中，移至 [**郵件流程** \> **連接器**]。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="b2ae4-143">選取 [**寄件者**] 值為**Office 365**的連接器，並選取**您組織的電子郵件伺服器**的 [**到**] 值，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="b2ae4-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="b2ae4-144">按一下 [**刪除**移除圖示] 以刪除連接器 ![](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="b2ae4-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="b2ae4-145">按一下 [**編輯** ![ 編輯圖示] 並取消 ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 選中 **，以**停用連接器。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="b2ae4-146">將與您的內部部署電子郵件環境關聯的 Microsoft 365 中公認的網域從**內部轉送**變更為**權威性**。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="b2ae4-147">如需相關指示，請參閱[管理 Exchange Online 中公認的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="b2ae4-148">**附注**：一般會有30分鐘到1小時的變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="b2ae4-149">一小時後，請確認您不再收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="b2ae4-150">如果錯誤來自您的夥伴組織（例如，協力廠商雲端服務提供者），您必須聯繫您的合作夥伴以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="b2ae4-151">錯誤碼： 450 4.4.317 無法連接至遠端伺服器</span><span class="sxs-lookup"><span data-stu-id="b2ae4-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="b2ae4-152">此錯誤通常是指 Microsoft 365 連接至目的地電子郵件伺服器，但伺服器會以立即錯誤回應，或不符合連線需求。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="b2ae4-153">錯誤詳細資料會說明問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-153">The error details will explain the problem.</span></span> <span data-ttu-id="b2ae4-154">例如：</span><span class="sxs-lookup"><span data-stu-id="b2ae4-154">For example:</span></span>

- <span data-ttu-id="b2ae4-155">目的地電子郵件伺服器會以「服務無法使用」的錯誤回應，這表示伺服器無法與 Microsoft 365 保持通訊。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="b2ae4-156">連接器設定為需要 TLS，但目的地電子郵件伺服器不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="b2ae4-157">如何修正錯誤碼 450 4.4.317？</span><span class="sxs-lookup"><span data-stu-id="b2ae4-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="b2ae4-158">確認您的內部部署電子郵件伺服器上的 TLS 設定和憑證，以及連接器上的 TLS 設定。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="b2ae4-159">如果錯誤來自您的夥伴組織（例如，協力廠商雲端服務提供者），您必須聯繫您的合作夥伴以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="b2ae4-160">錯誤碼： 450 4.4.318 Connection 突然關閉</span><span class="sxs-lookup"><span data-stu-id="b2ae4-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="b2ae4-161">一般來說，此錯誤表示 Microsoft 365 在與您的內部部署電子郵件環境通訊時有困難，所以連線已中斷。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="b2ae4-162">這種錯誤的可能原因如下：</span><span class="sxs-lookup"><span data-stu-id="b2ae4-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="b2ae4-163">您的防火牆使用 SMTP 封包檢查規則，而這些規則不會正常運作。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="b2ae4-164">您的內部部署電子郵件伺服器無法正常運作（例如，服務懸掛、損毀或低系統資源），這會導致伺服器超時並關閉 Microsoft 365 的連線。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="b2ae4-165">您的內部部署環境與 Microsoft 365 之間有網路問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="b2ae4-166">如何修正錯誤碼 450 4.4.318？</span><span class="sxs-lookup"><span data-stu-id="b2ae4-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="b2ae4-167">找出哪個案例適用于您，並進行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="b2ae4-168">如果問題是由您的內部部署環境和 Microsoft 365 之間的網路問題所造成，請與您的網路小組聯繫以進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="b2ae4-169">如果錯誤來自您的夥伴組織（例如，協力廠商雲端服務提供者），您必須聯繫您的合作夥伴以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="b2ae4-170">錯誤碼： 450 4.7.320 憑證驗證失敗</span><span class="sxs-lookup"><span data-stu-id="b2ae4-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="b2ae4-171">一般來說，此錯誤表示 Microsoft 365 在嘗試驗證目的地電子郵件伺服器的憑證時，發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="b2ae4-172">錯誤詳細資料會說明錯誤。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-172">The error details will explain the error.</span></span> <span data-ttu-id="b2ae4-173">例如：</span><span class="sxs-lookup"><span data-stu-id="b2ae4-173">For example:</span></span>

- <span data-ttu-id="b2ae4-174">憑證已到期</span><span class="sxs-lookup"><span data-stu-id="b2ae4-174">Certificate expired</span></span>

- <span data-ttu-id="b2ae4-175">憑證主體不符</span><span class="sxs-lookup"><span data-stu-id="b2ae4-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="b2ae4-176">憑證已不再有效</span><span class="sxs-lookup"><span data-stu-id="b2ae4-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="b2ae4-177">如何修正錯誤碼 450 4.7.320？</span><span class="sxs-lookup"><span data-stu-id="b2ae4-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="b2ae4-178">修正連接器上的憑證或設定，讓 Microsoft 365 中的排隊郵件可以傳遞。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="b2ae4-179">如果錯誤來自您的夥伴組織（例如，協力廠商雲端服務提供者），您必須聯繫您的合作夥伴以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="b2ae4-180">其他錯誤碼</span><span class="sxs-lookup"><span data-stu-id="b2ae4-180">Other error codes</span></span>

<span data-ttu-id="b2ae4-181">Microsoft 365 在將郵件傳遞至您的內部部署或夥伴電子郵件伺服器時遇到問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="b2ae4-182">請使用錯誤中的**目的伺服器**資訊檢查您環境中的問題，或在發生設定錯誤時修改連接器。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="b2ae4-183">如果錯誤來自您的夥伴組織（例如，協力廠商雲端服務提供者），您必須聯繫您的合作夥伴以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="b2ae4-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
