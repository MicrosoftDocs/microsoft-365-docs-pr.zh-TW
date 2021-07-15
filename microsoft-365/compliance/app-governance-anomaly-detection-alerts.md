---
title: 調查異常偵測警示
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 調查異常偵測警示。
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420118"
---
# <a name="investigate-anomaly-detection-alerts"></a><span data-ttu-id="de1c9-103">調查異常偵測警示</span><span class="sxs-lookup"><span data-stu-id="de1c9-103">Investigate anomaly detection alerts</span></span>

 <span data-ttu-id="de1c9-104">Microsoft 應用程式控管提供惡意活動的安全性偵測和警示。</span><span class="sxs-lookup"><span data-stu-id="de1c9-104">Microsoft app governance provides security detections and alerts for malicious activities.</span></span> <span data-ttu-id="de1c9-105">本指南的目的是提供您每個警示的一般和實用資訊，協助您進行調查和補救工作。</span><span class="sxs-lookup"><span data-stu-id="de1c9-105">The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.</span></span> <span data-ttu-id="de1c9-106">本指南包含觸發警示的一般條件資訊。</span><span class="sxs-lookup"><span data-stu-id="de1c9-106">Included in this guide is general information about the conditions for triggering alerts.</span></span> <span data-ttu-id="de1c9-107">由於異常偵測本質上是不確定的，因此只有在有偏離標準的行為時，才會觸發異常偵測。</span><span class="sxs-lookup"><span data-stu-id="de1c9-107">Because anomaly detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm.</span></span> <span data-ttu-id="de1c9-108">最後，某些警示可能處於預覽階段，因此請定期查看正式文件，以取得更新的警示狀態。</span><span class="sxs-lookup"><span data-stu-id="de1c9-108">Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.</span></span>

## <a name="mitre-attck"></a><span data-ttu-id="de1c9-109">MITRE ATT&CK</span><span class="sxs-lookup"><span data-stu-id="de1c9-109">MITRE ATT&CK</span></span>

<span data-ttu-id="de1c9-110">為了更容易對應 Microsoft 應用程式控管警示與熟悉的 MITRE ATT&CK 矩陣之間的關係，我們已根據對應的 MITRE ATT&CK 策略將警示分類。</span><span class="sxs-lookup"><span data-stu-id="de1c9-110">To make it easier to map the relationship between Microsoft app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic.</span></span> <span data-ttu-id="de1c9-111">這個額外的參考資料可讓您容易了解當觸發 Microsoft 應用程式安全性與控管警示時，可能使用的可疑攻擊技術。</span><span class="sxs-lookup"><span data-stu-id="de1c9-111">This additional reference makes it easier to understand the suspected attacks technique potentially in use when Microsoft Application Security and Governance alert is triggered.</span></span>

<span data-ttu-id="de1c9-112">本指南提供調查和補救 Microsoft 應用程式控管警示的資訊，分為以下各類。</span><span class="sxs-lookup"><span data-stu-id="de1c9-112">This guide provides information about investigating and remediating Microsoft app governance alerts in the following categories.</span></span>

- <span data-ttu-id="de1c9-113">初次存取</span><span class="sxs-lookup"><span data-stu-id="de1c9-113">Initial Access</span></span>
- <span data-ttu-id="de1c9-114">執行</span><span class="sxs-lookup"><span data-stu-id="de1c9-114">Execution</span></span>
- <span data-ttu-id="de1c9-115">持續性</span><span class="sxs-lookup"><span data-stu-id="de1c9-115">Persistence</span></span>
- <span data-ttu-id="de1c9-116">權限提升</span><span class="sxs-lookup"><span data-stu-id="de1c9-116">Privilege Escalation</span></span>
- <span data-ttu-id="de1c9-117">防禦規避</span><span class="sxs-lookup"><span data-stu-id="de1c9-117">Defense Evasion</span></span>
- <span data-ttu-id="de1c9-118">認證存取</span><span class="sxs-lookup"><span data-stu-id="de1c9-118">Credential Access</span></span>
- <span data-ttu-id="de1c9-119">集合</span><span class="sxs-lookup"><span data-stu-id="de1c9-119">Collection</span></span>
- <span data-ttu-id="de1c9-120">外流</span><span class="sxs-lookup"><span data-stu-id="de1c9-120">Exfiltration</span></span>
- <span data-ttu-id="de1c9-121">影響</span><span class="sxs-lookup"><span data-stu-id="de1c9-121">Impact</span></span>

