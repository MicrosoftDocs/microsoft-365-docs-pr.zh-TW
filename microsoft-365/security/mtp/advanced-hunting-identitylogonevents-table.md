---
title: Advanced 搜尋架構中的 IdentityLogonEvents 表格
description: 深入瞭解在高級搜尋架構的 IdentityLogonEvents 資料表中，由 Active Directory 記錄的驗證事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，描述，IdentityLogonEvents，Azure AD，Active Directory，Azure ATP，身分識別
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 2116d8f6f1006f5acf9d468006fa07a04e13087b
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046025"
---
# <a name="identitylogonevents"></a><span data-ttu-id="42b4e-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="42b4e-104">IdentityLogonEvents</span></span>

<span data-ttu-id="42b4e-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="42b4e-105">**Applies to:**</span></span>
- <span data-ttu-id="42b4e-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="42b4e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="42b4e-107">[！附注] `IdentityLogonEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含透過 Azure ATP 和驗證活動（透過 Microsoft Cloud App Security 所捕獲的 microsoft online 服務所捕獲）進行驗證的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="42b4e-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities made through your on-premises Active Directory captured by Azure ATP and authentication activities related to Microsoft online services captured by Microsoft Cloud App Security.</span></span> <span data-ttu-id="42b4e-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="42b4e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="42b4e-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="42b4e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="42b4e-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="42b4e-110">Column name</span></span> | <span data-ttu-id="42b4e-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="42b4e-111">Data type</span></span> | <span data-ttu-id="42b4e-112">描述</span><span class="sxs-lookup"><span data-stu-id="42b4e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="42b4e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="42b4e-113">datetime</span></span> | <span data-ttu-id="42b4e-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="42b4e-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="42b4e-115">字串</span><span class="sxs-lookup"><span data-stu-id="42b4e-115">string</span></span> | <span data-ttu-id="42b4e-116">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="42b4e-116">Type of activity that triggered the event</span></span> |
| `LogonType` | <span data-ttu-id="42b4e-117">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-117">string</span></span> | <span data-ttu-id="42b4e-118">登入會話的類型，特別：</span><span class="sxs-lookup"><span data-stu-id="42b4e-118">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="42b4e-119">- **互動式**使用者會使用本機鍵盤和畫面，以實際方式與機器互動</span><span class="sxs-lookup"><span data-stu-id="42b4e-119">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="42b4e-120">- **遠端互動（RDP）** 登入-使用者利用遠端桌面、終端機服務、遠端協助或其他 RDP 用戶端從遠端互動</span><span class="sxs-lookup"><span data-stu-id="42b4e-120">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="42b4e-121">- 使用 PsExec 存取機器時，或在機器上共用資源（如印表機和共用資料夾）存取時，所啟動的**網路**會話</span><span class="sxs-lookup"><span data-stu-id="42b4e-121">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="42b4e-122">- 由排程任務所啟動的**批次**會話</span><span class="sxs-lookup"><span data-stu-id="42b4e-122">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="42b4e-123">- **服務**-啟動時由服務啟動的會話</span><span class="sxs-lookup"><span data-stu-id="42b4e-123">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="42b4e-124">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-124">string</span></span> | <span data-ttu-id="42b4e-125">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="42b4e-125">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="42b4e-126">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-126">string</span></span> | <span data-ttu-id="42b4e-127">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="42b4e-127">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="42b4e-128">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-128">string</span></span> | <span data-ttu-id="42b4e-129">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="42b4e-129">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="42b4e-130">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-130">string</span></span> | <span data-ttu-id="42b4e-131">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="42b4e-131">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="42b4e-132">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-132">string</span></span> | <span data-ttu-id="42b4e-133">帳戶的使用者主要名稱（UPN）</span><span class="sxs-lookup"><span data-stu-id="42b4e-133">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="42b4e-134">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-134">string</span></span> | <span data-ttu-id="42b4e-135">帳戶的安全性識別碼（SID）</span><span class="sxs-lookup"><span data-stu-id="42b4e-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="42b4e-136">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-136">string</span></span> | <span data-ttu-id="42b4e-137">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="42b4e-137">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="42b4e-138">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-138">string</span></span> | <span data-ttu-id="42b4e-139">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="42b4e-139">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="42b4e-140">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="42b4e-140">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="42b4e-141">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-141">string</span></span> | <span data-ttu-id="42b4e-142">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="42b4e-142">Fully qualified domain name (FQDN) of the machine</span></span> |
| `DeviceType` | <span data-ttu-id="42b4e-143">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-143">string</span></span> | <span data-ttu-id="42b4e-144">裝置類型</span><span class="sxs-lookup"><span data-stu-id="42b4e-144">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="42b4e-145">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-145">string</span></span> | <span data-ttu-id="42b4e-146">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="42b4e-146">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="42b4e-147">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="42b4e-147">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="42b4e-148">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-148">string</span></span> | <span data-ttu-id="42b4e-149">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="42b4e-149">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="42b4e-150">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-150">string</span></span> | <span data-ttu-id="42b4e-151">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="42b4e-151">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="42b4e-152">string</span><span class="sxs-lookup"><span data-stu-id="42b4e-152">string</span></span> | <span data-ttu-id="42b4e-153">與端點 IP 位址相關聯的網際網路服務提供者（ISP）</span><span class="sxs-lookup"><span data-stu-id="42b4e-153">Internet service provider (ISP) associated with the endpoint IP address</span></span> |

## <a name="related-topics"></a><span data-ttu-id="42b4e-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="42b4e-154">Related topics</span></span>
- [<span data-ttu-id="42b4e-155">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="42b4e-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="42b4e-156">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="42b4e-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="42b4e-157">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="42b4e-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="42b4e-158">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="42b4e-158">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="42b4e-159">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="42b4e-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="42b4e-160">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="42b4e-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
