---
title: 將 Microsoft Defender ATP macOS 裝置登記至 Jamf Pro
description: 將 Microsoft Defender ATP macOS 裝置登記至 Jamf Pro
keywords: microsoft，defender，atp，mac，安裝，部署，卸載，intune，jamfpro，macos，catalina，mojave，高塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ea71875dedf7e8706c9022420abd63bc5eb20c69
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689722"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>在 macOS 裝置上為 Jamf Pro 註冊 Microsoft Defender for Endpoint 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>註冊 macOS 裝置

有多種方法可以取得 JamF 的登記。

本文將引導您進行兩種方法：

- [方法1：註冊邀請](#enrollment-method-1-enrollment-invitations)
- [方法2：預備登記](#enrollment-method-2-prestage-enrollments)

如需完整清單，請參閱 [關於電腦註冊](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)。


## <a name="enrollment-method-1-enrollment-invitations"></a>註冊方法1：註冊邀請

1. 在 Jamf Pro 儀表板中，流覽至 [ **註冊邀請**]。

    ![設定 settings1 的影像](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. 選取 [ **+ 新增**]。

    ![自動產生的標誌說明的特寫](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. 在 **[指定邀請** 的收件者] 底下 > 在 [ **電子郵件地址** ] 中，輸入收件者 (es) 的電子郵件地址。

    ![設定 settings2 的影像](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![設定 settings3 的影像](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    例如： janedoe@contoso.com

    ![設定 settings4 的影像](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. 設定邀請的訊息。

    ![設定 settings5 的影像](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![設定 settings6 的影像](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![設定 settings7 的影像](images/3ced5383a6be788486d89d407d042f28.png)

    ![設定 settings8 的影像](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>註冊方法2：預備登記

1. 在 Jamf Pro 儀表板中，流覽至 [預先 **安排註冊**]。

    ![設定 settings9 的影像](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. 依照電腦預先加以 [登記](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)中的指示進行。

## <a name="enroll-macos-device"></a>註冊 macOS 裝置

1. 選取 [ **繼續** ]，然後從 [ **系統偏好** 設定] 視窗中安裝 CA 憑證。

    ![Jamf Pro enrollment1 的影像](images/jamfpro-ca-certificate.png)

2. 安裝 CA 憑證之後，請回到瀏覽器視窗，然後選取 [ **繼續** ] 並安裝 MDM 設定檔。 

    ![Jamf Pro enrollment2 的影像](images/jamfpro-install-mdm-profile.png)

3. 選取 [ **允許** 從 JAMF 下載]。

    ![Jamf Pro enrollment3 的影像](images/jamfpro-download.png)

4. 選取 [ **繼續** ]，繼續執行 MDM 設定檔安裝。 

    ![Jamf Pro enrollment4 的影像](images/jamfpro-install-mdm.png)

5. 選取 [ **繼續** ] 安裝 MDM 設定檔。

    ![Jamf Pro enrollment5 的影像](images/jamfpro-mdm-unverified.png)

6. 選取 [ **繼續**  ] 以完成設定。 

    ![Jamf Pro enrollment6 的影像](images/jamfpro-mdm-profile.png)
