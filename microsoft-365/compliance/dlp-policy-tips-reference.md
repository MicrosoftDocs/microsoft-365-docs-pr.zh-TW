---
title: 資料外洩防護原則提示參考資料
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: 瞭解如何將原則提示新增至資料遺失防護 (DLP) 原則通知使用者他們使用與 DLP 原則衝突的內容。
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 36e4d4f96146b51e0b31731c9e93222eed767045
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903799"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="87de0-103">資料外洩防護原則提示參考資料</span><span class="sxs-lookup"><span data-stu-id="87de0-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="87de0-104">在下列情況下，Outlook Web Access 中的 DLP 原則秘訣可用於 DLP 原則中適用于 Exchange 工作負載的所有條件、例外狀況和動作：</span><span class="sxs-lookup"><span data-stu-id="87de0-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="87de0-105">**條件：**</span><span class="sxs-lookup"><span data-stu-id="87de0-105">**Conditions:**</span></span>

- <span data-ttu-id="87de0-106">寄件者是</span><span class="sxs-lookup"><span data-stu-id="87de0-106">Sender Is</span></span>
- <span data-ttu-id="87de0-107">Sender Domain 是</span><span class="sxs-lookup"><span data-stu-id="87de0-107">Sender Domain Is</span></span>
- <span data-ttu-id="87de0-108">收件者是的成員</span><span class="sxs-lookup"><span data-stu-id="87de0-108">Recipient is a member of</span></span>
- <span data-ttu-id="87de0-109">標頭包含字或片語</span><span class="sxs-lookup"><span data-stu-id="87de0-109">Header contains words or phrases</span></span>
- <span data-ttu-id="87de0-110">標頭符合模式</span><span class="sxs-lookup"><span data-stu-id="87de0-110">Header matches patterns</span></span>
- <span data-ttu-id="87de0-111">檔案大小等於或大於</span><span class="sxs-lookup"><span data-stu-id="87de0-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="87de0-112">郵件類型為</span><span class="sxs-lookup"><span data-stu-id="87de0-112">Message type is</span></span>
- <span data-ttu-id="87de0-113">郵件重要性為</span><span class="sxs-lookup"><span data-stu-id="87de0-113">Message importance is</span></span>
- <span data-ttu-id="87de0-114">內容字元集包含文字</span><span class="sxs-lookup"><span data-stu-id="87de0-114">Content character set contains words</span></span>
- <span data-ttu-id="87de0-115">主旨或內文包含文字或片語</span><span class="sxs-lookup"><span data-stu-id="87de0-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="87de0-116">主旨或內文符合模式</span><span class="sxs-lookup"><span data-stu-id="87de0-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="87de0-117">內容字元集包含文字</span><span class="sxs-lookup"><span data-stu-id="87de0-117">Content character set contains words</span></span>
- <span data-ttu-id="87de0-118">內容接收來源</span><span class="sxs-lookup"><span data-stu-id="87de0-118">Content is received from</span></span>
- <span data-ttu-id="87de0-119">寄件者覆寫原則提示</span><span class="sxs-lookup"><span data-stu-id="87de0-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="87de0-120">郵件大小等於或大於</span><span class="sxs-lookup"><span data-stu-id="87de0-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="87de0-121">Sender AD 屬性包含字詞或片語</span><span class="sxs-lookup"><span data-stu-id="87de0-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="87de0-122">寄件者 AD 屬性符合模式</span><span class="sxs-lookup"><span data-stu-id="87de0-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="87de0-123">檔內容包含文字或片語</span><span class="sxs-lookup"><span data-stu-id="87de0-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="87de0-124">檔內容符合模式</span><span class="sxs-lookup"><span data-stu-id="87de0-124">Document content matches patterns</span></span>

<span data-ttu-id="87de0-125">**行動：**</span><span class="sxs-lookup"><span data-stu-id="87de0-125">**Actions:**</span></span>

- <span data-ttu-id="87de0-126">轉寄郵件以核准給寄件者的管理員</span><span class="sxs-lookup"><span data-stu-id="87de0-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="87de0-127">將郵件轉寄給特定核准者</span><span class="sxs-lookup"><span data-stu-id="87de0-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="87de0-128">將郵件重新導向至特定使用者</span><span class="sxs-lookup"><span data-stu-id="87de0-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="87de0-129">將收件者新增至 [收件者] 方塊</span><span class="sxs-lookup"><span data-stu-id="87de0-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="87de0-130">將收件者新增至 [抄送] 方塊</span><span class="sxs-lookup"><span data-stu-id="87de0-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="87de0-131">將收件者新增至 [密件副本] 方塊</span><span class="sxs-lookup"><span data-stu-id="87de0-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="87de0-132">將寄件者的管理員新增為收件者</span><span class="sxs-lookup"><span data-stu-id="87de0-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="87de0-133">新增 HTML 免責聲明</span><span class="sxs-lookup"><span data-stu-id="87de0-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="87de0-134">前置電子郵件主題</span><span class="sxs-lookup"><span data-stu-id="87de0-134">Prepend email subject</span></span>
- <span data-ttu-id="87de0-135">移除 O365 郵件加密和許可權保護</span><span class="sxs-lookup"><span data-stu-id="87de0-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="87de0-136">Outlook 2013 和更新版本支援顯示僅限某些條件和例外的原則提示</span><span class="sxs-lookup"><span data-stu-id="87de0-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="87de0-137">目前，Outlook 2013 和更新版本支援顯示原則提示的原則，但不含下列所述條件和對應例外狀況之外的任何條件或例外狀況：</span><span class="sxs-lookup"><span data-stu-id="87de0-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="87de0-138">內容包含的 (只適用于機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="87de0-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="87de0-139">不支援敏感度標籤) </span><span class="sxs-lookup"><span data-stu-id="87de0-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="87de0-140">內容已共用</span><span class="sxs-lookup"><span data-stu-id="87de0-140">Content is shared</span></span>

