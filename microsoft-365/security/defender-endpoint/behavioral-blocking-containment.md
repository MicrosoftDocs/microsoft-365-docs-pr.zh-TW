---
title: 行為封鎖和包含專案
description: 深入瞭解 Microsoft Defender for Endpoint 中的行為封鎖和包容功能
keywords: Microsoft Defender for Endpoint，EDR 以封鎖模式，被動模式封鎖
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: a6271c1bd3714cfdffc606b7ada9b027e394216d
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866724"
---
# <a name="behavioral-blocking-and-containment"></a>行為封鎖和包含專案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>概觀

目前的威脅環境會因 [fileless 惡意](/windows/security/threat-protection/intelligence/fileless-threats) 代碼而溢出，但離土地的高多態威脅，隨著傳統解決方案的變化速度，可持續保持和人工運作的攻擊，以適應敵人在受損的裝置上找到的內容。 傳統的安全性解決方案不足以停止這類攻擊;您需要 (AI) 和裝置學習 (ML) 備份的功能（例如行為封鎖及包容）包含在[Defender for Endpoint](/windows/security)中。 

行為封鎖和包容功能可在威脅已開始執行時，根據其行為和程式樹，協助識別及停止威脅。 下一代保護、EDR 和 Defender 用於端點元件和功能，可搭配行為封鎖和包容功能一起運作。 

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="行為封鎖和包含專案":::

行為封鎖和包容功能可與使用的 Defender 的多個元件和功能搭配使用，以立即停止攻擊，並防止攻擊的進展。

- [下一代保護](microsoft-defender-antivirus-in-windows-10.md) (包括 Microsoft Defender 防毒軟體) 可透過分析行為來偵測威脅，以及停止已開始執行的威脅。

- [端點偵測和回應](overview-endpoint-detection-response.md) (EDR) 接收網路、裝置和內核行為間的安全性信號。 當偵測到威脅時，即會建立警示。 相同類型的多個警示會匯總到事件中，這可讓安全性作業小組更輕鬆地調查和回應。

- 除了透過 EDR 所收到的網路、端點和內核行為信號之外，該[端點的 Defender](overview-endpoint-detection-response.md)都具有各種身分識別、電子郵件、資料和應用程式的光纖。 [Microsoft 365 的 defender](../defender/microsoft-365-defender.md)、端點的 defender 的元件，以及與這些信號關聯的元件、引發偵測警示，以及連接事件中的相關警示。

使用這些功能時，即使已開始執行，也可以阻止或封鎖更多威脅。 每當偵測到可疑行為時，就會包含威脅、建立警示，並在其蹤跡中停止威脅。 

下圖顯示由行為封鎖及包容功能所觸發之警示的範例：

:::image type="content" source="images/blocked-behav-alert.png" alt-text="透過行為封鎖和包含的警示範例":::

## <a name="components-of-behavioral-blocking-and-containment"></a>行為封鎖及包容元件

