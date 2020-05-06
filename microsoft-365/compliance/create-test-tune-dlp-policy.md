---
title: 建立、測試及調整 DLP 原則
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 在本文中，您將瞭解如何根據組織的需求來建立、測試及調整 DLP 原則。
ms.openlocfilehash: 2a7ef029d00aff8450d9e8cf41253c2a86606807
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035755"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="0e6c9-103">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="0e6c9-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="0e6c9-104">資料遺失防護（DLP）是一項合規性功能，可協助您的組織避免對不想要的敏感資訊的故意或意外洩密。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-104">Data loss prevention (DLP) is a compliance feature designed to help your organization prevent the intentional or accidental exposure of sensitive information to unwanted parties.</span></span> <span data-ttu-id="0e6c9-105">DLP 在 Exchange Server 和 Exchange Online 中有其根，也適用于 SharePoint 線上和商務 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-105">DLP has its roots in Exchange Server and Exchange Online, and is also applicable in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="0e6c9-106">DLP 使用內容分析引擎檢查電子郵件訊息和檔案的內容，尋找機密資訊（例如信用卡號碼和個人身分識別資訊（PII））。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-106">DLP uses a content analysis engine to examine the contents of email messages and files, looking for sensitive information such as credit card numbers and personally identifiable information (PII).</span></span> <span data-ttu-id="0e6c9-107">敏感資訊一般不會以電子郵件傳送，或包含在檔中，而不需要採取其他步驟，例如加密電子郵件訊息或檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-107">Sensitive information should typically not be sent in email, or included in documents, without taking additional steps such as encrypting the email message or files.</span></span> <span data-ttu-id="0e6c9-108">使用 DLP，您可以偵測敏感資訊，並採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="0e6c9-108">Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="0e6c9-109">記錄事件的審計目的</span><span class="sxs-lookup"><span data-stu-id="0e6c9-109">Log the event for auditing purposes</span></span>
- <span data-ttu-id="0e6c9-110">向傳送電子郵件或共用檔的使用者顯示警告</span><span class="sxs-lookup"><span data-stu-id="0e6c9-110">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="0e6c9-111">主動封鎖電子郵件或檔案共用發生</span><span class="sxs-lookup"><span data-stu-id="0e6c9-111">Actively block the email or file sharing from taking place</span></span>

