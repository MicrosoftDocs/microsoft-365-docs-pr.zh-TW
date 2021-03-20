---
title: 啟用已加入網域的 Windows 10 裝置以供商務用 Microsoft 365 管理
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 瞭解如何啟用 Microsoft 365，以在幾個步驟中保護本機作用中已加入目錄的 Windows 10 裝置。
ms.openlocfilehash: 82d4ac3f1d6aba9489f9ea153de3a3d2083b47ec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913187"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>啟用已加入網域的 Windows 10 裝置以由 Microsoft 365 商務版 Premium 管理

如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版 Premium 來保護您的 Windows 10 裝置，同時仍維持對需要本機驗證的內部部署資源的存取。
若要設定此保護，您可以執行 **混合式 AZURE AD 聯結裝置**。 這些裝置會同時加入您的內部部署 Active Directory 和您的 Azure Active Directory。

這段影片說明如何針對最常見的案例設定此功能的步驟，在後續步驟中也會詳細說明。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>開始之前，請先確定您已完成下列步驟：
- 使用 Azure AD Connect 將使用者同步處理至 Azure AD。
- 完成 Azure AD Connect 組織單位 (OU) sync。
- 請確定您同步處理的所有網域使用者都具有 Microsoft 365 商務版的授權。

如需步驟，請參閱 [同步處理網域使用者至 Microsoft](manage-domain-users.md) 。

## <a name="1-verify-mdm-authority-in-intune"></a>1. 驗證 Intune 中的 MDM 授權

移至 [端點管理員](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) ，然後在 Microsoft Intune 頁面上，選取 [ **裝置註冊**]，然後在 [一覽] 頁面上，確定 **[** **MDM 授權** 為 **Intune**]。

- 如果 **mdm 授權** 單位為 **None**，請按一下 **MDM 授權** 單位將其設定為 **Intune**。
- 如果 **mdm 授權** 是 **Microsoft Office 365**，請移至 [**裝置]**  >  [**註冊裝置**]，並使用右側的 [**新增 mdm 授權機構**] 對話方塊，以加入 **Intune MDM** 授權 (只有當 **MDM 機關** 設定為 [Microsoft Office 365) 時，才可使用 [**新增 mdm 授權**] 對話方塊。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. 確認已針對加入的電腦啟用 Azure AD

- 移至系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  ，然後選取 [ **Azure active directory** (]，在 [系統 **管理中心** ] 清單中看不到 [azure active directory]) 的 [全部顯示]。 
- 在 **Azure Active directory 系統管理中心** 中，移至 [ **azure active directory** ]，選擇 [ **裝置** ]，然後選擇 [ **裝置設定**]。
- 確認 **使用者可以將裝置加入至 AZURE AD** 已啟用 
    1. 若要啟用所有使用者，請將設定為 [ **全部**]。
    2. 若要啟用特定使用者，請將設定為 [已 **選擇** ]，以啟用特定的使用者群組。
        - 將 Azure AD 中已同步處理的所需網域使用者新增至 [安全性群組](../admin/create-groups/create-groups.md)。
        - 選擇 [ **選取群組** ]，以啟用該安全性群組的 MDM 使用者範圍。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. 確認已為 MDM 啟用 Azure AD

- 移至系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  ，然後選取 [Select **endpoint Managemen** t (選取 [ **顯示所有** if **端點管理員** ] 不可見) 
- 在 **Microsoft 端點** 管理員系統管理中心中，移至 [**裝置**] [windows  >    >  **windows 註冊**]  >  **自動註冊**。
- 確認已啟用 MDM 使用者範圍。

    1. 若要註冊所有電腦，設定為 [ **全部** ] 可在使用者將工作帳戶新增至 Windows 時，自動註冊所有加入 Azure AD 的使用者電腦和新電腦。
    2. 設定為 [ **部分** ]，以註冊特定使用者群組的電腦。
        -  將 Azure AD 中已同步處理的所需網域使用者新增至 [安全性群組](../admin/create-groups/create-groups.md)。
        -  選擇 [ **選取群組** ]，以啟用該安全性群組的 MDM 使用者範圍。

## <a name="4-create-the-required-resources"></a>4. 建立必要的資源 

使用[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 模組中的[Initialize-SecMgmtHybirdDeviceEnrollment 指令程式](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)，執行[設定混合式 Azure AD 聯結](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)所需的工作已得到簡化。 當您呼叫此 Cmdlet 時，它會建立並設定所需的服務連線點和群組原則。

您可以從 PowerShell: 實例中喚醒呼叫下列各項，以安裝此模組。

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> 建議您在執行 Azure AD Connect 的 Windows Server 上安裝此模組。

若要建立所需的服務連線點和群組原則，您將會呼叫  [SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Cmdlet。 當您執行此工作時，您將需要 Microsoft 365 商務版通用的系統管理員認證。 當您準備好建立資源時，請呼叫下列專案：

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

第一個命令會建立與 Microsoft 雲端的連線，當系統提示時，請指定您的 Microsoft 365 商務版通用系統管理員認證。

## <a name="5-link-the-group-policy"></a>5. 連結群組原則

1. 在 [群組原則管理主控台 (GPMC) 中，以滑鼠右鍵按一下您要連結原則的位置，然後從快顯功能表中選取 [ *連結現有的 GPO ...* ]。
2. 選取上一個步驟中建立的原則，然後按一下 **[確定]**。

## <a name="get-the-latest-administrative-templates"></a>取得最新的系統管理範本

如果您看不到原則 **使用預設 AZURE AD 認證來啟用自動 MDM 註冊**，可能是因為您沒有為 Windows 10、版本1803或更新版本安裝 ADMX。 若要修正此問題，請遵循下列步驟 (附注：最新的 MDM 會向後相容) ：

1.  下載： [Windows 10 十月 2020 Update (20H2) 的系統管理範本 ( admx) ](https://www.microsoft.com/download/102157)。
2.  在網域控制站上安裝套件。
3.  根據系統管理範本的版本，流覽至資料夾： **C:\Program 檔案 (x86) \Microsoft Group Policy\Windows 10 十月 2020 Update (20H2)**。
4.  將上述路徑中的 **原則定義** 資料夾重新命名為 **PolicyDefinitions**。
5.  將 **PolicyDefinitions** 資料夾複製到 SYSVOL 共用（預設位於 **C:\Windows\SYSVOL\domain\Policies** 中）。 
    -   如果您打算使用整個網域的中央原則存放區，請在那裡新增 PolicyDefinitions 的內容。
6.  如果您有多個網域控制站，請等候 SYSVOL 進行複製，以供使用原則。 此程式適用于任何未來版本的系統管理範本。

此時，您應該可以查看原則 **使用預設 AZURE AD 認證啟用自動 MDM 註冊** 。