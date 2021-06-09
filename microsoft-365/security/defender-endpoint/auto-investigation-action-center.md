---
title: 流覽行動中心以查看修正動作
description: 使用重要訊息中心來查看自動調查後的詳細資料和結果
keywords: action，center，autoir，自動化，調查，回應，修正
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844907"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="9d946-104">流覽行動中心以查看修正動作</span><span class="sxs-lookup"><span data-stu-id="9d946-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="9d946-105">在自動調查期間和之後，會識別威脅偵測的修正動作。</span><span class="sxs-lookup"><span data-stu-id="9d946-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="9d946-106">根據特定威脅及如何為您的組織設定 [Microsoft Defender For Endpoint](/windows/security/threat-protection) ，有些修正動作會自動採取，其他一些要求必須核准。</span><span class="sxs-lookup"><span data-stu-id="9d946-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="9d946-107">如果您是組織的安全性運作小組的一部分，您可以在重要訊息 **中心** 中查看暫止及已完成的 [修復動作](manage-auto-investigation.md#remediation-actions)。</span><span class="sxs-lookup"><span data-stu-id="9d946-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="9d946-108">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9d946-108">**Applies to:**</span></span>
- [<span data-ttu-id="9d946-109">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9d946-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9d946-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d946-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="9d946-111"> (NEW！ ) 整合的動作中心</span><span class="sxs-lookup"><span data-stu-id="9d946-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="9d946-112">我們很樂意宣告新的整合的動作中心 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) ！</span><span class="sxs-lookup"><span data-stu-id="9d946-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Microsoft 365 安全性中心的行動中心":::

<span data-ttu-id="9d946-114">下表將新的整合的動作中心與上一個操作中心進行比較。</span><span class="sxs-lookup"><span data-stu-id="9d946-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="9d946-115">新的整合的動作中心</span><span class="sxs-lookup"><span data-stu-id="9d946-115">The new, unified Action center</span></span>  |<span data-ttu-id="9d946-116">上一個操作中心</span><span class="sxs-lookup"><span data-stu-id="9d946-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="9d946-117">列出裝置和電子郵件在一個位置的擱置和完成的動作</span><span class="sxs-lookup"><span data-stu-id="9d946-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="9d946-118">為 ([的端點](microsoft-defender-endpoint.md)加上 microsoft defender [Office 365](/microsoft-365/security/office-365-security/office-365-atp)) </span><span class="sxs-lookup"><span data-stu-id="9d946-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span></span>|<span data-ttu-id="9d946-119">列出裝置的擱置及已完成的動作</span><span class="sxs-lookup"><span data-stu-id="9d946-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="9d946-120">僅限 [端點的 Microsoft Defender](microsoft-defender-endpoint.md) () </span><span class="sxs-lookup"><span data-stu-id="9d946-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) only)</span></span>   |
|<span data-ttu-id="9d946-121">位於：</span><span class="sxs-lookup"><span data-stu-id="9d946-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="9d946-122">位於：</span><span class="sxs-lookup"><span data-stu-id="9d946-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="9d946-123">在 [Microsoft 365 安全性中心] 中，選擇 [**動作中心**]。</span><span class="sxs-lookup"><span data-stu-id="9d946-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="流覽至 Microsoft 365 安全性中心的「行動中心」"::: | <span data-ttu-id="9d946-125">在 Microsoft Defender 資訊安全中心中，選擇 [**自動調查**]  >  **動作中心**。</span><span class="sxs-lookup"><span data-stu-id="9d946-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="從 Microsoft Defender 資訊安全中心流覽至 [行動中心]":::  |