<span data-ttu-id="87de0-141">請注意，所有條件都適用于在 Outlook 用戶端應用程式中撰寫的電子郵件，其將會符合內容，並強制執行內容的保護動作。</span><span class="sxs-lookup"><span data-stu-id="87de0-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="87de0-142">不過，對於除了上述所述以外的任何情況，都不支援對使用者顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="87de0-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="87de0-143">Outlook 2013 和更新版本，以及在桌面機上的 Office 應用程式支援只顯示某些敏感資訊類型的原則秘訣</span><span class="sxs-lookup"><span data-stu-id="87de0-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="87de0-144">在桌面 (2013 和更新版本的 Outlook 中，會偵測到顯示 DLP 原則提示的預置資訊類型清單。) 和 Office app (Word、Excel、PowerPoint) 在桌面上，如下所示：</span><span class="sxs-lookup"><span data-stu-id="87de0-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="87de0-145">ABA 路由號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-145">ABA Routing Number</span></span>
- <span data-ttu-id="87de0-146">阿根廷國家身分識別 (DNI) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="87de0-147">澳大利亞銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="87de0-148">澳大利亞醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="87de0-149">澳大利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-149">Australia Passport Number</span></span>
- <span data-ttu-id="87de0-150">澳大利亞稅收檔編號</span><span class="sxs-lookup"><span data-stu-id="87de0-150">Australia Tax File Number</span></span>
- <span data-ttu-id="87de0-151">Azure DocumentDB 驗證金鑰</span><span class="sxs-lookup"><span data-stu-id="87de0-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="87de0-152">Azure IAAS 資料庫連接字串和 Azure SQL 連接字串</span><span class="sxs-lookup"><span data-stu-id="87de0-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="87de0-153">Azure IoT 連接字串</span><span class="sxs-lookup"><span data-stu-id="87de0-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="87de0-154">Azure 發佈設定密碼</span><span class="sxs-lookup"><span data-stu-id="87de0-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="87de0-155">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="87de0-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="87de0-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="87de0-156">Azure SAS</span></span>  
- <span data-ttu-id="87de0-157">Azure 服務匯流排連接字串</span><span class="sxs-lookup"><span data-stu-id="87de0-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="87de0-158">Azure 儲存體帳戶金鑰</span><span class="sxs-lookup"><span data-stu-id="87de0-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="87de0-159">Azure 儲存體帳戶金鑰 (泛型) </span><span class="sxs-lookup"><span data-stu-id="87de0-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="87de0-160">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="87de0-160">Belgium National Number</span></span>
- <span data-ttu-id="87de0-161">巴西 CPF 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-161">Brazil CPF Number</span></span>
- <span data-ttu-id="87de0-162">巴西法人編號 (CNPJ) </span><span class="sxs-lookup"><span data-stu-id="87de0-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="87de0-163">巴西全國身分識別卡 (RG) </span><span class="sxs-lookup"><span data-stu-id="87de0-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="87de0-164">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="87de0-165">加拿大駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="87de0-166">加拿大健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-166">Canada Health Service Number</span></span>
- <span data-ttu-id="87de0-167">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-167">Canada Passport Number</span></span>
- <span data-ttu-id="87de0-168">加拿大個人健康身分識別號碼 (PHIN) </span><span class="sxs-lookup"><span data-stu-id="87de0-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="87de0-169">加拿大社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="87de0-170">智利身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="87de0-171">中國居民身分識別卡 (中國) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="87de0-172">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-172">Credit Card Number</span></span>
- <span data-ttu-id="87de0-173">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="87de0-174">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="87de0-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="87de0-175">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="87de0-176">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="87de0-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="87de0-177">藥物執行代理商 (DEA) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="87de0-178">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-178">EU Debit Card Number</span></span>
- <span data-ttu-id="87de0-179">歐盟駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="87de0-180">歐盟國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-180">EU National Identification Number</span></span>  
- <span data-ttu-id="87de0-181">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-181">EU Passport Number</span></span>  
- <span data-ttu-id="87de0-182"> (SSN) 或同等識別碼的歐盟社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="87de0-183">歐盟)  (TIN 的納稅識別號</span><span class="sxs-lookup"><span data-stu-id="87de0-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="87de0-184">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="87de0-184">Finland National ID</span></span>
- <span data-ttu-id="87de0-185">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-185">Finland Passport Number</span></span>
- <span data-ttu-id="87de0-186">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-186">France Driver's License Number</span></span>
- <span data-ttu-id="87de0-187">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="87de0-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="87de0-188">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-188">France Passport Number</span></span>
- <span data-ttu-id="87de0-189">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="87de0-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="87de0-190">德國駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-190">German Driver's License Number</span></span>
- <span data-ttu-id="87de0-191">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-191">German Passport Number</span></span>
- <span data-ttu-id="87de0-192">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="87de0-193">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="87de0-193">Greece National ID Card</span></span>  
- <span data-ttu-id="87de0-194">香港身分識別卡 (HKID) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="87de0-195"> (平移) 的印度永久帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="87de0-196">印度唯一識別碼 (Aadhaar) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="87de0-197">印尼身分識別卡 (KTP) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="87de0-198">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="87de0-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="87de0-199">國際分類的疾病 (ICD-10-釐米) </span><span class="sxs-lookup"><span data-stu-id="87de0-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="87de0-200">疾病 (ICD-9 釐米) 的國際分類</span><span class="sxs-lookup"><span data-stu-id="87de0-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="87de0-201">IP 位址</span><span class="sxs-lookup"><span data-stu-id="87de0-201">IP Address</span></span>
- <span data-ttu-id="87de0-202">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="87de0-203">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="87de0-204">以色列國家識別碼</span><span class="sxs-lookup"><span data-stu-id="87de0-204">Israel National ID</span></span>
- <span data-ttu-id="87de0-205">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="87de0-206">日本銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="87de0-207">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="87de0-208">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-208">Japan Passport Number</span></span>
- <span data-ttu-id="87de0-209">日本居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="87de0-210">日本社交保險號碼 (SIN) </span><span class="sxs-lookup"><span data-stu-id="87de0-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="87de0-211">日本住家電話卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="87de0-212">馬來西亞身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="87de0-213">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="87de0-214">紐西蘭健康情況號碼的部</span><span class="sxs-lookup"><span data-stu-id="87de0-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="87de0-215">挪威身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-215">Norway Identity Number</span></span>  
- <span data-ttu-id="87de0-216">菲律賓統一多用途識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="87de0-217">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="87de0-217">Poland Identity Card</span></span>
- <span data-ttu-id="87de0-218">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="87de0-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="87de0-219">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="87de0-219">Poland Passport</span></span>
- <span data-ttu-id="87de0-220">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="87de0-221">沙烏地阿拉伯國際身分識別</span><span class="sxs-lookup"><span data-stu-id="87de0-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="87de0-222">新加坡國家註冊身分識別卡 (NRIC) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="87de0-223">南非識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="87de0-224">韓國居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="87de0-225">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="87de0-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="87de0-226">SQL Server 連接字串</span><span class="sxs-lookup"><span data-stu-id="87de0-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="87de0-227">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="87de0-227">Sweden National ID</span></span>
- <span data-ttu-id="87de0-228">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-228">Sweden Passport Number</span></span>
- <span data-ttu-id="87de0-229">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="87de0-229">SWIFT Code</span></span>
- <span data-ttu-id="87de0-230">臺灣國家 ID</span><span class="sxs-lookup"><span data-stu-id="87de0-230">Taiwan National ID</span></span>
- <span data-ttu-id="87de0-231">臺灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="87de0-232">臺灣居民憑證 (ARC/TARC) </span><span class="sxs-lookup"><span data-stu-id="87de0-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="87de0-233">泰國人口識別碼</span><span class="sxs-lookup"><span data-stu-id="87de0-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="87de0-234">土耳其國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-234">Turkish National Identification number</span></span>
- <span data-ttu-id="87de0-p103">英國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="87de0-p104">英國選民名冊編號</span><span class="sxs-lookup"><span data-stu-id="87de0-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="87de0-p105">英國國民健保服務號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="87de0-p106">英國國民保險號碼 (NINO)</span><span class="sxs-lookup"><span data-stu-id="87de0-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="87de0-243">美國/英國</span><span class="sxs-lookup"><span data-stu-id="87de0-243">U.S. / U.K.</span></span> <span data-ttu-id="87de0-244">護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-244">Passport Number</span></span>
- <span data-ttu-id="87de0-245">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="87de0-246">美國駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="87de0-247">ITIN) 的美國個別納稅人識別號碼 (</span><span class="sxs-lookup"><span data-stu-id="87de0-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="87de0-248"> (SSN) 的 U.S. 社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="87de0-249">請注意，除了上述現成的敏感資訊類型之外，還支援 DLP 原則提示的自訂敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="87de0-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="87de0-250">端點裝置上的資料遺失防護只支援某些敏感資訊類型的原則秘訣</span><span class="sxs-lookup"><span data-stu-id="87de0-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="87de0-251">在位於端點裝置上的檔中，會偵測到的現成敏感資訊類型清單如下：</span><span class="sxs-lookup"><span data-stu-id="87de0-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="87de0-252">ABA 路由號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-252">ABA Routing Number</span></span> 
- <span data-ttu-id="87de0-253">阿根廷國家身分識別 (DNI) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="87de0-254">澳大利亞銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="87de0-255">澳大利亞醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="87de0-256">澳大利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-256">Australia Passport Number</span></span> 
- <span data-ttu-id="87de0-257">澳大利亞稅收檔編號</span><span class="sxs-lookup"><span data-stu-id="87de0-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="87de0-258">澳大利亞商務電話號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-258">Australian Business Number</span></span> 
- <span data-ttu-id="87de0-259">澳大利亞公司號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-259">Australian Company Number</span></span> 
- <span data-ttu-id="87de0-260">奧地利駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="87de0-261">奧地利身分識別卡</span><span class="sxs-lookup"><span data-stu-id="87de0-261">Austria Identity Card</span></span> 
- <span data-ttu-id="87de0-262">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-262">Austria Passport Number</span></span> 
- <span data-ttu-id="87de0-263">奧地利的社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="87de0-264">奧地利納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="87de0-265">奧地利增值 (加值稅) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="87de0-266">Azure DocumentDB 驗證金鑰</span><span class="sxs-lookup"><span data-stu-id="87de0-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="87de0-267">Azure IAAS 資料庫連接字串和 Azure SQL 連接字串</span><span class="sxs-lookup"><span data-stu-id="87de0-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="87de0-268">Azure IoT 連接字串</span><span class="sxs-lookup"><span data-stu-id="87de0-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="87de0-269">Azure 發佈設定密碼</span><span class="sxs-lookup"><span data-stu-id="87de0-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="87de0-270">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="87de0-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="87de0-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="87de0-271">Azure SAS</span></span> 
- <span data-ttu-id="87de0-272">Azure 服務匯流排連接字串</span><span class="sxs-lookup"><span data-stu-id="87de0-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="87de0-273">Azure 儲存體帳戶金鑰</span><span class="sxs-lookup"><span data-stu-id="87de0-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="87de0-274">Azure 儲存體帳戶金鑰 (泛型) </span><span class="sxs-lookup"><span data-stu-id="87de0-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="87de0-275">比利時駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="87de0-276">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="87de0-276">Belgium National Number</span></span> 
- <span data-ttu-id="87de0-277">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="87de0-278">比利時增值的納稅號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="87de0-279">巴西 CPF 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="87de0-280">巴西法人編號 (CNPJ) </span><span class="sxs-lookup"><span data-stu-id="87de0-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="87de0-281">巴西全國身分識別卡 (RG) </span><span class="sxs-lookup"><span data-stu-id="87de0-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="87de0-282">保加利亞駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="87de0-283">保加利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="87de0-284">保加利亞統一的民事編號</span><span class="sxs-lookup"><span data-stu-id="87de0-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="87de0-285">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="87de0-286">加拿大駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="87de0-287">加拿大健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="87de0-288">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-288">Canada Passport Number</span></span> 
- <span data-ttu-id="87de0-289">加拿大個人健康身分識別號碼 (PHIN) </span><span class="sxs-lookup"><span data-stu-id="87de0-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="87de0-290">加拿大社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="87de0-291">智利身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="87de0-292">中國居民身分識別卡 (中國) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="87de0-293">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-293">Credit Card Number</span></span> 
- <span data-ttu-id="87de0-294">克羅地亞駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="87de0-295">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="87de0-296">克羅地亞國際身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="87de0-297">克羅地亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="87de0-298">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="87de0-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="87de0-299">CSCAN-AZURE0060 Azure 儲存體帳戶共用存取簽名</span><span class="sxs-lookup"><span data-stu-id="87de0-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="87de0-300">CSCAN-GENERAL0140 一般對稱金鑰</span><span class="sxs-lookup"><span data-stu-id="87de0-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="87de0-301">賽普勒斯駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="87de0-302">賽普勒斯身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="87de0-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="87de0-303">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="87de0-304">賽普勒斯納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="87de0-305">捷克文駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="87de0-306">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="87de0-307">捷克共和國護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="87de0-308">丹麥駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="87de0-309">丹麥護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="87de0-310">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="87de0-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="87de0-311">藥物執行代理商 (DEA) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="87de0-312">愛沙尼亞駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="87de0-313">愛沙尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="87de0-314">愛沙尼亞個人識別碼</span><span class="sxs-lookup"><span data-stu-id="87de0-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="87de0-315">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="87de0-316">歐盟駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="87de0-317">歐盟國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-317">EU National Identification Number</span></span> 
- <span data-ttu-id="87de0-318">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-318">EU Passport Number</span></span> 
- <span data-ttu-id="87de0-319"> (SSN) 或同等識別碼的歐盟社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="87de0-320">歐盟)  (TIN 的納稅識別號</span><span class="sxs-lookup"><span data-stu-id="87de0-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="87de0-321">芬蘭駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="87de0-322">芬蘭歐洲健康情況保險業號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="87de0-323">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="87de0-323">Finland National ID</span></span> 
- <span data-ttu-id="87de0-324">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-324">Finland Passport Number</span></span> 
- <span data-ttu-id="87de0-325">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-325">France Driver's License Number</span></span> 
- <span data-ttu-id="87de0-326">法國健康保險業號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="87de0-327">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="87de0-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="87de0-328">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-328">France Passport Number</span></span> 
- <span data-ttu-id="87de0-329">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="87de0-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="87de0-330">法國納稅識別號碼 (numéro SPI。 ) </span><span class="sxs-lookup"><span data-stu-id="87de0-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="87de0-331">法國加值稅收號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="87de0-332">德國駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-332">German Driver's License Number</span></span> 
- <span data-ttu-id="87de0-333">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-333">German Passport Number</span></span> 
- <span data-ttu-id="87de0-334">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="87de0-335">德國納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="87de0-336">德國加值稅號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="87de0-337">希臘駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="87de0-338">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="87de0-338">Greece National ID Card</span></span> 
- <span data-ttu-id="87de0-339">希臘護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-339">Greece Passport Number</span></span> 
- <span data-ttu-id="87de0-340"> (AMKA) 的希臘社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="87de0-341">希臘所得稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="87de0-342">香港身分識別卡 (HKID) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="87de0-343">匈牙利文社會安全號碼 (TAJ) </span><span class="sxs-lookup"><span data-stu-id="87de0-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="87de0-344">匈牙利增值銷售稅編號</span><span class="sxs-lookup"><span data-stu-id="87de0-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="87de0-345">匈牙利駕照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="87de0-346">匈牙利護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="87de0-347">匈牙利個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="87de0-348">匈牙利納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="87de0-349"> (平移) 的印度永久帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="87de0-350">印度唯一識別碼 (Aadhaar) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="87de0-351">印尼身分識別卡 (KTP) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="87de0-352">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="87de0-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="87de0-353">國際分類的疾病 (ICD-10-釐米) </span><span class="sxs-lookup"><span data-stu-id="87de0-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="87de0-354">疾病 (ICD-9 釐米) 的國際分類</span><span class="sxs-lookup"><span data-stu-id="87de0-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="87de0-355">IP 位址</span><span class="sxs-lookup"><span data-stu-id="87de0-355">IP Address</span></span> 
- <span data-ttu-id="87de0-356">愛爾蘭駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="87de0-357">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="87de0-358">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="87de0-359">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="87de0-360">以色列國家識別碼</span><span class="sxs-lookup"><span data-stu-id="87de0-360">Israel National ID</span></span> 
- <span data-ttu-id="87de0-361">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="87de0-362">義大利會計代碼</span><span class="sxs-lookup"><span data-stu-id="87de0-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="87de0-363">義大利護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-363">Italy Passport Number</span></span> 
- <span data-ttu-id="87de0-364">義大利值增加的納稅號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="87de0-365">日本銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="87de0-366">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="87de0-367">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-367">Japan Passport Number</span></span> 
- <span data-ttu-id="87de0-368">日本居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="87de0-369">日本社交保險號碼 (SIN) </span><span class="sxs-lookup"><span data-stu-id="87de0-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="87de0-370">日本我的數位公司</span><span class="sxs-lookup"><span data-stu-id="87de0-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="87de0-371">日本我的數位個人</span><span class="sxs-lookup"><span data-stu-id="87de0-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="87de0-372">日本住家電話卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="87de0-373">拉脫維亞駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="87de0-374">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="87de0-375">拉脫維亞個人程式碼</span><span class="sxs-lookup"><span data-stu-id="87de0-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="87de0-376">立陶宛駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="87de0-377">立陶宛護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="87de0-378">立陶宛個人程式碼</span><span class="sxs-lookup"><span data-stu-id="87de0-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="87de0-379">Luxemburg 駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="87de0-380">Luxemburg (自然個人的國家識別號碼) </span><span class="sxs-lookup"><span data-stu-id="87de0-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="87de0-381">Luxemburg 非自然人員 (的本國識別碼) </span><span class="sxs-lookup"><span data-stu-id="87de0-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="87de0-382">Luxemburg 護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="87de0-383">馬來西亞身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="87de0-384">馬爾他駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="87de0-385">馬爾他身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="87de0-386">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-386">Malta Passport Number</span></span> 
- <span data-ttu-id="87de0-387">馬爾他納稅識別碼編號</span><span class="sxs-lookup"><span data-stu-id="87de0-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="87de0-388">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="87de0-389">荷蘭駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="87de0-390">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="87de0-391">荷蘭稅務識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="87de0-392">荷蘭增值納稅號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="87de0-393">紐西蘭銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="87de0-394">紐西蘭駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="87de0-395">紐西蘭 Inland 收入數目</span><span class="sxs-lookup"><span data-stu-id="87de0-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="87de0-396">紐西蘭健康情況號碼的部</span><span class="sxs-lookup"><span data-stu-id="87de0-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="87de0-397">紐西蘭社交 Welfare 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="87de0-398">挪威身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-398">Norway Identity Number</span></span> 
- <span data-ttu-id="87de0-399">菲律賓統一多用途識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="87de0-400">波蘭駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="87de0-401">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="87de0-401">Poland Identity Card</span></span> 
- <span data-ttu-id="87de0-402">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="87de0-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="87de0-403">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="87de0-403">Poland Passport</span></span> 
- <span data-ttu-id="87de0-404">波蘭納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="87de0-405">波蘭文 REGON 編號</span><span class="sxs-lookup"><span data-stu-id="87de0-405">Polish REGON Number</span></span> 
- <span data-ttu-id="87de0-406">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="87de0-407">葡萄牙駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="87de0-408">葡萄牙護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="87de0-409">葡萄牙納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="87de0-410">羅馬尼亞駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="87de0-411">羅馬尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-411">Romania Passport Number</span></span> 
- <span data-ttu-id="87de0-412">羅馬尼亞個人數值碼 (CNP) </span><span class="sxs-lookup"><span data-stu-id="87de0-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="87de0-413"> (國內) 的俄文護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="87de0-414"> (國際) 的俄文護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="87de0-415">沙烏地阿拉伯國際身分識別</span><span class="sxs-lookup"><span data-stu-id="87de0-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="87de0-416">新加坡國家註冊身分識別卡 (NRIC) 號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="87de0-417">斯洛伐克駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="87de0-418">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="87de0-419">斯洛伐克個人號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="87de0-420">斯洛維尼亞駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="87de0-421">斯洛維尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="87de0-422">斯洛維尼亞納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="87de0-423">斯洛維尼亞唯一主公民號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="87de0-424">南非識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="87de0-425">韓國居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="87de0-426">西班牙 DNI</span><span class="sxs-lookup"><span data-stu-id="87de0-426">Spain DNI</span></span> 
- <span data-ttu-id="87de0-427">西班牙駕照編號</span><span class="sxs-lookup"><span data-stu-id="87de0-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="87de0-428">西班牙護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-428">Spain Passport Number</span></span> 
- <span data-ttu-id="87de0-429">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="87de0-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="87de0-430">西班牙納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="87de0-431">SQL Server 連接字串</span><span class="sxs-lookup"><span data-stu-id="87de0-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="87de0-432">瑞典駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="87de0-433">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="87de0-433">Sweden National ID</span></span> 
- <span data-ttu-id="87de0-434">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="87de0-435">瑞典納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="87de0-436">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="87de0-436">SWIFT Code</span></span> 
- <span data-ttu-id="87de0-437">瑞士社會安全號碼 AHV</span><span class="sxs-lookup"><span data-stu-id="87de0-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="87de0-438">臺灣國家 ID</span><span class="sxs-lookup"><span data-stu-id="87de0-438">Taiwan National ID</span></span> 
- <span data-ttu-id="87de0-439">臺灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="87de0-440">臺灣居民憑證 (ARC/TARC) </span><span class="sxs-lookup"><span data-stu-id="87de0-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="87de0-441">泰國人口識別碼</span><span class="sxs-lookup"><span data-stu-id="87de0-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="87de0-442">土耳其國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="87de0-p108">英國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="87de0-p109">英國選民名冊編號</span><span class="sxs-lookup"><span data-stu-id="87de0-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="87de0-p110">英國國民健保服務號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="87de0-p111">英國國民保險號碼 (NINO)</span><span class="sxs-lookup"><span data-stu-id="87de0-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="87de0-451">英國。</span><span class="sxs-lookup"><span data-stu-id="87de0-451">U.K.</span></span> <span data-ttu-id="87de0-452">唯一的納稅人參考編號</span><span class="sxs-lookup"><span data-stu-id="87de0-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="87de0-453">美國/英國</span><span class="sxs-lookup"><span data-stu-id="87de0-453">U.S. / U.K.</span></span> <span data-ttu-id="87de0-454">護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-454">Passport Number</span></span> 
- <span data-ttu-id="87de0-455">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="87de0-456">美國駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="87de0-457">ITIN) 的美國個別納稅人識別號碼 (</span><span class="sxs-lookup"><span data-stu-id="87de0-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="87de0-458"> (SSN) 的 U.S. 社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="87de0-459"> (國內) 的烏克蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="87de0-460"> (國際) 的烏克蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="87de0-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="87de0-461">請注意，除了上述現成的敏感資訊類型之外，也會偵測自訂的機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="87de0-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="87de0-462">跨 Microsoft 應用程式的 DLP 原則提示的支援清單</span><span class="sxs-lookup"><span data-stu-id="87de0-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="87de0-463">**應用程式和平臺**</span><span class="sxs-lookup"><span data-stu-id="87de0-463">**App and platform**</span></span>|<span data-ttu-id="87de0-464">**DLP 原則提示支援**</span><span class="sxs-lookup"><span data-stu-id="87de0-464">**DLP policy tip support**</span></span>|<span data-ttu-id="87de0-465">**支援的敏感資訊類型**</span><span class="sxs-lookup"><span data-stu-id="87de0-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="87de0-466">**支援的謂語和動作**</span><span class="sxs-lookup"><span data-stu-id="87de0-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="87de0-467">**Comments**</span><span class="sxs-lookup"><span data-stu-id="87de0-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="87de0-468">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="87de0-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="87de0-469">全部</span><span class="sxs-lookup"><span data-stu-id="87de0-469">All</span></span>|<span data-ttu-id="87de0-470">Subset</span><span class="sxs-lookup"><span data-stu-id="87de0-470">Subset</span></span>|<span data-ttu-id="87de0-471">請參閱 [資料遺失防護原則提示參考](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="87de0-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="87de0-472">**Outlook Win32 (Outlook 2013 及以上)**</span><span class="sxs-lookup"><span data-stu-id="87de0-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="87de0-473">Subset</span><span class="sxs-lookup"><span data-stu-id="87de0-473">Subset</span></span>|<span data-ttu-id="87de0-474">Subset</span><span class="sxs-lookup"><span data-stu-id="87de0-474">Subset</span></span>|<span data-ttu-id="87de0-475">請參閱 [outlook 2013 和更新版本支援顯示僅限某些條件和例外狀況](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) 和 [outlook 2013 及更新版本的原則提示，以及桌上型電腦上的 Office 應用程式，只顯示某些敏感資訊類型的原則提示](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) ，以提供有關敏感資訊類型支援的詳細資訊，以及在 OUTLOOK Win32 上顯示 dlp 原則提示所支援的 dlp 條件和動作的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="87de0-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="87de0-476">**Outlook Mobile (iOS、Android) /Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="87de0-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="87de0-477">無</span><span class="sxs-lookup"><span data-stu-id="87de0-477">None</span></span>|<span data-ttu-id="87de0-478">無</span><span class="sxs-lookup"><span data-stu-id="87de0-478">None</span></span>|<span data-ttu-id="87de0-479">Outlook mobile 不支援 DLP 原則秘訣</span><span class="sxs-lookup"><span data-stu-id="87de0-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="87de0-480">**適用于商務網頁用戶端的 Sharepoint Online/單一磁片磁碟機**</span><span class="sxs-lookup"><span data-stu-id="87de0-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="87de0-481">全部</span><span class="sxs-lookup"><span data-stu-id="87de0-481">All</span></span>|<span data-ttu-id="87de0-482">DLP 中的所有 SPO/ODB 謂語和動作</span><span class="sxs-lookup"><span data-stu-id="87de0-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="87de0-483">**適用于 Business Win32 用戶端的 Sharepoint Win32/單一磁片磁碟機**</span><span class="sxs-lookup"><span data-stu-id="87de0-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="87de0-484">無</span><span class="sxs-lookup"><span data-stu-id="87de0-484">None</span></span>|<span data-ttu-id="87de0-485">無</span><span class="sxs-lookup"><span data-stu-id="87de0-485">None</span></span>|<span data-ttu-id="87de0-486">Sharepoint 或 OneDrive 桌面用戶端應用程式不支援 DLP 原則提示</span><span class="sxs-lookup"><span data-stu-id="87de0-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="87de0-487">**Word、Excel、PowerPoint 網頁用戶端**</span><span class="sxs-lookup"><span data-stu-id="87de0-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="87de0-488">全部</span><span class="sxs-lookup"><span data-stu-id="87de0-488">All</span></span>|<span data-ttu-id="87de0-489">DLP 中的所有 SPO/ODB 謂語和動作</span><span class="sxs-lookup"><span data-stu-id="87de0-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="87de0-490">如果檔主控于 SPO 或 ODB web app 上，且已加蓋 DLP 原則，則支援 DLP 原則提示。</span><span class="sxs-lookup"><span data-stu-id="87de0-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="87de0-491">**Word、Excel、PowerPoint 行動用戶端**</span><span class="sxs-lookup"><span data-stu-id="87de0-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="87de0-492">無</span><span class="sxs-lookup"><span data-stu-id="87de0-492">None</span></span>|<span data-ttu-id="87de0-493">無</span><span class="sxs-lookup"><span data-stu-id="87de0-493">None</span></span>|<span data-ttu-id="87de0-494">Office 行動應用程式不支援 DLP 原則秘訣。</span><span class="sxs-lookup"><span data-stu-id="87de0-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="87de0-495">**小組 Web/小組的桌面/小組行動/小組 Mac**</span><span class="sxs-lookup"><span data-stu-id="87de0-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="87de0-496">全部</span><span class="sxs-lookup"><span data-stu-id="87de0-496">All</span></span>|<span data-ttu-id="87de0-497">DLP 原則中的所有團隊謂語</span><span class="sxs-lookup"><span data-stu-id="87de0-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="87de0-498">當郵件標示為「此郵件已標記為「已標示」時，就會顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="87de0-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="87de0-499">我可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="87de0-499">What can I do?”</span></span> <span data-ttu-id="87de0-500">按一下連結時，使用者可以查看偵測到的敏感資訊類型，並在系統管理員允許的情況下，覆寫或報告問題。請注意，檔案不會顯示任何原則提示。</span><span class="sxs-lookup"><span data-stu-id="87de0-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="87de0-501">當收件者嘗試存取檔時，如果不允許存取權，他們可能會遭到拒絕存取。</span><span class="sxs-lookup"><span data-stu-id="87de0-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="87de0-502">**Win32 端點裝置**</span><span class="sxs-lookup"><span data-stu-id="87de0-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="87de0-503">Subset</span><span class="sxs-lookup"><span data-stu-id="87de0-503">Subset</span></span>|<span data-ttu-id="87de0-504">DLP 原則中的所有端點 DLP 謂詞和動作</span><span class="sxs-lookup"><span data-stu-id="87de0-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="87de0-505">[在端點上查看資料遺失防護支援僅限某些敏感資訊類型的原則秘訣](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="87de0-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="87de0-506">**Mac 裝置**</span><span class="sxs-lookup"><span data-stu-id="87de0-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="87de0-507">無</span><span class="sxs-lookup"><span data-stu-id="87de0-507">None</span></span>|<span data-ttu-id="87de0-508">無</span><span class="sxs-lookup"><span data-stu-id="87de0-508">None</span></span>|<span data-ttu-id="87de0-509">目前無法在 Mac 裝置上強制進行資料遺失防護原則</span><span class="sxs-lookup"><span data-stu-id="87de0-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="87de0-510">**協力廠商 cloud app**</span><span class="sxs-lookup"><span data-stu-id="87de0-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="87de0-511">無</span><span class="sxs-lookup"><span data-stu-id="87de0-511">None</span></span>|<span data-ttu-id="87de0-512">無</span><span class="sxs-lookup"><span data-stu-id="87de0-512">None</span></span>|<span data-ttu-id="87de0-513">協力廠商 cloud app 不支援資料遺失防護原則提示</span><span class="sxs-lookup"><span data-stu-id="87de0-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="87de0-514">**部署**</span><span class="sxs-lookup"><span data-stu-id="87de0-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="87de0-515">無</span><span class="sxs-lookup"><span data-stu-id="87de0-515">None</span></span>|<span data-ttu-id="87de0-516">無</span><span class="sxs-lookup"><span data-stu-id="87de0-516">None</span></span>||
|<span data-ttu-id="87de0-517">**Word、Excel、PowerPoint Win32 用戶端**</span><span class="sxs-lookup"><span data-stu-id="87de0-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="87de0-518">Subset</span><span class="sxs-lookup"><span data-stu-id="87de0-518">Subset</span></span>|<span data-ttu-id="87de0-519">Subset</span><span class="sxs-lookup"><span data-stu-id="87de0-519">Subset</span></span>|<span data-ttu-id="87de0-520">請參閱 [Outlook 2013 和更新版本和 Office app On Desktop 支援，顯示針對](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) 支援的敏感資訊類型清單的某些敏感資訊類型的原則秘訣。</span><span class="sxs-lookup"><span data-stu-id="87de0-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="87de0-521">WXP 用戶端應用程式的原則提示可用於儲存在 Sharepoint Online 上的檔或一個用於商務用的磁片磁碟機，以取得完全符合下列條件的所有 DLP 原則，或 DLP 原則中的其中一個條件或動作的子集：</span><span class="sxs-lookup"><span data-stu-id="87de0-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="87de0-522">內容包含機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="87de0-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="87de0-523">存取範圍 (內容是內部或外部共用) </span><span class="sxs-lookup"><span data-stu-id="87de0-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="87de0-524">通知使用者 (原則提示/使用者通知) </span><span class="sxs-lookup"><span data-stu-id="87de0-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="87de0-525">封鎖所有人</span><span class="sxs-lookup"><span data-stu-id="87de0-525">Block everyone</span></span></li><li><span data-ttu-id="87de0-526">事件報告</span><span class="sxs-lookup"><span data-stu-id="87de0-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="87de0-527">如果有任何其他條件或動作出現，該原則的 DLP 原則提示就不會出現在 Word、Excel 或 PowerPoint 的桌面應用程式中。</span><span class="sxs-lookup"><span data-stu-id="87de0-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="87de0-528">如需詳細資訊，請參閱[Excel、PowerPoint 及 Word 中的原則提示](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word)</span><span class="sxs-lookup"><span data-stu-id="87de0-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
