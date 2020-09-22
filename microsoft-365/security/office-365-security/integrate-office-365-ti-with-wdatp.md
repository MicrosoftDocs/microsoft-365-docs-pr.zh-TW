---
title: 整合 Office 365 ATP 和 Microsoft Defender ATP
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201968"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>使用 Microsoft Defender 高級威脅防護整合 Office 365 高級威脅防護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 的高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (OFFICE 365 atp) 可以設定為搭配 [microsoft Defender 的 [高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection) ] (microsoft defender ATP) 。

將 Office 365 ATP 與 Microsoft Defender ATP 整合，可協助您的安全性運作小組監視並快速採取行動（如果使用者的裝置面臨危險）。 例如，啟用整合後，您的安全性作業小組將能夠查看偵測到的電子郵件訊息可能影響的裝置，以及這些裝置在 Microsoft Defender ATP 中的最近通知數目。 

下圖說明 [ **裝置** ] 索引標籤似乎已啟用 MICROSOFT Defender ATP 整合功能：
  
![啟用 Microsoft Defender ATP 後，您可以看到具有警示的裝置清單。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
在此範例中，您可以看到偵測到之電子郵件的收件者有四個裝置，一個有警示。 按一下裝置的連結會在 Microsoft Defender Security Center () 中開啟其頁面 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。

> [!TIP]
> **[深入瞭解 Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (也稱為 MICROSOFT defender ATP 入口網站。 ) 
  
## <a name="requirements"></a>需求

- 您的組織必須有 Office 365 ATP Plan 2 (或 Office 365 E5) 和 Microsoft Defender ATP。
    
- 您必須是全域系統管理員，或具有安全性系統管理員角色 (例如安全 [ &amp; 規範中心](https://protection.office.com)中所指派的安全性系統管理員) 。  (參閱 [安全性與 &amp; 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)) 
    
- 您必須能夠存取 [Explorer (或即時偵測) ](threat-explorer.md) 在安全性 & 規範中心和 Microsoft Defender Security center 中。
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>將 Office 365 ATP 與 Microsoft Defender ATP 整合

使用安全性 & 規範中心和 Microsoft Defender 安全性中心，將 Office 365 ATP 整合至 Microsoft Defender ATP。
  
1. 以全域管理員或安全性管理員為單位，請移至 [https://protection.office.com](https://protection.office.com) 並登入。  (這會帶您前往 Office 365 安全性 & 相容性中心。 ) 
    
2. 在功能窗格中，選擇 [**威脅管理**  >  **瀏覽器**]。<br>![威脅管理功能表中的 Explorer](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 在螢幕的右上角，選擇 [ **WDATP 設定**]。
    
4. 在 [Microsoft Defender ATP connection] 對話方塊中，開啟 **[連線到 WINDOWS ATP**]。<br>![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. 移至 Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 。

6. 在導覽列中，選擇 [ **設定**]。 然後，在 **[一般**] 下，選擇 [ **高級功能**]。

7. 向下滾動至 **Office 365 威脅情報**連線，然後開啟連線。<br/>![Office 365 威脅情報連接](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>相關文章

[Office 365 中的威脅調查和回應功能](office-365-ti.md)
  
[Office 365 進階威脅防護](office-365-atp.md)
  
[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection)
