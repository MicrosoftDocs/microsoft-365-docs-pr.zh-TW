---
title: 將保護套用至個人資料
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何使用資料外洩防護 (DLP) 原則來保護 Microsoft 365 中的個人資料。
ms.openlocfilehash: 54bfdd27f5c18d6c145b1e9f13c5e92c1b322048
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634271"
---
# <a name="apply-protection-to-personal-data"></a><span data-ttu-id="2fe9c-103">將保護套用至個人資料</span><span class="sxs-lookup"><span data-stu-id="2fe9c-103">Apply protection to personal data</span></span>

<span data-ttu-id="2fe9c-104">Microsoft 365 中的個人資訊保護包括使用資料外洩防護功能。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-104">Protection of personal information in Microsoft 365 includes using data loss prevention capabilities.</span></span> <span data-ttu-id="2fe9c-105">透過合規性中心的資料外洩防護 (DLP) 原則，您可以識別、監視及自動保護整個 Microsoft 365 的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-105">With data loss prevention (DLP) policies in the compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span>

<span data-ttu-id="2fe9c-p102">本主題描述如何使用 DLP 保護個人資料。本主題也會列出可用來實現 GDPR 規範的其他保護功能，包括在 SharePoint 文件庫中設定權限，以及使用裝置存取原則。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p102">This topic describes how to use DLP to protect personal data. This topic also lists other protection capabilities that can be used to achieve GDPR compliance, including setting permissions in SharePoint libraries and using device access policies.</span></span>

## <a name="apply-protection-using-data-loss-prevention-in-microsoft-365"></a><span data-ttu-id="2fe9c-108">使用 Microsoft 365 中的資料外洩防護來套用保護</span><span class="sxs-lookup"><span data-stu-id="2fe9c-108">Apply protection using data loss prevention in Microsoft 365</span></span>

<span data-ttu-id="2fe9c-109">使用 DLP 時，您可以：</span><span class="sxs-lookup"><span data-stu-id="2fe9c-109">With DLP, you can:</span></span>

-   <span data-ttu-id="2fe9c-110">識別各個位置中的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-110">Identify sensitive information across many locations.</span></span>

-   <span data-ttu-id="2fe9c-111">防止意外共用敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-111">Prevent accidental sharing of sensitive information.</span></span>

-   <span data-ttu-id="2fe9c-112">協助使用者了解如何符合規範，而不中斷其工作流程。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-112">Help users learn how to stay compliant without interrupting their workflow.</span></span>

