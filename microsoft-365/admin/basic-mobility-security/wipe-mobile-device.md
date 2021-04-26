---
title: 在基本行動及安全性中清除行動裝置
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
description: 使用內建基本行動性和安全性，以移除已註冊裝置中的資訊。
ms.openlocfilehash: 7830a0f4ef609f6465c171ecab2c9e3c48198424
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023854"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>在基本行動及安全性中清除行動裝置

您可以使用 Microsoft 365 的內建基本行動及安全性，只移除組織資訊，或執行出廠重設以刪除行動裝置中的所有資訊，並將其還原為出廠設定。

## <a name="before-you-begin"></a>開始之前

行動裝置可以儲存敏感組織資訊，並提供組織的 Microsoft 365 資源的存取權。 為了協助保護您組織的資訊，您可以進行原始重設或移除公司資料：

- **恢復出廠設定**：刪除使用者行動裝置上的所有資料，包括已安裝的應用程式、相片和個人資訊。 當清除完成時，裝置會還原為其出廠設定。

- **移除公司資料**：移除組織中的資料，並在使用者的行動裝置上保留已安裝的應用程式、相片和個人資訊。

- **在擦除裝置時 (出廠重設或移除公司資料)** 中，裝置會從受管理的裝置清單中移除。
    
- **自動重設裝置**：您可以設定基本行動性和安全性原則，當使用者未成功輸入裝置密碼的特定次數時，自動將裝置重設為自動出廠設定。 若要這麼做，請遵循以 [基本行動性和安全性建立裝置安全性原則](create-device-security-policies.md)中的步驟。
    
- **如果您想要知道** 您在擦除其裝置時的使用者體驗，請參閱   [使用者和裝置影響的情況為何？](#whats-the-user-and-device-impact)。

## <a name="wipe-a-mobile-device"></a>清除行動裝置

1. 移至 [Microsoft 365 系統管理中心](../../admin/admin-overview/about-the-admin-center.md)。

2. 在 [搜尋] 欄位中輸入行動裝置管理，並從結果清單中選取 [行動 **裝置管理** ]。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本行動裝置和 Secruity 行動裝置管理選項":::

3. 選取 [ **管理裝置**]。

4. 選取您要抹除的裝置。

5. 選取 [ **管理**]。

6. 選取您要執行的遠端抹除類型。

    - 若要執行完整清除並將裝置還原至其出廠設定，請選取 [ **原廠重設**]。
    - 若要進行選擇性清除並只刪除 Microsoft 365 組織資訊，請選取 [ **移除公司資料**]。
    - 若要從組織中移除裝置，請選取 [ **移除裝置**]。

7. 選取 **[是]** 加以確認。

## <a name="how-do-i-know-it-worked"></a>如何知道這是否正常運作？

您不再在受管理的裝置清單中看到行動裝置。

## <a name="why-would-you-want-to-wipe-a-device"></a>為何要清除裝置？

請清除裝置，原因如下：

- 行動裝置（例如 smartphone 和平板電腦）現在已經變得完全齊全。 這表示您的使用者更容易儲存敏感的公司資訊，例如個人身分識別或機密通訊，並可在旅途中存取。 如果其中一位行動裝置遺失或被盜，擦除裝置可協助避免您的組織的資訊在錯誤的手中結束。
- 當使用者使用已註冊基本行動性和安全性的個人裝置離開組織時，您可以執行出廠重設，以防止組織資訊與該使用者互動。
- 如果您的組織為使用者提供行動裝置，您可能需要重新指派裝置的時間。 在裝置上進行原廠重設，將其指派給新的使用者，有助於確保刪除先前擁有者的任何機密資訊。

## <a name="whats-the-user-and-device-impact"></a>使用者和裝置影響為何？

擦除會立即傳送給行動裝置，而且裝置會在 Azure active directory 中標示為不相容。 當裝置重設為出廠預設值時，會移除所有資料，下表會說明當您移除公司資料時，裝置會移除每種裝置類型的內容。

|**內容影響**|**iOS 10 和更新版本**|**Android 5 及更新版本**|
|:-----|:-----|:-----|
|如果使用 Intune 應用程式保護原則保護裝置，則會清除 Microsoft 365 應用程式資料。 未移除應用程式。 對於不是由行動應用程式管理 (MAM) 原則保護的裝置，Outlook 和 OneDrive 不會移除快取的資料。<br/>**記事** 若要套用 Intune 應用程式保護原則，您必須要有 Intune 授權。|是|是|
|已不再執行基本行動性和裝置安全性所套用的原則設定;使用者可以變更設定。|是|是|
|已移除基本行動性和安全性所建立的電子郵件設定檔，並刪除裝置上的快取電子郵件。|是|不適用|
>[!NOTE]
>您可以在應用程式存放區中的 iOS 和適用于 Android 裝置的播放存放區中取得公司入口網站應用程式。

## <a name="related-topics"></a>相關主題

[設定基本行動與安全性](set-up.md)
