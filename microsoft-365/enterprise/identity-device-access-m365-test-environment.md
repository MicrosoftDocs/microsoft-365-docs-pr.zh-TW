---
title: 您的 Microsoft 365 測試環境的身分識別與裝置存取
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
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境以測試身分識別與裝置存取。
ms.openlocfilehash: ed143341079a55d6bdd1d4a68feea68acb86ef85
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233725"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>您的 Microsoft 365 測試環境的身分識別與裝置存取

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

身分[識別與裝置存取](../security/office-365-security/microsoft-365-policies-configurations.md)設定是一組建議的設定和條件式存取原則，可保護對與 Azure Active Directory (azure AD) 整合的所有服務的存取。

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

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
