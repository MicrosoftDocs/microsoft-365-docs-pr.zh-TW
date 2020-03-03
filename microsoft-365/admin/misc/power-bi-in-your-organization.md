---
title: 貴組織中的 Power BI
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: 了解 Power BI，以及如何在組織中的使用者可以使用此商務分析服務。
ms.openlocfilehash: 4d89594812486d06629d614ab0c59fba09dcdad8
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361334"
---
# <a name="power-bi-in-your-organization"></a>貴組織中的 Power BI

本頁面說明貴組織的使用者能如何使用 Power BI，以及您如何控制貴組織取得這項服務的方式。
    
## <a name="what-is-power-bi"></a>什麼是 Power BI？

Microsoft Power BI 可讓使用者以視覺化的方式呈現資料、共用所獲得的資訊，以及用直覺式的新方法共同作業。 若要深入瞭解，請參閱 [Power BI 網站](https://powerbi.microsoft.com/en-us/)。
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI 是否符合國家、 區域和產業特定的合規性需求？

若要深入了解 Power BI 規範的詳細資訊，請參閱[Microsoft 信任中心](https://go.microsoft.com/fwlink/?LinkId=785324)。
  
## <a name="how-do-users-sign-up-for-power-bi"></a>使用者如何註冊 Power BI？

如果您是管理員，可以透過 [Power BI 網站](https://powerbi.microsoft.com/en-us/)註冊 Power BI。 您也可以註冊透過 Microsoft 365 系統管理中心 [購買服務] 頁面。 當管理員註冊 Power BI 時，他們可以將使用者訂閱授權指派給應有存取權的使用者。
  
此外，貴組織中的個別使用者也可以透過 [Power BI 網站](https://powerbi.microsoft.com/en-us/).註冊 Power BI。 當貴組織中的使用者註冊 Power BI 時，該使用者便會自動獲指派 Power BI 授權。
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>組織中的個別使用者如何註冊？

組織中的使用者可能屬於下列三種情況：
  
### <a name="scenario-1-your-organization-already-has-an-existing-office-365-environment-and-the-user-signing-up-for-power-bi-already-has-an-office-365-account"></a>情況 1：貴組織已有現有的 Office 365 環境，而且註冊 Power BI 的使用者已有 Office 365 帳戶。

在這種情況下，如果使用者已有租用戶 (例如，contoso.com) 中的公司或學校帳戶，但是還沒有 Power BI，那麼 Microsoft 只要為該帳戶啟用方案，使用者就會自動收到 Power BI 服務使用方式的通知。
  
### <a name="scenario-2-your-organization-has-an-existing-office-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-an-office-365-account"></a>情況 2：貴組織已有現有的 Office 365 環境，但是註冊 Power BI 的使用者並没有 Office 365 帳戶。

情況 2 的使用者已有組織網域中的電子郵件地址 (例如，contoso.com)，但是還沒有 Office 365 帳戶。 在這種情況下，使用者可以註冊 Power BI，而且會自動獲得指定帳戶。 這能讓使用者存取 Power BI 服務。 例如，若名為 Nancy 的員工用她的公司電子郵件地址 (例如，Nancy@contoso.com) 註冊，Microsoft 便會自動將 Nancy 新增到 Contoso 的 Office 365 環境中成為使用者，並且為該帳戶啟動 Power BI。
  
### <a name="scenario-3-your-organization-does-not-have-an-office-365-environment-connected-to-your-email-domain"></a>情況 3：貴組織沒有連線至您電子郵件網域的 Office 365 環境。

貴組織不需要採取任何管理動作，即可享有 Power BI 的優點。
  
> [!IMPORTANT]
> 如果您的組織有多個電子郵件網域，而且您偏好位於相同的租用戶之前任何使用者建立您主要的租用戶, 的所有電子郵件地址副檔名，所有電子郵件地址將網域新增至該租用戶之前任何使用者建立您主要的租用戶。 沒有任何自動化的機制能夠在租用戶之間移動使用者之後他們所建立。 如需有關此程序的詳細資訊，請參閱[如果我有多個網域，我可以控制使用者新增至 Office 365 租用戶？](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)稍後這篇文章和線上[新增網域至 Office 365](../setup/add-domain.md) 。 
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>這對於我目前管理組織使用者身分識別的方式有何影響？

如果貴組織已有現有的 Office 365 環境，而且貴組織的所有使用者都有 Office 365 帳戶，則身分識別管理不會變更。
  
如果貴組織已有現有的 Office 365 環境，但是貴組織的使用者並非都有 Office 365 帳戶，那麼我們會在租用戶中建立使用者，並根據該使用者的公司或學校電子郵件地址指派授權。這表示您在任何特定時間管理的使用者人數，都會隨著貴組織的使用者註冊服務而增加。
  
如果您負責管理內部部署的目錄，並且在使用 Active Directory 同盟服務 (AD FS)，則 Microsoft 不會將使用者新增至您的租用戶，而且任何想加入您租用戶的使用者都會收到一則訊息，要求該人員與其組織管理員連絡。
  
如果貴組織沒有連線至您電子郵件網域的 Office 365 環境，則您管理身分識別的方式不會改變。使用者會加入新的雲端專用使用者目錄，而您也可以選擇以租用戶管理員的身分接管工作，並管理使用者。
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>為使用者管理 Microsoft 所建立租用戶的程序為何？

如果租用戶由 Microsoft 建立，您可以透過下列步驟宣告及管理該租用戶：
  
1. 使用與您要管理之租用戶網域相符的電子郵件地址網域來[註冊 Power BI](https://go.microsoft.com/fwlink/?LinkId=522448)，藉此加入該租用戶。舉個例說，如果 Microsoft 建立了 contoso.com 租用戶，您就得用 @contoso.com 結尾的電子郵件地址加入租用戶。 
    
2. 確認網域擁有權以宣告管理控制：只要成為租用戶，您就可以透過確認網域擁有權的方式，將自己升級為管理員角色。其步驟如下：
 
::: moniker range="o365-worldwide"
   
3. 前往 [https://admin.microsoft.com](https://admin.microsoft.com)。
 

::: moniker-end

::: moniker range="o365-germany"

3. 請移至 [https://portal.office.de](https://portal.office.de)。

::: moniker-end

::: moniker range="o365-21vianet"

3. 請移至 [https://portal.partner.microsoftonline.cn](https://portal.partner.microsoftonline.cn)。

::: moniker-end

    
4. 選取左上角的應用程式啟動器圖示，然後選擇 [管理員]****。
    
    ![The Office 365 app launcher with the Admin app highlighted](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. 閱讀 [**成為管理員**] 頁面上的指示，然後選取 [**是，我想成為系統管理員**。
    
    > [!NOTE]
    >  如果沒有出現這個選項中, 已經有系統管理員的地方。 
  
## <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>如果我有多個網域，我可以控制新增使用者的 Office 365 租用戶嗎？

如果您不做任何動作，則會針對每一個使用者電子郵件網域和子網域建立租用戶。
  
如果您希望所有使用者都位於相同的租用戶 (不論他們的電子郵件地址副檔名為何)，請執行以下動作：
  
- 提前建立目標租用戶或使用現有租用戶，並新增您要在該租用戶內合併的所有現有網域與子網域。這麼一來，電子郵件地址以這些網域和子網域結尾的所有使用者，都會在註冊時自動加入目標租用戶。
    
> [!IMPORTANT]
> 在建立租用戶之後，便沒有任何支援的自動化機制能夠在租用戶之間移動使用者。 若要了解將網域新增至單一 Office 365 租用戶，請參閱[新增網域至 Office 365](../setup/add-domain.md)。 
  
> [!IMPORTANT]
> 其他資訊及管理租用戶的指引，請參閱[什麼是 Power BI 管理？](https://docs.microsoft.com/power-bi/service-admin-administering-power-bi-in-your-organization)。 
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>如何防止使用者加入我現有的 Office 365 租用戶？

有可身為系統管理員可防止使用者加入您現有的 Office 365 租用戶採取的步驟。 如果您不要封鎖這，使用者嘗試登入將會失敗，並會被導向他們連絡其組織的系統管理員。您不需要重複此程序，如果您已停用自動授權散佈之前 （例如 Office 365 教育版的學生與教職員）。
  
執行這些步驟必須使用 Windows PowerShell。 若要開始使用 Windows PowerShell，請參閱 [PowerShell 快速入門指南](https://go.microsoft.com/fwlink/p/?LinkID=286814)。
  
若要執行下列步驟，您必須安裝[適用於 Windows PowerShell 的 Azure Active Directory 模組](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5)的最新 64 位元版本。
  
您選取的連結後，請選取 「**執行**」，以執行安裝程式套件。 
  
 **停用自動租用戶加入**：使用這個 Windows PowerShell 命令可防止新使用者加入受管理的租用戶：
  
停用新使用者的自動租用戶加入： `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
啟用新使用者的自動租用戶加入： `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> 此封鎖防止組織從註冊 Power BI 中的新使用者。 註冊 Power BI 之前停用新 signups 組織的使用者仍會保留其授權。 請參閱[如何對已註冊的使用者移除 Power BI？](#how-do-i-remove-power-bi-for-users-that-already-signed-up)如需如何移除有，先前註冊服務的使用者存取 Power BI 的指示。 
  
## <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>如何允許使用者加入我現有的 Office 365 租用戶？

若要允許使用者加入您的租用戶，請參考上一個問題的說明，然後執行相反的命令：  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>我要如何確認我是否已在租用戶中進行封鎖？

使用下列 PowerShell 指令碼： `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>如何防止現有使用者開始使用 Power BI？

 **停用自動授權散佈：** 您可以使用這個 Windows PowerShell 指令碼，停用現有使用者的自動授權散佈。 您不需要重複此程序，如果您已停用自動授權散佈之前 （例如 Office 365 教育版的學生與教職員）。 
  
停用現有使用者的自動授權散佈： `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
啟用現有使用者的自動授權散佈： `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> *AllowAdHocSubscriptions*標幟可以用來控制許多使用者功能，在您的組織，包括使用者註冊 Azure 版權管理服務的能力。 如果變更這個旗標，將會影響上述所有功能。 
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>如何允許我現有的使用者註冊使用 Power BI？

若要允許現有的使用者註冊使用 Power BI，請參考上一個問題的說明，然後執行相反的命令：  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>如何對已註冊的使用者移除 Power BI？

有的使用者雖已註冊 Power BI，但是您不希望他們再繼續擁有 Power BI 的存取權，這時候您可以移除該使用者的 Power BI 授權。

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。
  
1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。
    
2. 尋找您想要移除的授權的使用者，然後選取其名稱。
    
3. 在 [**授權和應用程式**] 索引標籤上，清除 [ **Microsoft Power BI** ] 核取方塊。
    
4. 選取 [儲存變更]****。

::: moniker-end

  
::: moniker range="o365-germany"

1. 在系統管理中心中，移至 [使用者]**** \> [作用中使用者]<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank"></a> 頁面。

2. 尋找您想要移除的授權的使用者，然後選取其名稱。
    
3. 選取 [**產品授權**] 旁邊的 [**編輯**]。 
    
4. 切換關閉 [ **Microsoft Power BI** ] 選項。
    
5. 選取 **[儲存]**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。

2. 尋找您想要移除的授權的使用者，然後選取其名稱。
    
3. 選取 [**產品授權**] 旁邊的 [**編輯**]。 
    
4. 切換關閉 [ **Microsoft Power BI** ] 選項。
    
5. 選取 [儲存]****。

::: moniker-end 


## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>我怎麼知道新使用者何時已加入我的租用戶？

已在本方案中加入您租用戶的使用者，會獲得專屬授權的指派，您可以在管理員儀表板的 [作用中的使用者] 窗格內篩選這項授權。
  
若要建立此新的檢視中，在系統管理中心，請依照下列步驟中[建立自訂使用者檢視](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view)。 [**指派產品授權**，請選取 [ **Microsoft Power BI**]。 在建立新的檢視之後，您將能夠看到所有使用者在您的租用戶中有此程式中註冊。
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>我還需要準備其他任何事項嗎？

您可能會遇到增加密碼重設要求次數的情況。 有關此程序的資訊，請參閱[重設使用者的密碼](../add-users/reset-passwords.md)。
  
您可以透過標準程序在系統管理中心的租用戶移除使用者。 但是，如果使用者仍擁有組織發給的有效電子郵件地址，除非您不讓所有使用者加入，否則他們還是可以重新加入。
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-office-365-tenant"></a>為什麼我的 Office 365 租用戶中出現 1 百萬個 Microsoft Power BI 的授權？

如果貴組織符合條件，則組織中的使用者就有權使用 Microsoft Power BI 服務，而這些授權正代表租用戶中新 Power BI 使用者的可用權限。 這些授權為免費使用。 如果您已選擇要允許使用者註冊 Power bi 本身，它們會被指派其中一個這些可用的可用授權當他們完成註冊程序。 您也可以選擇將這些授權指派給使用者自行透過系統管理中心。
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>這是免費的嗎？ 使用這些授權需要付費嗎？

這些是免費版 Power BI 的授權。 如果您對額外的功能有興趣，不妨參考一下 Power BI 專業版。
  
## <a name="why-1-million-licenses"></a>為什麼有 1 百萬個授權？

我們選擇大大多數的組織會有充裕授權指派給其使用者提供這項優惠的數字。
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>如果我需要 100 萬個以上的授權，該怎麼辦？

如需取得更多授權，請連絡您的 Microsoft 客戶代表取得詳細資訊。