## <a name="security-alert-classifications"></a><span data-ttu-id="de1c9-122">安全性警示分類</span><span class="sxs-lookup"><span data-stu-id="de1c9-122">Security alert classifications</span></span>

<span data-ttu-id="de1c9-123">在適當的調查之後，所有 Microsoft 應用程式控管警示都可以分類為下列其中一種活動類型：</span><span class="sxs-lookup"><span data-stu-id="de1c9-123">Following proper investigation, all Microsoft app governance alerts can be classified as one of the following activity types:</span></span>

- <span data-ttu-id="de1c9-124">確判為真 (TP)：已確認是惡意活動的警報。</span><span class="sxs-lookup"><span data-stu-id="de1c9-124">True positive (TP): An alert on a confirmed malicious activity.</span></span>
- <span data-ttu-id="de1c9-125">良性確判為真 (B-TP)：對可疑但非惡意活動的警報，例如滲透測試或其他授權的可疑操作。</span><span class="sxs-lookup"><span data-stu-id="de1c9-125">Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.</span></span>
- <span data-ttu-id="de1c9-126">誤誤 (FP)：非惡意活動的警示。</span><span class="sxs-lookup"><span data-stu-id="de1c9-126">False positive (FP): An alert on a non-malicious activity.</span></span>

## <a name="general-investigation-steps"></a><span data-ttu-id="de1c9-127">一般調查步驟</span><span class="sxs-lookup"><span data-stu-id="de1c9-127">General investigation steps</span></span>

<span data-ttu-id="de1c9-128">在調查任何類型的警示時，請使用下列一般指導方針，以在應用建議動作之前更清楚地了解潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="de1c9-128">Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.</span></span>

- <span data-ttu-id="de1c9-129">檢閱應用程式嚴重性層級，並與租用戶中其餘的應用程式比較。</span><span class="sxs-lookup"><span data-stu-id="de1c9-129">Review the App severity level and compare with the rest of the app in your tenant.</span></span> <span data-ttu-id="de1c9-130">檢閱此資訊有助於發現您租用戶中的哪些應用程式會帶來更大的風險。</span><span class="sxs-lookup"><span data-stu-id="de1c9-130">This review will help you identify which Apps in your tenant pose the greater risk.</span></span>
- <span data-ttu-id="de1c9-131">如果您發現 TP，請檢閱所有應用程式活動，了解影響。</span><span class="sxs-lookup"><span data-stu-id="de1c9-131">If you identify a TP, review all the App activities to gain an understanding of the impact.</span></span> <span data-ttu-id="de1c9-132">例如，請檢閱下列應用程式資訊：</span><span class="sxs-lookup"><span data-stu-id="de1c9-132">For example, review the following App information:</span></span>

  - <span data-ttu-id="de1c9-133">授予存取權的範圍</span><span class="sxs-lookup"><span data-stu-id="de1c9-133">Scopes granted access</span></span>
  - <span data-ttu-id="de1c9-134">異常行為</span><span class="sxs-lookup"><span data-stu-id="de1c9-134">Unusual behavior</span></span>  
  - <span data-ttu-id="de1c9-135">IP 位址和位置</span><span class="sxs-lookup"><span data-stu-id="de1c9-135">IP address and location</span></span>

## <a name="initial-access-alerts"></a><span data-ttu-id="de1c9-136">初次存取警示</span><span class="sxs-lookup"><span data-stu-id="de1c9-136">Initial access alerts</span></span>

<span data-ttu-id="de1c9-137">本節描述的警示可指出可能試圖在您的組織中保持立足點的惡意應用程式。</span><span class="sxs-lookup"><span data-stu-id="de1c9-137">This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.</span></span>  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a><span data-ttu-id="de1c9-138">帶有可疑同意範圍的編碼應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="de1c9-138">Encoded app name with suspicious consent scopes</span></span>

