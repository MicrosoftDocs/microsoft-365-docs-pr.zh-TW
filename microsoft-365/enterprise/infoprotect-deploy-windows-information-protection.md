---
title: 步驟 4： 設定 Windows 資訊保護
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Microsoft 365 中的 Windows 資訊保護並且進行部署。
ms.openlocfilehash: ca706d49053bbc100a633afb74c7c978de2e4c5c
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353097"
---
# <a name="step-4-configure-windows-information-protection"></a>步驟 4： 設定 Windows 資訊保護

此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本**

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

當更多的個人裝置用於工作時，應用程式和裝置外洩組織私密資料的風險就會增加。 例如，有員工不經意地將未來產品行銷計劃的圖片傳送到社交媒體網站，或者將包含高度機密資訊的檔案儲存到他們的公用雲端儲存區。 

Windows 資訊保護 (WIP) 可協助保護 Windows 10 裝置上的此類資料外洩。 如需詳細資訊，請參閱[使用 WIP 保護您的企業資料](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) (機器翻譯)。

在 Microsoft 365 企業版中，WIP 是 Windows 10 企業版和 Microsoft Intune 的組合，隨附於您的訂閱中的 Enterprise Mobility + Security (EMS)。 

若要在貴組織中使用 Microsoft 365 企業版部署 WIP：

1. 在 Intune 中註冊您的 Windows 裝置。 您應該在[階段 5：行動裝置管理](mobility-infrastructure.md)中完成這項作業。
2. 建立[適用於 WIP 的 Intune 原則](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure) (機器翻譯)。
  - 請確定您已填寫受保護的應用程式清單。
  - 選擇您的 WIP 保護等級。

您也可以搭配 [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm) (機器翻譯) 使用 WIP。 

如需詳細資訊，請參閱 [WIP 最佳做法]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) (機器翻譯)。

作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step4)。

## <a name="next-step"></a>下一步


|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[設定 Office 365 資料外洩防護](infoprotect-data-loss-prevention.md)|


