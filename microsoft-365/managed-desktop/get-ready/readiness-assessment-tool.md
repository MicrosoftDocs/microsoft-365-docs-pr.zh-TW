---
title: 準備工作評估工具
description: 說明兩個工具、執行的檢查及結果的意義
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: caf9274284548a179e088131930ae832c098b521
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579395"
---
# <a name="readiness-assessment-tools"></a>準備工作評估工具

若要在 Microsoft 受管理的電腦中註冊時，最平滑的可能體驗，有一些設定及其他參數您必須預先設定，以及符合特定裝置和網路需求。 透過 Microsoft 受管理的電腦管理員入口網站存取的一個工具，會檢查與管理相關的設定。 另一種可供下載的工具會檢查個別裝置需求和網路設定。 您可以使用這些工具檢查這些設定，並取得修復任何非正確步驟的詳細步驟。

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>裝置和網路的可下載準備工作評估檢查

如需使用可下載的準備事項評估檢查程式的詳細資訊，請參閱 [可下載的準備事項評估檢查](readiness-assessment-downloadable.md)程式。

## <a name="online-readiness-assessment-tool-for-management-settings"></a>適用于管理設定的線上準備工作評估工具

[線上工具](https://aka.ms/mmdart)會在 Microsoft 端點管理員中檢查設定 (具體而言，Microsoft Intune) 、Azure Active Directory (Azure AD) 和 Microsoft 365，以確保它們可以搭配 Microsoft 受管理的電腦使用。 Microsoft 受管理的電腦會在您上次於 Azure AD 組織 (承租人) 中執行檢查後，保留與這些檢查相關聯的資料。 12個月後，我們會將它保留在解除識別的表單中。 您可以選擇刪除我們收集的資料。

任何至少具有全域讀取者或 Intune 系統管理員角色的人員，都可以執行此工具，但是兩個檢查 ([條件式存取原則](readiness-assessment-fix.md#conditional-access-policies) 和 [多重要素驗證](readiness-assessment-fix.md#multifactor-authentication) 都需要額外的許可權。
 
評估工具會檢查下列專案：

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

|支票  |描述  |
|---------|---------|
|Autopilot 部署設定檔     | 驗證 Autopilot 部署設定檔的指派是否不會套用至所有裝置 (設定檔不 *應該指派* 給任何 Microsoft 受管理的電腦裝置。 )        |
|憑證連接器     | 檢查憑證連接器的狀態，以確保它們為作用中狀態。   |
|條件式存取     | 確認未將條件式存取原則指派給所有使用者 (條件式存取原則 *不* 應該指派給 Microsoft 受管理的電腦服務帳戶。 )     |
|裝置合規性原則     | 檢查未將 Intune 規範原則指派給所有使用者 (*不* 應該將原則指派給任何 Microsoft 受管理的電腦裝置。 )     |
|裝置設定檔     | 確認設定設定檔並未指派給所有的使用者或所有裝置 (設定檔 *不* 應該指派給任何 Microsoft 受管理的電腦裝置。 )      |
|裝置類型限制     | 檢查您的組織中 Windows 10 裝置是否允許在 Intune 中註冊        |
|註冊狀態頁面     | 確認未啟用 [註冊狀態] 頁面      |
|Intune 登記     | 驗證您的 Azure AD 組織中的 Windows 10 裝置是否會自動註冊于 Intune 中         |
|商務用 Microsoft Store     | 確認商務用 Microsoft Store 已啟用並與 Intune 同步處理        |
|多重要素驗證 | 驗證不會對 Microsoft 受管理的電腦服務帳戶套用多重驗證。
|PowerShell 腳本     | 檢查 Windows PowerShell *腳本是否以* 以 Microsoft 受管理的電腦裝置為目標的方式指派    |
|區域     | 檢查 Microsoft 受管理的電腦是否支援您的地區        |
|安全性基準     | 檢查安全性基準設定檔不是以所有的使用者或所有裝置為目標。 (安全性基準原則 *不* 應以任何 Microsoft 受管理的電腦裝置為目標。 )        |
|Windows 應用程式     | 複查您要指派給 Microsoft 受管理的電腦裝置的應用程式      |
|Windows Hello 企業版     | 檢查 Windows 是否已啟用 Hello 企業版        |
|Windows 10 更新鈴聲     | 檢查 Intune 的「Windows 10 更新鈴聲」原則不是以所有使用者或所有裝置為目標 (原則 *不* 應以任何 Microsoft 受管理的電腦裝置為目標。 )      |


## <a name="azure-active-directory-settings"></a>Azure Active Directory 設定

|支票  |描述  |
|---------|---------|
|Enterprise 狀態漫遊的「Ad hoc」訂閱     | 建議您如何檢查設定為 "false" 的設定 () 可能會使 Enterprise 狀態漫遊無法正常運作  |
|企業狀態漫遊     | 建議如何檢查是否已啟用 Enterprise 狀態漫遊       |
|授權     | 檢查您是否已取得必要的 [授權](prerequisites.md#more-about-licenses)         |
|多重要素驗證     | 檢查是否所有使用者都未套用多重要素驗證 (多重因素驗證不得意外套用到 Microsoft 受管理的電腦服務帳戶。 ) |
|安全性帳戶名稱   | 檢查沒有任何使用者名稱與 Microsoft 受管理的電腦保留以供自己使用的使用者名稱衝突        |
|安全性管理員角色     | 確認具有安全性讀取者、安全性操作員或全域讀取者角色的使用者已在 Microsoft Defender for Endpoint 中指派這些角色。         |
|安全性預設 | 檢查您的 Azure AD 組織是否已在 Azure Active Directory 中啟用安全性預設值 |
|自助式密碼重設     | 確認已啟用自助密碼重設        |
|標準使用者角色     | 驗證使用者是標準使用者且不具備本機系統管理員許可權         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 Apps 企業版設定

|支票  |描述  |
|---------|---------|
|商務用 OneDrive     | 檢查商務用 OneDrive 是否使用不支援的設定。        |


針對每個檢查，該工具會報告下列四個可能的結果之一：


|結果  |意義  |
|---------|---------|
|就緒     | 完成註冊之前，不需要執行任何動作。        |
|公告    | 請遵循工具中的步驟，以取得註冊和使用者的最佳體驗。 您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。        |
|未就緒 | 如果您未修正這些問題，*註冊將會失敗*。 請遵循工具中的步驟加以解決。        |
|錯誤 | 您所使用的 Azure Active Director (AD) 角色，沒有足夠的許可權可執行這種檢查。 |

## <a name="after-enrollment"></a>註冊後

在 Microsoft 受管理的電腦中完成註冊後，請先回復並調整特定的 Intune 和 Azure AD 設定。 如需詳細資訊，請參閱 [在登記後調整設定](../get-started/conditional-access.md)。

## <a name="steps-to-get-ready"></a>準備就緒的步驟

1. 檢閱 [Microsoft 受管理的電腦的先決條件](prerequisites.md)。
2. 使用[整備評估工具](readiness-assessment-tool.md)。  (本文) 
3. [來賓帳戶的先決條件](guest-accounts.md)
4. [Microsoft 受管理的電腦的網路設定](network.md)
5. [為 Microsoft 受管理的電腦準備認證和網路設定檔](certs-wifi-lan.md)
6. [為 Microsoft 受管理的電腦準備內部部署資源存取](authentication.md)
7. [Microsoft 受管理的電腦中的應用程式](apps.md)
8. [為 Microsoft 受管理的電腦準備對應磁碟機](mapped-drives.md)
9. [為 Microsoft 受管理的電腦準備列印資源](printing.md)
