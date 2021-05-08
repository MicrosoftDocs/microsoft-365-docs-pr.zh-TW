---
title: Windows 安全性應用程式中的 Microsoft Defender 防毒軟體
description: 透過 Microsoft Defender 防毒軟體現在已包含在 Windows 安全性應用程式中，您可以檢查、比較及執行常見工作。
keywords: wdav，防毒程式，防火牆，安全性，windows
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
ms.openlocfilehash: ccb0d4cf168bbb4d3c1575c1e6611829909d0817
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275405"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Windows 安全性應用程式中的 Microsoft Defender 防毒軟體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

在 Windows 10 版本1703和更新版本中，Windows Defender 應用程式是 Windows 安全性的一部分。

先前屬於 Windows Defender 用戶端和主 Windows 設定的設定已合併並移至新的應用程式，此應用程式預設會在 Windows 10 版本1703中安裝。

> [!IMPORTANT]
> 停用 Windows 安全性 Center 服務不會停用 Microsoft Defender 防毒軟體或[Windows Defender 防火牆](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。 在安裝協力廠商防病毒或防火牆產品並保持最新狀態時，會自動停用這些功能。
>
> 如果您停用 Windows 安全性 Center 服務，或設定其相關聯的群組原則設定，以防止其啟動或執行，則 Windows 安全性應用程式可能會顯示您已在裝置上安裝之任何防毒軟體或防火牆產品的陳舊或不正確的資訊。
> 如果您有舊的或過時的協力廠商防病毒，或是卸載任何可能先前安裝的協力廠商防病毒產品，也會使 Microsoft Defender 防毒軟體無法自行啟用。
> 這會大幅降低保護您的裝置，並可能導致惡意程式碼感染。

如需其他可在應用程式中監控的 Windows 安全性功能的詳細資訊，請參閱[Windows 安全性文章](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center)。

Windows 安全性應用程式是 Windows 10 版本1703和更新版本上的用戶端介面。 這不是用來複查及管理[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)的 Microsoft Defender 資訊安全中心網頁入口網站。

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>在 Windows 安全性應用程式中審閱病毒和威脅防護設定

![Windows 安全性應用程式中的病毒 & 威脅防護設定] 標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

1. 按一下工作列中的盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 Windows 安全性應用程式。

2. 在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。
   
下列各節說明如何在查看或與 Windows 安全性應用程式中 Microsoft Defender 防毒軟體所提供的威脅防護進行互動時執行一些最常見的工作。

> [!NOTE]
> 如果使用群組原則來設定及部署這些設定，本節中所述的設定將會變灰，且無法在個別端點上使用。 您必須先將透過「群組原則」物件所做的變更部署到個別的端點，設定 Windows 設定中的設定才會更新。 「[設定使用者與 Microsoft Defender 防毒軟體互動](configure-end-user-interaction-microsoft-defender-antivirus.md)」主題說明如何設定本機原則覆寫設定。

## <a name="run-a-scan-with-the-windows-security-app"></a>使用 Windows 安全性 app 執行掃描

1. 搜尋 [**安全性**] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。

2. 在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。

3. 選取 [ **快速掃描**]。 或者，若要執行完整掃描，請選取 [ **掃描選項**]，然後選取選項，例如 **完整掃描**。

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>檢查安全性智慧更新版本，並在 Windows 安全性應用程式中下載最新的更新

![安全性智慧版本號碼資訊](images/defender/wdav-wdsc-defs.png)

1. 搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。

2. 在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。

3. 選取 [ **病毒 & 威脅防護更新**]。 目前安裝的版本會顯示，以及下載時的部分資訊。 您可以查看最新版本的最新版本，以供手動下載，或查看該版本的變更記錄檔。 請參閱[安全性情報更新的 Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體](https://www.microsoft.com/en-us/wdsi/defenderupdates)。

4. 如果有任何) ，請選取 [ **檢查更新** 以下載新的保護更新 (。

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>確定 Windows 安全性應用程式中已啟用 Microsoft Defender 防毒軟體

1. 搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。

2. 在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。

3. 選取 [ **病毒 & 威脅防護設定**]。

4. 將 **即時保護** 開關切換為 [ **開啟**]。

    > [!NOTE]
    > 如果您切換 **即時保護** ，它會在一段短暫的延遲之後自動重新開啟。 這是為了確保您免受惡意程式碼和威脅的侵擾。
    > 如果您安裝其他防病毒產品，Microsoft Defender 防毒軟體會在 Windows 安全性應用程式中自動停用自身，並以這種方式指示。 會出現一個設定，讓您啟用有限的 [定期掃描](limited-periodic-scanning-microsoft-defender-antivirus.md)。

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>在 Windows 安全性應用程式中新增 Microsoft Defender 防毒軟體的排除專案

1. 搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。

2. 在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。

3. 在 [ **管理設定**] 底下，選取 [ **病毒 & 威脅防護設定**]。

4. 在 [ **排除** ] 設定下，選取 [ **新增或移除排除**]。 

5. 選取加號圖示 (**+**) 選擇 [類型]，然後為每個排除專案設定選項。 

下表摘要列出排除類型以及所發生的情況：

|排除類型  |定義者  |會發生什麼事  |
|---------|---------|---------|
|**檔案** |位置 <br/>範例：`c:\sample\sample.test` |Microsoft Defender 防毒軟體會略過特定檔案。 |
|**Folder**    |位置 <br/>範例：`c:\test\sample`       |Microsoft Defender 防毒軟體會略過指定資料夾中的所有專案。         |
|**檔案類型**   |副檔名 <br/>範例：`.test` |`.test`您裝置上任何地方副檔名的所有檔案都會受到 Microsoft Defender 防毒軟體略過。         |
|**程序**     |可執行檔路徑 <br>範例：`c:\test\process.exe`         |Microsoft Defender 防毒軟體會略過此程式所開啟的特定程式和任何檔案。         |

若要深入了解，請參閱下列資源：
- [根據副檔名和資料夾位置，設定及驗證排除](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [設定處理常式開啟之檔案的排除專案](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>在 Windows Defender 的安全性中心應用程式中審閱威脅偵測歷程記錄

1. 搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。

2. 在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。

3. 選取 [ **保護歷程記錄**]。 已列出任何最近的專案。

## <a name="set-ransomware-protection-and-recovery-options"></a>設定勒索軟體防護和修復選項

1. 搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。

2. 在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。

3. 在 [ **勒索軟體防護**] 底下，選取 [ **管理勒索軟體防護**]。

4. 若要變更 **控制的資料夾存取** 設定，請參閱 [使用可控資料夾存取權保護重要資料夾](/microsoft-365/security/defender-endpoint/controlled-folders)。

5. 若要設定勒索軟體恢復選項，請選取 [在 **勒索軟體資料** 復原] 底下的 [**設定**]，並依照連結或設定 OneDrive 帳戶的指示進行，讓您能輕鬆地從勒索軟體攻擊復原。

## <a name="see-also"></a>另請參閱
- [Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)