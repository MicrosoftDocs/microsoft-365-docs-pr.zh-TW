---
title: 設定 Microsoft Defender 防毒軟體通知
description: 瞭解如何設定和自訂端點上的標準及其他 Microsoft Defender 防毒軟體通知。
keywords: 通知、defender、防毒程式、端點、管理、系統管理員
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985405"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>設定出現在端點上的 Microsoft Defender 防毒軟體通知

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

在 Windows 10 中，惡意程式碼偵測和修復的代理程式更新會變得更健壯、一致和簡潔。 在完成掃描及偵測到威脅時，端點上會出現 Microsoft Defender 防毒軟體通知。 通知遵循排程和手動觸發的掃描。 這些通知也會出現在 **通知中心**，以及掃描和威脅偵測的摘要會以固定時間間隔出現。

如果您是組織的安全小組的一部分，您可以設定在端點上顯示通知的方式，例如提示重新開機系統，或指出已偵測到威脅並進行修正的通知。

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>使用群組原則或 Windows 安全性應用程式設定防病毒通知

您可以在[Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)及群組原則中，設定其他通知的顯示（例如最近的威脅偵測摘要）。

> [!NOTE]
> 在 Windows 10 中，版本1607該功能稱為「**增強型通知**」，且是在 **Windows 設定**  >  **Update & 安全性**  >  **Windows Defender** 下設定。 在所有 Windows 10 版本的「群組原則」設定中，通知功能稱為「**增強的通知**」。

### <a name="use-group-policy-to-disable-additional-notifications"></a>使用群組原則來停用其他通知

1. 在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

3. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

4. 選取 [系統 **管理範本**]。

5. 展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**> 報告 * *。

6. 連按兩下 [ **關閉增強型通知**]，然後將選項設定為 [ **啟用**]。 然後選取 **[確定]**。 這會防止顯示其他通知。

> [!IMPORTANT]
> 停用其他通知將不會停用重要通知，例如威脅偵測和修正警示。

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>使用 Windows 安全性應用程式來停用其他通知

1. 按一下工作列中的盾牌圖示，或搜尋 [**安全性**] 的 [開始] 功能表，開啟 Windows 安全性應用程式。

2. 在左功能表列上選取 [**病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後選取 [**病毒 & 威脅防護設定**]。

3. 滾動至 [ **通知** ] 區段，然後選取 [ **變更通知設定**]。

4. 將開關滑動至 [ **關閉** ] 或 [ **開啟** ]，以停用或啟用其他通知。

> [!IMPORTANT]
> 停用其他通知將不會停用重要通知，例如威脅偵測和修正警示。

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>使用群組原則設定端點上的標準通知

您可以使用群組原則來：

- 當使用者需要執行動作時，在端點上顯示其他自訂的文字
- 隱藏端點上的所有通知
- 在端點上隱藏重新開機通知

隱藏通知可用於隱藏整個 Microsoft Defender 防毒軟體介面的情況。 如需詳細資訊，請參閱[防止使用者查看或與 Microsoft Defender 防毒軟體使用者介面互動](prevent-end-user-interaction-microsoft-defender-antivirus.md)。 隱藏通知只會發生于已部署原則的端點上。 與必須採取的動作相關的通知 (例如重新開機) 仍會顯示在[Microsoft 端點管理員 Endpoint Protection 監控儀表板和報告](/configmgr/protect/deploy-use/monitor-endpoint-protection)中。 

若要將自訂連絡人資訊新增至端點通知，請參閱[自訂群組織的 Windows 安全性應用程式](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)。

### <a name="use-group-policy-to-hide-notifications"></a>使用群組原則隱藏通知

1. 在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

3. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。

4. 展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **用戶端介面**。 

5. 按兩下 [ **抑制所有通知** ] 並將選項設定為 [ **啟用**]。 

6. 選取 **[確定]**。 這會防止顯示其他通知。

### <a name="use-group-policy-to-hide-reboot-notifications"></a>使用群組原則隱藏重新開機通知

1. 在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

2. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **用戶端介面**。

5. 按兩下 [ **重新開機通知** ]，並將選項設定為 [ **啟用**]。 

5. 選取 **[確定]**。 這會防止顯示其他通知。

