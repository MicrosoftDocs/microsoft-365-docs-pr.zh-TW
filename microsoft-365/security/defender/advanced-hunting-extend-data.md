---
title: 以適當的設定擴充高級搜尋範圍
description: 檢查 Windows 裝置上的審計設定及其他設定，以協助確保您在高級搜尋中取得最全面的資料
keywords: 高級搜尋、事件、資料透視、實體、審核設定、使用者帳戶管理、安全性群組管理、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365、Microsoft 威脅防護
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
ms.openlocfilehash: 1fc4635b71e68bb56fa7ec54c9c7b1263b83446b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498238"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="6666b-104">以適當的設定擴充高級搜尋範圍</span><span class="sxs-lookup"><span data-stu-id="6666b-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6666b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6666b-105">**Applies to:**</span></span>
- <span data-ttu-id="6666b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6666b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6666b-107">[[高級搜尋](advanced-hunting-overview.md)] 取決於來自各種來源的資料，包括您的裝置、Office 365 工作區、Azure AD 及 Microsoft Defender 身分識別。</span><span class="sxs-lookup"><span data-stu-id="6666b-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from various sources, including your devices, your Office 365 workspaces, Azure AD, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="6666b-108">若要盡可能取得最完整的資料，請務必在對應的資料來源中具備正確的設定。</span><span class="sxs-lookup"><span data-stu-id="6666b-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="6666b-109">Windows 裝置上的高級安全性審核</span><span class="sxs-lookup"><span data-stu-id="6666b-109">Advanced security auditing on Windows devices</span></span>
<span data-ttu-id="6666b-110">開啟這些高級審核設定，以確保您取得裝置上活動的相關資料，包括本機帳戶管理、本機安全性群組管理及服務建立。</span><span class="sxs-lookup"><span data-stu-id="6666b-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