<span data-ttu-id="de1c9-139">**嚴重性：** 中</span><span class="sxs-lookup"><span data-stu-id="de1c9-139">**Severity:** Medium</span></span>

<span data-ttu-id="de1c9-140">**描述**：此偵測可發現帶有字元 (例如 Unicode 或編碼字元) 的 OAuth 應用程式，收到可疑的同意範圍要求並透過 Graph API 存取使用者郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="de1c9-140">**Description**: This detection identifies OAuth apps with characters, such as Unicode or Encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API.</span></span> <span data-ttu-id="de1c9-141">此警示可能表示有人企圖將惡意應用程式偽裝成已知且受信任的應用程式，以便攻擊者可以誤導使用者同意使用惡意應用程式。</span><span class="sxs-lookup"><span data-stu-id="de1c9-141">This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.</span></span>

<span data-ttu-id="de1c9-142">**TP 或 FP？**</span><span class="sxs-lookup"><span data-stu-id="de1c9-142">**TP or FP?**</span></span>

- <span data-ttu-id="de1c9-143">**TP**：如果您可以確認 OAuth 應用程式已使用從未知來源提供的可疑範圍對顯示名稱進行編碼，則表示其確判為真。</span><span class="sxs-lookup"><span data-stu-id="de1c9-143">**TP**: If you can confirm that the OAuth app has Encoded the display name with suspicious scopes delivered from unknown source, then a true positive is indicated.</span></span>  

  <span data-ttu-id="de1c9-144">**建議動作**：檢閱此應用程式要求的權限層級，以及哪些使用者已授予存取權。</span><span class="sxs-lookup"><span data-stu-id="de1c9-144">**Recommended action**: Review the level of permission requested by this app and which users granted access.</span></span> <span data-ttu-id="de1c9-145">根據您的調查，您可以選擇禁止存取此應用程式。</span><span class="sxs-lookup"><span data-stu-id="de1c9-145">Based on your investigation you can choose to ban access to this app.</span></span>

  <span data-ttu-id="de1c9-146">若要禁止存取應用程式，請在 OAuth 應用程式頁面中，在您要禁止的應用程式出現的列上，選取禁止圖示。</span><span class="sxs-lookup"><span data-stu-id="de1c9-146">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="de1c9-147">您可以選擇是否要告知使用者他們安裝和授權的應用程式已被禁止。</span><span class="sxs-lookup"><span data-stu-id="de1c9-147">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="de1c9-148">通知可讓使用者知道應用程將遭到停用，且他們將無法存取連線的應用程式。</span><span class="sxs-lookup"><span data-stu-id="de1c9-148">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="de1c9-149">如果您不希望使用者知道，請在對話方塊中取消選取 [通知先前授與此遭禁應用程式存取權的使用者]。</span><span class="sxs-lookup"><span data-stu-id="de1c9-149">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="de1c9-150">建議您讓應用程式使用者知道他們的應用程式即將遭到禁用。</span><span class="sxs-lookup"><span data-stu-id="de1c9-150">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="de1c9-151">**FP**：如果您要確認應用程式具有編碼名稱，但在組織中具有合法的商業用途。</span><span class="sxs-lookup"><span data-stu-id="de1c9-151">**FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="de1c9-152">**建議動作**：關閉警示。</span><span class="sxs-lookup"><span data-stu-id="de1c9-152">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="de1c9-153">了解入侵範圍</span><span class="sxs-lookup"><span data-stu-id="de1c9-153">Understand the scope of the breach</span></span>

