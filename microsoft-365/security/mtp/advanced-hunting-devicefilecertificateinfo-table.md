---
title: Advanced 搜尋架構中的 DeviceFileCertificateInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceFileCertificateInfo 資料表中的檔案簽署資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，數位簽章，憑證，檔簽署，DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 926f129b95e1d9d6b07f56955bdf061884d4340b
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430101"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="72c13-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="72c13-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="72c13-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="72c13-105">**Applies to:**</span></span>
- <span data-ttu-id="72c13-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="72c13-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="72c13-107">[！附注] `DeviceFileCertificateInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含檔簽署憑證的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="72c13-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="72c13-108">此表格使用從憑證驗證活動取得的資料，定期對端點上的檔案執行。</span><span class="sxs-lookup"><span data-stu-id="72c13-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="72c13-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="72c13-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="72c13-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="72c13-110">Column name</span></span> | <span data-ttu-id="72c13-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="72c13-111">Data type</span></span> | <span data-ttu-id="72c13-112">描述</span><span class="sxs-lookup"><span data-stu-id="72c13-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="72c13-113">datetime</span><span class="sxs-lookup"><span data-stu-id="72c13-113">datetime</span></span> | <span data-ttu-id="72c13-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="72c13-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="72c13-115">string</span><span class="sxs-lookup"><span data-stu-id="72c13-115">string</span></span> | <span data-ttu-id="72c13-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="72c13-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="72c13-117">string</span><span class="sxs-lookup"><span data-stu-id="72c13-117">string</span></span> | <span data-ttu-id="72c13-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="72c13-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="72c13-119">字串</span><span class="sxs-lookup"><span data-stu-id="72c13-119">string</span></span> | <span data-ttu-id="72c13-120">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="72c13-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="72c13-121">布林值</span><span class="sxs-lookup"><span data-stu-id="72c13-121">boolean</span></span> | <span data-ttu-id="72c13-122">指出檔是否已簽署</span><span class="sxs-lookup"><span data-stu-id="72c13-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="72c13-123">string</span><span class="sxs-lookup"><span data-stu-id="72c13-123">string</span></span> | <span data-ttu-id="72c13-124">會指出簽章資訊是做為內嵌內容，還是從外部目錄檔讀取</span><span class="sxs-lookup"><span data-stu-id="72c13-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="72c13-125">string</span><span class="sxs-lookup"><span data-stu-id="72c13-125">string</span></span> | <span data-ttu-id="72c13-126">檔案的簽署者相關資訊</span><span class="sxs-lookup"><span data-stu-id="72c13-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="72c13-127">string</span><span class="sxs-lookup"><span data-stu-id="72c13-127">string</span></span> | <span data-ttu-id="72c13-128">識別簽署者的唯一雜湊值</span><span class="sxs-lookup"><span data-stu-id="72c13-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="72c13-129">string</span><span class="sxs-lookup"><span data-stu-id="72c13-129">string</span></span> | <span data-ttu-id="72c13-130">發證憑證授權 (CA 的相關資訊) </span><span class="sxs-lookup"><span data-stu-id="72c13-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="72c13-131">string</span><span class="sxs-lookup"><span data-stu-id="72c13-131">string</span></span> | <span data-ttu-id="72c13-132">唯一的雜湊值，用以識別發證憑證授權 (CA) </span><span class="sxs-lookup"><span data-stu-id="72c13-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="72c13-133">string</span><span class="sxs-lookup"><span data-stu-id="72c13-133">string</span></span> | <span data-ttu-id="72c13-134">發證憑證授權 (CA 所獨有之憑證的識別碼) </span><span class="sxs-lookup"><span data-stu-id="72c13-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="72c13-135">string</span><span class="sxs-lookup"><span data-stu-id="72c13-135">string</span></span> |  <span data-ttu-id="72c13-136">JSON 陣列，列出包含憑證和憑證吊銷清單 (Crl 的網路共用 URLs) </span><span class="sxs-lookup"><span data-stu-id="72c13-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="72c13-137">datetime</span><span class="sxs-lookup"><span data-stu-id="72c13-137">datetime</span></span> | <span data-ttu-id="72c13-138">建立憑證的日期和時間</span><span class="sxs-lookup"><span data-stu-id="72c13-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="72c13-139">datetime</span><span class="sxs-lookup"><span data-stu-id="72c13-139">datetime</span></span> | <span data-ttu-id="72c13-140">將憑證設為到期的日期和時間</span><span class="sxs-lookup"><span data-stu-id="72c13-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="72c13-141">datetime</span><span class="sxs-lookup"><span data-stu-id="72c13-141">datetime</span></span> | <span data-ttu-id="72c13-142">反署憑證的日期和時間</span><span class="sxs-lookup"><span data-stu-id="72c13-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="72c13-143">布林值</span><span class="sxs-lookup"><span data-stu-id="72c13-143">boolean</span></span> | <span data-ttu-id="72c13-144">會指出是否要根據 WinVerifyTrust 函式的結果來信任檔案，該函數會檢查未知的根憑證資訊、不正確簽章、吊銷的憑證，以及其他可疑屬性</span><span class="sxs-lookup"><span data-stu-id="72c13-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="72c13-145">布林值</span><span class="sxs-lookup"><span data-stu-id="72c13-145">boolean</span></span> | <span data-ttu-id="72c13-146">會指出根憑證的簽署者是否為 Microsoft</span><span class="sxs-lookup"><span data-stu-id="72c13-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="72c13-147">long</span><span class="sxs-lookup"><span data-stu-id="72c13-147">long</span></span> | <span data-ttu-id="72c13-148">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="72c13-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="72c13-149">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用。</span><span class="sxs-lookup"><span data-stu-id="72c13-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="72c13-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="72c13-150">Related topics</span></span>
- [<span data-ttu-id="72c13-151">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="72c13-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="72c13-152">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="72c13-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="72c13-153">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="72c13-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="72c13-154">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="72c13-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="72c13-155">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="72c13-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="72c13-156">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="72c13-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
