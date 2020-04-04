---
title: 在安全性&amp;與合規性中心中查看電子郵件安全性報告、遭到破壞的使用者、加密、威脅防護狀態、惡意程式碼偵測、主要惡意程式碼、垃圾郵件偵測、傳送和接收的電子郵件、使用者報告的訊息、讀取報表、偵測、安全性資料、安全性資訊
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/16/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 瞭解如何尋找及使用貴組織的電子郵件安全性報告。 電子郵件安全性報告可在安全性&amp;與規範中心中取得。
ms.openlocfilehash: b6c4e737d0bcc9f7373a669e8dcd20661733b294
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142704"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="29506-104">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="29506-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="29506-105">[安全性&amp;與合規性中心](https://protection.office.com)提供各種報告，可協助您瞭解 Office 365 中的電子郵件安全性功能（例如，反垃圾郵件、反惡意程式碼和加密功能）是如何保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="29506-105">A variety of reports are available in the [Security &amp; Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Office 365 are protecting your organization.</span></span> <span data-ttu-id="29506-106">如果您有[必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以移至 [**報告** \> ]**儀表板**，以在安全性&amp;與合規性中心中查看這些報告。</span><span class="sxs-lookup"><span data-stu-id="29506-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![您可以在其中看到高級威脅防護運作方式的儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="29506-108">您的電子郵件安全性報告包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="29506-108">Your email security reports include the following:</span></span>
- <span data-ttu-id="29506-109">[URL 威脅防護報告](#url-threat-protection-report-new)（**新！**）</span><span class="sxs-lookup"><span data-stu-id="29506-109">[URL Threat Protection report](#url-threat-protection-report-new) (**NEW!**)</span></span>
- [<span data-ttu-id="29506-110">已遭破壞的使用者報告</span><span class="sxs-lookup"><span data-stu-id="29506-110">Compromised Users report</span></span>](#compromised-users-report)
- [<span data-ttu-id="29506-111">加密報告</span><span class="sxs-lookup"><span data-stu-id="29506-111">Encryption report</span></span>](#encryption-report)
- [<span data-ttu-id="29506-112">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="29506-112">Threat Protection Status report</span></span>](#threat-protection-status-report) 
- [<span data-ttu-id="29506-113">惡意程式碼檢測報告</span><span class="sxs-lookup"><span data-stu-id="29506-113">Malware Detections report</span></span>](#malware-detections-report) 
- [<span data-ttu-id="29506-114">主要惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="29506-114">Top Malware report</span></span>](#top-malware-report)
- [<span data-ttu-id="29506-115">主要寄件者和收件者報表</span><span class="sxs-lookup"><span data-stu-id="29506-115">Top Senders and Recipients report</span></span>](#top-senders-and-recipients-report)
- [<span data-ttu-id="29506-116">欺騙偵測報告</span><span class="sxs-lookup"><span data-stu-id="29506-116">Spoof Detections report</span></span>](#spoof-detections-report)
- [<span data-ttu-id="29506-117">垃圾郵件偵測報告</span><span class="sxs-lookup"><span data-stu-id="29506-117">Spam Detections report</span></span>](#spam-detections-report)
- [<span data-ttu-id="29506-118">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="29506-118">Sent and received email report</span></span>](#sent-and-received-email-report)
- [<span data-ttu-id="29506-119">使用者報告的訊息報告</span><span class="sxs-lookup"><span data-stu-id="29506-119">User-reported messages report</span></span>](#user-reported-messages-report)


## <a name="url-threat-protection-report-new"></a><span data-ttu-id="29506-120">URL 威脅防護報告（**新！**）</span><span class="sxs-lookup"><span data-stu-id="29506-120">URL Threat Protection report (**NEW!**)</span></span>

<span data-ttu-id="29506-121">具有下列專案的任何人都可以使用 URL 威脅防護報告：</span><span class="sxs-lookup"><span data-stu-id="29506-121">The URL Threat Protection report is available to anyone with:</span></span>

- <span data-ttu-id="29506-122">Exchange Online Protection*和*高級威脅防護附加元件（方案 1*或*計畫2）</span><span class="sxs-lookup"><span data-stu-id="29506-122">An Exchange Online Protection, *and* Advanced Threat Protection add-on (Plan 1 *or* Plan 2)</span></span> 
- <span data-ttu-id="29506-123">Microsoft 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="29506-123">A Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="29506-124">這是以「按一下中心」的報表，具有兩個匯總的視圖。</span><span class="sxs-lookup"><span data-stu-id="29506-124">This is a 'click-centric' report that has two aggregated views.</span></span>
 
1. <span data-ttu-id="29506-125">第一個視圖是透過*url 按一下保護動作*，其重點是顯示使用者在租使用者中的 URL 按一下數目，以及按一下的結果。</span><span class="sxs-lookup"><span data-stu-id="29506-125">The first view is by *URL click-protection action*, which is focused on showing the number of URL clicks by users within the tenant, and the result of the click.</span></span> <span data-ttu-id="29506-126">A 按下會指出使用者已透過封鎖頁面按一下至惡意網站（這可以由系統管理員在安全連結原則中停用）。</span><span class="sxs-lookup"><span data-stu-id="29506-126">A click here indicates that the user has clicked through the block page to the malicious website (this can be disabled by the administrator within a Safe Links policy).</span></span>
 
2. <span data-ttu-id="29506-127">第二個 view 是*由應用程式按一下 URL*，它會顯示在目前支援安全連結的不同應用程式中，例如在電子郵件客戶程式或 Microsoft Word 中，URLs 按一下的數目。</span><span class="sxs-lookup"><span data-stu-id="29506-127">The second view is *URL click by applications*, which shows the number of URLs click in different applications that support Safe Links today, such as in an email client or in Microsoft Word.</span></span> <span data-ttu-id="29506-128">兩個匯總視圖中的資料都會每4小時重新整理一次。</span><span class="sxs-lookup"><span data-stu-id="29506-128">Data in both aggregated views are refreshed once every 4 hours.</span></span>

<span data-ttu-id="29506-129">「URL 威脅防護」報告的詳細資料表格可提供租使用者內所有按一下作業的近乎即時的視圖，其中包含諸如使用者*名稱*、 *URL*、*網路訊息識別碼*（如果 URL 已按一下電子郵件）的調查資訊，以及其他重要資訊，以供調查和分析使用。</span><span class="sxs-lookup"><span data-stu-id="29506-129">The details table of the URL Threat Protection report provides a near-real-time view of all clicks that happen within the tenant, and it includes investigative information such as *username*, *URL*, the *network message ID* (if the URL was clicked from an email), and other valuable pieces of information useful for investigations and analyses.</span></span>  

<span data-ttu-id="29506-130">根據預設，報告只會顯示由安全連結所封鎖 URLs 所按一下的資料，但也可以查看所有 URL 按一下的資訊，在篩選器中選取 [*允許的 URLs* ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="29506-130">By default, the report only shows data on clicks from URLs that were blocked by Safe Links, but it is also possible to see information for all URL clicks through selecting *Allowed URLs* checkbox in the filters.</span></span>  

<span data-ttu-id="29506-131">如果已套用安全連結原則的使用者已選取 [*不追蹤使用者點擊*] 選項，則此報告將不會有按一下的資料。</span><span class="sxs-lookup"><span data-stu-id="29506-131">This report will not have data of clicks from users where the Safe Links policy applied has the *Do not track user clicks* option selected.</span></span>

![動作中的 URL 威脅防護報告圖形。](../../media/tp-URLThreatProRpt1.PNG)

## <a name="compromised-users-report"></a><span data-ttu-id="29506-133">已遭破壞的使用者報告</span><span class="sxs-lookup"><span data-stu-id="29506-133">Compromised Users report</span></span> 

<span data-ttu-id="29506-134">這份報告可供任何使用 Exchange Online Protection 的使用者，顯示標示為可疑或受限制使用者的使用者帳戶數目，當帳戶進入指出使用者帳戶可能有問題或甚至遭到破壞的狀態時，資料特別有用。</span><span class="sxs-lookup"><span data-stu-id="29506-134">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="29506-135">在經常使用的情況下，已遭破壞的使用者報告可以發現具有可疑或限制狀態之帳戶中的波峰峰值，甚至是趨勢，也就是您租使用者的安全性和 wellness 可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="29506-135">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![已遭破壞的使用者會在 Office 365 中報告。](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a><span data-ttu-id="29506-137">加密報告</span><span class="sxs-lookup"><span data-stu-id="29506-137">Encryption report</span></span>

<span data-ttu-id="29506-138">**加密報告**會顯示已加密之電子郵件的相關資訊，不論是透過您組織的原則或透過使用者控制項。</span><span class="sxs-lookup"><span data-stu-id="29506-138">The **Encryption report** shows information about email messages that were encrypted, either through your organization's policies, or through end-user controls.</span></span> <span data-ttu-id="29506-139">組織的安全小組可以使用此報告中的資訊來識別模式，並主動套用或調整敏感電子郵件訊息的原則。</span><span class="sxs-lookup"><span data-stu-id="29506-139">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span>

<span data-ttu-id="29506-140">若要查看此報告，請在安全性 & 合規性中心，移至 [**報告** \> **] 儀表板** \> **加密報告**。</span><span class="sxs-lookup"><span data-stu-id="29506-140">To view this report, in the Security & Compliance Center, go to **Reports** \> **Dashboard** \> **Encryption report**.</span></span>

![加密報告](../../media/encryptionreport-defaultview.png) 

<span data-ttu-id="29506-142">當報表第一次開啟時，您會看到過去七（7）天內，電子郵件所使用之加密方法的資料。</span><span class="sxs-lookup"><span data-stu-id="29506-142">When the report first opens, you'll see data about encryption methods used on email messages for the past seven (7) days.</span></span> <span data-ttu-id="29506-143">您可以按一下螢幕右上角的 [**篩選器**]，以變更日期範圍及顯示在報告中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="29506-143">You can change the date range and the details that are displayed in the report by clicking **Filters** in the upper right corner of the screen.</span></span>

![加密報告篩選器](../../media/encryptionreport-filters.png)   

<span data-ttu-id="29506-145">您也可以使用 [**分解者**] 功能表，透過加密範本（或方法）來查看資料。</span><span class="sxs-lookup"><span data-stu-id="29506-145">You can also use the **Break down by** menu to view data by encryption template (or method).</span></span>

![加密方法或範本](../../media/encryptionreport-breakdownby.png)

<span data-ttu-id="29506-147">而且，您可以使用 [ **view data by** ] 功能表，將 view 改為查看前5位收件者網域的加密郵件計數。</span><span class="sxs-lookup"><span data-stu-id="29506-147">And, you can use the **View data by** menu to change the view to see counts of encrypted messages to the top five recipient domains.</span></span>

![加密報告依功能表查看資料](../../media/encryptionreport-viewdataby.png)

<span data-ttu-id="29506-149">使用新加密報告的彈性，您可以查看趨勢並採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="29506-149">With the flexibility of the new Encryption report, you can view trends and take appropriate actions.</span></span> <span data-ttu-id="29506-150">例如，如果您看到大量的電子郵件是由使用者加密，您可能會想要新增加密原則，以自動化某些使用案例的加密。</span><span class="sxs-lookup"><span data-stu-id="29506-150">For example, if you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="29506-151">（若要取得此相關說明，請參閱[定義郵件流程規則以在 Office 365 中加密電子郵件訊息](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。）在另一個範例中，如果您有許多可供使用的加密範本，但沒有人正在使用這些範本，則可以考察使用者是否需要對該功能進行訓練。</span><span class="sxs-lookup"><span data-stu-id="29506-151">(To get help with that, see [Define mail flow rules to encrypt email messages in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) As another example, if you have a number of encryption templates available but no one is using them, you might explore whether users need training for that feature.</span></span> 

<span data-ttu-id="29506-152">使用此報告可讓貴組織的安全性與合規性小組監視郵件加密的使用方式，以及是否需要進一步的動作。</span><span class="sxs-lookup"><span data-stu-id="29506-152">Use this report enables your organization's security and compliance team to monitor how message encryption is being used, and whether further actions are needed.</span></span> <span data-ttu-id="29506-153">若要深入瞭解加密，請參閱[Office 365 中的電子郵件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="29506-153">To learn more about encryption, see [Email encryption in Office 365](../../compliance/email-encryption.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="29506-154">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="29506-154">Threat Protection Status report</span></span>

<span data-ttu-id="29506-155">「**威脅防護狀態**報告」是一個智慧報告，顯示 Exchange Online Protection 偵測到並封鎖的惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="29506-155">The **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection.</span></span> <span data-ttu-id="29506-156">此報告可用於查看識別為惡意程式碼的電子郵件，或一段時間內的網路釣魚企圖（最多90天），並可讓安全性管理員識別趨勢或判斷是否需要調整原則。</span><span class="sxs-lookup"><span data-stu-id="29506-156">This report is useful for viewing email identified as malware or a phishing attempt over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

> [!NOTE]
> <span data-ttu-id="29506-157">具有[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)或[Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) （EOP）的客戶可以使用威脅防護狀態報表;不過，針對 ATP 客戶顯示在威脅防護狀態報表中的資訊，其可能會包含與客戶可能看到的 EOP 不同的資料。</span><span class="sxs-lookup"><span data-stu-id="29506-157">A Threat Protection Status report is available to customers who have either [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) or [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="29506-158">例如，EOP 客戶可以查看在電子郵件中偵測到惡意程式碼的相關資訊，但不是[在 SharePoint Online、OneDrive 或 Microsoft 小組中偵測到的惡意](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)檔案資訊，也就是 ATP 特有的功能。</span><span class="sxs-lookup"><span data-stu-id="29506-158">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), an ATP-specific capability.</span></span> <span data-ttu-id="29506-159">（[深入瞭解 ATP 報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)。）</span><span class="sxs-lookup"><span data-stu-id="29506-159">([Learn more about ATP reports](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span></span>
  
<span data-ttu-id="29506-160">若要在[安全性&amp;與合規性中心](https://protection.office.com)中查看此報告，請移至 [**報告** \> **] 儀表板** \> **威脅防護狀態**。</span><span class="sxs-lookup"><span data-stu-id="29506-160">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![威脅防護狀態報告](../../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="29506-162">當您第一次開啟威脅防護狀態報表時，報告預設會顯示過去7天的資料。不過，您可以按一下 [**篩選**]，然後在 [最多90天] 的 [詳細資料] 中變更日期範圍。</span><span class="sxs-lookup"><span data-stu-id="29506-162">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail.</span></span> <span data-ttu-id="29506-163">（如果您是使用試用訂閱，則可能會限制為30天的資料。）</span><span class="sxs-lookup"><span data-stu-id="29506-163">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

<span data-ttu-id="29506-164">此報告可用於查看組織的[Exchange Online Protection 功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)和長期趨勢分析的效能與影響。</span><span class="sxs-lookup"><span data-stu-id="29506-164">This report is useful for viewing the effectiveness and impact of your organization's [Exchange Online Protection features](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features), and for longer-term trending.</span></span> 
  
![威脅防護狀態報表篩選](../../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="29506-166">您也可以選擇是否要針對識別為惡意的電子郵件、識別為網路釣魚企圖的電子郵件，或是識別為包含惡意程式碼的電子郵件，來查看資料。</span><span class="sxs-lookup"><span data-stu-id="29506-166">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![威脅防護狀態報表檢視選項](../../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="29506-168">惡意程式碼檢測報告</span><span class="sxs-lookup"><span data-stu-id="29506-168">Malware Detections report</span></span>

<span data-ttu-id="29506-169">**惡意軟體**偵測報告會顯示偵測到包含組織之惡意程式碼的傳入和傳出郵件數目。</span><span class="sxs-lookup"><span data-stu-id="29506-169">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="29506-170">若要查看此報告，請[在&amp;安全性與合規性中心](https://protection.office.com)，移至 [**報告** \> ]**儀表板** \> **惡意程式碼檢測**。</span><span class="sxs-lookup"><span data-stu-id="29506-170">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![惡意程式碼偵測報告範例](../../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="29506-172">與其他報告類似于「[威脅防護狀態」報告](#threat-protection-status-report)，報表預設會顯示過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="29506-172">Similar to other reports, like the [Threat Protection Status report](#threat-protection-status-report), the report displays data for the past seven days by default.</span></span> <span data-ttu-id="29506-173">不過，您可以選擇 [**篩選**] 以變更日期範圍。</span><span class="sxs-lookup"><span data-stu-id="29506-173">However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="29506-174">主要惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="29506-174">Top Malware report</span></span>

<span data-ttu-id="29506-175">**主要惡意**代碼報告會顯示[Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)偵測到的各種惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="29506-175">The **Top Malware** report shows the various kinds of malware that was detected by [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span></span> 
  
<span data-ttu-id="29506-176">若要查看此報告，請[在&amp;安全性與合規性中心](https://protection.office.com)，移至 [**報告** \> ]**儀表板** \>的**主要惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="29506-176">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC-EOP 主要惡意程式碼](../../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="29506-178">當您將游標移到圓形圖中的楔形上方時，您可以看到惡意程式碼類型的名稱，以及偵測到該惡意程式碼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="29506-178">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="29506-179">按一下（或點擊）報表，以在新的瀏覽器視窗中開啟它，您可以在其中取得更詳細的報表檢視。</span><span class="sxs-lookup"><span data-stu-id="29506-179">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![此報告顯示針對您的組織偵測到的主要惡意程式碼](../../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="29506-181">在圖表下方，您會看到偵測到的惡意程式碼，以及偵測到該惡意程式碼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="29506-181">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="29506-182">主要寄件者和收件者報表</span><span class="sxs-lookup"><span data-stu-id="29506-182">Top Senders and Recipients report</span></span>

<span data-ttu-id="29506-183">「**主要寄件者與收件**者」報告是顯示您主要電子郵件寄件者的餅形圖。</span><span class="sxs-lookup"><span data-stu-id="29506-183">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="29506-184">若要查看此報告，請[在&amp;安全性與合規性中心](https://protection.office.com)，移至 [**報告** \> ]**儀表板** \>的**頁首和收件**者。</span><span class="sxs-lookup"><span data-stu-id="29506-184">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![若要查看此報告，請在&amp;安全性與合規性中心， \>移\>至 [報告] 儀表板的頁首和收件者](../../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="29506-186">當您將游標移到圓形圖中的楔形上方時，您可以看到所傳送或接收的郵件計數。</span><span class="sxs-lookup"><span data-stu-id="29506-186">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="29506-187">按一下（或點擊）報表，以在新的瀏覽器視窗中開啟它，您可以在其中取得更詳細的報表檢視。</span><span class="sxs-lookup"><span data-stu-id="29506-187">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="29506-188">使用 [**顯示資料**] 清單，選擇是否要查看主要寄件者、接收器、垃圾郵件收件者和惡意程式碼收件者的資料。</span><span class="sxs-lookup"><span data-stu-id="29506-188">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients.</span></span> <span data-ttu-id="29506-189">您也可以查看[Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop)已偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="29506-189">You can also see who received malware that was detected by [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span></span> 
  
![使用 [顯示資料] 清單查看特定資訊](../../media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="29506-191">在圖表下方，您會看到最上層的電子郵件寄件者或收件者，以及指定時間週期內傳送或接收的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="29506-191">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-detections-report"></a><span data-ttu-id="29506-192">欺騙偵測報告</span><span class="sxs-lookup"><span data-stu-id="29506-192">Spoof Detections report</span></span>

<span data-ttu-id="29506-193">「**欺騙**偵測報告」會顯示偵測到的電子郵件訊息數量，以及那些被視為「良好」（由於正當商務理由而完成的電子郵件）。</span><span class="sxs-lookup"><span data-stu-id="29506-193">The **Spoof Detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="29506-194">若要查看此報告，請[在&amp;安全性與合規性中心](https://protection.office.com)，移至 [**報告** \> ]**儀表板** \> **冒名郵件**。</span><span class="sxs-lookup"><span data-stu-id="29506-194">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![在安全性&amp;與合規性中心，移至\> [ \>報告] 儀表板冒名郵件](../../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="29506-196">當您將游標移到圖表中的某一天時，您可以看到有多少偽造的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="29506-196">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="29506-197">按一下（或點擊）報表，以在新的瀏覽器視窗中開啟它，您可以在其中取得更詳細的報表檢視。</span><span class="sxs-lookup"><span data-stu-id="29506-197">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span> <span data-ttu-id="29506-198">若要深入瞭解反欺騙防護，請參閱[Office 365 中的反欺騙保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection)。</span><span class="sxs-lookup"><span data-stu-id="29506-198">To learn more about anti-spoof protection, see [Anti-spoofing protection in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="29506-199">垃圾郵件偵測報告</span><span class="sxs-lookup"><span data-stu-id="29506-199">Spam Detections report</span></span>

<span data-ttu-id="29506-200">**垃圾郵件**偵測報告會顯示 Exchange Online 所封鎖的所有垃圾郵件內容。</span><span class="sxs-lookup"><span data-stu-id="29506-200">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> <span data-ttu-id="29506-201">郵件會依每封郵件計算，而非每個收件者。</span><span class="sxs-lookup"><span data-stu-id="29506-201">Messages are counted per message, and not per recipient.</span></span> <span data-ttu-id="29506-202">例如，如果電子郵件訊息傳送至您組織中的100收件者，則會將它計為一封郵件。</span><span class="sxs-lookup"><span data-stu-id="29506-202">For example, if an email message was sent to 100 recipients in your organization, it is counted as one message.</span></span>
  
<span data-ttu-id="29506-203">若要查看此報告，請[在&amp;安全性與合規性中心](https://protection.office.com)，移至 [**報告** \> ]**儀表板** \> **垃圾郵件**偵測。</span><span class="sxs-lookup"><span data-stu-id="29506-203">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![若要查看此報告，請在&amp;安全性與合規性中心， \>移\>至 [報告] 儀表板 EOP 垃圾郵件偵測](../../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="29506-205">當您將游標移到圖表中的某一天時，您可以查看該天已封鎖的專案數，以及這些專案的分類方式。</span><span class="sxs-lookup"><span data-stu-id="29506-205">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span> <span data-ttu-id="29506-206">例如，您可以查看已篩選的垃圾郵件數目，以及來自封鎖的網際網路通訊協定（IP）位址的專案數目。</span><span class="sxs-lookup"><span data-stu-id="29506-206">For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="29506-207">按一下（或點擊）報表，以在新的瀏覽器視窗中開啟它，您可以在其中取得更詳細的報表檢視。</span><span class="sxs-lookup"><span data-stu-id="29506-207">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![垃圾郵件偵測報告可告訴您封鎖或篩選出的垃圾郵件數目](../../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="29506-209">在圖表下方，您會看到偵測到的垃圾郵件專案清單。</span><span class="sxs-lookup"><span data-stu-id="29506-209">Below the chart, you'll see a list of spam items that were detected.</span></span> <span data-ttu-id="29506-210">選取專案以查看其他資訊，例如垃圾郵件專案為輸入或輸出、郵件識別碼及收件者。</span><span class="sxs-lookup"><span data-stu-id="29506-210">Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span> <span data-ttu-id="29506-211">若要深入瞭解反垃圾郵件保護，請參閱[Office 365 電子郵件反垃圾郵件保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)。</span><span class="sxs-lookup"><span data-stu-id="29506-211">To learn more about anti-spam protection, see [Office 365 email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="29506-212">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="29506-212">Sent and received email report</span></span>

<span data-ttu-id="29506-213">「**傳送及接收的電子郵件**報告」是一個智慧報告，顯示傳入和傳出電子郵件的相關資訊，包括垃圾郵件偵測、惡意程式碼，以及識別為「良好」的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="29506-213">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="29506-214">若要查看此報告，請[在&amp;安全性與合規性中心](https://protection.office.com)，移至 [**報告** \> ]**儀表板** \> **傳送和接收的電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="29506-214">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![若要查看此報告，請在&amp;安全性與合規性中心， \>移\>至 [報告] 儀表板傳送和接收的電子郵件](../../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="29506-216">當您將游標移到圖表中的某一天時，您就可以看到已有多少封郵件，以及這些郵件的分類方式。</span><span class="sxs-lookup"><span data-stu-id="29506-216">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized.</span></span> <span data-ttu-id="29506-217">例如，您可以查看偵測到包含惡意程式碼的郵件數目，以及識別為垃圾郵件的數目。</span><span class="sxs-lookup"><span data-stu-id="29506-217">For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="29506-218">按一下（或點擊）報表，以在新的瀏覽器視窗中開啟它，您可以在其中取得更詳細的報表檢視。</span><span class="sxs-lookup"><span data-stu-id="29506-218">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="29506-219">您可以使用 [**分解依據**] 清單，依類型或依方向（內送和外送）來查看資訊。</span><span class="sxs-lookup"><span data-stu-id="29506-219">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![使用 [分解依據] 清單，依類型或方向查看資訊](../../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="29506-221">在圖表下方，您會看到一個電子郵件類別清單，例如 [ **GoodMail**]、[ **SpamContentFiltered**] 等等。</span><span class="sxs-lookup"><span data-stu-id="29506-221">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on.</span></span> <span data-ttu-id="29506-222">選取類別以查看其他資訊，例如針對惡意程式碼採取的動作，以及電子郵件是傳入或傳出。</span><span class="sxs-lookup"><span data-stu-id="29506-222">Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![這個報告可告訴您反惡意程式碼、反垃圾郵件和其他郵件偵測](../../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

<span data-ttu-id="29506-224">若要深入瞭解電子郵件智慧，請參閱[Office 365 中的郵件流程智慧](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="29506-224">To learn more about email intelligence, see [Mail flow intelligence in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span></span>
  
## <a name="user-reported-messages-report"></a><span data-ttu-id="29506-225">使用者報告的訊息報告</span><span class="sxs-lookup"><span data-stu-id="29506-225">User-reported messages report</span></span>

<span data-ttu-id="29506-226">「**使用者報告的訊息**報告」顯示使用者已使用[報告郵件增益集](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)舉報為垃圾郵件、網路釣魚企圖或良好郵件的電子郵件資訊。</span><span class="sxs-lookup"><span data-stu-id="29506-226">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>
  
<span data-ttu-id="29506-227">詳細資料可用於每封郵件，包括傳遞原因、為您的組織設定的垃圾郵件原則例外狀況或郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="29506-227">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="29506-228">若要查看詳細資料，請選取 [使用者報告] 清單中的專案，然後查看 [**摘要**] 和 [**詳細資料**] 索引標籤上的資訊。</span><span class="sxs-lookup"><span data-stu-id="29506-228">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![使用者報告的郵件報告會顯示使用者標示為垃圾郵件，而非垃圾郵件或網路釣魚企圖。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="29506-230">若要查看此報告，請[在&amp;安全性與合規性中心](https://protection.office.com)執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="29506-230">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), do one of the following:</span></span>
  
- <span data-ttu-id="29506-231">移至**威脅管理** \> **儀表板** \> **使用者報告的郵件**。</span><span class="sxs-lookup"><span data-stu-id="29506-231">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="29506-232">移至**威脅管理** \> **檢查** \> **使用者報告的郵件**。</span><span class="sxs-lookup"><span data-stu-id="29506-232">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![在 [安全性&amp;與合規性中心] 中\> ， \>選擇 [威脅管理] 複查使用者報告的訊息](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="29506-234">為了讓使用者報告的郵件報告正確運作，您必須為您的 Office 365 環境**開啟審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="29506-234">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="29506-235">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="29506-235">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="29506-236">如需詳細資訊，請參閱[開啟或關閉 Office 365 稽核記錄搜尋](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="29506-236">For more information, see [Turn Office 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="29506-237">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="29506-237">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="29506-238">為了查看和使用本文所述的報告，**您必須為安全性&amp;與合規性中心和 Exchange 系統管理中心指派適當的角色**。</span><span class="sxs-lookup"><span data-stu-id="29506-238">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="29506-239">針對「安全性與合規性中心」，您必須受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="29506-239">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="29506-240">組織管理</span><span class="sxs-lookup"><span data-stu-id="29506-240">Organization Management</span></span>
    - <span data-ttu-id="29506-241">安全性管理員（可以在 Azure Active Directory 系統管理中心中指派[https://aad.portal.azure.com](https://aad.portal.azure.com)）</span><span class="sxs-lookup"><span data-stu-id="29506-241">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="29506-242">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="29506-242">Security Reader</span></span>

- <span data-ttu-id="29506-243">針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) 受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="29506-243">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="29506-244">組織管理</span><span class="sxs-lookup"><span data-stu-id="29506-244">Organization Management</span></span>
    - <span data-ttu-id="29506-245">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="29506-245">View-only Organization Management</span></span>
    - <span data-ttu-id="29506-246">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="29506-246">View-Only Recipients role</span></span>
    - <span data-ttu-id="29506-247">合規性管理</span><span class="sxs-lookup"><span data-stu-id="29506-247">Compliance Management</span></span>

<span data-ttu-id="29506-248">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="29506-248">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="29506-249">Office 365 安全性與合規性中心權限</span><span class="sxs-lookup"><span data-stu-id="29506-249">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [<span data-ttu-id="29506-250">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="29506-250">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="29506-251">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="29506-251">What if the reports aren't showing data?</span></span>

<span data-ttu-id="29506-252">如果您未看到報表中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="29506-252">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="29506-253">若要深入了解，請參閱[防範 Office 365 中的威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。</span><span class="sxs-lookup"><span data-stu-id="29506-253">To learn more, see [Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="29506-254">相關主題</span><span class="sxs-lookup"><span data-stu-id="29506-254">Related topics</span></span>

[<span data-ttu-id="29506-255">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="29506-255">Office 365 Email Anti-Spam Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)
  
[<span data-ttu-id="29506-256">Office 365 安全性&amp;與合規性中心內的報告與深入瞭解</span><span class="sxs-lookup"><span data-stu-id="29506-256">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)
  
[<span data-ttu-id="29506-257">在安全性&amp;與合規性中心建立報表的排程</span><span class="sxs-lookup"><span data-stu-id="29506-257">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)
  
[<span data-ttu-id="29506-258">在安全性&amp;與合規性中心內設定及下載自訂報告</span><span class="sxs-lookup"><span data-stu-id="29506-258">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
  

