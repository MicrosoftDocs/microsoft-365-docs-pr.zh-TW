---
title: Microsoft OneDrive
description: Microsoft Managed Desktop 如何為已註冊的裝置設定 OneDrive
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、應用程式、企業營運服務應用程式、LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904837"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft 受管理的桌上型電腦使用 [業務 OneDrive](/onedrive/plan-onedrive-enterprise) 作為所有 Microsoft 受管理桌面裝置的雲端儲存服務，以確保裝置盡可能具有無狀態。 不管使用者登入的裝置為何，使用者都能找到他們的檔案。 例如，如果您將 Microsoft 受管理的桌面裝置更換為新的桌面裝置，則檔案會自動同步處理至新的裝置。

在 Microsoft 受管理的裝置上，預設會自動設定這些設定：

- OneDrive 會以無訊息方式設定使用者帳戶，並自動登入 (，但沒有使用者互動) 至用來登入 Windows 的使用者帳戶。 如需詳細資訊，請參閱以 [無訊息方式設定使用者帳戶-OneDrive](/onedrive/use-silent-account-configuration)

- 已啟用檔隨選功能，讓使用者可以在 OneDrive 存取其雲端儲存中的檔案，而不需要不必要地使用磁碟空間。 如需詳細資訊，請參閱 [Save disk space with OneDrive Files On Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)。

- 已知的資料夾移動功能會以無訊息方式啟用，以在雲端中備份使用者的資料，讓他們可以從任何裝置存取其檔案。 如需詳細資訊，請參閱 [備份您的檔、圖片和桌面資料夾與 OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)。

- 使用者無法停用已知的資料夾移動功能或變更已知資料夾的位置，以確保 Microsoft 受管理桌面裝置的一致體驗。

## <a name="user-experience"></a>使用者體驗

當 Microsoft 受管理的桌面使用者收到新的裝置時，他們會在設定裝置時輸入其 Azure 認證，以經歷初次執行的體驗。 完成此程式之後，即可存取其桌面並獲得 OneDrive 體驗。

1. 系統會告知使用者已設定 OneDrive，且已自動登入 OneDrive。

:::image type="content" source="media/onedrive-sync.png" alt-text="通知讀取您現在正在同步處理 OneDrive，您可以在 OneDrive 中編輯檔案。按一下這裡以查看您的檔案":::

2. 系統會告訴使用者已為使用者設定 OneDrive 已知資料夾移動。

:::image type="content" source="media/onedrive-folders.png" alt-text="讀取您的 IT 部門的通知已備份重要的資料夾。現在，資料夾會備份至 OneDrive，並可從其他裝置取得。":::

3. 若要在裝置重設或 reimaged 時避免桌面上重複的圖示，系統會自動從 OneDrive 同步中移除 Microsoft Edge 和 Microsoft 小組圖示，如檔案瀏覽器中的此視圖所示。

:::image type="content" source="media/onedrive-teams.png" alt-text="檔案瀏覽器顯示小組和 Edge 清單，其中包含已清除的核取方塊及未同步處理的懸停文字讀取。":::


## <a name="onedrive-sync-restrictions"></a>OneDrive 同步處理限制

如果您需要限制 OneDrive 同步處理，建議您透過 Azure Active Directory 條件式存取原則來控制存取。 如需詳細資訊，請參閱 [在 OneDrive 同步處理應用程式中啟用條件式存取支援](/onedrive/enable-conditional-access)。

如果您的組織中不能使用 Azure AD 條件式存取原則，您的 IT 系統管理員應該遵循下列步驟：

1. 如果您還沒有知道，請查詢您的租使用者識別碼（如 [ [尋找您的 Microsoft 365 租使用者識別碼](/onedrive/find-your-office-365-tenant-id)] 所述）。
2. 登入 OneDrive 系統管理中心，然後在左窗格中選取 [ **同步** 處理]。 選取 [ **只允許在加入特定網域的電腦上進行同步** 處理] 核取方塊，然後將租使用者識別碼新增至網域清單。 如需詳細資訊，請參閱 [僅允許同步處理加入特定網域的電腦](/onedrive/allow-syncing-only-on-specific-domains)。

> [!NOTE]
> 此指南只適用于 Microsoft 受管理的電腦中的承租人。 其他使用中的設定不在本文中討論。