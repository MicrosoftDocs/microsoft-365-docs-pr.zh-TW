---
title: SMTP 驗證用戶端報告
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
description: 系統管理員可以了解 SMTP 驗證的用戶端報表中安全性 & 合規性中心中的郵件流程儀表板。
ms.openlocfilehash: 7dee70de4000b23302348d964010801c8e097744
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598830"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="61b07-103">SMTP 驗證用戶端報告</span><span class="sxs-lookup"><span data-stu-id="61b07-103">SMTP Auth clients report</span></span>

<span data-ttu-id="61b07-104">**SMTP 驗證的用戶端**報表會醒目提示 SMTP 驗證用戶端提交通訊協定，由使用者或系統帳戶，在您的組織中的使用。</span><span class="sxs-lookup"><span data-stu-id="61b07-104">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="61b07-105">此舊版通訊協定 （使用端點 smtp.office365.com） 只提供基本驗證]，且容易受到正由遭入侵帳戶傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="61b07-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="61b07-106">此報告可讓您檢查有不尋常的活動。</span><span class="sxs-lookup"><span data-stu-id="61b07-106">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="61b07-107">它也顯示 TLS 流量資料的用戶端或裝置使用 SMTP 驗證]。</span><span class="sxs-lookup"><span data-stu-id="61b07-107">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="61b07-108">郵件流程儀表板中顯示小工具指示的使用者或服務帳戶所擁有的 SMTP 驗證通訊協定過去 7 天的數目。</span><span class="sxs-lookup"><span data-stu-id="61b07-108">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![SMTP 驗證的用戶端報表中安全性 & 合規性中心中的郵件流程儀表板](../media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="61b07-110">按一下 [] 小工具會開啟提供 TLS 流量及磁碟區的彙總的檢視的最後一週彈出式視窗。</span><span class="sxs-lookup"><span data-stu-id="61b07-110">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![SMTP 驗證的用戶端報告中的彈出式視窗](../media/smtp-auth-clients-flyout.png)

<span data-ttu-id="61b07-112">當您按一下 [ **SMTP 驗證的用戶端報告**] 連結時，您會看到兩個主要的資料樞紐分析表和兩個資料檢視。</span><span class="sxs-lookup"><span data-stu-id="61b07-112">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="61b07-113">資料樞紐分析表，而**傳送大量** **TLS 流量**。</span><span class="sxs-lookup"><span data-stu-id="61b07-113">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="61b07-114">[資料] 檢視，而圖表 details] 資料表。</span><span class="sxs-lookup"><span data-stu-id="61b07-114">The data views are the chart and the details table.</span></span>

<span data-ttu-id="61b07-115">**傳送大量**檢視會顯示使用 SMTP 驗證指定的時間範圍內所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="61b07-115">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="61b07-116">您可以藉由按一下 [**篩選器**調整範圍。</span><span class="sxs-lookup"><span data-stu-id="61b07-116">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="61b07-117">圖表會依照寄件者網域。</span><span class="sxs-lookup"><span data-stu-id="61b07-117">The chart is organized by sender domain.</span></span> <span data-ttu-id="61b07-118">您可以看到下拉式清單中**顯示的資料**中選取該網域的每個網域的個別的資料。</span><span class="sxs-lookup"><span data-stu-id="61b07-118">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![在 [SMTP 驗證傳送大量的用戶端報告](../media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="61b07-120">您可以檢視寄件者的詳細的資訊，以及其訊息計數藉由按一下 [**檢視詳細資料] 表格**。</span><span class="sxs-lookup"><span data-stu-id="61b07-120">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="61b07-121">若要傳回的圖表，請按一下 [**檢視報告**。</span><span class="sxs-lookup"><span data-stu-id="61b07-121">To return to the chart, click **View report**.</span></span>

![傳送大量 SMTP 驗證的用戶端報告的詳細資料表格](../media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="61b07-123">**TLS 流量**樞紐分析表是很重要，因為 TLS1.0 和 Office 365 中的 TLS1.1 即將來臨的 deprecation >。</span><span class="sxs-lookup"><span data-stu-id="61b07-123">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="61b07-124">許多傳統的裝置和應用程式將無法傳送電子郵件，如果他們只能夠 TLS1.0 使用 SMTP 驗證]。這個樞紐分析表可讓您以找出並採取動作的使用者和仍在使用 TLS 的舊版本的系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="61b07-124">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![在 SMTP 驗證用戶端的 TLS 流量報告](../media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="61b07-126">您可以檢視的寄件者，他們會使用 SMTP 驗證的 TLS 版本的詳細的資訊，以及其訊息計數藉由按一下 [**檢視詳細資料] 表格**。</span><span class="sxs-lookup"><span data-stu-id="61b07-126">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="61b07-127">若要傳回的圖表，請按一下 [**檢視報告**。</span><span class="sxs-lookup"><span data-stu-id="61b07-127">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="61b07-128">您也可以藉由按一下 [要求報告下載版本更詳細的報告。</span><span class="sxs-lookup"><span data-stu-id="61b07-128">You can also download a more detailed version of the report by clicking Request report.</span></span>

![SMTP 驗證的用戶端報告中的 TLS 使用狀況詳細資料表格](../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a><span data-ttu-id="61b07-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="61b07-130">See also</span></span>

<span data-ttu-id="61b07-131">如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="61b07-131">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
