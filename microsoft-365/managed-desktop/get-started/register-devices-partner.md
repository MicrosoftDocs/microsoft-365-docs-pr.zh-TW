---
title: 讓合作夥伴註冊裝置的步驟
description: 合作夥伴如何註冊裝置，以便由 Microsoft 受管理的電腦來管理
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
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689230"
---
# <a name="steps-for-partners-to-register-devices"></a>讓合作夥伴註冊裝置的步驟


本文說明在註冊裝置時，可讓合作夥伴遵循的步驟。 您自行註冊裝置的程式會記錄在 [Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。



## <a name="prepare-for-registration"></a>準備註冊 
在完成客戶的註冊之前，您必須先在 [夥伴中心](https://partner.microsoft.com/dashboard)建立與他們的關聯。 如需該程式的詳細資訊，請參閱 [同意檔](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 。 任何 CSP 合作夥伴只要客戶 consents，即可代表任何客戶新增裝置。 您也可以在 [夥伴中心協助](/partner-center/customers_revoke_admin_privileges#windows-autopilot)深入瞭解合作夥伴關係和 Autopilot 許可權。


> [!NOTE]
> 本檔僅供合作夥伴和 Oem 用。 自行註冊的程式會記錄在 [Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。


## <a name="register-devices-by-using-partner-center"></a>使用夥伴中心註冊裝置

建立與客戶的關聯之後，您可以遵循下列步驟，使用 Partner Center 新增裝置，針對您具有關聯性的任何客戶 Autopilot：

1. 流覽至 [[合作夥伴中心](https://partner.microsoft.com/dashboard)]
2. 從 [合作夥伴中心] 功能表選取 [ **客戶** ]，然後選取您想要管理其裝置的客戶。
3. 在客戶的詳細資料頁面上，選取 [ **裝置**]。
4. 在 [ **將設定檔** 套用至裝置] 底下，選取 [ **新增裝置**]。
5. 針對您已選取的裝置設定檔輸入適當的群組標籤 (如下表所示) 然後選取 **[流覽]** ，將客戶的清單 (為 .csv 檔案格式) 至 [夥伴中心]。

|[裝置設定檔](../service-description/profiles.md)  |Group 標記  |
|---------|---------|
|敏感性資料     |**Microsoft365Managed \_ SensitiveData**    |
|Power user     | **Microsoft365Managed \_ PowerUser**          |
|標準版     | **Microsoft365Managed \_ 標準**        |

> [!IMPORTANT]
> 組名必須與表格中所列的內容完全相符，包括大小寫和特殊字元。 這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。

>[!NOTE]
> 您應該會收到此 .csv 檔案與您的裝置購買。 如果您未收到 .csv 檔案，您可以遵循 [新增裝置至 Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)中的步驟，自行建立。 Windows PowerShell 腳本與 [Microsoft Managed Desktop Admin 入口網站](./register-devices-self.md#obtain-the-hardware-hash)所使用的腳本不同。 協力廠商應該使用 [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 在夥伴中心中為 Microsoft 受管理的桌面裝置註冊裝置。

如果您在嘗試上傳 .csv 檔案時收到錯誤訊息，請檢查檔案的格式。 請確定欄順序符合在 [新裝置上使用 Windows Autopilot 設定檔中所述的資料，以自訂客戶的現成體驗](/partner-center/autopilot#add-devices-to-a-customers-account)。 您也可以使用 [ **新增裝置** ] 旁邊的連結所提供的範例 .csv 檔案，以建立裝置清單。 

如需 Autopilot 在合作夥伴案例中的詳細資訊，請參閱 [將裝置新增至客戶的帳戶](/partner-center/autopilot#add-devices-to-a-customers-account)。


## <a name="register-devices-by-using-the-oem-api"></a>使用 OEM API 註冊裝置

在完成客戶的註冊之前，您必須先與其建立關聯。 您應該有一個唯一的連結，可提供給您的各個客戶。 請參閱 [如何建立 OEM 關聯](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

建立關聯之後，您可以開始使用適當的群組標籤為客戶註冊裝置，以供每個選取的裝置設定檔使用：


|裝置設定檔  |Group 標記  |
|---------|---------|
|敏感性資料     | **Microsoft365Managed \_ SensitiveData**     |
|Power user     | **Microsoft365Managed \_ PowerUser**          |
|標準版     | **Microsoft365Managed \_ 標準**      |

> [!IMPORTANT]
> Group 標記必須與表格中所列的標籤完全相符，包括大小寫和特殊字元。 這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。