---
title: Microsoft 受管理電腦中註冊裝置的合作夥伴
description: 如何合作夥伴可以註冊裝置，可由 Microsoft 受管理的電腦
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 06ec98ebc7ea44a1bf3d8039e3a3ab7102521d3e
ms.sourcegitcommit: ef749c44d72b5258706be86a4af1aeca4154ead2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "35447525"
---
# <a name="register-devices-in-microsoft-managed-desktop-for-partners"></a>Microsoft 受管理電腦中註冊裝置的合作夥伴


本主題說明適用於要遵循註冊裝置的合作夥伴的步驟。 自行註冊裝置的程序會詳細說明[自行註冊 Microsoft 受管理電腦中的裝置](register-devices-self.md)。



## <a name="prepare-for-registration"></a>準備註冊 
完成之前註冊為客戶，您必須先建立與其[合作夥伴中心](https://partner.microsoft.com/dashboard)的關係。 請務必選取 [**包含委派管理 Azure Active Directory 和 Office 365 的權限**。 深入瞭解[合作夥伴中心的說明](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer)。

若要完成註冊您的客戶，請先建立 CSV 檔案。

>[!NOTE]
>以方便您使用，您可以下載[範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx)此*協力廠商版本*的 CSV 檔案。

您的檔案必須包含**完全相同的欄名**為其中一個範例 （製造商、 型號、 等），但您自己的資料列的資料。 如果您使用的範本，在編輯 [記事本] 之類的文字中開啟，並且考慮離開的所有資料列 1 單獨中的，只輸入資料，資料列 2 中下, 面。 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```


>[!NOTE]
>這種格式是僅供合作夥伴程序。 自助註冊的程序會詳細說明[自行註冊 Microsoft 受管理電腦中的裝置](register-devices-self.md)。

>[!IMPORTANT]
>這些值必須完全符合 SMBIOS 的製造商值。 您也必須包含*硬體雜湊*中的第一列 （但沒有值的它的第二列） 結尾的逗點之後的第二列的*序號*值。

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
8. 在 [**檔案上傳**，提供您先前建立的 CSV 檔案的路徑。
9. （選用） 您可以新增**順序識別碼**或**購買識別碼**自己追蹤的目的。 沒有這些值的格式需求。
10. 選取 [**註冊的裝置**]。 系統會將裝置新增至您的**裝置] 刀鋒視窗中**，標示為 [**擱置中註冊**裝置的清單。 註冊通常採用小於 10 分鐘，並成功時裝置將會顯示為**使用者準備**這很好，等待使用者開始使用。


您可以監視進度的主要**Microsoft 受管理電腦的 [裝置**] 頁面上的裝置註冊。 報告那里可能的狀態包括：

| 狀態 | 描述 |
|---------------|-------------|
| 註冊暫止 | 註冊未尚未完成。 請稍後再回來。 |
| 註冊失敗 | 無法完成註冊。 如需詳細資訊，請參閱[疑難排解](register-devices-self.md#troubleshooting)。 |
| 準備使用者 | 註冊成功，而且裝置已準備好要傳遞給使用者。 Microsoft 受管理的電腦會逐步引導其第一次 」 設定，因此不需要為您進行任何進一步的準備工作。 |
| Active | 裝置已經傳送給使用者，他們必須註冊您的租用戶。 這也表示他們定期使用裝置。 |
| 非使用中 | 裝置已經傳送給使用者，他們必須註冊您的租用戶。 不過，他們有不適用於裝置最近 （過去 7 天）。  |

## <a name="register-devices-by-using-an-api"></a>使用 API 來註冊裝置

註冊 API 等同於自助，不同之處在於裝置集合的硬體雜湊屬性是選用的 CSV 一節所述。 

## <a name="troubleshooting"></a>疑難排解

| 錯誤訊息 | 詳細資料 |
|---------------|-------------|
| 找不到裝置 | 我們無法註冊此裝置，因為我們找不到相符項目提供的製造商、 模型，或序號。 與您的裝置供應商確認這些值。 |
| 找不到裝置 | 我們無法取消註冊此裝置，因為不存在於您的組織。 不再需要的動作。 |
| 不正確的硬體雜湊 | 您提供此裝置的硬體雜湊格式不正確。 請仔細檢查硬體雜湊，然後重新提交。 |
| 已註冊的裝置 | 此裝置已登錄至您的組織。 不再需要的動作。 |
| 另一個組織所宣告的裝置 | 此裝置已經被另一個組織所宣告。 請與您的裝置供應商。 |
| 未預期的錯誤 | 無法自動處理您的要求。 連絡客戶支援 (<support link>)，並提供 「 要求識別碼：<requestId> |
