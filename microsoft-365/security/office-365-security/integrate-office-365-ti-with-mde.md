---
title: 將 microsoft defender 用於 Office 365 搭配 microsoft defender for Endpoint 使用
f1.keywords:
- NOCSH
keywords: 整合，Microsoft defender，Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 使用 microsoft defender for Office 365 搭配 microsoft defender for Endpoint，以取得對您的裝置和電子郵件內容的威脅相關的詳細資訊。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d54e4ec40c636b8b3ea319e79cbad5005850952
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029260"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>將 microsoft defender 用於 Office 365 搭配 microsoft defender for Endpoint 使用

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[microsoft defender for Office 365](defender-for-office-365.md)可以設定為搭配[Microsoft defender for Endpoint](/windows/security/threat-protection)使用。

整合 microsoft defender for Office 365 與 microsoft defender for Endpoint 可協助您的安全性運作小組監視，並在使用者的裝置面臨危險時快速採取行動。 例如，啟用整合後，您的安全性作業小組將能夠查看偵測到的電子郵件訊息可能影響的裝置，以及為 Microsoft Defender for Endpoint 中的裝置產生多少最近的提醒。

下圖說明當您已啟用 Microsoft Defender 端點整合時，[ **裝置** ] 索引標籤的外觀。

![啟用 Microsoft Defender for Endpoint 時，您可以看到具有警示的裝置清單。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

在此範例中，您可以看到偵測到之電子郵件的收件者有四個裝置，一個有警示。 按一下裝置的連結會開啟其頁面[Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (先前是 Microsoft Defender security center) 。

> [!TIP]
> Microsoft 365 Defender 入口網站會取代 Microsoft Defender 資訊安全中心。 [在 Microsoft 365 Defender 中查看 Microsoft Defender For Endpoint](../defender/microsoft-365-security-center-mde.md)。

## <a name="requirements"></a>需求

- 您的組織必須具有 Microsoft defender Office 365 (或 Office 365 E5) 和 Microsoft defender for Endpoint。

- 您必須是全域系統管理員，或具有安全性系統管理員角色 (例如 Microsoft 365 中指派的安全性系統管理員) 。 如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-microsoft-365-security-center.md)。

- 您必須可以存取 [Explorer (或即時偵測) ](threat-explorer.md)。

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>若要將 microsoft defender 用於 Office 365 與 microsoft defender for Endpoint 整合

整合 microsoft defender for Office 365 搭配 microsoft defender for endpoint 是在 defender for endpoint 和 defender for Office 365 中設定。

1. 以全域管理員或安全性管理員為進行 <https://security.microsoft.com/threatexplorer> 。

2. 在功能窗格中，選擇 [ **電子郵件 & 協同** \> **瀏覽器**]。

3. 在 [ **Explorer** ] 頁面上，按一下螢幕右上角的 [ **MDE 設定**]。

4. 在出現的 [ **microsoft defender for endpoint connection** 浮出] 中，連線開啟) 上的 [microsoft **defender for endpoint** ] (![ 切換] ](../../media/scc-toggle-on.png) ，然後按一下 [關閉圖示] [ ![ ](../../media/m365-cc-sc-close-icon.png) **關閉**]。

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 連接":::

5. 回到功能窗格中，選擇 [**設定**]。 在 [**設定**] 頁面上，選擇 [**端點**]

6. 在開啟的 [ **端點** ] 頁面上，選擇 [ **高級功能**]。

7. 向下滾動至 **Office 365 威脅情報**]，然後在) 上 (切換開啟此介面 ![ ](../../media/scc-toggle-on.png) 。

   完成後，按一下 [ **儲存喜好** 設定]。

## <a name="related-articles"></a>相關文章

[Office 365 中的威脅調查和回應功能](office-365-ti.md)

[適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md)

[適用於端點的 Microsoft Defender](/windows/security/threat-protection)
