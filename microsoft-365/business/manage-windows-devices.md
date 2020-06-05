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
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564924"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>啟用已加入網域的 Windows 10 裝置以由 Microsoft 365 商務版 Premium 管理

如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版 Premium 來保護您的 Windows 10 裝置，同時仍維持對需要本機驗證的內部部署資源的存取。
若要設定此保護，您可以執行**混合式 AZURE AD 聯結裝置**。 這些裝置會同時加入您的內部部署 Active Directory 和您的 Azure Active Directory。

這段影片說明如何針對最常見的案例設定此功能的步驟，在後續步驟中也會詳細說明。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>開始之前，請先確定您已完成下列步驟：
- 使用 Azure AD Connect 將使用者同步處理至 Azure AD。
- 完成 Azure AD Connect 組織單位（OU）同步處理。
- 請確定您同步處理的所有網域使用者都具有 Microsoft 365 商務版的授權。

如需步驟，請參閱[同步處理網域使用者至 Microsoft](manage-domain-users.md) 。

## <a name="1-verify-mdm-authority-in-intune"></a>1. 驗證 Intune 中的 MDM 授權

移至 [portal.azure.com]，並在 [頁面搜尋] 上方的 [Intune] 搜尋。
在 [Microsoft Intune] 頁面上，選取 [**裝置註冊**]，然後在 [**概覽**] 頁面上，確認**MDM 授權**為**Intune**。

- 如果**mdm 授權**單位為**None**，請按一下**MDM 授權**單位將其設定為**Intune**。
- 如果**mdm 授權**是**Microsoft Office 365**，請移至 [**裝置]**  >  [**註冊裝置**]，並使用右側的 [**新增 mdm 授權機構**] 對話方塊，以新增**Intune MDM**授權（[**新增 mdm 機關**] 對話方塊只有在**MDM 授權**設定為 [Microsoft Office 365] 時才可用）。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. 確認已針對加入的電腦啟用 Azure AD

- 移至系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，並選取 [ **Azure active directory** ] （如果未顯示 azure active directory，請選取 [全部顯示**Admin centers**所有專案）] 清單中的 [azure active directory]。 
- 在**Azure Active directory 系統管理中心**中，移至 [ **azure active directory** ]，選擇 [**裝置**]，然後選擇 [**裝置設定**]。
- 確認**使用者可以將裝置加入至 AZURE AD**已啟用 
    1. 若要啟用所有使用者，請將設定為 [**全部**]。
    2. 若要啟用特定使用者，請將設定為 [已**選擇**]，以啟用特定的使用者群組。
        - 將 Azure AD 中已同步處理的所需網域使用者新增至[安全性群組](../admin/create-groups/create-groups.md)。
        - 選擇 [**選取群組**]，以啟用該安全性群組的 MDM 使用者範圍。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. 確認已為 MDM 啟用 Azure AD

- 移至系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然後選取 [Select **endpoint Managemen**t （選取所有 if**端點管理員**時不會**顯示所有**的）]
- 在**Microsoft 端點**管理員系統管理中心中，移至 [**裝置**] [windows  >  **Windows**  >  **windows 註冊**]  >  **自動註冊**。
- 確認已啟用 MDM 使用者範圍。

    1. 若要註冊所有電腦，設定為 [**全部**] 可在使用者將工作帳戶新增至 Windows 時，自動註冊所有加入 Azure AD 的使用者電腦和新電腦。
    2. 設定為 [**部分**]，以註冊特定使用者群組的電腦。
        -  將 Azure AD 中已同步處理的所需網域使用者新增至[安全性群組](../admin/create-groups/create-groups.md)。
        -  選擇 [**選取群組**]，以啟用該安全性群組的 MDM 使用者範圍。

## <a name="4-set-up-service-connection-point-scp"></a>4. 設定服務連線點（SCP）

您可以從[設定混合式 AZURE AD 聯結](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)簡化這些步驟。 若要完成使用 Azure AD Connect 和您的 Microsoft 365 商務版全域管理員和 Active Directory 系統管理員密碼所需的步驟。

