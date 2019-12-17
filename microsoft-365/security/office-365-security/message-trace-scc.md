---
title: 安全性與合規性中心內的郵件追蹤
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: 系統管理員可以在安全性與合規性中心使用郵件追蹤，以了解郵件發生什麼情況。
ms.openlocfilehash: fa10c4168720565770ec0a3bc4bb06486155c3cc
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970329"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="1b6de-103">安全性與合規性中心內的郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="1b6de-103">Message trace in the Security & Compliance Center</span></span>

## <a name="overview"></a><span data-ttu-id="1b6de-104">概觀</span><span class="sxs-lookup"><span data-stu-id="1b6de-104">Overview</span></span>

<span data-ttu-id="1b6de-105">安全性與合規性中心內的郵件追蹤可追蹤透過 Exchange Online 組織收發的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-105">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="1b6de-106">您可以判斷服務是否已經收到、拒絕、延遲或傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-106">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="1b6de-107">它也會顯示在郵件到達其最終狀態前，已對郵件執行哪些動作。</span><span class="sxs-lookup"><span data-stu-id="1b6de-107">It also shows what actions were taken on the message before it reached its final status.</span></span>

> [!NOTE]
> <span data-ttu-id="1b6de-108">若要執行郵件追蹤，系統管理員必須是組織管理、合規性管理或支援人員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1b6de-108">To perform message trace, administrator must be member of Organization Management, Compliance Management or Help Desk role groups.</span></span>

<span data-ttu-id="1b6de-109">安全性與合規性中心內的郵件追蹤改善了 Exchange 系統管理中心 (EAC) 內所提供的郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="1b6de-109">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="1b6de-110">您可以使用來自郵件追蹤的資訊，有效率地回答使用者其郵件有何變化的相關問題、疑難排解郵件流程問題，以及驗證原則變更。</span><span class="sxs-lookup"><span data-stu-id="1b6de-110">You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="1b6de-111">結果中只會顯示前 50000 封郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-111">Only the first 50000 messages are displayed in the results.</span></span> <span data-ttu-id="1b6de-112">Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的 [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/reporting/get-historicalsearch) Cmdlet 會在結果中傳回所有郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-112">The [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/reporting/get-historicalsearch) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="1b6de-113">開啟郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="1b6de-113">Open the message trace tool</span></span>

