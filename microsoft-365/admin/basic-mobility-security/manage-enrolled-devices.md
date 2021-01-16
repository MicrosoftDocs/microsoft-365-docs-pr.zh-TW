---
title: 在 Microsoft 365 中管理已登記行動裝置管理的裝置
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本行動性和安全性可協助您保護和管理行動裝置。
ms.openlocfilehash: 4954da0ff44276d9bd46cabc78bc52c7879e5e26
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876957"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>在 Microsoft 365 中管理已登記行動裝置管理的裝置

Microsoft 365 內建的行動裝置管理可協助您保護和管理使用者的行動裝置，例如 Iphone、Ipad、Androids 和 Windows phone。 第一步是登入 Microsoft 365，並設定基本行動性和安全性。 如需詳細資訊，請參閱 [設定基本行動性和安全性](set-up.md)。

完成設定之後，您組織中的人員必須在服務中註冊其裝置。 如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)。然後，您可以使用基本行動性和安全性來協助管理組織中的裝置。 例如，您可以使用裝置安全性原則來協助限制電子郵件存取或其他服務、查看裝置報告，以及遠端清除裝置。 您通常會進入安全性 & 合規性中心，以執行這些工作。 如需詳細資訊，請參閱 [Microsoft 365 規範中心](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)。

## <a name="device-management-tasks"></a>裝置管理工作

若要取得「裝置管理」面板，請遵循下列步驟：

1. 移至 [Microsoft 365 系統管理中心](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)。

2. 在 [搜尋] 欄位中輸入行動裝置管理，並從結果清單中選取 [行動 **裝置管理**]   。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="行動裝置管理選項":::

3. 選取 [  **讓我們開始** 吧！]。

## <a name="manage-mobile-devices"></a>管理行動裝置

在您掌握基本行動性和安全性後，您可以在以下幾種方式管理組織中的行動裝置。

|**以便進行下列動作**|**執行**|
|:----------------|:------------------------------------------------------------------------------|
|擦除裝置 |在 [裝置管理] 面板中，選取 [ *裝置名稱*]，然後選取 [  **完全擦除**]，   以刪除所有資訊或  **選擇性擦除**   ，只刪除裝置上的組織資訊。 如需詳細資訊，請參閱 [在基本行動及安全性中清除行動裝置](wipe-mobile-device.md)。|
|封鎖不支援的裝置使用 Exchange 來存取 Exchange 電子郵件 ActiveSync |在 [裝置管理] 面板中，選取 [  **封鎖**]。 |
|設定密碼需求和安全性設定等裝置原則 |在 [裝置管理] 面板中，選取 [**裝置安全性原則**] [   >  **新增 +**]。 如需詳細資訊，請參閱 [在基本行動性和安全性中建立裝置安全性原則](create-device-security-policies.md)。|
|查看封鎖的裝置清單  |在 [裝置管理] 面板的 [  **選取視圖**] 下，   選取 [  **封鎖**]。 |
|解除封鎖使用者或使用者群組不相容或不受支援的裝置  |選擇下列其中一個以解除封鎖裝置：<br/>-從套用原則的安全性群組中移除使用者。 移至 Microsoft 365 系統管理中心 > **群組**，然後選取 [組名]。 選取 [ **編輯成員和系統管理員**]。<br/>-從裝置原則中移除使用者所屬的安全性群組。 移至安全性 & 規範中心 > **安全性原則**   >  **裝置安全性原則**。 選取 [裝置原則名稱]，然後選取 [**編輯**  >  **部署**]。<br/>-取消封鎖裝置原則的所有不相容裝置。 移至安全性 & 規範中心 > **安全性原則**   >  **裝置安全性原則**。 選取 [裝置原則名稱]，然後選取 [**編輯**  >  **存取權要求**]。 選取 [  **允許存取和舉報違規**]。<br/>-若要解除封鎖使用者或使用者群組的不相容或不受支援的裝置，請移至安全性 & 合規性中心 > **安全性原則**   >  **裝置管理**   >  **管理裝置存取設定**。 新增包含您要排除的成員，以封鎖對 Microsoft 365 的存取權的安全性群組。 如需詳細資訊，請參閱 [Create、edit 或 delete a security group In Microsoft 365 admin center](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)。|
|移除使用者，使其裝置不再由基本行動性和安全性管理 |若要移除使用者，請編輯具有裝置管理原則的安全性群組，以取得基本行動性和安全性。 如需詳細資訊，請參閱  [Create、edit 或 delete a security group In Microsoft 365 admin center](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)。<br/>若要從您的所有 Microsoft 365 使用者移除基本行動性和安全性，請參閱 [關閉基本行動性和安全性](turn-off.md)。|

Live (v14) 