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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059476"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="c9a22-104">疑難排解適用于 Mac 的 Microsoft Defender for Endpoint 的授權問題</span><span class="sxs-lookup"><span data-stu-id="c9a22-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c9a22-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c9a22-105">**Applies to:**</span></span>

- [<span data-ttu-id="c9a22-106">Mac 版端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c9a22-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="c9a22-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c9a22-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c9a22-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9a22-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c9a22-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c9a22-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c9a22-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c9a22-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c9a22-111">當您要透過 [Microsoft Defender For Mac](microsoft-defender-endpoint-mac.md) 和 [手動部署](mac-install-manually.md) 測試或概念證明 (PoC) 時，您可能會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="c9a22-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![授權的圖像錯誤](images/no-license-found.png)

<span data-ttu-id="c9a22-113">**消息：**</span><span class="sxs-lookup"><span data-stu-id="c9a22-113">**Message:**</span></span> 

<span data-ttu-id="c9a22-114">找不到授權</span><span class="sxs-lookup"><span data-stu-id="c9a22-114">No license found</span></span>

<span data-ttu-id="c9a22-115">好像您的組織沒有 Microsoft 365 企業版訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="c9a22-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="c9a22-116">請與您的系統管理員聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="c9a22-116">Contact your administrator for help.</span></span>

<span data-ttu-id="c9a22-117">**原因：**</span><span class="sxs-lookup"><span data-stu-id="c9a22-117">**Cause:**</span></span> 

<span data-ttu-id="c9a22-118">您已為 macOS 套件部署和/或安裝 Microsoft Defender for Endpoint ( "下載安裝套件" ) 但是您可能已執行設定腳本 ( "下載上架套件" ) 。</span><span class="sxs-lookup"><span data-stu-id="c9a22-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="c9a22-119">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="c9a22-119">**Solution:**</span></span>

<span data-ttu-id="c9a22-120">遵循下列所述的 MicrosoftDefenderATPOnboardingMacOs.py 指示： [Client configuration](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="c9a22-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

