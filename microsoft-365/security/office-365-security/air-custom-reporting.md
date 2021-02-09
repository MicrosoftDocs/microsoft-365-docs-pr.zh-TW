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
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142966"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="bb0c3-104">Microsoft Defender for Office 365 的自訂或協力廠商報表解決方案</span><span class="sxs-lookup"><span data-stu-id="bb0c3-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="bb0c3-105">使用 [Microsoft Defender For Office 365](office-365-atp.md)，您可以取得 [有關自動化調查的詳細資訊](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="bb0c3-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="bb0c3-106">不過，部分組織也會使用自訂或協力廠商報表解決方案。</span><span class="sxs-lookup"><span data-stu-id="bb0c3-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="bb0c3-107">如果您的組織想要整合利用這類方案進行的 [自動調查](office-365-air.md) 資訊，您可以使用 Office 365 管理活動 API。</span><span class="sxs-lookup"><span data-stu-id="bb0c3-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="bb0c3-108">設定整合的資源</span><span class="sxs-lookup"><span data-stu-id="bb0c3-108">Resources to configure integration</span></span>

|<span data-ttu-id="bb0c3-109">資源</span><span class="sxs-lookup"><span data-stu-id="bb0c3-109">Resource</span></span>|<span data-ttu-id="bb0c3-110">描述</span><span class="sxs-lookup"><span data-stu-id="bb0c3-110">Description</span></span>|
|:---|:---|
|<span data-ttu-id="bb0c3-111">[Office 365 Management API 概觀](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) (英文)</span><span class="sxs-lookup"><span data-stu-id="bb0c3-111">[Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span></span>|<span data-ttu-id="bb0c3-112">Office 365 管理活動 API 提供有關 Microsoft 365 和 Azure Active Directory 活動記錄中各種使用者、系統管理員、系統及原則動作和事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="bb0c3-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|<span data-ttu-id="bb0c3-113">[開始使用 Office 365 管理 API](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) (英文)</span><span class="sxs-lookup"><span data-stu-id="bb0c3-113">[Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)</span></span>|<span data-ttu-id="bb0c3-114">Office 365 管理 API 使用 Azure AD 提供應用程式的驗證服務，以存取 Microsoft 365 資料。</span><span class="sxs-lookup"><span data-stu-id="bb0c3-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="bb0c3-115">請依照本文中的步驟進行設定。</span><span class="sxs-lookup"><span data-stu-id="bb0c3-115">Follow the steps in this article to set this up.</span></span>|
|<span data-ttu-id="bb0c3-116">[Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) (英文)</span><span class="sxs-lookup"><span data-stu-id="bb0c3-116">[Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)</span></span>|<span data-ttu-id="bb0c3-117">您可以使用 Office 365 管理活動 API，從 Microsoft 365 和 Azure AD 活動記錄檔中取得使用者、系統管理員、系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bb0c3-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="bb0c3-118">請閱讀本文以深入了解其運作方式。</span><span class="sxs-lookup"><span data-stu-id="bb0c3-118">Read this article to learn more about how this works.</span></span>|
|<span data-ttu-id="bb0c3-119">[Office 365 管理活動 API 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema) (英文)</span><span class="sxs-lookup"><span data-stu-id="bb0c3-119">[Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)</span></span>|<span data-ttu-id="bb0c3-120">取得 [一般架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 和 [Office 365 的 Defender （威脅調查和回應架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) ）的概況，以瞭解透過 OFFICE 365 管理活動 API 提供的特定資料類型。</span><span class="sxs-lookup"><span data-stu-id="bb0c3-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="bb0c3-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bb0c3-121">See also</span></span>

- [<span data-ttu-id="bb0c3-122">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bb0c3-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="bb0c3-123">Microsoft 365 Defender 的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="bb0c3-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
