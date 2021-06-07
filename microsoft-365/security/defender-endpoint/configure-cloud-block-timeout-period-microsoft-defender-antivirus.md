---
title: 設定 Microsoft Defender 防毒軟體 cloud block 超時期間
description: 您可以設定 Microsoft Defender 防毒軟體會封鎖檔案在等候雲端決定時執行的時間長度。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，cloud，timeout，block，period，seconds
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789084"
---
# <a name="configure-the-cloud-block-timeout-period"></a>設定雲端封鎖逾時期間

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

當 Microsoft Defender 防毒軟體發現可疑的檔案時，它會在查詢[Microsoft Defender 防毒軟體雲端服務](cloud-protection-microsoft-defender-antivirus.md)時，防止檔案執行。

[封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md)檔的預設週期為10秒。 如果您是安全性管理員，您可以指定在允許檔案執行之前所等候的時間。 擴充雲端封鎖超時期限可協助確保有足夠的時間從 Microsoft Defender 防毒軟體雲端服務接收適當的判斷。

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>使用擴展雲端封鎖超時的必要條件

[在第一次看到時會封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md) ，必須先啟用其必要條件，您才能指定延長的超時期限。

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>使用 Microsoft 端點管理員指定延長的超時期間

您可以[在 Microsoft 端點管理員中指定包含端點安全性原則](/mem/intune/protect/endpoint-security-policy)的雲端封鎖超時期限。

1. 請移至端點管理員系統管理中心 ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) 並登入。

2. 選取 [ **端點安全性**]，然後在 [ **管理**] 下選擇 [ **防病毒**]。

3. 選取 [ (] 或 [建立) 防病毒原則]。

4. 在 [ **設定設定** ] 區段中，展開 [ **Cloud protection**]。 然後，在 [ **Defender Cloud Extended Timeout** Time （秒）] 方塊中，指定從1秒到50秒的時間（秒）。 您指定的任何內容都會新增至預設的10秒。

5.  (此步驟是選用的) 對防病毒原則進行其他變更。  (需要協助嗎？ 請參閱[Microsoft Intune 中 Microsoft Defender 防毒軟體原則的設定](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)。 ) 

6. 選擇 **[下一步**]，然後完成原則的設定。

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>使用群組原則指定擴充的超時週期

您可以使用群組原則指定用於雲端檢查的延伸超時。

1. 在您的群組原則管理電腦上，開啟「[群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))」

2. 以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

3. 在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。

3. 展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **MpEngine**。

4. 按兩下 [ **設定擴展的雲端檢查** ]，並確定已啟用此選項。 

   指定在等待雲端決定時，防止檔案執行的額外時間長度。 指定從1秒到50秒之間的額外時間（秒）。 您指定的任何內容都會新增至預設的10秒。

5. 選取 [確定]。

 