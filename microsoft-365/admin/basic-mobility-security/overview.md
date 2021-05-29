---
title: Microsoft 365 的基本行動性及安全性概述
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
description: 使用基本行動及安全性設定裝置安全性原則和存取規則。
ms.openlocfilehash: 37be420a4b9499da3d1290b8b6a898b9fcb09c5b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706307"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Microsoft 365 的基本行動性及安全性概述

您可以使用基本行動性和安全性，在行動裝置連線至 Microsoft 365 組織時，管理並保護行動裝置。 行動裝置（例如 smartphone 和平板電腦），用來存取工作電子郵件、行事曆、連絡人及檔，可確保員工隨時隨地從任何地方完成工作。 所以很重要的一點是，當使用者使用裝置時，您可以協助保護組織的資訊。 您可以使用基本行動及安全性，設定裝置安全性原則和存取規則，以及在行動裝置遺失或遭盜時加以清除。

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本行動及安全性設定":::

## <a name="what-types-of-devices-can-you-manage"></a>您可以管理哪些類型的裝置？

您可以使用基本行動性和安全性來管理許多類型的行動裝置，例如 Windows Phone、Android、iPhone 及 iPad。 若要管理組織中人員所使用的行動裝置，每個人都必須有適當的 Microsoft 365 授權，而且其裝置必須以基本行動性和安全性進行註冊。

若要查看每種裝置類型所支援的基本行動性和安全性，請參閱 [基本行動性和安全性的功能](capabilities.md)。

## <a name="setup-steps-for-basic-mobility-and-security"></a>基本行動性和安全性的設定步驟

Microsoft 365 全域管理員必須完成下列步驟，以啟動及設定基本行動性和安全性。 如需詳細步驟，請遵循 [設定基本行動性和安全性](set-up.md)中的指導方針。 

以下是步驟的摘要：

**步驟1：** 依照  [設定基本行動性和安全性](set-up.md)中的步驟，啟用基本行動性和安全性。

**步驟2：** 例如，建立 APNs 憑證以管理 iOS 裝置，並新增網域名稱系統 (DNS) 的網域名稱系統，以支援 Windows 電話，以設定基本行動性及安全性。

**步驟3：** 建立裝置原則，並將其套用至使用者群組。 當您執行此動作時，您的使用者會在其裝置上取得註冊訊息，當他們完成註冊時，其裝置會受到您為其所設定的原則所限制。 如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)。 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全性和行動性原則設定":::

## <a name="device-management-tasks"></a>裝置管理工作

當您已設定基本行動性和安全性，且使用者已註冊其裝置後，您就可以管理裝置、封鎖存取或擦除裝置（如有必要）。 若要深入瞭解一些常見的裝置管理工作（包括完成工作的位置），請參閱[Manage Manage device In Mobile Device management for Microsoft 365](manage-enrolled-devices.md)。

## <a name="other-ways-to-manage-devices-and-apps"></a>其他管理裝置和應用程式的方法

如果您只需要行動電話應用程式管理 (MAM) （可能是因為人員在自己的裝置上更新工作專案），則 Intune 除了註冊及管理裝置之外，還提供另一個選項。 Intune 訂閱可讓您使用 Azure 入口網站來設定 MAM 原則，即使人員的裝置並未在 Intune 中註冊也是一樣。 如需詳細資訊，請參閱 [App protection 原則一覽](/mem/intune/apps/app-protection-policy)。

## <a name="related-content"></a>相關內容

[設定基本行動及安全性](set-up.md) (文章) \
[使用基本行動性和安全性](enroll-your-mobile-device.md) (文章) \ 中，註冊行動裝置
[在 Microsoft 365 (文章中管理已登記行動裝置管理的裝置](manage-enrolled-devices.md)) \
[取得由基本行動性及安全性 (文章) 所管理之裝置的詳細資料](get-details-about-managed-devices.md)