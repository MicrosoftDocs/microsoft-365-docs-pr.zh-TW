---
title: 隱藏 Microsoft Defender 防毒軟體介面
description: 您可以在 Windows 安全性應用程式中隱藏病毒和威脅防護磚。
keywords: ui 鎖定、無周邊模式、隱藏應用程式、隱藏設定、隱藏介面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007659"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>防止使用者看到或與 Microsoft Defender 防毒軟體使用者介面互動

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用群組原則，防止使用者在端點上看到 Microsoft Defender 防毒軟體介面。 您也可以防止使用者暫停掃描。

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>隱藏 Microsoft Defender 防毒軟體介面

在 Windows 10 中，隱藏介面的版本1703會隱藏 Microsoft Defender 防毒軟體通知，並防止病毒 & 威脅防護磚出現在 Windows 安全性應用程式中。

設定為 [ **啟用**] 時：

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Windows 安全性，但沒有盾牌圖示與病毒和威脅防護區段":::

設定為 [ **停** 用] 或 [未設定] 時：

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="具有盾牌圖示及威脅防護區段 Windows 安全性的螢幕擷取畫面":::

>[!NOTE]
>隱藏介面也會使 Microsoft Defender 防毒軟體通知不會出現在端點上。 仍會顯示 Microsoft Defender for Endpoint 通知。 您也可以個別 [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md)

在舊版的 Windows 10 中，設定會隱藏 Windows Defender 用戶端介面。 如果使用者嘗試開啟它，他們會收到警告說：「您的系統管理員已限制存取此應用程式」。

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Windows 10 中的無周邊模式啟用時的警告訊息，版本低於1703":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>使用群組原則從使用者隱藏 Microsoft Defender AV 介面

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 用戶端介面**。

5. 按兩下 [啟用無 **外設 UI 模式]** 設定，並將選項設定為 [ **啟用**]。 按一下 ****[確定]。 

請參閱 [防止使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) ] 中的更多選項，以防止使用者表單修改其電腦上的保護。

## <a name="prevent-users-from-pausing-a-scan"></a>防止使用者暫停掃描

您可以防止使用者暫停掃描，這有助於確保使用者不會中斷排程或要求的掃描。

> [!NOTE]
> Windows 10 不支援此設定。

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>使用群組原則防止使用者暫停掃描

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows**  >  **Microsoft Defender 防毒軟體**  >  **掃描** 的元件。

5. 按兩下 [ **允許使用者暫停掃描** ] 設定，並將選項設定為 [ **已停用**]。 按一下 ****[確定]。 

## <a name="related-articles"></a>相關文章

- [設定端點顯示的通知](configure-notifications-microsoft-defender-antivirus.md)

- [設定使用者與 Microsoft Defender 防毒軟體互動互動](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)