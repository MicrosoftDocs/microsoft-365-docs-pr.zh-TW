---
title: 了解 Microsoft Teams 中的預設資料外洩防護原則 (預覽)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 深入瞭解 Microsoft Teams 中的預設資料遺失防護原則
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114141"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="3448a-103">了解 Microsoft Teams 中的預設資料外洩防護原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="3448a-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="3448a-104">[資料遺失防護](dlp-learn-about-dlp.md)功能已擴充，可納入 Microsoft Teams 聊天及通道訊息，包括私人通道郵件。</span><span class="sxs-lookup"><span data-stu-id="3448a-104">[Data loss prevention](dlp-learn-about-dlp.md) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="3448a-105">在此版本中，我們會為第一次客戶建立「合規性中心」的預設 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="3448a-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="3448a-106">適用於</span><span class="sxs-lookup"><span data-stu-id="3448a-106">Applies to</span></span>

<span data-ttu-id="3448a-107">以下列一或多個授權授權的任何租使用者，且具有作用中 Teams 使用者</span><span class="sxs-lookup"><span data-stu-id="3448a-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="3448a-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="3448a-108">ME5,</span></span> 
- <span data-ttu-id="3448a-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="3448a-109">MA5,</span></span> 
- <span data-ttu-id="3448a-110">E5/A5 規範</span><span class="sxs-lookup"><span data-stu-id="3448a-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="3448a-111">IP + G，</span><span class="sxs-lookup"><span data-stu-id="3448a-111">IP+G,</span></span> 
- <span data-ttu-id="3448a-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="3448a-112">OE5,</span></span> 
- <span data-ttu-id="3448a-113">O365 高級規範</span><span class="sxs-lookup"><span data-stu-id="3448a-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="3448a-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="3448a-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="3448a-115">預設原則的功能為何？</span><span class="sxs-lookup"><span data-stu-id="3448a-115">What does the default policy do?</span></span>

<span data-ttu-id="3448a-116">預設的 DLP 原則會追蹤組織內部及外部共用的所有信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="3448a-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="3448a-117">針對租使用者的所有使用者，預設為此原則。</span><span class="sxs-lookup"><span data-stu-id="3448a-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="3448a-118">它不會產生任何原則秘訣給使用者，但是會產生警示事件，也會觸發「低嚴重性」電子郵件至系統管理員 (新增于原則) 中。</span><span class="sxs-lookup"><span data-stu-id="3448a-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="3448a-119">管理員可以透過登入規範中心，查看活動並編輯原則詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3448a-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="3448a-120">系統管理員可以在「 [規範中心](https://compliance.microsoft.com/compliancesettings) 」 > 資料遺失防護原則」頁面中查看此原則。</span><span class="sxs-lookup"><span data-stu-id="3448a-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="3448a-121">![預設 Teams DLP 原則](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="3448a-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="3448a-122">編輯或刪除預設原則</span><span class="sxs-lookup"><span data-stu-id="3448a-122">Edit or delete the default policy</span></span>

<span data-ttu-id="3448a-123">若要 [編輯預設原則以取得較佳效能，或將其刪除](create-test-tune-dlp-policy.md#tune-a-dlp-policy)，只需使用具有 **DLP 合規性管理** 許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="3448a-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="3448a-124">如需詳細資訊，請參閱 [許可權](create-test-tune-dlp-policy.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="3448a-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

