---
title: 以正確的設定擴充進位搜尋範圍
description: 檢查 Windows 裝置上的稽核設定及其他設定，以確保您取得最完整的進一次搜尋資料
keywords: 進進搜尋、事件、樞紐、實體、稽核設定、使用者帳戶管理、安全性群組管理、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365、Microsoft 威脅防護
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
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929583"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="d5915-104">以正確的設定擴充進位搜尋範圍</span><span class="sxs-lookup"><span data-stu-id="d5915-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d5915-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="d5915-105">**Applies to:**</span></span>
- <span data-ttu-id="d5915-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5915-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d5915-107">[進位](advanced-hunting-overview.md) 搜尋仰賴來自各種來源的資料，包括您的裝置、您的 Office 365 工作區、Azure AD 和 Microsoft Defender 的身分識別。</span><span class="sxs-lookup"><span data-stu-id="d5915-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from various sources, including your devices, your Office 365 workspaces, Azure AD, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="d5915-108">若要盡可能取得最完整的資料，請確保您在對應資料來源中擁有正確的設定。</span><span class="sxs-lookup"><span data-stu-id="d5915-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="d5915-109">Windows 裝置上的進位安全性稽核</span><span class="sxs-lookup"><span data-stu-id="d5915-109">Advanced security auditing on Windows devices</span></span>
<span data-ttu-id="d5915-110">開啟這些進位稽核設定，以確保您取得裝置上的活動資料，包括本地帳戶管理、本地安全性群組管理，以及服務建立。</span><span class="sxs-lookup"><span data-stu-id="d5915-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

| <span data-ttu-id="d5915-111">資料</span><span class="sxs-lookup"><span data-stu-id="d5915-111">Data</span></span> | <span data-ttu-id="d5915-112">描述</span><span class="sxs-lookup"><span data-stu-id="d5915-112">Description</span></span> | <span data-ttu-id="d5915-113">架構資料表</span><span class="sxs-lookup"><span data-stu-id="d5915-113">Schema table</span></span> | <span data-ttu-id="d5915-114">如何設定</span><span class="sxs-lookup"><span data-stu-id="d5915-114">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="d5915-115">Account management</span><span class="sxs-lookup"><span data-stu-id="d5915-115">Account management</span></span> | <span data-ttu-id="d5915-116">事件會以各種 `ActionType` 值捕獲，指出建立、刪除和其他帳戶相關活動</span><span class="sxs-lookup"><span data-stu-id="d5915-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="d5915-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="d5915-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="d5915-118">- 部署進一步的安全性稽核政策 [：稽核使用者帳戶管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="d5915-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="d5915-119">- [瞭解進位安全性稽核政策](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="d5915-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="d5915-120">安全性群組管理</span><span class="sxs-lookup"><span data-stu-id="d5915-120">Security group management</span></span> | <span data-ttu-id="d5915-121">事件會以各種值來取用，指出建立本地 `ActionType` 安全性群組和其他本機群組管理活動</span><span class="sxs-lookup"><span data-stu-id="d5915-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="d5915-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="d5915-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="d5915-123">- 部署進一步的安全性稽核政策 [：稽核安全性群組管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="d5915-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="d5915-124">- [瞭解進位安全性稽核政策](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="d5915-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="d5915-125">服務安裝</span><span class="sxs-lookup"><span data-stu-id="d5915-125">Service installation</span></span> | <span data-ttu-id="d5915-126">使用值所取 `ActionType` 的事件 `ServiceInstalled` ，表示已建立服務</span><span class="sxs-lookup"><span data-stu-id="d5915-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="d5915-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="d5915-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="d5915-128">- 部署進一步的安全性稽核政策 [：稽核安全性系統擴充功能](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="d5915-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="d5915-129">- [瞭解進位安全性稽核政策](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="d5915-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a><span data-ttu-id="d5915-130">網域控制站上的 Microsoft Defender for Identity 感應器</span><span class="sxs-lookup"><span data-stu-id="d5915-130">Microsoft Defender for Identity sensor on the domain controller</span></span>
<span data-ttu-id="d5915-131">如果您執行內部部署 Active Directory，您必須在網域控制站上安裝 Microsoft Defender for Identity 感應器，以取得 Microsoft Defender for Identity 的資料。</span><span class="sxs-lookup"><span data-stu-id="d5915-131">If you're running Active Directory on premises, you need to install the Microsoft Defender for Identity sensor on the domain controller to get data for Microsoft Defender for Identity.</span></span> <span data-ttu-id="d5915-132">安裝並正確安裝之後，這項資料也會透過 Microsoft Defender for Identity 進一步搜尋，並提供您網路中身分識別資訊和事件的更深入資訊。</span><span class="sxs-lookup"><span data-stu-id="d5915-132">When installed and properly configured, this data also feeds into advanced hunting through Microsoft Defender for Identity and provides a more holistic picture of identity information and events in your network.</span></span> <span data-ttu-id="d5915-133">此資料也強化了 Microsoft Defender for Identity 產生進一步搜尋所涵蓋之相關警示的能力。</span><span class="sxs-lookup"><span data-stu-id="d5915-133">This data also enhances the ability of Microsoft Defender for Identity to generate relevant alerts that are also covered by advanced hunting.</span></span> 

| <span data-ttu-id="d5915-134">資料</span><span class="sxs-lookup"><span data-stu-id="d5915-134">Data</span></span> | <span data-ttu-id="d5915-135">描述</span><span class="sxs-lookup"><span data-stu-id="d5915-135">Description</span></span> | <span data-ttu-id="d5915-136">架構資料表</span><span class="sxs-lookup"><span data-stu-id="d5915-136">Schema table</span></span> | <span data-ttu-id="d5915-137">如何設定</span><span class="sxs-lookup"><span data-stu-id="d5915-137">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="d5915-138">網域控制站</span><span class="sxs-lookup"><span data-stu-id="d5915-138">Domain controller</span></span> | <span data-ttu-id="d5915-139">內部部署 Active Directory 的資料會針對身分識別而寄至 Microsoft Defender，豐富身分識別相關資訊，例如帳戶詳細資料、登入活動和 Active Directory 查詢</span><span class="sxs-lookup"><span data-stu-id="d5915-139">Data from on-premises Active Directory sent to Microsoft Defender for Identity, enriching identity-related information, such as account details, logon activity, and Active Directory queries</span></span> | <span data-ttu-id="d5915-140">多個資料表，包括[IdentityInfo、IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)和[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) [](advanced-hunting-identityinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="d5915-140">Multiple tables, including [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), and [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)</span></span>  | <span data-ttu-id="d5915-141">- [安裝 Microsoft Defender for Identity 感應器](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)</span><span class="sxs-lookup"><span data-stu-id="d5915-141">- [Install the Microsoft Defender for Identity sensor](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)</span></span><br><span data-ttu-id="d5915-142">- [開啟相關的 Windows 活動](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection)</span><span class="sxs-lookup"><span data-stu-id="d5915-142">- [Turn on relevant Windows Events](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection)</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d5915-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="d5915-143">Related topics</span></span>
- [<span data-ttu-id="d5915-144">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="d5915-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d5915-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="d5915-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