1. <span data-ttu-id="1b6de-114">以工作或學校帳戶[登入 Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-114">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="1b6de-115">選取左上角的應用程式啟動器圖示 ![Office 365 應用程式啟動器圖示](../media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png)，然後選擇 [管理員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1b6de-115">Select the app launcher icon ![The app launcher icon in Office 365](../media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span>

3. <span data-ttu-id="1b6de-116">在左下方瀏覽區域中，展開 [系統管理中心]\*\*\*\*，然後選取 [安全性與合規性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1b6de-116">In the lower-left navigation pane, expand **Admin centers** and select  **Exchange**.</span></span>

4. <span data-ttu-id="1b6de-117">在隨即開啟的 [安全性與合規性]\*\*\*\* 頁面中，展開 [郵件流程]\*\*\*\*，然後選取 [訊息追蹤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1b6de-117">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="1b6de-118">[訊息追蹤] 頁面</span><span class="sxs-lookup"><span data-stu-id="1b6de-118">Message trace page</span></span>

<span data-ttu-id="1b6de-119">您可以按一下 [開始追蹤]\*\*\*\* 按鈕，從這裡開始新的預設追蹤。</span><span class="sxs-lookup"><span data-stu-id="1b6de-119">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="1b6de-120">這會搜尋過去兩天的所有寄件者和收件者的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-120">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="1b6de-121">或者，您也可以從可用的查詢類別使用其中一個已儲存的查詢，並且依現狀執行它們或將它們用來作為自己的查詢起點：</span><span class="sxs-lookup"><span data-stu-id="1b6de-121">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="1b6de-122">**預設查詢**：Office 365 提供的內建查詢。</span><span class="sxs-lookup"><span data-stu-id="1b6de-122">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="1b6de-123">**自訂查詢**：貴組織的系統管理員所儲存的查詢，可供日後使用。</span><span class="sxs-lookup"><span data-stu-id="1b6de-123">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="1b6de-124">**自動儲存的查詢**：過去十筆最近執行的查詢。</span><span class="sxs-lookup"><span data-stu-id="1b6de-124">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="1b6de-125">此清單可讓您輕鬆繼續進行您上次未完成的工作。</span><span class="sxs-lookup"><span data-stu-id="1b6de-125">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="1b6de-126">此外，此頁面也提供一個 [可下載的報告]\*\*\*\* 區段，顯示您已提交的要求，以及本身可供下載的報告。</span><span class="sxs-lookup"><span data-stu-id="1b6de-126">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="1b6de-127">新郵件追蹤的選項</span><span class="sxs-lookup"><span data-stu-id="1b6de-127">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="1b6de-128">依寄件者和收件者篩選</span><span class="sxs-lookup"><span data-stu-id="1b6de-128">Filter by senders and recipients</span></span>

<span data-ttu-id="1b6de-129">預設值為 [所有寄件者]\*\*\*\* 和 [所有收件者]\*\*\*\*，但您可以使用下列欄位來篩選結果：</span><span class="sxs-lookup"><span data-stu-id="1b6de-129">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="1b6de-130">**依據這些人**：在此欄位中按一下以選取貴組織中的一或多個寄件者。</span><span class="sxs-lookup"><span data-stu-id="1b6de-130">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="1b6de-131">您也可以開始輸入名稱，然後清單中的項目將依據您輸入的內容進行篩選，就像搜尋頁面的運作方式一樣。</span><span class="sxs-lookup"><span data-stu-id="1b6de-131">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="1b6de-132">**給這些人**：在此欄位中按一下以選取貴組織中的一或多個收件者。</span><span class="sxs-lookup"><span data-stu-id="1b6de-132">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="1b6de-133">您也可以輸入外部寄件者和收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-133">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="1b6de-134">支援萬用字元 (例如 `*@contoso.com`)，但您無法同時在相同的欄位中使用多個萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="1b6de-134">Wildcards are supported (for example, `*@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span><br/><span data-ttu-id="1b6de-135">您可以貼上多份以分號 (`;`) 分隔的寄件者或收件者清單。</span><span class="sxs-lookup"><span data-stu-id="1b6de-135">You can paste multiple senders or recipients lists separated by semicolons (`;`).</span></span> <span data-ttu-id="1b6de-136">空格 (`\s`)、歸位字元 (`\r`) 或換行 (`\n`)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-136">spaces (`\s`), carriage returns (`\r`), or next lines (`\n`).</span></span>

### <a name="time-range"></a><span data-ttu-id="1b6de-137">時間範圍</span><span class="sxs-lookup"><span data-stu-id="1b6de-137">Time range</span></span>

<span data-ttu-id="1b6de-138">預設值為 [2 天]\*\*\*\*，但您最多可指定 90 天的日期/時間範圍。</span><span class="sxs-lookup"><span data-stu-id="1b6de-138">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="1b6de-139">當您使用日期/時間範圍時，請考慮這些問題：</span><span class="sxs-lookup"><span data-stu-id="1b6de-139">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="1b6de-140">根據預設，您使用時間線在 [滑桿]\*\*\*\* 檢視中選取時間範圍。</span><span class="sxs-lookup"><span data-stu-id="1b6de-140">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="1b6de-141">您只能選取顯示的天數或時間設定。</span><span class="sxs-lookup"><span data-stu-id="1b6de-141">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="1b6de-142">嘗試選取介於中間的值會讓開始/結束泡泡貼齊最近的顯示設定。</span><span class="sxs-lookup"><span data-stu-id="1b6de-142">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![安全性與合規性中心的新增郵件追蹤內的滑桿時間範圍](../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="1b6de-144">不過，您也可以切換到 [自訂]\*\*\*\* 檢視，您可以在該檢視中指定 [開始日期]\*\*\*\* 和 [結束日期]\*\*\*\* 值 (包括時間)，而且還可以選取日期/時間範圍的 [時區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1b6de-144">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="1b6de-145">請注意，[時區]\*\*\*\* 設定會同時套用到您的查詢輸入和查詢結果。</span><span class="sxs-lookup"><span data-stu-id="1b6de-145">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![安全性與合規性中心的新增郵件追蹤內的自訂時間範圍](../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="1b6de-147">10 天內的結果會立即以 [摘要]\*\*\*\* 報告的形式提供。</span><span class="sxs-lookup"><span data-stu-id="1b6de-147">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="1b6de-148">如果您指定甚至稍微大於 10 天的時間範圍，結果將會顯示為只能以可下載的 CSV 檔案形式提供 ([增強摘要]\*\*\*\* 或 [延伸]\*\*\*\* 報告)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-148">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="1b6de-149">如需有關各種不同報告類型的詳細資訊，請參閱本主題中的[選擇報告類型](#choose-report-type)一節。</span><span class="sxs-lookup"><span data-stu-id="1b6de-149">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="1b6de-150">**注意**：系統會使用封存的郵件追蹤資料來準備 [增強摘要] 和 [延伸] 報告，而且最多可能需要數小時的時間，才能下載您的報告。</span><span class="sxs-lookup"><span data-stu-id="1b6de-150">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="1b6de-151">根據有多少個其他系統管理員也已同時提交報告要求而定，您可能也會在系統開始處理您的佇列要求前察覺到延遲的情形。</span><span class="sxs-lookup"><span data-stu-id="1b6de-151">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="1b6de-152">在 [滑桿]\*\*\*\* 檢視中儲存查詢會儲存相對的時間範圍 (例如，今天起 3 天之後的日期)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-152">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="1b6de-153">在 [自訂]\*\*\*\* 檢視中儲存查詢會儲存絕對的日期/時間範圍 (例如，2018-05-06 13:00 到 2018-05-08 18:00)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-153">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="1b6de-154">其他搜尋選項</span><span class="sxs-lookup"><span data-stu-id="1b6de-154">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="1b6de-155">傳遞狀態</span><span class="sxs-lookup"><span data-stu-id="1b6de-155">Delivery status</span></span>

<span data-ttu-id="1b6de-156">您可以將預設值 [全部]\*\*\*\* 保留為選取狀態，或者也可以選取下列其中一個值來篩選結果：</span><span class="sxs-lookup"><span data-stu-id="1b6de-156">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="1b6de-157">**已傳遞**：郵件已成功傳遞到預定目的地。</span><span class="sxs-lookup"><span data-stu-id="1b6de-157">**Delivered** The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="1b6de-158">**擱置**：仍在嘗試或正在重新嘗試傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-158">**Pending** Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="1b6de-159">**已展開**：在傳遞到群組的個別成員之前，已展開通訊群組收件者。</span><span class="sxs-lookup"><span data-stu-id="1b6de-159">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="1b6de-160">**失敗**：未傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-160">**Failed** The message was not delivered.</span></span>

- <span data-ttu-id="1b6de-161">**已隔離**：已隔離郵件 (垃圾郵件、大宗郵件或網路釣魚)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-161">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="1b6de-162">如需詳細資訊，請參閱[在 Office 365 中隔離電子郵件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-162">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

- <span data-ttu-id="1b6de-163">**篩選為垃圾郵件**：已將郵件識別為垃圾郵件，而且已拒絕或封鎖該郵件 (未隔離)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-163">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="1b6de-164">**正在取得狀態**：Office 365 最近已收到郵件，但還沒有其他狀態資料。</span><span class="sxs-lookup"><span data-stu-id="1b6de-164">**Getting status:** The message was recently received by Office 365, but no other status data is yet available.</span></span> <span data-ttu-id="1b6de-165">請在幾分鐘後再回來查看。</span><span class="sxs-lookup"><span data-stu-id="1b6de-165">Check back in a few minutes.</span></span>

<span data-ttu-id="1b6de-166">**注意**：只有小於 10 天的搜尋，才能使用 [擱置]\*\*\*\*、[已隔離]\*\*\*\* 和 [篩選為垃圾郵件]\*\*\*\* 這些值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-166">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="1b6de-167">此外，實際和報告的傳遞狀態之間可能會有 5 到 10 分鐘的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b6de-167">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="1b6de-168">郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="1b6de-168">Message Id</span></span>

<span data-ttu-id="1b6de-169">這是網際網路郵件識別碼 (也稱為「用戶端識別碼」)，可在郵件標頭的 [郵件識別碼:]\*\*\*\* 標頭欄位中找到。</span><span class="sxs-lookup"><span data-stu-id="1b6de-169">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="1b6de-170">使用者可將此值提供給您，以便您調查特定郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-170">Users can provide you with this information in order to investigate specific messages.</span></span>

<span data-ttu-id="1b6de-171">此值是郵件存留時間的常數。</span><span class="sxs-lookup"><span data-stu-id="1b6de-171">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="1b6de-172">針對在 Office 365 或 Exchange 中建立的郵件，此值的格式為 `<GUID@ServerFQDN>`，包括角括號 (\< \>)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-172">For messages created in Exchange, the value is in the format  `<GUID@ServerFQDN>`, including the angle brackets ( \< \>).</span></span> <span data-ttu-id="1b6de-173">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="1b6de-173">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="1b6de-174">其他郵件系統可能會使用不同的語法或值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-174">Other messaging systems may use different syntax or values.</span></span> <span data-ttu-id="1b6de-175">此值應為唯一的狀態，但並非所有電子郵件系統都會嚴格遵循此要求。</span><span class="sxs-lookup"><span data-stu-id="1b6de-175">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="1b6de-176">如果來自外部來源的內送郵件的 [郵件識別碼:]\*\*\*\* 標頭欄位不存在或空白，則會指派任意值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-176">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="1b6de-177">當您使用 [郵件識別碼:]\*\*\*\* 來篩選結果時，請務必包含完整的字串，包括任何角括號。</span><span class="sxs-lookup"><span data-stu-id="1b6de-177">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="1b6de-178">方向</span><span class="sxs-lookup"><span data-stu-id="1b6de-178">Direction</span></span>

<span data-ttu-id="1b6de-179">您可以將預設值 [全部]\*\*\*\* 保留為選取狀態，或者也可以選取 [內送]\*\*\*\* (傳送給貴組織中收件者的郵件) 或 [外寄]\*\*\*\* (貴組織中使用者所傳送的郵件) 來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="1b6de-179">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="1b6de-180">原始用戶端 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1b6de-180">Original client IP address</span></span>

<span data-ttu-id="1b6de-181">您可以依據用戶端 IP 位址篩選結果，來調查傳送大量垃圾郵件或惡意程式碼，所以遭到駭客入侵的電腦。</span><span class="sxs-lookup"><span data-stu-id="1b6de-181">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="1b6de-182">雖然郵件看起來可能像是來自多個寄件者，真實的情況有可能是來自產生所有這些郵件的同一部電腦。</span><span class="sxs-lookup"><span data-stu-id="1b6de-182">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="1b6de-183">**附註**：用戶端 IP 位址資訊只有在 10 天內可供使用，而且只能在 [增強摘要]\*\*\*\* 或 [延伸]\*\*\*\* 報告中取得 (可下載的 CSV 檔案)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-183">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="1b6de-184">選擇報告類型</span><span class="sxs-lookup"><span data-stu-id="1b6de-184">Choose report type</span></span>

<span data-ttu-id="1b6de-185">提供下列報告類型：</span><span class="sxs-lookup"><span data-stu-id="1b6de-185">The available traffic types are:</span></span>

- <span data-ttu-id="1b6de-186">**摘要**：適用於時間範圍小於 10 天，且不需要任何額外篩選選項的情況。</span><span class="sxs-lookup"><span data-stu-id="1b6de-186">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="1b6de-187">幾乎可在按一下 [搜尋]\*\*\*\* 後立即取得結果。</span><span class="sxs-lookup"><span data-stu-id="1b6de-187">The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="1b6de-188">**增強摘要**或**延伸**：這些報告僅以可下載的 CSV 檔案形式提供，而且需要下列一或多個篩選選項 (無論時間範圍為何)：[依據這些人]\*\*\*\*、[給這些人]\*\*\*\* 或 [郵件識別碼]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1b6de-188">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="1b6de-189">您可以將萬用字元用於寄件者或收件者 (例如，\*@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-189">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="1b6de-190">**附註**：</span><span class="sxs-lookup"><span data-stu-id="1b6de-190">**Notes**:</span></span>

- <span data-ttu-id="1b6de-191">系統會使用封存的郵件追蹤資料來準備 [增強摘要] 和 [延伸] 報告，而且最多可能需要數小時的時間，才能下載您的報告。</span><span class="sxs-lookup"><span data-stu-id="1b6de-191">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="1b6de-192">根據有多少個其他系統管理員也已同時提交報告要求而定，您可能也會在系統開始處理您的佇列要求前察覺到延遲的情形。</span><span class="sxs-lookup"><span data-stu-id="1b6de-192">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="1b6de-193">雖然您可以選取任何日期/時間範圍的 [增強摘要] 或 [延伸] 報告，通常將還無法取得這兩種報告類型過去四個小時的封存資料。</span><span class="sxs-lookup"><span data-stu-id="1b6de-193">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="1b6de-194">當您按一下 [下一步]\*\*\*\* 時，會呈現列出您已選取的篩選選項的摘要頁面、唯一 (可編輯) 的報告標題，以及在郵件追蹤完成時接收通知的電子郵件地址 (也可編輯，而且必須位於貴組織的其中一個可接受的網域中)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-194">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="1b6de-195">按一下 [準備報告]\*\*\*\* 來提交郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="1b6de-195">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="1b6de-196">在主要的 [郵件追蹤]\*\*\*\* 頁面上，您可以在 [可下載的報告]\*\*\*\* 區段中查看報告狀態。</span><span class="sxs-lookup"><span data-stu-id="1b6de-196">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="1b6de-197">如需有關各種不同報告類型中傳回資訊的詳細資訊，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="1b6de-197">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="1b6de-198">訊息追蹤結果</span><span class="sxs-lookup"><span data-stu-id="1b6de-198">Message trace results</span></span>

<span data-ttu-id="1b6de-199">不同的報告類型會傳回不同程度的資訊。</span><span class="sxs-lookup"><span data-stu-id="1b6de-199">The different report types return different levels of information.</span></span> <span data-ttu-id="1b6de-200">下列各節將說明各種不同報告中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="1b6de-200">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="1b6de-201">摘要報告輸出</span><span class="sxs-lookup"><span data-stu-id="1b6de-201">Summary report output</span></span>

<span data-ttu-id="1b6de-202">執行郵件追蹤之後，將會列出結果，並依遞減日期/時間進行排序 (先列出最近的項目)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-202">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![安全性與合規性中心的郵件追蹤摘要報告結果](../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="1b6de-204">摘要報告包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1b6de-204">The activity report contains the following information.</span></span>

- <span data-ttu-id="1b6de-205">**日期**：服務接收到郵件的日期和時間 (使用設定的 UTC 時區)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-205">**Date** The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="1b6de-206">**寄件者**：寄件者的電子郵件地址 (*別名*@*網域*)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-206">**Sender** The email address of the sender in the form  *alias*@*domain*  .</span></span>

- <span data-ttu-id="1b6de-207">**收件者**：收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-207">**Recipient** The email address of the recipient or recipients.</span></span> <span data-ttu-id="1b6de-208">針對傳送給多個收件者的郵件，每個收件者各有一行。</span><span class="sxs-lookup"><span data-stu-id="1b6de-208">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="1b6de-209">如果收件者是通訊群組、動態通訊群組或具備郵件功能的安全性群組，群組將會是第一個收件者，然後每個群組成員會列在個別的行中。</span><span class="sxs-lookup"><span data-stu-id="1b6de-209">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="1b6de-210">**主旨**：郵件的 [主旨：]\*\*\*\* 欄位的前 256 個字元。</span><span class="sxs-lookup"><span data-stu-id="1b6de-210">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="1b6de-211">**狀態**：這些值在[＜傳遞狀態＞](#delivery-status)一節中有相關說明。</span><span class="sxs-lookup"><span data-stu-id="1b6de-211">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="1b6de-212">根據預設，會載入前 250 筆結果，而且可供使用。</span><span class="sxs-lookup"><span data-stu-id="1b6de-212">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="1b6de-213">當您向下捲動時，在載入下一批結果時有稍微停頓的情形。</span><span class="sxs-lookup"><span data-stu-id="1b6de-213">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="1b6de-214">您可以按一下 [全部載入]\*\*\*\* 來載入所有結果 (最多 10,000 筆)，而不使用捲動的方式。</span><span class="sxs-lookup"><span data-stu-id="1b6de-214">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="1b6de-215">您可以按一下欄標頭，依該欄中的值以遞增或遞減順序排序結果。</span><span class="sxs-lookup"><span data-stu-id="1b6de-215">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="1b6de-216">您可以按一下 [篩選結果]\*\*\*\* 來依一或多個欄篩選結果。</span><span class="sxs-lookup"><span data-stu-id="1b6de-216">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="1b6de-217">您可以按一下 [匯出結果]\*\*\*\*，然後選取 [匯出所有結果]\*\*\*\*、[匯出載入的結果]\*\*\*\* 或 [匯出選取項目]\*\*\*\*，以在選取一或多列後匯出結果。</span><span class="sxs-lookup"><span data-stu-id="1b6de-217">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="1b6de-218">尋找此郵件的相關記錄</span><span class="sxs-lookup"><span data-stu-id="1b6de-218">Find related records for this message</span></span>

<span data-ttu-id="1b6de-219">相關郵件記錄是擁有相同 [郵件識別碼] 的記錄。</span><span class="sxs-lookup"><span data-stu-id="1b6de-219">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="1b6de-220">請記得，甚至兩個人之間所傳送的單一郵件都會產生多筆記錄。</span><span class="sxs-lookup"><span data-stu-id="1b6de-220">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="1b6de-221">在郵件受到通訊群組展開、轉寄、郵件流程規則 (也稱為傳輸規則) 等因素影響時，郵件數目也會增加。</span><span class="sxs-lookup"><span data-stu-id="1b6de-221">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="1b6de-222">選取某一列的核取方塊之後，您可以按一下出現的 [尋找相關內容]\*\*\*\* 按鈕，或選取 [其他選項]\*\*\*\* ![更多](../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> [尋找此郵件的相關記錄]\*\*\*\*，以尋找郵件的相關記錄。</span><span class="sxs-lookup"><span data-stu-id="1b6de-222">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="1b6de-223">如需有關郵件識別碼的詳細資訊，請參閱本主題先前所述的＜郵件識別碼＞一節。</span><span class="sxs-lookup"><span data-stu-id="1b6de-223">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="1b6de-224">訊息追蹤詳細資料</span><span class="sxs-lookup"><span data-stu-id="1b6de-224">Message trace details</span></span>

<span data-ttu-id="1b6de-225">在摘要報告輸出中，您可以使用下列任一方法檢視郵件的相關詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1b6de-225">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="1b6de-226">選取列 (按一下列中的任何位置，除了核取方塊以外)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-226">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="1b6de-227">選取列的核取方塊，然後按一下 [其他選項]\*\*\*\* ![更多](../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> [檢視郵件詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1b6de-227">Select the row's check box and click **More options** ![More](../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![在安全性與合規性中心的郵件追蹤摘要報告結果資料列上按兩下後的詳細資料](../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="1b6de-229">郵件追蹤詳細資料包含摘要報告中未呈現的下列額外資訊：</span><span class="sxs-lookup"><span data-stu-id="1b6de-229">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="1b6de-230">**郵件事件**：此區段包含多種分類，可協助針對服務在郵件上執行的動作進行分類。</span><span class="sxs-lookup"><span data-stu-id="1b6de-230">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="1b6de-231">以下是您可能會遇到的**某些更有趣的事件**：</span><span class="sxs-lookup"><span data-stu-id="1b6de-231">**Some of the more interesting events** that you might encounter are:</span></span>

  - <span data-ttu-id="1b6de-232">**接收**：服務收到郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-232">**RECEIVE** The message was received by the service.</span></span>

  - <span data-ttu-id="1b6de-233">**傳送**：服務寄出的郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-233">**SEND** The message was sent by the service.</span></span>

  - <span data-ttu-id="1b6de-234">**失敗**：無法傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-234">**FAIL** The message failed to be delivered.</span></span>

  - <span data-ttu-id="1b6de-235">**傳遞**：郵件已傳遞到信箱。</span><span class="sxs-lookup"><span data-stu-id="1b6de-235">**DELIVER** The message was delivered to a mailbox.</span></span>

  - <span data-ttu-id="1b6de-236">**展開**：郵件已傳送到展開的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="1b6de-236">**EXPAND** The message was sent to a distribution group that was expanded.</span></span>

  - <span data-ttu-id="1b6de-237">**轉換**：因為內容轉換、郵件收件者限制或代理程式的緣故，收件者已移至傳遞路徑分為兩條的郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-237">**TRANSFER** Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

  - <span data-ttu-id="1b6de-238">**延遲**：郵件傳遞已延遲，且稍後可能再試。</span><span class="sxs-lookup"><span data-stu-id="1b6de-238">The message delivery was postponed and may be re-attempted later.</span></span>

  - <span data-ttu-id="1b6de-239">**已解析**：根據 Active Directory 查閱，已將郵件重新導向至新的收件者地址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-239">**RESOLVED** The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="1b6de-240">發生此情況時，原始收件者地址會伴隨著郵件的最終傳遞狀態，出現在郵件追蹤裡的另一列。</span><span class="sxs-lookup"><span data-stu-id="1b6de-240">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

  <span data-ttu-id="1b6de-241">附註：</span><span class="sxs-lookup"><span data-stu-id="1b6de-241">Notes:</span></span>

  - <span data-ttu-id="1b6de-242">一封已成功傳遞的普通郵件都會在郵件追蹤中產生多個 [事件]\*\*\*\* 項目。</span><span class="sxs-lookup"><span data-stu-id="1b6de-242">An uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

  - <span data-ttu-id="1b6de-243">這份清單不應詳盡。</span><span class="sxs-lookup"><span data-stu-id="1b6de-243">This list is not meant to be exhaustive.</span></span> <span data-ttu-id="1b6de-244">如需更多事件的說明，請參閱[郵件追蹤記錄中事件種類](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-244">For descriptions of more events, see [Event types in the message tracking log](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log).</span></span> <span data-ttu-id="1b6de-245">請注意，此連結是 Exchange Server (內部部署 Exchange) 主題。</span><span class="sxs-lookup"><span data-stu-id="1b6de-245">Note that this link is an Exchange Server (on-premises Exchange) topic.</span></span>

- <span data-ttu-id="1b6de-246">**其他資訊**：此區段包含下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1b6de-246">**More information**: This section contains the following details:</span></span>

  - <span data-ttu-id="1b6de-247">**郵件識別碼**：此值在本主題先前所述的[郵件識別碼](#message-id)一節中有相關說明。</span><span class="sxs-lookup"><span data-stu-id="1b6de-247">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="1b6de-248">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="1b6de-248">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

  - <span data-ttu-id="1b6de-249">**郵件大小**</span><span class="sxs-lookup"><span data-stu-id="1b6de-249">**Message size**</span></span>

  - <span data-ttu-id="1b6de-250">**來源 IP**：傳送郵件的電腦 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-250">**From IP** The IP address of the computer that sent the message.</span></span> <span data-ttu-id="1b6de-251">對於從 Exchange Online 傳送的外寄郵件，此值為空白。</span><span class="sxs-lookup"><span data-stu-id="1b6de-251">For outbound messages sent from Exchange Online, this value is blank.</span></span>

  - <span data-ttu-id="1b6de-252">**目標 IP**：服務嘗試傳遞郵件的目標 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-252">**To IP** The IP address or addresses to which the service attempted to deliver the message.</span></span> <span data-ttu-id="1b6de-253">如果郵件有多位收件者，則會顯示這些位址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-253">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="1b6de-254">對於傳送至 Exchange Online 的輸入郵件，此值為空白。</span><span class="sxs-lookup"><span data-stu-id="1b6de-254">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="1b6de-255">增強摘要報告</span><span class="sxs-lookup"><span data-stu-id="1b6de-255">Enhanced summary reports</span></span>

<span data-ttu-id="1b6de-256">您可以在訊息追蹤開頭的 [可下載的報告]\*\*\*\* 區段中取得可用 (已完成) 的 [增強摘要] 報告。</span><span class="sxs-lookup"><span data-stu-id="1b6de-256">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="1b6de-257">報告提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1b6de-257">The following information is available in the report:</span></span>

- <span data-ttu-id="1b6de-258">**origin_timestamp**<sup>\*</sup>：服務一開始接收到郵件的日期和時間 (使用設定的 UTC 時區)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-258">**origin_timestamp** The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="1b6de-259">**sender_address**：寄件者的電子郵件地址 (*別名*@*網域*)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-259">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="1b6de-260">**Recipient_status**：將郵件傳遞至收件者的狀態。</span><span class="sxs-lookup"><span data-stu-id="1b6de-260">**Recipient_status** The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="1b6de-261">如果郵件已傳送至多個收件者，則會顯示所有收件者和其對應狀態，格式為：\<*電子郵件地址*\>##\<*狀態*\>。</span><span class="sxs-lookup"><span data-stu-id="1b6de-261">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status against each, in the format: \<  *email address*  \>##\<  *status*  \>.</span></span> <span data-ttu-id="1b6de-262">例如：</span><span class="sxs-lookup"><span data-stu-id="1b6de-262">For example:</span></span>

  - <span data-ttu-id="1b6de-263">**##接收、傳送**表示郵件已由服務接收，而且已傳送到預定的目的地。</span><span class="sxs-lookup"><span data-stu-id="1b6de-263">**##Receive, Send** means that the message was received by the service and sent to the intended destination.</span></span>

  - <span data-ttu-id="1b6de-264">**##接收、失敗**表示郵件已由服務接收，但無法傳遞到預定的目的地。</span><span class="sxs-lookup"><span data-stu-id="1b6de-264">**##Receive, Fail** means that the message was received by the service but failed to be delivered to the intended destination.</span></span>

  - <span data-ttu-id="1b6de-265">**##接收、傳遞**表示郵件已由服務接收，而且已傳遞到收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="1b6de-265">**##Receive, Deliver** means that the message was received by the service and delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="1b6de-266">**message_subject**：郵件的 [主旨]\*\*\*\* 欄位的前 256 個字元。</span><span class="sxs-lookup"><span data-stu-id="1b6de-266">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="1b6de-267">**total_bytes**：郵件大小 (以位元組為單位)，包括附件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-267">**total_bytes** The size of the message, including attachments, in bytes.</span></span>

- <span data-ttu-id="1b6de-268">**message_id**：此值在本主題先前所述的[郵件識別碼](#message-id)一節中有相關說明。</span><span class="sxs-lookup"><span data-stu-id="1b6de-268">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="1b6de-269">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="1b6de-269">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="1b6de-270">**network_message_id**：唯一的郵件識別碼值，會持續存在於郵件可能因為複本發送或通訊群組展開等原因而產生的所有複本上。</span><span class="sxs-lookup"><span data-stu-id="1b6de-270">**network_message_id** This is a unique message ID value that persists across copies of the message that may be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="1b6de-271">例如，此值可能為 `1341ac7b13fb42ab4d4408cf7f55890f`。</span><span class="sxs-lookup"><span data-stu-id="1b6de-271">An example value is  `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="1b6de-272">**original_client_ip**：寄件者的用戶端 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-272">**original_client_ip** The IP address of the sender's client.</span></span>

- <span data-ttu-id="1b6de-273">**directionality**：表示郵件是內送 (1) 到您的組織，或由您的組織外寄 (2)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-273">**directionality** This field denotes whether the message was sent inbound (1) to your organization or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="1b6de-274">**connector_id**：來源或目的地連接器的名稱。</span><span class="sxs-lookup"><span data-stu-id="1b6de-274">**connector_id** The name of the source or destination Send connector or Receive connector.</span></span> <span data-ttu-id="1b6de-275">如需 Exchange Online 中連接器的詳細資訊，請參閱[使用 Office 365 中的連接器設定郵件流程](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-275">For more information about connectors, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="1b6de-276">**delivery_priority**<sup>\*</sup>：傳送優先順序是否為 [高]\*\*\*\*、[低]\*\*\*\* 或 [標準]\*\*\*\* 的郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-276">delivery_priority Denotes whether the message was sent with High, Low, or Normal priority.</span></span>

<span data-ttu-id="1b6de-277"><sup>\*</sup>只有 [增強摘要] 報告才會提供這些屬性。</span><span class="sxs-lookup"><span data-stu-id="1b6de-277"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="1b6de-278">[延伸] 報告</span><span class="sxs-lookup"><span data-stu-id="1b6de-278">Extended reports</span></span>

<span data-ttu-id="1b6de-279">您可以在郵件追蹤開頭的 [可下載的報告]\*\*\*\* 區段中取得可用 (已完成) 的 [延伸] 報告。</span><span class="sxs-lookup"><span data-stu-id="1b6de-279">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="1b6de-280">幾乎所有來自 [增強摘要] 報告的資訊都可在 [延伸] 報告中取得 (除了 **origin_timestamp** 和 **delivery_priority** 以外)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-280">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="1b6de-281">下列額外資訊只有在 [延伸] 報告中才能取得：</span><span class="sxs-lookup"><span data-stu-id="1b6de-281">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="1b6de-282">**client_ip**：已提交郵件之電子郵件伺服器或郵件用戶端的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-282">The IPv4 or IPv6 address of the messaging server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="1b6de-283">**client_hostname**：已提交郵件之電子郵件伺服器或郵件用戶端的主機名稱或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1b6de-283">The host name or FQDN of the messaging server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="1b6de-284">**server_ip**：來源或目的地伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-284">The IPv4 or IPv6 address of the source or destination Exchange server.</span></span>

- <span data-ttu-id="1b6de-285">**server_hostname**：目的地伺服器的主機名稱或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1b6de-285">The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="1b6de-286">**source_context**：與 **source** 欄位相關聯的額外資訊。</span><span class="sxs-lookup"><span data-stu-id="1b6de-286">Extra information associated with the **source** field.</span></span> <span data-ttu-id="1b6de-287">例如：</span><span class="sxs-lookup"><span data-stu-id="1b6de-287">For example:</span></span>

  - `Protocol Filter Agent`

  - `3489061114359050000`

- <span data-ttu-id="1b6de-288">**source**：負責事件的 Exchange Online 元件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-288">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="1b6de-289">例如：</span><span class="sxs-lookup"><span data-stu-id="1b6de-289">For example:</span></span>

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- <span data-ttu-id="1b6de-290">**event_id**：這些對應到[尋找此郵件的相關記錄](#find-related-records-for-this-message)一節中所說明的 [郵件事件]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-290">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="1b6de-291">**internal_message_id**：目前正在處理郵件之 Exchange Online 伺服器所指派的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="1b6de-291">A message identifier assigned by the Exchange server currently processing the message.</span></span>

- <span data-ttu-id="1b6de-292">**recipient_address**：郵件收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-292">The email addresses of the message's recipients.</span></span> <span data-ttu-id="1b6de-293">多個電子郵件地址會以分號字元 (;) 隔開。</span><span class="sxs-lookup"><span data-stu-id="1b6de-293">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="1b6de-294">**recipient_count**：郵件中的收件者總人數。</span><span class="sxs-lookup"><span data-stu-id="1b6de-294">The number of recipients in the message.</span></span>

- <span data-ttu-id="1b6de-295">**related_recipient_address**：與 `EXPAND`、`REDIRECT` 和 `RESOLVE` 事件搭配使用，顯示與郵件相關聯的其他收件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-295">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="1b6de-296">**reference**：此欄位包含特定事件類型的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="1b6de-296">This field contains additional information for specific types of events.</span></span> <span data-ttu-id="1b6de-297">例如：</span><span class="sxs-lookup"><span data-stu-id="1b6de-297">For example:</span></span>

  - <span data-ttu-id="1b6de-298">**DSN**：包含報告連結，也就是在此事件後續產生 DSN 的情況下，相關聯之傳遞狀態通知 (也稱為 DSN、未傳遞回報、NDR 或退回的郵件) 的 **message_id** 值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-298">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="1b6de-299">如果這是 DSN 郵件，此欄位會包含產生 DSN 之原始郵件的 **message_id** 值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-299">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

  - <span data-ttu-id="1b6de-300">**EXPAND**：包含相關郵件的 **related_recipient_address** 值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-300">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

  - <span data-ttu-id="1b6de-301">**RECEIVE**：如果郵件是由其他程序 (例如 [收件匣] 規則) 所產生，可能會包含相關郵件的 **message_id** 值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-301">**RECEIVE** The Reference field may contain the **Message-Id** value of the related message if the message was generated by other processes, for example, journaling or Inbox rules.</span></span>

  - <span data-ttu-id="1b6de-302">**SEND**：包含任何 DSN 郵件的 **internal_message_id** 值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-302">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

  - <span data-ttu-id="1b6de-303">**TRANSFER**：包含分支之郵件的 **internal_message_id** 值 (例如，由於內容轉換、郵件收件者限制或代理程式)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-303">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

  - <span data-ttu-id="1b6de-304">**MAILBOXRULE**：包含導致 [收件匣] 規則產生外寄郵件之內送郵件的 **internal_message_id** 值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-304">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

    <span data-ttu-id="1b6de-305">對於其他類型的事件，此欄位通常為空白。</span><span class="sxs-lookup"><span data-stu-id="1b6de-305">For other types of events, the Reference field is usually blank.</span></span>

- <span data-ttu-id="1b6de-306">**return_path**：傳送郵件的 **MAIL FROM**命令所指定的傳回電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-306">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="1b6de-307">雖然此欄位絕對不會是空白，但會以 `<>` 來表示 Null 寄件者地址值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-307">Although this field is never empty, it can have the null sender address value represented as  `<>`.</span></span>

- <span data-ttu-id="1b6de-308">**message_info**：郵件的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1b6de-308">Additional information about the message.</span></span> <span data-ttu-id="1b6de-309">例如：</span><span class="sxs-lookup"><span data-stu-id="1b6de-309">For example:</span></span>

  - <span data-ttu-id="1b6de-310">`DELIVER` 與 `SEND` 事件的郵件原始日期時間 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-310">The message origination UTC date-time for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="1b6de-311">原始日期時間是指郵件最初進入 Exchange Online 組織的時間。</span><span class="sxs-lookup"><span data-stu-id="1b6de-311">The origination date-time is the time when the message first entered the Exchange organization.</span></span> <span data-ttu-id="1b6de-312">以 ISO 8601 日期時間格式表示 UTC 日期時間：`yyyy-mm-ddThh:mm:ss.fffZ`，其中 `yyyy` = 年、`mm` = 月、`dd` = 日，`T` 表示時間元件的開頭，`hh` = 時、`mm` = 分、`ss` = 秒、`fff` = 秒的分數，以及另外一個表示 UTC 的方法 `Z` 代表 `Zulu`。</span><span class="sxs-lookup"><span data-stu-id="1b6de-312">The UTC date-time is represented in the ISO 8601 date-time format: yyyy-mm-ddThh:mm:ss.fffZ, where yyyy = year, mm = month, dd = day, T indicates the beginning of  the time component, hh = hour, mm = minute, ss = second, fff = fractions of a second, and Z signifies Zulu, which is another way to denote UTC.</span></span>

  - <span data-ttu-id="1b6de-313">驗證錯誤。</span><span class="sxs-lookup"><span data-stu-id="1b6de-313">Authentication errors.</span></span> <span data-ttu-id="1b6de-314">例如，您可能會看見值 `11a`，以及發生驗證錯誤時所使用的驗證類型。</span><span class="sxs-lookup"><span data-stu-id="1b6de-314">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="1b6de-315">**tenant_id**：代表 Exchange Online 組織的 GUID 值 (例如，`39238e87-b5ab-4ef6-a559-af54c6b07b42`)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-315">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="1b6de-316">**original_server_ip**：原始伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b6de-316">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="1b6de-317">**custom_data**：包含特定事件類型的相關資料。</span><span class="sxs-lookup"><span data-stu-id="1b6de-317">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="1b6de-318">如需詳細資訊，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="1b6de-318">For more information, see the following sections:</span></span>

#### <a name="custom_data-values"></a><span data-ttu-id="1b6de-319">custom_data 值</span><span class="sxs-lookup"><span data-stu-id="1b6de-319">custom_data values</span></span>

<span data-ttu-id="1b6de-320">各種 Exchange Online 代理程式會使用 `AGENTINFO` 事件的 **custom_data** 欄位來記錄郵件處理詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1b6de-320">The custom_data field in an AGENTINFO event is used by a variety of different agents to log details from the agent's processing of the message.</span></span> <span data-ttu-id="1b6de-321">下列各節說明某些更有趣的代理程式。</span><span class="sxs-lookup"><span data-stu-id="1b6de-321">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="1b6de-322">垃圾郵件篩選器代理程式</span><span class="sxs-lookup"><span data-stu-id="1b6de-322">Spam filter agent</span></span>

<span data-ttu-id="1b6de-323">以 `S:SFA` 做為開頭的 **custom_data** 值是來自垃圾郵件篩選器代理程式。</span><span class="sxs-lookup"><span data-stu-id="1b6de-323">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="1b6de-324">下表說明重要的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1b6de-324">The key differences are described in the following table:</span></span>

|<span data-ttu-id="1b6de-325">**值**</span><span class="sxs-lookup"><span data-stu-id="1b6de-325">**Value**</span></span>|<span data-ttu-id="1b6de-326">**描述**</span><span class="sxs-lookup"><span data-stu-id="1b6de-326">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="1b6de-327">郵件標記為非垃圾郵件，並傳送給預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="1b6de-327">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="1b6de-328">內容篩選已將郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-328">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="1b6de-329">已略過篩選，且郵件來自封鎖的寄件者，所以封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-329">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="1b6de-p153">郵件先被標示為垃圾郵件，再由內容篩選器進行處理。這包括與傳輸規則相符而被自動標示為垃圾郵件，並略過所有其他篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-p153">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="1b6de-332">如需不同 SCL 值和其意義的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-332">For more information about the different SCL values and what they mean, see [Spam Confidence Levels](spam-confidence-levels.md).</span></span>|
|`PCL=<number>`|<span data-ttu-id="1b6de-333">郵件的網路釣魚信賴等級 (PCL) 值。</span><span class="sxs-lookup"><span data-stu-id="1b6de-333">The Phishing Confidence Level (PCL) value of the message.</span></span> <span data-ttu-id="1b6de-334">這些值的解譯方式與[垃圾郵件信賴等級](spam-confidence-levels.md)中所記載的 SCL 值相同。</span><span class="sxs-lookup"><span data-stu-id="1b6de-334">These can be interpreted the same way as the SCL values documented in [Spam Confidence Levels](spam-confidence-levels.md).</span></span>|
|`DI=SB`|<span data-ttu-id="1b6de-335">已封鎖郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="1b6de-335">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="1b6de-336">已隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-336">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="1b6de-337">已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-337">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="1b6de-338">郵件被傳送到收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1b6de-338">The message was sent to the recipient’s Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="1b6de-339">已透過較高風險傳遞集區路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-339">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="1b6de-340">如需詳細資訊，請參閱[外寄郵件的較高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-340">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>|
|`DI=SO`|<span data-ttu-id="1b6de-341">已透過標準輸出傳遞集區路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-341">The message was routed through the normal outbound delivery pool.</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="1b6de-342">這表示已符合垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="1b6de-342">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="1b6de-343">因為 IP 位址指定於連線篩選的 [IP 允許] 清單中，所以已透過垃圾郵件篩選允許郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-343">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="1b6de-344">連線電子郵件伺服器的 HELO 或 EHLO 字串。</span><span class="sxs-lookup"><span data-stu-id="1b6de-344">The HELO or EHLO string of the connecting mail server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="1b6de-345">傳送 IP 位址 (也稱為反向 DNS 位址) 的 PTR 記錄。</span><span class="sxs-lookup"><span data-stu-id="1b6de-345">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="1b6de-346">篩選出垃圾郵件之郵件的 **custom_data** 範例值，例如：</span><span class="sxs-lookup"><span data-stu-id="1b6de-346">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="1b6de-347">惡意程式碼篩選代理程式</span><span class="sxs-lookup"><span data-stu-id="1b6de-347">Malware filter agent</span></span>

<span data-ttu-id="1b6de-348">以 `S:AMA` 做為開頭的 **custom_data** 值是來自惡意程式碼篩選器代理程式。</span><span class="sxs-lookup"><span data-stu-id="1b6de-348">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="1b6de-349">下表說明重要的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1b6de-349">The key differences are described in the following table:</span></span>

|<span data-ttu-id="1b6de-350">**值**</span><span class="sxs-lookup"><span data-stu-id="1b6de-350">**Value**</span></span>|<span data-ttu-id="1b6de-351">**描述**</span><span class="sxs-lookup"><span data-stu-id="1b6de-351">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b6de-352">`AMA=SUM|v=1|` 或 `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="1b6de-352">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="1b6de-353">郵件已判定為包含惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="1b6de-353">The message was determined to contain malware.</span></span> <span data-ttu-id="1b6de-354">`SUM` 表示任意數目的引擎可能已偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="1b6de-354">SUM denotes that the malware could’ve been detected by any number of engines.</span></span> <span data-ttu-id="1b6de-355">`EV` 表示特定引擎偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="1b6de-355">EV denotes that the malware was detected by a specific engine.</span></span> <span data-ttu-id="1b6de-356">引擎偵測到惡意程式碼時，這會觸發後續動作。</span><span class="sxs-lookup"><span data-stu-id="1b6de-356">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="1b6de-357">已取代郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-357">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="1b6de-358">已略過郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-358">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="1b6de-359">已延遲郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-359">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="1b6de-360">已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-360">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="1b6de-361">已略過郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-361">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="1b6de-362">已略過郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-362">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="1b6de-363">已拒絕郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-363">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="1b6de-364">已拒絕郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-364">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="1b6de-365">已封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="1b6de-365">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="1b6de-366">偵測到之惡意程式碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="1b6de-366">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="1b6de-367">含有惡意程式碼之檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="1b6de-367">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="1b6de-368">內含惡意程式碼之郵件的 **custom_data** 範例值看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="1b6de-368">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="1b6de-369">傳輸規則代理程式</span><span class="sxs-lookup"><span data-stu-id="1b6de-369">Transport Rule agent</span></span>

<span data-ttu-id="1b6de-370">以 `S:TRA` 作為開頭的 **custom_data** 值是來自郵件流程規則 (也稱為傳輸規則) 的傳輸規則代理程式。</span><span class="sxs-lookup"><span data-stu-id="1b6de-370">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="1b6de-371">下表說明重要的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1b6de-371">The key differences are described in the following table:</span></span>

|<span data-ttu-id="1b6de-372">**值**</span><span class="sxs-lookup"><span data-stu-id="1b6de-372">**Value**</span></span>|<span data-ttu-id="1b6de-373">**描述**</span><span class="sxs-lookup"><span data-stu-id="1b6de-373">**Description**</span></span>|
|:-----|:-----|
|`ETR|ruleId=<guid>`|<span data-ttu-id="1b6de-374">已符合的規則 ID。</span><span class="sxs-lookup"><span data-stu-id="1b6de-374">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="1b6de-375">規則相符時的日期和時間 (以 UTC 表示)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-375">The date and time (in UTC) when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="1b6de-376">已套用的動作。</span><span class="sxs-lookup"><span data-stu-id="1b6de-376">The action that was applied.</span></span> <span data-ttu-id="1b6de-377">如需可用動作的清單，請參閱 [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="1b6de-377">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="1b6de-378">規則的模式。</span><span class="sxs-lookup"><span data-stu-id="1b6de-378">The mode of the rule.</span></span> <span data-ttu-id="1b6de-379">有效值為：</span><span class="sxs-lookup"><span data-stu-id="1b6de-379">Valid values are:</span></span> <br/><span data-ttu-id="1b6de-380">• **強制**：將強制執行規則上的所有動作。</span><span class="sxs-lookup"><span data-stu-id="1b6de-380">**Enforce** All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="1b6de-381">• **搭配原則提示來測試**：將會傳送任何原則提示動作，但將不會處理其他強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="1b6de-381">**Test with Policy Tips** Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="1b6de-382">• **不搭配原則提示的測試**：動作將會列在記錄檔中，但是不會以任何方法通知寄件者，而且不會處理強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="1b6de-382">**Test without Policy Tips** Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="1b6de-383">符合郵件流程規則條件之郵件的 **custom_data** 範例值看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="1b6de-383">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
