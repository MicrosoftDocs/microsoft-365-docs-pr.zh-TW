---
title: 位址裝置名稱相依性
description: 移除裝置名稱上的相依性或要求例外狀況
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 8c82acb5306e3add7c41fd4e6f7e313782d47574
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893779"
---
# <a name="address-device-name-dependency"></a><span data-ttu-id="41790-103">位址裝置名稱相依性</span><span class="sxs-lookup"><span data-stu-id="41790-103">Address device name dependency</span></span>

<span data-ttu-id="41790-104">Microsoft 受管理的桌面會在裝置註冊時套用標準化名稱格式，而且會在名稱稍後變更時自動重新命名裝置。</span><span class="sxs-lookup"><span data-stu-id="41790-104">Microsoft Managed Desktop applies a standardized name format when devices are enrolled and will automatically rename devices if the name is changed later.</span></span> <span data-ttu-id="41790-105">如需詳細資訊，請參閱 [裝置名稱](../service-description/device-names.md)。</span><span class="sxs-lookup"><span data-stu-id="41790-105">For more info, see [Device names](../service-description/device-names.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41790-106">如果您的環境取決於特定的裝置名稱 (例如，若要支援特定網路設定) ，您應該調查選項，以移除該相依性，然後在 Microsoft 受管理的電腦中進行註冊。</span><span class="sxs-lookup"><span data-stu-id="41790-106">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="41790-107">如果您必須保留名稱相依性，您可以透過系統 [管理入口網站](../working-with-managed-desktop/admin-support.md) 提交要求，以停用重新命名函式，並使用您想要的名稱格式。</span><span class="sxs-lookup"><span data-stu-id="41790-107">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>