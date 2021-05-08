---
title: 排程 Microsoft Defender 防毒軟體保護更新
description: 排程應下載保護更新的日期、時間和間隔
keywords: 更新、安全性基準、排程更新
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 26b88b8677c27a5d6615776a371326e37034afd4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275033"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>管理何時應下載並套用保護更新的排程

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防毒軟體可讓您決定何時應尋找及下載更新。

您可以依下列方式排程端點的更新： 

- 指定每週的哪一天檢查保護更新 
- 指定檢查保護更新的間隔
- 指定檢查保護更新的時間

您也可以隨機化每個端點檢查和下載保護更新的時間。 如需詳細資訊，請參閱 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主題。

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>使用 Configuration Manager 來排程保護更新

1.  在您的 Microsoft 端點管理員主控台上，開啟您想要變更的反惡意軟體原則 (按一下左側功能窗格中的 **[****資產和符合性**]，然後展開樹狀目錄  >  **Endpoint Protection**  >  **反惡意軟體原則**) 

2.  移至 [ **安全性情報更新** ] 區段。

3. 若要在特定時間檢查及下載更新：
      1. 將 [**檢查 Endpoint Protection 的安全性智慧更新**] 設定為 [特定間隔 ...] 設定為 **0**。
      2. 將 [**每日的安全性智慧更新的 Endpoint Protection 檢查**] 設定為 [每日 ...]，檢查更新的時間。
      個
4. 若要連續檢查和下載更新，請將 [**檢查是否有 Endpoint Protection 的安全性智慧更新**] 設定為 [在特定的時間間隔中更新]。

5.  [照常部署更新的原則](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

## <a name="use-group-policy-to-schedule-protection-updates"></a>使用群組原則來排程保護更新

> [!IMPORTANT]
> 根據預設，Microsoft Defender 防毒軟體會在任何排程的掃描之前，先檢查是否有15分鐘的更新。 啟用這些設定將覆寫該預設值。

1.  在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

3.  在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

4.  按一下 [ **原則** 然後是系統 **管理範本**]。

5.  展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體** 簽章  >  **智慧更新** 及設定下列設定：

    1. 按兩下 [ **指定要檢查安全性智慧更新的星期幾** ] 設定，並將此選項設定為 [ **啟用**]。 輸入星期幾以檢查更新。 按一下 ****[確定]。
    2. 按兩下 [ **指定檢查安全性智慧更新的間隔** ] 設定，並將選項設定為 [ **啟用**]。 輸入更新之間的小時數。 按一下 ****[確定]。
    3. 按兩下 [ **指定檢查安全性智慧更新的時間** ] 設定，並將選項設定為 [ **啟用**]。 輸入應檢查更新的時間。 時間是以端點的當地時間為基礎。 按一下 ****[確定]。


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>使用 PowerShell Cmdlet 來排程保護更新

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>使用 Windows 管理指令 (WMI) 來排程保護更新

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

如需詳細資訊及允許的參數，請參閱下列各項：
- [Windows DefenderWMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>相關文章

- [部署 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [管理事件型強制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
- [管理行動裝置和虛擬機器 (VM) 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)