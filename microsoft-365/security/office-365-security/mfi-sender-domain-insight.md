---
title: 修正寄件者網域深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解安全性 & 規範中心的郵件流程儀表板中的修正寄件者網域洞察力。
ms.openlocfilehash: c4cf4a87ad770325ca6ad2f0b87ac8ce52c345c2
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818828"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="ec1e8-103">修正寄件者網域深入解析</span><span class="sxs-lookup"><span data-stu-id="ec1e8-103">Fix sender domain insight</span></span>

<span data-ttu-id="ec1e8-104">Microsoft 365 需要從內部內部部署電子郵件環境傳送至 Microsoft 365 的郵件，以符合特定的安全性準則：</span><span class="sxs-lookup"><span data-stu-id="ec1e8-104">Microsoft 365 requires messages sending from internal on-premises email environments to Microsoft 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="ec1e8-105">您已在 Microsoft 365 中建立輸入連接器，以利用來源 IP 位址或憑證來驗證來自內部部署電子郵件伺服器的 SMTP 連線。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-105">You've created an inbound connector in Microsoft 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="ec1e8-106">您已設定內部部署電子郵件伺服器，透過 Microsoft 365 將電子郵件轉送至外部世界。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-106">You've configured your on-premises email server to relay email via Microsoft 365 to external world.</span></span>

- <span data-ttu-id="ec1e8-107">在您的設定中，下列其中一個表述為真：</span><span class="sxs-lookup"><span data-stu-id="ec1e8-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="ec1e8-108">寄件者的電子郵件網域已在您的組織中註冊。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-108">The sender's email domain is registered in your organization.</span></span> <span data-ttu-id="ec1e8-109">如需詳細資訊，請參閱在 Office 365 中新增網域 (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="ec1e8-110">您的內部部署電子郵件伺服器設定為使用憑證將電子郵件傳送至 Microsoft 365，該憑證包含或完全符合您在 Microsoft 365 中註冊的功能變數名稱，而且您已在 Microsoft 365 中以該網域建立一個以憑證為基礎的連接器。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-110">Your on-premises email server is configured to use a certificate to send email to Microsoft 365, the certificate contains or exactly matches a domain name that you've registered in Microsoft 365, and you've created a certificate based connector in Microsoft 365 with that domain.</span></span> 

<span data-ttu-id="ec1e8-111">不符合準則的郵件將不會歸對組織，而且可能會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="ec1e8-112">**Fix sender domain**真知灼見會向您顯示來自內部部署環境的電子郵件，但不符合準則，可協助您識別內部部署電子郵件環境中可能遭到破壞的機器和使用者帳戶，並協助您採取修正動作。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![在安全性 & 規範中心的郵件流程儀表板中，修正寄件者網域的洞察力](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="ec1e8-114">當您按一下 [**查看詳細資料**] 時，會移至另一個包含更多詳細資料的小工具，如下列圖表所示：</span><span class="sxs-lookup"><span data-stu-id="ec1e8-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![Fix sender domain 真知灼見中的詳細資料小工具](../../media/sender-domain-view-details.png)

<span data-ttu-id="ec1e8-116">您會看到用來將郵件傳遞到 Office 365 的輸入連接器。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="ec1e8-117">您也可以按一下 [ **view sample message IDs** ]，以查看從您的內部部署電子郵件環境傳送的郵件詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="ec1e8-118">因為這些郵件是由 Office 365 拒絕，所以您無法使用郵件追蹤，但是您可以使用示範郵件識別碼來追蹤內部部署電子郵件環境中的郵件。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![View a Fix sender domain 真知灼見中的示範郵件識別碼](../../media/sender-domain-view-sample-message-ids.png)

## <a name="related-topics"></a><span data-ttu-id="ec1e8-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="ec1e8-120">Related topics</span></span>

<span data-ttu-id="ec1e8-121">如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1e8-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
