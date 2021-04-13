---
title: 隱藏 Microsoft Defender 防病毒介面
description: 您可以隱藏 Windows 安全性應用程式中的病毒和威脅防護磚。
keywords: ui 鎖定、無周邊模式、隱藏應用程式、隱藏設定、隱藏介面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b5ce018db436aee35bfa1899fb42f1dca31efa6
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690179"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="b101b-104">防止使用者看到 Microsoft Defender 防病毒使用者介面或與其互動</span><span class="sxs-lookup"><span data-stu-id="b101b-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b101b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b101b-105">**Applies to:**</span></span>

- [<span data-ttu-id="b101b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b101b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b101b-107">您可以使用群組原則，防止使用者在端點上看到 Microsoft Defender 防病毒介面。</span><span class="sxs-lookup"><span data-stu-id="b101b-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="b101b-108">您也可以防止使用者暫停掃描。</span><span class="sxs-lookup"><span data-stu-id="b101b-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="b101b-109">隱藏 Microsoft Defender 防病毒介面</span><span class="sxs-lookup"><span data-stu-id="b101b-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="b101b-110">在 Windows 10 版本1703中，隱藏介面會隱藏 Microsoft Defender 防病毒通知，並防止病毒 & 威脅防護磚出現在 Windows 安全性應用程式中。</span><span class="sxs-lookup"><span data-stu-id="b101b-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="b101b-111">設定為 [ **啟用**] 時：</span><span class="sxs-lookup"><span data-stu-id="b101b-111">With the setting set to **Enabled**:</span></span>

![沒有盾牌圖示及病毒和威脅防護區段之 Windows 安全性的螢幕擷取畫面](images/defender/wdav-headless-mode-1703.png)

<span data-ttu-id="b101b-113">設定為 [ **停** 用] 或 [未設定] 時：</span><span class="sxs-lookup"><span data-stu-id="b101b-113">With the setting set to **Disabled** or not configured:</span></span>

![顯示盾牌圖示及病毒和威脅防護區段之 Windows 安全性的螢幕擷取畫面](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
><span data-ttu-id="b101b-115">隱藏介面也會使 Microsoft Defender 防病毒通知不會出現在端點上。</span><span class="sxs-lookup"><span data-stu-id="b101b-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="b101b-116">仍會顯示 Microsoft Defender for Endpoint 通知。</span><span class="sxs-lookup"><span data-stu-id="b101b-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="b101b-117">您也可以個別 [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b101b-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="b101b-118">在舊版 Windows 10 中，此設定會隱藏 Windows Defender 用戶端介面。</span><span class="sxs-lookup"><span data-stu-id="b101b-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="b101b-119">如果使用者嘗試開啟它，他們會收到警告說：「您的系統管理員已限制存取此應用程式」。</span><span class="sxs-lookup"><span data-stu-id="b101b-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

![Windows 10 中已啟用無周邊模式的警告訊息，版本低於1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="b101b-121">使用群組原則從使用者隱藏 Microsoft Defender AV 介面</span><span class="sxs-lookup"><span data-stu-id="b101b-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="b101b-122">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b101b-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b101b-123">使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="b101b-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b101b-124">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="b101b-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="b101b-125">在 [ **Microsoft Defender 防病毒 > 用戶端] 介面** 中，將樹狀目錄展開為 Windows 元件 >。</span><span class="sxs-lookup"><span data-stu-id="b101b-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="b101b-126">按兩下 [啟用無 **外設 UI 模式]** 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="b101b-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b101b-127">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="b101b-127">Click **OK**.</span></span> 

<span data-ttu-id="b101b-128">請參閱 [防止使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) ] 中的更多選項，以防止使用者表單修改其電腦上的保護。</span><span class="sxs-lookup"><span data-stu-id="b101b-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="b101b-129">防止使用者暫停掃描</span><span class="sxs-lookup"><span data-stu-id="b101b-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="b101b-130">您可以防止使用者暫停掃描，這有助於確保使用者不會中斷排程或要求的掃描。</span><span class="sxs-lookup"><span data-stu-id="b101b-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="b101b-131">Windows 10 不支援此設定。</span><span class="sxs-lookup"><span data-stu-id="b101b-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="b101b-132">使用群組原則防止使用者暫停掃描</span><span class="sxs-lookup"><span data-stu-id="b101b-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="b101b-133">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b101b-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b101b-134">使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="b101b-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b101b-135">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="b101b-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="b101b-136">將樹狀目錄展開為 **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **掃描**。</span><span class="sxs-lookup"><span data-stu-id="b101b-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="b101b-137">按兩下 [ **允許使用者暫停掃描** ] 設定，並將選項設定為 [ **已停用**]。</span><span class="sxs-lookup"><span data-stu-id="b101b-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="b101b-138">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="b101b-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="b101b-139">相關文章</span><span class="sxs-lookup"><span data-stu-id="b101b-139">Related articles</span></span>

- [<span data-ttu-id="b101b-140">設定出現在端點上的通知</span><span class="sxs-lookup"><span data-stu-id="b101b-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="b101b-141">使用 Microsoft Defender 防毒軟體設定使用者互動</span><span class="sxs-lookup"><span data-stu-id="b101b-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="b101b-142">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="b101b-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)