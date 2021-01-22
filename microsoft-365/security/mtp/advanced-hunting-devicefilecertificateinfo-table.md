---
title: 進位搜尋架構中的 DeviceFileCertificateInfo 資料表
description: 瞭解進位搜尋架構之 DeviceFileCertificateInfo 資料表中的檔案簽署資訊
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、數位簽章、憑證、檔案簽署、DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931311"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="6113e-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="6113e-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6113e-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="6113e-105">**Applies to:**</span></span>
- <span data-ttu-id="6113e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6113e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6113e-107">進 `DeviceFileCertificateInfo` 位搜尋架構 [中的資料表](advanced-hunting-overview.md) 包含有關檔案簽署憑證的資訊。</span><span class="sxs-lookup"><span data-stu-id="6113e-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="6113e-108">此表格使用從憑證驗證活動取得的資料，會定期在端點上的檔案上執行。</span><span class="sxs-lookup"><span data-stu-id="6113e-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="6113e-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="6113e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6113e-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="6113e-110">Column name</span></span> | <span data-ttu-id="6113e-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="6113e-111">Data type</span></span> | <span data-ttu-id="6113e-112">描述</span><span class="sxs-lookup"><span data-stu-id="6113e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6113e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6113e-113">datetime</span></span> | <span data-ttu-id="6113e-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="6113e-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6113e-115">string</span><span class="sxs-lookup"><span data-stu-id="6113e-115">string</span></span> | <span data-ttu-id="6113e-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="6113e-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6113e-117">string</span><span class="sxs-lookup"><span data-stu-id="6113e-117">string</span></span> | <span data-ttu-id="6113e-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6113e-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="6113e-119">字串</span><span class="sxs-lookup"><span data-stu-id="6113e-119">string</span></span> | <span data-ttu-id="6113e-120">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="6113e-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="6113e-121">布林值</span><span class="sxs-lookup"><span data-stu-id="6113e-121">boolean</span></span> | <span data-ttu-id="6113e-122">指出檔案是否已簽署</span><span class="sxs-lookup"><span data-stu-id="6113e-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="6113e-123">string</span><span class="sxs-lookup"><span data-stu-id="6113e-123">string</span></span> | <span data-ttu-id="6113e-124">指出簽章資訊是在檔案本身中讀取為內嵌內容，或從外部目錄檔案讀取</span><span class="sxs-lookup"><span data-stu-id="6113e-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="6113e-125">string</span><span class="sxs-lookup"><span data-stu-id="6113e-125">string</span></span> | <span data-ttu-id="6113e-126">檔案簽署者的資訊</span><span class="sxs-lookup"><span data-stu-id="6113e-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="6113e-127">string</span><span class="sxs-lookup"><span data-stu-id="6113e-127">string</span></span> | <span data-ttu-id="6113e-128">識別簽簽者的唯一雜湊值</span><span class="sxs-lookup"><span data-stu-id="6113e-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="6113e-129">string</span><span class="sxs-lookup"><span data-stu-id="6113e-129">string</span></span> | <span data-ttu-id="6113e-130">有關發行憑證授權單位 (CA) </span><span class="sxs-lookup"><span data-stu-id="6113e-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="6113e-131">string</span><span class="sxs-lookup"><span data-stu-id="6113e-131">string</span></span> | <span data-ttu-id="6113e-132">唯一雜湊值識別會發行憑證授權單位 (CA) </span><span class="sxs-lookup"><span data-stu-id="6113e-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="6113e-133">string</span><span class="sxs-lookup"><span data-stu-id="6113e-133">string</span></span> | <span data-ttu-id="6113e-134">憑證的識別碼，是發行憑證授權單位 (CA) </span><span class="sxs-lookup"><span data-stu-id="6113e-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="6113e-135">string</span><span class="sxs-lookup"><span data-stu-id="6113e-135">string</span></span> |  <span data-ttu-id="6113e-136">列出網路共用 URL 的 JSON 陣列，其中包含憑證和憑證吊銷清單 (CLS) </span><span class="sxs-lookup"><span data-stu-id="6113e-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="6113e-137">datetime</span><span class="sxs-lookup"><span data-stu-id="6113e-137">datetime</span></span> | <span data-ttu-id="6113e-138">建立憑證的日期和時間</span><span class="sxs-lookup"><span data-stu-id="6113e-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="6113e-139">datetime</span><span class="sxs-lookup"><span data-stu-id="6113e-139">datetime</span></span> | <span data-ttu-id="6113e-140">憑證設定到期日的日期和時間</span><span class="sxs-lookup"><span data-stu-id="6113e-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="6113e-141">datetime</span><span class="sxs-lookup"><span data-stu-id="6113e-141">datetime</span></span> | <span data-ttu-id="6113e-142">憑證簽錯的日期和時間</span><span class="sxs-lookup"><span data-stu-id="6113e-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="6113e-143">布林值</span><span class="sxs-lookup"><span data-stu-id="6113e-143">boolean</span></span> | <span data-ttu-id="6113e-144">根據 WinVerifyTrust 函數的結果來判斷檔案是否受信任，該函數會檢查不明的根憑證資訊、不正確簽章、撤銷的憑證，以及其他可問屬性</span><span class="sxs-lookup"><span data-stu-id="6113e-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="6113e-145">布林值</span><span class="sxs-lookup"><span data-stu-id="6113e-145">boolean</span></span> | <span data-ttu-id="6113e-146">指出根憑證的簽署者是否為 Microsoft</span><span class="sxs-lookup"><span data-stu-id="6113e-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="6113e-147">long</span><span class="sxs-lookup"><span data-stu-id="6113e-147">long</span></span> | <span data-ttu-id="6113e-148">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="6113e-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6113e-149">若要識別唯一事件，此欄必須與 DeviceName 和 Timestamp 資料行一起使用。</span><span class="sxs-lookup"><span data-stu-id="6113e-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="6113e-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="6113e-150">Related topics</span></span>
- [<span data-ttu-id="6113e-151">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="6113e-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6113e-152">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="6113e-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6113e-153">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="6113e-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6113e-154">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="6113e-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6113e-155">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="6113e-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6113e-156">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="6113e-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