<span data-ttu-id="0e6c9-112">有時客戶會解除 DLP，因為他們不會考慮他們需要保護的資料類型。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-112">Sometimes customers dismiss DLP because they don't consider themselves to have the type of data that needs protecting.</span></span> <span data-ttu-id="0e6c9-113">假設敏感性資料（例如醫療記錄或財務資訊）只會存在於衛生保健或執行線上商店之公司的行業。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-113">The assumption is that sensitive data, such as medical records or financial information, only exists for industries like health care or for companies that run online stores.</span></span> <span data-ttu-id="0e6c9-114">不過，任何業務都可以定期處理機密資訊，即使未加以實現也是一樣。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-114">But any business can handle sensitive information on a regular basis, even if they don't realize it.</span></span> <span data-ttu-id="0e6c9-115">員工姓名和出生日期的試算表，都如同客戶名稱和信用卡詳細資料的試算表一樣機密。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-115">A spreadsheet of employee names and dates of birth is just as sensitive as a spreadsheet of customer names and credit card details.</span></span> <span data-ttu-id="0e6c9-116">而且這種資訊類型的來源可能會比您預期的更多，因為員工不知不覺地前往日常工作中，請考慮從系統中匯出 CSV 檔案，並將郵件傳送給某人。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-116">And this type of information tends to float around more than you might expect, as employees quietly go about their day to day tasks, thinking nothing of export a CSV file from a system and emailing it to someone.</span></span> <span data-ttu-id="0e6c9-117">您也可能會驚訝的是，員工傳送包含信用卡或銀行詳細資料的電子郵件時，不會考慮結果。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-117">You might also be surprised how often employees send emails containing credit card or banking details without considering the consequences.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="0e6c9-118">DLP 偵測到敏感資訊的方式</span><span class="sxs-lookup"><span data-stu-id="0e6c9-118">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="0e6c9-119">機密資訊會透過正則運算式（RegEx）模式比對來識別，並與其他指標（如某些關鍵字接近于相符的模式）搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-119">Sensitive information is identified by regular expression (RegEx) pattern matching, in combination with other indicators such as the proximity of certain keywords to the matching patterns.</span></span> <span data-ttu-id="0e6c9-120">這是信用卡號碼的範例。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-120">An example of this is credit card numbers.</span></span> <span data-ttu-id="0e6c9-121">簽證信用卡號碼具有16位數。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-121">A VISA credit card number has 16 digits.</span></span> <span data-ttu-id="0e6c9-122">不過，這些數位可以以不同的方式寫入，例如1111-1111-1111-1111、1111 1111 1111 1111 或1111111111111111。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-122">However, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="0e6c9-123">任何16位數的字串不一定是信用卡號碼，它可能是技術支援人員系統中的票證號碼，或是某一塊硬體的系列號碼。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-123">Any 16 digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware.</span></span> <span data-ttu-id="0e6c9-124">為了說明信用卡號碼和無害的16位數位符串之間的差異，會執行計算（checksum）以確認號碼符合各種信用卡品牌的已知模式。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-124">To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="0e6c9-125">此外，像是 "簽證" 或 "AMEX" 等關鍵字的接近性，以及可能是信用卡到期日的最接近日期值，也會被視為決定是否要將資料設為信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-125">Furthermore, the proximity of keywords such as "VISA" or "AMEX", along with the proximity to date values that might be the credit card expiry date, is also considered to make a decision about whether the data is a credit card number or not.</span></span>

<span data-ttu-id="0e6c9-126">換句話說，DLP 通常是智慧化，足以辨識電子郵件中這兩種文字之間的差異：</span><span class="sxs-lookup"><span data-stu-id="0e6c9-126">In other words, DLP is usually smart enough to recognize the difference between these two texts in an email:</span></span>

- <span data-ttu-id="0e6c9-127">「您可以定購新的可擕式電腦。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-127">"Can you order me a new laptop.</span></span> <span data-ttu-id="0e6c9-128">使用我的簽證號碼1111-1111-1111-1111，到期11/22，當您有時，將預估的傳遞日期傳送給我。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-128">Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it."</span></span>
- <span data-ttu-id="0e6c9-129">「我的膝上型電腦序號是2222-2222-2222-2222，其購買于11/2010。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-129">"My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010.</span></span> <span data-ttu-id="0e6c9-130">順便說一來，我的旅行簽證是否已獲批准？</span><span class="sxs-lookup"><span data-stu-id="0e6c9-130">By the way, is my travel visa approved yet?"</span></span>

<span data-ttu-id="0e6c9-131">[保留書簽] 的良好參考是[有關機密資訊類型](what-the-sensitive-information-types-look-for.md)的這一主題，說明每種資訊類型的偵測方式。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-131">A good reference to keep bookmarked is this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="0e6c9-132">從資料遺失防護開始的位置</span><span class="sxs-lookup"><span data-stu-id="0e6c9-132">Where to start with data loss prevention</span></span>

<span data-ttu-id="0e6c9-133">當資料洩漏風險不完全顯而易見時，就很難實際開始執行 DLP。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-133">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP.</span></span> <span data-ttu-id="0e6c9-134">幸運的是，DLP 原則可以在「測試模式」中執行，這樣您就能在開啟之前估量效能和精確度。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-134">Fortunately, DLP policies can be run in "test mode", allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="0e6c9-135">可透過 Exchange 系統管理中心來管理 Exchange Online 的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-135">DLP policies for Exchange Online can be managed through the Exchange admin center.</span></span> <span data-ttu-id="0e6c9-136">不過，您可以透過安全性 & 規範中心設定所有工作負載的 DLP 原則，如此一來，我們將在本文中示範。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-136">But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article.</span></span> <span data-ttu-id="0e6c9-137">在 [安全性 & 規範中心] 中，您會在 [**資料遺失防護** > ]**原則**下找到 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-137">In the Security & Compliance Center you'll find the DLP policies under **Data loss prevention** > **Policy**.</span></span> <span data-ttu-id="0e6c9-138">按一下 [**建立要啟動的原則**]。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-138">Click on **Create a policy** to start.</span></span>

