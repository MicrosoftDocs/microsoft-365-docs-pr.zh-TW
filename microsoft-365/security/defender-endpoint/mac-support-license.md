---
title: 針對 Mac 上的 Microsoft Defender for Endpoint 的授權問題進行疑難排解
description: 在 Mac 上為端點的 Microsoft Defender 中的授權問題進行疑難排解。
keywords: microsoft、defender、Microsoft Defender for Endpoint、mac、performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244977"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="b11e5-104">疑難排解 macOS 上的 Microsoft Defender for Endpoint 的授權問題</span><span class="sxs-lookup"><span data-stu-id="b11e5-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b11e5-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b11e5-105">**Applies to:**</span></span>

- [<span data-ttu-id="b11e5-106">macOS 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b11e5-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="b11e5-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b11e5-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b11e5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b11e5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b11e5-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b11e5-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b11e5-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b11e5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b11e5-111">當您在 macOS 和[手動部署](mac-install-manually.md)測試或概念證明 (PoC) 時，若要透過[Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) ，您可能會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="b11e5-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![授權的圖像錯誤](images/no-license-found.png)

<span data-ttu-id="b11e5-113&quot;>**消息：**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;b11e5-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;b11e5-114&quot;>找不到授權</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;b11e5-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;b11e5-115&quot;>好像組織沒有 Microsoft 365 企業版訂閱的授權。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;b11e5-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;b11e5-116&quot;>請與您的系統管理員聯繫以取得協助。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;b11e5-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;b11e5-117&quot;>**原因：**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;b11e5-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;b11e5-118&quot;>您已為 macOS 套件部署及（或）安裝 Microsoft Defender for Endpoint ( &quot;下載安裝套件" ) ，但是您可能已執行設定腳本 ( "下載上架套件" ) ，或是未將授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b11e5-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package"), but you might have run the configuration script ("Download onboarding package"), or you have not assigned a license to the user.</span></span>

<span data-ttu-id="b11e5-119">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="b11e5-119">**Solution:**</span></span>

<span data-ttu-id="b11e5-120">遵循下列所述的 MicrosoftDefenderATPOnboardingMacOs.py 指示： [Client configuration](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="b11e5-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>
