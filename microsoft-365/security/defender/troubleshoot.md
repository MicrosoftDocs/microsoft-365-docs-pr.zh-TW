---
title: 疑難排解 Microsoft 365 的 Defender 服務問題
description: 尋找已知 Microsoft 365 Defender 問題的解決方案和解決方法
keywords: 疑難排解 Microsoft 365 Defender、疑難排解、Microsoft Defender for Identity、問題、附加元件、設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782738"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="02e7d-104">疑難排解 Microsoft 365 的 Defender 服務問題</span><span class="sxs-lookup"><span data-stu-id="02e7d-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="02e7d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="02e7d-105">**Applies to:**</span></span>
- <span data-ttu-id="02e7d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02e7d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="02e7d-107">本節說明當您使用 Microsoft 365 Defender 服務時可能會發生的問題。</span><span class="sxs-lookup"><span data-stu-id="02e7d-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="02e7d-108">我看不到 Microsoft 365 的 Defender 內容</span><span class="sxs-lookup"><span data-stu-id="02e7d-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="02e7d-109">如果您在流覽窗格中看不到 [事件]、[重要訊息中心] 或 [搜尋] 等功能，您必須確認您的承租人具有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="02e7d-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="02e7d-110">如需詳細資訊，請參閱[必要條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="02e7d-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="02e7d-111">Microsoft defender for Identity 警示未顯示在 Microsoft 365 Defender 事件中</span><span class="sxs-lookup"><span data-stu-id="02e7d-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="02e7d-112">如果您已在環境中部署 Microsoft Defender，但在 Microsoft 365 defender 事件中卻沒有看到身分識別警示，您必須確定已啟用 Microsoft Cloud App Security 和 Defender 的身分識別整合。</span><span class="sxs-lookup"><span data-stu-id="02e7d-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="02e7d-113">如需詳細資訊，請參閱 [Microsoft Defender For Identity integration](/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="02e7d-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="02e7d-114">開啟服務的設定頁面位於何處？</span><span class="sxs-lookup"><span data-stu-id="02e7d-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="02e7d-115">若要開啟 Microsoft 365 Defender，請從 Microsoft 365 安全性中心的功能窗格存取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="02e7d-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="02e7d-116">只有當您具有 [必要許可權和授權](m365d-enable.md#check-license-eligibility-and-required-permissions)時，才會顯示此導覽專案。</span><span class="sxs-lookup"><span data-stu-id="02e7d-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="02e7d-117">如何建立檔案/URL 的例外狀況？</span><span class="sxs-lookup"><span data-stu-id="02e7d-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="02e7d-118">誤報是指偵測為惡意但不是威脅的檔案或 URL。</span><span class="sxs-lookup"><span data-stu-id="02e7d-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="02e7d-119">您可以建立指示器並定義排除專案，以解除封鎖並允許某些檔案/URLs。</span><span class="sxs-lookup"><span data-stu-id="02e7d-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="02e7d-120">請參閱 [在 Defender For Endpoint 中的位址誤報/負片](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。</span><span class="sxs-lookup"><span data-stu-id="02e7d-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


