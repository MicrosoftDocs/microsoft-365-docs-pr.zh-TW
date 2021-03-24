---
title: 使用 Microsoft Defender for Office 365 模擬網路釣魚攻擊
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解如何使用 Microsoft Defender for Office 365 中的攻擊模擬訓練訓練，以模擬網路釣魚攻擊及訓練使用者。
ms.technology: mdo
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059000"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="ba0ee-103">模擬網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="ba0ee-103">Simulate a phishing attack</span></span>

<span data-ttu-id="ba0ee-104">Microsoft Defender for Office 365 中的攻擊模擬訓練可讓您在組織上執行良性 cyberattack 模擬，以測試您的安全性原則和做法，並訓練員工以提升其知名度，並減少對攻擊的敏感程度。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="ba0ee-105">本文將引導您使用攻擊模擬訓練來建立模擬網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="ba0ee-106">如需有關攻擊模擬訓練的快速入門資訊，請參閱 [開始使用攻擊模擬訓練](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="ba0ee-107">若要啟動模擬網路釣魚攻擊，請開啟 [Microsoft 365 的安全性中心](https://security.microsoft.com/)，移至 [ **電子郵件 &** 共同作業 \> **攻擊模擬訓練**]，然後切換至 [ [**類比**](https://security.microsoft.com/attacksimulator?viewid=simulations) ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="ba0ee-108">在 [ **類比**] 底下，選取 [ **+ 發射類比**]。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![在 Microsoft 365 的安全性中心啟動模擬按鈕](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="ba0ee-110">在類比建立過程中的任何一點，您都可以儲存並關閉，繼續進行類比。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="ba0ee-111">選取社交工程技術</span><span class="sxs-lookup"><span data-stu-id="ba0ee-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="ba0ee-112">從4個不同的技術中，策劃 [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="ba0ee-113">不同的負載可用於不同的技術：</span><span class="sxs-lookup"><span data-stu-id="ba0ee-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="ba0ee-114">**認證搜集** 會透過讓使用者進入眾所周知的網站，並使用輸入方塊送出使用者名稱和密碼來收集認證。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="ba0ee-115">**惡意程式碼附件** 會將惡意附件加入郵件。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="ba0ee-116">當使用者開啟附件時，會執行任意程式碼，以協助攻擊者損害目標裝置。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="ba0ee-117">**附件中的連結** 是一種混合式認證的類型。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="ba0ee-118">攻擊者會將 URL 插入電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="ba0ee-119">附件內的 URL 與認證探索所遵循的技術相同。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="ba0ee-120">**連結至惡意** 代碼會從眾所周知的檔案共用服務上的檔案執行一些任意程式碼。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="ba0ee-121">傳送給使用者的郵件將會包含此惡意檔案的連結。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="ba0ee-122">開啟檔案，協助攻擊者損害目標裝置。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-122">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="ba0ee-123">[**磁片磁碟機 url** ] 是指郵件中的惡意 url 讓使用者進入熟悉的網站，該網站會以無訊息的方式執行，並/或在使用者的裝置上安裝程式碼代碼。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-123">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="ba0ee-124">按一下每個技術說明中的 [ **查看詳細資料** ]，可顯示進一步的資訊及類比步驟的技術。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-124">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Microsoft 365 安全中心內的認證模擬訓練中認證的類比步驟](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="ba0ee-126">選取好技術並按一下 **[下一步]** 之後，請提供類比名稱並選擇性地提供描述。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-126">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="ba0ee-127">選取負載</span><span class="sxs-lookup"><span data-stu-id="ba0ee-127">Selecting a payload</span></span>

<span data-ttu-id="ba0ee-128">接下來，您必須從預先存在的負載目錄中選取負載。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-128">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="ba0ee-129">負載具有許多可協助您選擇的資料點：</span><span class="sxs-lookup"><span data-stu-id="ba0ee-129">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="ba0ee-130">**按一下 [流量** 計數] 按此負載的人數。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-130">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="ba0ee-131">**預測的折衷率** 會根據 Microsoft Defender for Office 365 客戶的負載，預測此負載會危及之人員的百分比。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-131">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="ba0ee-132">**模擬已啟動** 計算此負載在其他類比中使用的次數。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-132">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="ba0ee-133">可透過 **篩選器** 使用的 **複雜性**，是根據在其指示其為攻擊之目標的負載內的指標數目來計算。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-133">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="ba0ee-134">更多指示器會導致較低的複雜性。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-134">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="ba0ee-135">**來源**（透過 **篩選器** 提供）會指出是否已在您的租使用者上建立負載，或是 Microsoft 預先存在的負載目錄 (全域) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-135">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Microsoft 365 security center 中的攻擊模擬訓練中所選的負載](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="ba0ee-137">從清單中選取一個負載，以查看具有其相關詳細資訊的負載預覽。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-137">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="ba0ee-138">如果您想要建立自己的負載，請參閱 [建立攻擊模擬訓練的負載](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-138">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="ba0ee-139">對象目標</span><span class="sxs-lookup"><span data-stu-id="ba0ee-139">Audience targeting</span></span>

<span data-ttu-id="ba0ee-140">現在請選擇此模擬的物件。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-140">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="ba0ee-141">您可以選擇 **包含組織中的所有使用者** ，或 **只包含特定的使用者和群組**。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-141">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="ba0ee-142">當您選擇 **只包含特定的使用者和群組** 時，您可以執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ba0ee-142">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="ba0ee-143">**新增使用者**，可讓您利用租使用者的搜尋功能，以及高級搜尋和篩選功能，例如以過去3個月內模擬的目標使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-143">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="ba0ee-144">![Microsoft 365 安全中心的攻擊模擬訓練中的使用者篩選](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="ba0ee-144">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="ba0ee-145">**從 CSV 匯入** 可讓您為此模擬匯入一組預先定義的使用者。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-145">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="ba0ee-146">指派訓練</span><span class="sxs-lookup"><span data-stu-id="ba0ee-146">Assigning training</span></span>

<span data-ttu-id="ba0ee-147">建議您指派每個類比的訓練，因為參加訓練的員工會不易遭受類似的攻擊。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-147">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="ba0ee-148">您可以選擇將訓練指派給您或自行選擇訓練課程和模組。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-148">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="ba0ee-149">選取 [ **訓練到期日** ]，確定員工及時完成訓練。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-149">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="ba0ee-150">如果您選擇自行選取課程和模組，您仍然可以查看建議的內容，以及所有可用的課程和模組。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-150">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![在 Microsoft 365 安全中心的攻擊模擬訓練中新增建議訓練](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="ba0ee-152">在後續步驟中，如果您選擇自行自行選擇訓練，您將需要 **新增** 訓練，並自訂訓練登陸頁面。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-152">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="ba0ee-153">您可以預覽 [訓練] 登陸頁面，也可以變更其頁首和本文。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-153">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="ba0ee-154">發佈詳細資料和評論</span><span class="sxs-lookup"><span data-stu-id="ba0ee-154">Launch details and review</span></span>

<span data-ttu-id="ba0ee-155">現在已設定所有內容，您可以立即啟動這項類比，也可以在稍後的日期排程。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-155">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="ba0ee-156">您也必須選擇何時結束此模擬。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-156">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="ba0ee-157">在選取的時間之後，我們將停止與此模擬進行的捕捉互動。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-157">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="ba0ee-158">**啟用地區感知時區傳遞** ，以根據地區的工作時間，將模擬的攻擊訊息傳遞給您的員工。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-158">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="ba0ee-159">完成後，請按一下 **[下一步]** 並查看類比的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-159">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="ba0ee-160">在任何要回復的元件上按一下 [ **編輯** ]，然後變更任何需要變更的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-160">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="ba0ee-161">完成後，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="ba0ee-161">Once done, click **Submit**.</span></span>
