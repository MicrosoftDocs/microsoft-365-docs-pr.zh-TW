---
title: 設定 Microsoft Defender 防毒軟體 cloud block 超時期間
description: 您可以設定 Microsoft Defender 防毒軟體會封鎖檔案在等候雲端決定時執行的時間長度。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，cloud，timeout，block，period，seconds
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789084"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="964b1-104">設定雲端封鎖逾時期間</span><span class="sxs-lookup"><span data-stu-id="964b1-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="964b1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="964b1-105">**Applies to:**</span></span>

- [<span data-ttu-id="964b1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="964b1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="964b1-107">當 Microsoft Defender 防毒軟體發現可疑的檔案時，它會在查詢[Microsoft Defender 防毒軟體雲端服務](cloud-protection-microsoft-defender-antivirus.md)時，防止檔案執行。</span><span class="sxs-lookup"><span data-stu-id="964b1-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="964b1-108">[封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md)檔的預設週期為10秒。</span><span class="sxs-lookup"><span data-stu-id="964b1-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="964b1-109">如果您是安全性管理員，您可以指定在允許檔案執行之前所等候的時間。</span><span class="sxs-lookup"><span data-stu-id="964b1-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="964b1-110">擴充雲端封鎖超時期限可協助確保有足夠的時間從 Microsoft Defender 防毒軟體雲端服務接收適當的判斷。</span><span class="sxs-lookup"><span data-stu-id="964b1-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="964b1-111">使用擴展雲端封鎖超時的必要條件</span><span class="sxs-lookup"><span data-stu-id="964b1-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="964b1-112">[在第一次看到時會封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md) ，必須先啟用其必要條件，您才能指定延長的超時期限。</span><span class="sxs-lookup"><span data-stu-id="964b1-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="964b1-113">使用 Microsoft 端點管理員指定延長的超時期間</span><span class="sxs-lookup"><span data-stu-id="964b1-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="964b1-114">您可以[在 Microsoft 端點管理員中指定包含端點安全性原則](/mem/intune/protect/endpoint-security-policy)的雲端封鎖超時期限。</span><span class="sxs-lookup"><span data-stu-id="964b1-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="964b1-115">請移至端點管理員系統管理中心 ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="964b1-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="964b1-116">選取 [ **端點安全性**]，然後在 [ **管理**] 下選擇 [ **防病毒**]。</span><span class="sxs-lookup"><span data-stu-id="964b1-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="964b1-117">選取 [ (] 或 [建立) 防病毒原則]。</span><span class="sxs-lookup"><span data-stu-id="964b1-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="964b1-118">在 [ **設定設定** ] 區段中，展開 [ **Cloud protection**]。</span><span class="sxs-lookup"><span data-stu-id="964b1-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="964b1-119">然後，在 [ **Defender Cloud Extended Timeout** Time （秒）] 方塊中，指定從1秒到50秒的時間（秒）。</span><span class="sxs-lookup"><span data-stu-id="964b1-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="964b1-120">您指定的任何內容都會新增至預設的10秒。</span><span class="sxs-lookup"><span data-stu-id="964b1-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="964b1-121"> (此步驟是選用的) 對防病毒原則進行其他變更。</span><span class="sxs-lookup"><span data-stu-id="964b1-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="964b1-122"> (需要協助嗎？</span><span class="sxs-lookup"><span data-stu-id="964b1-122">(Need help?</span></span> <span data-ttu-id="964b1-123">請參閱[Microsoft Intune 中 Microsoft Defender 防毒軟體原則的設定](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)。 ) </span><span class="sxs-lookup"><span data-stu-id="964b1-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="964b1-124">選擇 **[下一步**]，然後完成原則的設定。</span><span class="sxs-lookup"><span data-stu-id="964b1-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="964b1-125">使用群組原則指定擴充的超時週期</span><span class="sxs-lookup"><span data-stu-id="964b1-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="964b1-126">您可以使用群組原則指定用於雲端檢查的延伸超時。</span><span class="sxs-lookup"><span data-stu-id="964b1-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="964b1-127">在您的群組原則管理電腦上，開啟「[群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))」</span><span class="sxs-lookup"><span data-stu-id="964b1-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="964b1-128">以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="964b1-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="964b1-129">在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="964b1-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="964b1-130">展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **MpEngine**。</span><span class="sxs-lookup"><span data-stu-id="964b1-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="964b1-131">按兩下 [ **設定擴展的雲端檢查** ]，並確定已啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="964b1-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="964b1-132">指定在等待雲端決定時，防止檔案執行的額外時間長度。</span><span class="sxs-lookup"><span data-stu-id="964b1-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="964b1-133">指定從1秒到50秒之間的額外時間（秒）。</span><span class="sxs-lookup"><span data-stu-id="964b1-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="964b1-134">您指定的任何內容都會新增至預設的10秒。</span><span class="sxs-lookup"><span data-stu-id="964b1-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="964b1-135">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="964b1-135">Select **OK**.</span></span>

 