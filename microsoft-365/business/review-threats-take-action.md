---
title: 查看偵測到的威脅並採取動作
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 瞭解如何在 Windows 10 裝置上複查及管理 Microsoft Defender 防毒程式所偵測到的威脅。
ms.openlocfilehash: 21830b91bfbb88fdd5d5139ee07c4dfb35f5b875
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376679"
---
# <a name="review-detected-threats-and-take-action"></a>查看偵測到的威脅並採取動作

偵測到惡意檔或軟體之後，Microsoft Defender 防毒程式會封鎖它，並防止其執行。 而且，已開啟雲端提供的保護，新偵測到的威脅會新增至防毒軟體和反惡意程式碼引擎，讓其他裝置和使用者也受到保護。

Microsoft Defender 防病毒偵測並防護下列威脅類型：

- 裝置上的病毒、惡意程式碼和網路型威脅
- 網路釣魚企圖
- 資料竊取嘗試

做為 IT 專業人員/系統管理員，您可以在 Microsoft 365 系統管理中心，查看在 [Intune 中註冊的 Windows 10 裝置](/mem/intune/enrollment/device-enrollment) 中威脅偵測的相關資訊。 您將會看到摘要資訊，例如：

- 需要防防毒保護的裝置數目
- 安全性原則不相容的裝置數目
- 目前使用中、已緩解或已解決的威脅數目

您有數個選項可以查看有關威脅偵測和裝置的特定資訊：

