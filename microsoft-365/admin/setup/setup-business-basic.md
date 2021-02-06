---
title: 設定 Microsoft 365 商務基本版
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: 瞭解如何設定 Microsoft 365 商務基本版訂閱。
ms.openlocfilehash: 43ae19b24058429c9276bd44dd4c3960c792ca0d
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126182"
---
# <a name="set-up-microsoft-365-business-basic"></a>設定 Microsoft 365 商務基本版

 觀看有關設定 Microsoft 365 商務基本版的短片。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="add-your-domain-to-personalize-sign-in"></a>新增您的網域以個人化登入

當您購買 Microsoft 365 商務基本版時，您可以選擇使用自己的網域，或在註冊時購買一個網域。

- 如果您在註冊時購買新的網域，則您的網域全都都已設定完畢，您可以移至 [新增使用者並指派授權](#add-users-and-assign-licenses)。

 ::: moniker range="o365-worldwide"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

::: moniker-end

::: moniker range="o365-germany"

1. 如果您使用的是 Office 365 Germany，請移至[此系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)。

::: moniker-end

::: moniker range="o365-21vianet"

1. 如果您使用的是由 21Vianet 運作的 Office 365，請移至[此系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)。

::: moniker-end 

2. 請選擇 **[移至設定]** 來啟動精靈。
    
3. 在 **[新增網域]** 步驟中，輸入您要使用的網域名城（例如 contoso.com）。

    > [!IMPORTANT]
    > 如果您在註冊時購買了網域，就不會在此看到 **[新增網域]** 步驟。 改移至 [[新增使用者]](#add-users-and-assign-licenses)。

    
4. 按照精靈中的步驟操作，在任何可驗證您擁有網域的[ 適用於 Office 365 的 DNS 主機服務供應商中建立 DNS 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。 如果您知道您的網域主機，請參閱 [[主機特定指示]](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。

    如果您的主機服務供應商是 GoDaddy 或透過 [[網域連結]](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) 所啟用的另一個主機，這個過程便會很簡單，您自動便會被要求登入，並讓 Microsoft 替您進行驗證。

    ![在 GoDaddy 確認存取頁面上，選取 [授權]。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>新增使用者並指派授權

您可以在精靈中新增使用者，或稍後在系統管理中心[[新增使用者]](../add-users/add-users.md)。 此外，如果您有本機網域控制站，您可以使用 [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)新增使用者。

## <a name="add-users-in-the-wizard"></a>在精靈中新增使用者

您在精靈中所新增的任何使用者，都會自動指派 Microsoft 365 商務基本版授權。

1. 如果您的 Microsoft 365 商務基本版訂閱有現有的使用者 (例如，如果您使用 Azure AD Connect 的話)，系統會提供立即將授權指派給他們的選項。 請繼續進行，為他們新增授權。

2. 新增使用者之後，您也會看到與您新增之使用者共用認證的選項。 您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。

## <a name="connect-your-domain"></a>連接您的網域

> [!NOTE]
> 如果您選擇使用 onmicrosoft 網域，或使用 Azure AD Connect 來設定使用者，您將不會看到此步驟。
  
若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。
  
1. 設定精靈通常會偵測您的註冊機構，並提供您一個逐步指示連結，讓您更新在註冊機構網站上的 NS 記錄。 如果沒有，請[變更名稱伺服器，以透過任何網域註冊機構來設定 Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)。 

    - 如果您有現有的 DNS 記錄，例如現有網站，但您的 DNS 主機已啟用 [網域連線](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)，請選擇 **[為我新增記錄]**。 在 **[選擇您的線上服務]** 頁面，接受所有預設值，並選擇 **[下一步]**，然後在您的 DNS 主機頁面上選擇 **[授權]**。
    - 如果您的現有 DNS 記錄中有其他 DNS 主機(該主機無法用於網域連線)，您最好能自己管理自己的 DNS 記錄，以確保現有服務保持連線。 如需詳細資訊，請參閱 [網域基本資訊](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。

2. 按照精靈中的步驟進行，系統會為您設定電子郵件及其他服務。

    註冊程序完成後，系統會將您導向系統管理中心，您可以在該處新增使用者，以及指派授權。 完成初始安裝後，您可以使用系統管理中心的 [設定] 頁面繼續設定和設定訂閱隨附的服務。

    如需有關安裝精靈和系統管理中心 [設定] 頁面的詳細資訊，請參閱[安裝精靈和設定頁面之間的差異](o365-setup-wizard-and-setup-page.md)。