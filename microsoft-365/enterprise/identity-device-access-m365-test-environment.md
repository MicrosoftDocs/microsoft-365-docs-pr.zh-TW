---
title: 您的 Microsoft 365 測試環境的身分識別與裝置存取
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境以測試身分識別與裝置存取。
ms.openlocfilehash: b8e91a58bb6e1c00013b963c77151080a419b836
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398804"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>您的 Microsoft 365 測試環境的身分識別與裝置存取

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

身分[識別與裝置存取](../security/office-365-security/microsoft-365-policies-configurations.md)設定是一組功能和條件式存取原則，可保護與 Azure Active Directory (azure AD) 整合的所有服務存取權。

若要建立具備通用身分識別和裝置存取設定的測試環境：

1. 根據您所選擇的身分識別模型以及驗證方法，設定您的測試環境使其具備身分識別和安全性功能的先決條件：

  - [僅限雲端](cloud-only-prereqs-m365-test-environment.md)
  - [密碼雜湊同步處理 (PHS) ](phs-prereqs-m365-test-environment.md)
  - [傳遞驗證 (PTA)](pta-prereqs-m365-test-environment.md)

2. 使用 [通用身分識別和裝置存取原則](identity-access-policies.md) ，設定針對測試環境所設定的必要條件建立的原則，並探索及驗證身分識別及裝置的保護。

## <a name="see-also"></a>請參閱

[其他身分識別測試實驗室指南](m365-enterprise-test-lab-guides.md#identity)

[身分識別藍圖](identity-roadmap-microsoft-365.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[適用于企業的 Microsoft 365 檔](https://docs.microsoft.com/microsoft-365-enterprise/)
