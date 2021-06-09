---
title: 適用於端點的 Microsoft Defender 中的主機防火牆報告
description: 在 Microsoft 365 的安全性中心內主控及流覽防火牆報告。
keywords: windows defender，防火牆
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809252"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>適用於端點的 Microsoft Defender 中的主機防火牆報告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

如果您是系統管理員，您現在可以主控防火牆報表來[Microsoft 365 的安全性中心](https://security.microsoft.com)。 這項功能可讓您從集中位置查看 Windows 10 和 Windows 伺服器2019防火牆報告。 

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？ 

- 您必須執行 Windows 10 或 Windows 伺服器2019。
- 若要將板載裝置加入至 Microsoft Defender for Endpoint service，請參閱 [此處](onboard-configure.md)。 
- 為了讓 Microsoft 365 的安全性中心開始接收資料，您必須針對具有高級安全性的 Windows Defender 防火牆啟用 **審核事件**。 
    - [審核篩選平臺封包丟棄](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [審核篩選平臺連接](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- 使用群組原則物件編輯器、本機安全性原則或 auditpol.exe 命令來啟用這些事件。 如需詳細資訊，請參閱 [這裡](/windows/win32/fwp/auditing-and-logging)。 
    - 這兩個 PowerShell 命令為：
        - **auditpol/set/subcategory： "篩選平臺封包 Drop"/failure： enable** 
        - **auditpol/set/subcategory： "a 篩選平臺 Connection"/failure： enable** 

## <a name="the-process"></a>處理常式
> [!NOTE]
> 請務必遵循上述區段中的指示，並正確設定您的裝置，以進行早期預覽參與。

- 啟用事件後，Microsoft 365 的安全性中心會開始監控資料。
    - 遠端 IP、遠端埠、本機埠、本機 IP、電腦名稱稱、跨輸入和輸出連線的處理常式。
- 管理員現在可以[在這裡](https://security.microsoft.com/firewall)看到 Windows 主機防火牆活動。
    - 透過下載[自訂報表腳本](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)，以利用 Power BI 監視 Windows Defender 防火牆活動，可加速其他報告。 
    - 在反映資料之前，可能需要長達12小時。

## <a name="supported-scenarios"></a>支援的案例
Ring0 預覽期間支援下列案例。 

### <a name="firewall-reporting-in-security-center"></a>安全中心的防火牆報告

以下是幾個防火牆報告頁面的範例。 您可以在這裡找到輸入、輸出和應用程式活動的摘要。 您可以前往直接存取此頁面 https://security.microsoft.com/firewall 。 

> [!div class="mx-imgBorder"]
> ![主機防火牆報告頁面](\images\host-firewall-reporting-page.png)

您也可以移至 **報告**  >  **安全性報告**  >  **裝置** (區段) 位於 **防火牆封鎖的輸入** 連線卡的底部，即可存取這些報告。

### <a name="from-computers-with-a-blocked-connection-to-device"></a>從「已封鎖連線的電腦」到裝置

卡片支援互動式物件。 您可以按一下裝置名稱（會在新索引標籤 https://securitycenter.microsoft.com 中啟動）並直接前往 [ **裝置時程表** ] 索引標籤，以深入查看裝置的活動。 

> [!div class="mx-imgBorder"]
> ![具有封鎖連線的電腦](\images\firewall-reporting-blocked-connection.png)

您現在可以選取 [ **時程表** ] 索引標籤，它會提供與該裝置相關聯的事件清單。 

在查看窗格右上角的 [ **篩選** ] 按鈕上按一下滑鼠右鍵，選取您要的事件種類。 在此情況下，請選取 **防火牆事件** ，並將窗格篩選為防火牆事件。 

> [!div class="mx-imgBorder"]
> ![篩選按鈕](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>深入搜尋高級搜尋 (預覽重新整理) 

防火牆報告會透過按一下 [**開啟高級搜尋**] 按鈕，直接從卡片鑽孔到 **高級搜尋**。 將預先填入查詢。 

> [!div class="mx-imgBorder"]
> ![開啟 [高級搜尋] 按鈕](\images\firewall-reporting-advanced-hunting.png)

現在可以執行查詢，並可探索過去30天內所有相關的防火牆事件。 

如需其他報告或自訂變更，可將查詢匯出至 Power BI 以進行進一步分析。 您可以透過下載[自訂報表腳本](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)，使用 Power BI 監視 Windows Defender 防火牆活動，以加速自訂報告。 

 