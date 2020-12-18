---
title: 使用完全符合結構描述和敏感性資訊類型精靈
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何使用完全符合結構描述和敏感性資訊類型精靈。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699149"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="c47b8-103">使用完全符合結構描述和敏感性資訊類型精靈</span><span class="sxs-lookup"><span data-stu-id="c47b8-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="c47b8-104">[使用以精確資料比對為基礎 (EDM) 的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 包含諸多步驟。</span><span class="sxs-lookup"><span data-stu-id="c47b8-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="c47b8-105">您可以使用此精靈來建立結構描述和敏感性資訊類型模式 (規則套件) 檔案，以協助簡化程式。</span><span class="sxs-lookup"><span data-stu-id="c47b8-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="c47b8-106">「完全符合結構描述和敏感性資訊類型」精靈只適用于 World Wide 和 GCC 雲端。</span><span class="sxs-lookup"><span data-stu-id="c47b8-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="c47b8-107">您可以使用這個精靈取代：</span><span class="sxs-lookup"><span data-stu-id="c47b8-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="c47b8-108">定義用於敏感性資訊的資料庫結構描述</span><span class="sxs-lookup"><span data-stu-id="c47b8-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="c47b8-109">設定模式 (規則套件)</span><span class="sxs-lookup"><span data-stu-id="c47b8-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="c47b8-110">[第 1 部分：設定以 EDM 為基礎的分類](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification) 的步驟。</span><span class="sxs-lookup"><span data-stu-id="c47b8-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="c47b8-111">先決條件</span><span class="sxs-lookup"><span data-stu-id="c47b8-111">Pre-requisites</span></span>

1. <span data-ttu-id="c47b8-112">快速瞭解使用 EDM 建立自訂敏感性資訊類型的步驟 [工作流程概覽](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance)。</span><span class="sxs-lookup"><span data-stu-id="c47b8-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="c47b8-113">執行 [將敏感性資料儲存為 .csv 格式](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) 一節中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c47b8-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="c47b8-114">使用完全符合結構描述和敏感性資訊類型模式精靈</span><span class="sxs-lookup"><span data-stu-id="c47b8-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="c47b8-115">針對您的租使用者，在 Microsoft 365 合規性中心，移至 **資料分類** > **完全資料比對**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="c47b8-116">選擇 **[建立 EDM 結構描述]** 以開啟結構描述精靈設定飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="c47b8-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![EDM 結構描述建立精靈設定飛出視窗](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="c47b8-118">請填入適當的 **名稱** 和 **描述**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="c47b8-119">如果您想要執行該行為，請選擇 **[忽略所有結構描述欄位的分隔符號及標點符號]**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="c47b8-120">若要深入瞭解如何設定 EDM 以忽略案例或分隔符號，請參閱 [使用以精確資料對比 (EDM) 為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="c47b8-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="c47b8-121">在 **結構描述欄位 #1** 填入您想要的值，並視需要新增更多欄位。</span><span class="sxs-lookup"><span data-stu-id="c47b8-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c47b8-122">您至少必須將其中一個最多五個結構描述欄位指定為可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="c47b8-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="c47b8-123">選擇 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c47b8-123">Choose save.</span></span> <span data-ttu-id="c47b8-124">您的結構描述會隨即列出。</span><span class="sxs-lookup"><span data-stu-id="c47b8-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="c47b8-125">選擇 **[EDM 敏感性資訊類型]** 和 **[建立 EDM 敏感性資訊類型]**，以開啟 [敏感性資訊類型設定] 精靈。</span><span class="sxs-lookup"><span data-stu-id="c47b8-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="c47b8-126">選擇 **[選擇現有的 EDM 結構描述]**，然後從清單中選擇您在步驟2-6 中所建立的結構描述。</span><span class="sxs-lookup"><span data-stu-id="c47b8-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="c47b8-127">選擇 **[下一步]**，然後選擇 **[建立模式]**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="c47b8-128">選擇 **[信賴等級]** 和 **[主要元素]**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="c47b8-129">若要深入瞭解如何設定模式，請參閱 [在合規性中心內建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="c47b8-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="c47b8-130">選擇 **[主要元素的敏感性資訊類型]** 以建立關聯。</span><span class="sxs-lookup"><span data-stu-id="c47b8-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="c47b8-131">若要深入瞭解可用的敏感性資訊類型，請參閱 [[敏感性資訊類型實體定義]](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="c47b8-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="c47b8-132">選擇 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-132">Choose **Done**.</span></span>

13. <span data-ttu-id="c47b8-133">選擇您想要的 **[信賴等級和字元概量]**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="c47b8-134">這會是整個 EDM 敏感性資訊類型的預設值</span><span class="sxs-lookup"><span data-stu-id="c47b8-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="c47b8-135">如果您想要為 EDM 敏感性資訊類型建立其他模式，請選擇 **[建立模式]**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="c47b8-136">選擇 **[下一步]** 並填入 **[名稱]** 和 **[系統管理員的描述]**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="c47b8-137">檢閱並選擇 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="c47b8-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="c47b8-138">您可以選取顯示 [編輯] 和 [刪除] 的控制項，以刪除或編輯敏感性資訊類型模式。</span><span class="sxs-lookup"><span data-stu-id="c47b8-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c47b8-139">如果您想要移除某一結構描述，且它已與 EDM 敏感性資訊類型相關聯，您必須先刪除 EDM 敏感性資訊類型，然後您就可以刪除該結構描述。</span><span class="sxs-lookup"><span data-stu-id="c47b8-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="c47b8-140">文章步驟</span><span class="sxs-lookup"><span data-stu-id="c47b8-140">Post steps</span></span>

<span data-ttu-id="c47b8-141">在您使用這個精靈建立 EDM 結構描述和模式 (規則套件) 檔案之後，您仍需執行 [第2部分：雜湊並上傳敏感性資料]](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) 中的步驟，您才能使用 EDM 自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c47b8-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>