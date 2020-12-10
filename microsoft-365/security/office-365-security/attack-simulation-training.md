---
title: 使用 Microsoft Defender 來模擬網路的網路釣魚攻擊
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
description: 瞭解如何模擬網路釣魚攻擊，並使用 Microsoft Defender for Office 365 中的攻擊模擬訓練，訓練您的使用者網路釣魚防護。
ms.openlocfilehash: 8f5f457f60c81fe961282f33bb8c37f4d9e27aab
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616101"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="68019-103">模擬網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="68019-103">Simulate a phishing attack</span></span>

<span data-ttu-id="68019-104">透過 Microsoft Defender for Office 365 的攻擊模擬器訓練可讓您在組織上執行良性網路攻擊模擬，以測試您的安全性原則和作法，以及訓練組織的員工以提升其知名度，並減少對攻擊的敏感程度。</span><span class="sxs-lookup"><span data-stu-id="68019-104">Attack simulator training through Microsoft Defender for Office 365 lets you run benign cyber attack simulations on your organization to test your security policies and practices, as well as train the employees of your organization to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="68019-105">下列步驟會引導您使用攻擊模擬器訓練來模擬網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="68019-105">The following walks you through simulating a phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="68019-106">若要啟動模擬網路釣魚攻擊，請流覽至 [Microsoft 365 的安全性中心](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="68019-106">To launch a simulated phishing attack, navigate to the [Microsoft 365 security center](https://security.microsoft.com/).</span></span> <span data-ttu-id="68019-107">在 [ **電子郵件 &** 共同作業] 底下，按一下 **攻擊模擬器** 上的 [ [**模擬**](https://security.microsoft.com/attacksimulator?viewid=simulations) ]，然後切換至 [</span><span class="sxs-lookup"><span data-stu-id="68019-107">Under **Email & collaboration** click on **Attack simulator** and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="68019-108">在 [ **類比** ] 下，選取 [ **啟動類比**]。</span><span class="sxs-lookup"><span data-stu-id="68019-108">Under **Simulations** select **+ Launch a simulation**.</span></span>

![在 Microsoft 365 的安全性中心啟動模擬按鈕](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="68019-110">在類比建立過程中的任何時刻，您都可以儲存並關閉，繼續進行類比。</span><span class="sxs-lookup"><span data-stu-id="68019-110">At any point during simulation creation you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="68019-111">選取社交工程技術</span><span class="sxs-lookup"><span data-stu-id="68019-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="68019-112">從4個不同的技術中，策劃 [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="68019-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="68019-113">不同的負載可用於不同的技術。</span><span class="sxs-lookup"><span data-stu-id="68019-113">Different payloads are available for different techniques.</span></span>

- <span data-ttu-id="68019-114">**認證搜集** 會嘗試透過使用輸入方塊送出使用者名稱和密碼，以取得員工的身分識別的網站來收集認證。</span><span class="sxs-lookup"><span data-stu-id="68019-114">**Credential harvest** attempts to collect credentials from employees by taking them to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="68019-115">**惡意程式碼附件** 會將惡意附件加入郵件。</span><span class="sxs-lookup"><span data-stu-id="68019-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="68019-116">開啟時，這個附件會執行一些可協助攻擊者損害目標裝置的任意程式碼。</span><span class="sxs-lookup"><span data-stu-id="68019-116">When opened, this attachment will run some arbitrary code that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="68019-117">**附件中的連結** 是一種混合式認證的類型。</span><span class="sxs-lookup"><span data-stu-id="68019-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="68019-118">攻擊者會將 URL 插入電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="68019-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="68019-119">附件內的 URL 與認證探索所遵循的技術相同。</span><span class="sxs-lookup"><span data-stu-id="68019-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="68019-120">**連結至惡意** 代碼會從眾所周知的檔案共用網站上的檔案執行一些任意程式碼。</span><span class="sxs-lookup"><span data-stu-id="68019-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file-sharing site.</span></span> <span data-ttu-id="68019-121">此惡意檔案的連結會新增至傳送至目標的郵件，然後按一下此連結會執行該檔案，並協助攻擊者損害目標裝置。</span><span class="sxs-lookup"><span data-stu-id="68019-121">A link to this malicious file is added to the message sent to the target and clicking it will run the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="68019-122">按一下每個技術說明中的 [ **查看詳細資料** ]，可顯示技術的進一步資訊，以及該技巧的類比步驟。</span><span class="sxs-lookup"><span data-stu-id="68019-122">Clicking on **View details** within the description of each technique will display further information about the technique as well as the simulation steps for that technique.</span></span>
>
> ![Microsoft 365 安全中心內的認證模擬訓練中認證的類比步驟](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="68019-124">當您選取了該方法並按一下 **[下一步]** ，便會提供類比名稱和選擇性的描述。</span><span class="sxs-lookup"><span data-stu-id="68019-124">Once you've selected the technique and clicked on **Next** give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="68019-125">選取負載</span><span class="sxs-lookup"><span data-stu-id="68019-125">Selecting a payload</span></span>

<span data-ttu-id="68019-126">接下來，您必須從預先存在的負載目錄中選取負載。</span><span class="sxs-lookup"><span data-stu-id="68019-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="68019-127">負載具有許多可協助您選擇的資料點：</span><span class="sxs-lookup"><span data-stu-id="68019-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="68019-128">**按一下 [流量** 計數] 按此負載的人數。</span><span class="sxs-lookup"><span data-stu-id="68019-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="68019-129">**預測的折衷率** 會根據此負載在 Microsoft Defender for Office 365 客戶上的歷史資料，預測此負載會危及之人員的百分比。</span><span class="sxs-lookup"><span data-stu-id="68019-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historic data for this payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="68019-130">**模擬已啟動** 計算此負載在其他類比中使用的次數。</span><span class="sxs-lookup"><span data-stu-id="68019-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="68019-131">可透過 **篩選器** 使用的 **複雜性**，是根據在其指示其為攻擊之目標的負載內的指標數目來計算。</span><span class="sxs-lookup"><span data-stu-id="68019-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="68019-132">更多指示器會導致較低的複雜性。</span><span class="sxs-lookup"><span data-stu-id="68019-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="68019-133">**來源**（透過 **篩選器** 提供）會指出是否已在您的租使用者上建立負載，或是 Microsoft 預先存在的負載目錄 (全域) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="68019-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Microsoft 365 security center 中的攻擊模擬訓練中所選的負載](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="68019-135">從清單中選取一個負載，以查看具有其相關詳細資訊的負載預覽。</span><span class="sxs-lookup"><span data-stu-id="68019-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="68019-136">如果您想要建立自己的負載，請參閱 [建立攻擊模擬訓練的負載](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="68019-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="68019-137">對象目標</span><span class="sxs-lookup"><span data-stu-id="68019-137">Audience targeting</span></span>

<span data-ttu-id="68019-138">現在請選擇此模擬的物件。</span><span class="sxs-lookup"><span data-stu-id="68019-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="68019-139">您可以選擇 **包含組織中的所有使用者** ，或 **只包含特定的使用者和群組**。</span><span class="sxs-lookup"><span data-stu-id="68019-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="68019-140">當您選擇 **只包含特定的使用者和群組** 時，您可以執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="68019-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="68019-141">**新增使用者**，可讓您利用租使用者的搜尋功能，以及高級搜尋和篩選功能，例如以過去3個月內模擬的目標使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="68019-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="68019-142">![Microsoft 365 安全中心的攻擊模擬訓練中的使用者篩選](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="68019-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="68019-143">**從 CSV 匯入** 可讓您為此模擬匯入一組預先定義的使用者。</span><span class="sxs-lookup"><span data-stu-id="68019-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="68019-144">指派訓練</span><span class="sxs-lookup"><span data-stu-id="68019-144">Assigning training</span></span>

<span data-ttu-id="68019-145">建議您指派每個類比的訓練，因為參加訓練的員工會不易遭受類似的攻擊。</span><span class="sxs-lookup"><span data-stu-id="68019-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="68019-146">您可以選擇將訓練指派給您或自行選擇訓練課程和模組。</span><span class="sxs-lookup"><span data-stu-id="68019-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="68019-147">選取 [ **訓練到期日** ]，確定員工及時完成訓練。</span><span class="sxs-lookup"><span data-stu-id="68019-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="68019-148">如果您選擇自行選取課程和模組，您仍然可以查看建議的內容，以及所有可用的課程和模組。</span><span class="sxs-lookup"><span data-stu-id="68019-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![在 Microsoft 365 安全中心的攻擊模擬訓練中新增建議訓練](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="68019-150">在後續步驟中，如果您選擇自行自行選擇訓練，您將需要 **新增** 訓練，並自訂訓練登陸頁面。</span><span class="sxs-lookup"><span data-stu-id="68019-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="68019-151">您可以預覽 [訓練] 登陸頁面，也可以變更其頁首和本文。</span><span class="sxs-lookup"><span data-stu-id="68019-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="68019-152">發佈詳細資料和評論</span><span class="sxs-lookup"><span data-stu-id="68019-152">Launch details and review</span></span>

<span data-ttu-id="68019-153">現在已設定所有內容，您可以立即啟動這項類比，也可以在稍後的日期排程。</span><span class="sxs-lookup"><span data-stu-id="68019-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="68019-154">您也必須選擇何時結束此模擬。</span><span class="sxs-lookup"><span data-stu-id="68019-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="68019-155">在選取的時間之後，我們將停止與此模擬進行的捕捉互動。</span><span class="sxs-lookup"><span data-stu-id="68019-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="68019-156">**啟用地區感知時區傳遞** ，以根據地區的工作時間，將模擬的攻擊訊息傳遞給您的員工。</span><span class="sxs-lookup"><span data-stu-id="68019-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="68019-157">完成後，請按一下 **[下一步]** 並查看類比的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="68019-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="68019-158">在任何要回復的元件上按一下 [ **編輯** ]，然後變更任何需要變更的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="68019-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="68019-159">完成後，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="68019-159">Once done, click **Submit**.</span></span>