| <span data-ttu-id="6666b-111">資料</span><span class="sxs-lookup"><span data-stu-id="6666b-111">Data</span></span> | <span data-ttu-id="6666b-112">描述</span><span class="sxs-lookup"><span data-stu-id="6666b-112">Description</span></span> | <span data-ttu-id="6666b-113">架構表格</span><span class="sxs-lookup"><span data-stu-id="6666b-113">Schema table</span></span> | <span data-ttu-id="6666b-114">如何設定</span><span class="sxs-lookup"><span data-stu-id="6666b-114">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="6666b-115">Account management</span><span class="sxs-lookup"><span data-stu-id="6666b-115">Account management</span></span> | <span data-ttu-id="6666b-116">以各種值來捕獲的事件， `ActionType` 表示本地帳戶建立、刪除及其他與帳戶相關的活動</span><span class="sxs-lookup"><span data-stu-id="6666b-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="6666b-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="6666b-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="6666b-118">-部署高級安全性審核原則： [審核使用者帳戶管理](/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="6666b-118">- Deploy an advanced security audit policy: [Audit User Account Management](/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="6666b-119">- [深入瞭解高級安全性審核原則](/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="6666b-119">- [Learn about advanced security audit policies](/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="6666b-120">安全性群組管理</span><span class="sxs-lookup"><span data-stu-id="6666b-120">Security group management</span></span> | <span data-ttu-id="6666b-121">以各種值來捕獲的事件 `ActionType` ，表示本機安全性群組的建立和其他本地群組管理活動</span><span class="sxs-lookup"><span data-stu-id="6666b-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="6666b-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="6666b-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="6666b-123">-部署高級安全性審核原則： [審核安全性群組管理](/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="6666b-123">- Deploy an advanced security audit policy: [Audit Security Group Management](/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="6666b-124">- [深入瞭解高級安全性審核原則](/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="6666b-124">- [Learn about advanced security audit policies](/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="6666b-125">服務安裝</span><span class="sxs-lookup"><span data-stu-id="6666b-125">Service installation</span></span> | <span data-ttu-id="6666b-126">以值捕獲的 `ActionType` 事件 `ServiceInstalled` ，表示已建立服務</span><span class="sxs-lookup"><span data-stu-id="6666b-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="6666b-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="6666b-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="6666b-128">-部署高級安全性審核原則： [審核安全性系統擴充](/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="6666b-128">- Deploy an advanced security audit policy: [Audit Security System Extension](/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="6666b-129">- [深入瞭解高級安全性審核原則](/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="6666b-129">- [Learn about advanced security audit policies](/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a><span data-ttu-id="6666b-130">網域控制站上的身分識別感應器的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6666b-130">Microsoft Defender for Identity sensor on the domain controller</span></span>
<span data-ttu-id="6666b-131">如果您要在內部部署中執行 Active Directory，您必須在網域控制站上安裝 Microsoft Defender for Identity 感應器，以取得 Microsoft Defender 身分識別的資料。</span><span class="sxs-lookup"><span data-stu-id="6666b-131">If you're running Active Directory on premises, you need to install the Microsoft Defender for Identity sensor on the domain controller to get data for Microsoft Defender for Identity.</span></span> <span data-ttu-id="6666b-132">安裝並正確設定後，此資料也會進入透過 Microsoft Defender 身分識別的高級搜尋，並提供網路中身分識別資訊和事件的整體功能。</span><span class="sxs-lookup"><span data-stu-id="6666b-132">When installed and properly configured, this data also feeds into advanced hunting through Microsoft Defender for Identity and provides a more holistic picture of identity information and events in your network.</span></span> <span data-ttu-id="6666b-133">這項資料也會增強 Microsoft Defender 身分識別產生相關警示的功能，這些警示也會在高級搜尋中涵蓋。</span><span class="sxs-lookup"><span data-stu-id="6666b-133">This data also enhances the ability of Microsoft Defender for Identity to generate relevant alerts that are also covered by advanced hunting.</span></span> 

| <span data-ttu-id="6666b-134">資料</span><span class="sxs-lookup"><span data-stu-id="6666b-134">Data</span></span> | <span data-ttu-id="6666b-135">描述</span><span class="sxs-lookup"><span data-stu-id="6666b-135">Description</span></span> | <span data-ttu-id="6666b-136">架構表格</span><span class="sxs-lookup"><span data-stu-id="6666b-136">Schema table</span></span> | <span data-ttu-id="6666b-137">如何設定</span><span class="sxs-lookup"><span data-stu-id="6666b-137">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="6666b-138">網域控制站</span><span class="sxs-lookup"><span data-stu-id="6666b-138">Domain controller</span></span> | <span data-ttu-id="6666b-139">從內部部署 Active Directory 傳送至 Microsoft Defender 以進行身分識別的資料，濃縮身分識別相關的資訊，例如帳戶詳細資料、登入活動和 Active Directory 查詢</span><span class="sxs-lookup"><span data-stu-id="6666b-139">Data from on-premises Active Directory sent to Microsoft Defender for Identity, enriching identity-related information, such as account details, logon activity, and Active Directory queries</span></span> | <span data-ttu-id="6666b-140">多個資料表，包括 [IdentityInfo](advanced-hunting-identityinfo-table.md)、 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)及 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="6666b-140">Multiple tables, including [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), and [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)</span></span>  | <span data-ttu-id="6666b-141">- [安裝 Microsoft Defender 的身分識別感應器](/azure-advanced-threat-protection/install-atp-step4)</span><span class="sxs-lookup"><span data-stu-id="6666b-141">- [Install the Microsoft Defender for Identity sensor](/azure-advanced-threat-protection/install-atp-step4)</span></span><br><span data-ttu-id="6666b-142">- [開啟相關的 Windows 事件](/azure-advanced-threat-protection/configure-event-collection)</span><span class="sxs-lookup"><span data-stu-id="6666b-142">- [Turn on relevant Windows Events](/azure-advanced-threat-protection/configure-event-collection)</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6666b-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="6666b-143">Related topics</span></span>
- [<span data-ttu-id="6666b-144">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="6666b-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6666b-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="6666b-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)