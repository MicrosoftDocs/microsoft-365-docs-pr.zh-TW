---
title: 資料遺失防護原則提示參考
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
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876799"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="55b37-103">資料遺失防護原則提示參考</span><span class="sxs-lookup"><span data-stu-id="55b37-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="55b37-104">在下列情況下，Outlook Web Access 中的 DLP 原則秘訣可用於 DLP 原則中適用于 Exchange 工作負載的所有條件、例外狀況和動作：</span><span class="sxs-lookup"><span data-stu-id="55b37-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="55b37-105">**條件：**</span><span class="sxs-lookup"><span data-stu-id="55b37-105">**Conditions:**</span></span>

- <span data-ttu-id="55b37-106">寄件者是</span><span class="sxs-lookup"><span data-stu-id="55b37-106">Sender Is</span></span>
- <span data-ttu-id="55b37-107">Sender Domain 是</span><span class="sxs-lookup"><span data-stu-id="55b37-107">Sender Domain Is</span></span>
- <span data-ttu-id="55b37-108">收件者是的成員</span><span class="sxs-lookup"><span data-stu-id="55b37-108">Recipient is a member of</span></span>
- <span data-ttu-id="55b37-109">標頭包含字或片語</span><span class="sxs-lookup"><span data-stu-id="55b37-109">Header contains words or phrases</span></span>
- <span data-ttu-id="55b37-110">標頭符合模式</span><span class="sxs-lookup"><span data-stu-id="55b37-110">Header matches patterns</span></span>
- <span data-ttu-id="55b37-111">檔案大小等於或大於</span><span class="sxs-lookup"><span data-stu-id="55b37-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="55b37-112">郵件類型為</span><span class="sxs-lookup"><span data-stu-id="55b37-112">Message type is</span></span>
- <span data-ttu-id="55b37-113">郵件重要性為</span><span class="sxs-lookup"><span data-stu-id="55b37-113">Message importance is</span></span>
- <span data-ttu-id="55b37-114">內容字元集包含文字</span><span class="sxs-lookup"><span data-stu-id="55b37-114">Content character set contains words</span></span>
- <span data-ttu-id="55b37-115">主旨或內文包含文字或片語</span><span class="sxs-lookup"><span data-stu-id="55b37-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="55b37-116">主旨或內文符合模式</span><span class="sxs-lookup"><span data-stu-id="55b37-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="55b37-117">內容字元集包含文字</span><span class="sxs-lookup"><span data-stu-id="55b37-117">Content character set contains words</span></span>
- <span data-ttu-id="55b37-118">內容接收來源</span><span class="sxs-lookup"><span data-stu-id="55b37-118">Content is received from</span></span>
- <span data-ttu-id="55b37-119">寄件者覆寫原則提示</span><span class="sxs-lookup"><span data-stu-id="55b37-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="55b37-120">郵件大小等於或大於</span><span class="sxs-lookup"><span data-stu-id="55b37-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="55b37-121">Sender AD 屬性包含字詞或片語</span><span class="sxs-lookup"><span data-stu-id="55b37-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="55b37-122">寄件者 AD 屬性符合模式</span><span class="sxs-lookup"><span data-stu-id="55b37-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="55b37-123">檔內容包含文字或片語</span><span class="sxs-lookup"><span data-stu-id="55b37-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="55b37-124">檔內容符合模式</span><span class="sxs-lookup"><span data-stu-id="55b37-124">Document content matches patterns</span></span>

<span data-ttu-id="55b37-125">**行動：**</span><span class="sxs-lookup"><span data-stu-id="55b37-125">**Actions:**</span></span>

- <span data-ttu-id="55b37-126">轉寄郵件以核准給寄件者的管理員</span><span class="sxs-lookup"><span data-stu-id="55b37-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="55b37-127">將郵件轉寄給特定核准者</span><span class="sxs-lookup"><span data-stu-id="55b37-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="55b37-128">將郵件重新導向至特定使用者</span><span class="sxs-lookup"><span data-stu-id="55b37-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="55b37-129">將收件者新增至 [收件者] 方塊</span><span class="sxs-lookup"><span data-stu-id="55b37-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="55b37-130">將收件者新增至 [抄送] 方塊</span><span class="sxs-lookup"><span data-stu-id="55b37-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="55b37-131">將收件者新增至 [密件副本] 方塊</span><span class="sxs-lookup"><span data-stu-id="55b37-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="55b37-132">將寄件者的管理員新增為收件者</span><span class="sxs-lookup"><span data-stu-id="55b37-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="55b37-133">新增 HTML 免責聲明</span><span class="sxs-lookup"><span data-stu-id="55b37-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="55b37-134">前置電子郵件主題</span><span class="sxs-lookup"><span data-stu-id="55b37-134">Prepend email subject</span></span>
- <span data-ttu-id="55b37-135">移除 O365 郵件加密和許可權保護</span><span class="sxs-lookup"><span data-stu-id="55b37-135">Remove O365 Message Encryption and rights protection</span></span>
- <span data-ttu-id="55b37-136">移除</span><span class="sxs-lookup"><span data-stu-id="55b37-136">Remove</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="55b37-137">Outlook 2013 和更新版本支援顯示僅限某些條件和例外的原則提示</span><span class="sxs-lookup"><span data-stu-id="55b37-137">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="55b37-138">目前，Outlook 2013 和更新版本支援顯示原則提示的原則，但不含下列所述條件和對應例外狀況之外的任何條件或例外狀況：</span><span class="sxs-lookup"><span data-stu-id="55b37-138">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="55b37-139">內容包含的 (只適用于機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="55b37-139">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="55b37-140">不支援敏感度標籤) </span><span class="sxs-lookup"><span data-stu-id="55b37-140">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="55b37-141">內容已共用</span><span class="sxs-lookup"><span data-stu-id="55b37-141">Content is shared</span></span>

