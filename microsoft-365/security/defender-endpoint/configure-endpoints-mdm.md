---
title: 使用行動裝置管理工具上線 Windows 10 電腦
description: 使用行動裝置管理工具，在裝置上部署設定套件，讓裝置可架至服務。
keywords: 使用 mdm 的板載裝置、裝置管理、板載 Microsoft Defender for Endpoint 裝置、mdm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f0a0a35d41d56abfcc7975c9e79ff7d537b72f40
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338574"
---
# <a name="onboard-the-windows-10-devices-using-mobile-device-management-tools"></a>使用行動裝置管理工具板載 Windows 10 裝置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

您可以使用 [行動裝置管理] (MDM) 解決方案來設定裝置。 Endpoint for Endpoint 支援 MDMs，方法是提供建立原則來管理裝置的 OMA-URIs。

如需使用 Defender for Endpoint CSP 的詳細資訊，請參閱 [WINDOWSADVANCEDTHREATPROTECTION CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)檔案。

## <a name="before-you-begin"></a>事前準備
如果您正在使用 Microsoft Intune，則必須已註冊裝置 MDM。 否則，將不會成功套用設定。 

如需使用 Microsoft Intune 啟用 MDM 的詳細資訊，請參閱[Device 註冊 (Microsoft Intune) ](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-devices-using-microsoft-intune"></a>使用 Microsoft Intune 的板載裝置

[![顯示使用 Microsoft Intune ](images/onboard-intune.png) 之 Endpoint To Defender 的內架裝置的 PDF 影像](images/onboard-intune-big.png#lightbox)

請取出[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)或[Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ，以查看部署 Defender for Endpoint 的各種路徑。 

遵循 [Intune](/intune/advanced-threat-protection)中的指示。

如需使用 Defender for Endpoint CSP 的詳細資訊，請參閱 [WINDOWSADVANCEDTHREATPROTECTION CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)檔案。


> [!NOTE]
> - **架裝置原則的健全狀況狀態** 會使用唯讀屬性，而且無法補救。
> - 診斷資料包表頻率設定僅適用于 Windows 10，版本1703上的裝置。


>[!TIP]
> 在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。 如需詳細資訊，請參閱 [在新架的 Microsoft Defender For Endpoint 裝置上執行偵測測試](run-detection-test.md)。


取出[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)或[Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ，以查看部署 Microsoft Defender for Endpoint 中的各種路徑。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>使用行動裝置管理工具下架及監視裝置
基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。 傳送給裝置的已到期的脫離套件會遭到拒絕。 下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。

> [!NOTE]
> 上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。

1. 從[Microsoft 365 Defender 入口網站](https://security.microsoft.com/)取得脫離套件：

   1. 在功能窗格中，選取 [**設定**  >  **端點**  >  **裝置管理**  >  **脫離**]。

   1. 選取 [Windows 10] 做為作業系統。

   1. 在 [**部署方法**] 欄位中，選取 [行動 **裝置管理/Microsoft Intune**]。
    
   1. 按一下 [ **下載套件**]，然後儲存 .zip 檔。

2. 將 .zip 檔案的內容解壓至共用的唯讀位置，該位置可供將要部署此套件的網路系統管理員存取。 您應該會有一個名為 *WindowsDefenderATP_valid_until_YYYY-MM 的* 檔案名。

3. 使用 Microsoft Intune 自訂設定原則部署下列支援的 OMA URI 設定。

      OMA URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      Date type： String<br/>
      值： [從 WindowsDefenderATP_valid_until_YYYY-DD 映射檔的內容複寫並貼上值]

如需 Microsoft Intune 原則設定的詳細資訊，請參閱[Windows 10 Microsoft Intune 中的原則設定](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)。


> [!NOTE]
> **Offboarded 裝置原則的健全狀況狀態** 會使用唯讀屬性，而且無法補救。

> [!IMPORTANT]
> 脫離會導致裝置停止將感應器資料傳送至入口網站，但是來自裝置的資料（包括對它所做的任何警示參考）將保留最多6個月。

## <a name="related-topics"></a>相關主題
- [使用群組原則的板載 Windows 10 裝置](configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置](configure-endpoints-sccm.md)
- [使用本機指令碼上線 Windows 10 裝置](configure-endpoints-script.md)
- [上線非持續 Virtual Desktop Infrastructure (VDI) 裝置](configure-endpoints-vdi.md)
- [在新架的 Microsoft Defender for Endpoint 裝置上執行偵測測試](run-detection-test.md)
- [疑難排解 Microsoft Defender 的端點上架問題](troubleshoot-onboarding.md)
