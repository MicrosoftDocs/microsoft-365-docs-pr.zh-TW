---
title: 整合 Office 365 進階的威脅防護與 Microsoft Defender 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: 整合 Microsoft Defender 進階威脅防護來威脅管理的詳細的資訊請參閱 < Office 365 進階威脅防護。
ms.openlocfilehash: a4e96615cf0f132a43957a5885b5fb33a5e8f031
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076826"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>整合 Office 365 進階的威脅防護與 Microsoft Defender 進階威脅防護

如果您是貴組織的安全性小組的一部分，您可以將[Office 365 進階威脅防護](office-365-atp.md)和相關的調查和回應功能整合與[Microsoft Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。 這可協助您快速了解您正在調查 Office 365 中的威脅時是否使用者的電腦是否處於風險。 例如，一旦啟用整合，您將能夠查看機器所使用的郵件收件者偵測到的電子郵件，以及如何在 Microsoft Defender 進階威脅防護中的許多最近的通知這些機器有。
  
下圖顯示 [**裝置**] 索引標籤，您會看到已啟用 Microsoft Defender ATP 整合的時機：
  
![啟用 Microsoft Defender ATP 時，您可以看到機器警示的清單。](../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
在這個範例中，您可以看到電子郵件的收件者有四種裝置，以及其他有警示。 按一下 [裝置] 連結會開啟其 Microsoft defender 資訊安全中心。
  
## <a name="requirements"></a>需求

- 您的組織必須有 Office 365 ATP 計劃 2 （或 Office 365 E5） 和 Microsoft Defender ATP。
    
- 您必須是 Office 365 全域管理員或具有安全性系統管理員角色 （例如安全性管理員） 中指派[安全性&amp;合規性中心](https://protection.office.com)。 (請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md))
    
- 您必須擁有存取權這兩個[檔案總管] （或即時偵測的資訊）](threat-explorer.md)中的安全性 & 規範中心和 Microsoft defender 資訊安全中心。
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>若要將 Microsoft Defender ATP 與整合 Office 365 ATP

整合 Office 365 ATP 與 Microsoft Defender ATP 會設定使用安全 & 與規範中心和 Microsoft defender 資訊安全中心。
  
1. 為 Office 365 全域系統管理員或安全性系統管理員，請移至[https://protection.office.com](https://protection.office.com)並以 Office 365 您公司或學校帳戶登入。
    
2. 選擇 [**威脅管理** \> **總管**。<br>![威脅管理] 功能表中的 explorer](../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 在螢幕的右上角，選擇 [ **WDATP 設定**。
    
4. 在 [Windows Defender ATP 連線] 對話方塊中，開啟連線到 Windows ATP。<br>![Microsoft Defender ATP 連線](../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. 啟用 Microsoft defender 資訊安全中心中的連線。

  
## <a name="related-topics"></a>相關主題

[Office 365 威脅調查及回應](office-365-ti.md)
  
[Office 365 進階威脅防護](office-365-atp.md)
  

