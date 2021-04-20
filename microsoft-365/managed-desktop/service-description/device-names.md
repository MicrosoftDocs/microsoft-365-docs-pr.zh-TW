---
title: 裝置名稱
description: Microsoft Managed Desktop 如何管理裝置名稱
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
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893775"
---
# <a name="device-names"></a><span data-ttu-id="cdf69-103">裝置名稱</span><span class="sxs-lookup"><span data-stu-id="cdf69-103">Device names</span></span>

<span data-ttu-id="cdf69-104">Microsoft 受管理的桌面使用 Windows Autopilot、Azure Active Directory 和 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="cdf69-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="cdf69-105">為了讓這些服務能夠順利搭配合作，裝置需要一致且標準化的名稱。</span><span class="sxs-lookup"><span data-stu-id="cdf69-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="cdf69-106">Microsoft Managed Desktop 會在註冊裝置時，套用 *MMD-% RAND11*) 的標準化名稱格式 (。</span><span class="sxs-lookup"><span data-stu-id="cdf69-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="cdf69-107">Windows Autopilot 會指派這些名稱。</span><span class="sxs-lookup"><span data-stu-id="cdf69-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="cdf69-108">如需 Autopilot 的詳細資訊，請參閱 [使用 Autopilot 的第一次執行體驗和註冊狀態頁面](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="cdf69-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="cdf69-109">自動化名稱變更</span><span class="sxs-lookup"><span data-stu-id="cdf69-109">Automated name changes</span></span>

<span data-ttu-id="cdf69-110">如果重新命名裝置，則 Microsoft Managed Desktop 會自動將其重新命名為標準化格式的新名稱。</span><span class="sxs-lookup"><span data-stu-id="cdf69-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="cdf69-111">此程式每四小時發生一次。</span><span class="sxs-lookup"><span data-stu-id="cdf69-111">This process occurs every four hours.</span></span> <span data-ttu-id="cdf69-112">名稱變更會在使用者下一次重新開機裝置時進行。</span><span class="sxs-lookup"><span data-stu-id="cdf69-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdf69-113">如果您的環境取決於特定的裝置名稱 (例如，若要支援特定網路設定) ，您應該調查選項，以移除該相依性，然後在 Microsoft 受管理的電腦中進行註冊。</span><span class="sxs-lookup"><span data-stu-id="cdf69-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="cdf69-114">如果您必須保留名稱相依性，您可以透過系統 [管理入口網站](../working-with-managed-desktop/admin-support.md) 提交要求，以停用重新命名函式，並使用您想要的名稱格式。</span><span class="sxs-lookup"><span data-stu-id="cdf69-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>