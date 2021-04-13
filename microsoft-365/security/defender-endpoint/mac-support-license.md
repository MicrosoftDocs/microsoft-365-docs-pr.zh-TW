---
title: 疑難排解 Microsoft Defender ATP for Mac 的授權問題
description: 疑難排解 Microsoft Defender ATP for Mac 中的授權問題。
keywords: microsoft、defender、atp、mac、效能
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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689110"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="0b24f-104">疑難排解 macOS 上的 Microsoft Defender for Endpoint 的授權問題</span><span class="sxs-lookup"><span data-stu-id="0b24f-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0b24f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0b24f-105">**Applies to:**</span></span>

- [<span data-ttu-id="0b24f-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b24f-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="0b24f-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0b24f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0b24f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b24f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0b24f-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="0b24f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0b24f-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="0b24f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="0b24f-111">當您在 macOS 和[手動部署](mac-install-manually.md)測試或概念證明 (PoC) 時，若要透過[Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) ，您可能會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="0b24f-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![授權的圖像錯誤](images/no-license-found.png)

<span data-ttu-id="0b24f-113">**消息：**</span><span class="sxs-lookup"><span data-stu-id="0b24f-113">**Message:**</span></span> 

<span data-ttu-id="0b24f-114">找不到授權</span><span class="sxs-lookup"><span data-stu-id="0b24f-114">No license found</span></span>

<span data-ttu-id="0b24f-115">好像您的組織沒有 Microsoft 365 企業版訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="0b24f-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="0b24f-116">請與您的系統管理員聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="0b24f-116">Contact your administrator for help.</span></span>

<span data-ttu-id="0b24f-117">**原因：**</span><span class="sxs-lookup"><span data-stu-id="0b24f-117">**Cause:**</span></span> 

<span data-ttu-id="0b24f-118">您已在 macOS 套件 ( 「下載安裝套件」上部署及（或）安裝 Microsoft Defender for Endpoint ) 但是您可能已執行設定腳本 ( 「下載上架套件」 ) 。</span><span class="sxs-lookup"><span data-stu-id="0b24f-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="0b24f-119">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="0b24f-119">**Solution:**</span></span>

<span data-ttu-id="0b24f-120">遵循下列所述的 MicrosoftDefenderATPOnboardingMacOs.py 指示： [Client configuration](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="0b24f-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

