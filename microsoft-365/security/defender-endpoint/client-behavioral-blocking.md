---
title: 用戶端行為封鎖
description: 用戶端行為封鎖是 Microsoft Defender for Endpoint 中行為封鎖和包容功能的一部分
keywords: 行為封鎖，快速保護，用戶端行為，Microsoft Defender ATP，microsoft defender for endpoint
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
ms.openlocfilehash: 48929d0e2b0c932d37cb5d29783712d00b17117f
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904149"
---
# <a name="client-behavioral-blocking"></a>用戶端行為封鎖

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>概觀

用戶端行為封鎖是在 Defender for Endpoint 中的 [行為封鎖和包容功能](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) 的元件。 在裝置上偵測到可疑行為時 (也稱為「用戶端」或「端點」) 時，系統會自動封鎖、檢查和修正偽像 (（如檔案或應用程式) ）。 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="雲端和用戶端保護":::

搭配雲端保護時，防防毒保護的運作方式最佳。

## <a name="how-client-behavioral-blocking-works"></a>用戶端行為封鎖的運作方式

[Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 可以偵測可疑行為、惡意程式碼、fileless 及記憶體中的攻擊，以及裝置上的其他功能。 偵測到可疑行為時，Microsoft Defender 防毒程式會監視並將這些可疑行為及其程式樹傳送至雲端保護服務。 機器學習會區別惡意應用程式與在毫秒內的良好行為，以及分類每個專案。 在幾乎即時的情況下，只要有惡意的偽像，該專案就會在裝置上遭到封鎖。 

每當偵測到可疑行為時，就會產生 [警示](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) ，而且會在 Microsoft Defender 安全中心 () 中顯示 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。

用戶端行為封鎖是有效的，因為它不只是協助防止攻擊的啟動，它可協助停止已開始執行的攻擊。 而且，以反應反應 [封鎖](feedback-loop-blocking.md) (另一個功能封鎖和包含) 的功能，您的組織中的其他裝置都可以攻擊。

## <a name="behavior-based-detections"></a>以行為為基礎的偵測

行為架構的偵測會根據 [MITRE ATT&CK Matrix For Enterprise](https://attack.mitre.org/matrices/enterprise)來命名。 命名慣例有助於識別遭受惡意行為的攻擊階段：


|策略 |   偵測威脅名稱 |
|----|----|
|初始存取 | 行為： Win32/InitialAccess. *！ ml |
|執行  | 行為： Win32/執行。 *！ ml |
|堅持    | 行為： Win32/持久化。 *！ ml |
|許可權提升   | 行為： Win32/PrivilegeEscalation. *！ ml |
|國防規避    | 行為： Win32/DefenseEvasion. *！ ml |
|認證存取  | 行為： Win32/CredentialAccess. *！ ml |
|發現  | 行為： Win32/探索。 *！ ml |
|橫向移動 | 行為： Win32/LateralMovement. *！ ml |
|集合 |   行為： Win32/集合。 *！ ml |
|命令和控制項 | 行為： Win32/CommandAndControl. *！ ml |
|Exfiltration   | 行為： Win32/Exfiltration. *！ ml |
|影響 | 行為： Win32/影響。 *！ ml |
|未分類  | 行為： Win32/Generic. *！ ml |

> [!TIP]
> 若要深入瞭解特定威脅，請參閱 **[最近的全域威脅活動](https://www.microsoft.com/wdsi/threats)**。


## <a name="configuring-client-behavioral-blocking"></a>設定用戶端行為封鎖

如果您的組織使用的是用於端點的 Defender，則預設會啟用用戶端行為封鎖。 不過，若要受益于所有的 Defender for Endpoint 功能，包括 [行為封鎖和包容](behavioral-blocking-containment.md)，請確定已啟用並設定 Defender for endpoint 的下列功能和功能：

- [用於端點基準的 Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [裝置架至 Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [封鎖模式中的 EDR](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [攻擊面縮減](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [下一代保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (防病毒) 

## <a name="related-articles"></a>相關文章

- [行為封鎖和包含專案](behavioral-blocking-containment.md)

- [意見反應迴圈封鎖](feedback-loop-blocking.md)

- [ (博客) 行為封鎖與包容：將光學器件轉換成保護](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [適用于端點資源的有用的 Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