-   <span data-ttu-id="2fe9c-113">檢視 DLP 報告以了解有哪些內容符合您的組織的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-113">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="2fe9c-114">如需詳細資訊，請參閱[資料外洩防護原則概觀](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-114">For more information, see [Overview of data loss prevention policies](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span></span>

![用於建立資料外洩防護原則的選項](../media/Apply-protection-to-personal-data-in-Office-365-image1.png)

<span data-ttu-id="2fe9c-116">下圖顯示用於建立 DLP 原則的選項：</span><span class="sxs-lookup"><span data-stu-id="2fe9c-116">This illustration shows the options for creating a DLP policy:</span></span>

-   <span data-ttu-id="2fe9c-p103">選擇要套用的保護。保護可以包含：</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p103">Choose the protection to apply. Protection can include:</span></span>

    -   <span data-ttu-id="2fe9c-119">使用者的原則提示</span><span class="sxs-lookup"><span data-stu-id="2fe9c-119">Policy tips for users</span></span>

    -   <span data-ttu-id="2fe9c-120">系統管理員的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="2fe9c-120">Email report for admins</span></span>

    -   <span data-ttu-id="2fe9c-121">防止外部共用、內部共用或兩者</span><span class="sxs-lookup"><span data-stu-id="2fe9c-121">Prevent sharing externally, internally, or both</span></span>

-   <span data-ttu-id="2fe9c-p104">選擇套用保護的準則。使用這種類型的內容，將保護套用至文件：您可以設定原則，來使用敏感資訊類型和/或標籤。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p104">Choose the criteria for applying the protection. Apply the protection to documents with this type of content: you can configure the policy to use sensitive information types and/or labels.</span></span>

### <a name="using-dlp-for-gdpr-compliance"></a><span data-ttu-id="2fe9c-124">對 GDPR 規範使用 DLP</span><span class="sxs-lookup"><span data-stu-id="2fe9c-124">Using DLP for GDPR compliance</span></span>

<span data-ttu-id="2fe9c-p105">Microsoft 365 DLP 的其中一個主要用途為識別 Microsoft 365 環境中與歐盟資料主旨相關的個人資料。Microsoft 365 DLP 可以通知規範小組，個人資訊在 SharePoint Online 和商務用 OneDrive 的儲存位置，或使用者何時傳送包含個人資訊的電子郵件。使用與歐盟居民相關的個人資訊時，DLP 也可以為您的員工提供原則提示。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p105">One of the primary uses of Microsoft 365 DLP is to identify personal data related to EU data subjects in your Microsoft 365 environment. Microsoft 365 DLP can notify your compliance teams of where personal information is stored in SharePoint Online and OneDrive for Business, or when users send email containing personal information. DLP can also provide policy tips to your employees when working with personal information related to EU residents.</span></span>

<span data-ttu-id="2fe9c-p106">教育並認知歐盟居民資料應儲存在您環境的何處中，以及允許您的員工如何處理這些資料，這代表一種使用 Microsoft 365 DLP 的資訊保護層級。通常，已有權存取這類資訊的員工需要這個存取權，才能進行其日常工作。實施 DLP 原則來協助遵循 GDPR，可能不需要限制存取。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p106">Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Microsoft 365 DLP. Often, employees who already have access to this type of information require this access to do their day to day work. Enforcing DLP policies to help comply with GDPR may not require restricting access.</span></span>

<span data-ttu-id="2fe9c-p107">不過，遵循 GDPR 通常包含組織的風險型評估，其依循法律與資訊安全觀點、何種類型與個人資訊儲存位置的識別，以及是否有儲存及處理該資訊的法律理由。根據此評估，實作原則來保護組織及遵循 GDPR，可能需要移除員工對文件的存取，而此文件包含歐盟資料主旨的個人資訊。若需要進一步保護，可以另外設定 DLP 保護。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p107">However, complying with GDPR typically involves a risk-based assessment of the organization from both a legal and information security perspective, identification of what type and where personal information is stored, as well as if there's a legal justification to store and process that information. Based on this assessment, implementing policies to protect the organization and comply with GDPR might require removing access for employees to documents that contain personal information for EU data subjects. In cases where further protection is required, additional DLP protection can be configured.</span></span>

<span data-ttu-id="2fe9c-p108">下表列出三個使用 DLP 增加保護的設定。第一個設定 (認知).可以用作起點，以及 GDPR 的最低保護層級。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p108">The following table lists three configurations of increasing protection using DLP. The first configuration, awareness, can be used as a starting point and minimum level of protection for GDPR.</span></span>

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a><span data-ttu-id="2fe9c-136">可以使用 DLP 原則來設定及用於 GDPR 規範的保護層級範例</span><span class="sxs-lookup"><span data-stu-id="2fe9c-136">Example protection levels that can be configured with DLP policies and used for GDPR compliance</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fe9c-137"><strong>保護層級</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-137"><strong>Protection level</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-138"><strong>具有與歐盟資料主旨相關的個人資訊之文件的 DLP 設定</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-138"><strong>DLP configuration for documents with personal information related to EU data subjects</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-139"><strong>效益與風險</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-139"><strong>Benefits and risks</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-140">認知</span><span class="sxs-lookup"><span data-stu-id="2fe9c-140">Awareness</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-141">在 SharePoint Online 和商務用 OneDrive 的文件中找到此資料時，將電子郵件通知傳送至規範小組。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-141">Send email notifications to compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business.</span></span></p>
<p><span data-ttu-id="2fe9c-142">存取包含此資料的文件時，在 SharePoint 和商務用 OneDrive 中自訂原則提示並向員工顯示。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-142">Customize and display Policy Tips to employees in SharePoint and OneDrive for Business when accessing documents containing this data.</span></span></p>
<p><span data-ttu-id="2fe9c-143">共用此資料時偵測報告。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-143">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fe9c-144">提高規範小組以及員工關於此資料儲存位置的認知。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-144">Raise awareness with compliance teams and employees about where this data is stored.</span></span></p>
<p><span data-ttu-id="2fe9c-145">教育員工關於處理包含此資料之文件的公司原則。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-145">Educate employees on corporate policy for handling documents containing this data.</span></span></p>
<p><span data-ttu-id="2fe9c-146">不阻止員工在內部或外部共用資料。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-146">Does not prevent employees from sharing this data internally or externally.</span></span></p>
<p><span data-ttu-id="2fe9c-147">您可以檢閱共用資料的 DLP 報告，並決定是否需要增加保護。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-147">You can review DLP reports for shared data and decide if you need to increase the protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-148">阻止外部共用</span><span class="sxs-lookup"><span data-stu-id="2fe9c-148">Prevent external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-149">當此資料與外部使用者共用時，即會限制存取 SharePoint 和商務用 OneDrive 中包含該內容的文件。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-149">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared with external users.</span></span></p>
<p><span data-ttu-id="2fe9c-150">文件若包含此資料，即會阻止將具有該文件的電子郵件傳送至外部收件者。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-150">Prevent sending emails with documents that contain this data to external recipients.</span></span></p>
<p><span data-ttu-id="2fe9c-151">共用此資料時偵測報告。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-151">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fe9c-152">允許員工內部使用此資料時，即會阻止外部共用此資料。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-152">Prevents external sharing of this data while allowing for employees to work with this data internally.</span></span></p>
<p><span data-ttu-id="2fe9c-153">您可以檢閱內部共用資料的 DLP 報告，並決定是否需要增加此保護。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-153">You can review DLP reports for internally shared data and decide if you need to increase this protection.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-154">阻止內部及外部共用</span><span class="sxs-lookup"><span data-stu-id="2fe9c-154">Prevent internal and external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-155">在內部或外部共用此資料時，即會限制存取 SharePoint 和商務用 OneDrive 中包含該內容的文件。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-155">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared internally or externally.</span></span></p>
<p><span data-ttu-id="2fe9c-156">阻止包含此資料的電子郵件同時傳送至內部和外部收件者。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-156">Prevent sending emails that contain this data to both internal and external recipients.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fe9c-157">阻止內部及外部共用此資料</span><span class="sxs-lookup"><span data-stu-id="2fe9c-157">Prevents internal and external sharing of this data.</span></span></p>
<p><span data-ttu-id="2fe9c-158">員工可能會無法完成需要使用此資料的工作。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-158">Employees might not be able to complete tasks that require working with this data.</span></span></p>
<p><span data-ttu-id="2fe9c-159">您可以檢閱內部或外部共用資料的 DLP 報告，並決定是否需要使用者訓練。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-159">You can review DLP reports for internally or externally shared data and decide if end-user training is needed.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2fe9c-p109">附註：當保護層級增加時，在某些情況下，使用者存取資訊的能力將會降低，而且可能會影響其生產力或完成日常工作的能力。實作影響員工的原則來增加保護層級，通常會伴隨使用者訓練、教育使用者關於新的安全性原則，以及協助他們在更安全的環境中繼續提高生產力。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p109">Note: As the levels of protection increase, the ability of users to access information will decrease in some cases, and could potentially impact their productivity or ability to complete day to day tasks. Increasing protection levels by implementing policies that impact employees is typically accompanied by end-user training, educating users on new security policies and procedures to help them continue to be productive in a more secure environment.</span></span>

### <a name="example-dlp-policy-for-gdpr--awareness"></a><span data-ttu-id="2fe9c-162">GDPR 的外部 DLP 原則 — 認知</span><span class="sxs-lookup"><span data-stu-id="2fe9c-162">Example DLP policy for GDPR — Awareness</span></span> 

<span data-ttu-id="2fe9c-163">名稱：受到 GDPR 約束之個人資料的認知。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-163">Name: Awareness for personal data that is subject to GDPR.</span></span>

<span data-ttu-id="2fe9c-164">描述：向員工顯示原則提示、在 SharePoint 和商務用 OneDrive 的文件中找到此資料時通知規範小組、在您組織之外共用此資料時偵測並回報。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-164">Description: Display policy tips to employees, notify compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business, detect and report when this data is being shared outside your organization.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fe9c-165"><strong>控制</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-165"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-166"><strong>設定</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-166"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-167">選擇要保護的資訊</span><span class="sxs-lookup"><span data-stu-id="2fe9c-167">Choose information to protect</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-168">選取自訂原則範本。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-168">Select a Custom policy template.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-169">位置</span><span class="sxs-lookup"><span data-stu-id="2fe9c-169">Locations</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-170">Microsoft 365 中的所有位置</span><span class="sxs-lookup"><span data-stu-id="2fe9c-170">All locations in Microsoft 365</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-171">尋找包含的內容</span><span class="sxs-lookup"><span data-stu-id="2fe9c-171">Find content that contains</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-172">按一下 [編輯]，然後新增所有您針對環境策劃的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-172">Click 'Edit' and add all the sensitive information types you curated for your environment.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-173">在共用此內容時偵測</span><span class="sxs-lookup"><span data-stu-id="2fe9c-173">Detect when this content is shared</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-174">核取此方塊，然後選取 [與我組織外的人員]。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-174">Check this box and select 'with people outside my organization.'</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-175">在內容符合原則設定時通知使用者</span><span class="sxs-lookup"><span data-stu-id="2fe9c-175">Notify users when content matches the policy settings</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-176">核取此方塊 (「向使用者顯示原則提示並傳送電子郵件通知。」)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-176">Check this box ("Show policy tips to users and send them an email notification.")</span></span></p>
<p><span data-ttu-id="2fe9c-p110">按一下 [自訂提示和電子郵件]，並針對您的環境更新這些項目。請參閱本文中的預設通知：<a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">傳送電子郵件通知，並顯示 DLP 原則的原則提示</a>。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p110">Click 'Customize the tip and email' and update these for your environment. See the default notifications in this article: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Send email notifications and show policy tips for DLP policies</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-179">在一次共用特定數量的敏感資訊時偵測</span><span class="sxs-lookup"><span data-stu-id="2fe9c-179">Detect when a specific amount of sensitive info is being shared at one time</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-180">[在共用的內容包含：至少 ___ 個執行個體，屬於相同的敏感資訊類型時偵測] — 將此項設為 1。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-180">'Detect when content that's being shared contains: At least ____ instances of the same sensitive info type' — Set this to 1.</span></span></p>
<p><span data-ttu-id="2fe9c-p111">[以電子郵件傳送事件報告] — 請核取此方塊。按一下 [選擇要包含在報告中的項目以及接收者]。請務必新增您的合規性小組。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p111">'Send incident reports in email' — check this box. Click 'Choose what to include in the report and who receives it.' Be sure to add your compliance team.</span></span></p>
<p><span data-ttu-id="2fe9c-184">[限制誰可以存取的內容並覆寫原則] — 清除此核取方塊，以接收關於敏感資訊的通知，不阻止使用者存取該資訊。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-184">'Restrict who can access the content and override the policy' — clear this checkbox to receive notifications about sensitive information without preventing users from access that information.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2fe9c-185">所有位置包括</span><span class="sxs-lookup"><span data-stu-id="2fe9c-185">All locations includes:</span></span>

- <span data-ttu-id="2fe9c-186">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2fe9c-186">SharePoint Online</span></span>

- <span data-ttu-id="2fe9c-187">OneDrive for商務用帳戶</span><span class="sxs-lookup"><span data-stu-id="2fe9c-187">OneDrive for Business accounts</span></span>

- <span data-ttu-id="2fe9c-188">Exchange 信箱</span><span class="sxs-lookup"><span data-stu-id="2fe9c-188">Exchange mailboxes</span></span>

<span data-ttu-id="2fe9c-189">由於內容搜尋目前無法讓您利用電子郵件測試敏感資訊類型，請考慮為 Exchange 建立個別原則 (每一個原則中都有敏感資訊類型的子集)，以及監視這些原則的推出。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-189">Because Content Search doesn't currently let you test sensitive information types with email, consider creating separate policies for Exchange with a subset of sensitive information types in each policy and monitoring the rollout of these policies.</span></span>

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-microsoft-365"></a><span data-ttu-id="2fe9c-190">您可套用以對 Microsoft 365 中的個人資料進行保護的額外保護</span><span class="sxs-lookup"><span data-stu-id="2fe9c-190">Additional protection you can apply to protect personal data in Microsoft 365</span></span>

<span data-ttu-id="2fe9c-p112">敏感資訊類型、標籤和資料外洩防護原則可協助您識別包含特定資料的文件，並套用保護。不過，這些保護視將針對資料存取而設定的權限、具有未受連累之帳戶的使用者，以及狀況良好的裝置而定。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p112">Sensitive information types, labels, and data loss protection policies help you identify documents containing specific data and apply protection. However, these protections depend on appropriate permissions being set for access to data, users with accounts that aren't compromised, and devices that are healthy.</span></span>

<span data-ttu-id="2fe9c-193">下圖詳述您可以套用以保護個人資料存取的額外保護。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-193">The following illustration details additional protection you can apply to protect access to personal data.</span></span>

![保護個人資料存取的額外保護](../media/Apply-protection-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="2fe9c-195">為了便於存取，下表會在圖例中提供相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-195">For accessibility, the following table provides the same information in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fe9c-196"><strong>保護範圍</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-196"><strong>Scope of protection</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-197"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-197"><strong>Capabilities</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-198">文件和電子郵件層級保護 (包括傳輸中郵件，但不包括目前在信箱中處於靜態的郵件)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-198">Document and email-level protection (includes mail in transit, but not currently mailboxes at rest)</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-199">敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="2fe9c-199">Sensitive information types</span></span></p>
<p><span data-ttu-id="2fe9c-200">Office 標籤</span><span class="sxs-lookup"><span data-stu-id="2fe9c-200">Office labels</span></span></p>
<p><span data-ttu-id="2fe9c-201">資料外洩防護原則</span><span class="sxs-lookup"><span data-stu-id="2fe9c-201">Data loss prevention policies</span></span></p>
<p><span data-ttu-id="2fe9c-202">電子郵件的 Microsoft 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="2fe9c-202">Microsoft 365 Message Encryption for email</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-203">網站和文件庫層級保護 (包括 SharePoint 和 OneDrive 網站)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-203">Site and library-level protection (includes SharePoint Online and OneDrive for Business sites)</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-204">SharePoint Online 和商務用 OneDrive 網站與文件庫的權限</span><span class="sxs-lookup"><span data-stu-id="2fe9c-204">Permissions for SharePoint Online and OneDrive for Business sites and libraries</span></span></p>
<p><span data-ttu-id="2fe9c-205">SharePoint Online 和商務用 OneDrive 的外部共用原則 (網站層級)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-205">External sharing policies for SharePoint Online and OneDrive for Business (site-level)</span></span></p>
<p><span data-ttu-id="2fe9c-206">網站層級裝置存取控制</span><span class="sxs-lookup"><span data-stu-id="2fe9c-206">Site-level device access policies</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-207">服務存取保護 (包括 Microsoft 365 中所有服務的存取)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-207">Service access protection (includes access to all services in Microsoft 365)</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-208">企業行動力 + 安全性 (EMS) 套件的身分識別與裝置存取保護</span><span class="sxs-lookup"><span data-stu-id="2fe9c-208">Identity and device access protection in Enterprise Mobility + Security (EMS) suite</span></span></p>
<p><span data-ttu-id="2fe9c-209">特許存取管理</span><span class="sxs-lookup"><span data-stu-id="2fe9c-209">Privileged access management</span></span></p>
<p><span data-ttu-id="2fe9c-210">Windows 10 安全性功能</span><span class="sxs-lookup"><span data-stu-id="2fe9c-210">Windows 10 security capabilities</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2fe9c-211">本文的其餘部分提供其中每一種保護類別的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-211">The rest of this article provides more information on each of these categories of protection.</span></span>

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a><span data-ttu-id="2fe9c-212">可與 GDPR 搭配使用的功能</span><span class="sxs-lookup"><span data-stu-id="2fe9c-212">Capabilities that are OK to use with GDPR</span></span>

<span data-ttu-id="2fe9c-p113">您可以在針對 GDPR 規範設定的環境中使用下列功能。GDPR 規範不一定需要這些功能，但可以使用它們，不會對您探索、保護、監視及報告與 GDPR 規範相關之資料的能力產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p113">You can use the following capabilities in an environment configured for GDPR compliance. These capabilities are not necessary for GDPR compliance, but they can be used without adversely affecting your ability to discover, protect, monitor, and report on data related to GDPR compliance.</span></span>

<span data-ttu-id="2fe9c-p114">客戶金鑰 — 可讓客戶對用來在 Microsoft 365 內加密靜態資料的加密金鑰提供及保留控制權。此建議只適用於法規上需要管理其本身加密金鑰的客戶。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p114">Customer Key — Allows customers to provide and retain control over the encryption keys that are used to encrypt data at rest within Microsoft 365. Recommended only for customers with a regulatory need to manage their own encryption keys.</span></span>

<span data-ttu-id="2fe9c-p115">客戶加密箱 — 客戶加密箱可讓您控制 Microsoft 支援工程師如何存取您的資料，以在必要時根據具體情況解決技術問題。您可以控制是否要授與支援工程師存取您資料的權限。每個要求都會隨附到期時間。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p115">Customer Lockbox — Customer lockbox allows you to control how a Microsoft support engineer accesses your data, if needed, to fix a technical issue on a case by case basis. You can control whether to give the support engineer access to your data or not. An expiration time is provided with each request.</span></span>

## <a name="site-and-library-level-protection"></a><span data-ttu-id="2fe9c-220">網站和文件庫層級保護</span><span class="sxs-lookup"><span data-stu-id="2fe9c-220">Site and library-level protection</span></span>

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="2fe9c-221">SharePoint 和商務用 OneDrive 文件庫的權限</span><span class="sxs-lookup"><span data-stu-id="2fe9c-221">Permissions for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="2fe9c-p116">使用 SharePoint 中的權限，允許或限制使用者存取網站或其內容。將個別使用者或 Azure Active Directory 群組新增至預設的 SharePoint 群組。或者，建立自訂群組進行更細微的控制。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p116">Use permissions in SharePoint to provide or restrict user access to the site or its contents. Add individual users or Azure Active Directory groups to the default SharePoint groups. Or, create a custom group for finer-grain control.</span></span>

![從完全控制到僅檢視的權限層級](../media/Apply-protection-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="2fe9c-p117">此圖描繪從完全控制到僅檢視的權限等級。下表包括相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p117">The illustration plots permission levels from Full control to View Only. The following table includes the same information.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fe9c-228"><strong>完全控制</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-228"><strong>Full Control</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-229"><strong>設計</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-229"><strong>Design</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-230"><strong>編輯</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-230"><strong>Edit</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-231"><strong>參與</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-231"><strong>Contribute</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-232"><strong>讀取</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-232"><strong>Read</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-233"><strong>僅檢視</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-233"><strong>View Only</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="2fe9c-234">參與 + 核准與自訂</span><span class="sxs-lookup"><span data-stu-id="2fe9c-234">Contribute + approve and customize</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-235">參與 + 新增、編輯和刪除清單 (不只是清單項目)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-235">Contribute + add, edit, and delete lists (not just list items)</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-236">檢視、新增、更新及刪除清單項目與文件</span><span class="sxs-lookup"><span data-stu-id="2fe9c-236">View, add, update, delete list items and documents</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-237">檢視並下載</span><span class="sxs-lookup"><span data-stu-id="2fe9c-237">View and download</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-238">檢視，不下載</span><span class="sxs-lookup"><span data-stu-id="2fe9c-238">View, no download</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2fe9c-239">詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="2fe9c-239">More information:</span></span>

-   [<span data-ttu-id="2fe9c-240">瞭解 SharePoint 中的權限層級</span><span class="sxs-lookup"><span data-stu-id="2fe9c-240">Understanding permission levels in SharePoint</span></span>](https://support.office.com/en-US/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [<span data-ttu-id="2fe9c-241">了解 SharePoint 群組</span><span class="sxs-lookup"><span data-stu-id="2fe9c-241">Understanding SharePoint groups</span></span>](https://support.office.com/en-US/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="2fe9c-242">SharePoint 和商務用 OneDrive 文件庫的外部共用原則</span><span class="sxs-lookup"><span data-stu-id="2fe9c-242">External sharing policies for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="2fe9c-p118">許多組織允許外部共用以支援分工合作。了解如何設定您租用戶的整個設定。然後，檢閱包含個人資料之網站的外部共用設定。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p118">Many organizations allow external sharing to support collaboration. Find out how your tenant-wide settings are configured. Then review the external sharing settings for sites that contain personal data.</span></span>

<span data-ttu-id="2fe9c-246">外部使用者是您組織外的人員，受邀存取您的 SharePoint 網站和文件，但沒有您的 SharePoint Online 或 Microsoft 365 訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-246">An external user is someone outside of your organization who is invited to access your SharePoint Online sites and documents but doesn't have a license for your SharePoint Online or Microsoft Microsoft 365 subscription.</span></span>

<span data-ttu-id="2fe9c-247">外部共用原則同時適用於 SharePoint Online 和商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="2fe9c-247">External sharing policies apply to both SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="2fe9c-248">您必須是 SharePoint Online 管理員，才能設定共用原則。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-248">You must be a SharePoint Online admin to configure sharing policies.</span></span>

-   <span data-ttu-id="2fe9c-249">您必須是網站擁有者或具備完全控制權限，才能與外部使用者共用網站或文件。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-249">You must be a Site Owner or have full control permissions to share a site or document with external users.</span></span>

<span data-ttu-id="2fe9c-250">下表彙總您可以設定的控制權。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-250">The following table summarizes the controls you can configure.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fe9c-251"><strong>控制類別</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-251"><strong>Control category</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-252"><strong>選項</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-252"><strong>Options</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-253">共用類型</span><span class="sxs-lookup"><span data-stu-id="2fe9c-253">Type of sharing</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-254">不允許組織外共用 (可以針對個別網站集合設定)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-254">Don't allow sharing outside your organization (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="2fe9c-255">僅允許與經過驗證的外部使用者共用 (允許新的使用者或限制為現有的使用者，也可以針對個別網站集合設定)\*</span><span class="sxs-lookup"><span data-stu-id="2fe9c-255">Allow sharing to authenticated external users only (allow new or limit to existing, can be set for individual site collections)\*</span></span></p>
<p><span data-ttu-id="2fe9c-256">允許利用匿名存取連結與外部使用者共用 (也可以針對個別網站集合設定)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-256">Allow sharing to external users with an anonymous access link (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="2fe9c-257">使用網域限制外部共用 (允許和拒絕清單)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-257">Limit external sharing using domains (allow and deny list)</span></span></p>
<p><span data-ttu-id="2fe9c-258">選擇預設連結類型 (匿名、公司可共用或受限制)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-258">Choose the default link type (anonymous, company shareable, or restricted)</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-259">外部使用者可以做什麼</span><span class="sxs-lookup"><span data-stu-id="2fe9c-259">What external users can do</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-260">阻止外部使用者共用他們未擁有的檔案、資料夾、網站</span><span class="sxs-lookup"><span data-stu-id="2fe9c-260">Prevent external users from sharing files, folders, sites they don't own</span></span></p>
<p><span data-ttu-id="2fe9c-261">要求外部使用者接受具有邀請傳送至其中之相同帳戶的共用邀請</span><span class="sxs-lookup"><span data-stu-id="2fe9c-261">Require external users to accept sharing invitations with the same account the invitation was sent to</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-262">通知</span><span class="sxs-lookup"><span data-stu-id="2fe9c-262">Notifications</span></span></td>
<td align="left"><p><span data-ttu-id="2fe9c-p119">目前僅適用於商務用 OneDrive。下列情況時通知擁有者：</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p119">Currently only available in OneDrive for Business. Notify owners when:</span></span></p>
- <p><span data-ttu-id="2fe9c-265">使用者邀請其他外部使用者共用檔案</span><span class="sxs-lookup"><span data-stu-id="2fe9c-265">Users invite additional external users to shared files</span></span></p>
- <p><span data-ttu-id="2fe9c-266">外部使用者接受存取檔案的邀請</span><span class="sxs-lookup"><span data-stu-id="2fe9c-266">External users accept invitations to access files</span></span></p>
- <p><span data-ttu-id="2fe9c-267">已建立或變更匿名存取連結</span><span class="sxs-lookup"><span data-stu-id="2fe9c-267">An anonymous access link is created or changed</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2fe9c-268">詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="2fe9c-268">More information:</span></span>

-   [<span data-ttu-id="2fe9c-269">管理您的 SharePoint Online 環境外部共用</span><span class="sxs-lookup"><span data-stu-id="2fe9c-269">Manage external sharing for your SharePoint Online environment</span></span>](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)

-   [<span data-ttu-id="2fe9c-270">與您組織外的人員共用網站或文件</span><span class="sxs-lookup"><span data-stu-id="2fe9c-270">Share sites or documents with people outside your organization</span></span>](https://support.office.com/en-US/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a><span data-ttu-id="2fe9c-271">網站層級裝置存取控制</span><span class="sxs-lookup"><span data-stu-id="2fe9c-271">Site-level device access policies</span></span>

<span data-ttu-id="2fe9c-p120">SharePoint Online 和商務用 OneDrive 可讓您在網站層級設定裝置存取原則。這可讓您針對具有敏感資料的網站設定更多的保護。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p120">SharePoint Online and OneDrive for Business let you configure device access policies at the site level. This lets you configure more protection for sites with sensitive data.</span></span>

<span data-ttu-id="2fe9c-274">如果您設定網站層級的裝置存取原則，請務必利用下列原則協調這些原則：租用戶層級原則，以及在 Azure Active Directory、Intune 和 Intune App Management 中設定的原則。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-274">If you configure site-level device access policies, be sure to coordinate these with tenant-level policies and also with access policies that are configured in Azure Active Directory, Intune, and Intune App Management.</span></span>

<span data-ttu-id="2fe9c-p121">SharePoint 和商務用 OneDrive 的裝置存取原則需要 Azure Active Directory 和 Microsoft Intune 中的支援原則，視視您正要實作的情節而定。下表彙總您可以使用裝置存取原則來達成的目標，並指出哪些產品需要支援原則。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p121">Device access policies for SharePoint and OneDrive for Business require supporting policies in Azure Active Directory and Microsoft Intune depending on the scenario you're implementing. The following table summarizes objectives you can achieve with device access policies and indicates which products require supporting policies.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="2fe9c-277">只允許從特定 IP 位址位置存取</span><span class="sxs-lookup"><span data-stu-id="2fe9c-277">Only allow access from specific IP address locations</span></span></th>
<th align="left"><span data-ttu-id="2fe9c-278">阻止使用者將檔案下載至非網域聯結的裝置</span><span class="sxs-lookup"><span data-stu-id="2fe9c-278">Prevent users from downloading files to non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="2fe9c-279">封鎖對非網域聯結之裝置的存取</span><span class="sxs-lookup"><span data-stu-id="2fe9c-279">Block access on non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="2fe9c-280">阻止使用者將檔案下載至不相容的裝置</span><span class="sxs-lookup"><span data-stu-id="2fe9c-280">Prevent users from downloading files to non-compliant devices</span></span></th>
<th align="left"><span data-ttu-id="2fe9c-281">封鎖對不相容裝置的存取</span><span class="sxs-lookup"><span data-stu-id="2fe9c-281">Block access on non-compliant devices</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-282">SharePoint 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="2fe9c-282">SharePoint admin center</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-283">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-283">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-284">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-284">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-285">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-285">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-286">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-286">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-287">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-287">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-288">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2fe9c-288">Azure Active Directory</span></span></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="2fe9c-289">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-289">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-290">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-290">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-291">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-291">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-292">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-292">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-293">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2fe9c-293">Microsoft Intune</span></span></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="2fe9c-294">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-294">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-295">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-295">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2fe9c-296">詳細資訊：[SharePoint Online 管理中心：控制從未受管理裝置的存取](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-296">More information: [SharePoint Online admin center: Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="service-access-protection-for-identities-and-devices"></a><span data-ttu-id="2fe9c-297">身分識別與裝置的服務存取保護</span><span class="sxs-lookup"><span data-stu-id="2fe9c-297">Service access protection for identities and devices</span></span>

<span data-ttu-id="2fe9c-p122">Microsoft 建議您針對存取服務的身分識別與裝置設定保護。您用於保護 Microsoft 365 服務存取的工作也可用來保護其他 SaaS 服務、PaaS 服務，甚至是其他雲端提供者中應用程式的存取。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p122">Microsoft recommends you configure protection for identities and devices that access the service. The work you put into protecting access to Microsoft 365 services can also be used to protect access to other SaaS services, PaaS services, and even apps in other cloud providers.</span></span>

<span data-ttu-id="2fe9c-300">身分識別與裝置的存取保護提供保護的底線，以確保身分識別不會受到連累、裝置安全無虞，且裝置上存取的組織資料遭到隔離並受到保護。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-300">Access protection for identities and devices provides a baseline of protection to ensure that identities aren't compromised, devices are safe, and organization data that is accessed on devices is isolated and protected.</span></span>

<span data-ttu-id="2fe9c-301">如需起點建議與指引，請參閱[適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-301">For starting point recommendations and configuration guidance, see [Microsoft security guidance for political campaigns, nonprofits, and other agile organizations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="2fe9c-302">如需搭配 AD FS 的混合式身分識別環境，請參閱[建議的安全性原則和設定](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-302">For hybrid identity environments with AD FS, see [Recommended security policies and configurations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="2fe9c-p123">下圖描述雲端服務 (SaaS、PaaS)、帳戶類型 (租用戶網域帳戶與 B2B 帳戶)，以及服務存取功能如何相關。請務必注意可與 B2B 帳戶搭配使用的功能。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p123">The following illustration describes how cloud services (SaaS, PaaS), account types (tenant domain accounts vs. B2B accounts), and service access capabilities relate. It's important to note which capabilities can be used with B2B accounts.</span></span>

![雲端服務、帳戶類型和存取功能](../media/Apply-protection-to-personal-data-in-Office-365-image4.png)

<span data-ttu-id="2fe9c-306">為了便於存取，本節的其餘部分描述此圖。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-306">For accessibility, the rest of this section describes this illustration.</span></span>

### <a name="cloud-services"></a><span data-ttu-id="2fe9c-307">雲端服務</span><span class="sxs-lookup"><span data-stu-id="2fe9c-307">Cloud services</span></span>

<span data-ttu-id="2fe9c-p124">Azure Active Directory 可讓您的身分識別存取任何雲端服務，包括非 Microsoft 提供者，例如 Amazon Web 服務。此圖顯示 Microsoft 365、「其他 SaaS 應用程式」和「PaaS 應用程式」。箭號從 Azure Active Directory 指向其中每一個服務，這顯示 Azure Active Directory 可用於所有這類應用程式類型的驗證。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p124">Azure Active Directory provides identity access to any cloud service, including non-Microsoft providers such as Amazon Web Services. The illustration shows Microsoft 365, "Other SaaS app," and "PaaS app." Arrows point from Azure Active Directory to each of these services, showing that Azure Active Directory can be used for authentication to all of these app types.</span></span>

### <a name="types-of-accounts"></a><span data-ttu-id="2fe9c-311">帳戶類型</span><span class="sxs-lookup"><span data-stu-id="2fe9c-311">Types of accounts</span></span>

<span data-ttu-id="2fe9c-p125">租用戶網域帳戶是您新增至租用戶並直接管理的帳戶。B2B 帳戶是組織外受邀與您合作之使用者的帳戶。這些可以是其他 Microsoft 365 帳戶、其他組織帳戶或消費者帳戶 (例如 Gmail)。此圖顯示 Azure Active Directory 內的兩種帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p125">Tenant domain accounts are account you add to your tenant and manage directly. B2B accounts are accounts for users outside your organization you invite to collaborate with. These can be other Microsoft 365 accounts, other organization accounts, or consumer accounts (such as Gmail). The illustration shows both account types within Azure Active Directory.</span></span>

### <a name="capabilities"></a><span data-ttu-id="2fe9c-316">功能</span><span class="sxs-lookup"><span data-stu-id="2fe9c-316">Capabilities</span></span>

<span data-ttu-id="2fe9c-p126">下表中的功能可保護身分識別與裝置。該表指出也可以與 B2B 帳戶搭配使用的功能，與此圖類似。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-p126">The capabilities in the following table protect identities and devices. The table indicates which capabilities can also be used with B2B accounts, similar to the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fe9c-319"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-319"><strong>Capability</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-320"><strong>使用租用戶網域帳戶</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-320"><strong>Works with tenant domain accounts</strong></span></span></th>
<th align="left"><span data-ttu-id="2fe9c-321"><strong>使用 Azure B2B 帳戶 (不需額外授權)</strong></span><span class="sxs-lookup"><span data-stu-id="2fe9c-321"><strong>Works with Azure B2B accounts (without additional licensing)</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-322">多重要素驗證和條件式存取</span><span class="sxs-lookup"><span data-stu-id="2fe9c-322">Multi-factor authentication and conditional access</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-323">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-323">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-324">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-324">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-325">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="2fe9c-325">Azure AD Identity Protection</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-326">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-326">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-327">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-327">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-328">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="2fe9c-328">Azure AD Privileged Identity Management</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-329">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-329">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-330">Mobile Application Management (MAM)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-330">Mobile Application Management (MAM)</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-331">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-331">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2fe9c-332">裝置註冊和管理</span><span class="sxs-lookup"><span data-stu-id="2fe9c-332">Device enrollment and management</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-333">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-333">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-334">只有一個組織可以管理裝置</span><span class="sxs-lookup"><span data-stu-id="2fe9c-334">Only one organization can manage a device</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2fe9c-335">Windows 10 安全性功能 (根據裝置相容性的條件式存需要裝置管理)</span><span class="sxs-lookup"><span data-stu-id="2fe9c-335">Windows 10 security capabilities (conditional access based on device compliance requires device management)</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-336">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-336">Yes</span></span></td>
<td align="left"><span data-ttu-id="2fe9c-337">是</span><span class="sxs-lookup"><span data-stu-id="2fe9c-337">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2fe9c-338">您可以將授權新增至 B2B 帳戶，提供這些使用者額外的功能，以在需要時保護您環境中的個人資料存取。</span><span class="sxs-lookup"><span data-stu-id="2fe9c-338">You can add licenses to B2B accounts to give these users additional capabilities, if needed, to protect access to personal data in your environment.</span></span>
