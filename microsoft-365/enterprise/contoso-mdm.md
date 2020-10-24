---
title: Contoso 的行動裝置管理
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 瞭解 Contoso 如何在 Microsoft 365 for enterprise 中使用 Microsoft Intune 來管理其裝置和在其上執行的應用程式。
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753988"
---
# <a name="mobile-device-management-for-contoso"></a>Contoso 的行動裝置管理

適用于企業的 Microsoft 365 包括 Intune 和一組 Azure 服務，可支援行動裝置和應用程式管理及安全性。

Contoso 有許多啟用行動的員工。有些地方的辦事處位於 Contoso 位置，有些則沒有辦事處。Contoso 需要一種方式來啟用員工生產力，但保留裝置、儲存在這些裝置上的 Contoso 資料，以及應用程式行為的安全性。

## <a name="plan"></a>方案

Contoso 已針對企業版的行動裝置365管理，識別以下 Intune 使用案例：

- 保護 Exchange Online 電子郵件和資料，讓行動裝置可以安全地加以存取。
- 為 Contoso 員工實施隨 (的隨) 計畫。
- 發佈組織所擁有的電話，並將共用的平板電腦限制于 Contoso 員工。

Contoso 不使用 Intune 執行下列作業：

- 允許員工透過非管理的公用展臺安全地存取 Microsoft 365。
- 保護內部部署電子郵件和資料，讓行動裝置可以安全地存取它，因為內部部署 Microsoft Exchange 伺服器沒有任何內部部署。

## <a name="deploy"></a>部署

這是 Contoso 設定行動裝置管理基礎架構的方式：

- 將 Intune 設定為行動裝置管理 (MDM) 授權，並在 Azure 上使用 Intune 管理內容及管理裝置
- 針對註冊及 Intune 設定和裝置型條件式存取原則，建立裝置的 Azure Active Directory (Azure AD) 群組

  如需詳細資訊，請參閱 [Contoso 條件式存取原則](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。

- 已啟用 Apple 裝置平臺，以支援具有 Ipad、Imac、Iphone 及公司所有 Iphone 的員工。
- 建立 Contoso 特定的條款與條件原則，會在行動裝置安裝 Contoso 公司入口網站時出現
- 在未註冊的裝置中，會執行一組行動應用程式管理 (MAM) 原則，以要求對 Microsoft 365 服務的存取進行驗證
- 建立 Intune 原則以強制執行：
  - 允許的應用程式。
  - 裝置加密，以協助防止未經授權的存取。
  - 六位數的 PIN 碼或密碼。
  - 非使用中的超時期限。
  - 在 Windows 10 裝置上進行防病毒和惡意程式碼保護，以及 Windows Defender 的簽章更新。
  - 在 Windows 10 裝置上自動更新（包含最新的安全性更新）。
  - 將憑證推入受管理的裝置。
  - 清楚分隔商務和個人資料。使用者或系統管理員可以選擇性地從裝置清除公司資料，而不影響個人資料，例如圖片、個人電子郵件帳戶及個人檔案。

Contoso 註冊的電腦及公司所擁有的 smartphone 和平板電腦，方法是將其新增至適當的 Intune 裝置群組。 他們也建立了 BYOD 程式，讓員工註冊其個人裝置。 已註冊的裝置會收到 Intune 原則，這會產生受管理和安全裝置及其應用程式。 未註冊的裝置具有指定允許之應用程式的行動應用程式管理 (MAM) 原則。

以下是 Contoso mobile device management 部署架構。

![Contoso 行動裝置管理部署基礎結構](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>下一步

瞭解 Contoso 如何使用 Microsoft 365 for enterprise 的 [資訊保護功能](contoso-info-protect.md) ，在其整個組織中分類、識別及保護重要的數位資產。

## <a name="see-also"></a>請參閱

[Microsoft 365 裝置管理](device-management-roadmap-microsoft-365.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)

