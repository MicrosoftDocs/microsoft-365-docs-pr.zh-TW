---
title: 裝置清單 CSV 檔案
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 了解如何讓 AutoPilo 錫 Microsoft 365 商務版的 CSV 檔案。
ms.openlocfilehash: 56d8fb234a1b526192468309c93c638694b92c6e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361354"
---
# <a name="device-list-csv-file"></a>裝置清單 CSV 檔案

## <a name="device-list-csv-file-format"></a>裝置清單的.csv 檔案格式

若要管理及部署透過 Windows Autopilot 裝置，您需要包含之裝置的特定資訊的.csv 檔案。
  
在裝置清單檔案中的欄必須具備下列標頭中指定的順序：
  
- 欄 A：裝置序號

- 欄 B:WINDOWS 保留空白

- 欄 C：硬體雜湊

您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。 

當您新增裝置時，您也需要將它們新增至設定檔。 設定檔用來將 AutoPilot 部署設定檔套用到單一裝置或一組裝置。
  
## <a name="related-articles"></a>相關文章

[Microsoft 365 商務版文件和資源](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[開始使用 Microsoft 365 商務版](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[管理 Microsoft 365 商務版](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
