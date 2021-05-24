---
title: 啟用已加入網域的 Windows 10 裝置以供商務 Microsoft 365 管理
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: 瞭解如何啟用 Microsoft 365，以在少數幾個步驟中保護本機作用中已加入目錄的 Windows 10 裝置。
ms.openlocfilehash: ec80159bdceffd8a13d09a297a2acc1b78c9b1b3
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636079"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>啟用已加入網域的 Windows 10 裝置以供 Microsoft 365 商務進階版管理

如果您的組織使用 Windows 的伺服器 Active Directory 內部部署，您可以設定 Microsoft 365 商務進階版來保護 Windows 10 裝置，同時仍維持對需要本機驗證之內部部署資源的存取。
若要設定此保護，您可以執行 **混合式 AZURE AD 聯結裝置**。 這些裝置會同時加入您的內部部署 Active Directory 和您的 Azure Active Directory。

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>觀賞：設定混合式 Azure Active Directory 聯結

這段影片說明如何針對最常見的案例設定此功能的步驟，在後續步驟中也會詳細說明。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>開始之前

- 使用 Azure AD 連線將使用者同步處理至 Azure AD。
-  (OU) 同步處理完成 Azure AD 連線組織單位。
- 請確定您同步處理的所有網域使用者都具有 Microsoft 365 商務進階版的授權。

如需步驟，請參閱 [同步處理網域使用者至 Microsoft](manage-domain-users.md) 。

## <a name="1-verify-mdm-authority-in-intune"></a>1. 驗證 Intune 中的 MDM 授權

移至 [端點管理員](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)，然後在 [Microsoft Intune] 頁面上，選取 [**裝置註冊**]，然後在 [概覽] 頁面上，確定 **[** **MDM 授權** 為 **Intune**]。

- 如果 **mdm 授權** 單位為 **None**，請按一下 **MDM 授權** 單位將其設定為 **Intune**。
- 如果已 **Microsoft Office 365** **mdm 授權**，請移至 [**裝置**] [  >  **註冊裝置**]，並使用右側的 [**新增 mdm 授權機構**] 對話方塊，以加入 **Intune MDM** 機關 (只有當 **MDM 授權** 設定為 Microsoft Office 365) 時，才可使用 [**新增 mdm 授權**] 對話方塊。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. 確認已針對加入的電腦啟用 Azure AD

- 移至 [系統管理中心] <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然後選取 [ **Azure Active Directory** (在 [系統 **管理中心**] 清單) 沒有看見 Azure Active Directory 時，請選取 [全部顯示]。 
- 在 **Azure Active Directory 系統管理中心**，移至 [ **Azure Active Directory** ]，選擇 [**裝置**]，然後選擇 [**裝置設定**]。
- 確認 **使用者可以將裝置加入至 AZURE AD** 已啟用 
    1. 若要啟用所有使用者，請將設定為 [ **全部**]。
    2. 若要啟用特定使用者，請將設定為 [已 **選擇** ]，以啟用特定的使用者群組。
        - 將 Azure AD 中已同步處理的所需網域使用者新增至 [安全性群組](../admin/create-groups/create-groups.md)。
        - 選擇 [ **選取群組** ]，以啟用該安全性群組的 MDM 使用者範圍。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. 確認已為 MDM 啟用 Azure AD

- 移至 [系統管理中心] <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然後選取 [select **Endpoint Managemen** t (] [如果不顯示 **端點管理員**，請選取 **全部顯示**]) 
- 在 **Microsoft 端點管理員系統管理中心**，移至 [**裝置**]  >  **Windows**  >  **Windows 註冊**  >  **自動註冊**。
- 確認已啟用 MDM 使用者範圍。

    1. 若要註冊所有電腦，設定為 [**全部**] 可在使用者將工作帳戶新增至 Windows 時，自動註冊所有加入 Azure AD 和新電腦的使用者電腦。
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
> 建議您在執行 Azure AD 連線的 Windows 伺服器上安裝此模組。

若要建立所需的服務連線點和群組原則，您將會呼叫  [SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Cmdlet。 當您執行此工作時，您將需要 Microsoft 365 商務進階版全域系統管理員認證。 當您準備好建立資源時，請呼叫下列專案：

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

第一個命令會建立與 Microsoft 雲端的連線，當出現提示時，請指定您的 Microsoft 365 商務進階版全域系統管理員認證。

## <a name="5-link-the-group-policy"></a>5. 連結群組原則

1. 在 [群組原則管理主控台 (GPMC) 中，以滑鼠右鍵按一下您要連結原則的位置，然後從快顯功能表中選取 [ *連結現有的 GPO ...* ]。
2. 選取上一個步驟中建立的原則，然後按一下 **[確定]**。

## <a name="get-the-latest-administrative-templates"></a>取得最新的系統管理範本

如果您看不到原則 **使用預設 Azure AD 認證來啟用自動 MDM 註冊**，可能是因為您沒有為 Windows 10、版本1803或更新版本安裝 ADMX。 若要修正此問題，請遵循下列步驟 (附注：最新的 MDM 會向後相容) ：

1.  下載： [Windows 10 10 月2020更新 (20H2) 的系統管理範本 ( admx) ](https://www.microsoft.com/download/102157)。
2.  在網域控制站上安裝套件。
3.  根據系統管理範本的版本，流覽至資料夾： **C:\Program 檔案 (x86) \microsoft 群組原則 \ Windows 10 10 月2020更新 (20H2)**。
4.  將上述路徑中的 **原則定義** 資料夾重新命名為 **PolicyDefinitions**。
5.  將 **PolicyDefinitions** 資料夾複製到 SYSVOL 共用，預設位置為 **C：\ Windows \SYSVOL\domain\Policies**。 
    -   如果您打算使用整個網域的中央原則存放區，請在那裡新增 PolicyDefinitions 的內容。
6.  如果您有多個網域控制站，請等候 SYSVOL 進行複製，以供使用原則。 此程式適用于任何未來版本的系統管理範本。

此時，您應該可以查看原則 **使用預設 AZURE AD 認證啟用自動 MDM 註冊** 。

## <a name="related-content"></a>相關內容

[同步處理網域使用者 Microsoft 365](manage-domain-users.md) (文章) \
[在系統管理中心中建立群組](../admin/create-groups/create-groups.md) (文章) \
[教程：設定受管理網域的混合式 Azure Active Directory 加入](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (文章) 