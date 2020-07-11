---
title: 自行註冊新裝置
description: 自行註冊裝置，以便由 Microsoft 受管理的電腦管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 3c43c42ba2cb1feb339ad61b76d28fde4ed94298
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101656"
---
# <a name="register-new-devices-yourself"></a>自行註冊新裝置

Microsoft 受管理的電腦可搭配全新的裝置運作，或您可重複使用您可能已經擁有的裝置 (這需要您重新製作其映像)。 您可以使用 Microsoft Managed Desktop Admin 入口網站來註冊裝置。

> [!NOTE]
> 與合作夥伴合作來取得裝置嗎？ 若是如此，您就不需要擔心取得硬體雜湊，他們會為您處理。 請確定您的夥伴已在 [夥伴中心](https://partner.microsoft.com/dashboard)與您建立關聯。 您的合作夥伴可在 [合作夥伴中心說明](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)深入了解。 建立這種關聯性後，您的合作夥伴就會代表您直接註冊裝置，您不須採取任何進一步動作。 如果您想要查看詳細資料，或您的合作夥伴有疑問，請參閱[可供合作夥伴註冊裝置的步驟](register-devices-partner.md)。 註冊好裝置後，您可以繼續[檢查映像](#check-the-image)並[將裝置交付](#deliver-the-device)給您的使用者。

## <a name="prepare-to-register-brand-new-devices"></a>準備註冊全新的裝置


在您擁有新的裝置後，您會依照下列步驟執行：

1. [取得每個裝置的硬體雜湊。](#obtain-the-hardware-hash)
2. [合併雜湊資料](#merge-hash-data)
3. [在 Microsoft 受管理的電腦中註冊裝置](#register-devices)。
4. [再次確認映像是否正確。](#check-the-image)
5. [交付裝置](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>取得硬體雜湊

Microsoft 受管理的電腦會藉由參照其硬體雜湊來唯一識別每個裝置。 您有三種選項可取得此資訊：

- 請向您的 OEM 提供者索取 AutoPilot 註冊檔案，其中會包含硬體雜湊。
- 在每個裝置上執行 [Windows PowerShell 指令碼](#powershell-script-method)，並收集檔案中的結果。
- 啟動每個裝置 (但不要完成 Windows 設定體驗)，然後[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。

#### <a name="powershell-script-method"></a>PowerShell 指令碼方法

1.  以系統管理權限開啟 PowerShell 提示字元。
2.  執行 `Install-Script -Name Get-MMDRegistrationInfo`
3.  執行 `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`

#### <a name="flash-drive-method"></a>快閃磁碟機方法

1. 在您要註冊的裝置以外的裝置上，插入 USB 磁碟機。
2. 以系統管理權限開啟 PowerShell 提示字元。
3. 執行 `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. 開啟您要註冊的裝置，但*請勿開始設定體驗*。 如果您不小心開始設定體驗，則必須重設裝置或重新製作其映像。
5. 插入 USB 磁碟機，然後按 SHIFT + F10。
6. 以系統管理權限開啟 PowerShell 提示字元，然後執行 `cd <pathToUsb>`。
7. 執行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 執行 `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. 移除 USB 磁碟機，然後執行 `shutdown -s -t 0` 以關閉裝置

>[!IMPORTANT]
>在您完成註冊前，請勿開啟您所註冊的裝置。 


### <a name="merge-hash-data"></a>合併雜湊資料

您必須將 CSV 檔案中的資料合併成單一檔案，才能完成註冊。 以下是讓註冊變輕鬆的範例 PowerShell 指令碼：

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a>註冊裝置

CSV 檔案必須採用可供註冊的特定格式。 如果您在先前步驟中自行收集了資料，檔案應該已經是正確的格式。如果您是向供應商取得檔案，則可能需要調整格式。

>[!NOTE]
>為方便您使用，您可以下載[範例 CSV](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)檔案。

您的檔案必須包含**完全相同的欄標題**作為範例一 (製造商、型號等)，但您自己的資料適用於其他列。 如果您使用範本，請在記事本這類的文字編輯工具中開啟範本，然後不妨將列 1 的所有資料維持原狀，只在列 2 以下輸入資料。 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>如果您忘記變更任何範例資料，註冊將會失敗。

#### <a name="register-devices-by-using-the-admin-portal"></a>使用管理入口網站註冊裝置

從 Microsoft Managed Desktop [Admin 入口網站](https://aka.ms/mmdportal)的左側流覽窗格中，選取 [**裝置**]。 選取 [+ 註冊裝置]****；飛入視窗隨即開啟：

[![在選取 [註冊裝置] 之後飛入，並列出裝置與已指派使用者、序號、狀態、上次查看日期和年限等欄](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (事實並非如此。我們可以移除此注意事項 - 但現在暫且擱置，留待我們有機會討論。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


請遵循下列步驟：

1. 在 [檔案上傳]**** 中，提供您先前建立的 CSV 檔案路徑。
2. 或者，您可以新增 [訂單識別碼]**** 或 [購買識別碼]****，以便自行追蹤。 這些值沒有格式需求。
3. 選取 [註冊裝置]****。 系統會將裝置新增至 [裝置] 刀鋒視窗**** 上標示為 [註冊擱置]**** 的裝置清單。 註冊通常需要不到 10 分鐘的時間，而註冊成功時，裝置將會顯示為 [使用者就緒]****，標示其已準備就緒並等待終端使用者開始使用。


您可以在主要 [Microsoft 受管理的電腦 - 裝置]**** 頁面上監視裝置註冊的進度。 其回報的可能狀態包括：

| 狀態 | 描述 |
|---------------|-------------|
| 註冊擱置 | 尚未完成註冊。 稍後再回頭檢查。 |
| 註冊失敗 | 無法完成註冊。 如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](#troubleshooting-device-registration)。 |
| 使用者就緒 | 註冊成功，且裝置現在已準備好交付給使用者。 Microsoft 受管理的電腦將會逐步引導使用者完成首次設定，因此您不需要再做任何進一步的準備。 |
| 作用中 | 裝置已交付給終端使用者並已向您的租用戶註冊。 這也表示使用者經常使用該裝置。 |
| 非作用中 | 裝置已交付給終端使用者並已向您的租用戶註冊。 不過，使用者最近尚未使用裝置 (在過去 7 天內)。  | 

#### <a name="troubleshooting-device-registration"></a>針對裝置註冊進行疑難排解

| 錯誤訊息 | 詳細資料 |
|---------------|-------------|
| 找不到裝置 | 我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。 請與您的裝置供應商確認這些值。 |
| 硬體雜湊無效 | 您為這個裝置提供的硬體雜湊格式不正確。 再次確認硬體雜湊，然後重新提交。 |
| 裝置已經註冊 | 此裝置已經註冊到您的組織。 無需採取任何動作。 |
| 其他組織所宣告的裝置 | 此裝置已經由其他組織所宣告。 請洽詢您的裝置供應商。 |
| 未預期的錯誤 | 無法自動處理您的要求。 連絡客戶支援並提供要求識別碼：<requestId> |

### <a name="check-the-image"></a>檢查映像

如果您的裝置來自 Microsoft 受管理的電腦合作夥伴供應商，映射應是正確的。

如果您想要的話，也歡迎您自行套用映像。 若要開始使用，請連絡您的 Microsoft 代表，他們會將映像的位置及其套用步驟提供給您。

### <a name="deliver-the-device"></a>交付裝置

> [!IMPORTANT]
> 將裝置交給使用者之前，請確認您已取得並套用[適合該使用者的授權](../get-ready/prerequisites.md)。

如果已套用所有授權，您可以[讓使用者準備好使用裝置](get-started-devices.md)，然後使用者即可啟動裝置並繼續進行 Windows 設定體驗。






