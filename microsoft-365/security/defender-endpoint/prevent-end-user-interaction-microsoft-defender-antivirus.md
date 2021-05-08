---
title: 隱藏 Microsoft Defender 防毒軟體介面
description: 您可以在 Windows 安全性應用程式中隱藏病毒和威脅防護磚。
keywords: ui 鎖定、無周邊模式、隱藏應用程式、隱藏設定、隱藏介面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274913"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="7a335-104">防止使用者看到或與 Microsoft Defender 防毒軟體使用者介面互動</span><span class="sxs-lookup"><span data-stu-id="7a335-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7a335-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7a335-105">**Applies to:**</span></span>

- [<span data-ttu-id="7a335-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7a335-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7a335-107">您可以使用群組原則，防止使用者在端點上看到 Microsoft Defender 防毒軟體介面。</span><span class="sxs-lookup"><span data-stu-id="7a335-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="7a335-108">您也可以防止使用者暫停掃描。</span><span class="sxs-lookup"><span data-stu-id="7a335-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="7a335-109">隱藏 Microsoft Defender 防毒軟體介面</span><span class="sxs-lookup"><span data-stu-id="7a335-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="7a335-110">在 Windows 10 中，隱藏介面的版本1703會隱藏 Microsoft Defender 防毒軟體通知，並防止病毒 & 威脅防護磚出現在 Windows 安全性應用程式中。</span><span class="sxs-lookup"><span data-stu-id="7a335-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="7a335-111">設定為 [ **啟用**] 時：</span><span class="sxs-lookup"><span data-stu-id="7a335-111">With the setting set to **Enabled**:</span></span>

![沒有盾牌圖示與病毒和威脅防護區段的 Windows 安全性螢幕擷取畫面](images/defender/wdav-headless-mode-1703.png)

<span data-ttu-id="7a335-113">設定為 [ **停** 用] 或 [未設定] 時：</span><span class="sxs-lookup"><span data-stu-id="7a335-113">With the setting set to **Disabled** or not configured:</span></span>

![顯示盾牌圖示及病毒和威脅防護區段 Windows 安全性的螢幕擷取畫面](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
><span data-ttu-id="7a335-115">隱藏介面也會使 Microsoft Defender 防毒軟體通知不會出現在端點上。</span><span class="sxs-lookup"><span data-stu-id="7a335-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="7a335-116">仍會顯示 Microsoft Defender for Endpoint 通知。</span><span class="sxs-lookup"><span data-stu-id="7a335-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="7a335-117">您也可以個別 [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7a335-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="7a335-118">在舊版的 Windows 10 中，設定會隱藏 Windows Defender 用戶端介面。</span><span class="sxs-lookup"><span data-stu-id="7a335-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="7a335-119">如果使用者嘗試開啟它，他們會收到警告說：「您的系統管理員已限制存取此應用程式」。</span><span class="sxs-lookup"><span data-stu-id="7a335-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

![Windows 10 中的無周邊模式啟用時的警告訊息，版本低於1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="7a335-121">使用群組原則從使用者隱藏 Microsoft Defender AV 介面</span><span class="sxs-lookup"><span data-stu-id="7a335-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="7a335-122">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7a335-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="7a335-123">使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="7a335-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="7a335-124">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="7a335-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="7a335-125">展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 用戶端介面**。</span><span class="sxs-lookup"><span data-stu-id="7a335-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="7a335-126">按兩下 [啟用無 **外設 UI 模式]** 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="7a335-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="7a335-127">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="7a335-127">Click **OK**.</span></span> 

<span data-ttu-id="7a335-128">請參閱 [防止使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) ] 中的更多選項，以防止使用者表單修改其電腦上的保護。</span><span class="sxs-lookup"><span data-stu-id="7a335-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="7a335-129">防止使用者暫停掃描</span><span class="sxs-lookup"><span data-stu-id="7a335-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="7a335-130">您可以防止使用者暫停掃描，這有助於確保使用者不會中斷排程或要求的掃描。</span><span class="sxs-lookup"><span data-stu-id="7a335-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="7a335-131">Windows 10 不支援此設定。</span><span class="sxs-lookup"><span data-stu-id="7a335-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="7a335-132">使用群組原則防止使用者暫停掃描</span><span class="sxs-lookup"><span data-stu-id="7a335-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="7a335-133">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7a335-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="7a335-134">使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="7a335-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="7a335-135">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="7a335-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="7a335-136">展開樹狀目錄，以 **Windows**  >  **Microsoft Defender 防毒軟體**  >  **掃描** 的元件。</span><span class="sxs-lookup"><span data-stu-id="7a335-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="7a335-137">按兩下 [ **允許使用者暫停掃描** ] 設定，並將選項設定為 [ **已停用**]。</span><span class="sxs-lookup"><span data-stu-id="7a335-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="7a335-138">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="7a335-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="7a335-139">相關文章</span><span class="sxs-lookup"><span data-stu-id="7a335-139">Related articles</span></span>

- [<span data-ttu-id="7a335-140">設定出現在端點上的通知</span><span class="sxs-lookup"><span data-stu-id="7a335-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="7a335-141">設定使用者與 Microsoft Defender 防毒軟體互動互動</span><span class="sxs-lookup"><span data-stu-id="7a335-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="7a335-142">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="7a335-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)