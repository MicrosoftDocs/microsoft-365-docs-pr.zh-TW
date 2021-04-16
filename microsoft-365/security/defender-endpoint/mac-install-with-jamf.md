---
title: 使用 Jamf Pro 為 macOS 部署 Microsoft Defender for Endpoint
description: 使用 Jamf Pro 為 macOS 部署 Microsoft Defender for Endpoint
keywords: microsoft，defender，atp，mac，安裝，部署，卸載，intune，jamfpro，macos，catalina，mojave，高塞拉里昂
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
ms.openlocfilehash: e49a56b138e792f06229345d19a5867c9f6438af
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862256"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="2bc7d-104">在具有 Jamf Pro 的 macOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bc7d-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2bc7d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2bc7d-105">**Applies to:**</span></span>
- [<span data-ttu-id="2bc7d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2bc7d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2bc7d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bc7d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2bc7d-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2bc7d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2bc7d-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2bc7d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="2bc7d-110">瞭解如何在使用 Jamf Pro 的 macOS 上部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="2bc7d-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="2bc7d-111">如果您使用 macOS Catalina (10.15.4) 或更新版本的 macOS，請參閱 [新的設定設定檔以取得 MacOS Catalina 和更新版本的 macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)。</span><span class="sxs-lookup"><span data-stu-id="2bc7d-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="2bc7d-112">這是一個多重步驟過程。</span><span class="sxs-lookup"><span data-stu-id="2bc7d-112">This is a multi step process.</span></span> <span data-ttu-id="2bc7d-113">您必須完成下列所有步驟：</span><span class="sxs-lookup"><span data-stu-id="2bc7d-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="2bc7d-114">登入至 Jamf 入口網站</span><span class="sxs-lookup"><span data-stu-id="2bc7d-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="2bc7d-115">在 Jamf Pro 的 macOS 裝置群組上設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bc7d-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="2bc7d-116">在 Jamf Pro 的 macOS 原則上設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bc7d-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="2bc7d-117">在 macOS 裝置上為 Jamf Pro 註冊 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bc7d-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




