---
title: 建立攻擊模擬訓練的負載
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 瞭解如何在 Microsoft Defender for Office 365 中建立攻擊模擬訓練的自訂負載。
ms.openlocfilehash: a8366e6cbf703ef1e1a14e216ada71200668cd14
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616269"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="efbc9-103">建立攻擊模擬訓練的自訂承載</span><span class="sxs-lookup"><span data-stu-id="efbc9-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="efbc9-104">Microsoft 會提供強大的負載目錄，以用於各種社交工程技術，以與您的攻擊模擬訓練進行配對。</span><span class="sxs-lookup"><span data-stu-id="efbc9-104">Microsoft offer a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="efbc9-105">不過，您可能會想要建立更適合貴組織的自訂負載。</span><span class="sxs-lookup"><span data-stu-id="efbc9-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="efbc9-106">下列說明如何透過 Microsoft Defender for Office 365 在攻擊模擬訓練中建立負載。</span><span class="sxs-lookup"><span data-stu-id="efbc9-106">The following describes how to create a payload in attack simulation training through Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="efbc9-107">您可以按一下 [[專用 **負載**]](https://security.microsoft.com/attacksimulator?viewid=payload)索引標籤或 [[類比建立嚮導]](attack-simulation-training.md#selecting-a-payload)中的 [**建立負載**]，以建立負載。</span><span class="sxs-lookup"><span data-stu-id="efbc9-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="efbc9-108">嚮導的第一個步驟會選取一種負載類型。</span><span class="sxs-lookup"><span data-stu-id="efbc9-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="efbc9-109">**目前只有電子郵件可供使用**。</span><span class="sxs-lookup"><span data-stu-id="efbc9-109">**Currently only email is available**.</span></span>

