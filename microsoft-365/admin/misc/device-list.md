---
title: 裝置清單 CSV-檔案
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 瞭解如何為商務 Microsoft 365 中的 AutoPilot 建立 CSV 檔案。
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579215"
---
# <a name="device-list-csv-file"></a>裝置清單 CSV-檔案

## <a name="device-list-csv-file-format"></a>裝置清單 .csv 檔案格式

若要透過 Windows Autopilot 管理及部署裝置，您需要包含裝置特定資訊的 .csv 檔案。
  
裝置清單檔案中的欄必須以指定的順序排列下列標頭：
  
- 欄 A：裝置序號

- 欄 B：保留空白

- 欄 C：硬體雜湊

您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。 

當您新增裝置時，您也需要將裝置新增至設定檔。 設定檔是用來將 AutoPilot 部署設定檔套用至裝置或裝置群組。
  
## <a name="related-articles"></a>相關文章

[商務檔和資源的 Microsoft 365](../../business/index.yml)
  
[開始使用商務 Microsoft 365](../../business/microsoft-365-business-overview.md)
  
[管理商務 Microsoft 365](../../business/manage.md)
