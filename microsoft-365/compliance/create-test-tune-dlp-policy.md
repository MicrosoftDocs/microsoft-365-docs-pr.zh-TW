---
title: 建立、測試及調整 DLP 原則
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: '要開始使用 DLP 原則，最簡單且最常見方式是使用 Office 365 所包含的其中一個範本。 '
ms.openlocfilehash: b13dab63514dc8658479dbd68d5a014dc7347bb8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076457"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="48c7a-103">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="48c7a-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="48c7a-104">**主體作者**</span><span class="sxs-lookup"><span data-stu-id="48c7a-104">**Principal author**</span></span> <br/>
<span data-ttu-id="48c7a-105">Paul Cunningham，Microsoft 的 MVP</span><span class="sxs-lookup"><span data-stu-id="48c7a-105">Paul Cunningham, Microsoft MVP</span></span> <br/>
[<span data-ttu-id="48c7a-106">實用 365</span><span class="sxs-lookup"><span data-stu-id="48c7a-106">Practical 365</span></span>](https://practical365.com/) <br/>
[<span data-ttu-id="48c7a-107">@Practical365</span><span class="sxs-lookup"><span data-stu-id="48c7a-107">@Practical365</span></span>](https://twitter.com/practical365)<br/>
__________________________________________________

<span data-ttu-id="48c7a-108">資料外洩防護是設計來協助您防止敏感資訊給不想要的對象 」 刻意或意外曝光的組織的 Office 365 的合規性功能。</span><span class="sxs-lookup"><span data-stu-id="48c7a-108">Data loss prevention is a compliance feature of Office 365 that is designed to help your organization prevent the intentional or accidental exposure of sensitive information to unwanted parties.</span></span> <span data-ttu-id="48c7a-109">DLP 已在 Exchange 伺服器] 及 [Exchange Online 中，其根物件，而且也適用於 SharePoint Online 和商務用 OneDrive 中。</span><span class="sxs-lookup"><span data-stu-id="48c7a-109">DLP has its roots in Exchange Server and Exchange Online, and is also applicable in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="48c7a-110">DLP 會使用若要檢查的內容，電子郵件和檔案，例如信用卡號碼敏感資訊和個人識別資訊 (PII) 要尋找的內容分析引擎。</span><span class="sxs-lookup"><span data-stu-id="48c7a-110">DLP uses a content analysis engine to examine the contents of email messages and files, looking for sensitive information such as credit card numbers and personally identifiable information (PII).</span></span> <span data-ttu-id="48c7a-111">敏感資訊通常不應該傳送電子郵件，或包含在文件，而不採取額外的步驟，例如加密的電子郵件訊息或檔案。</span><span class="sxs-lookup"><span data-stu-id="48c7a-111">Sensitive information should typically not be sent in email, or included in documents, without taking additional steps such as encrypting the email message or files.</span></span> <span data-ttu-id="48c7a-112">您可以使用 DLP 偵測敏感資訊，並採取動作，例如：</span><span class="sxs-lookup"><span data-stu-id="48c7a-112">Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="48c7a-113">記錄的事件稽核用途</span><span class="sxs-lookup"><span data-stu-id="48c7a-113">Log the event for auditing purposes</span></span>
- <span data-ttu-id="48c7a-114">顯示警告訊息至使用者傳送電子郵件或共用檔案</span><span class="sxs-lookup"><span data-stu-id="48c7a-114">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="48c7a-115">主動封鎖的電子郵件或檔案共用從發生</span><span class="sxs-lookup"><span data-stu-id="48c7a-115">Actively block the email or file sharing from taking place</span></span>

<span data-ttu-id="48c7a-116">客戶有時會關閉 DLP 因為它們不視為具有需要保護的資料類型。</span><span class="sxs-lookup"><span data-stu-id="48c7a-116">Sometimes customers dismiss DLP because they don't consider themselves to have the type of data that needs protecting.</span></span> <span data-ttu-id="48c7a-117">假設是： 的機密資料，例如醫療記錄或財務資訊，請僅存在於像醫療保健產業或執行線上商店的公司。</span><span class="sxs-lookup"><span data-stu-id="48c7a-117">The assumption is that sensitive data, such as medical records or financial information, only exists for industries like health care or for companies that run online stores.</span></span> <span data-ttu-id="48c7a-118">但是任何商業可以處理定期上的敏感資訊，即使他們不知道它。</span><span class="sxs-lookup"><span data-stu-id="48c7a-118">But any business can handle sensitive information on a regular basis, even if they don't realize it.</span></span> <span data-ttu-id="48c7a-119">試算表的員工名稱及日期是出生的為客戶的名稱和信用卡的詳細資訊的試算表為敏感。</span><span class="sxs-lookup"><span data-stu-id="48c7a-119">A spreadsheet of employee names and dates of birth is just as sensitive as a spreadsheet of customer names and credit card details.</span></span> <span data-ttu-id="48c7a-120">這種類型的資訊會浮動周圍超過您所預期，如員工安靜模式前往關於其日常工作，以為 nothing 匯出從系統的 CSV 檔案並以電子郵件傳送給其他人。</span><span class="sxs-lookup"><span data-stu-id="48c7a-120">And this type of information tends to float around more than you might expect, as employees quietly go about their day to day tasks, thinking nothing of export a CSV file from a system and emailing it to someone.</span></span> <span data-ttu-id="48c7a-121">您可能也會有大吃一驚頻率員工傳送電子郵件包含信用卡或銀行詳細資料，而不考慮方法的結果。</span><span class="sxs-lookup"><span data-stu-id="48c7a-121">You might also be surprised how often employees send emails containing credit card or banking details without considering the consequences.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="48c7a-122">如何所 DLP 偵測到機密資訊</span><span class="sxs-lookup"><span data-stu-id="48c7a-122">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="48c7a-123">識別敏感資訊規則運算式 (RegEx) 模式比對，組合與其他的指標，例如近似值與特定關鍵字]，以比對的模式。</span><span class="sxs-lookup"><span data-stu-id="48c7a-123">Sensitive information is identified by regular expression (RegEx) pattern matching, in combination with with other indicators such as the proximity of certain keywords to the matching patterns.</span></span> <span data-ttu-id="48c7a-124">例如，這是信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="48c7a-124">An example of this is credit card numbers.</span></span> <span data-ttu-id="48c7a-125">VISA 信用卡卡號有 16 位數。</span><span class="sxs-lookup"><span data-stu-id="48c7a-125">A VISA credit card number has 16 digits.</span></span> <span data-ttu-id="48c7a-126">不過，這些數字可以寫成不同的方式，例如 1111年-1111年-1111年-1111，1111年 1111年 1111年 1111，或 1111111111111111。</span><span class="sxs-lookup"><span data-stu-id="48c7a-126">However, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="48c7a-127">任何 16 位數字串不一定是信用卡號，它可能是從說明 desk 系統或硬體序號的票證數字。</span><span class="sxs-lookup"><span data-stu-id="48c7a-127">Any 16 digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware.</span></span> <span data-ttu-id="48c7a-128">若要告訴信用卡卡號和無害的 16 位數字串之間的差異，計算會是執行 （總和檢查碼） 以確認號碼符合各種信用卡品牌來自已知的模式。</span><span class="sxs-lookup"><span data-stu-id="48c7a-128">To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="48c7a-129">此外，例如 「 VISA 」 或 「 AMEX 」，以及近似值 [關鍵字]，以可能是信用卡到期日期的日期值的近似值也會被視為進行決策的資料是否是信用卡號。</span><span class="sxs-lookup"><span data-stu-id="48c7a-129">Furthermore, the proximity of keywords such as “VISA” or “AMEX”, along with the proximity to date values that might be the credit card expiry date, is also considered to make a decision about whether the data is a credit card number or not.</span></span>

<span data-ttu-id="48c7a-130">換句話說，DLP 是通常是足夠的智慧辨識電子郵件中的下列兩個敘述性文字之間的差異：</span><span class="sxs-lookup"><span data-stu-id="48c7a-130">In other words, DLP is usually smart enough to recognize the difference between these two texts in an email:</span></span>

- <span data-ttu-id="48c7a-131">「 您訂購我新的膝上型電腦。</span><span class="sxs-lookup"><span data-stu-id="48c7a-131">“Can you order me a new laptop.</span></span> <span data-ttu-id="48c7a-132">使用我 VISA 號碼 1111年-1111年-1111年-1111，到期 11/22，和傳送給我有時的估計的傳遞日期 」。</span><span class="sxs-lookup"><span data-stu-id="48c7a-132">Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it.”</span></span>
- <span data-ttu-id="48c7a-133">「 我的膝上型電腦序號是 2222年 2222年-2222年 2222年和它已購買 11/2010年上。</span><span class="sxs-lookup"><span data-stu-id="48c7a-133">“My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010.</span></span> <span data-ttu-id="48c7a-134">順便一提，我旅行 visa 核准尚未？ 」</span><span class="sxs-lookup"><span data-stu-id="48c7a-134">By the way, is my travel visa approved yet?”</span></span>

<span data-ttu-id="48c7a-135">保留書籤的良好參照會說明如何每一種資訊類型會偵測到此[敏感資訊類型的主題](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="48c7a-135">A good reference to keep bookmarked is this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="48c7a-136">要從何處開始與資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="48c7a-136">Where to start with data loss prevention</span></span>

<span data-ttu-id="48c7a-137">當資料外洩的風險不完全明顯時，很難找出其中完全您應該從開始實作 DLP。</span><span class="sxs-lookup"><span data-stu-id="48c7a-137">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP.</span></span> <span data-ttu-id="48c7a-138">幸好，DLP 原則可以在執行 「 測試模式 」，可讓您評估其效率和準確度之前您將其開啟。</span><span class="sxs-lookup"><span data-stu-id="48c7a-138">Fortunately, DLP policies can be run in “test mode”, allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="48c7a-139">管理 Exchange Online 的 DLP 原則時，可以透過 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="48c7a-139">DLP policies for Exchange Online can be managed through the Exchange admin center.</span></span> <span data-ttu-id="48c7a-140">但是，您可以設定適用於透過安全性 & 規範中心] 內的所有工作負載的 DLP 原則，因此我將使用的本文中的示範。</span><span class="sxs-lookup"><span data-stu-id="48c7a-140">But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article.</span></span> <span data-ttu-id="48c7a-141">在安全性 & 合規性中心中，您會發現 [**資料外洩防護**] 下的 DLP 原則 > **原則**。</span><span class="sxs-lookup"><span data-stu-id="48c7a-141">In the Security & Compliance Center you'll find the DLP policies under **Data loss prevention** > **Policy**.</span></span> <span data-ttu-id="48c7a-142">按一下 [**建立原則**]，以啟動]。</span><span class="sxs-lookup"><span data-stu-id="48c7a-142">Click on **Create a policy** to start.</span></span>

<span data-ttu-id="48c7a-143">Office 365 提供的[DLP 原則範本](what-the-dlp-policy-templates-include.md)可用於建立 DLP 原則的範圍。</span><span class="sxs-lookup"><span data-stu-id="48c7a-143">Office 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create DLP policies.</span></span> <span data-ttu-id="48c7a-144">例如，假設您是澳洲商務。</span><span class="sxs-lookup"><span data-stu-id="48c7a-144">Let's say that you're an Australian business.</span></span> <span data-ttu-id="48c7a-145">您可以篩選以顯示只與澳洲，相關的那些原則範本可分為金融、 醫療和健康情況及隱私權一般類別。</span><span class="sxs-lookup"><span data-stu-id="48c7a-145">You can filter the policy templates to display only those that are relevant to Australia, which fall into the general categories of Financial, Medical and Health, and Privacy.</span></span>

![國家/地區或區域中選擇選項](media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="48c7a-147">此示範而言我將會選擇澳洲個人識別資訊 (PII) 資料，包括澳洲稅務檔案號碼 (TFN) 和駕駛執照號碼資訊類型。</span><span class="sxs-lookup"><span data-stu-id="48c7a-147">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![若要選擇的原則範本的選項](media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="48c7a-149">提供您的新 DLP 原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="48c7a-149">Give your new DLP policy a name.</span></span> <span data-ttu-id="48c7a-150">預設的名稱會比對的 DLP 原則範本，但因為可以從相同的範本建立多個原則，您應選擇您自己，更具描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="48c7a-150">The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![選項來命名您的原則](media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="48c7a-152">選擇原則會套用到的位置。</span><span class="sxs-lookup"><span data-stu-id="48c7a-152">Choose the locations that the policy will apply to.</span></span> <span data-ttu-id="48c7a-153">DLP 原則可以套用至 Exchange Online、 SharePoint Online 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="48c7a-153">DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="48c7a-154">我要保留此原則的設定將套用至所有位置。</span><span class="sxs-lookup"><span data-stu-id="48c7a-154">I am going to leave this policy configured to apply to all locations.</span></span>

![若要選擇的所有位置選項](media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="48c7a-156">在第一個**原則設定**步驟只接受立即的預設值。</span><span class="sxs-lookup"><span data-stu-id="48c7a-156">At the first **Policy Settings** step just accept the defaults for now.</span></span> <span data-ttu-id="48c7a-157">有很多您可以在 DLP 原則] 中的自訂，但預設值會是不錯的起點。</span><span class="sxs-lookup"><span data-stu-id="48c7a-157">There is quite a lot of customization you can do in DLP policies, but the defaults are a fine place to start.</span></span>

![若要自訂要保護的內容類型的選項](media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="48c7a-159">按一下 [**下一步**] 之後就會看到與其他的**原則設定**] 頁面上具有更多自訂選項。</span><span class="sxs-lookup"><span data-stu-id="48c7a-159">After clicking **Next** you'll be presented with an additional **Policy Settings** page with more customization options.</span></span> <span data-ttu-id="48c7a-160">您只測試原則，以下是您可以開始進行某些調整。</span><span class="sxs-lookup"><span data-stu-id="48c7a-160">For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="48c7a-161">我已關閉的現在，這是合理的步驟，如果您只要測試內容，而且不想要尚未對使用者顯示的任何項目採取的原則提示。</span><span class="sxs-lookup"><span data-stu-id="48c7a-161">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet.</span></span> <span data-ttu-id="48c7a-162">原則提示對它們即將違反 DLP 原則的使用者顯示警告。</span><span class="sxs-lookup"><span data-stu-id="48c7a-162">Policy tips display warnings to users that they're about to violate a DLP policy.</span></span> <span data-ttu-id="48c7a-163">例如，Outlook 使用者會看到警告他們已附加的檔案包含信用卡號碼，且會導致他們的電子郵件遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="48c7a-163">For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected.</span></span> <span data-ttu-id="48c7a-164">原則提示的目標是要前些什麼停止不相容行為。</span><span class="sxs-lookup"><span data-stu-id="48c7a-164">The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="48c7a-165">我也已降低為 1，10 的執行個體數目，因此這項原則會偵測任何共用澳洲 PII 資料，不只是大量資料的共用。</span><span class="sxs-lookup"><span data-stu-id="48c7a-165">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="48c7a-166">我也已新增其他收件者的附隨報告電子郵件。</span><span class="sxs-lookup"><span data-stu-id="48c7a-166">I've also added another recipient to the incident report email.</span></span>

![其他原則設定](media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="48c7a-168">最後，已在測試模式中執行的初始此原則。</span><span class="sxs-lookup"><span data-stu-id="48c7a-168">Finally, I've configured this policy to run in test mode initially.</span></span> <span data-ttu-id="48c7a-169">請注意有也是用來停用在測試模式中的原則提示以下的選項。</span><span class="sxs-lookup"><span data-stu-id="48c7a-169">Notice there's also an option here to disable policy tips while in test mode.</span></span> <span data-ttu-id="48c7a-170">這可以讓您已在原則中啟用的原則提示，但然後決定是否要顯示或隱藏他們您在測試期間的彈性。</span><span class="sxs-lookup"><span data-stu-id="48c7a-170">This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![若要先測試原則的選項](media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="48c7a-172">在最後檢閱畫面，請按一下 [**建立**] 以完成建立原則]。</span><span class="sxs-lookup"><span data-stu-id="48c7a-172">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="48c7a-173">測試 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="48c7a-173">Test a DLP policy</span></span>

<span data-ttu-id="48c7a-174">您的新 DLP 原則會開始於大約 1 小時才會生效。</span><span class="sxs-lookup"><span data-stu-id="48c7a-174">Your new DLP policy will begin to take effect within about 1 hour.</span></span> <span data-ttu-id="48c7a-175">您可以 sit 這個並等待其觸發的一般使用者活動，或您可以嘗試觸發它自己。</span><span class="sxs-lookup"><span data-stu-id="48c7a-175">You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself.</span></span> <span data-ttu-id="48c7a-176">稍早我連結到此[敏感資訊類型的主題](what-the-sensitive-information-types-look-for.md)，可提供讓您如何觸發 DLP 相符項目資訊。</span><span class="sxs-lookup"><span data-stu-id="48c7a-176">Earlier I linked to this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="48c7a-177">做為範例，我的這篇文章所建立的 DLP 原則會偵測澳洲稅務檔案號碼 (TFN)。</span><span class="sxs-lookup"><span data-stu-id="48c7a-177">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN).</span></span> <span data-ttu-id="48c7a-178">根據文件中，相符項目根據下列準則。</span><span class="sxs-lookup"><span data-stu-id="48c7a-178">According to the documentation, the match is based on the following criteria.</span></span>

![澳洲稅務檔案編號的相關文件](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="48c7a-180">若要示範 TFN 偵測而鈍的方式，與文字 「 稅務檔案號碼 」 電子郵件和接近 9 的數字字串會帶到處透過沒有任何問題。</span><span class="sxs-lookup"><span data-stu-id="48c7a-180">To demonstrate TFN detection in a rather blunt manner, an email with the words “Tax file number” and a 9 digit string in close proximity will sail through without any issues.</span></span> <span data-ttu-id="48c7a-181">它不會觸發 DLP 原則的原因是 9 位數字串必須通過總和檢查碼表示它是有效的 TFN 而不只是無害的數字字串。</span><span class="sxs-lookup"><span data-stu-id="48c7a-181">The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![澳洲稅務檔案編號未通過總和檢查碼](media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="48c7a-183">相較之下，含有文字"稅務檔案編號 」 的電子郵件和傳遞總和檢查碼有效 TFN 會觸發該原則。</span><span class="sxs-lookup"><span data-stu-id="48c7a-183">In comparison, an email with the words “Tax file number” and a valid TFN that passes the checksum will trigger the policy.</span></span> <span data-ttu-id="48c7a-184">對於資料錄，我使用 TFN 來自中的網站，就會產生有效，但不是正版，TFNs。</span><span class="sxs-lookup"><span data-stu-id="48c7a-184">For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs.</span></span> <span data-ttu-id="48c7a-185">有類似產生[正確的但假信用卡號碼](http://www.fakecreditcardgenerator.net/)的網站。</span><span class="sxs-lookup"><span data-stu-id="48c7a-185">There are similar sites that generate [valid but fake credit card numbers](http://www.fakecreditcardgenerator.net/).</span></span> <span data-ttu-id="48c7a-186">這類網站是很有用，因為下列其中一個最常見的錯誤測試 DLP 原則時使用的假的數字不是有效，並不會通過總和檢查碼 （也就不會觸發原則）。</span><span class="sxs-lookup"><span data-stu-id="48c7a-186">Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![澳洲稅務檔案編號傳遞總和檢查碼](media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="48c7a-188">附隨報告電子郵件包含偵測到的敏感資訊類型、 偵測到多少個執行個體，並偵測信賴等級。</span><span class="sxs-lookup"><span data-stu-id="48c7a-188">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![偵測到附隨報告顯示稅務檔案編號](media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="48c7a-190">如果您在測試模式中離開您的 DLP 原則，並分析附隨報告電子郵件，您可以開始取得風格的 DLP 原則和如何有效它將會強制使用時的精確度。</span><span class="sxs-lookup"><span data-stu-id="48c7a-190">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced.</span></span> <span data-ttu-id="48c7a-191">除了附隨報告，您還可以[使用 DLP 報告](view-the-dlp-reports.md)以查看您的租用戶原則相符項目彙總的檢視。</span><span class="sxs-lookup"><span data-stu-id="48c7a-191">In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="48c7a-192">調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="48c7a-192">Tune a DLP policy</span></span>

<span data-ttu-id="48c7a-193">當您分析您的原則拜訪人次您可能想要進行某些調整，以原則的行為方式。</span><span class="sxs-lookup"><span data-stu-id="48c7a-193">As you analyze your policy hits you might want to make some adjustments to how the policies behave.</span></span> <span data-ttu-id="48c7a-194">簡單的範例中，您可能會決定電子郵件中的一個 TFN 不是 （我會認為它仍是，但這是因為示範與它讓我們移） 時發生問題，但兩個或多個執行個體是問題。</span><span class="sxs-lookup"><span data-stu-id="48c7a-194">As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem.</span></span> <span data-ttu-id="48c7a-195">多個執行個體可能風險的案例，例如員工 HR 資料庫從 CSV 匯出至外部廠商，例如外部會計服務以電子郵件傳送。</span><span class="sxs-lookup"><span data-stu-id="48c7a-195">Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service.</span></span> <span data-ttu-id="48c7a-196">必定為某些動作，您偏好偵測並封鎖。</span><span class="sxs-lookup"><span data-stu-id="48c7a-196">Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="48c7a-197">在安全性 & 合規性中心中，您可以編輯現有的原則來調整行為。</span><span class="sxs-lookup"><span data-stu-id="48c7a-197">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![若要編輯原則的選項](media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="48c7a-199">因此，只有特定的工作負載，或特定網站及帳戶，已套用原則，您可以調整的位置設定。</span><span class="sxs-lookup"><span data-stu-id="48c7a-199">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![若要選擇特定位置的選項](media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="48c7a-201">您也可以調整的原則設定，並編輯規則，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="48c7a-201">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![若要編輯規則的選項](media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="48c7a-203">編輯 DLP 原則內的規則時，您可以變更：</span><span class="sxs-lookup"><span data-stu-id="48c7a-203">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="48c7a-204">條件，包括機密資料，就會觸發規則的執行個體數目與類型。</span><span class="sxs-lookup"><span data-stu-id="48c7a-204">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="48c7a-205">動作所採取的例如限制內容的存取。</span><span class="sxs-lookup"><span data-stu-id="48c7a-205">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="48c7a-206">使用者通知，也就是在他們的電子郵件用戶端或 web 瀏覽器中對使用者顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="48c7a-206">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="48c7a-207">使用者會覆寫，會決定使用者是否可以選擇要繼續進行其電子郵件或繼續共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="48c7a-207">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="48c7a-208">附隨報告，通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="48c7a-208">Incident reports, to notify administrators.</span></span>

![若要編輯之規則的組件的選項](media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="48c7a-210">此示範而言我已新增使用者通知 （小心這麼做不適當的使用者認知訓練） 的原則，並允許使用者覆寫原則與業務理由，或藉由標幟為誤判。</span><span class="sxs-lookup"><span data-stu-id="48c7a-210">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive.</span></span> <span data-ttu-id="48c7a-211">請注意，您也可以自訂的電子郵件和原則提示文字，是否您想要併入任何其他您的組織原則的相關資訊或提示使用者在他們有疑問，請連絡客戶支援。</span><span class="sxs-lookup"><span data-stu-id="48c7a-211">Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![使用者通知和覆寫選項](media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="48c7a-213">原則包含兩個規則，而出現大量和低量的處理，因此請務必編輯兩者都具有您想要的動作。</span><span class="sxs-lookup"><span data-stu-id="48c7a-213">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want.</span></span> <span data-ttu-id="48c7a-214">這是將視為方式有所不同其特性的情況下的機會。</span><span class="sxs-lookup"><span data-stu-id="48c7a-214">This is an opportunity to treat cases differently depending on their characteristics.</span></span> <span data-ttu-id="48c7a-215">例如，您可能會允許低量違規的覆寫，但不是允許覆寫的大量違規。</span><span class="sxs-lookup"><span data-stu-id="48c7a-215">For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![大量和低的磁碟區的一項規則的一個規則](media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="48c7a-217">此外，如果您想要實際封鎖或限制存取內容的原則違規情形中，您需要在要執行這項操作的規則上設定巨集指令。</span><span class="sxs-lookup"><span data-stu-id="48c7a-217">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![若要限制存取內容的選項](media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="48c7a-219">之後將這些變更儲存至原則設定，我還需要回到原則主要設定] 頁面上，啟用選項，雖然原則是在測試模式中，向使用者顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="48c7a-219">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode.</span></span> <span data-ttu-id="48c7a-220">這是您的使用者，採用 DLP 原則，然後執行使用者認知訓練，不必擔心會影響其產能的太多誤判的有效方法。</span><span class="sxs-lookup"><span data-stu-id="48c7a-220">This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![若要在測試模式中顯示原則提示選項](media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="48c7a-222">在伺服器端 （或雲端戶端如果您想要的話），變更可能不會立即生效，由於各種處理間隔。</span><span class="sxs-lookup"><span data-stu-id="48c7a-222">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals.</span></span> <span data-ttu-id="48c7a-223">如果您發出會對使用者顯示新的原則提示的 DLP 原則變更，使用者可能不會看到所做的變更立即生效，原則變更每隔 24 小時會檢查其 Outlook 用戶端中。</span><span class="sxs-lookup"><span data-stu-id="48c7a-223">If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours.</span></span> <span data-ttu-id="48c7a-224">如果您想要加快以為測試，您可以使用此登錄修正，以[清除從 PolicyNudges 機碼的最後一個下載時間戳記](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。</span><span class="sxs-lookup"><span data-stu-id="48c7a-224">If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451).</span></span> <span data-ttu-id="48c7a-225">Outlook 會下載最新的原則資訊下次您重新啟動它，然後開始撰寫電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="48c7a-225">Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="48c7a-226">如果您有已啟用的原則提示，使用者會開始看到在 Outlook 中的提示，並在發生時，可以報告誤判給您。</span><span class="sxs-lookup"><span data-stu-id="48c7a-226">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![使用以報告誤判] 選項的原則提示](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="48c7a-228">調查誤判</span><span class="sxs-lookup"><span data-stu-id="48c7a-228">Investigate false positives</span></span>

<span data-ttu-id="48c7a-229">DLP 原則範本不是完美直線現成可用的。</span><span class="sxs-lookup"><span data-stu-id="48c7a-229">DLP policy templates are not perfect straight out of the box.</span></span> <span data-ttu-id="48c7a-230">很有可能，您會發現發生在環境中，這是很來簡化雜亂到 DLP 部署如此重要的原因，部分誤判花時間適當地測試及調整您的原則。</span><span class="sxs-lookup"><span data-stu-id="48c7a-230">It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="48c7a-231">以下是誤判的範例。</span><span class="sxs-lookup"><span data-stu-id="48c7a-231">Here's an example of a false positive.</span></span> <span data-ttu-id="48c7a-232">這封電子郵件是相當無害。</span><span class="sxs-lookup"><span data-stu-id="48c7a-232">This email is quite harmless.</span></span> <span data-ttu-id="48c7a-233">使用者是提供給某人，其行動電話號碼，並包括其電子郵件簽章。</span><span class="sxs-lookup"><span data-stu-id="48c7a-233">The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![電子郵件顯示為 false 正數資訊](media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="48c7a-235">使用者會看到警告電子郵件包含敏感資訊，原則提示，但明確地說，澳洲駕照編號。</span><span class="sxs-lookup"><span data-stu-id="48c7a-235">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![報告誤判的原則提示選項](media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="48c7a-237">使用者可以報告誤判，和系統管理員可以查看它已發生的原因。</span><span class="sxs-lookup"><span data-stu-id="48c7a-237">The user can report the false positive, and the administrator can look into why it has occurred.</span></span> <span data-ttu-id="48c7a-238">附隨報告電子郵件中的電子郵件被標示為誤判。</span><span class="sxs-lookup"><span data-stu-id="48c7a-238">In the incident report email, the email is flagged as a false positive.</span></span>

![附隨報告顯示誤判](media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="48c7a-240">此驅動程式的授權案例是很好的範例，若要深入探究。</span><span class="sxs-lookup"><span data-stu-id="48c7a-240">This driver's license case is a good example to dig into.</span></span> <span data-ttu-id="48c7a-241">此誤判發生 「 澳洲駕照 」 類型將會觸發的任何 9 位數字的字串 （甚至是一個屬於 10 位數字的字串），就是 300 個字元鄰近的關鍵字"雪梨 nsw 」 內的原因 （不區分大小寫）。</span><span class="sxs-lookup"><span data-stu-id="48c7a-241">The reason this false positive has occurred is that the “Australian Driver's License” type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords “sydney nsw” (not case sensitive).</span></span> <span data-ttu-id="48c7a-242">這樣它就會觸發的電話號碼和電子郵件簽章，只有因為使用者位於雪梨的情況。</span><span class="sxs-lookup"><span data-stu-id="48c7a-242">So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>

<span data-ttu-id="48c7a-243">有趣的是，如果 「 雪梨、 NSW 」 有逗號，並不會觸發 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="48c7a-243">Interestingly, if “Sydney, NSW” has a comma, the DLP policy is not triggered.</span></span> <span data-ttu-id="48c7a-244">我已經不知道原因逗號差別任何在這裡，也不為何澳洲驅動程式的授權資訊類型，關鍵字中並未包含其他城市和澳洲的狀態，但就可以了。</span><span class="sxs-lookup"><span data-stu-id="48c7a-244">I have no idea why a comma makes any difference here, nor why other cities and states in Australia aren't included in the keywords for the Australian driver's license information type, but there you go.</span></span> <span data-ttu-id="48c7a-245">因此，什麼呢？ 其相關資訊</span><span class="sxs-lookup"><span data-stu-id="48c7a-245">So, what can we do about it?</span></span> <span data-ttu-id="48c7a-246">沒有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="48c7a-246">There's a couple of options.</span></span>

<span data-ttu-id="48c7a-247">其中一個選項是從原則移除澳洲驅動程式的授權資訊類型。</span><span class="sxs-lookup"><span data-stu-id="48c7a-247">One option is to remove the Australian driver's license information type from the policy.</span></span> <span data-ttu-id="48c7a-248">它是在該處因為它是一部分的 DLP 原則範本，但我們不強制使用它。</span><span class="sxs-lookup"><span data-stu-id="48c7a-248">It's in there because it's part of the DLP policy template, but we're not forced to use it.</span></span> <span data-ttu-id="48c7a-249">如果您僅有興趣稅務檔案號碼和不驅動程式的授權，您只可以將其移除。</span><span class="sxs-lookup"><span data-stu-id="48c7a-249">If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it.</span></span> <span data-ttu-id="48c7a-250">例如，您可以移除低量規則在原則中，但保留大量規則中，如此仍然會偵測到多個驅動程式授權的清單。</span><span class="sxs-lookup"><span data-stu-id="48c7a-250">For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![若要刪除規則的機密資訊類型的選項](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="48c7a-252">另一個選項是只要增加的執行個體計數，以便驅動程式的授權低量只偵測到當有多個執行個體。</span><span class="sxs-lookup"><span data-stu-id="48c7a-252">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![若要編輯的執行個體計數選項](media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="48c7a-254">除了變更的執行個體計數，您也可以調整的比對正確性 （或信賴等級）。</span><span class="sxs-lookup"><span data-stu-id="48c7a-254">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level).</span></span> <span data-ttu-id="48c7a-255">如果您的機密資訊類型具有多種模式，您可以調整的比對正確性，在您的規則，使您的規則比對特定的模式即可。</span><span class="sxs-lookup"><span data-stu-id="48c7a-255">If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns.</span></span> <span data-ttu-id="48c7a-256">例如，若要協助減少誤判，您可以設定您的規則的比對正確性，使其符合最高的信賴等級的圖樣。</span><span class="sxs-lookup"><span data-stu-id="48c7a-256">For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level.</span></span> <span data-ttu-id="48c7a-257">了解如何計算信賴等級是有點難以 （及過後的這篇文章的範圍），但以下是如何[使用以調整您的規則信賴等級](data-loss-prevention-policies.md#match-accuracy)的理想說明。</span><span class="sxs-lookup"><span data-stu-id="48c7a-257">Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](data-loss-prevention-policies.md#match-accuracy).</span></span>

<span data-ttu-id="48c7a-258">最後，如果您想要取得更多進階，您可以自訂任何敏感資訊類型--例如，您可以 「 雪梨 NSW 」 從清單中移除之關鍵字[澳洲駕照](what-the-sensitive-information-types-look-for.md#australia-drivers-license-number)，以避免誤判觸發上方。</span><span class="sxs-lookup"><span data-stu-id="48c7a-258">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australian Driver's License](what-the-sensitive-information-types-look-for.md#australia-drivers-license-number), to eliminate the false positive triggered above.</span></span> <span data-ttu-id="48c7a-259">若要了解如何藉由使用 XML 和 PowerShell 執行這項操作，請參閱在[自訂內建的敏感資訊類型](customize-a-built-in-sensitive-information-type.md)的本主題。</span><span class="sxs-lookup"><span data-stu-id="48c7a-259">To learn how to do this by using XML and PowerShell, see this topic on [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="48c7a-260">關閉 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="48c7a-260">Turn off a DLP policy</span></span>

<span data-ttu-id="48c7a-261">當您滿意，DLP 原則很精確，且有效率地偵測敏感資訊類型，以及您的使用者準備好要處理正在進行中的原則，然後您可以啟用此原則。</span><span class="sxs-lookup"><span data-stu-id="48c7a-261">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![若要啟用原則的選項](media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="48c7a-263">如果您正在等待若要查看原則會採取時生效，[連接到安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)並執行[Get-dlpcompliancepolicy 指令程式](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps)，請參閱 DistributionStatus。</span><span class="sxs-lookup"><span data-stu-id="48c7a-263">If you're waiting to see when the policy will take effect, [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and run the [Get-DlpCompliancePolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) to see the DistributionStatus.</span></span>

![在 PowerShell 中執行指令程式](media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="48c7a-265">後忘記的 DLP 原則，您應該執行某些最終您自己的測試要確定預期的原則動作會發生。</span><span class="sxs-lookup"><span data-stu-id="48c7a-265">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring.</span></span> <span data-ttu-id="48c7a-266">如果您想要測試之類的信用卡資料，有一些網站，online 提供的資訊來產生範例信用卡或其他個人資訊，會傳遞總和檢查碼及您的原則會觸發。</span><span class="sxs-lookup"><span data-stu-id="48c7a-266">If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="48c7a-267">允許使用者覆寫的原則會顯示該選項給使用者的原則提示的一部分。</span><span class="sxs-lookup"><span data-stu-id="48c7a-267">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![原則提示，以允許使用者覆寫](media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="48c7a-269">限制內容的原則會一部分的原則提示，向使用者顯示警告，並且阻止傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="48c7a-269">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![原則提示，內容是受限制](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="48c7a-271">摘要</span><span class="sxs-lookup"><span data-stu-id="48c7a-271">Summary</span></span>

<span data-ttu-id="48c7a-272">資料外洩防護原則是適合各種類型的組織。</span><span class="sxs-lookup"><span data-stu-id="48c7a-272">Data loss prevention policies are useful for organizations of all types.</span></span> <span data-ttu-id="48c7a-273">測試 DLP 原則是低風險練習，因為您已透過之類的原則提示，使用者覆寫及附隨報告的控制項。</span><span class="sxs-lookup"><span data-stu-id="48c7a-273">Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports.</span></span> <span data-ttu-id="48c7a-274">安靜模式，您就可以測試若要查看您組織中已發生何種類型的違規的一些 DLP 原則並再使用特殊功能原則低，則為 false 的誤判率、 教育使用者需要允許及不允許，然後推出 DLP 原則，以組織。</span><span class="sxs-lookup"><span data-stu-id="48c7a-274">You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>
