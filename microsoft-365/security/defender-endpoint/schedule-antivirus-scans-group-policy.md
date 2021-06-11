---
title: 使用群組原則排程防病毒掃描
description: 使用群組原則設定防病毒掃描
keywords: 快速掃描、完整掃描、排程、群組原則、防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879693"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>使用群組原則排程防病毒掃描

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

本文說明如何使用「群組原則」設定排程掃描。 若要深入瞭解排程掃描及掃描類型的相關資訊，請參閱[設定排程快速或完整 Microsoft Defender 防毒軟體掃描](schedule-antivirus-scans.md)。 

## <a name="configure-antivirus-scans-using-group-policy"></a>使用群組原則設定防病毒掃描

1. 在您的群組原則管理電腦上，在 [群組原則編輯器] 中，移至 [電腦設定]**系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **掃描**]。

2. 以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

3. 指定「群組原則」物件的設定，然後選取 **[確定]**。 

4. 針對每個您要設定的設定，請重複步驟1-4。

5. 照常部署您的群組原則物件。 如果您需要「群組原則」物件的協助，請參閱 [建立群組原則物件](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。

> [!TIP]
> 請參閱 [管理應下載及套用保護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) ，並 [防止或允許使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主題。

## <a name="group-policy-settings-for-scheduling-scans"></a>排程掃描的群組原則設定

| 位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|:---|:---|:---|:---|
| 掃描 | 指定用於排程掃描的掃描類型 | 快速掃描 |
| 掃描 | 指定一周中的哪一天執行排程掃描 | 指定 [天] (或 [永不) ] 執行掃描。 | 從來不需要 |
| 掃描 | 指定一天中執行排程掃描的時間 | 指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) 。 | 淩晨2點 |
| 根 | 隨機化排程的任務時間 |在 Microsoft Defender 防毒軟體中，將掃描的開始時間隨機化為從0到4小時的任何間隔。 <p>在 [SCEP](/mem/intune/protect/certificates-scep-configure)中，隨機化掃描任何間隔加上或減30分鐘。 這對虛擬機器或 VDI 部署很有用。 | 啟用 |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>在端點未使用時進行排程掃描的群組原則設定

| 位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|:---|:---|:---|:---|
| 掃描 | 僅當電腦已開啟但未在使用中時啟動排程掃描 | 除非電腦已開啟但未在使用中，否則不會執行排程掃描 | 啟用 |

> [!NOTE]
> 當您排程掃描時未使用端點時，掃描功能不會服從 CPU 節流設定，而且將充分利用可讓您盡可能快地完成掃描的資源。

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>排程修正的群組原則設定-必要的掃描

| 位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|---|---|---|---|
| 修復 | 指定一周中的哪幾天執行排程完整掃描以完成修復 | 指定 [天] (或 [永不) ] 執行掃描。 | 從來不需要 |
| 修復 | 指定一天中執行計畫完整掃描以完成修復的時間 | 指定午夜後的分鐘數 (例如，輸入 **60** a.m. )  | 淩晨2點 |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>排程每日掃描的群組原則設定

| 位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|:---|:---|:---|:---|
| 掃描 | 指定每天執行快速掃描的間隔 | 指定下一個快速掃描之前所應經過的小時數。 例如，若要每兩個小時執行一次，請輸入 **2** 一天一次，輸入 **24**。 輸入 **0** ，永遠不執行每日快速掃描。 | 從來不需要 |
| 掃描 | 指定每日快速掃描的時間 | 指定午夜後的分鐘數 (例如，輸入 **60** a.m. )  | 淩晨2點 |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>保護更新後進行排程掃描的群組原則設定

| 位置 | 設定 | 描述 | 預設設定 (（如果未設定）) |
|:---|:---|:---|:---|
| 特徵碼更新 | 在安全性智慧更新後開啟掃描 | 下載新的保護更新後會立即進行掃描 | 啟用 |

