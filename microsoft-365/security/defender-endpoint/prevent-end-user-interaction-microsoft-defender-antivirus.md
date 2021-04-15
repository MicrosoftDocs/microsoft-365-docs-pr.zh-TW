---
title: 隱藏 Microsoft Defender 防病毒介面
description: 您可以隱藏 Windows 安全性應用程式中的病毒和威脅防護磚。
keywords: ui 鎖定、無周邊模式、隱藏應用程式、隱藏設定、隱藏介面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 93cd6331099c5c89aec2e0706f79ec7fb305b42a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765548"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>防止使用者看到 Microsoft Defender 防病毒使用者介面或與其互動

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用群組原則，防止使用者在端點上看到 Microsoft Defender 防病毒介面。 您也可以防止使用者暫停掃描。

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>隱藏 Microsoft Defender 防病毒介面

在 Windows 10 版本1703中，隱藏介面會隱藏 Microsoft Defender 防病毒通知，並防止病毒 & 威脅防護磚出現在 Windows 安全性應用程式中。

設定為 [ **啟用**] 時：

![沒有盾牌圖示及病毒和威脅防護區段之 Windows 安全性的螢幕擷取畫面](images/defender/wdav-headless-mode-1703.png)

設定為 [ **停** 用] 或 [未設定] 時：

![顯示盾牌圖示及病毒和威脅防護區段之 Windows 安全性的螢幕擷取畫面](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
>隱藏介面也會使 Microsoft Defender 防病毒通知不會出現在端點上。 仍會顯示 Microsoft Defender for Endpoint 通知。 您也可以個別 [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md)

在舊版 Windows 10 中，此設定會隱藏 Windows Defender 用戶端介面。 如果使用者嘗試開啟它，他們會收到警告說：「您的系統管理員已限制存取此應用程式」。

![Windows 10 中已啟用無周邊模式的警告訊息，版本低於1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>使用群組原則從使用者隱藏 Microsoft Defender AV 介面

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 在 [ **Microsoft Defender 防病毒 > 用戶端] 介面** 中，將樹狀目錄展開為 Windows 元件 >。

5. 按兩下 [啟用無 **外設 UI 模式]** 設定，並將選項設定為 [ **啟用**]。 按一下 [確定]。 

請參閱 [防止使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) ] 中的更多選項，以防止使用者表單修改其電腦上的保護。

## <a name="prevent-users-from-pausing-a-scan"></a>防止使用者暫停掃描

您可以防止使用者暫停掃描，這有助於確保使用者不會中斷排程或要求的掃描。

> [!NOTE]
> Windows 10 不支援此設定。

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>使用群組原則防止使用者暫停掃描

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 將樹狀目錄展開為 **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **掃描**。

5. 按兩下 [ **允許使用者暫停掃描** ] 設定，並將選項設定為 [ **已停用**]。 按一下 [確定]。 

## <a name="related-articles"></a>相關文章

- [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md)

- [使用 Microsoft Defender 防毒軟體設定使用者互動](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)