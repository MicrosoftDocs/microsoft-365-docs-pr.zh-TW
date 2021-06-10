---
title: 當地語系化使用者體驗
description: 如何當地語系化使用者的裝置
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023258"
---
# <a name="localize-the-user-experience"></a>當地語系化使用者體驗

Microsoft 受管理的電腦裝置的使用者可以在安裝程式期間，選取其選擇的語言 (「全新體驗」 ) 或之後。

## <a name="during-setup-the-out-of-box-experience"></a>在安裝期間 (「全新體驗」 ) 

完成安裝程式的過程中，使用者可以選取其選擇的語言。 這項選取專案會影響下列屬性：

- Windows 10 語言功能：
    - 顯示語言
    - 鍵盤語言
    - 依需求的語言相關功能

- Enterprise 語言功能的 Microsoft 365 Apps：
    - 顯示語言
    - 校對和製作工具

> [!NOTE]
> 使用者可以在安裝程式期間選取語言，以根據需要取得與語言相關的功能。

## <a name="after-completing-setup"></a>完成安裝後

使用者可以在安裝程式完成之後，為 Enterprise 的 Windows 10 和 Microsoft 365 Apps 選取其選擇的語言。 特別是：

- Windows 10 語言功能：
    - 顯示語言
    - 鍵盤語言

- Enterprise 語言功能的 Microsoft 365 Apps：
    - 顯示語言
    - 校對和製作工具

若要讓 [支援](#supported-languages)的 Microsoft 365 Apps 語言供使用者安裝 Enterprise，請將使用者新增至 **新式的 Workplace Office Language_Packs** 群組。 語言將會出現在 Intune 公司入口網站中。


## <a name="supported-languages"></a>支援的語言

若為新裝置，製造商必須提供包含您所需語言的裝置影像。 如果製造商的影像包含的語言不是支援的語言清單中所提供的語言，則服務仍然支援該功能。

若要重複使用現有的裝置，您可能需要與您的 Microsoft 帳戶代表合作，以取得適當的影像。 如需詳細資訊，請參閱 [裝置影像](../service-description/device-images.md)。

Microsoft 受管理的電腦提供的[通用影像](../service-description/device-images.md#universal-image)包含下列語言和 Windows 10：

- 阿拉伯文
- 保加利亞文
- Chinese Simplified
- Chinese Traditional
- 克羅埃西亞文
- 捷克文
- 丹麥文  
- 荷蘭文  
- 英文 (US，GB，AU，CA，) 
- 愛沙尼亞文
- 芬蘭文 
- 法文 (法國，加拿大) 
- 德文
- 希臘文
- 希伯來文
- 匈牙利文
- 印尼文
- 義大利文
- 日文
- 韓文
- 拉脫維亞文
- 立陶宛文
- 挪威文 (巴克摩)
- 波蘭文
- 葡萄牙文 (巴西)
- 葡萄牙文 (葡萄牙)
- 羅馬尼亞文
- 俄文 
- 塞爾維亞文 (拉丁字母) 
- 斯洛伐克文
- 斯洛維尼亞文
- 西班牙文 (西班牙，墨西哥) 
- 瑞典文
- 泰文
- 土耳其文
- 烏克蘭文
- 越南文

Enterprise 的 Microsoft 365 Apps 可能支援稍有不同的清單。

如果您的使用者不需要這裡所列的語言，請使用系統[管理入口網站](access-admin-portal.md)來歸檔[支援要求](../working-with-managed-desktop/admin-support.md)。

## <a name="languages-for-support-and-operations"></a>支援和作業的語言

### <a name="user-support"></a>使用者支援
Microsoft 受管理的電腦提供僅限英文版的支援。 如果使用者在取得協助應用程式中選擇其他語言，他們會從一般的 Microsoft 支援通道取得支援，而不是直接從 Microsoft 受管理的電腦支援。 如需詳細資訊，請參閱 [取得使用者的](../working-with-managed-desktop/end-user-support.md)說明。

如果您的使用者需要其他語言的支援，您必須透過非 Microsoft 支援來源或您自己的組織提供此支援。

### <a name="admin-support-and-operations"></a>系統管理支援和作業
Microsoft 受管理的電腦僅以英文提供系統管理員支援。 這包括管理員入口網站和所有與 Microsoft 受管理的電腦作業的通訊。 除非另有指定，否則您應假設所有系統管理員相關的互動和介面皆為英文。


