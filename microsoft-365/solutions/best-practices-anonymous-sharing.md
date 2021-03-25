---
title: 未驗證共用的最佳做法
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: 在本文中，您將了解與未驗證使用者共用檔案和資料夾的最佳做法。
ms.openlocfilehash: acc825a8fc445d224fbc91dd12dace2a5e1b25c8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199522"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a>與未驗證使用者共用檔案和資料夾的最佳做法

未驗證共用 (*任何人* 連結) 在許多案例下都相當方便。 *任何人* 連結為共用最簡單的方式：人員可以不經驗證就開啟連結，且可隨意將它傳送給其他人。

一般來說，並非組織中的所有內容都適合進行未驗證共用。 本文涵蓋可協助您建立一個環境的選項，您的使用者能夠在該環境中未驗證共用檔案和資料夾，但在其中有一些既有措施可協助保護組織內容的安全。

> [!NOTE]
> 若要讓未驗證共用運作，您必須為組織以及您將使用的個別網站或小組啟用該功能。 如需您要啟用的案例，請參閱[與組織外部人員共同作業](collaborate-with-people-outside-your-organization.md)。

## <a name="set-an-expiration-date-for-anyone-links"></a>設定任何人連結的到期日

檔案通常會長時間儲存在網站、群組和小組。 有時候，有一些資料保留原則會要求將檔案保留數年。 如果將這類檔案與未驗證的人員共用，可能導致未來非預期地存取和變更這些檔案。 若要降低此可能性，您可以為 *任何人* 連結設定到期時間。

*任何人* 連結到期後，就無法再用來存取內容。

設定組織中任何人的連結到期日。

1. 開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。
2. 在左側導覽窗格中，按一下 [共用]。
3. 在 **[為任何人連結選擇過期和授權選項]** 下，選取 **[這些連結必須在此天數內過期]** 核取方塊。</br>
   ![SharePoint 組織層級任何人連結到期設定的螢幕擷取畫面](../media/sharepoint-organization-anyone-link-expiration.png)
4. 在方塊中輸入天數，然後按一下 [儲存]。

在特定網站上，設定任何人連結的到期日

1. 開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。
2. 在左側瀏覽窗格中，展開 **[網站]**，然後按一下 **[作用中網站]**。
3. 選取要變更的網站，然後按一下 **[共用]**。
4. 在 **[任何人連結的進階設定]** 的 **[任何人連結到期日]** 底下，清除 **[與組織層級相同設定]** 核取方塊。</br>
   ![SharePoint 網站層級任何人連結到期設定的螢幕擷取畫面](../media/sharepoint-organization-anyone-link-expiration-site.png)
5. 選取 **[這些連結必須在此天數內過期]** 選項，然後在方塊中輸入天數。
6. 按一下 **[儲存]**。

請注意，*任何人* 連結到期之後，就可以使用新的 *任何人* 連結重新共用檔案或資料夾。

您可以使用 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite)，為特定 OneDrive 設定 *任何人* 連結到期日。

## <a name="set-link-permissions"></a>設定連結權限

根據預設，檔案的 *任何人* 連結會允許人員編輯檔案，而資料夾的 *任何人* 連結則會允許人員編輯和檢視檔案，以及上傳新檔案到資料夾。 您可以獨立將檔案和資料夾的這些權限變更為僅供檢視。

如果您想要允許未驗證共用，但擔心未驗證的人員修改組織的內容，請考慮將檔案和資料夾權限設定為 [檢視]。

設定組織中任何人連結的權限。

1. 開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。
2. 在左側導覽窗格中，按一下 [共用]。
3. 在 [「任何人」連結的進階設定] 底下，選取您要使用的檔案和資料夾權限。</br>
   ![SharePoint 組織層級任何人連結權限設定的螢幕擷取畫面](../media/sharepoint-organization-anyone-link-permissions.png)

將 *任何人* 連結設為 [檢視] 時，使用者仍然可以與來賓共用檔案和資料夾，並使用 *特定人員* 連結提供編輯權限。 這些連結要求組織外的人員驗證為來賓身分，而您可以追蹤和稽核使用這些連結共用的檔案和資料夾上的來賓活動。

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a>將預設連結類型設定為僅適用組織中的人員

為組織啟用 *任何人* 共用時，預設的共用連結一般會設定為 **任何人**。 雖然這對使用者而言很方便，但可能會增加無意間未驗證共用的風險。 如果使用者在共用機密文件時忘記變更連結類型，他們可能會意外建立不需要驗證的共用連結。

您可以透過將預設連結設定變更為僅適用組織內部人員的連結，來降低此風險。 這麼一來，想要進行未驗證共用的使用者，必須特別選取該選項。

為組織設定預設的檔案和資料夾共用連結
1. 開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。
2. 在左側導覽窗格中，按一下 **[共用]**。
3. 在 **[檔案與資料夾連結]** 下，選取 **[只有貴組織中的人員]**。

   ![SharePoint 預設連結類型設定的螢幕擷取畫面](../media/sharepoint-default-sharing-link-company-link.png)

4. 按一下 **[儲存]**

