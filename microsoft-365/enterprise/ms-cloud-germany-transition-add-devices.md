---
title: 從 Microsoft Cloud Deutschland 遷移的其他裝置資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：從 microsoft cloud 德國移至服務時，服務的其他裝置資訊 (Microsoft cloud Deutschland) 以 Office 365 新德文 datacenter 區域中的服務。
ms.openlocfilehash: 1eb7b18360cefeeb2d5770c3d77e564d5a757a5e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453564"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 遷移的其他裝置資訊

連接至 Microsoft 雲端 Deutschland 的 Azure AD 加入和註冊裝置必須在階段9和階段10之前遷移。 裝置的遷移取決於裝置類型、作業系統和 Azure AD 關聯。

## <a name="azure-ad-joined-windows-10-devices"></a>Azure AD 加入 Windows 10 裝置
如果 Windows 10 裝置已加入 azure ad，必須中斷與 azure ad 的連線，且必須重新連線。

[![AZURE AD 裝置 Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


如果使用者是 Windows 10 裝置上的系統管理員，使用者可以從 Azure AD 中登出裝置，並以三個步驟重新加入。

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>步驟1：判斷裝置是否已加入 Azure 識別碼

1. 使用您的工作帳戶登入。
2. 移至 **設定**  >  **帳戶**  >  **存取工作或學校**。
3. 在清單中尋找 **已連接至 [...] ' 的帳戶s Azure AD**。
4. 如果已連線的帳戶存在，請繼續進行步驟2。

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>步驟2：從 Azure AD 中斷裝置連線

1. 在 [連線的公司或學校帳戶] 上，按一下 [ **中斷連線]** 。
2. 確認 [中斷連線] 兩次。
3. 輸入本機系統管理員的使用者名稱和密碼。 裝置中斷連線。
4. 重新開機裝置。

### <a name="step-3-join-the-device-to-azure-ad"></a>步驟3：將裝置加入 Azure AD

1. 使用本機系統管理員的認證登入。
2. 移至 **設定**  >  **帳戶**  >  **存取工作或學校**。
3. 按一下 **[連線]**。
4. **重要** 事項：按一下 [ **加入 Azure AD**]。
5. 輸入您工作帳戶的電子郵件地址和密碼。 裝置已連線。
6. 重新開機裝置。
7. 使用您的工作帳戶的電子郵件地址和密碼登入。

如果使用者不是裝置的系統管理員，Azure AD 全域系統管理員可以在此設定路徑之後的裝置上建立本機系統管理員帳戶，然後將裝置脫離：

*設定 > 帳戶 > 其他帳戶 > 憑證未知 > 新增沒有 Microsoft 帳戶的使用者*

若要重新加入，您可以在此步驟中使用您組織中任何工作帳戶的認證。

請考慮加入裝置所用的工作帳戶，會自動以裝置管理員的身分升級。
組織中的任何其他工作帳戶都可以登入裝置，但沒有系統管理員許可權。

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a>) Windows 10 裝置 (已加入 workplace 的 Azure AD

如果 Windows 10 裝置已註冊 azure ad，則必須中斷與 azure ad 的連線，並再次連接。

[![AZURE AD 裝置 Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a>步驟1：判斷裝置是否已註冊 Azure 識別碼

1. 使用使用者登入。
2. 移至 **設定**  >  **帳戶**  >  **存取工作或學校**。
3. 在清單中探索您的工作帳戶，並檢查其是否已 **連接至 [...] 's Azure AD**。

    如果您的工作帳戶在清單中，但未連線到 Azure AD，請繼續進行步驟2。

    否則，您的裝置是 azure 已加入 azure 的裝置，您必須參照[azure ad 加入的 Windows 10 裝置](#azure-ad-joined-windows-10-devices)。

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>步驟2：從 Azure AD 中斷裝置連線

1. 按一下您的工作帳戶。 隨即出現 [按鈕 *資訊* 及 *中斷連線]* 。
2. 按一下 **[中斷連線]**。
3. 按一下 **[是]** 確認移除裝置中的帳戶。

### <a name="step-3-connect-the-device-to-azure-ad"></a>步驟3：將裝置連線至 Azure AD

1. 按一下 **[連線]**。
2. 輸入您的工作帳戶的電子郵件地址，然後按 **[下一步]**。
3. 輸入工作帳戶的密碼，然後按一下 [登 **入**]。
4. 按一下 [ **完成**] 以確認。 您的工作帳戶會再次列出。

## <a name="android"></a>Android

若為 Android，使用者將需要撤銷註冊並重新登錄其裝置。 這可以透過 Microsoft Authenticator 應用程式或公司入口網站應用程式來完成。

- 在 Microsoft Authenticator 應用程式中，使用者可以前往 **設定 > 裝置註冊**。 從這裡開始，使用者可以撤銷註冊並重新登錄其裝置。

- 從公司入口網站中，使用者可以移至 [**裝置**] 索引標籤並移除裝置。 之後，使用公司入口網站重新註冊裝置。

- 使用者也可以從 [帳戶設定] 頁面移除帳戶，然後重新加入工作帳戶，以取消登錄和重新註冊。

若要使用 Microsoft Authenticator 應用程式在 Android 上撤銷登錄並重新登錄，請執行下列動作：

1. 開啟 Microsoft Authenticator 應用程式，然後移至 **設定**。
2. 選取 **Device registration**。
3. 選取 [ **登出**] 以取消登錄裝置。
4. 若為 **Device registration**，請輸入您的電子郵件地址，然後選取 [ **註冊**]，以重新註冊裝置。

若要使用 Android 設定頁面來撤銷註冊並重新登錄 Android 裝置，請執行下列動作：

1. 開啟 [**裝置設定**]，然後移至 [**帳戶**]。
2. 選取您要重新註冊的工作帳戶，然後選取 [ **移除帳戶**]。
3. 移除帳戶後，請從 [ **帳戶** ] 頁面中，選取 [ **新增帳戶 > 工作帳戶**]。
4. 在 [ **Workplace Join**] 中輸入您的電子郵件地址，然後選取 [ **加入** ] 以完成裝置的註冊。

若要從公司入口網站登出並重新登錄 Android 上的裝置：

1. 啟動公司入口網站，然後移至 [**裝置**] 索引標籤。
2. 選取裝置以查看裝置詳細資料。
3. 從省略號 (三點) 功能表中，選取 [ **移除裝置**]，並在對話方塊中確認以完成移除。
4. 您現在應該已登出公司入口網站的應用程式。 選取 [登入] 以重新 **登錄** 裝置。

如需此工作負載遷移階段所需之任何動作的詳細資訊，或對管理或使用的影響，請參閱 azure ad) 中 Azure Active Directory (Azure ad 的相關資訊，以[供從 Microsoft Cloud Deutschland 進行遷移的其他 azure ad 資訊中取得](ms-cloud-germany-transition-azure-ad.md)。

## <a name="ios"></a>iOS

在 iOS 裝置上，使用者將需要從 Microsoft Authenticator 手動移除任何快取的帳戶、登出裝置，然後登出裝置上的任何原生應用程式。

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>步驟1：若存在，請從 Microsoft Authenticator 應用程式中移除帳戶。

1. 在 Microsoft Authenticator 應用程式中點擊帳戶。
2. 按一下右上角的 **設定** 圖示。 如果您沒有看到 **設定** 圖示，則可能是您使用的是 Microsoft Authenticator 的最新版本。
3. 點擊 [ **移除帳戶** ] 按鈕。
4. 點擊 [ **此裝置上的所有應用程式**]。

### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>步驟2：從 Microsoft Authenticator 應用程式中登出裝置

1. 在右上角點擊功能表圖示。
2. 按 **設定**，然後按 **裝置註冊**。
3. 如果顯示您的帳戶，請點擊 [ **登出裝置** ]，然後在對話方塊中 **繼續** 。 之後，您就不會看到任何帳戶。

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>步驟3：必要時登出個別應用程式

使用者可以移至個別應用程式，例如 Outlook、Teams 及 OneDrive，以及從這些應用程式中移除帳戶。

## <a name="frequently-asked-questions"></a>常見問題集

**如何判斷組織是否受到影響？**

管理員應該檢查 `https://portal.microsoftazure.de` 是否有任何 AZURE ad 已註冊或 AZURE ad 聯結裝置。 如果您的組織已註冊 Azure AD 或已加入 Azure AD 的裝置，您的組織必須依照此頁面上的指示進行。

**我的使用者何時重新註冊其裝置？**

您的成功必須先取消註冊，然後在 [階段 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 完成之後重新登錄裝置，這一點很重要。 您必須在第10階段開始之前完成重新註冊，否則您可能會失去對裝置的存取權。

**如何知道我的所有裝置都已登錄公用雲端？**

若要檢查您的裝置是否已在公用雲端中註冊，您應該將裝置清單從 Azure AD 入口網站匯出並下載至 Excel 試算表。 然後，在您的組織已超過遷移程式的 [階段 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)之後，使用 _registeredTime_ 欄) ，以篩選 (註冊的裝置。

**我還是需要 [使用以 Windows 為基礎的 dns 建立 Microsoft dns 記錄](/microsoft-365/admin/dns/create-dns-records-using-windows-based-dns?view=o365-worldwide#add-two-cname-records-for-mobile-device-management-mdm-for-microsoft)中所述的方式來新增 dns 名稱嗎？**

重新註冊裝置不再需要此 DNS 專案。 

## <a name="additional-considerations"></a>其他考量

> [!IMPORTANT]
> 在遷移程式的 [階段 3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)之後，將會啟用 Intune 服務主體，這表示 Azure AD Device Registration 的啟用。 如果您在遷移之前封鎖 Azure AD 裝置註冊，您必須使用 PowerShell 停用 Intune service 主體，以使用 Azure AD 入口網站停用 Azure AD 裝置註冊。 您可以在 Graph 模組的 Azure Active Directory PowerShell 中，使用此命令來停用 Intune 服務主體。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a>其他相關資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德國資料中心區域的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移轉程式資訊](/power-bi/admin/service-admin-migrate-data-germany)
- [開始升級您的 Microsoft Teams](/microsoftteams/upgrade-start-here)