- **用戶端、原則導向的 [攻擊面降低規則](attack-surface-reduction.md)** 預先定義的常見攻擊行為會因攻擊面減少規則而無法執行。 當這類行為企圖執行時，這些行為會在 Microsoft Defender 資訊安全中心中看作是 [https://securitycenter.windows.com](https://securitycenter.windows.com) 資訊性警示。 預設不會啟用 (攻擊面降低規則;您可以在 Microsoft Defender 資訊安全中心中設定原則。 ) 

- **[用戶端行為封鎖](client-behavioral-blocking.md)** 會透過機器學習來偵測端點的威脅，然後自動封鎖並修正。 預設會啟用用戶端行為封鎖 (。 )  

- 反應反應 **[-環路封鎖](feedback-loop-blocking.md)** (也稱為快速防護) 威脅偵測透過行為情報加以觀察。 威脅已停止，無法在其他端點上執行。  (反應-迴圈封鎖預設為啟用。 )  

- **[在封鎖模式中) 的端點偵測和回應 (EDR](edr-in-block-mode.md)** 會封鎖並包含透過破壞性保護所觀測到的惡意專案或行為。 即使 Microsoft Defender 防毒軟體不是主要的防病毒解決方案，封鎖模式中的 EDR 仍可運作。 預設不會啟用封鎖模式中的 (EDR;您可以在 Microsoft Defender 資訊安全中心中將其開啟。 )  

預期會有更多的行為封鎖和包容領域，因為 Microsoft 會繼續改進威脅防護的功能和功能。 若要查看現在已計畫及推出的專案，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>動作中的行為封鎖及包容範例

行為封鎖和包容功能已封鎖攻擊者的技術，如下所示：

- 從 LSASS 轉儲憑證
- 跨進程注入
- 處理 hollowing
- 使用者帳戶控制旁路
- 篡改防病毒 (，例如停用它或將惡意程式碼新增為排除) 
- 聯繫我們命令和控制項 (C&C) 下載有效載荷
- 硬幣挖掘
- 修改開機記錄
- 傳遞-雜湊攻擊
- 安裝根憑證
- 各種漏洞的攻擊嘗試

以下是兩個實際行為封鎖和包含在動作中的範例。

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>範例1：針對100組織的認證盜竊攻擊

如 [elusive 威脅的熱實施中所述：以 AI 為導向的行為基礎的封鎖會在其追蹤中停止攻擊](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)。由於行為封鎖及包容能力，對全球各地的100組織所進行的認證盜竊攻擊已停止。 Spear-包含引誘檔的網路釣魚電子郵件會傳送給目標群組織。 如果收件者開啟附件，則相關的遠端檔能夠在使用者的裝置上執行程式碼，並載入 Lokibot 惡意程式碼，這會 stole 認證、挾帶竊取的資料，並等候來自命令和控制伺服器的進一步指示。 

Defender for Endpoint 中的行為基礎裝置教學模型，在攻擊鏈中的兩個點上捕捉及停止攻擊者的技術：

- 第一個保護層偵測到利用行為行為。 雲端中的裝置學習分類器已正確識別威脅，並立即指示用戶端裝置封鎖攻擊。
- 第二個保護層，可協助停止攻擊超過第一層的情況、偵測到的處理常式 hollowing、停止該處理常式，並移除對應的檔案 (例如 Lokibot) 。 

偵測並停止攻擊時，系統會觸發及顯示「初始存取警示」等警示，以) Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com) ：

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Microsoft Defender 資訊安全中心中的初始訪問警示":::

此範例會顯示雲端中的行為基礎裝置教學模型如何在攻擊開始執行之後，新增防護的新層。

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>範例2： NTLM 轉送 Juicy 薯片惡意程式碼變種

如近期的博客文章中所述， [行為封鎖和包容：將光學器件轉換成保護](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)，在2020年1月，該端點的 Defender 已偵測到組織中裝置上的許可權提升活動。 觸發稱為「使用 NTLM 轉送可能的許可權提升」的警示。

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="Juicy 薯片惡意程式碼的 NTLM 警示":::

威脅已變成惡意程式碼;它是一種稱為「Juicy 薯片」之 notorious 駭客工具的新功能之前的變種，它是被攻擊者在裝置上取得許可權提升所用的。 

觸發警示之後的分鐘數，會分析檔案，並確認是否有惡意。 其進程已停止並封鎖，如下圖所示：

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="封鎖專案":::

在專案遭到封鎖之後的幾分鐘內，相同檔案的多個實例會在相同的裝置上封鎖，以防其他攻擊者或其他惡意程式碼無法在裝置上部署。 

本範例顯示使用行為封鎖和包容功能，會自動偵測、包含並封鎖威脅。 

## <a name="next-steps"></a>後續步驟

- [深入瞭解端點的 Defender](overview-endpoint-detection-response.md)

- [設定攻擊面減少規則](attack-surface-reduction.md)

- [在封鎖模式中啟用 EDR](edr-in-block-mode.md)

- [查看最近的全域威脅活動](https://www.microsoft.com/wdsi/threats)

- [取得 Microsoft 365 Defender 的概覽](../defender/microsoft-365-defender.md)
