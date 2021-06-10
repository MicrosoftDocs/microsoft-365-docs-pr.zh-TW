---
title: Advanced 搜尋架構中的 DeviceFileCertificateInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceFileCertificateInfo 資料表中的檔案簽署資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，數位簽章，憑證，檔簽署，DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023210"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="10fb0-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="10fb0-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="10fb0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="10fb0-105">**Applies to:**</span></span>
- <span data-ttu-id="10fb0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10fb0-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="10fb0-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="10fb0-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="10fb0-108">[！附注] `DeviceFileCertificateInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含檔簽署憑證的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="10fb0-108">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="10fb0-109">此表格使用從憑證驗證活動取得的資料，定期對端點上的檔案執行。</span><span class="sxs-lookup"><span data-stu-id="10fb0-109">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="10fb0-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="10fb0-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="10fb0-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="10fb0-111">Column name</span></span> | <span data-ttu-id="10fb0-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="10fb0-112">Data type</span></span> | <span data-ttu-id="10fb0-113">描述</span><span class="sxs-lookup"><span data-stu-id="10fb0-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="10fb0-114">datetime</span><span class="sxs-lookup"><span data-stu-id="10fb0-114">datetime</span></span> | <span data-ttu-id="10fb0-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="10fb0-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="10fb0-116">string</span><span class="sxs-lookup"><span data-stu-id="10fb0-116">string</span></span> | <span data-ttu-id="10fb0-117">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="10fb0-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="10fb0-118">string</span><span class="sxs-lookup"><span data-stu-id="10fb0-118">string</span></span> | <span data-ttu-id="10fb0-119">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="10fb0-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="10fb0-120">字串</span><span class="sxs-lookup"><span data-stu-id="10fb0-120">string</span></span> | <span data-ttu-id="10fb0-121">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="10fb0-121">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="10fb0-122">布林值</span><span class="sxs-lookup"><span data-stu-id="10fb0-122">boolean</span></span> | <span data-ttu-id="10fb0-123">指出檔是否已簽署</span><span class="sxs-lookup"><span data-stu-id="10fb0-123">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="10fb0-124">string</span><span class="sxs-lookup"><span data-stu-id="10fb0-124">string</span></span> | <span data-ttu-id="10fb0-125">會指出簽章資訊是做為內嵌內容，還是從外部目錄檔讀取</span><span class="sxs-lookup"><span data-stu-id="10fb0-125">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="10fb0-126">string</span><span class="sxs-lookup"><span data-stu-id="10fb0-126">string</span></span> | <span data-ttu-id="10fb0-127">檔案的簽署者相關資訊</span><span class="sxs-lookup"><span data-stu-id="10fb0-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="10fb0-128">string</span><span class="sxs-lookup"><span data-stu-id="10fb0-128">string</span></span> | <span data-ttu-id="10fb0-129">識別簽署者的唯一雜湊值</span><span class="sxs-lookup"><span data-stu-id="10fb0-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="10fb0-130">string</span><span class="sxs-lookup"><span data-stu-id="10fb0-130">string</span></span> | <span data-ttu-id="10fb0-131">發證憑證授權 (CA 的相關資訊) </span><span class="sxs-lookup"><span data-stu-id="10fb0-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="10fb0-132">string</span><span class="sxs-lookup"><span data-stu-id="10fb0-132">string</span></span> | <span data-ttu-id="10fb0-133">唯一的雜湊值，用以識別發證憑證授權 (CA) </span><span class="sxs-lookup"><span data-stu-id="10fb0-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="10fb0-134">string</span><span class="sxs-lookup"><span data-stu-id="10fb0-134">string</span></span> | <span data-ttu-id="10fb0-135">發證憑證授權 (CA 所獨有之憑證的識別碼) </span><span class="sxs-lookup"><span data-stu-id="10fb0-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="10fb0-136">string</span><span class="sxs-lookup"><span data-stu-id="10fb0-136">string</span></span> |  <span data-ttu-id="10fb0-137">JSON 陣列，列出包含憑證和憑證吊銷清單 (Crl 的網路共用 URLs) </span><span class="sxs-lookup"><span data-stu-id="10fb0-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="10fb0-138">datetime</span><span class="sxs-lookup"><span data-stu-id="10fb0-138">datetime</span></span> | <span data-ttu-id="10fb0-139">建立憑證的日期和時間</span><span class="sxs-lookup"><span data-stu-id="10fb0-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="10fb0-140">datetime</span><span class="sxs-lookup"><span data-stu-id="10fb0-140">datetime</span></span> | <span data-ttu-id="10fb0-141">將憑證設為到期的日期和時間</span><span class="sxs-lookup"><span data-stu-id="10fb0-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="10fb0-142">datetime</span><span class="sxs-lookup"><span data-stu-id="10fb0-142">datetime</span></span> | <span data-ttu-id="10fb0-143">反署憑證的日期和時間</span><span class="sxs-lookup"><span data-stu-id="10fb0-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="10fb0-144">布林值</span><span class="sxs-lookup"><span data-stu-id="10fb0-144">boolean</span></span> | <span data-ttu-id="10fb0-145">會指出是否要根據 WinVerifyTrust 函式的結果來信任檔案，該函數會檢查未知的根憑證資訊、不正確簽章、吊銷的憑證，以及其他可疑屬性</span><span class="sxs-lookup"><span data-stu-id="10fb0-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="10fb0-146">布林值</span><span class="sxs-lookup"><span data-stu-id="10fb0-146">boolean</span></span> | <span data-ttu-id="10fb0-147">會指出根憑證的簽署者是否為 Microsoft</span><span class="sxs-lookup"><span data-stu-id="10fb0-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="10fb0-148">long</span><span class="sxs-lookup"><span data-stu-id="10fb0-148">long</span></span> | <span data-ttu-id="10fb0-149">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="10fb0-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="10fb0-150">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用。</span><span class="sxs-lookup"><span data-stu-id="10fb0-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="10fb0-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="10fb0-151">Related topics</span></span>
- [<span data-ttu-id="10fb0-152">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="10fb0-152">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="10fb0-153">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="10fb0-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="10fb0-154">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="10fb0-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="10fb0-155">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="10fb0-155">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="10fb0-156">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="10fb0-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="10fb0-157">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="10fb0-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
