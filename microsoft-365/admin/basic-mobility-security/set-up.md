---
title: 設定基本行動與安全性
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
description: 設定基本行動性和安全性，以保護和管理使用者的行動裝置。
ms.openlocfilehash: 38f122141b370468bc591df49b3e1891a8a66a43
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876861"
---
# <a name="set-up-basic-mobility-and-security"></a>設定基本行動與安全性

Microsoft 365 的內建基本行動性和安全性可協助您保護和管理使用者的行動裝置，例如 Iphone、Ipad、Androids 和 Windows phone。 您可以建立及管理裝置安全性原則、遠端抹除裝置資料，以及檢視詳細的裝置報告。

Have questions? 如需協助解決常見問題的常見問題，請參閱 [基本行動性及安全性常見問題 (常見問題) ](frequently-asked-questions.md)。 請注意，您無法使用委派的系統管理員帳戶來管理基本行動性和安全性。 如需詳細資訊，請參閱 [合作夥伴：提供委派的管理](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。 

裝置管理是安全性 & 規範中心的一部分，因此您必須先開始執行基本行動及安全性設定。

## <a name="activate-the-basic-mobility-and-security-service"></a>啟動基本行動及安全性服務

1. 使用您的全域系統管理員帳戶登入 Microsoft 365。

2. 移至 [ [啟用基本行動及安全性](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)]。

   啟用基本行動性和安全性可能需要一些時間。 完成後，您會收到一封電子郵件，說明接下來要採取的步驟。

## <a name="set-up-mobile-device-management"></a>設定行動裝置管理

當服務準備好時，請完成下列步驟以完成安裝程式。

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>步驟1： (必要) 設定網域以取得基本行動性和安全性

如果您沒有與 Microsoft 365 相關聯的自訂網域，或者您不是管理 Windows 裝置，則可以略過本節。 否則，您必須在您的 DNS 主機上新增網域的 DNS 記錄。 如果您已新增記錄，請在使用 Microsoft 365 設定網域時，全部都是設定。 在您新增記錄之後，您組織中使用您自訂網域的電子郵件地址登入之 Windows 裝置的 Microsoft 365 使用者會重新導向，以登錄基本行動性和安全性。

需要設定記錄的協助嗎？ 尋找您的網域註冊機構，並選取 [註冊機構名稱]，以移至 [[新增 dns 記錄] 以連接您的網域](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)時，在清單中建立 dns 記錄的逐步說明。 使用這些指示來建立簡化的 Windows 登記中所述的 CNAME 記錄， [而不使用 AZURE AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)。

新增這兩個 CNAME 記錄後，請回到安全性 & 合規性中心，然後移至 [**資料遺失防護**  >  **裝置管理**   ] 以完成下一個步驟。

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>步驟2： (必要) 設定 iOS 裝置的 APNs 憑證

若要管理的 iOS 裝置如 iPad 和 Iphone，您必須建立 APNs 憑證。

1. 使用您的全域系統管理員帳戶登入 Microsoft 365。

2. 在您的瀏覽器類型：中  [https://protection.office.com](https://protection.office.com/) 。

3. 選取 [ **資料遺失防護**   >  **裝置管理**]，然後 **為 iOS 裝置選擇 APNs 憑證**。

4. 在 [Apple 推播通知憑證設定] 頁面上，選擇 **[下一步]**。

5. 選取 [ **下載您的 CSR** 檔案]   ，然後將憑證簽署要求儲存至電腦上您所記得的地方。 選取 **[下一步]**。

6. 在 [建立 APNs 憑證] 頁面上：

   - 選取 Apple APNS 入口網站以開啟 Apple Push 憑證入口網站。
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - 選取 [建立憑證] 並接受 [使用條款]。
   - 流覽至您從 Microsoft 365 和 selectUpload 下載到電腦的憑證簽署要求。
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. 請回到 Microsoft 365，然後選取 **[下一步]**。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. 選取  **[完成]**。

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>步驟3： (建議) 設定多重要素驗證

由於要求第二種驗證格式，MFA 可協助您保護登入 Microsoft 365 以進行行動裝置註冊。 使用者在輸入其工作帳戶密碼後，必須在其行動裝置上認可來電、文字訊息或代理程式更新。 他們只能在第二個驗證表單完成後註冊其裝置。 在使用基本行動性和安全性的使用者裝置登錄之後，使用者只可以存取其工作帳戶的 Microsoft 365 資源。

若要瞭解如何在 Azure AD 入口網站中開啟 MFA，請參閱 [設定多重要素驗證](https://go.microsoft.com/fwlink/p/?LinkId=519255)。

設定 MFA 後，請回到安全性 & 合規性中心，並流覽至「 **資料遺失防護**」   >  **裝置管理**   >  **裝置原則**，   以完成下一個步驟。

### <a name="step-4-recommended-manage-device-security-policies"></a>步驟4： (建議) 管理裝置安全性原則

下一步是建立及部署裝置安全性原則，以協助保護您的 Microsoft 365 組織資料。 例如，您可以在三次登入失敗之後建立一個原則，以鎖定裝置，以鎖定裝置，以防止資料遺失（如果使用者在非活動狀態和擦除裝置上鎖定裝置）。

1. 使用您的全域系統管理員帳戶登入 Microsoft 365。

2. 選取 [ [啟用行動裝置管理](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)]。 如果服務已啟動，則改為啟用步驟，您會看到 [管理裝置](https://admin.microsoft.com/adminportal/home#/MifoDevices)的連結   。

3. 移至 [ **裝置原則**]。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全性和行動性原則設定":::

4. 遵循以 [基本行動性和安全性建立裝置安全性原則中](create-device-security-policies.md)的步驟，建立及部署適用于貴組織的裝置安全性原則。

> [!TIP]
>
> - 當您建立新的原則時，您可能會想要設定原則，以允許在使用者裝置與原則不相容的情況下進行存取和報告原則侵犯。 這可讓您查看原則所影響的行動裝置數目，而不會封鎖對 Microsoft 365 的存取。
>
> - 在您將新的原則部署給組織中的每個人之前，我們建議您在少量使用者所使用的裝置上進行測試。
>
> - 此外，在您部署原則之前，請讓您的組織知道使用基本行動性和安全性登錄裝置的潛在影響。 根據您設定原則的方式，不遵循 (不相容裝置之原則的裝置) 可以封鎖存取 Microsoft 365。 不相容的裝置也可能會在擦除裝置時，在已註冊的裝置上安裝應用程式、相片和其他個人資訊。 如需詳細資訊，請參閱 [在基本行動及安全性中清除行動裝置](wipe-mobile-device.md)。

## <a name="make-sure-users-enroll-their-devices"></a>請確定使用者已註冊其裝置

在您建立並部署行動裝置管理原則之後，組織中的每一個已授權的 Microsoft 365 使用者在下次從其行動裝置登入 Microsoft 365 時，該使用者就會收到註冊郵件。 他們必須先完成註冊和啟用步驟，才能存取 Microsoft 365 電子郵件和檔。 如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)。

> [!IMPORTANT]
> 如果註冊程式不支援使用者的慣用語言，使用者可能會在其行動裝置上以其他語言接收註冊通知和步驟。 在行動裝置上，目前不支援所有 Microsoft 365 中支援的語言註冊程式。

必須有 Android 或 iOS 裝置的使用者，才能安裝公司入口網站應用程式作為註冊過程的一部分。

## <a name="related-topics"></a>相關主題

[基本行動與安全性的功能](capabilities.md)<br/>
[在基本行動性和安全性中建立裝置安全性原則](create-device-security-policies.md)