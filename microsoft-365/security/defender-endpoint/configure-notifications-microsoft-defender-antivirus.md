---
title: 設定 Microsoft Defender 防毒軟體通知
description: 瞭解如何設定和自訂端點上的標準及其他 Microsoft Defender 防毒軟體通知。
keywords: 通知、defender、防毒程式、端點、管理、系統管理員
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985405"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="251ae-104">設定出現在端點上的 Microsoft Defender 防毒軟體通知</span><span class="sxs-lookup"><span data-stu-id="251ae-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="251ae-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="251ae-105">**Applies to:**</span></span>

- [<span data-ttu-id="251ae-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="251ae-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="251ae-107">在 Windows 10 中，惡意程式碼偵測和修復的代理程式更新會變得更健壯、一致和簡潔。</span><span class="sxs-lookup"><span data-stu-id="251ae-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="251ae-108">在完成掃描及偵測到威脅時，端點上會出現 Microsoft Defender 防毒軟體通知。</span><span class="sxs-lookup"><span data-stu-id="251ae-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="251ae-109">通知遵循排程和手動觸發的掃描。</span><span class="sxs-lookup"><span data-stu-id="251ae-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="251ae-110">這些通知也會出現在 **通知中心**，以及掃描和威脅偵測的摘要會以固定時間間隔出現。</span><span class="sxs-lookup"><span data-stu-id="251ae-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="251ae-111">如果您是組織的安全小組的一部分，您可以設定在端點上顯示通知的方式，例如提示重新開機系統，或指出已偵測到威脅並進行修正的通知。</span><span class="sxs-lookup"><span data-stu-id="251ae-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="251ae-112">使用群組原則或 Windows 安全性應用程式設定防病毒通知</span><span class="sxs-lookup"><span data-stu-id="251ae-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="251ae-113">您可以在[Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)及群組原則中，設定其他通知的顯示（例如最近的威脅偵測摘要）。</span><span class="sxs-lookup"><span data-stu-id="251ae-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="251ae-114">在 Windows 10 中，版本1607該功能稱為「**增強型通知**」，且是在 **Windows 設定**  >  **Update & 安全性**  >  **Windows Defender** 下設定。</span><span class="sxs-lookup"><span data-stu-id="251ae-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="251ae-115">在所有 Windows 10 版本的「群組原則」設定中，通知功能稱為「**增強的通知**」。</span><span class="sxs-lookup"><span data-stu-id="251ae-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="251ae-116">使用群組原則來停用其他通知</span><span class="sxs-lookup"><span data-stu-id="251ae-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="251ae-117">在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="251ae-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="251ae-118">以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="251ae-119">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="251ae-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="251ae-120">選取 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="251ae-121">展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**> 報告 \* \*。</span><span class="sxs-lookup"><span data-stu-id="251ae-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="251ae-122">連按兩下 [ **關閉增強型通知**]，然後將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="251ae-123">然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="251ae-123">Then select **OK**.</span></span> <span data-ttu-id="251ae-124">這會防止顯示其他通知。</span><span class="sxs-lookup"><span data-stu-id="251ae-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="251ae-125">停用其他通知將不會停用重要通知，例如威脅偵測和修正警示。</span><span class="sxs-lookup"><span data-stu-id="251ae-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="251ae-126">使用 Windows 安全性應用程式來停用其他通知</span><span class="sxs-lookup"><span data-stu-id="251ae-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="251ae-127">按一下工作列中的盾牌圖示，或搜尋 [**安全性**] 的 [開始] 功能表，開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="251ae-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="251ae-128">在左功能表列上選取 [**病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後選取 [**病毒 & 威脅防護設定**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="251ae-129">滾動至 [ **通知** ] 區段，然後選取 [ **變更通知設定**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="251ae-130">將開關滑動至 [ **關閉** ] 或 [ **開啟** ]，以停用或啟用其他通知。</span><span class="sxs-lookup"><span data-stu-id="251ae-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="251ae-131">停用其他通知將不會停用重要通知，例如威脅偵測和修正警示。</span><span class="sxs-lookup"><span data-stu-id="251ae-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="251ae-132">使用群組原則設定端點上的標準通知</span><span class="sxs-lookup"><span data-stu-id="251ae-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="251ae-133">您可以使用群組原則來：</span><span class="sxs-lookup"><span data-stu-id="251ae-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="251ae-134">當使用者需要執行動作時，在端點上顯示其他自訂的文字</span><span class="sxs-lookup"><span data-stu-id="251ae-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="251ae-135">隱藏端點上的所有通知</span><span class="sxs-lookup"><span data-stu-id="251ae-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="251ae-136">在端點上隱藏重新開機通知</span><span class="sxs-lookup"><span data-stu-id="251ae-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="251ae-137">隱藏通知可用於隱藏整個 Microsoft Defender 防毒軟體介面的情況。</span><span class="sxs-lookup"><span data-stu-id="251ae-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="251ae-138">如需詳細資訊，請參閱[防止使用者查看或與 Microsoft Defender 防毒軟體使用者介面互動](prevent-end-user-interaction-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="251ae-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="251ae-139">隱藏通知只會發生于已部署原則的端點上。</span><span class="sxs-lookup"><span data-stu-id="251ae-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="251ae-140">與必須採取的動作相關的通知 (例如重新開機) 仍會顯示在[Microsoft 端點管理員 Endpoint Protection 監控儀表板和報告](/configmgr/protect/deploy-use/monitor-endpoint-protection)中。</span><span class="sxs-lookup"><span data-stu-id="251ae-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="251ae-141">若要將自訂連絡人資訊新增至端點通知，請參閱[自訂群組織的 Windows 安全性應用程式](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="251ae-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="251ae-142">使用群組原則隱藏通知</span><span class="sxs-lookup"><span data-stu-id="251ae-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="251ae-143">在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="251ae-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="251ae-144">以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="251ae-145">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="251ae-146">展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **用戶端介面**。</span><span class="sxs-lookup"><span data-stu-id="251ae-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="251ae-147">按兩下 [ **抑制所有通知** ] 並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="251ae-148">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="251ae-148">Select **OK**.</span></span> <span data-ttu-id="251ae-149">這會防止顯示其他通知。</span><span class="sxs-lookup"><span data-stu-id="251ae-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="251ae-150">使用群組原則隱藏重新開機通知</span><span class="sxs-lookup"><span data-stu-id="251ae-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="251ae-151">在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="251ae-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="251ae-152">以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="251ae-153">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="251ae-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="251ae-154">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="251ae-155">展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **用戶端介面**。</span><span class="sxs-lookup"><span data-stu-id="251ae-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="251ae-156">按兩下 [ **重新開機通知** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="251ae-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="251ae-157">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="251ae-157">Select **OK**.</span></span> <span data-ttu-id="251ae-158">這會防止顯示其他通知。</span><span class="sxs-lookup"><span data-stu-id="251ae-158">This will prevent additional notifications from appearing.</span></span>

