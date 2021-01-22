---
title: 為攻擊模擬訓練建立裝載
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解如何在 Microsoft Defender for Office 365 中建立攻擊模擬訓練的自訂裝載。
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929187"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="7b530-103">建立攻擊模擬訓練的自訂承載</span><span class="sxs-lookup"><span data-stu-id="7b530-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="7b530-104">Microsoft 針對各種社交工程技術提供強大的負載目錄，以搭配您的攻擊模擬訓練。</span><span class="sxs-lookup"><span data-stu-id="7b530-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="7b530-105">不過，您可能會想要建立更適用于貴組織的自訂裝載。</span><span class="sxs-lookup"><span data-stu-id="7b530-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="7b530-106">本文將說明如何在 Microsoft Defender for Office 365 中建立攻擊模擬訓練的裝載。</span><span class="sxs-lookup"><span data-stu-id="7b530-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="7b530-107">您可以按一下專用之攜帶點或模擬建立精靈中的建立要載人，以建立[負載](attack-simulation-training.md#selecting-a-payload)。 [  ](https://security.microsoft.com/attacksimulator?viewid=payload)</span><span class="sxs-lookup"><span data-stu-id="7b530-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="7b530-108">精靈的第一個步驟會提供您選取一種負載類型。</span><span class="sxs-lookup"><span data-stu-id="7b530-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="7b530-109">**目前僅提供電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="7b530-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="7b530-110">接下來，選取相關的技巧。</span><span class="sxs-lookup"><span data-stu-id="7b530-110">Next, select an associated technique.</span></span> <span data-ttu-id="7b530-111">請參閱選取社交工程 [技巧以瞭解有關技巧的詳細資訊](attack-simulation-training.md#selecting-a-social-engineering-technique)。</span><span class="sxs-lookup"><span data-stu-id="7b530-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="7b530-112">在下一個步驟中，為任務命名。</span><span class="sxs-lookup"><span data-stu-id="7b530-112">In the next step name your payload.</span></span> <span data-ttu-id="7b530-113">或者，您可以為它提供描述。</span><span class="sxs-lookup"><span data-stu-id="7b530-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="7b530-114">設定負載</span><span class="sxs-lookup"><span data-stu-id="7b530-114">Configure payload</span></span>

<span data-ttu-id="7b530-115">現在該建立您的負荷了。</span><span class="sxs-lookup"><span data-stu-id="7b530-115">Now it's time to build your payload.</span></span> <span data-ttu-id="7b530-116">在寄件者詳細資料區段輸入寄件者的名稱、電子郵件地址和 **電子郵件的主體** 。</span><span class="sxs-lookup"><span data-stu-id="7b530-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="7b530-117">從提供的清單中挑選網路釣魚 URL。</span><span class="sxs-lookup"><span data-stu-id="7b530-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="7b530-118">此 URL 稍後會內嵌在郵件本文中。</span><span class="sxs-lookup"><span data-stu-id="7b530-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="7b530-119">您可以選擇要裝載之寄件者的內部電子郵件，讓這個裝載顯示為來自公司另一個員工。</span><span class="sxs-lookup"><span data-stu-id="7b530-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="7b530-120">這將提高對於負載的敏感度，並有助於教育員工內部威脅的風險。</span><span class="sxs-lookup"><span data-stu-id="7b530-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="7b530-121">豐富的文字編輯器可用於建立您的負載。</span><span class="sxs-lookup"><span data-stu-id="7b530-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="7b530-122">您也可以事先匯出已建立的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7b530-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="7b530-123">當您建立電子郵件內內容時，請利用動態標記，將電子郵件個人化至您的目標。</span><span class="sxs-lookup"><span data-stu-id="7b530-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="7b530-124">按一下 **網路釣魚連結** ，將先前選取的網路釣魚 URL 新增到郵件內文。</span><span class="sxs-lookup"><span data-stu-id="7b530-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Microsoft Defender for Office 365 在建立負載時反顯示網路釣魚連結和動態標記](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="7b530-126">若要節省時間，請開啟選項，以網路釣魚連結取代電子郵件訊息 **中所有的連結**。</span><span class="sxs-lookup"><span data-stu-id="7b530-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="7b530-127">在您建立完喜歡的負荷後，按一下 [下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="7b530-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="7b530-128">新增標記</span><span class="sxs-lookup"><span data-stu-id="7b530-128">Adding indicators</span></span>

<span data-ttu-id="7b530-129">標記可協助員工在受到攻擊時瞭解可以在未來攻擊中尋找的線索。</span><span class="sxs-lookup"><span data-stu-id="7b530-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="7b530-130">若要開始，請按一下 [ **新增標記**。</span><span class="sxs-lookup"><span data-stu-id="7b530-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="7b530-131">從下拉式清單中選取您目前所要使用標記。</span><span class="sxs-lookup"><span data-stu-id="7b530-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="7b530-132">此清單已過策展，包含網路釣魚電子郵件訊息中最常見的線索。</span><span class="sxs-lookup"><span data-stu-id="7b530-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="7b530-133">選取後，請確定標記位置設定為 [從電子郵件本文中選取文字，然後按一下 **選取文字**。</span><span class="sxs-lookup"><span data-stu-id="7b530-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="7b530-134">將這個標記出現時，將您攜帶的一部分強調顯示，然後按一下 [ **選取**。</span><span class="sxs-lookup"><span data-stu-id="7b530-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![郵件內文中以強調顯示的文字，以在攻擊模擬訓練中新增標記](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="7b530-136">新增自訂描述來描述標記，然後按一下標記預覽框架，即可查看標記的預覽。</span><span class="sxs-lookup"><span data-stu-id="7b530-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="7b530-137">完成後，按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="7b530-137">Once done, click **Add**.</span></span> <span data-ttu-id="7b530-138">重複這些步驟，直到涵蓋您負載中所有的標記。</span><span class="sxs-lookup"><span data-stu-id="7b530-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="7b530-139">重閱負載</span><span class="sxs-lookup"><span data-stu-id="7b530-139">Review payload</span></span>

<span data-ttu-id="7b530-140">您已完成建立您的負荷。</span><span class="sxs-lookup"><span data-stu-id="7b530-140">You're done building your payload.</span></span> <span data-ttu-id="7b530-141">現在該是檢查詳細資料，並預覽您負載的時間了。</span><span class="sxs-lookup"><span data-stu-id="7b530-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="7b530-142">預覽會包含您建立的所有標記。</span><span class="sxs-lookup"><span data-stu-id="7b530-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="7b530-143">您可以編輯此步驟中的每個負載部分。</span><span class="sxs-lookup"><span data-stu-id="7b530-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="7b530-144">一旦獲得滿足，您可以 **提交** 您的裝載。</span><span class="sxs-lookup"><span data-stu-id="7b530-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b530-145">您建立之裝載會以 **租使用者** 做為來源。</span><span class="sxs-lookup"><span data-stu-id="7b530-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="7b530-146">選取負載時，請確認您沒有篩選出租 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="7b530-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="7b530-147">相關連結</span><span class="sxs-lookup"><span data-stu-id="7b530-147">Related links</span></span>

[<span data-ttu-id="7b530-148">開始使用攻擊模擬訓練</span><span class="sxs-lookup"><span data-stu-id="7b530-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="7b530-149">建立網路釣魚攻擊模擬</span><span class="sxs-lookup"><span data-stu-id="7b530-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="7b530-150">透過攻擊模擬訓練取得深入解析</span><span class="sxs-lookup"><span data-stu-id="7b530-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
