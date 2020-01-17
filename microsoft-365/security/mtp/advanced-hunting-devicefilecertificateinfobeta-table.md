---
title: DeviceFileCertificateInfoBeta 資料表中的進階的狩獵結構描述
description: 了解簽章 DeviceFileCertificateInfoBeta 表格中的資訊的進階的狩獵結構描述檔案
keywords: 進階搜尋，搜尋，搜尋，microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、] 欄中，輸入資料的網路威脅、 數位簽章、 憑證、 簽章的檔案的威脅DeviceFileCertificateInfoBeta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d5769088f3904bf62d2889f35f236c9410628db
ms.sourcegitcommit: 7705fdbcee4f8714ce044c9e120a431023f7a367
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2020
ms.locfileid: "41230201"
---
# <a name="devicefilecertificateinfobeta"></a><span data-ttu-id="5839d-104">DeviceFileCertificateInfoBeta</span><span class="sxs-lookup"><span data-stu-id="5839d-104">DeviceFileCertificateInfoBeta</span></span>

<span data-ttu-id="5839d-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5839d-105">**Applies to:**</span></span>
- <span data-ttu-id="5839d-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="5839d-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5839d-107">`DeviceFileCertificateInfoBeta` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含簽署憑證的檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5839d-107">The `DeviceFileCertificateInfoBeta` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="5839d-108">此表格會使用取自憑證驗證活動的端點上的檔案上定期執行的資料。</span><span class="sxs-lookup"><span data-stu-id="5839d-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="5839d-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="5839d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5839d-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="5839d-110">Column name</span></span> | <span data-ttu-id="5839d-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="5839d-111">Data type</span></span> | <span data-ttu-id="5839d-112">描述</span><span class="sxs-lookup"><span data-stu-id="5839d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5839d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5839d-113">datetime</span></span> | <span data-ttu-id="5839d-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="5839d-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="5839d-115">字串</span><span class="sxs-lookup"><span data-stu-id="5839d-115">string</span></span> | <span data-ttu-id="5839d-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="5839d-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5839d-117">string</span><span class="sxs-lookup"><span data-stu-id="5839d-117">string</span></span> | <span data-ttu-id="5839d-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="5839d-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="5839d-119">string</span><span class="sxs-lookup"><span data-stu-id="5839d-119">string</span></span> | <span data-ttu-id="5839d-120">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="5839d-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="5839d-121">布林值</span><span class="sxs-lookup"><span data-stu-id="5839d-121">boolean</span></span> | <span data-ttu-id="5839d-122">會指出是否已簽署的檔案</span><span class="sxs-lookup"><span data-stu-id="5839d-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="5839d-123">string</span><span class="sxs-lookup"><span data-stu-id="5839d-123">string</span></span> | <span data-ttu-id="5839d-124">指出是否已讀取的簽章資訊為內嵌</span><span class="sxs-lookup"><span data-stu-id="5839d-124">Indicates whether signature information was read as embedded</span></span> | <span data-ttu-id="5839d-125">在檔案本身的內容或從外部類別目錄檔案的讀取</span><span class="sxs-lookup"><span data-stu-id="5839d-125">content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="5839d-126">string</span><span class="sxs-lookup"><span data-stu-id="5839d-126">string</span></span> | <span data-ttu-id="5839d-127">檔案的簽署者的相關資訊</span><span class="sxs-lookup"><span data-stu-id="5839d-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="5839d-128">string</span><span class="sxs-lookup"><span data-stu-id="5839d-128">string</span></span> | <span data-ttu-id="5839d-129">唯一的雜湊值，識別之簽章</span><span class="sxs-lookup"><span data-stu-id="5839d-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="5839d-130">string</span><span class="sxs-lookup"><span data-stu-id="5839d-130">string</span></span> | <span data-ttu-id="5839d-131">憑證授權單位 (CA) 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="5839d-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="5839d-132">string</span><span class="sxs-lookup"><span data-stu-id="5839d-132">string</span></span> | <span data-ttu-id="5839d-133">唯一的雜湊值，識別發行的憑證授權單位 (CA)</span><span class="sxs-lookup"><span data-stu-id="5839d-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="5839d-134">string</span><span class="sxs-lookup"><span data-stu-id="5839d-134">string</span></span> | <span data-ttu-id="5839d-135">憑證的憑證授權單位 (CA) 的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="5839d-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="5839d-136">string</span><span class="sxs-lookup"><span data-stu-id="5839d-136">string</span></span> |  <span data-ttu-id="5839d-137">列出包含憑證和憑證撤銷清單 (Crl) 的網路共用的 Url 的 JSON 陣列</span><span class="sxs-lookup"><span data-stu-id="5839d-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="5839d-138">datetime</span><span class="sxs-lookup"><span data-stu-id="5839d-138">datetime</span></span> | <span data-ttu-id="5839d-139">憑證已建立的日期和時間</span><span class="sxs-lookup"><span data-stu-id="5839d-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="5839d-140">datetime</span><span class="sxs-lookup"><span data-stu-id="5839d-140">datetime</span></span> | <span data-ttu-id="5839d-141">憑證設定到期日期和時間</span><span class="sxs-lookup"><span data-stu-id="5839d-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="5839d-142">datetime</span><span class="sxs-lookup"><span data-stu-id="5839d-142">datetime</span></span> | <span data-ttu-id="5839d-143">日期和時間已簽署的憑證</span><span class="sxs-lookup"><span data-stu-id="5839d-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="5839d-144">布林值</span><span class="sxs-lookup"><span data-stu-id="5839d-144">boolean</span></span> | <span data-ttu-id="5839d-145">會指出檔案是否信任根據檢查未知的根憑證資訊、 無效的簽章、 撤銷的憑證及其他可疑屬性 WinVerifyTrust 函式的結果</span><span class="sxs-lookup"><span data-stu-id="5839d-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="5839d-146">布林值</span><span class="sxs-lookup"><span data-stu-id="5839d-146">boolean</span></span> | <span data-ttu-id="5839d-147">指出根憑證的簽署者是否為 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5839d-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="5839d-148">long</span><span class="sxs-lookup"><span data-stu-id="5839d-148">long</span></span> | <span data-ttu-id="5839d-149">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="5839d-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="5839d-150">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄。</span><span class="sxs-lookup"><span data-stu-id="5839d-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="5839d-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="5839d-151">Related topics</span></span>
- [<span data-ttu-id="5839d-152">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="5839d-152">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5839d-153">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="5839d-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5839d-154">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="5839d-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5839d-155">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="5839d-155">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5839d-156">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="5839d-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5839d-157">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="5839d-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)