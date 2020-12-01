---
title: 準備工作評估工具
description: 說明工具執行的檢查及結果的意義
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e2d1c68c3fe963c957e4c3e18fce441b92c96bf1
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519818"
---
# <a name="readiness-assessment-tool"></a>準備工作評估工具

若要在 Microsoft 受管理的電腦上登錄時產生最平滑的可能體驗，您必須預先設定許多設定及其他參數。 您可以使用此工具檢查這些設定，並取得修復任何非正確步驟的詳細步驟。

工具會檢查 Microsoft 端點管理員中的設定 (具體地說，Microsoft Intune) ，Azure Active Directory (Azure AD) 和 Microsoft 365，以確保它們能夠與 Microsoft 受管理的電腦搭配使用。 在您上次於 Azure AD 組織 (租使用者) 中執行檢查後，Microsoft 受管理的桌面會保留與這些檢查相關的資料。 12個月後，我們會將它保留在解除識別的表單中。  您可以選擇刪除我們收集的資料。

具有至少 Intune 系統管理員角色的任何人都可以執行此工具，但是兩個檢查 (條件式 [存取原則](readiness-assessment-fix.md#conditional-access-policies) 和 [多重要素驗證](readiness-assessment-fix.md#multi-factor-authentication) 都需要額外的許可權。
 
評估工具會檢查下列專案：

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

|檢查  |描述  |
|---------|---------|
|Autopilot 部署設定檔     | 驗證 Autopilot 部署設定檔的指派是否不會套用到所有的裝置 (設定檔 *不應該指派* 給任何 Microsoft 受管理的桌面裝置。 )        |
|憑證連接器     | 檢查憑證連接器的狀態，以確保它們為作用中狀態。   |
|條件式存取     | 驗證是否 *未將條件* 式存取原則指派給所有使用者 (條件式存取原則不得指派給 Microsoft Managed Desktop 服務帳戶。 )     |
|裝置合規性原則     | 檢查是否未將 Intune 規範原則指派給所有使用者 (*不* 應該將原則指派給任何 Microsoft 受管理的桌面裝置。 )     |
|裝置設定檔     | 確認設定設定檔並未指派給所有的使用者或所有裝置 (設定檔 *不* 應該指派給任何 Microsoft 受管理的桌面裝置。 )      |
|裝置類型限制     | 檢查您組織中的 Windows 10 裝置是否可在 Intune 中註冊        |
|註冊狀態頁面     | 確認未啟用 [註冊狀態] 頁面      |
|Intune 登記     | 驗證 Azure AD 組織中的 Windows 10 裝置是否已自動註冊于 Intune 中         |
|商務用 Microsoft Store     | 確認已啟用商務用 Microsoft Store，且已與 Intune 同步處理        |
|多重要素驗證 | 驗證是否對 Microsoft Managed Desktop service 帳戶套用多重要素驗證。
|PowerShell 腳本     | 檢查 Windows PowerShell 腳本的指派方式， *不* 是以 Microsoft 受管理的電腦裝置為目標    |
|區域     | 檢查 Microsoft Managed Desktop 是否支援您的地區        |
|安全性基準     | 檢查安全性基準設定檔不是以所有使用者或所有裝置為目標。 (安全性基準原則 *不* 應以任何 Microsoft 受管理的桌面裝置為目標。 )        |
|Windows 應用程式     | 複查您要指派給 Microsoft 受管理的桌面裝置的應用程式      |
|Windows Hello 企業版     | 檢查是否已啟用 Windows Hello 企業版        |
|Windows 10 更新環     | 檢查 Intune 的「Windows 10 更新環路」原則並非針對所有使用者或所有裝置 (原則不得以任何 Microsoft 受管理的電腦裝置 *為目標。* )      |


## <a name="azure-active-directory-settings"></a>Azure Active Directory 設定

|檢查  |描述  |
|---------|---------|
|企業狀態漫遊的「Ad hoc」訂閱     | 建議您如何檢查是否 (如果設定為 "false" ) 設定為 "false" 可使企業狀態漫遊無法正常運作  |
|企業狀態漫遊     | 建議如何檢查是否已啟用企業狀態漫遊       |
|授權     | 檢查您是否已取得必要的 [授權](prerequisites.md#more-about-licenses)         |
|多重要素驗證     | 檢查多重要素驗證未套用至所有使用者 (多重要素驗證不得意外套用至 Microsoft Managed Desktop service 帳戶。 ) |
|安全性帳戶名稱   | 檢查沒有任何使用者名稱與 Microsoft Managed 桌面保留以供自己使用的使用者名稱衝突        |
|安全性管理員角色     | 確認具有安全性讀取者、安全性操作員或全域讀取者角色的使用者已在 Microsoft Defender for Endpoint 中指派這些角色。         |
|安全性預設 | 檢查您的 Azure AD 組織是否已在 Azure Active Directory 中啟用安全性預設值 |
|自助式密碼重設     | 確認已啟用自助密碼重設        |
|標準使用者角色     | 驗證使用者是標準使用者且不具備本機系統管理員許可權         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 應用程式的企業版設定

|檢查  |描述  |
|---------|---------|
|商務用 OneDrive     | 檢查商務用 OneDrive 是否使用不支援的設定。        |


針對每個檢查，該工具會報告下列四個可能的結果之一：


|結果  |意義  |
|---------|---------|
|就緒     | 完成註冊之前，不需要執行任何動作。        |
|諮詢    | 請遵循工具中的步驟，以取得註冊和使用者的最佳體驗。 您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。        |
|未就緒 | 如果您未修正這些問題，*註冊將會失敗*。 請遵循工具中的步驟加以解決。        |
|錯誤 | 您所使用的 Azure Active Director (AD) 角色，沒有足夠的許可權可執行這種檢查。 |
