---
title: 設定 Microsoft Defender 防病毒通知
description: 瞭解如何設定和自訂端點上的標準及其他 Microsoft Defender 防病毒通知。
keywords: 通知、defender、防毒程式、端點、管理、系統管理員
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
ms.openlocfilehash: a91da48f27450d6f4a6fd2b9607aa979458ccf71
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765092"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>設定出現在端點上的通知

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

在 Windows 10 中，惡意程式碼偵測和修復的代理程式更新會變得更健壯、一致和簡潔。

當手動觸發和排程的掃描已完成且偵測到威脅時，在端點上會出現通知。 這些通知也會出現在 **通知中心**，以及掃描和威脅偵測的摘要會以固定時間間隔出現。

您也可以設定在端點上顯示標準通知的方式，例如，當偵測到威脅或已偵測到威脅時的通知。

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>設定出現在端點上的其他通知

您可以在 [ [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md) ] 和 [群組原則] 中，設定其他通知的顯示（例如最近的威脅偵測摘要）。

> [!NOTE]
> 在 windows 10 中，版本1607該功能稱為「**增強型通知**」，可在 [ **windows 設定**  >  **更新 & security**  >  **Windows Defender**] 下加以設定。 在所有 Windows 10 版本的「群組原則」設定中，稱為 **增強型通知**。

> [!IMPORTANT]
> 停用其他通知將不會停用重要通知，例如威脅偵測和修正警示。

**使用 Windows 安全性應用程式來停用其他通知：**

1. 按一下工作列上的盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 [Windows 安全性] 應用程式。

2. 在左功能表列上，按一下 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後按一下 [ **病毒 & 威脅防護設定** ] 標籤：

    ![Windows 安全性應用程式中的病毒 & 威脅防護設定] 標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. 滾動至 [ **通知** ] 區段，然後按一下 [ **變更通知設定**]。

4. 將開關滑動至 [ **關閉** ] 或 [ **開啟** ]，以停用或啟用其他通知。

**使用群組原則來停用其他通知：**

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 在 [ **Microsoft Defender 防病毒 > 報告**] 中，展開 [Windows 元件] > 的樹狀目錄。

5. 按兩下 [ **關閉增強型通知** ]，並將選項設定為 [ **啟用**]。 按一下 [確定]。 這會防止顯示其他通知。

## <a name="configure-standard-notifications-on-endpoints"></a>設定端點的標準通知

您可以使用群組原則來：

- 當使用者需要執行動作時，在端點上顯示其他自訂的文字
- 隱藏端點上的所有通知
- 在端點上隱藏重新開機通知

隱藏通知可用於隱藏整個 Microsoft Defender 防病毒介面的情況。 請參閱 [防止使用者查看或與 Microsoft Defender 防病毒使用者介面互動](prevent-end-user-interaction-microsoft-defender-antivirus.md) ，以取得詳細資訊。 

> [!NOTE]
> 隱藏通知只會發生于已部署原則的端點上。 與必須採取的動作相關的通知 (例如重新開機) 仍會出現在 [Microsoft 端點管理員端點防護監控儀表板和報告](/configmgr/protect/deploy-use/monitor-endpoint-protection)上。 

請參閱 [自訂群組織的 Windows 安全性 app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) ，以取得將自訂連絡人資訊新增至使用者在其機器上看到之通知的指示。

**使用群組原則隱藏通知：**

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統****管理範本**]。

3. 在 [ **Microsoft Defender 防病毒 > 用戶端] 介面** 中，將樹狀目錄展開為 Windows 元件 >。 

4. 按兩下 [ **抑制所有通知** ] 並將選項設定為 [ **啟用**]。 按一下 [確定]。 這會防止顯示其他通知。

**使用群組原則隱藏重新開機通知：**

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 在 [ **Microsoft Defender 防病毒 > 用戶端] 介面** 中，將樹狀目錄展開為 Windows 元件 >。

5. 按兩下 [ **重新開機通知** ]，並將選項設定為 [ **啟用**]。 按一下 [確定]。 這會防止顯示其他通知。

## <a name="related-topics"></a>相關主題

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [使用 Microsoft Defender 防毒軟體設定使用者互動](configure-end-user-interaction-microsoft-defender-antivirus.md)