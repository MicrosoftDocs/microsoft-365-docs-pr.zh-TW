---
title: 設定 Microsoft Defender 防毒軟體雲端封鎖的超時期限
description: 您可以設定 Microsoft Defender 防毒程式在等待雲端決定時，封鎖檔案執行的時間。
keywords: Microsoft Defender 防毒程式，反惡意程式碼，安全性，Defender，cloud，timeout，組塊，period，seconds
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690123"
---
# <a name="configure-the-cloud-block-timeout-period"></a>設定雲端封鎖超時期限

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

當 Microsoft Defender 防毒程式發現可疑檔案時，它會在查詢 [Microsoft Defender 防毒軟體雲端服務](cloud-protection-microsoft-defender-antivirus.md)時，防止檔案執行。

會 [封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md) 檔案的預設週期為10秒。 您可以指定在允許檔案執行之前所等候的其他時間週期。 這可協助確保有足夠的時間接收 Microsoft Defender 防毒軟體雲端服務的適當判斷。

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>使用擴展雲端封鎖超時的必要條件

[在第一次看到時會封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md) ，必須先啟用其必要條件，您才能指定延長的超時期限。

## <a name="specify-the-extended-timeout-period"></a>指定延長的超時期限

您可以使用群組原則指定用於雲端檢查的延伸超時。

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統****管理範本**]。

3. 在 **Microsoft Defender 防病毒 > MpEngine** 中，展開樹狀目錄至 Windows 元件 >

4. 按兩下 [ **設定擴展的雲端檢查** ]，並確定已啟用此選項。 指定在等待雲端決定時，防止檔案執行的額外時間長度。 您可以指定從1秒到50秒之間的額外時間（以秒為單位）。 此時間將會新增至預設的10秒。

5. 按一下 [確定]。

## <a name="related-topics"></a>相關主題

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [透過雲端提供的保護來使用下一代防病毒技術](cloud-protection-microsoft-defender-antivirus.md)
- [設定初次看到的封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [啟用雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)