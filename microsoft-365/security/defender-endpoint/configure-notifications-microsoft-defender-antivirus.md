---
title: 設定 Microsoft Defender 防病毒通知
description: 瞭解如何設定和自訂端點上的標準及其他 Microsoft Defender 防病毒通知。
keywords: 通知、defender、防毒程式、端點、管理、系統管理員
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
ms.openlocfilehash: 82ca54e383943f4994f9647ce1e110a6621b1327
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690208"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="353cf-104">設定出現在端點上的通知</span><span class="sxs-lookup"><span data-stu-id="353cf-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="353cf-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="353cf-105">**Applies to:**</span></span>

- [<span data-ttu-id="353cf-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="353cf-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="353cf-107">在 Windows 10 中，惡意程式碼偵測和修復的代理程式更新會變得更健壯、一致和簡潔。</span><span class="sxs-lookup"><span data-stu-id="353cf-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="353cf-108">當手動觸發和排程的掃描已完成且偵測到威脅時，在端點上會出現通知。</span><span class="sxs-lookup"><span data-stu-id="353cf-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="353cf-109">這些通知也會出現在 **通知中心**，以及掃描和威脅偵測的摘要會以固定時間間隔出現。</span><span class="sxs-lookup"><span data-stu-id="353cf-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="353cf-110">您也可以設定在端點上顯示標準通知的方式，例如，當偵測到威脅或已偵測到威脅時的通知。</span><span class="sxs-lookup"><span data-stu-id="353cf-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="353cf-111">設定出現在端點上的其他通知</span><span class="sxs-lookup"><span data-stu-id="353cf-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="353cf-112">您可以在 [ [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md) ] 和 [群組原則] 中，設定其他通知的顯示（例如最近的威脅偵測摘要）。</span><span class="sxs-lookup"><span data-stu-id="353cf-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="353cf-113">在 windows 10 中，版本1607該功能稱為「**增強型通知**」，可在 [ **windows 設定**  >  **更新 & security**  >  **Windows Defender**] 下加以設定。</span><span class="sxs-lookup"><span data-stu-id="353cf-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="353cf-114">在所有 Windows 10 版本的「群組原則」設定中，稱為 **增強型通知**。</span><span class="sxs-lookup"><span data-stu-id="353cf-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="353cf-115">停用其他通知將不會停用重要通知，例如威脅偵測和修正警示。</span><span class="sxs-lookup"><span data-stu-id="353cf-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="353cf-116">**使用 Windows 安全性應用程式來停用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="353cf-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="353cf-117">按一下工作列上的盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 [Windows 安全性] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="353cf-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="353cf-118">在左功能表列上，按一下 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後按一下 [ **病毒 & 威脅防護設定** ] 標籤：</span><span class="sxs-lookup"><span data-stu-id="353cf-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Windows 安全性應用程式中的病毒 & 威脅防護設定] 標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="353cf-120">滾動至 [ **通知** ] 區段，然後按一下 [ **變更通知設定**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="353cf-121">將開關滑動至 [ **關閉** ] 或 [ **開啟** ]，以停用或啟用其他通知。</span><span class="sxs-lookup"><span data-stu-id="353cf-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="353cf-122">**使用群組原則來停用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="353cf-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="353cf-123">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="353cf-124">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="353cf-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="353cf-125">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="353cf-126">在 [ **Microsoft Defender 防病毒 > 報告**] 中，展開 [Windows 元件] > 的樹狀目錄。</span><span class="sxs-lookup"><span data-stu-id="353cf-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="353cf-127">按兩下 [ **關閉增強型通知** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="353cf-128">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="353cf-128">Click **OK**.</span></span> <span data-ttu-id="353cf-129">這會防止顯示其他通知。</span><span class="sxs-lookup"><span data-stu-id="353cf-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="353cf-130">設定端點的標準通知</span><span class="sxs-lookup"><span data-stu-id="353cf-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="353cf-131">您可以使用群組原則來：</span><span class="sxs-lookup"><span data-stu-id="353cf-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="353cf-132">當使用者需要執行動作時，在端點上顯示其他自訂的文字</span><span class="sxs-lookup"><span data-stu-id="353cf-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="353cf-133">隱藏端點上的所有通知</span><span class="sxs-lookup"><span data-stu-id="353cf-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="353cf-134">在端點上隱藏重新開機通知</span><span class="sxs-lookup"><span data-stu-id="353cf-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="353cf-135">隱藏通知可用於隱藏整個 Microsoft Defender 防病毒介面的情況。</span><span class="sxs-lookup"><span data-stu-id="353cf-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="353cf-136">請參閱 [防止使用者查看或與 Microsoft Defender 防病毒使用者介面互動](prevent-end-user-interaction-microsoft-defender-antivirus.md) ，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="353cf-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="353cf-137">隱藏通知只會發生于已部署原則的端點上。</span><span class="sxs-lookup"><span data-stu-id="353cf-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="353cf-138">與必須採取的動作相關的通知 (例如重新開機) 仍會出現在 [Microsoft 端點管理員端點防護監控儀表板和報告](/configmgr/protect/deploy-use/monitor-endpoint-protection)上。</span><span class="sxs-lookup"><span data-stu-id="353cf-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="353cf-139">請參閱 [自訂群組織的 Windows 安全性 app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) ，以取得將自訂連絡人資訊新增至使用者在其機器上看到之通知的指示。</span><span class="sxs-lookup"><span data-stu-id="353cf-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="353cf-140">**使用群組原則隱藏通知：**</span><span class="sxs-lookup"><span data-stu-id="353cf-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="353cf-141">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="353cf-142">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="353cf-143">在 [ **Microsoft Defender 防病毒 > 用戶端] 介面** 中，將樹狀目錄展開為 Windows 元件 >。</span><span class="sxs-lookup"><span data-stu-id="353cf-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="353cf-144">按兩下 [ **抑制所有通知** ] 並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="353cf-145">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="353cf-145">Click **OK**.</span></span> <span data-ttu-id="353cf-146">這會防止顯示其他通知。</span><span class="sxs-lookup"><span data-stu-id="353cf-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="353cf-147">**使用群組原則隱藏重新開機通知：**</span><span class="sxs-lookup"><span data-stu-id="353cf-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="353cf-148">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="353cf-149">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="353cf-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="353cf-150">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="353cf-151">在 [ **Microsoft Defender 防病毒 > 用戶端] 介面** 中，將樹狀目錄展開為 Windows 元件 >。</span><span class="sxs-lookup"><span data-stu-id="353cf-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="353cf-152">按兩下 [ **重新開機通知** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="353cf-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="353cf-153">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="353cf-153">Click **OK**.</span></span> <span data-ttu-id="353cf-154">這會防止顯示其他通知。</span><span class="sxs-lookup"><span data-stu-id="353cf-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="353cf-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="353cf-155">Related topics</span></span>

- [<span data-ttu-id="353cf-156">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="353cf-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="353cf-157">使用 Microsoft Defender 防毒軟體設定使用者互動</span><span class="sxs-lookup"><span data-stu-id="353cf-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)