---
title: Advanced 搜尋架構中的 DeviceFileCertificateInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceFileCertificateInfo 資料表中的檔案簽署資訊
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、數位簽章、憑證、檔簽署、DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058452"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="a2172-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="a2172-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a2172-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a2172-105">**Applies to:**</span></span>
- [<span data-ttu-id="a2172-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a2172-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="a2172-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a2172-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a2172-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a2172-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="a2172-109">[！附注] `DeviceFileCertificateInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含檔簽署憑證的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a2172-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="a2172-110">此表格使用從憑證驗證活動取得的資料，定期對端點上的檔案執行。</span><span class="sxs-lookup"><span data-stu-id="a2172-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="a2172-111">如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。</span><span class="sxs-lookup"><span data-stu-id="a2172-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="a2172-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="a2172-112">Column name</span></span> | <span data-ttu-id="a2172-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="a2172-113">Data type</span></span> | <span data-ttu-id="a2172-114">描述</span><span class="sxs-lookup"><span data-stu-id="a2172-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a2172-115">datetime</span><span class="sxs-lookup"><span data-stu-id="a2172-115">datetime</span></span> | <span data-ttu-id="a2172-116">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="a2172-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a2172-117">string</span><span class="sxs-lookup"><span data-stu-id="a2172-117">string</span></span> | <span data-ttu-id="a2172-118">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="a2172-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a2172-119">string</span><span class="sxs-lookup"><span data-stu-id="a2172-119">string</span></span> | <span data-ttu-id="a2172-120">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="a2172-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="a2172-121">字串</span><span class="sxs-lookup"><span data-stu-id="a2172-121">string</span></span> | <span data-ttu-id="a2172-122">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="a2172-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="a2172-123">布林值</span><span class="sxs-lookup"><span data-stu-id="a2172-123">boolean</span></span> | <span data-ttu-id="a2172-124">指出檔是否已簽署</span><span class="sxs-lookup"><span data-stu-id="a2172-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="a2172-125">string</span><span class="sxs-lookup"><span data-stu-id="a2172-125">string</span></span> | <span data-ttu-id="a2172-126">會指出簽章資訊是做為內嵌內容，還是從外部目錄檔讀取</span><span class="sxs-lookup"><span data-stu-id="a2172-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="a2172-127">string</span><span class="sxs-lookup"><span data-stu-id="a2172-127">string</span></span> | <span data-ttu-id="a2172-128">檔案的簽署者相關資訊</span><span class="sxs-lookup"><span data-stu-id="a2172-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="a2172-129">string</span><span class="sxs-lookup"><span data-stu-id="a2172-129">string</span></span> | <span data-ttu-id="a2172-130">識別簽署者的唯一雜湊值</span><span class="sxs-lookup"><span data-stu-id="a2172-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="a2172-131">string</span><span class="sxs-lookup"><span data-stu-id="a2172-131">string</span></span> | <span data-ttu-id="a2172-132">發證憑證授權 (CA 的相關資訊) </span><span class="sxs-lookup"><span data-stu-id="a2172-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="a2172-133">string</span><span class="sxs-lookup"><span data-stu-id="a2172-133">string</span></span> | <span data-ttu-id="a2172-134">唯一的雜湊值，用以識別發證憑證授權 (CA) </span><span class="sxs-lookup"><span data-stu-id="a2172-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="a2172-135">string</span><span class="sxs-lookup"><span data-stu-id="a2172-135">string</span></span> | <span data-ttu-id="a2172-136">發證憑證授權 (CA 所獨有之憑證的識別碼) </span><span class="sxs-lookup"><span data-stu-id="a2172-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="a2172-137">string</span><span class="sxs-lookup"><span data-stu-id="a2172-137">string</span></span> |  <span data-ttu-id="a2172-138">JSON 陣列，列出包含憑證和憑證吊銷清單 (Crl 的網路共用 URLs) </span><span class="sxs-lookup"><span data-stu-id="a2172-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="a2172-139">datetime</span><span class="sxs-lookup"><span data-stu-id="a2172-139">datetime</span></span> | <span data-ttu-id="a2172-140">建立憑證的日期和時間</span><span class="sxs-lookup"><span data-stu-id="a2172-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="a2172-141">datetime</span><span class="sxs-lookup"><span data-stu-id="a2172-141">datetime</span></span> | <span data-ttu-id="a2172-142">將憑證設為到期的日期和時間</span><span class="sxs-lookup"><span data-stu-id="a2172-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="a2172-143">datetime</span><span class="sxs-lookup"><span data-stu-id="a2172-143">datetime</span></span> | <span data-ttu-id="a2172-144">反署憑證的日期和時間</span><span class="sxs-lookup"><span data-stu-id="a2172-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="a2172-145">布林值</span><span class="sxs-lookup"><span data-stu-id="a2172-145">boolean</span></span> | <span data-ttu-id="a2172-146">會指出是否要根據 WinVerifyTrust 函式的結果來信任檔案，該函數會檢查未知的根憑證資訊、不正確簽章、吊銷的憑證，以及其他可疑屬性</span><span class="sxs-lookup"><span data-stu-id="a2172-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="a2172-147">布林值</span><span class="sxs-lookup"><span data-stu-id="a2172-147">boolean</span></span> | <span data-ttu-id="a2172-148">會指出根憑證的簽署者是否為 Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2172-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="a2172-149">long</span><span class="sxs-lookup"><span data-stu-id="a2172-149">long</span></span> | <span data-ttu-id="a2172-150">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="a2172-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a2172-151">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用。</span><span class="sxs-lookup"><span data-stu-id="a2172-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="a2172-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="a2172-152">Related topics</span></span>
- [<span data-ttu-id="a2172-153">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="a2172-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a2172-154">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="a2172-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a2172-155">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="a2172-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
