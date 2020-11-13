---
title: 讓合作夥伴註冊裝置的步驟
description: 合作夥伴如何註冊裝置，以便由 Microsoft 受管理的電腦來管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071440"
---
# <a name="steps-for-partners-to-register-devices"></a>讓合作夥伴註冊裝置的步驟


本主題說明可讓合作夥伴遵循的步驟來註冊裝置。 您自行註冊裝置的程式會記錄在 [Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。



## <a name="prepare-for-registration"></a>準備註冊 
在完成客戶的註冊之前，您必須先在 [夥伴中心](https://partner.microsoft.com/dashboard)建立與他們的關聯。 如需該程式的詳細資訊，請參閱 [同意檔](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 。 任何 CSP 合作夥伴只要客戶 consents，即可代表任何客戶新增裝置。 您也可以在 [夥伴中心協助](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)深入瞭解合作夥伴關係和 Autopilot 許可權。


> [!NOTE]
> 本檔僅供合作夥伴和 Oem 用。 自行註冊的程式會記錄在 [Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。


## <a name="register-devices-by-using-partner-center"></a>使用夥伴中心註冊裝置

當您建立與客戶的關聯之後，您可以遵循下列步驟，利用合作夥伴中心新增裝置，針對您具有關聯性的任何客戶 Autopilot：

1. 流覽至 [[合作夥伴中心](https://partner.microsoft.com/dashboard)]
2. 從 [合作夥伴中心] 功能表選取 [ **客戶** ]，然後選取您想要管理其裝置的客戶。
3. 在客戶的詳細資料頁面上，選取 [ **裝置** ]。
4. 在 [ **將設定檔** 套用至裝置] 底下，選取 [ **新增裝置** ]。
5. 輸入組名的 **Microsoft365Managed_Autopilot** ，然後選取 **[流覽]** ，將客戶的清單 (以 .csv 檔案格式上傳) 至 [夥伴中心]。


> [!IMPORTANT]
> 群組名稱必須完全符合 **Microsoft365Managed_Autopilot** ，包括大小寫和特殊字元。 這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。

>[!NOTE]
> 您應該會收到此 .csv 檔案與您的裝置購買。 如果您未收到 .csv 檔案，您可以遵循 [新增裝置至 Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)中的步驟，自行建立。 Windows PowerShell 腳本與 [Microsoft Managed Desktop Admin 入口網站](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)所使用的腳本不同。 協力廠商應該使用 [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 在夥伴中心中為 Microsoft 受管理的桌面裝置註冊裝置。

如果您在嘗試上傳 .csv 檔案時收到錯誤訊息，請檢查檔案的格式。 請確定欄順序符合在 [新裝置上使用 Windows Autopilot 設定檔中所述的資料，以自訂客戶的現成體驗](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)。 您也可以使用 [ **新增裝置** ] 旁邊的連結所提供的範例 .csv 檔案，以建立裝置清單。 

如需 Autopilot 在合作夥伴案例中的詳細資訊，請參閱 [將裝置新增至客戶的帳戶](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)。


## <a name="register-devices-by-using-the-oem-api"></a>使用 OEM API 註冊裝置

在完成客戶的註冊之前，您必須先與其建立關聯。 您應該有一個唯一的連結，可提供給您的各個客戶。 請參閱 [如何建立 OEM 關聯](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

建立關聯之後，您可以開始使用群組標籤 **Microsoft365Managed_Autopilot** 為客戶註冊裝置。

> [!IMPORTANT]
> 群組名稱必須完全符合 **Microsoft365Managed_Autopilot** ，包括大小寫和特殊字元。 這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。
