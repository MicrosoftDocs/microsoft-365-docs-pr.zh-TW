---
title: '基本行動及安全性常見問題 (常見問題) '
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
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
description: 有關基本行動性和安全性的常見問題。
ms.openlocfilehash: e05815392510ad54bb530457d7f0f6490ece4a95
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430116"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>基本行動及安全性常見問題 (常見問題) 

本文包含有關基本行動性及安全性的常見問題，可協助您管理 Microsoft 365 中的行動裝置和保護其安全的功能。 如果您找不到問題的答案，請在頁面上留下批註以告知我們，我們可以考慮將您的問題加入本文。

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>如何取得基本行動性和安全性？ 我在 Microsoft 365 系統管理中心中看不到它

1.  移至 [Office 365 安全性 & 合規性](https://protection.office.com/) 頁面，啟用基本行動及安全性。   

2.  移至資料遺失防護 > 裝置管理。   

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>如何開始使用基本行動性和安全性的裝置管理？

基本行動性及安全性入門的步驟有四個： 

1. 移至 [Office 365 的安全性 & 符合性](https://protection.office.com/)，以啟用基本行動及安全性。
    
2. 移至資料遺失防護 > 裝置管理 > 裝置原則。
    
3. 建立裝置管理原則，並將其套用至安全性群組中設定的使用者群組。 建議您先將原則部署至小型測試群組。 如需詳細資訊，請參閱 [在基本行動性和安全性中建立裝置安全性原則](create-device-security-policies.md)。      

4. 已套用原則的使用者會在嘗試存取 Microsoft 365 資料時，提示他們註冊其裝置。 如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)。

如需詳細資訊，請參閱 [設定基本行動性和安全性](set-up.md)。

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>我嘗試設定基本行動性和安全性，但似乎已停滯。 Microsoft 365 服務的健康情況已經顯示 "布建" 一段時間。 我該怎麼做？

可能需要一些時間才能讓您準備好服務。 布建完成後，您會看到 [適用于 Microsoft 365 的行動裝置管理] 頁面。 如果您已等候24小時，但狀態仍為 [布建]，請聯繫支援人員，我們將協助找出問題的含義。 如需支援選項，請參閱 [仍需協助？](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp) 

## <a name="what-can-i-do-if-device-enrollment-fails"></a>裝置註冊失敗時，該怎麼辦？

如果您在註冊裝置時遇到問題，請先檢查下列各項：

- 確定設備尚未使用其他行動裝置管理提供者（例如 Intune）進行註冊。
    
- 請確定裝置已設定為正確的日期和時間。
    
- 切換至裝置上的不同 WIFI 或蜂窩網路。
    
- 針對 Android 或 iOS 裝置，請在裝置上卸載並重新安裝 Intune 公司入口網站應用程式。
    
如果註冊仍無法運作，請參閱 [疑難排解基本行動性和安全性](troubleshoot.md)。

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Intune 與基本行動能力及安全性有何差異？

初級行動及安全性是由 Intune 服務所主控。 它是一項 Intune 服務的子集，可提供給 Microsoft 365 的新增權益，也就是內建的雲端式解決方案，可用於管理組織中的裝置。 如需兩項服務的並列比較，以協助您決定使用 Intune 或 Microsoft 365 的基本行動及安全性，是最適合您的，請參閱 [Choose Basic 行動性安全性與 Intune](choose-between-basic-mobility-and-security-and-intune.md)。

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>原則如何運作以取得基本行動性和安全性？ 如何設定？ 停用它們？

在您完成基本行動性和安全性的初始設定之後，您可以建立原則，並將它們套用至安全性 & 合規性中心的使用者群組。 原則要求原則的使用者在基本行動性和安全性中註冊裝置，裝置才能用來存取 Microsoft 365 資料。 您設定的原則決定行動裝置的設定，例如密碼必須重設的頻率，或是否需要資料加密。 如需詳細資訊，請參閱[在基本行動性和安全性](create-device-security-policies.md)   和[Microsoft 365 規範中心](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)建立裝置安全性原則。

如需建立及部署裝置原則的逐步指示，請參閱 [在基本行動性和安全性中建立裝置安全性原則](create-device-security-policies.md)。

如果您想要將特定使用者群組排除在受原則影響之外，您可以將群組新增至排除群組。

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>我是否可以從 Exchange ActiveSync 裝置管理切換至 Microsoft 365 的基本行動及安全性？

如果您已使用 Exchange ActiveSync 原則來管理行動裝置，則可以遵循下列步驟來開始使用基本行動性和安全性：設定基本行動性和安全性。 如需詳細資訊，請參閱 [保護使用者和裝置存取權](https://go.microsoft.com/fwlink/?LinkId=615145) 及 [設定基本行動性和安全性](set-up.md)。

當您將基本行動性和安全性中所建立的原則套用至使用者群組時，這些原則會覆寫 Exchange ActiveSync 行動裝置信箱原則和您先前在 Exchange 系統管理中心中為這些使用者建立的裝置存取規則。

在基本行動性和安全性中註冊裝置後，就會忽略任何 Exchange ActiveSync 行動裝置信箱原則或裝置存取規則套用至裝置。

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>我設定基本行動性和安全性，但是現在我想要將它移除。 步驟有哪些？

不幸的是，在您設定後，您無法直接 "取消「取消」「基本行動性」和「安全性」。 不過，您可以從您已建立的裝置原則中移除使用者安全性群組，將其從使用者群組中移除。 或者，您可以移除裝置原則使其不存在，而且不會強制執行，以停用這些裝置的使用者。 如需詳細資訊，請參閱 [關閉基本行動性和安全性](turn-off.md)。

