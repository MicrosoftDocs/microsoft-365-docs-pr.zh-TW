---
title: 在 Microsoft 威脅防護中的自動化調查及回應功能的修復動作
description: Microsoft 威脅防護的自動化調查及回應功能的概
keywords: automated, investigation, alert, trigger, action, remediation, 自動化, 調查, 警示, 觸發, 動作, 補救
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175911"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="94678-104">在 Microsoft 威脅防護中的自動化調查及回應功能的修復動作</span><span class="sxs-lookup"><span data-stu-id="94678-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="94678-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="94678-105">**Applies to:**</span></span>
- <span data-ttu-id="94678-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="94678-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="94678-107">Microsoft 威脅防護中的自動化的調查及回應功能包含特定修復動作。</span><span class="sxs-lookup"><span data-stu-id="94678-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="94678-108">某些類型的補救動作所採取的裝置，也稱為端點。</span><span class="sxs-lookup"><span data-stu-id="94678-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="94678-109">在 [電子郵件內容上採取其他修復動作。</span><span class="sxs-lookup"><span data-stu-id="94678-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="94678-110">下表摘要說明目前支援 Microsoft 威脅防護中的補救動作：</span><span class="sxs-lookup"><span data-stu-id="94678-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="94678-111">端點補救動作</span><span class="sxs-lookup"><span data-stu-id="94678-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="94678-112">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="94678-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="94678-113">隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="94678-113">Quarantine file</span></span><br/><span data-ttu-id="94678-114">移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="94678-114">Remove registry key</span></span><br/><span data-ttu-id="94678-115">刪除處理序</span><span class="sxs-lookup"><span data-stu-id="94678-115">Kill process</span></span> <br/><span data-ttu-id="94678-116">停止服務</span><span class="sxs-lookup"><span data-stu-id="94678-116">Stop service</span></span> <br/><span data-ttu-id="94678-117">移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="94678-117">Remove registry key</span></span> <br/><span data-ttu-id="94678-118">停用驅動程式</span><span class="sxs-lookup"><span data-stu-id="94678-118">Disable driver</span></span> <br/><span data-ttu-id="94678-119">移除排程工作</span><span class="sxs-lookup"><span data-stu-id="94678-119">Remove scheduled task</span></span>      |<span data-ttu-id="94678-120">虛刪除電子郵件訊息或群集</span><span class="sxs-lookup"><span data-stu-id="94678-120">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="94678-121">封鎖 URL (點擊時)</span><span class="sxs-lookup"><span data-stu-id="94678-121">Block URL (time-of-click)</span></span><br/><span data-ttu-id="94678-122">關閉外部郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="94678-122">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="94678-123">修復動作，不論他們正在等待核准或已完成，可以檢視在[重要訊息中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)。</span><span class="sxs-lookup"><span data-stu-id="94678-123">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="94678-124">後續步驟</span><span class="sxs-lookup"><span data-stu-id="94678-124">Next steps</span></span>

- [<span data-ttu-id="94678-125">與自動化調查及回應相關的核准或拒絕動作</span><span class="sxs-lookup"><span data-stu-id="94678-125">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="94678-126">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="94678-126">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
