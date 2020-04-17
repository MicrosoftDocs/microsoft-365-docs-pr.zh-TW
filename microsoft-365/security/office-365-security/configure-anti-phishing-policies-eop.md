---
title: 在 EOP 中設定預設的反網路釣魚原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用 Exchange Online 信箱，修改 Office 365 組織之預設反網路釣魚原則中可用的反欺騙設定。
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537530"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a>在 EOP 中設定預設的反網路釣魚原則

Office 365 組織若有 Exchange Online 信箱和獨立 Exchange Online Protection （EOP）組織，但沒有 Exchange Online 信箱的組織有預設的反網路釣魚原則。 這個原則包含預設會啟用的有限數量的反欺騙功能。 如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。

具有 Exchange Online 信箱的 Office 365 組織可以在 Office 365 安全性 & 合規性中心或 Exchange Online PowerShell 中修改預設的反網路釣魚原則。 沒有 Exchange Online 信箱的獨立 EOP 組織無法修改其預設的反網路釣魚原則。

如需建立及修改 Office 365 Advanced 威脅防護中可用的更高級 ATP 反網路釣魚原則的詳細資訊，請參閱[在 office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [**反網路釣魚**] 頁面<https://protection.office.com/antiphishing>，請使用。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 若要新增、修改和刪除反網路釣魚原則，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。 若要獲得反網路釣魚原則的唯讀存取權，您必須是**Security Reader**角色群組的成員。 如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱 [Office 365 安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。

- 如需針對預設反網路釣魚原則的建議設定，請參閱[EOP 預設的反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

- 允許套用更新的原則最多30分鐘。

- 如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱[Office 365 中的電子郵件保護順序和優先順序](how-policies-and-protections-are-combined.md)。

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>使用安全性 & 合規性中心來修改預設的反網路釣魚原則

預設的反網路釣魚原則命名為 Office365 AntiPhish 預設值，且不會顯示在原則清單中。 若要修改預設的反網路釣魚原則，請執行下列步驟：

1. 在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。

2. 在 [**反網路釣魚**] 頁面上，按一下 [**預設原則**]。

3. 隨即會顯示 [**編輯您的原則 Office365 AntiPhish 預設**] 頁面。 在 [**哄騙**] 區段中，按一下 [**編輯**]。

   請注意，這些設定與 ATP 反網路釣魚原則中提供的欺騙設定相同。

   - **哄騙篩選設定**：預設值為 [**開啟**]，建議您將其保持開啟。 若要將它關閉，請將開關滑動至 [**關閉**]。 如需詳細資訊，請參閱[Configure 哄騙情報 In Office 365](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > 如果您的 MX 記錄未指向 Office 365，您不需要停用反欺騙保護;請改為啟用連接器的增強篩選。 如需相關指示，請參閱[在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   - **啟用未經驗證的寄件者功能**：如果郵件失敗電子郵件驗證檢查，則會在寄件者的相片中加入一個問號。 如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。 預設值為 [開啟]****。 若要將它關閉，請將開關滑動至 [**關閉**]。

   - **動作**：指定對哄騙智慧失敗的郵件採取的動作：

     **如果電子郵件是由不允許哄騙您網域的人員所傳送**：

     - **將郵件移至收件者的 [垃圾郵件] 資料夾**（此為預設值）。
     - **隔離郵件**

   - 請**複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。

     - 您可以按一下每個區段中的 [**編輯**]，以跳回到相關頁面。
     - 您可以在此頁面**上****直接切換**下列設定：

       - **啟用 antispoofing 保護**
       - **啟用未經驗證的寄件者功能**

   完成後，按一下 [**儲存**] 任何頁面。

4. 回到 [**編輯您的原則] Office365 [AntiPhish 預設**] 頁面上，複查您的設定，然後按一下 [**關閉**]。

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a>使用安全性 & 合規性中心來查看預設的反網路釣魚原則

1. 在安全性 & 規範中心，然後移至**威脅管理** \> **原則** \> **ATP 反網路釣魚**。

2. 按一下 [**預設原則**] 以查看預設的反網路釣魚原則。

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a>使用 Exchange Online PowerShell 設定預設的反網路釣魚原則

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a>使用 PowerShell 來查看預設的反網路釣魚原則

若要查看預設的反網路釣魚原則，請執行下列命令：

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

如需詳細的語法及參數資訊，請參閱[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a>使用 PowerShell 修改預設的反網路釣魚原則

若要修改預設的反網路釣魚原則，請使用下列語法：

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

此範例會變更因驗證失敗，且驗證檢查是否有隔離的欺騙性郵件的動作。

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

如需詳細的語法及參數資訊，請參閱[Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功設定預設的反網路釣魚原則，請執行下列任一步驟：

- 在 [安全性 & 規範中心] 中，移至**威脅管理** \> **原則** \> **反網路釣魚** \>按一下 [**預設原則**]，然後查看快顯視窗中的詳細資料。

- 在 Exchange Online PowerShell 中，執行下列命令並確認設定：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
