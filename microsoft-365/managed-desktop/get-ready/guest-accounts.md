---
title: 來賓帳戶的先決條件
description: 來賓帳戶的設定指導方針及其調整方式
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694242"
---
# <a name="prerequisites-for-guest-accounts"></a>來賓帳戶的先決條件

Microsoft 受管理的電腦需要在您的 Azure AD 組織中具備下列設定，以供來賓帳戶存取使用。 您可以在 [外部身分識別 **/外部協同作業設定**] 底下的 [Azure 入口網站](https://portal.azure.com)調整這些設定：

-   若要將 **來賓邀請限制** 設定為 **成員使用者，並將指派給特定系統管理員角色的使用者，可邀請來賓使用者（包括具有成員許可權的來賓**）
-   針對共同作業 **限制**，選擇下列其中一個選項：
    -   如果您選取 [ **允許將邀請傳送至任何網域 (最包含)**]，則不需要其他設定。
    -   如果您選取 **[拒絕指定的網域邀請**]，請確定 Microsoft.com 未列在目標網域中。
    -   如果您選取 **[只對指定的網域允許邀請] (最嚴格的)**，請 *確定 Microsoft.com 列* 在目標網域中。

如果您設定的限制與這些設定互動，請務必排除 Azure Active Directory 新式的 **Workplace Service 帳戶**。 例如，如果您有一個條件式存取原則，可防止來賓帳戶存取 Intune 入口網站，請從這個原則中排除 **新式的 Workplace Service 帳戶** 群組。

## <a name="steps-to-get-ready"></a>準備就緒的步驟

1. 檢閱 [Microsoft 受管理的電腦的先決條件](prerequisites.md)。
2. 使用[整備評估工具](readiness-assessment-tool.md)。
3.  (本文[的來賓帳戶先決條件](guest-accounts.md)) 
4. [Microsoft 受管理的電腦的網路設定](network.md)
5. [為 Microsoft 受管理的電腦準備認證和網路設定檔](certs-wifi-lan.md)
6. [為 Microsoft 受管理的電腦準備內部部署資源存取](authentication.md)
7. [Microsoft 受管理的電腦中的應用程式](apps.md)
8. [為 Microsoft 受管理的電腦準備對應磁碟機](mapped-drives.md)
9. [為 Microsoft 受管理的電腦準備列印資源](printing.md)
