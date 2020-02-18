---
title: 適用於 Office Online Server 和 Office Web Apps Server 的 GDPR
description: 深入了解如何在內部部署 Exchange Server 中解決 GDPR 需求。
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: e16f206c858d35dd2894b44d398e375c0a59fde5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073253"
---
# <a name="gdpr-for-office-web-apps-server-and-office-online-server"></a><span data-ttu-id="35e15-103">適用於 Office Web Apps Server 和 Office Online Server 的 GDPR</span><span class="sxs-lookup"><span data-stu-id="35e15-103">GDPR for Office Web Apps Server and Office Online Server</span></span>

<span data-ttu-id="35e15-p101">Office Online Server 和 Office Web Apps Server 遙測資料是以 ULS 記錄的形式儲存。您可以使用 [ULS 檢視器](https://www.microsoft.com/download/details.aspx?id=44020)，從您的內部部署租用戶檢視 ULS 記錄。</span><span class="sxs-lookup"><span data-stu-id="35e15-p101">Office Online Server and Office Web Apps Server telemetry data is stored in the form of ULS logs. You can use [ULS Viewer](https://www.microsoft.com/download/details.aspx?id=44020) to view ULS logs from your on-premises tenant.</span></span>

<span data-ttu-id="35e15-p102">每個記錄行包含 CorrelationID。相關的記錄行會共用相同的 CorrelationID。每個 CorrelationID 繫結至單一 SessionID，而一個 SessionID 可能與許多 CorrelationID 相關。每個 SessionID 可能與單一 UserID 相關，某些工作階段是匿名的，因此沒有相關聯的 UserID。為了判斷哪些資料與特定使用者相關聯，會從單一 UserID 對應至與該使用者相關聯的 SessionID、從這些 SessionID 對應至相關聯的 CorrelationID，然後從這些 CorrelationID 對應至這些相互關聯中的所有記錄。請參閱下圖以了解不同識別碼之間的關係。</span><span class="sxs-lookup"><span data-stu-id="35e15-p102">Every log line contains a CorrelationID. Related log lines share the same CorrelationID. Each CorrelationID is tied to a single SessionID, and one SessionID may be related to many CorrelationIDs. Each SessionID may be related to a single UserID, although some sessions can be anonymous and therefore not have an associated UserID. In order to determine what data is associated with a particular user, it is therefore possible to map from a single UserID to the SessionIDs associated with that user, from those SessionIDs to the associated CorrelationIDs, and from those CorrelationIDs to all the logs in those correlations. See the below diagram for the relationship between the different IDs.</span></span>

![](../media/gdpr-for-office-online-server-image1.jpg)

## <a name="gathering-logs"></a><span data-ttu-id="35e15-112">收集記錄</span><span class="sxs-lookup"><span data-stu-id="35e15-112">Gathering Logs</span></span>

<span data-ttu-id="35e15-p103">舉例來說，若要收集與 UserID 1 相關聯的所有記錄，第一個步驟是收集與 UserID 1 相關聯的所有工作階段 (也就是 SessionID 1 和 SessionID2)。下一步是收集與 SessionID 1 相關聯的所有相互關聯 (也就是 CorrelationIDs 1、2 和 3) 以及與 SessionID 2 相關聯的所有相互關聯 (也就是 CorrelationID 4)。最後，收集與清單中的每個相互關聯相關聯的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="35e15-p103">In order to gather all logs associated with UserID 1, for example, the first step would be to gather all sessions associated with UserID 1 (i.e. SessionID 1 and SessionID2). The next step would be to gather all correlations associated with SessionID 1 (i.e. CorrelationIDs 1, 2, and 3) and with SessionID 2 (i.e. CorrelationID 4). Finally, gather all logs associated with each of the correlations in the list.</span></span>

1.  <span data-ttu-id="35e15-116">啟動 UlsViewer</span><span class="sxs-lookup"><span data-stu-id="35e15-116">Launch UlsViewer</span></span>

2.  <span data-ttu-id="35e15-117">開啟對應至預期時間範圍的 ULS 記錄；ULS 記錄儲存在 %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span><span class="sxs-lookup"><span data-stu-id="35e15-117">Open up the uls log corresponding to the intended timeframe; ULS logs are stored in %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span></span>

3.  <span data-ttu-id="35e15-118">編輯 | 修改篩選</span><span class="sxs-lookup"><span data-stu-id="35e15-118">Edit | Modify Filter</span></span>

4.  <span data-ttu-id="35e15-119">套用以下篩選：</span><span class="sxs-lookup"><span data-stu-id="35e15-119">Apply a filter that is:</span></span>

    -   <span data-ttu-id="35e15-120">EventID 等於 apr3y 或</span><span class="sxs-lookup"><span data-stu-id="35e15-120">EventID equals apr3y Or</span></span>

    -   <span data-ttu-id="35e15-121">EventID 等於 bp2d6</span><span class="sxs-lookup"><span data-stu-id="35e15-121">EventID equals bp2d6</span></span>

5.  <span data-ttu-id="35e15-122">雜湊的 UserIds 會在其中一個事件的 Message 中</span><span class="sxs-lookup"><span data-stu-id="35e15-122">Hashed UserIds will be in the Message of either one of these two events</span></span>

6.  <span data-ttu-id="35e15-123">針對 apr3y，Message 會包含 UserID 值和 PUID 值</span><span class="sxs-lookup"><span data-stu-id="35e15-123">For apr3y, the Message will contain a UserID value and a PUID value</span></span>

7.  <span data-ttu-id="35e15-p104">針對 bp2d6，Message 會包含一些資訊。LoggableUserId 值欄位是雜湊的 UserID。</span><span class="sxs-lookup"><span data-stu-id="35e15-p104">For bp2d6, the Message will contain quite a bit of information. The LoggableUserId Value field is the hashed UserID.</span></span>

8.  <span data-ttu-id="35e15-126">一旦從其中一個標記取得雜湊的 UserId，該資料列的 WacSessionId 值在 ULSViewer 中會包含與該使用者相關聯的 WacSessionId</span><span class="sxs-lookup"><span data-stu-id="35e15-126">Once the hashed UserId is obtained from either of these two tags, the WacSessionId value of that row in ULSViewer will contain the WacSessionId associated with that user</span></span>

9.  <span data-ttu-id="35e15-127">收集與有問題的使用者相關聯的所有 WacSessionId 值</span><span class="sxs-lookup"><span data-stu-id="35e15-127">Collect all of the WacSessionId values associated with the user in question</span></span>

10. <span data-ttu-id="35e15-128">針對清單中的第一個 WacSessionId，以所有 EventId 等於 "xmnv"、Message 等於 "UserSessionId=\<WacSessionId\>" 進行篩選 (使用您的 WacSessionId 取代篩選的 \<WacSessionId\> 部分)</span><span class="sxs-lookup"><span data-stu-id="35e15-128">Filter for all EventId equals "xmnv", Message equals "UserSessionId=\<WacSessionId\>" for the first WacSessionId in the list (replacing the \<WacSessionId\> part of the filter with your WacSessionId)</span></span>

11. <span data-ttu-id="35e15-129">收集與該 WacSessionId 相符的所有 Correlation 值</span><span class="sxs-lookup"><span data-stu-id="35e15-129">Collect all values of Correlation that match that WacSessionId</span></span>

12. <span data-ttu-id="35e15-130">為有問題的使用者針對清單中 WacSessionId 的所有值，重複步驟 10-11</span><span class="sxs-lookup"><span data-stu-id="35e15-130">Repeat steps 10-11 for all values of WacSessionId in your list for the user in question</span></span>

13. <span data-ttu-id="35e15-131">針對所有 Correlation 等於您的清單中第一個 Correlation 進行篩選</span><span class="sxs-lookup"><span data-stu-id="35e15-131">Filter for all Correlation equals the first Correlation in your list</span></span>

14. <span data-ttu-id="35e15-132">收集符合該 Correlation 的所有記錄</span><span class="sxs-lookup"><span data-stu-id="35e15-132">Collect all logs matching that Correlation</span></span>

15. <span data-ttu-id="35e15-133">為有問題的使用者針對清單中 Correlation 的所有值，重複步驟 13-14</span><span class="sxs-lookup"><span data-stu-id="35e15-133">Repeat steps 13-14 for all values of Correlation in your list for the user in question</span></span>

## <a name="types-of-data"></a><span data-ttu-id="35e15-134">資料類型</span><span class="sxs-lookup"><span data-stu-id="35e15-134">Types of Data</span></span>

<span data-ttu-id="35e15-p105">Office 記錄包含各種不同類型的資料。以下是 ULS 記錄可能包含的資料範例：</span><span class="sxs-lookup"><span data-stu-id="35e15-p105">Office logs contain a variety of different types of data. The following are examples of the data that ULS logs may contain:</span></span>

-   <span data-ttu-id="35e15-137">使用產品時發生的問題的錯誤碼</span><span class="sxs-lookup"><span data-stu-id="35e15-137">Error codes for issues encountered during use of the product</span></span>

-   <span data-ttu-id="35e15-138">按一下按鈕和與應用程式使用方式相關的其他資料片段</span><span class="sxs-lookup"><span data-stu-id="35e15-138">Button clicks and other pieces of data about app usage</span></span>

-   <span data-ttu-id="35e15-139">應用程式及/或應用程式內特定功能的效能資料</span><span class="sxs-lookup"><span data-stu-id="35e15-139">Performance data about the app and/or particular features within the app</span></span>

-   <span data-ttu-id="35e15-140">使用者電腦所在的一般位置資訊 (例如，從 IP 位址衍生的國家/區域、州和城市)，而不是準確的地理位置</span><span class="sxs-lookup"><span data-stu-id="35e15-140">General location information about where the user’s computer is (e.g. country / region, state, and city, derived from the IP address), but not precise geolocation</span></span>

-   <span data-ttu-id="35e15-141">瀏覽器的相關基本中繼資料，例如，瀏覽器名稱和版本，以及電腦，例如，作業系統類型和版本</span><span class="sxs-lookup"><span data-stu-id="35e15-141">Basic metadata about the browser, e.g. browser name and version, and the computer, e.g. OS type and version</span></span>

-   <span data-ttu-id="35e15-142">來自文件主機的錯誤訊息 (例如，OneDrive、SharePoint、Exchange)</span><span class="sxs-lookup"><span data-stu-id="35e15-142">Error messages from the document host (e.g. OneDrive, SharePoint, Exchange)</span></span>

-   <span data-ttu-id="35e15-143">應用程式內部程序的相關資訊，與使用者採取的任何動作不相關</span><span class="sxs-lookup"><span data-stu-id="35e15-143">Information about processes internal to the app, unrelated to any action the user has taken</span></span>
