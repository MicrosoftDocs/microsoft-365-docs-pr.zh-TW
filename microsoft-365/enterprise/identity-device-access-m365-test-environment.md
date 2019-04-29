---
title: 您的 Microsoft 365 測試環境的身分識別與裝置存取
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境以測試身分識別與裝置存取。
ms.openlocfilehash: 7004a46873e32f39ace672bd955147e2f13ee05d
ms.sourcegitcommit: 2f7791159b715790463c6ce4835fbd9c0b48c047
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2019
ms.locfileid: "33243055"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>您的 Microsoft 365 測試環境的身分識別與裝置存取

[身分識別與裝置存取組態](microsoft-365-policies-configurations.md)是一組功能和條件式存取原則，用來保護對與 Azure Active Directory (Azure AD) 整合之所有服務的存取，包括 Microsoft 365 企業版中的 Office 365 和 Enterprise Mobility + Security (EMS)。

若要建立具備這些原則的測試環境：

1. 根據您所選擇的身分識別模型以及驗證方法，設定您的測試環境使其具備身分識別和安全性功能的先決條件：

  - [僅限雲端](cloud-only-prereqs-m365-test-environment.md)
  - [密碼雜湊同步處理 (PHS)](phs-prereqs-m365-test-environment.md)
  - [傳遞驗證 (PTA)](pta-prereqs-m365-test-environment.md)

2. 使用[一般身分識別與裝置存取原則](identity-access-policies.md)來設定根據先決條件建置的原則，並測試身分識別與裝置的保護。

## <a name="see-also"></a>請參閱

[其他身分識別測試實驗室指南](m365-enterprise-test-lab-guides.md#identity)

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
