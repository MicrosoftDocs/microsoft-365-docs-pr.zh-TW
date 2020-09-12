---
title: 在基本行動性和安全性中建立裝置安全性原則
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用基本行動性和安全性來建立保護組織資訊的裝置原則。
ms.openlocfilehash: 322bca862c852f83406ca4622a63384b2e2275e5
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545881"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>在基本行動性和安全性中建立裝置安全性原則

您可以使用基本行動性和安全性來建立裝置原則，以協助保護 Microsoft 365 上的組織資訊免受未授權的存取。 您可以將原則套用至組織中的任何行動裝置，讓裝置的使用者具有適用的 Microsoft 365 授權，並已在基本行動性和安全性中註冊裝置。

## <a name="before-you-begin"></a>開始之前

> [!IMPORTANT]
> 在您可以建立行動裝置原則之前，您必須啟動並設定基本行動性和安全性。 如需詳細資訊，請參閱基本行動性和安全性概述。

- 深入瞭解基本行動性和安全性所支援的裝置、行動裝置應用程式及安全性設定。 請參閱 [基本行動性和安全性的功能](capabilities.md)。
- 建立安全性群組，其中包含您想要部署原則的 Microsoft 365 使用者，以及您可能想要排除禁止存取 Microsoft 365 的使用者。 建議您在將新的原則部署至組織之前，先將原則部署至少量的使用者，以測試原則。 您可以建立並使用安全性群組，其中只包含您自己或可以為您測試原則的少數 Microsoft 365 使用者。 若要深入瞭解安全性群組，請參閱 [建立、編輯或刪除安全性群組](https://go.microsoft.com/fwlink/p/?LinkId=518555)。
- 若要在 Microsoft 365 中建立及部署基本行動及安全性原則，您必須是 Microsoft 365 全域管理員。如需詳細資訊，請參閱 [安全性 & 合規性中心的許可權](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1)。
- 在您部署原則之前，請讓您的組織知道以基本行動性和安全性登錄裝置的潛在影響。 根據您設定原則的方式，可以封鎖不相容的裝置以存取 Microsoft 365 和資料，包括已註冊裝置上已安裝的應用程式、相片和個人資訊，以及可刪除的資料。

> [!NOTE]
> 在 MDM for Microsoft 365 商務標準中建立的原則和存取規則會覆寫 Exchange 系統管理中心建立的行動裝置信箱原則和裝置存取規則 ActiveSync。 在 MDM for Microsoft 365 商務標準中登記裝置後，就會忽略任何 Exchange ActiveSync 行動裝置信箱原則或裝置存取規則套用至裝置。 若要深入瞭解 Exchange ActiveSync，請參閱 exchange [Online 中的 exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)。

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>步驟1：建立裝置原則並部署至測試群組

開始之前，請先確定您已啟動並設定基本行動性和安全性。 如需相關指示，請參閱 [基本行動性和安全性概述](overview.md)。

1. 在您的瀏覽器中輸入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. 選取 [ **建立原則**]。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本行動及安全性原則設定":::

3. 在 [ **原則設定** ] 頁面上，指定您要套用至組織中行動裝置的需求。

4. **需要管理電子郵件設定檔**：啟用時，未使用基本行動和安全性管理的電子郵件設定檔的裝置會被視為不相容。 裝置沒有正確的目標時，或使用者已手動在裝置上設定電子郵件帳戶時，無法使用受管理的電子郵件設定檔。 當您保持 **未啟用狀態** (預設) 時，此設定不會針對相容性或非規範評估。 如需選取此選項時，使用者如何取得相容性的指示，請參閱 [找到現有的電子郵件帳戶](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。

5. 在 [ **您要立即套用此原則？** ] 頁面上，選擇您要套用此原則的群組。

6. 選取 [ **建立這個原則**]。

原則會推入每位使用者的裝置，在下一次使用行動裝置登入 Microsoft 365 時，該原則會套用至此裝置。 如果使用者之前沒有將原則套用到其行動裝置，則在您部署原則之後，他們的裝置上會出現通知，其中包含登錄和啟用基本行動性及安全性的步驟。 如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)。 在 Intune 服務所主控的基本行動性和安全性中完成註冊之前，就會限制存取電子郵件、OneDrive 及其他服務。 在完成使用 Intune 公司入口網站的註冊後，他們就能使用服務，並將原則套用至其裝置。

## <a name="step-2-verify-that-your-policy-works"></a>步驟2：確認原則可以運作

在您建立裝置原則之後，請先檢查原則是否如預期那樣運作，再將其部署至您的組織。

1. 在您的瀏覽器中輸入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. 選取 **[查看受管理的裝置清單**]。
3. 檢查已套用原則的使用者裝置狀態。 您想要管理裝置的 **狀態** **。**
4. 您也可以在選取裝置後，按一下 [**出廠重設**] 或 [從**管理**中**移除公司資料**] 按鈕，在裝置上進行完整或選擇性的擦除。 如需相關指示，請參閱 [在 Microsoft 365 中清除行動裝置。

## <a name="step-3-deploy-a-policy-to-your-organization"></a>步驟3：將原則部署至您的組織

在您建立裝置原則並驗證它如預期般運作後，請將其部署至您的組織。

1. 從瀏覽器類型： [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. 選取您要部署的原則，然後選擇 [所套用**的群組**] 旁邊的 [**編輯**]。
3. 搜尋要新增的群組，然後按一下 [ **選取**]。
4. 選取 [ **關閉** 並 **變更設定]。**
5. 選取 [ **關閉** 並 **編輯原則]。**

原則會推入每位使用者的行動裝置，在下一次從其行動裝置登入 Microsoft 365 時，該原則會套用至行動裝置。 如果使用者未將原則套用到其行動裝置，他們會在其裝置上取得通知，以及註冊及啟用基本行動性和安全性的步驟。 完成註冊後，會將原則套用至其裝置。 如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)。

## <a name="step-4-block-email-access-for-unsupported-devices"></a>步驟4：封鎖不受支援的裝置的電子郵件存取

為了協助保護您的組織資訊，您應該封鎖 Microsoft 365 電子郵件的應用程式存取（基本行動裝置及安全性不支援的行動裝置）。 如需支援的裝置清單，請參閱 [支援的裝置](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices)。

**封鎖應用程式存取：**

1. 在您的瀏覽器中輸入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. 選取 [ **管理整個組織的裝置存取設定**]。
3. 若要封鎖不支援的裝置，請選擇 [**如果 Microsoft 365 的 MDM 不支援裝置**，請選擇**封鎖**]，然後選取 [**儲存**]。

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="基本行動性和安全性封鎖存取選項":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>步驟5：選擇要從條件式存取檢查排除的安全性群組

如果您想要在行動裝置上排除某些人員的條件式存取檢查，而且您已為這些人員建立一個或多個安全性群組，請在這裡新增安全性群組。 這些群組中的人員不會針對其支援的行動裝置強制實施任何原則。 如果您不再想要在組織中使用基本行動性和安全性，建議您使用此選項。

1. 在您的瀏覽器中輸入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. 選取 [ **管理整個組織的裝置存取設定**]。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本行動及安全性建立原則選項":::

3. 選取 [ **新增** ]，以新增您要從封鎖 Microsoft 365 的存取權中排除之使用者的安全性群組。 當使用者已新增至此清單時，他們可以在使用不受支援的裝置時存取 Microsoft 365 電子郵件。

4. 在 [ **選取群組** ] 面板中，選取您要使用的安全性群組。

5. 選取名稱，然後新增 [ **Add**  >  **儲存**]。

6. 在 **全組織的裝置存取設定** 面板上，選擇 [ **儲存**]。

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="基本行動及安全性允許存取選項":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>安全性原則對不同裝置類型的影響為何？

當您將原則套用至使用者裝置時，每個裝置的影響會因裝置類型而異。 如需不同裝置之原則影響的範例，請參閱下表。

|**安全性原則**|**Android 4 和更新版本**|**Samsung KNOX**|**iOS 6 和更新版本**|**附註**|
|:-----|:-----|:-----|:-----|:-----|
|需要加密備份|否|是|是|需要 iOS 加密備份。|
|封鎖雲端備份|是|是|是|在 Android 上封鎖 Google 備份 (在 iOS 上的雲端備份) 暗顯。|
|封鎖檔同步處理|否|否|是|iOS：封鎖雲端中的檔。|
|封鎖照片同步處理 |否|否|是|iOS (原生) ：封鎖相片資料流程。|
|封鎖螢幕捕捉 |否|是|是|嘗試時封鎖。|
|封鎖影片會議 |否|否|是|FaceTime 在 iOS 上封鎖，而不是在 Skype 或其他人上封鎖。|
|封鎖傳送診斷資料 |否|是|是|在 Android 上封鎖發送 Google 崩潰報告。|
|封鎖對應用程式存放區的存取 |否|是|是|在 Android 首頁上遺漏的應用程式存放區圖示，在 Windows 上停用，在 iOS 上遺失。|
|需要密碼的應用程式存放區 |否|否|是|iOS： iTunes 購買所需的密碼。|
|封鎖可移動儲存裝置的連線 |否|是|不適用|Android： SD 卡在 [設定] 中會顯示為灰色，Windows 會通知使用者，安裝的應用程式無法使用|
|封鎖藍牙連線 |查看附注|查看附注|是|我們無法停用藍牙做為 Android 的設定。 相反地，我們會停用所有需要藍牙的交易：高級音訊發佈、Audio/Video 遙控裝置、免提裝置、電話薄存取和序列埠。 當您使用其中任何一項時，就會在頁面底部顯示一則小型 toast 訊息。|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>當您刪除原則或從原則中移除使用者時會發生什麼情況？

當您刪除原則或移除已部署原則的群組中的使用者時，可能會從使用者的裝置中移除原則設定 [Microsoft 365 電子郵件設定檔及快取的電子郵件。 請參閱下表，查看針對不同裝置類型移除的內容。

|**移除的功能**|**iOS 6 和更新版本**|**Android 4 和更新版本 (包括 Samsung KNOX**|
|:-----|:-----|:-----|
|受管理的電子郵件設定檔<sup>1</sup>|是|否|
|封鎖雲端備份|是|否|

<sup>1</sup> 如果已選取 [ **受管理的電子郵件設定檔** ] 來部署原則，則會從使用者裝置中刪除受管理的電子郵件設定檔及快取的電子郵件。

原則會從行動裝置中移除每位使用者，原則會套用至下一次其裝置使用基本行動性和安全性進行簽入時。 如果您部署的是套用至這些使用者裝置的新原則，系統會提示他們在基本行動性和安全性中重新註冊。

您也可以完全清除裝置，或選擇性地清除裝置中的組織資訊。 如需詳細資訊，請參閱 [在基本行動及安全性中清除行動裝置](wipe-mobile-device.md)。

## <a name="related-topics"></a>相關主題

[基本行動及安全性概述](overview.md)

[基本行動及安全性的功能](capabilities.md)
