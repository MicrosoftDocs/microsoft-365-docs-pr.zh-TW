---
title: 讓合作夥伴註冊裝置的步驟
description: 如何合作夥伴可以註冊裝置，可由 Microsoft 受管理的電腦
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a9a2a0ccb1e0830d674f4b1b1ef5495fafb38ca3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596550"
---
# <a name="steps-for-partners-to-register-devices"></a>讓合作夥伴註冊裝置的步驟


本主題說明適用於要遵循註冊裝置的合作夥伴的步驟。 自行註冊裝置的程序會詳細說明[自行註冊 Microsoft 受管理電腦中的裝置](register-devices-self.md)。



## <a name="prepare-for-registration"></a>準備註冊 
完成之前註冊為客戶，您必須先建立與其[合作夥伴中心](https://partner.microsoft.com/dashboard)的關係。 請務必選取 [**包含委派管理 Azure Active Directory 和 Office 365 的權限**。 深入瞭解[合作夥伴中心的說明](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)。

若要完成註冊您的客戶，請先建立 CSV 檔案。

>[!NOTE]
>以方便您使用，您可以下載[範例 CSV 檔](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)此*協力廠商版本*。

您的檔案必須包含**完全相同的欄標題**作為範例一 (製造商、型號等)，但您自己的資料適用於其他列。 如果您使用範本，請在記事本這類的文字編輯工具中開啟範本，然後不妨將列 1 的所有資料維持原狀，只在列 2 以下輸入資料。 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
>這種格式是僅供合作夥伴程序。 自助註冊的程序會詳細說明[自行註冊 Microsoft 受管理電腦中的裝置](register-devices-self.md)。

>[!IMPORTANT]
>這些值必須 SMBIOS 的製造商值完全相符，包括大小寫和特殊字元。 

- 裝置製造商 (範例： SpiralOrbit) 
- 裝置型號 (範例： ContosoABC)
- 裝置序號

## <a name="register-devices-by-using-the-azure-portal"></a>使用 Azure 入口網站來註冊裝置

除了在入口網站存取不同註冊使用 Azure 入口網站是與自助，相同。 請遵循下列步驟：

1. 瀏覽至[合作夥伴中心](https://partner.microsoft.com/dashboard)
2. 選取 [**客戶**]。
3. 選取您想要管理的客戶。
4. 選取 [**服務管理**]。
5. 選取 [ **Intune**]。
6. 搜尋 「 mmd 」 在上方的搜尋方塊中的 Azure 入口網站。
7. 選取 [**裝置**]。
8. 在 [檔案上傳]**** 中，提供您先前建立的 CSV 檔案路徑。
9. 或者，您可以新增 [訂單識別碼]**** 或 [購買識別碼]****，以便自行追蹤。 這些值沒有格式需求。
10. 選取 [註冊裝置]****。 系統會將裝置新增至 [裝置] 刀鋒視窗**** 上標示為 [註冊擱置]**** 的裝置清單。 註冊通常需要不到 10 分鐘的時間，而註冊成功時，裝置將會顯示為 [使用者就緒]****，標示其已準備就緒並等待終端使用者開始使用。


您可以在主要 [Microsoft 受管理的電腦 - 裝置]**** 頁面上監視裝置註冊的進度。 其回報的可能狀態包括：

| 狀態 | 描述 |
|---------------|-------------|
| 註冊擱置 | 尚未完成註冊。 稍後再回頭檢查。 |
| 註冊失敗 | 無法完成註冊。 如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](register-devices-self.md#troubleshooting-device-registration)。 |
| 使用者就緒 | 註冊成功，且裝置現在已準備好交付給使用者。 Microsoft 受管理的電腦將會逐步引導使用者完成首次設定，因此您不需要再做任何進一步的準備。 |
| 作用中 | 裝置已交付給終端使用者並已向您的租用戶註冊。 這也表示使用者經常使用該裝置。 |
| 非作用中 | 裝置已交付給終端使用者並已向您的租用戶註冊。 不過，使用者最近尚未使用裝置 (在過去 7 天內)。  |



## <a name="troubleshooting"></a>疑難排解

| 錯誤訊息 | 詳細資料 |
|---------------|-------------|
| 找不到裝置 | 我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。 請與您的裝置供應商確認這些值。 |
| 硬體雜湊無效 | 您為這個裝置提供的硬體雜湊格式不正確。 再次確認硬體雜湊，然後重新提交。 |
| 裝置已經註冊 | 此裝置已經註冊到您的組織。 無需採取任何動作。 |
| 其他組織所宣告的裝置 | 此裝置已經由其他組織所宣告。 請洽詢您的裝置供應商。 |
| 未預期的錯誤 | 無法自動處理您的要求。 連絡客戶支援 (<support link>)，並提供 「 要求識別碼：<requestId> |