<span data-ttu-id="0e6c9-139">Microsoft 365 提供一系列[dlp 原則範本](what-the-dlp-policy-templates-include.md)，您可以用來建立 dlp 原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-139">Microsoft 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create DLP policies.</span></span> <span data-ttu-id="0e6c9-140">假設您是澳大利亞公司。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-140">Let's say that you're an Australian business.</span></span> <span data-ttu-id="0e6c9-141">您可以篩選原則範本，只顯示與澳大利亞相關的使用者，這些範本屬於財務、醫療和健康情況和隱私權等一般類別。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-141">You can filter the policy templates to display only those that are relevant to Australia, which fall into the general categories of Financial, Medical and Health, and Privacy.</span></span>

![選擇國家或地區的選項](../media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="0e6c9-143">在本次示範中，我將選擇澳大利亞個人身分識別資訊（PII）資料，其中包括澳大利亞稅收檔案編號（TFN）和駕駛執照號碼的資訊類型。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-143">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![選擇原則範本的選項](../media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="0e6c9-145">請將新的 DLP 原則命名為 [名稱]。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-145">Give your new DLP policy a name.</span></span> <span data-ttu-id="0e6c9-146">預設名稱會符合 DLP 原則範本，但您應選擇更具描述性的名稱，因為您可以從同一個範本建立多個原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-146">The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![用於命名原則的選項](../media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="0e6c9-148">選擇原則將套用的位置。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-148">Choose the locations that the policy will apply to.</span></span> <span data-ttu-id="0e6c9-149">DLP 原則可以套用到 Exchange Online、SharePoint Online 和商務 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-149">DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="0e6c9-150">我要將此原則設定為套用至所有位置。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-150">I am going to leave this policy configured to apply to all locations.</span></span>

![選擇所有位置的選項](../media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="0e6c9-152">在第一個**原則設定**步驟中，只要接受預設值即可。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-152">At the first **Policy Settings** step just accept the defaults for now.</span></span> <span data-ttu-id="0e6c9-153">您可以在 DLP 原則中執行許多自訂作業，但是預設值是一個不錯的開始位置。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-153">There is quite a lot of customization you can do in DLP policies, but the defaults are a fine place to start.</span></span>

![自訂要保護的內容類型的選項](../media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="0e6c9-155">按 **[下一步]** 之後，您將會看到其他具有更多自訂選項的 [**原則設定**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-155">After clicking **Next** you'll be presented with an additional **Policy Settings** page with more customization options.</span></span> <span data-ttu-id="0e6c9-156">針對您剛測試的原則，您可以在這裡開始進行一些調整。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-156">For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="0e6c9-157">現在已經關閉原則提示，這是在您只測試專案，而不想要向使用者顯示任何專案時採取的合理步驟。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-157">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet.</span></span> <span data-ttu-id="0e6c9-158">原則提示會向使用者顯示警告，告知您其即將違反 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-158">Policy tips display warnings to users that they're about to violate a DLP policy.</span></span> <span data-ttu-id="0e6c9-159">例如，Outlook 使用者將會看到一則警告，指出其附加的檔案包含信用卡號碼，並將拒絕其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-159">For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected.</span></span> <span data-ttu-id="0e6c9-160">原則秘訣的目標是先停止不相容的行為，再進行此動作。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-160">The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="0e6c9-161">我也減少了從10到1的實例數目，所以這個原則會偵測所有的澳大利亞 PII 資料共用，而不只是大量的資料共用。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-161">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="0e6c9-162">我也將另一位收件者新增至附隨報告電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-162">I've also added another recipient to the incident report email.</span></span>

![其他原則設定](../media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="0e6c9-164">最後，我已設定此原則最初在測試模式中執行。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-164">Finally, I've configured this policy to run in test mode initially.</span></span> <span data-ttu-id="0e6c9-165">請注意，在 [測試模式] 中也有一個用於停用原則提示的選項。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-165">Notice there's also an option here to disable policy tips while in test mode.</span></span> <span data-ttu-id="0e6c9-166">這可讓您彈性啟用原則中的原則提示，但接著決定是否要在測試期間顯示或隱藏它們。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-166">This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![先測試原則的選項](../media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="0e6c9-168">在最後的審閱畫面上，按一下 [**建立**] 以完成建立原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-168">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="0e6c9-169">測試 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="0e6c9-169">Test a DLP policy</span></span>

<span data-ttu-id="0e6c9-170">新的 DLP 原則會在大約1小時內開始生效。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-170">Your new DLP policy will begin to take effect within about 1 hour.</span></span> <span data-ttu-id="0e6c9-171">您可以坐下來，等待一般的使用者活動觸發，否則您也可以嘗試自行觸發。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-171">You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself.</span></span> <span data-ttu-id="0e6c9-172">舊版 I 連結至此[主題的敏感資訊類型](what-the-sensitive-information-types-look-for.md)，可讓您瞭解如何觸發 DLP 相符的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-172">Earlier I linked to this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="0e6c9-173">舉例來說，我為本文建立的 DLP 原則會偵測到澳大利亞稅收檔編號（TFN）。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-173">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN).</span></span> <span data-ttu-id="0e6c9-174">根據檔，符合下列準則為基礎。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-174">According to the documentation, the match is based on the following criteria.</span></span>

![澳大利亞稅收檔案編號的檔](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="0e6c9-176">為了以緊密的方式示範 TFN 偵測，具有 "稅收 file number" 字樣的電子郵件，以及接近接近的九位數位符串都是 sail，不會有任何問題。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-176">To demonstrate TFN detection in a rather blunt manner, an email with the words "Tax file number" and a 9 digit string in close proximity will sail through without any issues.</span></span> <span data-ttu-id="0e6c9-177">不會觸發 DLP 原則的原因是，9位數位符串必須傳遞校驗和，表示它是有效的 TFN，而不只是無害的數位字串。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-177">The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![未通過檢查的澳大利亞稅收檔編號](../media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="0e6c9-179">相比之下，具有 "稅收檔號碼" 字樣的電子郵件和傳遞校驗和的有效 TFN 會觸發原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-179">In comparison, an email with the words "Tax file number" and a valid TFN that passes the checksum will trigger the policy.</span></span> <span data-ttu-id="0e6c9-180">在這裡的記錄中，所使用的 TFN 是從網站產生，但不是正版，TFNs。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-180">For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs.</span></span> <span data-ttu-id="0e6c9-181">這類網站非常有用，因為測試 DLP 原則時最常見的錯誤之一是使用不正確虛假號碼，而且不會傳遞校驗和（因此不會觸發原則）。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-181">Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![傳遞校驗和的澳大利亞稅收檔編號](../media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="0e6c9-183">附隨報告電子郵件包括所偵測到的敏感資訊類型、偵測到多少個實例，以及偵測的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-183">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![顯示繳稅檔編號的附隨報告](../media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="0e6c9-185">如果您在測試模式中保留 DLP 原則，並分析附隨報告電子郵件，您可以開始進行 DLP 原則的準確性，以及強制執行它的有效性。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-185">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced.</span></span> <span data-ttu-id="0e6c9-186">除了附隨報告之外，您還可以[使用 DLP 報告](view-the-dlp-reports.md)來查看整個租使用者中原則相符專案的匯總視圖。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-186">In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="0e6c9-187">調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="0e6c9-187">Tune a DLP policy</span></span>

<span data-ttu-id="0e6c9-188">當您分析原則擊中時，您可能會想要對原則行為的方式進行一些調整。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-188">As you analyze your policy hits you might want to make some adjustments to how the policies behave.</span></span> <span data-ttu-id="0e6c9-189">簡單的範例是，您可能會判斷電子郵件中的某個 TFN 不是問題（我認為它仍然是，但為了示範，我們會告訴它），但有兩個以上的實例是問題。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-189">As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem.</span></span> <span data-ttu-id="0e6c9-190">多個實例可能是一種危險案例，例如員工使用從人力資源資料庫到外部方的 CSV 匯出電子郵件，例如外部會計服務。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-190">Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service.</span></span> <span data-ttu-id="0e6c9-191">絕對您想要偵測和封鎖的內容。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-191">Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="0e6c9-192">在 [安全性 & 規範中心] 中，您可以編輯現有的原則來調整行為。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-192">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![編輯原則的選項](../media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="0e6c9-194">您可以調整位置設定，讓原則僅套用至特定工作負載，或套用至特定的網站和帳戶。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-194">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![選擇特定位置的選項](../media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="0e6c9-196">您也可以調整原則設定，並編輯規則，以更符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-196">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![編輯規則的選項](../media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="0e6c9-198">當您在 DLP 原則中編輯規則時，您可以變更：</span><span class="sxs-lookup"><span data-stu-id="0e6c9-198">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="0e6c9-199">條件，包含會觸發規則的敏感性資料實例類型和數目。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-199">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="0e6c9-200">採取的動作，例如限制存取內容。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-200">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="0e6c9-201">使用者通知：這是在電子郵件客戶程式或網頁瀏覽器中向使用者顯示的原則提示。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-201">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="0e6c9-202">使用者覆寫，它會決定使用者是否可以選擇繼續進行電子郵件或檔案共用。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-202">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="0e6c9-203">附隨報告，以通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-203">Incident reports, to notify administrators.</span></span>

![編輯規則部分的選項](../media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="0e6c9-205">在本次示範中，我已將使用者通知新增至原則（在沒有適當的使用者知曉訓練的情況下，請注意這樣做），並且允許使用者以業務理由覆蓋原則，或將其標記為誤報。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-205">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive.</span></span> <span data-ttu-id="0e6c9-206">請注意，如果您想要包含組織原則的任何其他資訊，請自訂電子郵件和原則提示文字，如果有任何問題，也可以提示使用者與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-206">Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![使用者通知和覆寫的選項](../media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="0e6c9-208">原則包含兩個處理大量磁片或低容量的規則，因此請務必使用您想要的動作進行編輯。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-208">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want.</span></span> <span data-ttu-id="0e6c9-209">這是視案例的特性而異的機會。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-209">This is an opportunity to treat cases differently depending on their characteristics.</span></span> <span data-ttu-id="0e6c9-210">例如，您可以允許覆寫磁片容量低的情況，但不允許對高磁片區違規的覆寫。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-210">For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![適用于低容量的高容量和一個規則的一個規則](../media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="0e6c9-212">此外，如果您想要實際封鎖或限制存取違反原則的內容，您必須設定規則上的動作來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-212">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![可限制存取內容的選項](../media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="0e6c9-214">將變更儲存至原則設定後，我也需要回到原則的 [主要設定] 頁面，並啟用此選項，以在原則處於測試模式時，向使用者顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-214">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode.</span></span> <span data-ttu-id="0e6c9-215">這是將 DLP 原則引入使用者的有效方式，並進行使用者知曉訓練，但不會冒出影響其生產力的誤報數。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-215">This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![在測試模式中顯示原則提示的選項](../media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="0e6c9-217">在伺服器端（或您想要的雲端端）上，由於各種處理間隔，因此變更可能不會立即生效。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-217">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals.</span></span> <span data-ttu-id="0e6c9-218">如果您要進行 DLP 原則變更，以向使用者顯示新的原則提示，使用者可能看不到其 Outlook 用戶端中所做的變更會立即生效，這會檢查每24小時執行的原則變更。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-218">If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours.</span></span> <span data-ttu-id="0e6c9-219">如果您想要加快測試速度，您可以使用此註冊表修正程式，[從 PolicyNudges 機碼清除上次下載時間戳記](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-219">If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451).</span></span> <span data-ttu-id="0e6c9-220">Outlook 會在您下一次重新開機時下載最新的原則資訊，然後開始撰寫電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-220">Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="0e6c9-221">如果您已啟用原則提示，使用者就會開始查看 Outlook 中的秘訣，並在發生時向您報告誤報。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-221">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![具有報告 false 正值選項的原則提示](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="0e6c9-223">調查誤報</span><span class="sxs-lookup"><span data-stu-id="0e6c9-223">Investigate false positives</span></span>

<span data-ttu-id="0e6c9-224">DLP 原則範本並不完全直接離開盒。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-224">DLP policy templates are not perfect straight out of the box.</span></span> <span data-ttu-id="0e6c9-225">您很可能會發現環境中有一些誤報的情況，這就是為什麼讓您輕鬆地進行 DLP 部署變得如此重要的原因，請花些時間來充分測試及調整原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-225">It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="0e6c9-226">以下是誤報的範例。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-226">Here's an example of a false positive.</span></span> <span data-ttu-id="0e6c9-227">這封電子郵件相當無害。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-227">This email is quite harmless.</span></span> <span data-ttu-id="0e6c9-228">使用者向某人提供其行動電話號碼，並包含他們的電子郵件簽名。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-228">The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![顯示誤報正值資訊的電子郵件](../media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="0e6c9-230">不過，使用者會看到一個原則提示，告知他們電子郵件包含機密資訊（特別是澳大利亞駕駛執照號碼）。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-230">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![在原則提示中報告 false 陽性的選項](../media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="0e6c9-232">使用者可以報告誤報，而且系統管理員可以深入瞭解發生的原因。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-232">The user can report the false positive, and the administrator can look into why it has occurred.</span></span> <span data-ttu-id="0e6c9-233">在 [附隨報告] 電子郵件中，會將電子郵件標記為誤報。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-233">In the incident report email, the email is flagged as a false positive.</span></span>

![顯示誤報的附隨報告](../media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="0e6c9-235">此駕駛執照案例是深入瞭解的一個很好的範例。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-235">This driver's license case is a good example to dig into.</span></span> <span data-ttu-id="0e6c9-236">這種誤報的原因是，「澳大利亞駕駛執照」類型將會由任何9位數位符串（甚至是10位數位符串的一部分）所觸發，且在300個字元接近于關鍵字 "悉尼 nsw" （不區分大小寫）內。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-236">The reason this false positive has occurred is that the "Australian Driver's License" type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords "sydney nsw" (not case sensitive).</span></span> <span data-ttu-id="0e6c9-237">因此，它會因電話號碼和電子郵件簽章而觸發，只是因為使用者碰巧在悉尼。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-237">So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>


<span data-ttu-id="0e6c9-238">其中一個選項是移除來自原則的澳大利亞駕駛執照資訊類型。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-238">One option is to remove the Australian driver's license information type from the policy.</span></span> <span data-ttu-id="0e6c9-239">因為它是 DLP 原則範本的一部分，但不會強制您使用它。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-239">It's in there because it's part of the DLP policy template, but we're not forced to use it.</span></span> <span data-ttu-id="0e6c9-240">如果您只對稅收檔編號（而不是驅動程式的授權）感興趣，您可以將它移除。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-240">If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it.</span></span> <span data-ttu-id="0e6c9-241">例如，您可以從原則中的低容量規則中移除它，但將它保留在高容量規則中，以便仍偵測到多個驅動程式授權清單。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-241">For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![從規則刪除敏感資訊類型的選項](../media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="0e6c9-243">另一種方法是增加實例計數，這樣只有在有多個實例時，才會偵測到低數量的驅動程式授權。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-243">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![編輯實例計數的選項](../media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="0e6c9-245">除了變更實例計數之外，您也可以調整符合精確度（或信賴程度）。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-245">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level).</span></span> <span data-ttu-id="0e6c9-246">如果您的敏感資訊類型有多種模式，您可以調整規則中的相符準確度，使規則只符合特定模式。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-246">If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns.</span></span> <span data-ttu-id="0e6c9-247">例如，若要協助減少誤報，您可以設定規則的符合準確度，使其只符合具有最高信賴度的模式。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-247">For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level.</span></span> <span data-ttu-id="0e6c9-248">瞭解信賴等級的計算方式有點棘手（但超出此文章的範圍），但是這裡是[如何使用信賴層級調整規則](data-loss-prevention-policies.md#match-accuracy)的好說明。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-248">Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](data-loss-prevention-policies.md#match-accuracy).</span></span>

<span data-ttu-id="0e6c9-249">最後，如果您想要更進一步的掌握，您可以自訂任何敏感資訊類型，例如，您可以從[澳大利亞駕照](what-the-sensitive-information-types-look-for.md#australia-drivers-license-number)的關鍵字清單中移除 "悉尼 NSW"，以消除上述誤報。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-249">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australian Driver's License](what-the-sensitive-information-types-look-for.md#australia-drivers-license-number), to eliminate the false positive triggered above.</span></span> <span data-ttu-id="0e6c9-250">若要瞭解如何使用 XML 和 PowerShell 執行這項作業，請參閱本主題：[自訂內建的敏感資訊類型](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-250">To learn how to do this by using XML and PowerShell, see this topic on [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-on-a-dlp-policy"></a><span data-ttu-id="0e6c9-251">開啟 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="0e6c9-251">Turn on a DLP policy</span></span>

<span data-ttu-id="0e6c9-252">當您很樂意您的 DLP 原則正確且有效地偵測敏感資訊類型，而且使用者準備好處理已就地原則的原則之後，即可啟用該原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-252">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![開啟原則的選項](../media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="0e6c9-254">如果您想要查看原則何時生效，請連線[至安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) ，並執行[Get-DlpCompliancePolicy Cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) ，以查看 DistributionStatus。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-254">If you're waiting to see when the policy will take effect, [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and run the [Get-DlpCompliancePolicy cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) to see the DistributionStatus.</span></span>

![在 PowerShell 中執行 Cmdlet](../media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="0e6c9-256">開啟 DLP 原則之後，您應該先執行您自己的一些最終測試，以確保發生預期的原則動作。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-256">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring.</span></span> <span data-ttu-id="0e6c9-257">如果您嘗試測試像是信用卡資料之類的內容，則會有網站線上，提供如何產生範例信用卡或其他個人資訊的資訊，這些資訊會透過校驗和觸發您的原則。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-257">If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="0e6c9-258">允許使用者覆寫的原則會將該選項呈現給使用者，成為原則提示的一部分。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-258">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![允許使用者覆寫的原則提示](../media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="0e6c9-260">限制內容的原則會在原則提示的一部分向使用者呈現警告，並防止他們傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-260">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![內容受限制的原則提示](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="0e6c9-262">摘要</span><span class="sxs-lookup"><span data-stu-id="0e6c9-262">Summary</span></span>

<span data-ttu-id="0e6c9-263">資料遺失防護原則對於所有類型的組織都很有用。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-263">Data loss prevention policies are useful for organizations of all types.</span></span> <span data-ttu-id="0e6c9-264">測試某些 DLP 原則是低風險的執行動作，因為您的控制原則提示、使用者覆寫和附隨報告等專案。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-264">Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports.</span></span> <span data-ttu-id="0e6c9-265">您可以不知不覺地測試部分 DLP 原則，以查看組織中已發生的違規類型，然後使用低的誤報速率來製作原則，並對使用者提供允許和不允許的專案，然後將 DLP 原則推廣至組織。</span><span class="sxs-lookup"><span data-stu-id="0e6c9-265">You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>
