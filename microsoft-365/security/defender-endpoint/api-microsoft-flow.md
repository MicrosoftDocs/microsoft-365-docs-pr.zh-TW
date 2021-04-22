---
title: Microsoft Defender for Endpoint Flow connector
ms.reviewer: ''
description: 使用 Microsoft Defender for Endpoint Flow connector 來自動化安全性，並建立一個流程，當您租使用者上發生新警示時，就會觸發此流程。
keywords: 流程、支援的 api、api、Microsoft flow、查詢、自動化
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33a7c7b1907ac761dfdde43a70bfb8f515235150
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929296"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="2dff8-104">Microsoft Power (過去的 Microsoft Flow) 和 Azure 功能</span><span class="sxs-lookup"><span data-stu-id="2dff8-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2dff8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2dff8-105">**Applies to:**</span></span>
- [<span data-ttu-id="2dff8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2dff8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2dff8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2dff8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="2dff8-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="2dff8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2dff8-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2dff8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="2dff8-110">自動化的安全性程式是每一項新式安全性運作中心的標準需求。</span><span class="sxs-lookup"><span data-stu-id="2dff8-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="2dff8-111">缺乏專業的網路 defenders 強制 SOC 以最有效率的方式運作，而且自動化也是必須的。</span><span class="sxs-lookup"><span data-stu-id="2dff8-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="2dff8-112">Microsoft Power 自動支援完全為該所建立的不同連接器。</span><span class="sxs-lookup"><span data-stu-id="2dff8-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="2dff8-113">您可以在數分鐘內建立端對端程式自動化。</span><span class="sxs-lookup"><span data-stu-id="2dff8-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="2dff8-114">Microsoft Defender API 具有許多功能的官方流程連接器。</span><span class="sxs-lookup"><span data-stu-id="2dff8-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![編輯 credentials1 的影像](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="2dff8-116">如需有關高階 connector 授權必要條件的詳細資訊，請參閱 [優質連接器的授權](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)。</span><span class="sxs-lookup"><span data-stu-id="2dff8-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="2dff8-117">使用範例</span><span class="sxs-lookup"><span data-stu-id="2dff8-117">Usage example</span></span>

<span data-ttu-id="2dff8-118">下列範例會示範如何建立每當租使用者在租使用者上發生新警示時所觸發的流程。</span><span class="sxs-lookup"><span data-stu-id="2dff8-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="2dff8-119">登入 [Microsoft Power 自動功能](https://flow.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="2dff8-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="2dff8-120">從空白移至 [**我的流程**]  >  （**新增**  >  **）**。</span><span class="sxs-lookup"><span data-stu-id="2dff8-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![編輯 credentials2 的影像](images/api-flow-1.png)

3. <span data-ttu-id="2dff8-122">選擇您流程的名稱，並搜尋「Microsoft Defender ATP Trigger」做為觸發器，然後選取新的警示觸發。</span><span class="sxs-lookup"><span data-stu-id="2dff8-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![編輯 credentials3 的影像](images/api-flow-2.png)

<span data-ttu-id="2dff8-124">現在，您已有一個流程會在每次發生新警示時觸發。</span><span class="sxs-lookup"><span data-stu-id="2dff8-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![編輯 credentials4 的影像](images/api-flow-3.png)

<span data-ttu-id="2dff8-126">您現在只需要選擇下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="2dff8-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="2dff8-127">例如，您可以隔離裝置的嚴重性為高，並傳送與其相關的電子郵件時，您可以隔離裝置。</span><span class="sxs-lookup"><span data-stu-id="2dff8-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="2dff8-128">警示觸發器只會提供警示識別碼和電腦識別碼。</span><span class="sxs-lookup"><span data-stu-id="2dff8-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="2dff8-129">您可以使用連接器來展開這些實體。</span><span class="sxs-lookup"><span data-stu-id="2dff8-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="2dff8-130">使用連接器取得警示實體</span><span class="sxs-lookup"><span data-stu-id="2dff8-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="2dff8-131">選擇 [ **Microsoft DEFENDER ATP** ] 做為新步驟。</span><span class="sxs-lookup"><span data-stu-id="2dff8-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="2dff8-132">選擇 [ **警示-取得單一警示 API**]。</span><span class="sxs-lookup"><span data-stu-id="2dff8-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="2dff8-133">設定最後一個步驟中的 **警示識別碼** 做為 **輸入**。</span><span class="sxs-lookup"><span data-stu-id="2dff8-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![編輯 credentials5 的影像](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="2dff8-135">在警示嚴重性很高時隔離裝置</span><span class="sxs-lookup"><span data-stu-id="2dff8-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="2dff8-136">將 **條件** 新增為新步驟。</span><span class="sxs-lookup"><span data-stu-id="2dff8-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="2dff8-137">檢查警示嚴重性是否 **等於** High。</span><span class="sxs-lookup"><span data-stu-id="2dff8-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="2dff8-138">如果是，請使用電腦識別碼和批註新增 **Microsoft DEFENDER ATP 隔離的電腦** 動作。</span><span class="sxs-lookup"><span data-stu-id="2dff8-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![編輯 credentials6 的影像](images/api-flow-5.png)

3. <span data-ttu-id="2dff8-140">為有關預警和隔離的電子郵件新增步驟。</span><span class="sxs-lookup"><span data-stu-id="2dff8-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="2dff8-141">有多個可輕鬆使用的電子郵件連接器，例如 Outlook 或 Gmail。</span><span class="sxs-lookup"><span data-stu-id="2dff8-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="2dff8-142">儲存您的流程。</span><span class="sxs-lookup"><span data-stu-id="2dff8-142">Save your flow.</span></span>

<span data-ttu-id="2dff8-143">您也可以建立執行高級搜尋查詢的 **排程** 流程，以及更多！</span><span class="sxs-lookup"><span data-stu-id="2dff8-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="2dff8-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="2dff8-144">Related topic</span></span>
- [<span data-ttu-id="2dff8-145">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="2dff8-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
