---
title: 啟用或停用 Office 365 中的安全提示
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: 說明 Office 365 和 EOP 系統管理員如何啟用和停用電子郵件訊息中的安全提示。
ms.openlocfilehash: ae8a3bc9811aa54b0c5ae4cc8a0e2eb9aa80aef0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086241"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a>啟用或停用 Office 365 中的安全提示

Exchange Online Protection (EOP) 會對它傳遞的電子郵件加上 (或標記) 安全提示。 如果 Office 365 已將郵件標示為垃圾郵件、如果郵件包含某種可疑項目 (例如網路詐騙)，或者如果外部影像已遭到封鎖，這些安全提示會提供收件者快速且視覺化的方式，以判斷郵件是否來自安全且通過驗證的寄件者。 Office 365 和 EOP 獨立系統管理員可編輯垃圾郵件原則設定，以啟用或停用 Outlook 和其他桌面電子郵件用戶端之電子郵件中顯示的安全提示。

根據預設，Office 365 會為您的組織啟用安全提示，建議您保持啟用，以協助對抗垃圾郵件和網路釣魚攻擊。 您無法停用 Outlook 網頁版的安全提示。

若要查看範例並了解安全提示中顯示的資訊，請參閱 [Office 365 電子郵件的安全提示。](safety-tips-in-office-365.md)(部分內容為機器翻譯)

本主題內容：

- [使用 O365 安全性&amp;與合規性中心啟用或停用安全提示](enable-or-disable-safety-tips.md#SandCCsafetytip)

- [使用 PowerShell 啟用或停用安全提示](enable-or-disable-safety-tips.md#pshellsafetytip)

## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>使用 O365 安全性與&amp;合規性中心啟用或停用安全提示
<a name="SandCCsafetytip"> </a>

1. 請移至 [https://protection.office.com](https://protection.office.com)。

2. 使用您的公司或學校帳戶登入 Office 365。

3. 選擇 **[威脅管理]** \> **[原則]**。

4. 選擇 **[原則]** 頁面上的 **[反垃圾郵件]**。

    ![這個螢幕擷取畫面顯示如何前往安全性 &amp; 合規性中心中的 [反垃圾郵件] 設定頁面。](../../media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)

5. 選擇 **[垃圾郵件防護設定]** 頁面上的 **[自訂]** 索引標籤。

    ![此螢幕擷取畫面顯示安全性 &amp; 合規性中心中之 [反垃圾郵件] 設定頁面上的 [自訂] 索引標籤位置。](../../media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)

6. 如有需要，請選擇 **[自訂設定]** 開關，以開啟自訂設定。 如果自訂設定開關已設為 **[關閉]**，您將無法修改垃圾郵件篩選原則。

    ![此螢幕擷取畫面顯示自訂反垃圾郵件篩選原則設定為關閉。](../../media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)

7. 展開您要修改的垃圾郵件原則，然後選擇 **[編輯原則]**。 例如，選擇 **[預設垃圾郵件篩選原則]** 旁邊的向下箭號。 或者，您可以視需要選擇 **[新增原則]** 來建立新原則。

8. 展開 **[垃圾郵件及大量]** 動作。

9. 若要啟用安全提示，請在 **[安全提示]** 底下，選取 **[開啟]** 核取方塊。 若要停用安全提示，請清除 **[開啟]** 核取方塊。

10. 選擇 **[儲存]**。

## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>使用 PowerShell 啟用或停用安全提示
<a name="pshellsafetytip"> </a>

系統管理員可以使用 Exchange Online PowerShell 來啟用或停用安全提示。 使用 Set-HostedContentFilterPolicy cmdlet 啟用或停用垃圾郵件篩選原則中的安全提示。

1. 連線至 Exchange Online PowerShell。 如需資訊，請參閱 [連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

2. 執行 Set-HostedContentFilterPolicy cmdlet 啟用或停用安全提示：

   ```powershell
   Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true | $false>
   ```

其中：

- *原則名稱*是您要修改的原則名稱，例如 **[預設]**。

- `$true` 會啟用垃圾郵件篩選原則的安全提示。

- `$false` 會停用垃圾郵件篩選原則的安全提示。

例如，若要停用預設垃圾郵件篩選原則的安全提示，請執行下列命令：

```powershell
Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
```

如需有關此 cmdlet 的詳細資訊，請參閱 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy) (部分內容為機器翻譯)。

## <a name="still-need-help"></a>仍需要協助嗎？
<a name="pshellsafetytip"> </a>

如果您已停用安全提示，但仍在電子郵件中看到安全提示，請檢查下列項目：

- 您無法停用 Outlook 網頁版的安全提示。 嘗試在其他用戶端 (例如 Outlook) 檢視同一封電子郵件。

- 根據預設，每位使用 EOP 的人員的安全提示都是開啟狀態，這包括擁有 Office 365 的每個人。 為了停用安全提示使它們不再顯示於電子郵件中，您必須按本主題所述使用垃圾郵件篩選原則停用它們。 一旦您設定完原則，請確認已將它啟用。 如需有關啟用垃圾郵件篩選原則的資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md) (部分內容為機器翻譯)。

如需有關對抗垃圾郵件和網路釣魚的更多方式，請參閱 [Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md) (部分內容為機器翻譯)。
