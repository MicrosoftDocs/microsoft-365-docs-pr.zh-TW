---
title: 以適當的設定擴充高級搜尋範圍
description: 檢查 Windows 裝置上的審計設定及其他設定，以協助確保您在高級搜尋中取得最全面的資料
keywords: 高級搜尋、事件、資料透視、實體、審核設定、使用者帳戶管理、安全性群組管理、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、mdatp、Microsoft Defender ATP、Microsoft Defender for Endpoint、Windows Defender、Windows Defender ATP、Windows Defender 高級威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500621"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="71866-104">以適當的設定擴充高級搜尋範圍</span><span class="sxs-lookup"><span data-stu-id="71866-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71866-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="71866-105">**Applies to:**</span></span>
- [<span data-ttu-id="71866-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="71866-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="71866-107">[[高級搜尋](advanced-hunting-overview.md)] 取決於組織內的資料。</span><span class="sxs-lookup"><span data-stu-id="71866-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="71866-108">若要盡可能取得最完整的資料，請務必在對應的資料來源中具備正確的設定。</span><span class="sxs-lookup"><span data-stu-id="71866-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="71866-109">Windows 裝置上的高級安全性審核</span><span class="sxs-lookup"><span data-stu-id="71866-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="71866-110">開啟這些高級審核設定，以確保您取得裝置上活動的相關資料，包括本機帳戶管理、本機安全性群組管理及服務建立。</span><span class="sxs-lookup"><span data-stu-id="71866-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="71866-111">資料</span><span class="sxs-lookup"><span data-stu-id="71866-111">Data</span></span> | <span data-ttu-id="71866-112">描述</span><span class="sxs-lookup"><span data-stu-id="71866-112">Description</span></span> | <span data-ttu-id="71866-113">架構表格</span><span class="sxs-lookup"><span data-stu-id="71866-113">Schema table</span></span> | <span data-ttu-id="71866-114">如何設定</span><span class="sxs-lookup"><span data-stu-id="71866-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="71866-115">Account management</span><span class="sxs-lookup"><span data-stu-id="71866-115">Account management</span></span> | <span data-ttu-id="71866-116">以各種值來捕獲的事件， `ActionType` 表示本地帳戶建立、刪除及其他與帳戶相關的活動</span><span class="sxs-lookup"><span data-stu-id="71866-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="71866-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="71866-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="71866-118">-部署高級安全性審核原則： [審核使用者帳戶管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="71866-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="71866-119">- [深入瞭解高級安全性審核原則](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="71866-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="71866-120">安全性群組管理</span><span class="sxs-lookup"><span data-stu-id="71866-120">Security group management</span></span> | <span data-ttu-id="71866-121">以各種值來捕獲的事件 `ActionType` ，表示本機安全性群組的建立和其他本地群組管理活動</span><span class="sxs-lookup"><span data-stu-id="71866-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="71866-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="71866-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="71866-123">-部署高級安全性審核原則： [審核安全性群組管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="71866-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="71866-124">- [深入瞭解高級安全性審核原則](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="71866-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="71866-125">服務安裝</span><span class="sxs-lookup"><span data-stu-id="71866-125">Service installation</span></span> | <span data-ttu-id="71866-126">以值捕獲的 `ActionType` 事件 `ServiceInstalled` ，表示已建立服務</span><span class="sxs-lookup"><span data-stu-id="71866-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="71866-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="71866-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="71866-128">-部署高級安全性審核原則： [審核安全性系統擴充](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="71866-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="71866-129">- [深入瞭解高級安全性審核原則](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="71866-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="71866-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="71866-130">Related topics</span></span>

- [<span data-ttu-id="71866-131">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="71866-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="71866-132">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="71866-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="71866-133">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="71866-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="71866-134">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="71866-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="71866-135">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="71866-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="71866-136">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="71866-136">Custom detections overview</span></span>](overview-custom-detections.md)
