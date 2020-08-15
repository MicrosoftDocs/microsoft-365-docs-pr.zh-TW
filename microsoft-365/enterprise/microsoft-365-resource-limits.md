---
title: Microsoft 365 資源限制
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，您可以找到 Microsoft 365 內各種應用程式的資源限制的相關資訊。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6053740d41b02461432243c8527391a4f8ae22ea
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688679"
---
# <a name="resource-limits"></a><span data-ttu-id="de76f-103">資源限制</span><span class="sxs-lookup"><span data-stu-id="de76f-103">Resource Limits</span></span>

<span data-ttu-id="de76f-104">資源限制是使用配額來強制執行 (限制) 和節流。</span><span class="sxs-lookup"><span data-stu-id="de76f-104">Resource limits are enforced using quotas (limits) and throttling.</span></span> <span data-ttu-id="de76f-105">Azure Active Directory (Azure AD) 和個別 Microsoft 365 服務都會使用兩者。</span><span class="sxs-lookup"><span data-stu-id="de76f-105">Azure Active Directory (Azure AD) and the individual Microsoft 365 services use both.</span></span> <span data-ttu-id="de76f-106">限制是服務特有的，而且隨時間而變更會隨著新功能的增加而變更。</span><span class="sxs-lookup"><span data-stu-id="de76f-106">Limits are service-specific and change over time as new capabilities are added.</span></span> <span data-ttu-id="de76f-107">如需各種服務目前限制的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="de76f-107">For details on the current limits for the various services, see the following topics:</span></span>

- [<span data-ttu-id="de76f-108">Azure AD 服務限制和限制</span><span class="sxs-lookup"><span data-stu-id="de76f-108">Azure AD service limits and restrictions</span></span>](https://docs.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits)
- [<span data-ttu-id="de76f-109">Exchange Online 限制</span><span class="sxs-lookup"><span data-stu-id="de76f-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/library/exchange-online-limits.aspx)
- [<span data-ttu-id="de76f-110">Exchange Online Protection 限制</span><span class="sxs-lookup"><span data-stu-id="de76f-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="de76f-111">SharePoint 線上軟體界限和限制</span><span class="sxs-lookup"><span data-stu-id="de76f-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="de76f-112">商務用 Skype 限制</span><span class="sxs-lookup"><span data-stu-id="de76f-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="de76f-113">Yammer REST API 和速率限制</span><span class="sxs-lookup"><span data-stu-id="de76f-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="de76f-114">Sway 中的檔案大小限制</span><span class="sxs-lookup"><span data-stu-id="de76f-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="de76f-115">除了這些限制以外，還會在整個 Azure AD 和 Microsoft 365 中使用多個節流機制。</span><span class="sxs-lookup"><span data-stu-id="de76f-115">In addition to these limits, several throttling mechanisms are used throughout Azure AD and Microsoft 365.</span></span> <span data-ttu-id="de76f-116">在服務內節流尤其重要，因為 Microsoft 資料中心的網路資源已針對使用服務的廣泛客戶進行優化。</span><span class="sxs-lookup"><span data-stu-id="de76f-116">Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services.</span></span> <span data-ttu-id="de76f-117">節流機制包括：</span><span class="sxs-lookup"><span data-stu-id="de76f-117">Throttling mechanisms include:</span></span>

- <span data-ttu-id="de76f-118">Azure AD 和 Microsoft 365 功能的使用者層級節流，它會限制由單一使用者執行的腳本或程式碼) 所 (的交易或並行通話數目。</span><span class="sxs-lookup"><span data-stu-id="de76f-118">Azure AD and Microsoft 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="de76f-119">在建立承租人時，會將預設的 PowerShell 節流原則指派給每個承租人。</span><span class="sxs-lookup"><span data-stu-id="de76f-119">A default PowerShell throttling policy is assigned to each tenant at tenant creation.</span></span> <span data-ttu-id="de76f-120">這些設定會影響其他專案，例如可由單一系統管理員開啟的最大併發 PowerShell 會話數目。</span><span class="sxs-lookup"><span data-stu-id="de76f-120">These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="de76f-121">每個 Exchange Online 客戶都有 (EWS) 原則，以進行 EWS 用戶端作業的預設 Exchange Web 服務，以及適用于所有 Outlook 用戶端的節流。</span><span class="sxs-lookup"><span data-stu-id="de76f-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