1.  啟動 Azure AD Connect，然後選取 [**設定**]。
2.  在 [**其他**工作] 頁面上，選取 [**設定裝置選項**]，然後選取 **[下一步]**。
3.  在 [**概覽**] 頁面上，選取 **[下一步]**。
4.  在 [連線**到 AZURE AD]** 頁面上，輸入 Microsoft 365 商務版 Premium 全域管理員的認證。
5.  在 [**裝置選項**] 頁面上，選取 [**設定混合式 Azure AD 聯結**]，然後選取 **[下一步]**。
6.  在 [ **SCP** ] 頁面上，針對您要 Azure AD Connect 以設定 SCP 的每個樹系，完成下列步驟，然後選取 **[下一步]**：
    - 選取樹系名稱旁邊的方塊。 樹系應該是您的 AD 功能變數名稱。
    - 在 [**驗證服務**] 欄下，開啟下拉式清單，然後選取 [相符的功能變數名稱] （應該只有一個選項）。
    - 選取 [**新增**]，輸入網域管理員認證。  
7.  在 [**裝置作業系統**] 頁面上，只選取 [Windows 10 或更新版本的加入網域的裝置]。
8.  在 [**準備設定**] 頁面上，選取 [**設定**]。
9.  在 [設定完成] 頁面上 **，選取 [****結束**]。


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a>5. 建立 GPO 以供 Intune 登記– ADMX 方法

使用。ADMX 範本檔案。

1.  登入 AD server、搜尋及開啟**伺服器管理員**  >  **工具**  >  **群組原則管理**。
2.  選取 [**網域**] 底下的功能變數名稱，然後在 [**群組原則物件**] 上按一下滑鼠右鍵，選取 [**新增**]。
3.  提供新的 GPO 名稱，例如 "*Cloud_Enrollment*"，然後選取 **[確定]**。
4.  在 [**群組原則物件**] 底下的新 GPO 上按一下滑鼠右鍵，然後選取 [**編輯**]。
5.  在 [**群組原則管理編輯器**] 中，移至 [電腦設定原則] [**系統**  >  **Policies**  >  **管理範本] 「管理範本**」  >  **Windows 元件**  >  **MDM**
6. 以滑鼠右鍵按一下 [**啟用預設 Azure AD 認證的自動 MDM 註冊**]，然後選取 [**啟用**  >  **確定]**。 關閉 [編輯器] 視窗。

> [!IMPORTANT]
> 如果您未看到原則**使用預設 AZURE AD 認證啟用自動 MDM 註冊**，請參閱[取得最新的系統管理範本](#get-the-latest-administrative-templates)。

## <a name="6-deploy-the-group-policy"></a>6. 部署群組原則

1.  在 [伺服器管理員] 的 [**網域**> 群組原則物件] 底下，選取上述步驟3中的 GPO，例如 "Cloud_Enrollment"。
2.  為您的 GPO 選取 [**範圍**] 索引標籤。
3.  在 GPO 的 [範圍] 索引標籤中，以滑鼠右鍵按一下 [**連結**] 底下的 [網域] 連結。
4.  選取 [**強制**]，以部署 GPO，然後在確認畫面中按一下 **[確定]** 。

## <a name="get-the-latest-administrative-templates"></a>取得最新的系統管理範本

如果您看不到原則**使用預設 AZURE AD 認證來啟用自動 MDM 註冊**，可能是因為您沒有為 Windows 10、版本1803、版本1809或版本1903安裝 ADMX。 若要修正此問題，請遵循下列步驟（附注：最新的 MDM 會向後相容）：

1.  下載： [Windows 10 的系統管理範本（admx）可能是2019更新（1903）](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)。
2.  在網域主控站（PDC）上安裝套件。
3.  根據資料夾的版本來流覽： **C:\Program 檔案（x86） \Microsoft Group Policy\Windows 10 可能2019更新（1903） v3**。
4.  將上述路徑中的**原則定義**資料夾重新命名為**PolicyDefinitions**。
5.  將**PolicyDefinitions**資料夾複製到**C:\Windows\SYSVOL\domain\Policies**。 
    -   如果您打算使用整個網域的中央原則存放區，請在那裡新增 PolicyDefinitions 的內容。
6.  重新開機網域主控站以供原則使用。 此程式也適用于未來的任何版本。

此時，您應該可以查看原則**使用預設 AZURE AD 認證啟用自動 MDM 註冊**。

