---
title: 設定 Microsoft Defender 防毒軟體通知
description: 瞭解如何設定和自訂端點上的標準和額外 Microsoft Defender 防毒軟體通知。
keywords: 通知、defender、防毒程式、端點、管理、系統管理員
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572342"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="bc8cd-104">設定端點顯示的通知</span><span class="sxs-lookup"><span data-stu-id="bc8cd-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="bc8cd-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bc8cd-105">**Applies to:**</span></span>

- [<span data-ttu-id="bc8cd-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bc8cd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bc8cd-107">在 Windows 10 中，惡意程式碼偵測和修復的代理程式更新會變得更健壯、一致和簡潔。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="bc8cd-108">當手動觸發和排程的掃描已完成且偵測到威脅時，在端點上會出現通知。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="bc8cd-109">這些通知也會出現在 **通知中心**，以及掃描和威脅偵測的摘要會以固定時間間隔出現。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="bc8cd-110">您也可以設定在端點上顯示標準通知的方式，例如，當偵測到威脅或已偵測到威脅時的通知。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="bc8cd-111">設定出現在端點上的其他通知</span><span class="sxs-lookup"><span data-stu-id="bc8cd-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="bc8cd-112">您可以在[Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)及群組原則中，設定其他通知的顯示（例如最近的威脅偵測摘要）。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="bc8cd-113">在 Windows 10 中，版本1607該功能稱為「**增強型通知**」，可在 **Windows 設定**  >  **Update & 安全性**  >  **Windows Defender** 下加以設定。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="bc8cd-114">在所有 Windows 10 版本的「群組原則」設定中，稱為「**增強的通知**」。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc8cd-115">停用其他通知將不會停用重要通知，例如威脅偵測和修正警示。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="bc8cd-116">**使用 Windows 安全性應用程式來停用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="bc8cd-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="bc8cd-117">按一下工作列中的盾牌圖示，或搜尋 [**安全性**] 的 [開始] 功能表，開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="bc8cd-118">在左功能表列上選取 [**病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後選取 [**病毒 & 威脅防護設定**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="bc8cd-119">滾動至 [ **通知** ] 區段，然後按一下 [ **變更通知設定**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="bc8cd-120">將開關滑動至 [ **關閉** ] 或 [ **開啟** ]，以停用或啟用其他通知。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="bc8cd-121">**使用群組原則來停用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="bc8cd-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="bc8cd-122">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="bc8cd-123">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="bc8cd-124">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="bc8cd-125">展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 報告**。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="bc8cd-126">按兩下 [ **關閉增強型通知** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="bc8cd-127">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-127">Click **OK**.</span></span> <span data-ttu-id="bc8cd-128">這會防止顯示其他通知。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="bc8cd-129">設定端點的標準通知</span><span class="sxs-lookup"><span data-stu-id="bc8cd-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="bc8cd-130">您可以使用群組原則來：</span><span class="sxs-lookup"><span data-stu-id="bc8cd-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="bc8cd-131">當使用者需要執行動作時，在端點上顯示其他自訂的文字</span><span class="sxs-lookup"><span data-stu-id="bc8cd-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="bc8cd-132">隱藏端點上的所有通知</span><span class="sxs-lookup"><span data-stu-id="bc8cd-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="bc8cd-133">在端點上隱藏重新開機通知</span><span class="sxs-lookup"><span data-stu-id="bc8cd-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="bc8cd-134">隱藏通知可用於隱藏整個 Microsoft Defender 防毒軟體介面的情況。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="bc8cd-135">如需詳細資訊，請參閱[防止使用者查看或與 Microsoft Defender 防毒軟體使用者介面互動](prevent-end-user-interaction-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="bc8cd-136">隱藏通知只會發生于已部署原則的端點上。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="bc8cd-137">與必須採取的動作相關的通知 (例如重新開機) 仍會顯示在[Microsoft 端點管理員 Endpoint Protection 監控儀表板和報告](/configmgr/protect/deploy-use/monitor-endpoint-protection)中。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="bc8cd-138">請參閱[自訂群組織的 Windows 安全性 app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) ，以取得將自訂連絡人資訊新增至使用者在其機器上看到之通知的指示。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="bc8cd-139">**使用群組原則隱藏通知：**</span><span class="sxs-lookup"><span data-stu-id="bc8cd-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="bc8cd-140">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="bc8cd-141">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="bc8cd-142">展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 用戶端介面**。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="bc8cd-143">按兩下 [ **抑制所有通知** ] 並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="bc8cd-144">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-144">Click **OK**.</span></span> <span data-ttu-id="bc8cd-145">這會防止顯示其他通知。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="bc8cd-146">**使用群組原則隱藏重新開機通知：**</span><span class="sxs-lookup"><span data-stu-id="bc8cd-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="bc8cd-147">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="bc8cd-148">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="bc8cd-149">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="bc8cd-150">展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 用戶端介面**。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="bc8cd-151">按兩下 [ **重新開機通知** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="bc8cd-152">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-152">Click **OK**.</span></span> <span data-ttu-id="bc8cd-153">這會防止顯示其他通知。</span><span class="sxs-lookup"><span data-stu-id="bc8cd-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bc8cd-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="bc8cd-154">Related topics</span></span>

- [<span data-ttu-id="bc8cd-155">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="bc8cd-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="bc8cd-156">設定使用者與 Microsoft Defender 防毒軟體互動互動</span><span class="sxs-lookup"><span data-stu-id="bc8cd-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
