---
title: 使用 Microsoft Defender 高級威脅防護整合 Office 365 高級威脅防護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
description: 使用 Microsoft Defender 高級威脅防護整合 Office 365 高級威脅防護，以查看更詳細的威脅管理資訊。
ms.openlocfilehash: e416d70baf7498b0163d5bd8aa8e923585a5e5a4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633806"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>使用 Microsoft Defender 高級威脅防護整合 Office 365 高級威脅防護

如果您是組織的安全性小組的一部分，您可以使用[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)來整合[Office 365 的高級威脅防護](office-365-atp.md)和相關的調查和回應功能。 這可協助您在調查 Office 365 中的威脅時，快速瞭解使用者的機器是否存在危險。 例如，啟用整合後，您將可以查看偵測到之電子郵件的收件者所使用的機器清單，以及這些電腦在 Microsoft Defender 高級威脅防護中的最近通知數目。
  
下圖顯示您在啟用 Microsoft Defender ATP 整合時所看到的 [**裝置**] 索引標籤：
  
![啟用 Microsoft Defender ATP 後，您可以看到具有警示的裝置清單。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
在此範例中，您可以看到電子郵件的收件者有四個裝置，一個包含警示。 按一下裝置的連結會在 Microsoft Defender 安全中心開啟其頁面。
  
## <a name="requirements"></a>需求

- 您的組織必須具有 Office 365 ATP Plan 2 （或 Office 365 E5）和 Microsoft Defender ATP。
    
- 您必須是全域系統管理員，或具有安全性與[ &amp;合規性中心](https://protection.office.com)中所指派的安全性系統管理員角色（例如安全性管理員）。 （請參閱[安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)）
    
- 您必須能夠在安全性 & 規範中心和 Microsoft Defender Security Center 中存取[瀏覽器（或即時偵測）](threat-explorer.md) 。
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>將 Office 365 ATP 與 Microsoft Defender ATP 整合

使用安全性 & 規範中心和 Microsoft Defender 安全性中心，將 Office 365 ATP 整合至 Microsoft Defender ATP。
  
1. 以全域管理員或安全性管理員的身分，移至[https://protection.office.com](https://protection.office.com)並登入您的公司或學校帳戶。
    
2. 選擇 [**威脅管理** \> **瀏覽器**]。<br>![威脅管理功能表中的 Explorer](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 在螢幕的右上角，選擇 [ **WDATP 設定**]。
    
4. 在 [Microsoft Defender ATP connection] 對話方塊中，開啟 **[連線到 WINDOWS ATP**]。<br>![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. 啟用 Microsoft Defender Security Center 中的連線（[https://securitycenter.windows.com](https://securitycenter.windows.com)）。

## <a name="related-topics"></a>相關主題

[Office 365 中的威脅調查和回應功能](office-365-ti.md)
  
[Office 365 進階威脅防護](office-365-atp.md)
  