<span data-ttu-id="55b37-142">請注意，所有條件都適用于在 Outlook 用戶端應用程式中撰寫的電子郵件，其將會符合內容，並強制執行內容的保護動作。</span><span class="sxs-lookup"><span data-stu-id="55b37-142">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="55b37-143">不過，向使用者顯示原則提示，但除了上述所述的任何情況之外，還不支援任何條件。</span><span class="sxs-lookup"><span data-stu-id="55b37-143">However, showing policy tips to users is not yet supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="55b37-144">Outlook 2013 和更新版本支援只顯示某些敏感資訊類型的原則提示</span><span class="sxs-lookup"><span data-stu-id="55b37-144">Outlook 2013 and later supports showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="55b37-145">在桌面 (2013 和更新版本) 中，會偵測到顯示 DLP 原則提示的預置資訊類型清單，如下所示：</span><span class="sxs-lookup"><span data-stu-id="55b37-145">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) are the following :</span></span>

- <span data-ttu-id="55b37-146">ABA 路由號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-146">ABA Routing Number</span></span>
- <span data-ttu-id="55b37-147">阿根廷國家身分識別 (DNI) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-147">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="55b37-148">澳大利亞銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-148">Australia Bank Account Number</span></span>
- <span data-ttu-id="55b37-149">澳大利亞醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-149">Australia Medical Account Number</span></span>
- <span data-ttu-id="55b37-150">澳大利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-150">Australia Passport Number</span></span>
- <span data-ttu-id="55b37-151">澳大利亞稅收檔編號</span><span class="sxs-lookup"><span data-stu-id="55b37-151">Australia Tax File Number</span></span>
- <span data-ttu-id="55b37-152">Azure DocumentDB 驗證金鑰</span><span class="sxs-lookup"><span data-stu-id="55b37-152">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="55b37-153">Azure IAAS 資料庫連接字串和 Azure SQL 連接字串</span><span class="sxs-lookup"><span data-stu-id="55b37-153">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="55b37-154">Azure IoT 連接字串</span><span class="sxs-lookup"><span data-stu-id="55b37-154">Azure IoT Connection String</span></span>  
- <span data-ttu-id="55b37-155">Azure 發佈設定密碼</span><span class="sxs-lookup"><span data-stu-id="55b37-155">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="55b37-156">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="55b37-156">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="55b37-157">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="55b37-157">Azure SAS</span></span>  
- <span data-ttu-id="55b37-158">Azure 服務匯流排連接字串</span><span class="sxs-lookup"><span data-stu-id="55b37-158">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="55b37-159">Azure 儲存體帳戶金鑰</span><span class="sxs-lookup"><span data-stu-id="55b37-159">Azure Storage Account Key</span></span>  
- <span data-ttu-id="55b37-160">Azure 儲存體帳戶金鑰 (泛型) </span><span class="sxs-lookup"><span data-stu-id="55b37-160">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="55b37-161">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="55b37-161">Belgium National Number</span></span>
- <span data-ttu-id="55b37-162">巴西 CPF 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-162">Brazil CPF Number</span></span>
- <span data-ttu-id="55b37-163">巴西法人編號 (CNPJ) </span><span class="sxs-lookup"><span data-stu-id="55b37-163">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="55b37-164">巴西全國身分識別卡 (RG) </span><span class="sxs-lookup"><span data-stu-id="55b37-164">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="55b37-165">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-165">Canada Bank Account Number</span></span>
- <span data-ttu-id="55b37-166">加拿大駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-166">Canada Driver's License Number</span></span>
- <span data-ttu-id="55b37-167">加拿大健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-167">Canada Health Service Number</span></span>
- <span data-ttu-id="55b37-168">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-168">Canada Passport Number</span></span>
- <span data-ttu-id="55b37-169">加拿大個人健康身分識別號碼 (PHIN) </span><span class="sxs-lookup"><span data-stu-id="55b37-169">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="55b37-170">加拿大社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-170">Canada Social Insurance Number</span></span>
- <span data-ttu-id="55b37-171">智利身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-171">Chile Identity Card Number</span></span>
- <span data-ttu-id="55b37-172">中國居民身分識別卡 (中國) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-172">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="55b37-173">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-173">Credit Card Number</span></span>
- <span data-ttu-id="55b37-174">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-174">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="55b37-175">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="55b37-175">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="55b37-176">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-176">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="55b37-177">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="55b37-177">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="55b37-178">藥物執行代理商 (DEA) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-178">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="55b37-179">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-179">EU Debit Card Number</span></span>
- <span data-ttu-id="55b37-180">歐盟駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-180">EU Driver's License Number</span></span>  
- <span data-ttu-id="55b37-181">歐盟國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-181">EU National Identification Number</span></span>  
- <span data-ttu-id="55b37-182">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-182">EU Passport Number</span></span>  
- <span data-ttu-id="55b37-183"> (SSN) 或同等識別碼的歐盟社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-183">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="55b37-184">歐盟)  (TIN 的納稅識別號</span><span class="sxs-lookup"><span data-stu-id="55b37-184">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="55b37-185">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="55b37-185">Finland National ID</span></span>
- <span data-ttu-id="55b37-186">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-186">Finland Passport Number</span></span>
- <span data-ttu-id="55b37-187">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-187">France Driver's License Number</span></span>
- <span data-ttu-id="55b37-188">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="55b37-188">France National ID Card (CNI)</span></span>
- <span data-ttu-id="55b37-189">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-189">France Passport Number</span></span>
- <span data-ttu-id="55b37-190">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="55b37-190">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="55b37-191">德國駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-191">German Driver's License Number</span></span>
- <span data-ttu-id="55b37-192">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-192">German Passport Number</span></span>
- <span data-ttu-id="55b37-193">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-193">Germany Identity Card Number</span></span>
- <span data-ttu-id="55b37-194">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="55b37-194">Greece National ID Card</span></span>  
- <span data-ttu-id="55b37-195">香港身分識別卡 (HKID) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-195">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="55b37-196"> (平移) 的印度永久帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-196">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="55b37-197">印度唯一識別碼 (Aadhaar) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-197">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="55b37-198">印尼身分識別卡 (KTP) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-198">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="55b37-199">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="55b37-199">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="55b37-200">國際分類的疾病 (ICD-10-釐米) </span><span class="sxs-lookup"><span data-stu-id="55b37-200">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="55b37-201">疾病 (ICD-9 釐米) 的國際分類</span><span class="sxs-lookup"><span data-stu-id="55b37-201">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="55b37-202">IP 位址</span><span class="sxs-lookup"><span data-stu-id="55b37-202">IP Address</span></span>
- <span data-ttu-id="55b37-203">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-203">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="55b37-204">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-204">Israel Bank Account Number</span></span>
- <span data-ttu-id="55b37-205">以色列國家識別碼</span><span class="sxs-lookup"><span data-stu-id="55b37-205">Israel National ID</span></span>
- <span data-ttu-id="55b37-206">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-206">Italy Driver's License Number</span></span>
- <span data-ttu-id="55b37-207">日本銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-207">Japan Bank Account Number</span></span>
- <span data-ttu-id="55b37-208">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-208">Japan Driver's License Number</span></span>
- <span data-ttu-id="55b37-209">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-209">Japan Passport Number</span></span>
- <span data-ttu-id="55b37-210">日本居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-210">Japan Resident Registration Number</span></span>
- <span data-ttu-id="55b37-211">日本社交保險號碼 (SIN) </span><span class="sxs-lookup"><span data-stu-id="55b37-211">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="55b37-212">日本住家電話卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-212">Japanese Residence Card Number</span></span>
- <span data-ttu-id="55b37-213">馬來西亞身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-213">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="55b37-214">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-214">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="55b37-215">紐西蘭健康情況號碼的部</span><span class="sxs-lookup"><span data-stu-id="55b37-215">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="55b37-216">挪威身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-216">Norway Identity Number</span></span>  
- <span data-ttu-id="55b37-217">菲律賓統一多用途識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-217">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="55b37-218">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="55b37-218">Poland Identity Card</span></span>
- <span data-ttu-id="55b37-219">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="55b37-219">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="55b37-220">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="55b37-220">Poland Passport</span></span>
- <span data-ttu-id="55b37-221">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-221">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="55b37-222">沙烏地阿拉伯國際身分識別</span><span class="sxs-lookup"><span data-stu-id="55b37-222">Saudi Arabia National ID</span></span>
- <span data-ttu-id="55b37-223">新加坡國家註冊身分識別卡 (NRIC) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-223">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="55b37-224">南非識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-224">South Africa Identification Number</span></span>  
- <span data-ttu-id="55b37-225">韓國居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-225">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="55b37-226">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="55b37-226">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="55b37-227">SQL Server 連接字串</span><span class="sxs-lookup"><span data-stu-id="55b37-227">SQL Server Connection String</span></span>  
- <span data-ttu-id="55b37-228">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="55b37-228">Sweden National ID</span></span>
- <span data-ttu-id="55b37-229">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-229">Sweden Passport Number</span></span>
- <span data-ttu-id="55b37-230">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="55b37-230">SWIFT Code</span></span>
- <span data-ttu-id="55b37-231">臺灣國家 ID</span><span class="sxs-lookup"><span data-stu-id="55b37-231">Taiwan National ID</span></span>
- <span data-ttu-id="55b37-232">臺灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-232">Taiwan Passport Number</span></span>
- <span data-ttu-id="55b37-233">臺灣居民憑證 (ARC/TARC) </span><span class="sxs-lookup"><span data-stu-id="55b37-233">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="55b37-234">泰國人口識別碼</span><span class="sxs-lookup"><span data-stu-id="55b37-234">Thai Population Identification Code</span></span>
- <span data-ttu-id="55b37-235">土耳其國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-235">Turkish National Identification number</span></span>
- <span data-ttu-id="55b37-p103">英國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="55b37-p104">英國選民名冊編號</span><span class="sxs-lookup"><span data-stu-id="55b37-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="55b37-p105">英國國民健保服務號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="55b37-p106">英國國民保險號碼 (NINO)</span><span class="sxs-lookup"><span data-stu-id="55b37-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="55b37-244">美國/英國</span><span class="sxs-lookup"><span data-stu-id="55b37-244">U.S. / U.K.</span></span> <span data-ttu-id="55b37-245">護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-245">Passport Number</span></span>
- <span data-ttu-id="55b37-246">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-246">U.S. Bank Account Number</span></span>
- <span data-ttu-id="55b37-247">美國駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-247">U.S. Driver's License Number</span></span>
- <span data-ttu-id="55b37-248">ITIN) 的美國個別納稅人識別號碼 (</span><span class="sxs-lookup"><span data-stu-id="55b37-248">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="55b37-249"> (SSN) 的 U.S. 社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-249">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="55b37-250">請注意，除了上述現成的敏感資訊類型之外，還支援 DLP 原則提示的自訂敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="55b37-250">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="55b37-251">端點的資料遺失防護只支援某些敏感資訊類型的原則秘訣</span><span class="sxs-lookup"><span data-stu-id="55b37-251">Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="55b37-252">在位於端點裝置上的檔中，會偵測到的現成敏感資訊類型清單如下：</span><span class="sxs-lookup"><span data-stu-id="55b37-252">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="55b37-253">ABA 路由號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-253">ABA Routing Number</span></span> 
- <span data-ttu-id="55b37-254">阿根廷國家身分識別 (DNI) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-254">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="55b37-255">澳大利亞銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-255">Australia Bank Account Number</span></span> 
- <span data-ttu-id="55b37-256">澳大利亞醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-256">Australia Medical Account Number</span></span> 
- <span data-ttu-id="55b37-257">澳大利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-257">Australia Passport Number</span></span> 
- <span data-ttu-id="55b37-258">澳大利亞稅收檔編號</span><span class="sxs-lookup"><span data-stu-id="55b37-258">Australia Tax File Number</span></span> 
- <span data-ttu-id="55b37-259">澳大利亞商務電話號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-259">Australian Business Number</span></span> 
- <span data-ttu-id="55b37-260">澳大利亞公司號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-260">Australian Company Number</span></span> 
- <span data-ttu-id="55b37-261">奧地利駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-261">Austria Driver's License Number</span></span> 
- <span data-ttu-id="55b37-262">奧地利身分識別卡</span><span class="sxs-lookup"><span data-stu-id="55b37-262">Austria Identity Card</span></span> 
- <span data-ttu-id="55b37-263">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-263">Austria Passport Number</span></span> 
- <span data-ttu-id="55b37-264">奧地利的社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-264">Austria Social Security Number</span></span> 
- <span data-ttu-id="55b37-265">奧地利納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-265">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="55b37-266">奧地利增值 (加值稅) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-266">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="55b37-267">Azure DocumentDB 驗證金鑰</span><span class="sxs-lookup"><span data-stu-id="55b37-267">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="55b37-268">Azure IAAS 資料庫連接字串和 Azure SQL 連接字串</span><span class="sxs-lookup"><span data-stu-id="55b37-268">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="55b37-269">Azure IoT 連接字串</span><span class="sxs-lookup"><span data-stu-id="55b37-269">Azure IoT Connection String</span></span> 
- <span data-ttu-id="55b37-270">Azure 發佈設定密碼</span><span class="sxs-lookup"><span data-stu-id="55b37-270">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="55b37-271">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="55b37-271">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="55b37-272">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="55b37-272">Azure SAS</span></span> 
- <span data-ttu-id="55b37-273">Azure 服務匯流排連接字串</span><span class="sxs-lookup"><span data-stu-id="55b37-273">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="55b37-274">Azure 儲存體帳戶金鑰</span><span class="sxs-lookup"><span data-stu-id="55b37-274">Azure Storage Account Key</span></span> 
- <span data-ttu-id="55b37-275">Azure 儲存體帳戶金鑰 (泛型) </span><span class="sxs-lookup"><span data-stu-id="55b37-275">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="55b37-276">比利時駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-276">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="55b37-277">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="55b37-277">Belgium National Number</span></span> 
- <span data-ttu-id="55b37-278">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-278">Belgium Passport Number</span></span> 
- <span data-ttu-id="55b37-279">比利時增值的納稅號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-279">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="55b37-280">巴西 CPF 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-280">Brazil CPF Number</span></span> 
- <span data-ttu-id="55b37-281">巴西法人編號 (CNPJ) </span><span class="sxs-lookup"><span data-stu-id="55b37-281">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="55b37-282">巴西全國身分識別卡 (RG) </span><span class="sxs-lookup"><span data-stu-id="55b37-282">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="55b37-283">保加利亞駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-283">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="55b37-284">保加利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-284">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="55b37-285">保加利亞統一的民事編號</span><span class="sxs-lookup"><span data-stu-id="55b37-285">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="55b37-286">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-286">Canada Bank Account Number</span></span> 
- <span data-ttu-id="55b37-287">加拿大駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-287">Canada Driver's License Number</span></span> 
- <span data-ttu-id="55b37-288">加拿大健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-288">Canada Health Service Number</span></span> 
- <span data-ttu-id="55b37-289">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-289">Canada Passport Number</span></span> 
- <span data-ttu-id="55b37-290">加拿大個人健康身分識別號碼 (PHIN) </span><span class="sxs-lookup"><span data-stu-id="55b37-290">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="55b37-291">加拿大社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-291">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="55b37-292">智利身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-292">Chile Identity Card Number</span></span> 
- <span data-ttu-id="55b37-293">中國居民身分識別卡 (中國) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-293">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="55b37-294">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-294">Credit Card Number</span></span> 
- <span data-ttu-id="55b37-295">克羅地亞駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-295">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="55b37-296">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-296">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="55b37-297">克羅地亞國際身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-297">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="55b37-298">克羅地亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-298">Croatia Passport Number</span></span> 
- <span data-ttu-id="55b37-299">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="55b37-299">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="55b37-300">CSCAN-AZURE0060 Azure 儲存體帳戶共用存取簽名</span><span class="sxs-lookup"><span data-stu-id="55b37-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="55b37-301">CSCAN-GENERAL0140 一般對稱金鑰</span><span class="sxs-lookup"><span data-stu-id="55b37-301">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="55b37-302">賽普勒斯駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-302">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="55b37-303">賽普勒斯身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="55b37-303">Cyprus Identity Card</span></span> 
- <span data-ttu-id="55b37-304">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-304">Cyprus Passport Number</span></span> 
- <span data-ttu-id="55b37-305">賽普勒斯納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-305">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="55b37-306">捷克文駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-306">Czech Driver's License Number</span></span> 
- <span data-ttu-id="55b37-307">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-307">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="55b37-308">捷克共和國護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-308">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="55b37-309">丹麥駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-309">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="55b37-310">丹麥護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-310">Denmark Passport Number</span></span> 
- <span data-ttu-id="55b37-311">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="55b37-311">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="55b37-312">藥物執行代理商 (DEA) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-312">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="55b37-313">愛沙尼亞駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-313">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="55b37-314">愛沙尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-314">Estonia Passport Number</span></span> 
- <span data-ttu-id="55b37-315">愛沙尼亞個人識別碼</span><span class="sxs-lookup"><span data-stu-id="55b37-315">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="55b37-316">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-316">EU Debit Card Number</span></span> 
- <span data-ttu-id="55b37-317">歐盟駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-317">EU Driver's License Number</span></span> 
- <span data-ttu-id="55b37-318">歐盟國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-318">EU National Identification Number</span></span> 
- <span data-ttu-id="55b37-319">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-319">EU Passport Number</span></span> 
- <span data-ttu-id="55b37-320"> (SSN) 或同等識別碼的歐盟社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-320">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="55b37-321">歐盟)  (TIN 的納稅識別號</span><span class="sxs-lookup"><span data-stu-id="55b37-321">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="55b37-322">芬蘭駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-322">Finland Driver's License Number</span></span> 
- <span data-ttu-id="55b37-323">芬蘭歐洲健康情況保險業號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-323">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="55b37-324">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="55b37-324">Finland National ID</span></span> 
- <span data-ttu-id="55b37-325">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-325">Finland Passport Number</span></span> 
- <span data-ttu-id="55b37-326">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-326">France Driver's License Number</span></span> 
- <span data-ttu-id="55b37-327">法國健康保險業號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-327">France Health Insurance Number</span></span> 
- <span data-ttu-id="55b37-328">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="55b37-328">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="55b37-329">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-329">France Passport Number</span></span> 
- <span data-ttu-id="55b37-330">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="55b37-330">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="55b37-331">法國納稅識別號碼 (numéro SPI。 ) </span><span class="sxs-lookup"><span data-stu-id="55b37-331">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="55b37-332">法國加值稅收號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-332">France Value Added Tax Number</span></span> 
- <span data-ttu-id="55b37-333">德國駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-333">German Driver's License Number</span></span> 
- <span data-ttu-id="55b37-334">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-334">German Passport Number</span></span> 
- <span data-ttu-id="55b37-335">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-335">Germany Identity Card Number</span></span> 
- <span data-ttu-id="55b37-336">德國納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-336">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="55b37-337">德國加值稅號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-337">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="55b37-338">希臘駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-338">Greece Driver's License Number</span></span> 
- <span data-ttu-id="55b37-339">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="55b37-339">Greece National ID Card</span></span> 
- <span data-ttu-id="55b37-340">希臘護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-340">Greece Passport Number</span></span> 
- <span data-ttu-id="55b37-341"> (AMKA) 的希臘社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-341">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="55b37-342">希臘所得稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-342">Greek Tax identification Number</span></span> 
- <span data-ttu-id="55b37-343">香港身分識別卡 (HKID) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-343">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="55b37-344">匈牙利文社會安全號碼 (TAJ) </span><span class="sxs-lookup"><span data-stu-id="55b37-344">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="55b37-345">匈牙利增值銷售稅編號</span><span class="sxs-lookup"><span data-stu-id="55b37-345">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="55b37-346">匈牙利駕照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-346">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="55b37-347">匈牙利護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-347">Hungary Passport Number</span></span> 
- <span data-ttu-id="55b37-348">匈牙利個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-348">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="55b37-349">匈牙利納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-349">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="55b37-350"> (平移) 的印度永久帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-350">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="55b37-351">印度唯一識別碼 (Aadhaar) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-351">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="55b37-352">印尼身分識別卡 (KTP) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-352">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="55b37-353">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="55b37-353">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="55b37-354">國際分類的疾病 (ICD-10-釐米) </span><span class="sxs-lookup"><span data-stu-id="55b37-354">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="55b37-355">疾病 (ICD-9 釐米) 的國際分類</span><span class="sxs-lookup"><span data-stu-id="55b37-355">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="55b37-356">IP 位址</span><span class="sxs-lookup"><span data-stu-id="55b37-356">IP Address</span></span> 
- <span data-ttu-id="55b37-357">愛爾蘭駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-357">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="55b37-358">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-358">Ireland Passport Number</span></span> 
- <span data-ttu-id="55b37-359">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-359">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="55b37-360">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-360">Israel Bank Account Number</span></span> 
- <span data-ttu-id="55b37-361">以色列國家識別碼</span><span class="sxs-lookup"><span data-stu-id="55b37-361">Israel National ID</span></span> 
- <span data-ttu-id="55b37-362">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-362">Italy Driver's License Number</span></span> 
- <span data-ttu-id="55b37-363">義大利會計代碼</span><span class="sxs-lookup"><span data-stu-id="55b37-363">Italy Fiscal Code</span></span> 
- <span data-ttu-id="55b37-364">義大利護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-364">Italy Passport Number</span></span> 
- <span data-ttu-id="55b37-365">義大利值增加的納稅號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-365">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="55b37-366">日本銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-366">Japan Bank Account Number</span></span> 
- <span data-ttu-id="55b37-367">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-367">Japan Driver's License Number</span></span> 
- <span data-ttu-id="55b37-368">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-368">Japan Passport Number</span></span> 
- <span data-ttu-id="55b37-369">日本居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-369">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="55b37-370">日本社交保險號碼 (SIN) </span><span class="sxs-lookup"><span data-stu-id="55b37-370">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="55b37-371">日本我的數位公司</span><span class="sxs-lookup"><span data-stu-id="55b37-371">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="55b37-372">日本我的數位個人</span><span class="sxs-lookup"><span data-stu-id="55b37-372">Japanese My Number Personal</span></span> 
- <span data-ttu-id="55b37-373">日本住家電話卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-373">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="55b37-374">拉脫維亞駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-374">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="55b37-375">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-375">Latvia Passport Number</span></span> 
- <span data-ttu-id="55b37-376">拉脫維亞個人程式碼</span><span class="sxs-lookup"><span data-stu-id="55b37-376">Latvia Personal Code</span></span> 
- <span data-ttu-id="55b37-377">立陶宛駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-377">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="55b37-378">立陶宛護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-378">Lithuania Passport Number</span></span> 
- <span data-ttu-id="55b37-379">立陶宛個人程式碼</span><span class="sxs-lookup"><span data-stu-id="55b37-379">Lithuania Personal Code</span></span> 
- <span data-ttu-id="55b37-380">Luxemburg 駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-380">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="55b37-381">Luxemburg (自然個人的國家識別號碼) </span><span class="sxs-lookup"><span data-stu-id="55b37-381">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="55b37-382">Luxemburg 非自然人員 (的本國識別碼) </span><span class="sxs-lookup"><span data-stu-id="55b37-382">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="55b37-383">Luxemburg 護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-383">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="55b37-384">馬來西亞身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-384">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="55b37-385">馬爾他駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-385">Malta Driver's License Number</span></span> 
- <span data-ttu-id="55b37-386">馬爾他身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-386">Malta Identity Card Number</span></span> 
- <span data-ttu-id="55b37-387">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-387">Malta Passport Number</span></span> 
- <span data-ttu-id="55b37-388">馬爾他納稅識別碼編號</span><span class="sxs-lookup"><span data-stu-id="55b37-388">Malta Tax ID Number</span></span> 
- <span data-ttu-id="55b37-389">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-389">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="55b37-390">荷蘭駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-390">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="55b37-391">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-391">Netherlands Passport Number</span></span> 
- <span data-ttu-id="55b37-392">荷蘭稅務識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-392">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="55b37-393">荷蘭增值納稅號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-393">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="55b37-394">紐西蘭銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-394">New Zealand bank account number</span></span> 
- <span data-ttu-id="55b37-395">紐西蘭駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-395">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="55b37-396">紐西蘭 Inland 收入數目</span><span class="sxs-lookup"><span data-stu-id="55b37-396">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="55b37-397">紐西蘭健康情況號碼的部</span><span class="sxs-lookup"><span data-stu-id="55b37-397">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="55b37-398">紐西蘭社交 Welfare 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-398">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="55b37-399">挪威身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-399">Norway Identity Number</span></span> 
- <span data-ttu-id="55b37-400">菲律賓統一多用途識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-400">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="55b37-401">波蘭駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-401">Poland Driver's License Number</span></span> 
- <span data-ttu-id="55b37-402">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="55b37-402">Poland Identity Card</span></span> 
- <span data-ttu-id="55b37-403">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="55b37-403">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="55b37-404">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="55b37-404">Poland Passport</span></span> 
- <span data-ttu-id="55b37-405">波蘭納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-405">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="55b37-406">波蘭文 REGON 編號</span><span class="sxs-lookup"><span data-stu-id="55b37-406">Polish REGON Number</span></span> 
- <span data-ttu-id="55b37-407">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-407">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="55b37-408">葡萄牙駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-408">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="55b37-409">葡萄牙護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-409">Portugal Passport Number</span></span> 
- <span data-ttu-id="55b37-410">葡萄牙納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-410">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="55b37-411">羅馬尼亞駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-411">Romania Driver's License Number</span></span> 
- <span data-ttu-id="55b37-412">羅馬尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-412">Romania Passport Number</span></span> 
- <span data-ttu-id="55b37-413">羅馬尼亞個人數值碼 (CNP) </span><span class="sxs-lookup"><span data-stu-id="55b37-413">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="55b37-414"> (國內) 的俄文護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-414">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="55b37-415"> (國際) 的俄文護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-415">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="55b37-416">沙烏地阿拉伯國際身分識別</span><span class="sxs-lookup"><span data-stu-id="55b37-416">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="55b37-417">新加坡國家註冊身分識別卡 (NRIC) 號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-417">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="55b37-418">斯洛伐克駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-418">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="55b37-419">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-419">Slovakia Passport Number</span></span> 
- <span data-ttu-id="55b37-420">斯洛伐克個人號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-420">Slovakia Personal Number</span></span> 
- <span data-ttu-id="55b37-421">斯洛維尼亞駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-421">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="55b37-422">斯洛維尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-422">Slovenia Passport Number</span></span> 
- <span data-ttu-id="55b37-423">斯洛維尼亞納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-423">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="55b37-424">斯洛維尼亞唯一主公民號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-424">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="55b37-425">南非識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-425">South Africa Identification Number</span></span> 
- <span data-ttu-id="55b37-426">韓國居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-426">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="55b37-427">西班牙 DNI</span><span class="sxs-lookup"><span data-stu-id="55b37-427">Spain DNI</span></span> 
- <span data-ttu-id="55b37-428">西班牙駕照編號</span><span class="sxs-lookup"><span data-stu-id="55b37-428">Spain Driver's License Number</span></span> 
- <span data-ttu-id="55b37-429">西班牙護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-429">Spain Passport Number</span></span> 
- <span data-ttu-id="55b37-430">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="55b37-430">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="55b37-431">西班牙納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-431">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="55b37-432">SQL Server 連接字串</span><span class="sxs-lookup"><span data-stu-id="55b37-432">SQL Server Connection String</span></span> 
- <span data-ttu-id="55b37-433">瑞典駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-433">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="55b37-434">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="55b37-434">Sweden National ID</span></span> 
- <span data-ttu-id="55b37-435">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-435">Sweden Passport Number</span></span> 
- <span data-ttu-id="55b37-436">瑞典納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-436">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="55b37-437">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="55b37-437">SWIFT Code</span></span> 
- <span data-ttu-id="55b37-438">瑞士社會安全號碼 AHV</span><span class="sxs-lookup"><span data-stu-id="55b37-438">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="55b37-439">臺灣國家 ID</span><span class="sxs-lookup"><span data-stu-id="55b37-439">Taiwan National ID</span></span> 
- <span data-ttu-id="55b37-440">臺灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-440">Taiwan Passport Number</span></span> 
- <span data-ttu-id="55b37-441">臺灣居民憑證 (ARC/TARC) </span><span class="sxs-lookup"><span data-stu-id="55b37-441">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="55b37-442">泰國人口識別碼</span><span class="sxs-lookup"><span data-stu-id="55b37-442">Thai Population Identification Code</span></span> 
- <span data-ttu-id="55b37-443">土耳其國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-443">Turkish National Identification number</span></span> 
- <span data-ttu-id="55b37-p108">英國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="55b37-p109">英國選民名冊編號</span><span class="sxs-lookup"><span data-stu-id="55b37-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="55b37-p110">英國國民健保服務號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="55b37-p111">英國國民保險號碼 (NINO)</span><span class="sxs-lookup"><span data-stu-id="55b37-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="55b37-452">英國。</span><span class="sxs-lookup"><span data-stu-id="55b37-452">U.K.</span></span> <span data-ttu-id="55b37-453">唯一的納稅人參考編號</span><span class="sxs-lookup"><span data-stu-id="55b37-453">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="55b37-454">美國/英國</span><span class="sxs-lookup"><span data-stu-id="55b37-454">U.S. / U.K.</span></span> <span data-ttu-id="55b37-455">護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-455">Passport Number</span></span> 
- <span data-ttu-id="55b37-456">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-456">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="55b37-457">美國駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-457">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="55b37-458">ITIN) 的美國個別納稅人識別號碼 (</span><span class="sxs-lookup"><span data-stu-id="55b37-458">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="55b37-459"> (SSN) 的 U.S. 社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-459">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="55b37-460"> (國內) 的烏克蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-460">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="55b37-461"> (國際) 的烏克蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="55b37-461">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="55b37-462">請注意，除了上述現成的敏感資訊類型之外，也會偵測自訂的機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="55b37-462">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="55b37-463">跨 Microsoft 應用程式的 DLP 原則提示的支援清單</span><span class="sxs-lookup"><span data-stu-id="55b37-463">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="55b37-464">**應用程式和平臺**</span><span class="sxs-lookup"><span data-stu-id="55b37-464">**App and platform**</span></span>|<span data-ttu-id="55b37-465">**DLP 原則提示支援**</span><span class="sxs-lookup"><span data-stu-id="55b37-465">**DLP policy tip support**</span></span>|<span data-ttu-id="55b37-466">**支援的敏感資訊類型**</span><span class="sxs-lookup"><span data-stu-id="55b37-466">**Sensitive information types supported**</span></span>|<span data-ttu-id="55b37-467">**支援的謂語和動作**</span><span class="sxs-lookup"><span data-stu-id="55b37-467">**Predicates and actions supported**</span></span>|<span data-ttu-id="55b37-468">**Comments**</span><span class="sxs-lookup"><span data-stu-id="55b37-468">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="55b37-469">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="55b37-469">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="55b37-470">全部</span><span class="sxs-lookup"><span data-stu-id="55b37-470">All</span></span>|<span data-ttu-id="55b37-471">Subset</span><span class="sxs-lookup"><span data-stu-id="55b37-471">Subset</span></span>|<span data-ttu-id="55b37-472">請參閱 [資料遺失防護原則提示參考](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="55b37-472">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="55b37-473">**Outlook Win32 (Outlook 2013 及以上)**</span><span class="sxs-lookup"><span data-stu-id="55b37-473">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="55b37-474">Subset</span><span class="sxs-lookup"><span data-stu-id="55b37-474">Subset</span></span>|<span data-ttu-id="55b37-475">Subset</span><span class="sxs-lookup"><span data-stu-id="55b37-475">Subset</span></span>|<span data-ttu-id="55b37-476">請參閱 [outlook 2013 和更新版本支援僅顯示某些條件和例外狀況的原則提示](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) ，以及 [outlook 2013 和更新版本支援顯示只](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) 針對敏感資訊類型支援的原則提示，以及支援在 OUTLOOK Win32 上顯示 DLP 原則提示的 dlp 條件及動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="55b37-476">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later supports showing policy tips for only some sensitive information types](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="55b37-477">**Outlook Mobile (iOS、Android) /Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="55b37-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="55b37-478">無</span><span class="sxs-lookup"><span data-stu-id="55b37-478">None</span></span>|<span data-ttu-id="55b37-479">無</span><span class="sxs-lookup"><span data-stu-id="55b37-479">None</span></span>|<span data-ttu-id="55b37-480">Outlook mobile 不支援 DLP 原則秘訣</span><span class="sxs-lookup"><span data-stu-id="55b37-480">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="55b37-481">**適用于商務網頁用戶端的 Sharepoint Online/單一磁片磁碟機**</span><span class="sxs-lookup"><span data-stu-id="55b37-481">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="55b37-482">全部</span><span class="sxs-lookup"><span data-stu-id="55b37-482">All</span></span>|<span data-ttu-id="55b37-483">DLP 中的所有 SPO/ODB 謂語和動作</span><span class="sxs-lookup"><span data-stu-id="55b37-483">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="55b37-484">**適用于 Business Win32 用戶端的 Sharepoint Win32/單一磁片磁碟機**</span><span class="sxs-lookup"><span data-stu-id="55b37-484">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="55b37-485">無</span><span class="sxs-lookup"><span data-stu-id="55b37-485">None</span></span>|<span data-ttu-id="55b37-486">無</span><span class="sxs-lookup"><span data-stu-id="55b37-486">None</span></span>|<span data-ttu-id="55b37-487">Sharepoint 或 OneDrive 桌面用戶端應用程式不支援 DLP 原則提示</span><span class="sxs-lookup"><span data-stu-id="55b37-487">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="55b37-488">**Word、Excel、Powerpoint Web 用戶端**</span><span class="sxs-lookup"><span data-stu-id="55b37-488">**Word, Excel, Powerpoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="55b37-489">全部</span><span class="sxs-lookup"><span data-stu-id="55b37-489">All</span></span>|<span data-ttu-id="55b37-490">DLP 中的所有 SPO/ODB 謂語和動作</span><span class="sxs-lookup"><span data-stu-id="55b37-490">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="55b37-491">如果檔主控于 SPO 或 ODB web app 上，且已加蓋 DLP 原則，則支援 DLP 原則提示。</span><span class="sxs-lookup"><span data-stu-id="55b37-491">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="55b37-492">**Word、Excel、Powerpoint Mobile 用戶端**</span><span class="sxs-lookup"><span data-stu-id="55b37-492">**Word, Excel, Powerpoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="55b37-493">無</span><span class="sxs-lookup"><span data-stu-id="55b37-493">None</span></span>|<span data-ttu-id="55b37-494">無</span><span class="sxs-lookup"><span data-stu-id="55b37-494">None</span></span>|<span data-ttu-id="55b37-495">Office 行動應用程式不支援 DLP 原則秘訣。</span><span class="sxs-lookup"><span data-stu-id="55b37-495">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="55b37-496">**小組 Web/小組的桌面/小組行動/小組 Mac**</span><span class="sxs-lookup"><span data-stu-id="55b37-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="55b37-497">全部</span><span class="sxs-lookup"><span data-stu-id="55b37-497">All</span></span>|<span data-ttu-id="55b37-498">DLP 原則中的所有團隊謂語</span><span class="sxs-lookup"><span data-stu-id="55b37-498">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="55b37-499">當郵件標示為「此郵件已標記為「已標示」時，就會顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="55b37-499">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="55b37-500">我可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="55b37-500">What can I do?”</span></span> <span data-ttu-id="55b37-501">按一下連結時，使用者可以查看偵測到的敏感資訊類型，並在系統管理員允許的情況下，覆寫或報告問題。請注意，檔案不會顯示任何原則提示。</span><span class="sxs-lookup"><span data-stu-id="55b37-501">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="55b37-502">當收件者嘗試存取檔時，如果不允許存取權，他們可能會遭到拒絕存取。</span><span class="sxs-lookup"><span data-stu-id="55b37-502">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="55b37-503">**Win32 端點裝置**</span><span class="sxs-lookup"><span data-stu-id="55b37-503">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="55b37-504">Subset</span><span class="sxs-lookup"><span data-stu-id="55b37-504">Subset</span></span>|<span data-ttu-id="55b37-505">DLP 原則中的所有端點 DLP 謂詞和動作</span><span class="sxs-lookup"><span data-stu-id="55b37-505">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="55b37-506">[在端點上查看資料遺失防護支援僅限某些敏感資訊類型的原則秘訣](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="55b37-506">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="55b37-507">**Mac 裝置**</span><span class="sxs-lookup"><span data-stu-id="55b37-507">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="55b37-508">無</span><span class="sxs-lookup"><span data-stu-id="55b37-508">None</span></span>|<span data-ttu-id="55b37-509">無</span><span class="sxs-lookup"><span data-stu-id="55b37-509">None</span></span>|<span data-ttu-id="55b37-510">目前無法在 Mac 裝置上強制進行資料遺失防護</span><span class="sxs-lookup"><span data-stu-id="55b37-510">Data loss prevention are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="55b37-511">**協力廠商 cloud app**</span><span class="sxs-lookup"><span data-stu-id="55b37-511">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="55b37-512">無</span><span class="sxs-lookup"><span data-stu-id="55b37-512">None</span></span>|<span data-ttu-id="55b37-513">無</span><span class="sxs-lookup"><span data-stu-id="55b37-513">None</span></span>|<span data-ttu-id="55b37-514">資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="55b37-514">Data Loss Prevention</span></span>|
|<span data-ttu-id="55b37-515">**部署**</span><span class="sxs-lookup"><span data-stu-id="55b37-515">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="55b37-516">無</span><span class="sxs-lookup"><span data-stu-id="55b37-516">None</span></span>|<span data-ttu-id="55b37-517">無</span><span class="sxs-lookup"><span data-stu-id="55b37-517">None</span></span>||
|<span data-ttu-id="55b37-518">**Word、Excel、Powerpoint Win32 用戶端**</span><span class="sxs-lookup"><span data-stu-id="55b37-518">**Word, Excel, Powerpoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="55b37-519">Subset</span><span class="sxs-lookup"><span data-stu-id="55b37-519">Subset</span></span>|<span data-ttu-id="55b37-520">Subset</span><span class="sxs-lookup"><span data-stu-id="55b37-520">Subset</span></span>|<span data-ttu-id="55b37-521">WXP 用戶端應用程式的原則提示可用於儲存在 Sharepoint Online 上的檔或一個用於商務用的磁片磁碟機，以取得完全符合下列條件的所有 DLP 原則，或 DLP 原則中的其中一個條件或動作的子集：</span><span class="sxs-lookup"><span data-stu-id="55b37-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="55b37-522">內容包含機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="55b37-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="55b37-523">存取範圍 (內容是內部或外部共用) </span><span class="sxs-lookup"><span data-stu-id="55b37-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="55b37-524">通知使用者 (原則提示/使用者通知) </span><span class="sxs-lookup"><span data-stu-id="55b37-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="55b37-525">封鎖所有人</span><span class="sxs-lookup"><span data-stu-id="55b37-525">Block everyone</span></span></li><li><span data-ttu-id="55b37-526">事件報告</span><span class="sxs-lookup"><span data-stu-id="55b37-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="55b37-527">如果有任何其他條件或動作出現，該原則的 DLP 原則提示就不會出現在 Word、Excel 或 PowerPoint 的桌面應用程式中。</span><span class="sxs-lookup"><span data-stu-id="55b37-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span>|
||||||