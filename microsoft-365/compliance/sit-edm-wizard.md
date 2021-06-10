---
title: 使用完全符合結構描述和敏感性資訊類型精靈
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何使用完全符合結構描述和敏感性資訊類型精靈。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fdf289c403d8c09342a1eac1434c4219bb7b13c
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861656"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="7c64a-103">使用完全符合結構描述和敏感性資訊類型精靈</span><span class="sxs-lookup"><span data-stu-id="7c64a-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="7c64a-104">[使用以精確資料比對為基礎 (EDM) 的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 包含諸多步驟。</span><span class="sxs-lookup"><span data-stu-id="7c64a-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="7c64a-105">您可以使用此嚮導建立架構和機密資訊類型 (SIT) pattern (規則套件) 檔案，以協助簡化程式。</span><span class="sxs-lookup"><span data-stu-id="7c64a-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="7c64a-106">「完全符合結構描述和敏感性資訊類型」精靈只適用于 World Wide 和 GCC 雲端。</span><span class="sxs-lookup"><span data-stu-id="7c64a-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="7c64a-107">您可以使用這個精靈取代：</span><span class="sxs-lookup"><span data-stu-id="7c64a-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="7c64a-108">定義用於敏感性資訊的資料庫結構描述</span><span class="sxs-lookup"><span data-stu-id="7c64a-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="7c64a-109">設定模式 (規則套件)</span><span class="sxs-lookup"><span data-stu-id="7c64a-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="7c64a-110">[第 1 部分：設定以 EDM 為基礎的分類](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification) 的步驟。</span><span class="sxs-lookup"><span data-stu-id="7c64a-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="7c64a-111">先決條件</span><span class="sxs-lookup"><span data-stu-id="7c64a-111">Pre-requisites</span></span>

1. <span data-ttu-id="7c64a-112">快速瞭解使用 EDM 建立自訂敏感性資訊類型的步驟 [工作流程概覽](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance)。</span><span class="sxs-lookup"><span data-stu-id="7c64a-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="7c64a-113">執行 [將敏感性資料儲存為 .csv 格式](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) 一節中的步驟。</span><span class="sxs-lookup"><span data-stu-id="7c64a-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="7c64a-114">使用完全符合結構描述和敏感性資訊類型模式精靈</span><span class="sxs-lookup"><span data-stu-id="7c64a-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="7c64a-115">針對您的租使用者，在 Microsoft 365 合規性中心，移至 **資料分類** > **完全資料比對**。</span><span class="sxs-lookup"><span data-stu-id="7c64a-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="7c64a-116">選擇 **[建立 EDM 結構描述]** 以開啟結構描述精靈設定飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="7c64a-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![EDM 結構描述建立精靈設定飛出視窗](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="7c64a-118">請填入適當的 **名稱** 和 **描述**。</span><span class="sxs-lookup"><span data-stu-id="7c64a-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="7c64a-119">如果您想要該行為，請選擇 [ **所有架構欄位都忽略分隔符號和標點符號** ]。</span><span class="sxs-lookup"><span data-stu-id="7c64a-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="7c64a-120">若要深入瞭解設定 EDM 以忽略大小寫或分隔符號，請參閱 [使用精確的資料符合建立自訂機密資訊類型 (EDM) 型分類](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="7c64a-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="7c64a-121">在 **結構描述欄位 #1** 填入您想要的值，並視需要新增更多欄位。</span><span class="sxs-lookup"><span data-stu-id="7c64a-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7c64a-122">您至少必須將其中一個最多五個結構描述欄位指定為可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="7c64a-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="7c64a-123">選擇 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="7c64a-123">Choose save.</span></span> <span data-ttu-id="7c64a-124">您的結構描述會隨即列出。</span><span class="sxs-lookup"><span data-stu-id="7c64a-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="7c64a-125">選擇 **[EDM 敏感性資訊類型]** 和 **[建立 EDM 敏感性資訊類型]**，以開啟 [敏感性資訊類型設定] 精靈。</span><span class="sxs-lookup"><span data-stu-id="7c64a-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="7c64a-126">選擇 **[選擇現有的 EDM 結構描述]**，然後從清單中選擇您在步驟2-6 中所建立的結構描述。</span><span class="sxs-lookup"><span data-stu-id="7c64a-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="7c64a-127">選擇 **[下一步]**，然後選擇 **[建立模式]**。</span><span class="sxs-lookup"><span data-stu-id="7c64a-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="7c64a-128">選擇 **[信賴等級]** 和 **[主要元素]**。</span><span class="sxs-lookup"><span data-stu-id="7c64a-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="7c64a-129">若要深入瞭解如何設定模式，請參閱 [在合規性中心內建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="7c64a-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="7c64a-130">選擇 **[主要元素的敏感性資訊類型]** 以建立關聯。</span><span class="sxs-lookup"><span data-stu-id="7c64a-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="7c64a-131">若要深入瞭解可用的敏感性資訊類型，請參閱 [[敏感性資訊類型實體定義]](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="7c64a-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="7c64a-132">選擇 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="7c64a-132">Choose **Done**.</span></span>

13. <span data-ttu-id="7c64a-133">選擇您想要的 **[信賴等級和字元概量]**。</span><span class="sxs-lookup"><span data-stu-id="7c64a-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="7c64a-134">這會是整個 EDM 敏感性資訊類型的預設值</span><span class="sxs-lookup"><span data-stu-id="7c64a-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="7c64a-135">如果您想要建立其他 EDM 敏感資訊類型的模式，請選擇 [ **建立模式** ]。</span><span class="sxs-lookup"><span data-stu-id="7c64a-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="7c64a-136">選擇 **[下一步]** 並填入 **[名稱]** 和 **[系統管理員的描述]**。</span><span class="sxs-lookup"><span data-stu-id="7c64a-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="7c64a-137">檢閱並選擇 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="7c64a-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="7c64a-138">您可以選取顯示 [編輯] 和 [刪除] 的控制項，以刪除或編輯敏感性資訊類型模式。</span><span class="sxs-lookup"><span data-stu-id="7c64a-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c64a-139">如果您想要移除某一結構描述，且它已與 EDM 敏感性資訊類型相關聯，您必須先刪除 EDM 敏感性資訊類型，然後您就可以刪除該結構描述。</span><span class="sxs-lookup"><span data-stu-id="7c64a-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="7c64a-140">建立後的步驟</span><span class="sxs-lookup"><span data-stu-id="7c64a-140">Post creation steps</span></span>

<span data-ttu-id="7c64a-141">在您使用這個精靈建立 EDM 結構描述和模式 (規則套件) 檔案之後，您仍需執行 [第2部分：雜湊並上傳敏感性資料]](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) 中的步驟，您才能使用 EDM 自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="7c64a-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="7c64a-142">在確認您的機密資訊資料表已正確上載後，您可以測試它是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="7c64a-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="7c64a-143">開啟 **規範中心**  >  **資料分類**  >  **機密資訊類型**。</span><span class="sxs-lookup"><span data-stu-id="7c64a-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="7c64a-144">從清單中選取 EDM SIT，然後選取飛入窗格中的 [ **測試** ]。</span><span class="sxs-lookup"><span data-stu-id="7c64a-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="7c64a-145">Upload 包含您要偵測之資料的專案，例如，建立包含機密資訊表格中的部分資料的專案。</span><span class="sxs-lookup"><span data-stu-id="7c64a-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="7c64a-146">如果您在架構中使用 [可設定的相符] 功能定義略過的分隔符號，請確定該專案包括和沒有這些分隔符號的範例。</span><span class="sxs-lookup"><span data-stu-id="7c64a-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="7c64a-147">上載及掃描檔案後，請檢查是否符合 EDM SIT。</span><span class="sxs-lookup"><span data-stu-id="7c64a-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="7c64a-148">如果 SIT 中的 **Test** 函數偵測到相符的，請檢查它未進行裁切或解壓縮錯誤。</span><span class="sxs-lookup"><span data-stu-id="7c64a-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="7c64a-149">例如，只要只解壓縮其應該偵測的完整字串子字串，或是只拾取多字字串中的第一個字，或是在解壓縮中包含額外的符號或字元。</span><span class="sxs-lookup"><span data-stu-id="7c64a-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="7c64a-150">請參閱 [正則運算式語言-](/dotnet/standard/base-types/regular-expression-language-quick-reference) 正則運算式語言參考的快速參考。</span><span class="sxs-lookup"><span data-stu-id="7c64a-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="7c64a-151">疑難排解</span><span class="sxs-lookup"><span data-stu-id="7c64a-151">Troubleshooting</span></span>

