---
title: Contoso 的行動裝置管理
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 如何在 Microsoft 365 企業版中使用 Microsoft Intune，來管理裝置和在裝置上執行的應用程式。
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068362"
---
# <a name="mobile-device-management-for-contoso"></a>Contoso 的行動裝置管理

Microsoft 365 企業版包含 Intune 和一組 Azure 服務，可支援行動裝置和應用程式管理與安全性。

Contoso 有許多使用行動裝置的員工，有些在 Contoso 所在地有辦公室，有些則沒有。Contoso 需要能夠讓員工具備生產力，但保持裝置、儲存在裝置上的 Contoso 公司資料及應用程式行為安全的方法。

## <a name="plan"></a>計劃

在早期為 Microsoft 365 企業版分析行動裝置管理中，Contoso 識別出下列 Intune 使用案例：

- 保護 Exchange Online 的電子郵件和資料，讓其可以透過行動裝置安全地存取
- 為 Contoso 員工實施「帶您自己的裝置」(BYOD) 活動
- 分配公司手機和受限的共用平板電腦給 Contoso 員工

Contoso 不會使用 Intune 來：

- 讓員工從未受管理的公用 Kiosk 安全地存取 Office 365
- 由於不再有內部部署 Microsoft Exchange 伺服器，因此用以保護內部部署上的電子郵件和資料，讓其可以由行動裝置安全地存取。

## <a name="deploy"></a>部署

這是 Contoso 設定行動裝置管理基礎架構的方式：

- 將 Intune 設定為行動裝置管理 (MDM) 的授權單位，並在 Azure 上使用 Intune 管理內容及裝置
- 建立適用於裝置的 Azure AD 群組以進行註冊，並且使用 Intune 設定及以裝置為基礎的條件式存取原則

  如需詳細資訊，請參閱 [Contoso 的條件式存取原則](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。

- 啟用 Apple 裝置平台以支援員工使用 iPad、iMac、iPhone 及 iPhone 式公司手機
- 建立 Contoso 特定的條款與條件原則，會在行動裝置安裝 Contoso 公司入口網站時出現
- 對於未註冊的裝置，則需要一組 Mobile Application Management (MAM) 原則才能授權存取 Office 365 服務
- 建立 Intune 原則以強制執行：
  - 允許的應用程式
  - 裝置加密以防止未經授權的存取
  - 六位數 PIN 或密碼
  - 閒置等待逾時時間
  - Windows 10 裝置上的防毒軟體與惡意程式碼防護，以及 Windows Defender 的簽章更新
  - 自動更新 Windows 10 裝置，以包含最新的安全性更新
  - 推送憑證至受管理的裝置
  - 清楚分隔商務和個人資料。使用者或系統管理員可以選擇性地從裝置清除公司資料，而不影響個人資料，例如圖片、個人電子郵件帳戶及個人檔案。

一旦部署，Contoso 可透過新增至適當的 Intune 裝置群組註冊電腦及公司智慧型手機和平板電腦，以及推出 BYOD 計畫來讓員工註冊個人裝置。註冊的裝置將會收到 Intune 原則，將裝置和其應用程式納入管理及安全性保護。未註冊的裝置則會使用 Mobile Application Management (MAM) 原則指定允許的應用程式。

以下是 Contoso 的行動裝置管理部署架構。

![Contoso 的行動裝置管理部署基礎結構](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>下一步

[深入了解](contoso-info-protect.md) Contoso 如何使用 Microsoft 365 企業版的資訊保護功能，分類、識別及保護組織中的重要數位資產。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版的行動裝置管理](mobility-infrastructure.md)

[部署指南](deploy-microsoft-365-enterprise.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)

