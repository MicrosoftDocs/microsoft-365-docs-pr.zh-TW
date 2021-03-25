---
title: 使用自動調查和回應的自訂報告解決方案
keywords: SIEM，API，AIR，autoIR，ATP，自動化調查，整合，自訂報告
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 瞭解如何使用自訂或協力廠商報表解決方案來整合自動調查和回應。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82f3b38e5b6e31313c94f5ac389e883f6b076540
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204784"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="9214e-104">Microsoft Defender for Office 365 的自訂或協力廠商報表解決方案</span><span class="sxs-lookup"><span data-stu-id="9214e-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9214e-105">使用 [Microsoft Defender For Office 365](defender-for-office-365.md)，您可以取得 [有關自動化調查的詳細資訊](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="9214e-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="9214e-106">不過，部分組織也會使用自訂或協力廠商報表解決方案。</span><span class="sxs-lookup"><span data-stu-id="9214e-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="9214e-107">如果您的組織想要整合利用這類方案進行的 [自動調查](office-365-air.md) 資訊，您可以使用 Office 365 管理活動 API。</span><span class="sxs-lookup"><span data-stu-id="9214e-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="9214e-108">**適用於**</span><span class="sxs-lookup"><span data-stu-id="9214e-108">**Applies to**</span></span>
- [<span data-ttu-id="9214e-109">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="9214e-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9214e-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9214e-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9214e-111">使用 [Microsoft Defender For Office 365](defender-for-office-365.md)，您可以取得 [有關自動化調查的詳細資訊](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="9214e-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="9214e-112">不過，部分組織也會使用自訂或協力廠商報表解決方案。</span><span class="sxs-lookup"><span data-stu-id="9214e-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="9214e-113">如果您的組織想要整合利用這類方案進行的自動調查資訊，您可以使用 Office 365 管理活動 API。</span><span class="sxs-lookup"><span data-stu-id="9214e-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="9214e-114">資源</span><span class="sxs-lookup"><span data-stu-id="9214e-114">Resource</span></span>|<span data-ttu-id="9214e-115">描述</span><span class="sxs-lookup"><span data-stu-id="9214e-115">Description</span></span>|
|:---|:---|
|<span data-ttu-id="9214e-116">[Office 365 Management API 概觀](/office/office-365-management-api/office-365-management-apis-overview) (英文)</span><span class="sxs-lookup"><span data-stu-id="9214e-116">[Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview)</span></span>|<span data-ttu-id="9214e-117">Office 365 管理活動 API 提供有關 Microsoft 365 和 Azure Active Directory 活動記錄中各種使用者、系統管理員、系統及原則動作和事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="9214e-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|<span data-ttu-id="9214e-118">[開始使用 Office 365 管理 API](/office/office-365-management-api/get-started-with-office-365-management-apis) (英文)</span><span class="sxs-lookup"><span data-stu-id="9214e-118">[Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis)</span></span>|<span data-ttu-id="9214e-119">Office 365 管理 API 使用 Azure AD 提供應用程式的驗證服務，以存取 Microsoft 365 資料。</span><span class="sxs-lookup"><span data-stu-id="9214e-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="9214e-120">請依照本文中的步驟進行設定。</span><span class="sxs-lookup"><span data-stu-id="9214e-120">Follow the steps in this article to set this up.</span></span>|
|<span data-ttu-id="9214e-121">[Office 365 管理活動 API 參考](/office/office-365-management-api/office-365-management-activity-api-reference) (英文)</span><span class="sxs-lookup"><span data-stu-id="9214e-121">[Office 365 Management Activity API reference](/office/office-365-management-api/office-365-management-activity-api-reference)</span></span>|<span data-ttu-id="9214e-122">您可以使用 Office 365 管理活動 API，從 Microsoft 365 和 Azure AD 活動記錄檔中取得使用者、系統管理員、系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9214e-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="9214e-123">請閱讀本文以深入了解其運作方式。</span><span class="sxs-lookup"><span data-stu-id="9214e-123">Read this article to learn more about how this works.</span></span>|
|<span data-ttu-id="9214e-124">[Office 365 管理活動 API 架構](/office/office-365-management-api/office-365-management-activity-api-schema) (英文)</span><span class="sxs-lookup"><span data-stu-id="9214e-124">[Office 365 Management Activity API schema](/office/office-365-management-api/office-365-management-activity-api-schema)</span></span>|<span data-ttu-id="9214e-125">取得 [一般架構](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 和 [Office 365 的 Defender （威脅調查和回應架構](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) ）的概況，以瞭解透過 OFFICE 365 管理活動 API 提供的特定資料類型。</span><span class="sxs-lookup"><span data-stu-id="9214e-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="9214e-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9214e-126">See also</span></span>

- [<span data-ttu-id="9214e-127">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9214e-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9214e-128">Microsoft 365 Defender 的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="9214e-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
