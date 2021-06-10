---
title: 調查代理程式健康狀況問題
description: 瞭解執行 mdatp health 命令時所傳回的值
keywords: mdatp health，command，health，status，command，上架狀態
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
ms.openlocfilehash: acc75a931cb14a7aab729c09a7b835fb9f26d1d1
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281111"
---
# <a name="investigate-agent-health-issues"></a>調查代理程式健康狀況問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


下表提供當您執行命令及其對應的描述時，所傳回的值的相關資訊 `mdatp health` 。

| 值 | 描述 |
|-|-|
| automatic_definition_update_enabled | True 是表示如果啟用自動防病毒定義更新，否則為 false。 |
|  cloud_automatic_sample_submission_consent | 目前範例提交層級。 可以是下列其中一個值：     <br><br>  - **None**：沒有可疑的範例提交給 Microsoft。  <br> <br>     - **安全**：只有不含個人身分識別資訊 (PII) 的可疑範例會自動提交。 此為此設定的預設值。    <br> <br>   - **All**：將所有可疑的範例提交給 Microsoft。   |
| cloud_diagnostic_enabled | True 是表示如果啟用選用的診斷資料收集，否則為 false。 如需與 Defender for Endpoint 及其他產品及服務如 Microsoft Defender 防毒軟體和 Windows 10 相關的詳細資訊，請參閱[Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=827576)。 |
| cloud_enabled | True 是表示如果已啟用雲端傳遞的保護，否則為 false。 |
| conflicting_applications | 與 Microsoft Defender for Endpoint 可能衝突的應用程式清單。 此清單包含（但不限於）其他安全性產品及其他已知導致相容性問題的應用程式。 |
| definitions_status | 防病毒定義的狀態。 |
| definitions_updated | 上次防病毒定義更新的日期和時間。 |
| definitions_updated_minutes_ago | 自上次防病毒定義更新以來的分鐘數。 |
| definitions_version | 防病毒定義版本。 |
| edr_client_version | 在裝置上執行的 EDR 用戶端版本。 |
| edr_configuration_version | EDR 設定版本。 |
| edr_device_tags | 與裝置相關聯的標記清單。 |
| edr_group_ids | 裝置關聯的群組識別碼。 |
| edr_machine_id | 用於 Microsoft Defender 資訊安全中心的裝置識別碼。 |
| engine_version | 防病毒引擎的版本。 |
| 健康 | True 是表示如果產品狀況良好，否則為 false。 |
| 許可 | True 是表示如果裝置架至租使用者，否則為 false。 |
| log_level | 產品的目前記錄層級。 |
| machine_guid | 防病毒元件使用的唯一電腦識別碼。 |
| network_protection_status                 | 網路保護元件的狀態 (僅限 macOS) 。 可以是下列其中一個值：       <br> <br>- 正在 **啟動** 網路保護  <br> <br>     - 由於發生錯誤，無法啟動 **failed_to_start** 網路保護   <br> <br>    - **已啟動** -目前正在裝置上執行網路保護     <br> <br>  - **重新開機** -現在已重新開機網路保護   <br> <br>    - 正在 **停止** 網路保護     <br> <br>  - **已停止** -未執行網路保護 |
| org_id | 裝置架的組織。 如果裝置尚未架至任何組織，將無法使用此列印。 如需上架的詳細資訊，請參閱 [板載 To Microsoft Defender For Endpoint](onboarding.md)。 |
| passive_mode_enabled | True 是表示如果防病毒元件已設定為以被動模式執行; 否則為 false。 |
| product_expiration | 目前產品版本到達支援終止的日期和時間。 |
| real_time_protection_available | True 是表示如果即時保護元件狀況良好，否則為 false。 |
| real_time_protection_enabled | True 是表示如果啟用即時防防毒保護，否則為 false。 |
| real_time_protection_subsystem | 子系統用來提供即時保護。 如果即時保護未如預期運作，將無法使用此列印。 |
| release_ring | 放開鈴聲。 如需詳細資訊，請參閱   [部署環](deployment-rings.md)。 |