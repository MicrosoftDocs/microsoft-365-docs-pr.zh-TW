---
title: 如何報告誤判或漏報中產生 Microsoft 威脅防護中
description: 某個項目已未接或錯誤偵測到的空調中 Microsoft 威脅防護？ 了解如何提交誤判或 false 的負號給 Microsoft 進行分析。
keywords: 自動化，調查、 提醒、 觸發程序、 動作、 修復、 正數，則為 false 誤判
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d9175e78326832a2be874359babae5ae9c689420
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600080"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何報告中自動進行調查並回應功能，則為 false positive/負號

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

未[自動的調查及回應功能](mtp-autoir.md)Microsoft 威脅防護中遺漏或錯誤偵測到某個嗎？ 您可以向 Microsoft 報告，或調整您的通知 （如果需要）。 做為指南，請使用下表： 


|項目  |所偵測到  |如何將其報告  |
|---------|---------|---------|
|電子郵件訊息 <br/>電子郵件附件 <br/>在 [電子郵件訊息或 Office 檔案的 URL      |[Office 365 進階威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[送出可疑的垃圾郵件、 釣魚程式、 Url 和 microsoft Office 365 掃描的檔案](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|檔案或裝置上的應用程式    |[Windows Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection)         |[提交給 Microsoft 進行惡意程式碼分析的檔案](https://www.microsoft.com/wdsi/filesubmission)         |
|合法的使用由觸發警示 <br/>不精準的警示    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> 或 <br/>[Azure 的進階的威脅偵測](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[管理提醒在 Cloud App Security 入口網站](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a>後續步驟

- [與自動化調查及回應相關的核准或拒絕動作](mtp-autoir-actions.md)
- [深入了解重要訊息中心](mtp-action-center.md)
- [使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅](advanced-hunting-overview.md)