<span data-ttu-id="9d946-127">整合的動作中心會將每個 Defender 和 Defender 的修正動作彙集在一起，以供 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9d946-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="9d946-128">它會定義所有修正動作的共同語言，並提供統一的調查經驗。</span><span class="sxs-lookup"><span data-stu-id="9d946-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="9d946-129">如果您有適當的許可權以及下列一或多項訂閱，您可以使用統一的行動中心：</span><span class="sxs-lookup"><span data-stu-id="9d946-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="9d946-130">端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="9d946-130">Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)
- [<span data-ttu-id="9d946-131">適用於 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="9d946-131">Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="9d946-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d946-132">Microsoft 365 Defender</span></span>](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="9d946-133">若要深入瞭解，請參閱 [需求](/microsoft-365/security/mtp/prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="9d946-133">To learn more, see [Requirements](/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="9d946-134">使用動作中心</span><span class="sxs-lookup"><span data-stu-id="9d946-134">Using the Action center</span></span>

<span data-ttu-id="9d946-135">若要在增強的 Microsoft 365 安全性中心進入整合的動作中心：</span><span class="sxs-lookup"><span data-stu-id="9d946-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="9d946-136">請移至 Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="9d946-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="9d946-137">在功能窗格中，選取 [ **動作中心**]。</span><span class="sxs-lookup"><span data-stu-id="9d946-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="9d946-138">當您造訪「行動中心」時，您會看到兩個索引標籤： **擱置的動作** 和歷程 **記錄**。</span><span class="sxs-lookup"><span data-stu-id="9d946-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="9d946-139">下表摘要顯示每個索引標籤的內容：</span><span class="sxs-lookup"><span data-stu-id="9d946-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="9d946-140">索引標籤</span><span class="sxs-lookup"><span data-stu-id="9d946-140">Tab</span></span>  |<span data-ttu-id="9d946-141">描述</span><span class="sxs-lookup"><span data-stu-id="9d946-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9d946-142">**等待**</span><span class="sxs-lookup"><span data-stu-id="9d946-142">**Pending**</span></span>     | <span data-ttu-id="9d946-143">顯示需要注意的動作清單。</span><span class="sxs-lookup"><span data-stu-id="9d946-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="9d946-144">您可以一次核准或拒絕其中一項動作，或選取多個動作的動作為相同類型的動作 (例如 **隔離** 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="9d946-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="9d946-145">**秘訣**：請務必立即 [複查及核准 (或拒絕) 擱置的動作](manage-auto-investigation.md) ，以便您的自動化調查可以及時完成。</span><span class="sxs-lookup"><span data-stu-id="9d946-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="9d946-146">**歷程記錄**</span><span class="sxs-lookup"><span data-stu-id="9d946-146">**History**</span></span>     | <span data-ttu-id="9d946-147">做為已採取動作的審計記錄，例如：</span><span class="sxs-lookup"><span data-stu-id="9d946-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="9d946-148">-自動調查導致採取的修正動作</span><span class="sxs-lookup"><span data-stu-id="9d946-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="9d946-149">-您的安全作業小組已核准的修正動作</span><span class="sxs-lookup"><span data-stu-id="9d946-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="9d946-150">-已執行的命令和在即時回應會話期間所套用的修正動作</span><span class="sxs-lookup"><span data-stu-id="9d946-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="9d946-151">-Microsoft Defender 防毒軟體中的威脅防護功能所採取的修正動作</span><span class="sxs-lookup"><span data-stu-id="9d946-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="9d946-152">提供一種方法來復原特定動作 (請參閱 [復原已完成的動作](manage-auto-investigation.md#undo-completed-actions)) 。</span><span class="sxs-lookup"><span data-stu-id="9d946-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="9d946-153">您可以在「行動中心」中自訂、排序、篩選和匯出資料。</span><span class="sxs-lookup"><span data-stu-id="9d946-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="在重要訊息中心中的欄與篩選":::

- <span data-ttu-id="9d946-155">選取欄標題，以遞增或遞減順序排序專案。</span><span class="sxs-lookup"><span data-stu-id="9d946-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="9d946-156">使用 [時段] 篩選，以查看過去一天、一周、30天或6個月的資料。</span><span class="sxs-lookup"><span data-stu-id="9d946-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="9d946-157">選擇您要查看的欄。</span><span class="sxs-lookup"><span data-stu-id="9d946-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="9d946-158">指定每個資料頁面上要包含的專案數。</span><span class="sxs-lookup"><span data-stu-id="9d946-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="9d946-159">請使用篩選器，只查看您想要查看的專案。</span><span class="sxs-lookup"><span data-stu-id="9d946-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="9d946-160">選取 [ **匯出** ]，將結果匯出至 .csv 檔。</span><span class="sxs-lookup"><span data-stu-id="9d946-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="9d946-161">後續步驟</span><span class="sxs-lookup"><span data-stu-id="9d946-161">Next steps</span></span>

- [<span data-ttu-id="9d946-162">查看和核准補救動作</span><span class="sxs-lookup"><span data-stu-id="9d946-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="9d946-163">請參閱互動式指南：使用 Microsoft Defender for Endpoint 調查和修正威脅</span><span class="sxs-lookup"><span data-stu-id="9d946-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="9d946-164">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9d946-164">See also</span></span>

- [<span data-ttu-id="9d946-165">解決適用於端點的 Microsoft Defender 中的誤判/漏報</span><span class="sxs-lookup"><span data-stu-id="9d946-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