- <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>中的 [作用中 **裝置**] 頁面。 請參閱本文中 [作用中 [裝置] 頁面上的 [管理威脅](#manage-threat-detections-on-the-active-devices-page) 偵測]。
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>中的 [作用中 **威脅**] 頁面。 請參閱本文的「作用中 [威脅」頁面上的管理威脅](#manage-threat-detections-on-the-active-threats-page) 偵測。
- <a href="https://endpoint.microsoft.com" target="_blank">Microsoft 端點管理員</a>中的 [**防病毒**] 頁面。 請參閱本文中的 [管理 Microsoft 端點管理員](#manage-threat-detections-in-microsoft-endpoint-manager) 中的威脅偵測。

若要深入瞭解，請參閱 [Microsoft Defender 防病毒偵測到的威脅](threats-detected-defender-av.md)。

## <a name="manage-threat-detections-on-the-active-devices-page"></a>在 [作用中 **裝置** ] 頁面上管理威脅偵測

下列程式適用于具有 Microsoft 365 商務版 Premium 的客戶。

1. 移至 Microsoft 365 系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，並登入。

2. 在導覽頁面中，選取 [**裝置** 作用中  >  **裝置**]。 您將會看到作用中裝置和詳細資料的清單，例如保護狀態、防病毒 (AV) 保護狀態，以及偵測到的使用中威脅數目。

3. 選取裝置以查看該裝置和可用動作的詳細資料。 快顯視窗隨即開啟，包含建議和可用的動作，例如 **更新原則**、 **更新防病毒** 程式、 **執行快速掃描**、 **執行完整掃描** 等等。

## <a name="manage-threat-detections-on-the-active-threats-page"></a>在 [使用中 **威脅** ] 頁面上管理威脅偵測

下列程式適用于具有 Microsoft 365 商務版的客戶。 [Windows 10 裝置必須](/microsoft-365/business/secure-win-10-pcs)[在 Intune 中](/mem/intune/enrollment/windows-enrollment-methods)安全且註冊。

> [!NOTE]
> **Microsoft Defender 防毒軟體** 卡和作用中 **威脅** 頁面會以分階段的方式展開，所以您可能無法立即進行存取。

1. 移至 Microsoft 365 系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，並登入。

2. 在 **Microsoft Defender 防病毒** 卡上，選取 [ **查看主動威脅**]。  (此外，在功能窗格中，選取 [**健康**  >  **威脅] & 防病毒**。 ) 

3. 在 [ **積極威脅** ] 頁面上，選取偵測到的威脅以深入瞭解。 快顯視窗隨即開啟，並顯示該威脅的詳細資料，包括所影響的裝置。

4. 在快顯視窗中，選取裝置以查看可用的動作，例如「 **更新原則**」、「 **更新防病毒** 程式」、「 **執行快速掃描**」等等。

## <a name="actions-you-can-take"></a>您可以採取的動作

當您查看特定威脅或裝置的詳細資料時，您會看到建議，以及您可以採取的一或多項動作。 下表說明您可能會看到的動作。<br><br>

| 動作 | 描述 |
|--|--|
| 設定保護 | 您必須設定威脅防護原則。 選取 [連結] 以移至 [原則設定] 頁面。<br><br>需要協助？ 請參閱 [使用 Microsoft Intune 中的端點安全性原則管理裝置安全性](/mem/intune/protect/endpoint-security-policy)。 |
| 更新原則 | 您的防病毒和即時保護原則必須更新或設定。 選取連結以移至 [原則設定] 頁面。<br><br>需要協助？ 請參閱 [使用 Microsoft Intune 中的端點安全性原則管理裝置安全性](/mem/intune/protect/endpoint-security-policy)。 |
| 執行快速掃描 | 在裝置上啟動快速防病毒掃描，以著重于可能會註冊惡意程式碼的常見位置，例如登錄機碼和已知的 Windows startup 資料夾。 |
| 執行完整掃描 | 啟動裝置上的完整防病毒掃描，著重于可能會註冊惡意程式碼的常見位置，並包括裝置上的每個檔案和資料夾。 結果會傳送至 [Microsoft 端點管理員](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 更新防病毒 | 需要裝置取得 [安全情報更新](https://go.microsoft.com/fwlink/?linkid=2149926) ，以進行防病毒和反惡意程式碼保護。 |
| 重新開機裝置 | 強制 Windows 10 裝置在五分鐘內重新開機。<br><br>**重要：** 裝置擁有人或使用者不會自動通知重新開機，而且可能會遺失未儲存的工作。 |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>在 Microsoft 端點管理員中管理威脅偵測

您可以使用 Microsoft 端點管理員來管理威脅偵測。 Windows 10 裝置必須在 Intune (部分的 Microsoft 端點管理員) [中註冊](/mem/intune/enrollment/windows-enrollment-methods) 。

1. 移至 Microsoft 端點管理員管理中心 <a href="https://endpoint.microsoft.com" target="_blank">https://endpoint.microsoft.com</a> ，並登入。

2. 在功能窗格中，選取 [ **端點安全性**]。

3. 在 [ **管理**] 下，選取 [ **防病毒**]。 您將會看到數個選項卡，例如 **摘要**、 **windows 10 不正常的端點**，以及 **Windows 10 偵測到惡意** 代碼。

4. 查看可用的索引標籤上的資訊，然後採取任何必要的動作。

例如，假設裝置列于 [偵測 **到 Windows 10 惡意** 代碼] 索引標籤上。當您選取裝置時，您會有特定的動作可供使用，例如 **重新開機**、 **快速掃描**、 **完整掃描**、 **同步** 處理或 **更新簽名**。 為該裝置選取動作。

下表說明您可能會在 Microsoft 端點管理員中看到的動作。<br><br>

| 動作 | 描述 |
|--|--|
| 重新啟動 | 強制 Windows 10 裝置在五分鐘內重新開機。<br><br>**重要：** 裝置擁有人或使用者不會自動通知重新開機，而且可能會遺失未儲存的工作。 |
| 快速掃描 | 在裝置上啟動快速防病毒掃描，以著重于可能會註冊惡意程式碼的常見位置，例如登錄機碼和已知的 Windows startup 資料夾。 結果會傳送至 [Microsoft 端點管理員](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 完整掃描 | 啟動裝置上的完整防病毒掃描，著重于可能會註冊惡意程式碼的常見位置，並包括裝置上的每個檔案和資料夾。 結果會傳送至 [Microsoft 端點管理員](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| Sync | 需要裝置使用 Intune (部分的 Microsoft 端點管理員) 中存回。 裝置檢入時，裝置會收到指派給裝置的任何擱置動作或原則。 |
| 更新簽名 | 需要裝置取得 [安全情報更新](https://go.microsoft.com/fwlink/?linkid=2149926) ，以進行防病毒和反惡意程式碼保護。 |

> [!TIP]
> 如需詳細資訊，請參閱 [裝置的遠端動作](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)。

## <a name="how-to-submit-a-file-for-malware-analysis"></a>如何提交檔案以進行惡意程式碼分析

如果您的檔案已錯過或誤歸類為惡意程式碼，您可以將該檔案提交給 Microsoft，以進行惡意程式碼分析。 使用者和 IT 系統管理員可以提交檔案以進行分析。 就診 [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) 。