<span data-ttu-id="7c64a-152">如果您找不到任何相符專案，請嘗試下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7c64a-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="7c64a-153">使用 [EDM 工具上傳機密資料的指導](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)方針中所述的命令，確認您的機密資料已正確上傳。</span><span class="sxs-lookup"><span data-stu-id="7c64a-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="7c64a-154">請檢查您在專案中輸入的範例是否存在於您的機密資訊資料表中，而且忽略的分隔符號是否正確。</span><span class="sxs-lookup"><span data-stu-id="7c64a-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="7c64a-155">**測試** 您在每個模式中設定主要元素時所使用的 SIT。</span><span class="sxs-lookup"><span data-stu-id="7c64a-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="7c64a-156">這會確認 SIT 可以符合專案中的範例。</span><span class="sxs-lookup"><span data-stu-id="7c64a-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="7c64a-157">如果您在 EDM 類型中為主要元素選取的 SIT 沒有在專案中找到相符專案，或找到比預期更少的相符專案，請檢查它是否支援存在於內容中的分隔符號及分隔符號。</span><span class="sxs-lookup"><span data-stu-id="7c64a-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="7c64a-158">請務必包含您架構中定義的被忽略分隔符號。</span><span class="sxs-lookup"><span data-stu-id="7c64a-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="7c64a-159">如果 **Test** 函數根本沒有偵測任何內容，請檢查您選取的 SIT 是否包含其他關鍵字或其他驗證的需求。</span><span class="sxs-lookup"><span data-stu-id="7c64a-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="7c64a-160">針對內建的，請參閱 [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md) ，以確認符合每個類型的最低需求。</span><span class="sxs-lookup"><span data-stu-id="7c64a-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