<span data-ttu-id="efbc9-110">接下來，選取相關聯的技術。</span><span class="sxs-lookup"><span data-stu-id="efbc9-110">Next, select an associated technique.</span></span> <span data-ttu-id="efbc9-111">在 [選擇社交工程技術](attack-simulation-training.md#selecting-a-social-engineering-technique)時，請參閱技巧的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="efbc9-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="efbc9-112">在下一個步驟中，為您的負載命名。</span><span class="sxs-lookup"><span data-stu-id="efbc9-112">In the next step name your payload.</span></span> <span data-ttu-id="efbc9-113">您也可以選擇提供描述。</span><span class="sxs-lookup"><span data-stu-id="efbc9-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="efbc9-114">設定有效載荷</span><span class="sxs-lookup"><span data-stu-id="efbc9-114">Configure payload</span></span>

<span data-ttu-id="efbc9-115">現在就開始建立您的負載。</span><span class="sxs-lookup"><span data-stu-id="efbc9-115">Now it's time to build your payload.</span></span> <span data-ttu-id="efbc9-116">在 [ **寄件者詳細資料** ] 區段中輸入寄件者的名稱、電子郵件和電子郵件的主旨。</span><span class="sxs-lookup"><span data-stu-id="efbc9-116">Input the sender's name, email and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="efbc9-117">從提供的清單中挑選網路釣魚 URL。</span><span class="sxs-lookup"><span data-stu-id="efbc9-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="efbc9-118">稍後會將此 URL 嵌入郵件的本文中。</span><span class="sxs-lookup"><span data-stu-id="efbc9-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="efbc9-119">您可以為您的載荷寄件者選擇內部電子郵件，這會使該負載顯示為來自公司的其他員工。</span><span class="sxs-lookup"><span data-stu-id="efbc9-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="efbc9-120">這會增加對有效負載的敏感程度，並協助員工對內部威脅的風險進行教育。</span><span class="sxs-lookup"><span data-stu-id="efbc9-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="efbc9-121">可以使用 rtf 文字編輯器來建立您的負載。</span><span class="sxs-lookup"><span data-stu-id="efbc9-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="efbc9-122">您也可以匯入您事先建立的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="efbc9-122">You can also import an email you've created beforehand.</span></span> <span data-ttu-id="efbc9-123">當您構造電子郵件的本文時，請利用 **動態標記** ，將電子郵件自訂至您的目標。</span><span class="sxs-lookup"><span data-stu-id="efbc9-123">As you structure the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="efbc9-124">按一下 [ **網路釣魚連結** ]，將先前所選的網路釣魚 URL 新增至電子郵件的本文中。</span><span class="sxs-lookup"><span data-stu-id="efbc9-124">Click on **Phishing link** to add the previously selected phishing URL into the body of the email.</span></span>

![在 Microsoft Defender for Office 365 的負載建立中，反白顯示網路釣魚連結和動態標記](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="efbc9-126">若要節省一些時間，請切換此選項以 **取代電子郵件中的所有連結與網路釣魚連結**。</span><span class="sxs-lookup"><span data-stu-id="efbc9-126">To save yourself some time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="efbc9-127">當您想要建立負載後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="efbc9-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="efbc9-128">新增指示器</span><span class="sxs-lookup"><span data-stu-id="efbc9-128">Adding indicators</span></span>

<span data-ttu-id="efbc9-129">指標會協助員工透過攻擊模擬，瞭解他們可以在未來的攻擊中尋找的線索。</span><span class="sxs-lookup"><span data-stu-id="efbc9-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="efbc9-130">若要開始，請按一下 [ **新增指示器**]。</span><span class="sxs-lookup"><span data-stu-id="efbc9-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="efbc9-131">從下拉式清單中選取您想要使用的指示器。</span><span class="sxs-lookup"><span data-stu-id="efbc9-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="efbc9-132">這個清單是策劃，包含出現在網路釣魚電子郵件訊息中的最常見的線索。</span><span class="sxs-lookup"><span data-stu-id="efbc9-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="efbc9-133">選取之後，請確定指示器位置已設定為 **從電子郵件的內** 文，然後按一下 [ **選取文字**]。</span><span class="sxs-lookup"><span data-stu-id="efbc9-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="efbc9-134">反白顯示此指標會出現的部分負載，然後按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="efbc9-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![郵件內文中的突出顯示文字，以加入攻擊模擬訓練中的指示器](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="efbc9-136">新增自訂描述以描述指示器，然後按一下指標預覽框架內，以查看指示器預覽。</span><span class="sxs-lookup"><span data-stu-id="efbc9-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="efbc9-137">完成後，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="efbc9-137">Once done, click **Add**.</span></span> <span data-ttu-id="efbc9-138">重複這些步驟，直到您已在您的負載中涵蓋所有指示器為止。</span><span class="sxs-lookup"><span data-stu-id="efbc9-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="efbc9-139">檢查負載</span><span class="sxs-lookup"><span data-stu-id="efbc9-139">Review payload</span></span>

<span data-ttu-id="efbc9-140">您已經完成您的負載的建立。</span><span class="sxs-lookup"><span data-stu-id="efbc9-140">You're done building your payload.</span></span> <span data-ttu-id="efbc9-141">現在請查看詳細資料，並查看您的負載預覽。</span><span class="sxs-lookup"><span data-stu-id="efbc9-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="efbc9-142">預覽會包含您已建立的所有指示器。</span><span class="sxs-lookup"><span data-stu-id="efbc9-142">The preview will include all indicators you've created.</span></span> <span data-ttu-id="efbc9-143">您可以從這個步驟編輯每個部分的負載。</span><span class="sxs-lookup"><span data-stu-id="efbc9-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="efbc9-144">完成後，請 **提交** 您的負載。</span><span class="sxs-lookup"><span data-stu-id="efbc9-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efbc9-145">您已建立的負載會將 **承租人** 設定為其來源。</span><span class="sxs-lookup"><span data-stu-id="efbc9-145">Payloads you've created will have **Tenant** set as their source.</span></span> <span data-ttu-id="efbc9-146">選取 [有效負載] 時，請確定您未篩選出 **租** 使用者。</span><span class="sxs-lookup"><span data-stu-id="efbc9-146">When selecting payloads, make sure you don't have **Tenant** filtered out.</span></span>