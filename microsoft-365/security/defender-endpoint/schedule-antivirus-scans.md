---
title: 使用 Microsoft Defender 防毒軟體安排一般快速和完整掃描
description: 設定週期性 (排程) 掃描，包括何時應執行，以及是否執行為完整或快速掃描
keywords: 「快速掃描」、「完整掃描」、「快速完整」、「排程掃描」、「每天」、「排程」、「定期」、「定期」
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
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879685"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>設定排程的快速或完整 Microsoft Defender 防毒軟體掃描

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

除了永遠開啟、即時保護及 [隨選防病毒](run-scan-microsoft-defender-antivirus.md) 掃描之外，您還可以設定定期、排程的防病毒掃描。 您可以設定掃描類型、掃描應該發生時，以及在執行 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 或未使用端點時進行掃描。 您也可以視需要設定特殊的掃描，以完成修復動作。

## <a name="what-do-you-want-to-do"></a>您要執行的工作

- [深入瞭解快速掃描、完整掃描及自訂掃描](#quick-scan-full-scan-and-custom-scan)
- [使用群組原則來排程防病毒掃描](schedule-antivirus-scans-group-policy.md)
- [使用 Windows PowerShell 來排程防病毒掃描](schedule-antivirus-scans-powershell.md)
- [使用 Windows 管理工具來排程防病毒掃描](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>請記住下列幾點

- 根據預設，Microsoft Defender 防毒軟體會在任何排程的掃描時間之前，先檢查是否有15分鐘的更新。 您可以 [管理應下載保護更新及](manage-protection-update-schedule-microsoft-defender-antivirus.md) 套用的時程表，以覆寫此預設值。 

- 如果在排程完整掃描期間，裝置已拔出並在電池上執行，則排定的掃描會停止事件1002，這表明掃描在完成前已停止。 Microsoft Defender 防毒軟體會在下一個排程的時間執行完整掃描。

## <a name="quick-scan-full-scan-and-custom-scan"></a>快速掃描、完整掃描及自訂掃描

當您設定排程掃描時，您可以指定掃描是否應為完整或快速掃描。 在大多數情況下，建議使用快速掃描。 

| 快速掃描  | 完整掃描  | 自訂掃描 |
|---------|---------|---------|
| 建議的 () 快速掃描查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知的 Windows startup 資料夾。 <p>結合 always on 即時保護，可在開啟及關閉檔時對其進行審閱; 每當使用者流覽至資料夾時，快速掃描可協助對以系統和內核層級惡意程式碼開頭的惡意程式碼提供強防護。 <p>在大多數情況下，快速掃描足以滿足計畫掃描的建議選項。 | 完整掃描會從執行快速掃描開始，繼續執行所有已裝載固定磁片及移除/網路磁碟機的連續檔案掃描 (如果完整掃描已設定為執行此作業) 。 <p>根據需要掃描的資料量和類型，完整掃描可能需要數小時或數天才能完成。<p>完成完整掃描之後，就可以使用新的安全性智慧，並必須進行新的掃描，以確保不會以新的安全性情報偵測到其他威脅。 <p>由於完整掃描所涉及的時間和資源，在一般情況下，Microsoft 不建議排程完整掃描。  | 自訂掃描是在您指定的檔案和資料夾上執行的快速掃描。 例如，您可以選擇掃描 USB 磁片磁碟機，或裝置的本機磁片磁碟機上的特定資料夾。 <p> | 

> [!NOTE]
> 根據預設，在裝載的可拆卸裝置（例如 USB 磁片磁碟機）上執行快速掃描。

## <a name="how-do-i-know-which-scan-type-to-choose"></a>如何知道要選擇的掃描類型為何？

請使用下表選擇掃描類型。

| 案例  | 建議的掃描類型  |
|---------|---------|
| 您想要設定定期、排程掃描     | 快速掃描 <p>快速掃描會檢查裝置上的處理常式、記憶體、設定檔及特定位置。 [！注意] 結合了 [always on 即時保護](configure-real-time-protection-microsoft-defender-antivirus.md)，快速掃描可為以系統和內核層級惡意程式碼開頭的惡意程式碼提供強大的覆蓋。 即時保護會在開啟及關閉檔時查看檔案，以及每當使用者流覽至資料夾時，就會檢查檔案。         |
| 在個別裝置上偵測到威脅（如惡意程式碼）     | 快速掃描 <p>在大多數情況下，快速掃描會捕捉並清除偵測到的惡意程式碼。   |
| 您想要執行 [隨選掃描](run-scan-microsoft-defender-antivirus.md)     | 快速掃描       |
| 您想確定可擕式裝置（例如 USB 磁片磁碟機）不包含惡意程式碼 | 自訂掃描 <p>自訂掃描可讓您選取特定位置、資料夾或檔案，並執行快速掃描。 |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>若要瞭解快速和完整掃描，還需要瞭解什麼？

- 惡意檔案可以儲存在快速掃描中未包含的位置。 不過，always on 即時保護會檢查開啟和關閉的所有檔案，以及使用者可存取之資料夾中的所有檔案。 即時保護和快速掃描的組合，可協助抵禦惡意程式碼的加強防護。

- 以 [雲端傳送保護](cloud-protection-microsoft-defender-antivirus.md) 的存取保護，可協助確保已使用最新的安全性情報和雲端機教學模型掃描系統上存取的所有檔案。

- 當即時保護偵測到惡意程式碼，且不會最初決定受影響的檔案的程度時，Microsoft Defender 防毒軟體會在修復程式中啟動完整掃描。

- 完整掃描可偵測其他掃描未偵測到的惡意檔，例如快速掃描。 不過，完整掃描可能需要一段時間，並使用寶貴的系統資源完成。

- 如果裝置離線一段時間，則完整掃描可能需要較長的時間才能完成。 

