---
title: 使用自訂報表解決方案與自動調查和回應
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 瞭解如何使用自訂或協力廠商報表解決方案來整合自動調查和回應。
ms.openlocfilehash: 2ff0ef995fc8418c3d57895f00ea96f05b0aaa97
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195602"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="55886-104">使用自訂或協力廠商報表解決方案的管理活動 API</span><span class="sxs-lookup"><span data-stu-id="55886-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="55886-105">使用 [Office 365 的高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)，您可以取得 [有關自動化調查的詳細資訊](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="55886-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="55886-106">不過，部分組織也會使用自訂或協力廠商報表解決方案。</span><span class="sxs-lookup"><span data-stu-id="55886-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="55886-107">如果您的組織想要整合利用這類方案進行的自動調查資訊，您可以使用 Office 365 管理活動 API。</span><span class="sxs-lookup"><span data-stu-id="55886-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="55886-108">使用下列資源進行設定：</span><span class="sxs-lookup"><span data-stu-id="55886-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="55886-109">資源</span><span class="sxs-lookup"><span data-stu-id="55886-109">Resource</span></span>|<span data-ttu-id="55886-110">描述</span><span class="sxs-lookup"><span data-stu-id="55886-110">Description</span></span>|
|---|---|
|<span data-ttu-id="55886-111">[Office 365 Management API 概觀](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) (英文)</span><span class="sxs-lookup"><span data-stu-id="55886-111">[Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span></span>|<span data-ttu-id="55886-112">Office 365 管理活動 API 提供有關 Microsoft 365 和 Azure Active Directory 活動記錄中各種使用者、系統管理員、系統及原則動作和事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="55886-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|<span data-ttu-id="55886-113">[開始使用 Office 365 管理 API](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) (英文)</span><span class="sxs-lookup"><span data-stu-id="55886-113">[Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)</span></span>|<span data-ttu-id="55886-114">Office 365 管理 API 使用 Azure AD 提供應用程式的驗證服務，以存取 Microsoft 365 資料。</span><span class="sxs-lookup"><span data-stu-id="55886-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="55886-115">請依照本文中的步驟進行設定。</span><span class="sxs-lookup"><span data-stu-id="55886-115">Follow the steps in this article to set this up.</span></span>|
|<span data-ttu-id="55886-116">[Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) (英文)</span><span class="sxs-lookup"><span data-stu-id="55886-116">[Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)</span></span>|<span data-ttu-id="55886-117">您可以使用 Office 365 管理活動 API，從 Microsoft 365 和 Azure AD 活動記錄檔中取得使用者、系統管理員、系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="55886-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="55886-118">請閱讀本文以深入了解其運作方式。</span><span class="sxs-lookup"><span data-stu-id="55886-118">Read this article to learn more about how this works.</span></span>|
|<span data-ttu-id="55886-119">[Office 365 管理活動 API 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema) (英文)</span><span class="sxs-lookup"><span data-stu-id="55886-119">[Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)</span></span>|<span data-ttu-id="55886-120">取得[常見架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) (英文) 和 [Office 365 ATP 和威脅調查和回應架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (英文) 的概觀，以深入了解 Office 365 管理活動 API 中可用的特定類型資料。</span><span class="sxs-lookup"><span data-stu-id="55886-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="related-articles"></a><span data-ttu-id="55886-121">相關文章</span><span class="sxs-lookup"><span data-stu-id="55886-121">Related articles</span></span>

- [<span data-ttu-id="55886-122">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="55886-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="55886-123">深入瞭解 Microsoft 威脅防護中的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="55886-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