為特定網站設定預設的檔案和資料夾共用連結
1. 開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。
2. 在左側瀏覽窗格中，展開 **[網站]**，然後按一下 **[作用中網站]**。
3. 選取要變更的網站，然後按一下 **[共用]**。
4. 在 **[預設的共用連結類型]** 底下，清除 **[與組織層級設定相同]** 核取方塊。

   ![SharePoint 網站層級預設連結類型設定的螢幕擷取畫面](../media/sharepoint-organization-anyone-link-permissions-site.png)

5. 選取 **[只有貴組織的人員]** 選項，然後按一下 **[儲存]**。

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a>防止未經驗證的敏感性內容共用

您可以使用 [資料外洩防護 (DLP)](../compliance/data-loss-prevention-policies.md) 以防止未經驗證的敏感性內容共用。 資料外洩防護可根據檔案的敏感度標籤、保留標籤或檔案本身的敏感性資訊採取行動。

建立 DLP 規則
1. 在 Microsoft 365 合規性系統管理中心中，移至 [資料外外洩防護頁面](https://compliance.microsoft.com/datalossprevention)。
2. 按一下 **[建立原則]**。
3. 選擇 **[自訂]** ，然後按一下 **[下一步]**。
4. 輸入原則的名稱，並按 **[下一步]**。
5. 在 **[套用原則的位置]** 頁面上，關閉 **SharePoint 網站** 和 **OneDrive 帳戶** 以外的所有設定，然後按一下 **[下一步]**。
6. 在 **[定義原則設定]** 頁面上，按一下 **[下一步]**。
7. 在 **[自訂進階資料外洩防護規則]** 頁面上，按一下 **[建立規則]**，然後輸入規則的名稱。
8. 在 [條件 **]** 底下，按一下 [新增條件 **]**，並選擇 [內容包含 **]**。
9. 按一下 **[新增]**，然後選擇您想要防止未經授權共用的資訊類型。

   ![條件選項、敏感性資訊類型、敏感性標籤及保留標籤的螢幕擷取畫面。](../media/limit-accidental-exposure-dlp-conditions.png)

10. 在 [動作 **]** 底下，按一下 [新增動作 **]**，然後選擇 [限制存取或加密 Microsoft 365 位置中的內容 **]**。
11. 選取 **[限制存取權或加密 Microsoft 365 位置中的內容]** 核取方塊，然後選擇 **[僅限透過「具有連結的任何人」 選項獲得存取內容的人員]** 選項。

      ![DLP 規則動作選項的螢幕擷取畫面](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. 按一下 **[儲存]**，然後按 **[下一步]**。
13. 選擇您的測試選項，然後按一下 **[下一步]**。
14. 按一下 [提交 **]**，然後按一下 [完成 **]**。

## <a name="protect-against-malicious-files"></a>防範惡意檔案

允許匿名使用者上傳檔案時，可能會增加某人上傳惡意檔案的風險。 在 Microsoft 365 中，您可以使用適用於 Office 365 的 Defender 中的 *安全附件* 功能，自動掃描已上傳的檔案並隔離發現不安全的檔案。

開啟安全附件
1. 開啟 [安全性與合規性系統管理中心] 的 [[ATP 安全附件] 頁面](https://protection.office.com/safeattachmentv2)。
2. 按一下 **[通用設定]**。
3. 開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP。

   ![安全性與合規性中心安全附件設定的螢幕擷取畫面](../media/safe-attachments-setting.png)

4. 或者，也可以開啟 [安全文件]，然後按一下 **[儲存]**

請參閱 [適用於 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](../security/office-365-security/mdo-for-spo-odb-and-teams.md) ，並 [開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md) 以取得更多指導方針。

## <a name="add-copyright-information-to-your-files"></a>新增著作權資訊至您的檔案

如果您在 Microsoft 365 合規性系統管理中心使用敏感度標籤，即可以設定您的標籤，以自動新增浮水印或頁首或頁尾至組織的 Office 文件中。 這麼一來，您就可以確定共用的檔案包含著作權或其他擁有權資訊。

新增頁尾至標籤的檔案

1. 開啟 [Microsoft 365 合規性系統管理中心](https://compliance.microsoft.com)。
2. 在左側導覽窗格中的 **[解決方案]** 底下，按一下 **[資訊保護]**。
3. 按一下您要新增頁尾的標籤，然後按一下 **[編輯標籤]**。
4. 按一下 **[下一步]** 以移至 **[內容標示]** 索引標籤，然後 **[開啟]** 內容標示。
5. 選取要新增的文字類型的核取方塊，然後按一下 [自訂文字]。
6. 輸入要新增至文件的文字，選取需要的文字選項，然後按一下 [儲存]。</br>
   ![敏感度標籤內容標示設定的螢幕擷取畫面](../media/content-marking-for-anonymous-sharing.png)
7. 按一下 **[下一步]** 以移至精靈結尾，然後按一下 **[儲存標籤]**。

為標籤啟用內容標示後，當使用者套用該標籤，您指定的文字就會新增至 Office 文件中。

## <a name="see-also"></a>另請參閱

[敏感度標籤概觀](/Office365/SecurityCompliance/sensitivity-labels)

[與來賓共用時限制意外暴露檔案](share-limit-accidental-exposure.md)

[建立安全的來賓共用環境](create-secure-guest-sharing-environment.md)