<span data-ttu-id="de1c9-154">請遵循教學課程，了解如何[調查有風險的 OAuth 應用程式](/cloud-app-security/investigate-risky-oauth)。</span><span class="sxs-lookup"><span data-stu-id="de1c9-154">Follow the tutorial on how to [investigate risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span>

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a><span data-ttu-id="de1c9-155">具有讀取範圍的 OAuth 應用程式具有可疑的回覆 URL</span><span class="sxs-lookup"><span data-stu-id="de1c9-155">OAuth App with read Scopes have suspicious Reply URL</span></span>

<span data-ttu-id="de1c9-156">**嚴重性：** 中</span><span class="sxs-lookup"><span data-stu-id="de1c9-156">**Severity**: Medium</span></span>

<span data-ttu-id="de1c9-157">**描述**：此偵測會發現僅具有讀取範圍的 OAuth 應用程式，例如 User.Read、People.Read、Contacts.Read、Mail.Read、Contacts.Read.Shared 會透過 Graph API 重新導向至可疑的回覆 URL。</span><span class="sxs-lookup"><span data-stu-id="de1c9-157">**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API.</span></span> <span data-ttu-id="de1c9-158">此活動會嘗試指出，具有較低權限的惡意應用程式 (例如讀取範圍) 可能會受到利用，以執行使用者帳戶偵察。</span><span class="sxs-lookup"><span data-stu-id="de1c9-158">This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.</span></span>

<span data-ttu-id="de1c9-159">**TP 或 FP？**</span><span class="sxs-lookup"><span data-stu-id="de1c9-159">**TP or FP?**</span></span>

- <span data-ttu-id="de1c9-160">**TP**：如果您可以確認具有讀取範圍的 OAuth 應用程式來自未知來源並重新導向至可疑的 URL，則表示其確判為真。</span><span class="sxs-lookup"><span data-stu-id="de1c9-160">**TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.</span></span>

  <span data-ttu-id="de1c9-161">**建議動作**：檢閱應用程式要求的回覆 URL 和範圍。</span><span class="sxs-lookup"><span data-stu-id="de1c9-161">**Recommended action**: Review the Reply URL and scopes requested by the app.</span></span> <span data-ttu-id="de1c9-162">根據您的調查，您可以選擇禁止存取此應用程式。</span><span class="sxs-lookup"><span data-stu-id="de1c9-162">Based on your investigation you can choose to ban access to this app.</span></span> <span data-ttu-id="de1c9-163">檢閱此應用程式要求的權限層級，以及哪些使用者已授予存取權。</span><span class="sxs-lookup"><span data-stu-id="de1c9-163">Review the level of permission requested by this app and which users have granted access.</span></span>

  <span data-ttu-id="de1c9-164">若要禁止存取應用程式，請在 OAuth 應用程式頁面中，在您要禁止的應用程式出現的列上，選取禁止圖示。</span><span class="sxs-lookup"><span data-stu-id="de1c9-164">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="de1c9-165">您可以選擇是否要告知使用者他們安裝和授權的應用程式已被禁止。</span><span class="sxs-lookup"><span data-stu-id="de1c9-165">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="de1c9-166">通知可讓使用者知道應用程將遭到停用，且他們將無法存取連線的應用程式。</span><span class="sxs-lookup"><span data-stu-id="de1c9-166">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="de1c9-167">如果您不希望使用者知道，請在對話方塊中取消選取 [通知先前授與此遭禁應用程式存取權的使用者]。</span><span class="sxs-lookup"><span data-stu-id="de1c9-167">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="de1c9-168">建議您讓應用程式使用者知道他們的應用程式即將遭到禁用。</span><span class="sxs-lookup"><span data-stu-id="de1c9-168">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="de1c9-169">**B-TP**：調查後，您可以確認應用程式在組織中具有合法的商業用途。</span><span class="sxs-lookup"><span data-stu-id="de1c9-169">**B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="de1c9-170">**建議動作**：關閉警示。</span><span class="sxs-lookup"><span data-stu-id="de1c9-170">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="de1c9-171">了解入侵範圍</span><span class="sxs-lookup"><span data-stu-id="de1c9-171">Understand the scope of the breach</span></span> 

1. <span data-ttu-id="de1c9-172">檢閱應用程式完成的所有活動。</span><span class="sxs-lookup"><span data-stu-id="de1c9-172">Review all activities done by the app.</span></span>
1. <span data-ttu-id="de1c9-173">如果您懷疑應用程式可疑，建議您在不同的 App Store 中調查應用程式名稱和回覆 URL。</span><span class="sxs-lookup"><span data-stu-id="de1c9-173">If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores.</span></span> <span data-ttu-id="de1c9-174">檢查 App Store 時，請專注於下列類型的應用程式：</span><span class="sxs-lookup"><span data-stu-id="de1c9-174">When checking app stores, focus on the following types of apps:</span></span>
   - <span data-ttu-id="de1c9-175">最近建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="de1c9-175">Apps that have been created recently.</span></span>
   - <span data-ttu-id="de1c9-176">具有可疑回覆 URL 的應用程式</span><span class="sxs-lookup"><span data-stu-id="de1c9-176">Apps with a suspicious Reply URL</span></span>
   - <span data-ttu-id="de1c9-177">最近尚未更新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="de1c9-177">Apps that haven't been recently updated.</span></span> <span data-ttu-id="de1c9-178">缺少更新可能表示應用程式不再受到支援。</span><span class="sxs-lookup"><span data-stu-id="de1c9-178">Lack of updates might indicate the app is no longer supported.</span></span>
1. <span data-ttu-id="de1c9-179">如果您仍然懷疑應用程式可疑，您可以在網路上研究應用程式名稱、發行者名稱和回覆 URL</span><span class="sxs-lookup"><span data-stu-id="de1c9-179">If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online</span></span>  

## <a name="persistence-alerts"></a><span data-ttu-id="de1c9-180">持續性警示</span><span class="sxs-lookup"><span data-stu-id="de1c9-180">Persistence alerts</span></span>

<span data-ttu-id="de1c9-181">本節描述的警示可指出可能試圖在您的組織中保持立足點的惡意執行者。</span><span class="sxs-lookup"><span data-stu-id="de1c9-181">This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.</span></span>

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a><span data-ttu-id="de1c9-182">具有可疑 OAuth 範圍的應用程式會建立收件匣規則</span><span class="sxs-lookup"><span data-stu-id="de1c9-182">App with Suspicious OAuth scope creates Inbox Rule</span></span>  

<span data-ttu-id="de1c9-183">**嚴重性：** 中</span><span class="sxs-lookup"><span data-stu-id="de1c9-183">**Severity**: Medium</span></span>

<span data-ttu-id="de1c9-184">**MITRE 識別碼**：T1137.005、T1114</span><span class="sxs-lookup"><span data-stu-id="de1c9-184">**MITRE ID’s**: T1137.005, T1114</span></span>  

<span data-ttu-id="de1c9-185">此偵測可發現同意可疑範圍的 OAuth 應用程式、建立可疑的收件匣規則，然後透過 Graph API 存取使用者的郵件資料夾和郵件。</span><span class="sxs-lookup"><span data-stu-id="de1c9-185">This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API.</span></span> <span data-ttu-id="de1c9-186">收件匣規則，例如將所有或特定電子郵件轉寄到另一個電子郵件帳戶，以及 Graph 呼叫以存取電子郵件並傳送到另一個電子郵件帳戶，可能會試圖從您的組織中竊取資訊。</span><span class="sxs-lookup"><span data-stu-id="de1c9-186">Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.</span></span>  

<span data-ttu-id="de1c9-187">**TP 或 FP？**</span><span class="sxs-lookup"><span data-stu-id="de1c9-187">**TP or FP?**</span></span>

- <span data-ttu-id="de1c9-188">**TP**：如果您可以確認收件匣規則是由 OAuth 第三方應用程式建立，並且具有從未知來源提供的可疑範圍，則表示其確判為真。</span><span class="sxs-lookup"><span data-stu-id="de1c9-188">**TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.</span></span>

  <span data-ttu-id="de1c9-189">**建議動作**：停用並移除應用程式、重設密碼，以及移除收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="de1c9-189">**Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.</span></span>

  <span data-ttu-id="de1c9-190">請遵循「如何使用 Azure Active Directory 重設密碼」教學課程，以及遵循「如何移除收件匣規則」教學課程。</span><span class="sxs-lookup"><span data-stu-id="de1c9-190">Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.</span></span>

- <span data-ttu-id="de1c9-191">**FP**：如果您可以確認該應用程式出於合法理由，為新的或個人的外部電子郵件帳戶建立收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="de1c9-191">**FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.</span></span>

  <span data-ttu-id="de1c9-192">**建議動作**：關閉警示。</span><span class="sxs-lookup"><span data-stu-id="de1c9-192">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="de1c9-193">了解入侵範圍</span><span class="sxs-lookup"><span data-stu-id="de1c9-193">Understand the scope of the breach</span></span>

1. <span data-ttu-id="de1c9-194">檢閱應用程式完成的所有活動。</span><span class="sxs-lookup"><span data-stu-id="de1c9-194">Review all activities done by the app.</span></span>
1. <span data-ttu-id="de1c9-195">檢閱應用程式授與的範圍。</span><span class="sxs-lookup"><span data-stu-id="de1c9-195">Review the scopes granted by the app.</span></span>
1. <span data-ttu-id="de1c9-196">檢閱應用程式建立的收件匣規則動作和條件。</span><span class="sxs-lookup"><span data-stu-id="de1c9-196">Review the inbox rule action and condition created by the app.</span></span>

## <a name="collection-alerts"></a><span data-ttu-id="de1c9-197">集合警示</span><span class="sxs-lookup"><span data-stu-id="de1c9-197">Collection alerts</span></span>

<span data-ttu-id="de1c9-198">本節描述的警報可指出，惡意行為者可能正嘗試從您的組織收集對其目標有益的資料。</span><span class="sxs-lookup"><span data-stu-id="de1c9-198">This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.</span></span>

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a><span data-ttu-id="de1c9-199">應用程式進行異常 Graph 呼叫以讀取電子郵件</span><span class="sxs-lookup"><span data-stu-id="de1c9-199">App made anomalous Graph calls to read e-mail</span></span>

<span data-ttu-id="de1c9-200">**嚴重性：** 中</span><span class="sxs-lookup"><span data-stu-id="de1c9-200">**Severity**: Medium</span></span>

<span data-ttu-id="de1c9-201">**MITRE 識別碼**：T1114</span><span class="sxs-lookup"><span data-stu-id="de1c9-201">**MITRE ID**: T1114</span></span>

<span data-ttu-id="de1c9-202">此偵測可發現企業營運 (LOB) OAuth 應用程式透過 Graph API 存取異常且大量的使用者郵件資料夾和郵件，這表示惡意攻擊者已嘗試入侵您的組織。</span><span class="sxs-lookup"><span data-stu-id="de1c9-202">This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.</span></span>

<span data-ttu-id="de1c9-203">**TP 或 FP？**</span><span class="sxs-lookup"><span data-stu-id="de1c9-203">**TP or FP?**</span></span>

- <span data-ttu-id="de1c9-204">**TP**：如果您可以確認異常 Graph 活動是由企業營運 (LOB) OAuth 應用程式執行的，則表示其確判為真。</span><span class="sxs-lookup"><span data-stu-id="de1c9-204">**TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.</span></span>

  <span data-ttu-id="de1c9-205">**建議**：暫時停用應用程式並重設密碼，然後重新啟用應用程式。</span><span class="sxs-lookup"><span data-stu-id="de1c9-205">**Recommend actions**: Temporarily disable the app and reset the password and then re-enable the app.</span></span>

  <span data-ttu-id="de1c9-206">請遵循「如何使用 Azure Active Directory 重設密碼」教學課程。</span><span class="sxs-lookup"><span data-stu-id="de1c9-206">Follow the tutorial on how to Reset a password using Azure Active Directory.</span></span>

- <span data-ttu-id="de1c9-207">**FP**：如果您可以確認應用程式試圖執行異常大量的 Graph 呼叫。</span><span class="sxs-lookup"><span data-stu-id="de1c9-207">**FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.</span></span>

  <span data-ttu-id="de1c9-208">**建議動作**：關閉警示。</span><span class="sxs-lookup"><span data-stu-id="de1c9-208">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="de1c9-209">了解入侵範圍</span><span class="sxs-lookup"><span data-stu-id="de1c9-209">Understand the scope of the breach</span></span>

1. <span data-ttu-id="de1c9-210">請查閱此應用程式所執行之事件的活動記錄，以深入了解其他 Graph 活動，以讀取電子郵件並嘗試收集使用者的敏感性電子郵件資訊。</span><span class="sxs-lookup"><span data-stu-id="de1c9-210">Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.</span></span>
1. <span data-ttu-id="de1c9-211">監視新增到應用程式的未預期認證。</span><span class="sxs-lookup"><span data-stu-id="de1c9-211">Monitor for unexpected credential being added to the app.</span></span>
