---
title: 使用 Autopilot 和 [註冊狀態] 頁面的初次執行體驗
description: 如何部署 ESP 體驗、使用的設定，以及設定變更
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ec3758a2c452b5b20deab3b3776d631ebd48eaef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921939"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>使用 Autopilot 和 [註冊狀態] 頁面的初次執行體驗

Microsoft 受管理的桌面會使用 [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) 和 Microsoft Intune 的 [註冊狀態頁面 (ESP) ](/windows/deployment/windows-autopilot/enrollment-status) ，為您的使用者提供最佳的初次執行體驗。

[註冊狀態] 頁面目前是公開預覽。

## <a name="initial-deployment"></a>初始部署

若要提供 ESP 經驗，您必須在 Microsoft Managed Desktop service 中註冊裝置。 如需註冊的詳細資訊，請參閱 [自行註冊新裝置](../get-started/register-devices-self.md) 或 [取得協力廠商的步驟，以登錄裝置](../get-started/register-devices-partner.md)。

當裝置向服務註冊後，您可以透過 [管理入口網站](https://portal.azure.com/)來歸檔支援憑證，以啟用 Microsoft 受管理桌面裝置的 ESP。 當您檔案票據時，我們會最初將 ESP 設定部署至測試群組。 將其部署到其他後續的部署群組 (會在每24小時) 一開始、快及寬。 若要暫停部署，請 file 另一個票證要求作業保留。

## <a name="autopilot-profile-settings"></a>Autopilot 設定檔設定

Microsoft 受管理的桌面會在用於使用者裝置的 Autopilot 設定檔中，使用下列設定：


|設定  |值  |
|---------|---------|
|部署模式 |  使用者驅動       |
|加入 Azure AD as     |  Azure AD 已加入       |
|語言 (地區)      | 使用者選取        |
|自動設定鍵盤     | 否        |
|Microsoft 軟體授權條款     |  隱藏       |
|隱私權設定     | 隱藏        |
|隱藏變更帳戶選項     | 顯示        |
|使用者帳戶類型     |  標準版       |
|允許白色 Glove OOBE     |  是       |
|套用裝置名稱範本     | 是        |
|輸入名稱     | MMD-% RAND：11%        |

## <a name="enrollment-status-page-settings"></a>註冊狀態頁面設定

Microsoft 受管理的桌面會使用這些設定的註冊狀態頁面體驗：


|設定  |值  |
|---------|---------|
|顯示應用程式與設定檔設定進度     | 是        |
|安裝時間超過指定的分鐘數時顯示錯誤     |  60       |
|發生時間限制錯誤時顯示自訂訊息     |  是       |
|錯誤訊息     | 是的，設定您的裝置所需的時間會比預期的少。 按一下下方開始開始，我們會在背景中完成設定        |
|允許使用者收集有關安裝錯誤的記錄     |  是       |
|僅顯示頁面至已布由全新體驗 (OOBE) 所布建的裝置     | 是        |
|在安裝所有應用程式和設定檔之前封鎖裝置使用     |  是       |
|當安裝錯誤發生時，允許使用者重設裝置     |  是       |
|當安裝錯誤發生時，允許使用者使用裝置     |  是       |
|在這些必要的應用程式被指派給使用者/裝置之前，封鎖裝置的使用     |  新式工作場所-時間修正       |



「註冊狀態」頁面經驗會出現三個階段。 如需詳細資訊，請參閱 [註冊狀態頁面追蹤資訊](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)。

其經驗如下：

1. Autopilot 體驗隨即啟動，且使用者輸入其認證。
2. 裝置會開啟 [註冊狀態] 頁面，並繼續進行裝置準備和裝置安裝階段。 因為停用使用者 ESP，所以第三個步驟 (帳戶設定) *目前已略過* Microsoft Managed Desktop configuration。 裝置重新開機。
3. 重新開機之後，裝置會開啟與 **其他使用者** 的 Windows 登入頁面。
4. 使用者再次輸入他們的認證，桌面隨即開啟。

> [!NOTE]
> 只有在 Windows 10 版本為1903或更新版本的情況時，才會在 ESP 期間部署 Win32 應用程式。

![Autopilot 安裝程式的起始頁面，顯示「裝置準備」和「裝置設定」階段。](../../media/mmd-autopilot-screenshot.png)

## <a name="autopilot-for-pre-provisioned-deployment"></a>預先布建部署的 Autopilot
> [!NOTE]
> Microsoft Managed Desktop 中預先布建的部署的 Autopilot 目前處於公開預覽中。

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>預先布建部署的額外必要條件 Autopilot
- 您必須已啟用 [註冊狀態] 頁面 (ESP) 。 如需詳細資訊，請參閱 [初始部署](#initial-deployment)。
- 裝置必須具有有線網路連接。
- 如果您有在2020年8月之前使用 Microsoft 受管理的桌面入口網站註冊的裝置，請取消註冊，然後再註冊。
- 裝置必須具有工廠映射，其中包含11月2020累積更新 [19H1/19H2 2020.11 c](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) 或 [20H1 2020.11 c](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) （如有適當安裝），或必須 reimaged 與最新的 Microsoft 受管理桌面影像。
- 實體裝置必須支援 TPM 2.0 和裝置證明。 不支援虛擬機器。 預先布建程式會使用 Windows Autopilot 自我部署功能，因此需要使用 TPM 2.0。 TPM 證明程式也需要存取一組 HTTPS URLs，這組 HTTPS 對於每個 TPM 提供者都是唯一的。 如需詳細資訊，請參閱 [Windows Autopilot 網路需求](https://docs.microsoft.com/mem/autopilot/networking-requirements#tpm)中的 Autopilot 自行部署模式和 Autopilot 預先布建部署的專案。

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>預先布建部署的 Autopilot 中的事件順序
1. 必要時，IT 系統管理員 reimages 或重設裝置。
2. IT 系統管理員會引導裝置、達到現成的體驗，並按下 Windows 鍵五次。
3. IT 系統管理員會選取 [Windows Autopilot 布建]，然後選取 [ **繼續**]。 在 [Windows Autopilot 設定] 畫面上，會顯示裝置的相關資訊。
5. IT 系統管理員 **會選取 [** 布建]，以啟動布建處理常式。
6. 裝置啟動 ESP，並透過裝置準備工作和設定階段進行。 在裝置設定階段中，您會視 ESP 設定檔) 的確切設定而定，顯示 (**的應用程式安裝 x** 。
7. 因為我們停用使用者 ESP，所以 Microsoft Managed 桌面設定中的帳戶設定步驟目前已略過。
8. 裝置重新開機。

重新開機之後，裝置會顯示綠色的狀態畫面，並提供重新 **封裝** 按鈕。

> [!IMPORTANT]
> 已知問題： 
> - 在 Autopilot 預先布建的部署重新封裝功能之後，ESP 不會再次執行。
> - Autopilot 用於預先布建的部署時，未重新命名裝置。 裝置只會在經過 ESP 使用者流程之後重新命名。


## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>變更為 Autopilot 和註冊狀態頁面設定

如果 Microsoft 受管理的桌面所用的安裝程式不完全符合您的需求，您可以透過 [管理入口網站](https://portal.azure.com/)來提供支援票證。 以下是您可能需要的設定類型的一些範例：

### <a name="autopilot-settings-change"></a>Autopilot 設定變更

您可能想要要求其他的裝置名稱範本。 不過，您無法變更部署模式、加入 Azure AD As、隱私權設定或使用者帳戶類型。

### <a name="enrollment-status-page-settings-change"></a>註冊狀態頁面設定變更

- [當安裝時間超過指定的分鐘數] 設定時，會顯示 [錯誤] 的較長分鐘數。
- 顯示的錯誤訊息
- 新增或移除「封鎖裝置使用之前，請先安裝這些必要的應用程式，否則會指派給使用者/裝置」設定中的應用程式。

## <a name="required-applications"></a>必要的應用程式

- 您必須以新式的工作場所 *裝置群組* 測試、優先、快速及廣泛的目標為目標應用程式。 必須在「系統」內容中安裝應用程式。 在指派給所有群組之前，請務必先使用 Test 群組中的 ESP 完成測試。
- 任何應用程式都不應該需要重新開機裝置。 建議您在建立應用程式套件時，將應用程式設定為「無任何作用」（如果需要重新開機）。
- 僅在使用者登入裝置時立即需要的核心應用程式中，才限制必要的應用程式。
- 保留所有低於 1 GB 的應用程式總大小，以避免應用程式安裝階段超時。
- 理想狀況下，應用程式不應有任何相依性。 如果您的應用程式 *必須* 有相依性，請務必在 ESP 評估中進行設定、測試及驗證。
- 不需要 "user" 內容的應用程式 (例如，小組) 可以包含在 ESP 的公開預覽中。