---
title: 裝置名稱
description: Microsoft 受管理的電腦如何管理裝置名稱
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
# <a name="device-names"></a>裝置名稱

Microsoft 受管理的電腦會使用 Windows Autopilot、Azure Active Directory 及 Microsoft Intune。 為了讓這些服務能夠順利搭配合作，裝置需要一致且標準化的名稱。 Microsoft 受管理的電腦會在註冊裝置時套用格式為 *MMD-% RAND11* 的標準化名稱格式 () 。 WindowsAutopilot 會指派這些名稱。 如需 Autopilot 的詳細資訊，請參閱 [使用 Autopilot 的第一次執行體驗和註冊狀態頁面](../get-started/esp-first-run.md)。

## <a name="automated-name-changes"></a>自動化名稱變更

如果稍後重新命名裝置，Microsoft 受管理的電腦會以標準化格式自動將其重新命名為新的名稱。 此程式每四小時發生一次。 名稱變更會在使用者下一次重新開機裝置時進行。

> [!IMPORTANT]
> 如果您的環境取決於特定裝置名稱 (例如，若要支援特定網路設定) ，您應該調查選項，以移除該相依性，然後再註冊 Microsoft 受管理的電腦。 如果您必須保留名稱相依性，您可以透過系統 [管理入口網站](../working-with-managed-desktop/admin-support.md) 提交要求，以停用重新命名函式，並使用您想要的名稱格式。