---
title: 使用行動裝置管理工具上線 Windows 10 電腦
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用行動裝置管理工具，在裝置上部署設定套件，使其可架至服務。
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917989"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>使用行動裝置管理工具上線 Windows 10 電腦

**適用於：**

- [Microsoft 365端點資料遺失防護 (DLP) ](./endpoint-dlp-learn-about.md)

您可以使用 [行動裝置管理] (MDM) 解決方案來設定裝置。 Microsoft 365端點資料遺失防護可提供 OMA-URIs 來建立管理裝置的原則，以支援 MDMs。


## <a name="before-you-begin"></a>開始之前
如果您正在使用 Microsoft Intune，則必須已註冊裝置 MDM。 否則，將不會成功套用設定。 

如需使用 Microsoft Intune 啟用 MDM 的詳細資訊，請參閱[Device 註冊 (Microsoft Intune) ](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-devices-using-microsoft-intune"></a>使用 Microsoft Intune 的板載裝置

遵循 [Intune](/intune/advanced-threat-protection)中的指示。

> [!NOTE]
> - **架裝置原則的健全狀況狀態** 會使用唯讀屬性，而且無法補救。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>使用行動裝置管理工具下架及監視裝置

基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。 傳送給裝置的已到期的脫離套件會遭到拒絕。 下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。

> [!NOTE]
> 上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。

1. 從 [Microsoft 規範中心](https://compliance.microsoft.com/)取得脫離套件。

2. 在功能窗格中，選取 [**設定**  >  **裝置上架**]  >  **脫離**。

3. 在 [**部署方法**] 欄位中，選取 [行動 **裝置管理/Microsoft Intune**]。
    
4. 按一下 [ **下載套件**]，然後儲存 .zip 檔。

5. 將 .zip 檔案的內容解壓至共用的唯讀位置，該位置可供將要部署此套件的網路系統管理員存取。 您應該會有一個名為 *DeviceCompliance_valid_until_YYYY-MM 的* 檔案名。

6. 使用 Microsoft Intune 自訂設定原則部署下列支援的 OMA URI 設定。

      OMA URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Date type： String      
      值： [從 DeviceCompliance_valid_until_YYYY-DD 映射檔的內容複寫並貼上值]

如需 Microsoft Intune 原則設定的詳細資訊，請參閱[Windows 10 Microsoft Intune 中的原則設定](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)。

> [!NOTE]
> **Offboarded 裝置原則的健全狀況狀態** 會使用唯讀屬性，而且無法補救。

> [!IMPORTANT]
> 脫離會導致裝置停止將感應器資料傳送至入口網站，但是來自裝置的資料（包括對它所做的任何警示參考）將保留最多6個月。

## <a name="related-topics"></a>相關主題
- [使用群組原則的板載 Windows 10 裝置](dlp-configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置](dlp-configure-endpoints-sccm.md)
- [使用本機指令碼上線 Windows 10 裝置](dlp-configure-endpoints-script.md)
- [上線非持續 Virtual Desktop Infrastructure (VDI) 裝置](dlp-configure-endpoints-vdi.md)
- [疑難排解 Microsoft Defender 進階威脅防護上架問題](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)