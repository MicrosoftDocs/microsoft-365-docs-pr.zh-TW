---
title: 備備評定工具
description: 說明這兩項工具，即其執行檢查，以及結果的意義
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9fbd24185288265d698288e0d5e63e8b3c2afd10
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921843"
---
# <a name="readiness-assessment-tools"></a>備備評定工具

為了在註冊 Microsoft Managed Desktop 時獲得最順暢的體驗，您必須提前設定設定及其他參數，以及滿足特定裝置和網路需求。 透過 Microsoft Managed Desktop Admin 入口網站存取的一項工具會檢查管理相關設定。 另一個可下載的工具會檢查個別裝置需求與網路設定。 您可以使用這些工具檢查這些設定，並收到修正任何錯誤專案的詳細步驟。

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>可下載的裝置與網路的備查檢查程式

有關使用可下載的立即性評定檢查程式的詳細資訊，請參閱 [可下載的備備評定檢查程式](readiness-assessment-downloadable.md)。

## <a name="online-readiness-assessment-tool-for-management-settings"></a>管理設定的線上備備評定工具

線上工具會檢查 Microsoft Endpoint Manager (中的設定，特別是 Microsoft Intune) 、Azure Active Directory (Azure AD) 和 Microsoft 365，以確保它們能與 Microsoft Managed Desktop 一起使用。 Microsoft Managed Desktop 會保留與這些檢查相關聯的資料 12 個月，這是您上次在 Azure AD 組織或租使用者 (執行檢查後) 。 12 個月後，我們會保留其為識別狀態。 您可以選擇刪除我們收集的資料。

擁有 Intune 系統管理員角色的任何人都可以執行此工具，但其中兩項檢查需要 (存取策略和多重要素驗證時[](readiness-assessment-fix.md#conditional-access-policies)需要額外許可權。 [](readiness-assessment-fix.md#multifactor-authentication)
 
評定工具會檢查這些專案：

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

|支票  |說明  |
|---------|---------|
|Autopilot 部署設定檔     | 確認指派的 Autopilot 部署設定檔並未適用于所有裝置 (設定檔不應指派給任何 Microsoft 管理桌面裝置。)        |
|憑證連接器     | 檢查憑證連接器的狀態以確保它們為使用中   |
|條件式存取     | 驗證條件式存取策略並未指派給所有使用者 (條件式存取策略不應指派給 Microsoft  Managed Desktop 服務帳戶。)     |
|裝置合規性政策     | 檢查未將 Intune 合規性策略指派給所有使用者 (不應該將這個策略指派給任何Microsoft Managed Desktop 裝置。)     |
|裝置組配置設定檔     | 確認系統並未將設定檔指派給所有使用者，或系統 (設定檔的所有裝置均不應指派給任何 Microsoft受管理的桌面裝置。)      |
|裝置類型限制     | 檢查您組織的 Windows 10 裝置是否獲准在 Intune 註冊        |
|註冊狀態頁面     | 確認未啟用註冊狀態頁面      |
|Intune 註冊     | 驗證您的 Azure AD 組織中已自動在 Intune 註冊 Windows 10 裝置         |
|商務用 Microsoft Store     | 確認已啟用商務用 Microsoft Store 並同步處理 Intune        |
|多重要素驗證 | 驗證多重要素驗證未適用于 Microsoft Managed Desktop 服務帳戶。
|PowerShell 腳本     | 檢查 Windows PowerShell腳本的指派方式是否未以 Microsoft Managed Desktop 裝置為目標    |
|地區     | 檢查您的地區是否受 Microsoft 管理桌面支援        |
|安全性比較基準     | 檢查安全性比較基準設定檔未以所有使用者或安全性基準 (的目標，不應以任何 Microsoft Managed Desktop裝置為目標。)        |
|Windows 應用程式     | 查看您想要指派給 Microsoft 受管理桌面裝置的應用程式      |
|Windows Hello 企業版     | 檢查已啟用商務用 Windows Hello        |
|Windows 10 更新鈴聲     | 檢查 Intune 的「Windows 10 更新環」策略未以所有使用者或所有裝置為目標 (該策略不應該以任何Microsoft 管理的桌面裝置為目標。)      |


## <a name="azure-active-directory-settings"></a>Azure Active Directory 設定

|支票  |說明  |
|---------|---------|
|企業狀態漫遊的「臨時」訂閱     | 建議如何檢查設定，如果 (為 false"，) 企業狀態漫遊無法正確執行  |
|企業狀態漫遊     | 建議如何檢查是否已啟用企業狀態漫遊       |
|授權     | 檢查您是否已取得所需的 [授權](prerequisites.md#more-about-licenses)         |
|多重要素驗證     | 檢查多重要素驗證未對所有使用者 (多重要素驗證不可意外地應用至 Microsoft Managed Desktop 服務帳戶。) |
|安全性帳戶名稱   | 檢查使用者名稱與 Microsoft Managed Desktop 保留供自己使用的使用者名稱沒有衝突        |
|安全性系統管理員角色     | 確認具有安全性讀取者、安全性運算子或全域讀取者角色的使用者在 Microsoft Defender for Endpoint 中已指派這些角色         |
|安全性預設 | 檢查 Azure AD 組織是否已在 Azure Active Directory 中啟用安全性預設值 |
|自助式密碼重設     | 確認已啟用自助密碼重設        |
|標準使用者角色     | 確認使用者是標準使用者，而且沒有本地系統管理員許可權         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>適用于企業設定之 Microsoft 365 應用程式

|支票  |說明  |
|---------|---------|
|商務用 OneDrive     | 檢查商務用 OneDrive 是否使用不支援的設定。        |


工具會針對每項檢查報告四種可能的結果之一：


|結果  |意義  |
|---------|---------|
|就緒     | 完成註冊之前，無需執行任何動作。        |
|諮詢    | 請遵循工具中的步驟，為註冊和使用者提供最佳使用體驗。 您可以 *完成* 註冊，但必須在部署第一個裝置之前修正這些問題。        |
|未就緒 | *如果您沒有修正這些問題* ，註冊將會失敗。 請遵循工具中的步驟來解決問題。        |
|錯誤 | 使用 Azure Active Director (AD) 角色沒有足夠的許可權可以執行這項檢查。 |

## <a name="after-enrollment"></a>註冊之後

在 Microsoft Managed Desktop 中完成註冊後，請記得返回並調整特定的 Intune 和 Azure AD 設定。 詳情請參閱註冊 [後的調整設定](../get-started/conditional-access.md)。
