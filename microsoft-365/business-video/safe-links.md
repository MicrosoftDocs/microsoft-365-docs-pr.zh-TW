---
title: 管理安全連結
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何管理安全連結，以保護您的公司免受惡意網站的攻擊。
ms.openlocfilehash: 0f0cc6845f699ba5b05c30e21f876f4b4d47b6a6
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422240"
---
# <a name="manage-safe-links"></a>管理安全連結

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender for Office 365 （以前稱為 Microsoft 365 ATP 或「高級威脅防護」）可協助您在使用者按一下 Office app 中的連結時，防範惡意網站。

## <a name="try-it"></a>試試看吧！

1. 移至 [系統 [管理中心](https://admin.microsoft.com)]，然後選取 [ **安裝**]。
1. 向右下展開以 **提升高級威脅的防護**。 選取 [ **View**， **Manage**，然後 **ATP 安全連結**]。
1. 在 [ **適用于整個組織的原則**] 底下，選擇 [ **預設** 原則]，然後選取 [ **編輯** ] 圖示。
1. 輸入您要封鎖的 URL。
1. 選取 [ **使用 office 應用程式、office for iOS 和 Android 中的安全連結**];選取 [ **當使用者按一下安全連結時請勿追蹤**]，並選取 [ **不要讓使用者按一下 [安全連結至原始 URL**]。 如果您設定預設原則，這些可能已經被選取。 選取 [儲存]。
1. 在 [套用至特定收件者 **的原則**] 底下，選擇 [ **建議的安全連結規則**]，然後選取 [ **編輯** ] 圖示。
1. 選取 [ **設定**]，向下移動，輸入您不想要檢查的 URL，然後選取 [ **新增** ] 圖示。
1. 選取 [套用 **于**]，然後選取您的功能變數名稱。 選取您要套用規則的任何其他網域。 選取[新增 **]、[確定]**，然後按一下 [**儲存**]。

現在已設定 ATP 安全連結。 允許最多30分鐘的變更才會生效。

當使用者收到具有連結的電子郵件時，將會掃描連結。 如果連結是安全的，它們會是可按一下的。 不過，如果連結位於封鎖的清單中，使用者就會看到已封鎖的郵件。