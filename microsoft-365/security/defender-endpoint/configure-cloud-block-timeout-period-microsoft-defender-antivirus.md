---
title: 設定 Microsoft Defender 防毒軟體雲端封鎖的超時期限
description: 您可以設定 Microsoft Defender 防毒程式在等待雲端決定時，封鎖檔案執行的時間。
keywords: Microsoft Defender 防毒程式，反惡意程式碼，安全性，Defender，cloud，timeout，組塊，period，seconds
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690123"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="d9a59-104">設定雲端封鎖超時期限</span><span class="sxs-lookup"><span data-stu-id="d9a59-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9a59-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d9a59-105">**Applies to:**</span></span>

- [<span data-ttu-id="d9a59-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d9a59-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d9a59-107">當 Microsoft Defender 防毒程式發現可疑檔案時，它會在查詢 [Microsoft Defender 防毒軟體雲端服務](cloud-protection-microsoft-defender-antivirus.md)時，防止檔案執行。</span><span class="sxs-lookup"><span data-stu-id="d9a59-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="d9a59-108">會 [封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md) 檔案的預設週期為10秒。</span><span class="sxs-lookup"><span data-stu-id="d9a59-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="d9a59-109">您可以指定在允許檔案執行之前所等候的其他時間週期。</span><span class="sxs-lookup"><span data-stu-id="d9a59-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="d9a59-110">這可協助確保有足夠的時間接收 Microsoft Defender 防毒軟體雲端服務的適當判斷。</span><span class="sxs-lookup"><span data-stu-id="d9a59-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="d9a59-111">使用擴展雲端封鎖超時的必要條件</span><span class="sxs-lookup"><span data-stu-id="d9a59-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="d9a59-112">[在第一次看到時會封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md) ，必須先啟用其必要條件，您才能指定延長的超時期限。</span><span class="sxs-lookup"><span data-stu-id="d9a59-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="d9a59-113">指定延長的超時期限</span><span class="sxs-lookup"><span data-stu-id="d9a59-113">Specify the extended timeout period</span></span>

<span data-ttu-id="d9a59-114">您可以使用群組原則指定用於雲端檢查的延伸超時。</span><span class="sxs-lookup"><span data-stu-id="d9a59-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="d9a59-115">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d9a59-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="d9a59-116">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="d9a59-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="d9a59-117">在 **Microsoft Defender 防病毒 > MpEngine** 中，展開樹狀目錄至 Windows 元件 ></span><span class="sxs-lookup"><span data-stu-id="d9a59-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="d9a59-118">按兩下 [ **設定擴展的雲端檢查** ]，並確定已啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="d9a59-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="d9a59-119">指定在等待雲端決定時，防止檔案執行的額外時間長度。</span><span class="sxs-lookup"><span data-stu-id="d9a59-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="d9a59-120">您可以指定從1秒到50秒之間的額外時間（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="d9a59-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="d9a59-121">此時間將會新增至預設的10秒。</span><span class="sxs-lookup"><span data-stu-id="d9a59-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="d9a59-122">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="d9a59-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9a59-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="d9a59-123">Related topics</span></span>

- [<span data-ttu-id="d9a59-124">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d9a59-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d9a59-125">透過雲端提供的保護來使用下一代防病毒技術</span><span class="sxs-lookup"><span data-stu-id="d9a59-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d9a59-126">設定初次看到的封鎖</span><span class="sxs-lookup"><span data-stu-id="d9a59-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d9a59-127">啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="d9a59-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)