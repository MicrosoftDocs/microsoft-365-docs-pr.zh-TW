---
title: 什麼 Microsoft 安全分數即將？
description: 說明 Microsoft 安全分數 Microsoft 365 安全性中心、 詳細資料的計算方式，以及安全性系統管理員可以預期。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365，安全分數資訊安全中心、 改進動作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372001"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="637a8-104">什麼 Microsoft 安全分數即將？</span><span class="sxs-lookup"><span data-stu-id="637a8-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="637a8-105">若要讓 Microsoft 安全分數較佳的安全性狀態代表並改善可用性，我們會在不久的將來進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="637a8-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="637a8-106">您的成績和最大可能分數會變更。</span><span class="sxs-lookup"><span data-stu-id="637a8-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="637a8-107">不過，這並不表示您的安全性狀態變更。</span><span class="sxs-lookup"><span data-stu-id="637a8-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="637a8-108">若要深入了解最近的變更，請參閱[What's new in Microsoft 安全分數？](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="637a8-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="637a8-109">16 2020 年 3 月</span><span class="sxs-lookup"><span data-stu-id="637a8-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="637a8-110">移除不符合預期可靠的度量單位，或沒有提供實用的安全性狀態表示改進動作</span><span class="sxs-lookup"><span data-stu-id="637a8-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="637a8-111">若要確保 Microsoft 安全分數才有意義，以及改進的每一個動作是可以測量且可靠，我們會移除下列改進動作。</span><span class="sxs-lookup"><span data-stu-id="637a8-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="637a8-112">商務用 OneDrive 中儲存使用者文件</span><span class="sxs-lookup"><span data-stu-id="637a8-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="637a8-113">設定 Office 365 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="637a8-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="637a8-114">若要確認 Url 設定 Office 365 安全連結</span><span class="sxs-lookup"><span data-stu-id="637a8-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="637a8-115">不允許 [信箱委派]</span><span class="sxs-lookup"><span data-stu-id="637a8-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="637a8-116">允許匿名來賓共用網站和文件的連結</span><span class="sxs-lookup"><span data-stu-id="637a8-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="637a8-117">開啟雲端 App 安全性主控台</span><span class="sxs-lookup"><span data-stu-id="637a8-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="637a8-118">設定外部共用連結的到期時間</span><span class="sxs-lookup"><span data-stu-id="637a8-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="637a8-119">Azure AD 改進動作支援安全的預設值</span><span class="sxs-lookup"><span data-stu-id="637a8-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="637a8-120">Microsoft 安全分數會更新改進動作來支援[Azure AD 中預設的安全性](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，方便大家來協助保護您的組織使用的常見的攻擊的預先設定的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="637a8-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="637a8-121">它會影響下列改進動作：</span><span class="sxs-lookup"><span data-stu-id="637a8-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="637a8-122">確定所有的使用者可以完成的安全存取多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="637a8-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="637a8-123">需要 MFA 的系統管理角色</span><span class="sxs-lookup"><span data-stu-id="637a8-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="637a8-124">啟用原則，以封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="637a8-124">Enable policy to block legacy authentication</span></span>
