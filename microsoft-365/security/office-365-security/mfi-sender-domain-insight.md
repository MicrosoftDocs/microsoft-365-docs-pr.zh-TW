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
description: 系統管理員可以了解修正寄件者網域深入了解安全性 & 合規性中心中的郵件流程儀表板中。
ms.openlocfilehash: 1b154f4aecd5ada711b9177380d936cd888df425
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598820"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="04654-103">修正寄件者網域深入解析</span><span class="sxs-lookup"><span data-stu-id="04654-103">Fix sender domain insight</span></span>

<span data-ttu-id="04654-104">Office 365 需要從內部電子郵件環境到 Office 365 傳送到符合特定安全性條件的郵件：</span><span class="sxs-lookup"><span data-stu-id="04654-104">Office 365 requires messages sending from internal on-premises email environments to Office 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="04654-105">您已在使用來源 IP 位址或憑證驗證從您的內部部署電子郵件伺服器的 SMTP 連線的 Office 365 中建立的輸入的連接器。</span><span class="sxs-lookup"><span data-stu-id="04654-105">You've created an inbound connector in Office 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="04654-106">您已設定內部部署電子郵件伺服器轉送外部世界透過 Office 365 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="04654-106">You've configured your on-premises email server to relay email via Office 365 to external world.</span></span>

- <span data-ttu-id="04654-107">在您的組態，其中一個下列陳述式為真：</span><span class="sxs-lookup"><span data-stu-id="04654-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="04654-108">寄件者的電子郵件網域註冊 Office 365 組織中。</span><span class="sxs-lookup"><span data-stu-id="04654-108">The sender's email domain is registered in your Office 365 organization.</span></span> <span data-ttu-id="04654-109">如需詳細資訊，請參閱 < Office 365 中的 [新增網域。</span><span class="sxs-lookup"><span data-stu-id="04654-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="04654-110">內部部署電子郵件伺服器設定為使用憑證來傳送電子郵件給 Office 365 憑證包含或完全符合您已在 Office 365 中註冊的網域名稱，您已在 Office 365 中建立憑證型連接器程式網域。</span><span class="sxs-lookup"><span data-stu-id="04654-110">Your on-premises email server is configured to use a certificate to send email to Office 365, the certificate contains or exactly matches a domain name that you've registered in Office 365, and you've created a certificate based connector in Office 365 with that domain.</span></span> 

<span data-ttu-id="04654-111">不符合準則的郵件不歸因於組織，可能會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="04654-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="04654-112">**修正寄件者網域**深入了解顯示您的電子郵件從內部部署環境不符合準則，可協助您識別可能入侵的機器和使用者帳戶在內部部署電子郵件環境中，可協助您採取補救動作。</span><span class="sxs-lookup"><span data-stu-id="04654-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![修正寄件者網域深入了解在郵件流程儀表板中安全性 & 合規性中心](../media/sender-domain-insight-selected.png)

<span data-ttu-id="04654-114">當您按一下 [**檢視詳細資料**時，您將被帶往另一個小工具以更多的詳細資訊，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="04654-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![[詳細資料] 小工具在修正寄件者網域深入解析](../media/sender-domain-view-details.png)

<span data-ttu-id="04654-116">您會看到已用來將郵件傳遞到 Office 365 的輸入的連接器。</span><span class="sxs-lookup"><span data-stu-id="04654-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="04654-117">您也可以按一下**檢視範例郵件識別碼**，以查看從內部部署電子郵件環境傳送郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="04654-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="04654-118">因為這些郵件所拒絕的 Office 365，您無法使用郵件追蹤，但您可以使用範例郵件識別碼在內部部署電子郵件環境中追蹤郵件。</span><span class="sxs-lookup"><span data-stu-id="04654-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![在修正寄件者網域深入了解檢視範例郵件識別碼](../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="04654-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="04654-120">See also</span></span>

<span data-ttu-id="04654-121">如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="04654-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
