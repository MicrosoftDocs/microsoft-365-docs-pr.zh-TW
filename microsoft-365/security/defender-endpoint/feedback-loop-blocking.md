---
title: 意見反應迴圈封鎖
description: 意見反應-環路封鎖（也稱為快速保護）是 Microsoft Defender for Endpoint 中行為封鎖和包容功能的一部分
keywords: 行為封鎖，快速保護，回應封鎖，Microsoft Defender for Endpoint
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
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842455"
---
# <a name="feedback-loop-blocking"></a>意見反應迴圈封鎖

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>概觀

意見反應-環路封鎖（也稱為快速保護）是[Microsoft Defender For Endpoint](/windows/security/threat-protection/)中的[行為封鎖和包容功能](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)的元件。 透過反應反應封鎖，您組織中的裝置會更好地受到攻擊。 

## <a name="how-feedback-loop-blocking-works"></a>反應反應-環路封鎖的運作方式

偵測到可疑行為或檔案時（例如[Microsoft Defender 防毒軟體](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)），該專案的相關資訊會傳送至多個分類程式。 「快速保護環路引擎」會檢查資訊，並將資訊與其他信號關聯，以判斷是否封鎖檔。 檢查和分類偽像會很快進行。 這會導致快速封鎖已確認的惡意程式碼，並推動整個生態系統的保護。 

使用快速保護時，攻擊可以在裝置、組織中的其他裝置和其他組織中的裝置上停止，因為攻擊會嘗試拓寬其 foothold。


## <a name="configuring-feedback-loop-blocking"></a>設定反應反應-環路封鎖

如果您的組織使用的是用於端點的 Defender，則預設會啟用反應反應封鎖。 不過，透過 Microsoft 安全服務的 Endpoint 功能、機器學習保護功能和信號共用的組合，便會進行快速保護。 請確定已啟用並設定 Defender for Endpoint 的下列功能和功能：

- [Microsoft Defender for Endpoint 基準](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [裝置架至 Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboard-configure)

- [封鎖模式中的 EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [攻擊面縮減](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [下一代保護](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (防病毒) 

## <a name="related-articles"></a>相關文章

- [行為封鎖和包含專案](behavioral-blocking-containment.md)

- [ (博客) 行為封鎖與包容：將光學器件轉換成保護](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [有用的 Microsoft Defender for Endpoint resources](/microsoft-365/security/defender-endpoint/helpful-resources)
