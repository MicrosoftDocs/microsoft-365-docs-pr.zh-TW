---
title: 設定輸出垃圾郵件原則
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 如果您使用該服務來傳送輸出電子郵件，便會一律啟用輸出垃圾郵件篩選功能，從而保護使用該服務的組織及其預期的收件者。
ms.openlocfilehash: 43939022dc365f5b28418d96ae1217e159312da1
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808438"
---
# <a name="configure-the-outbound-spam-policy"></a>設定輸出垃圾郵件原則

如果您使用該服務來傳送輸出電子郵件，便會一律啟用輸出垃圾郵件篩選功能，從而保護使用該服務的組織及其預期的收件者。 輸入篩選相似，輸出垃圾郵件篩選連線篩選和內容篩選組成，可讓部分的特定控制項，以處理外寄郵件。 輸出垃圾郵件篩選原則設定類型：

- 預設值： 預設輸出垃圾郵件篩選原則用來設定全公司的輸出垃圾郵件篩選設定。 此原則不能重新命名且永遠開啟。

- 自訂： 自訂輸出垃圾郵件篩選原則細微及可套用至特定使用者、 群組或組織中的網域。 自訂原則的優先順序永遠高於預設原則。 您可以變更自訂原則執行藉由變更的每個自訂原則; 優先順序的順序不過，只有最高的優先順序 （亦即數字最接近 0） 如果使用者符合多個原則，將會套用原則。

> [!NOTE]
> 如需詳細資訊[輸出垃圾郵件在 Office 365 中的控制項](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls)的詳細資訊。 <br><br> 更新 「 輸出垃圾郵件原則是目前已導入，預期更新完成年 10 月 2019年的結尾。 在這段時間部分選項可能無法使用。  如需詳細資訊，請參閱[Office 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?featureid=54125) 

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

預估完成時間：5 分鐘

您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱 [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)主題中的＜反垃圾郵件＞項目。

下列程序也可以透過遠端 PowerShell 執行。 使用[Get-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) cmdlet 來檢閱您的設定，以及[Set-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)編輯您的輸出垃圾郵件原則設定。 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (部分機器翻譯)。 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

## <a name="use-the-security-and-compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>若要編輯預設輸出垃圾郵件原則使用安全性與合規性中心 (SCC)

使用下列程序編輯預設輸出垃圾郵件原則：

### <a name="to-configure-the-default-outbound-spam-policy"></a>設定預設輸出垃圾郵件原則

1. 在 SCC 中，瀏覽至**威脅管理，** \> **原則** \> **反垃圾郵件**

2. 展開 [**輸出垃圾郵件篩選原則 (always ON)** ] 區段中，按一下 [**編輯原則**]。

3. 展開 [**通知**] 區段中選取下列核取方塊相關外寄郵件，然後選取 [**新增人員**至在隨附的對話方塊中新增相關聯的電子郵件地址或地址。 （這些可通訊群組清單如果它們解析為有效的 SMTP 目的地）：

   - **傳送至下列電子郵件地址或地址的所有可疑輸出電子郵件訊息的複本**： 這些是由 （不管其 SCL 分級） 篩選標示為垃圾郵件的郵件。 篩選器不會拒絕這些郵件，而是會透過較高風險傳遞集區路由傳送這些郵件。 請以分號分隔多個地址。 請注意，指定的收件者會當作密件副本 (Bcc) 地址收到郵件 ([寄件者] 和 [收件者] 欄位為原始寄件者和收件者)。

   - **傳送到下列電子郵件地址傳送輸出垃圾郵件封鎖寄件者時通知**： 以分號分隔多個地址。

   當大量的垃圾郵件或其他傳送異常偵測到來自特定使用者時，限制使用者只能傳送電子郵件和通知傳送給指定的電子郵件地址。

   網域的系統管理員 (使用此設定指定) 會收到通知，告知已封鎖該使用者的輸出郵件。  若要查看此通知的外觀，請參閱[當封鎖寄件者時傳送輸出垃圾郵件的範例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)。

   > [附註] ！系統也警示指出使用者已受到限制。  若要了解關於警示以及如何復原使用者的詳細資訊，請參閱[移除之後傳送的垃圾郵件的限制使用者入口網站中的使用者](removing-user-from-restricted-users-portal-after-spam.md)。

4. 展開 [**收件者限制**] 區段中指定的使用者可以傳送至每小時每日的最大數目以及內部和外部收件者的收件者數目上限。

    > [附註] ！對於任何輸入數目上限為 10000。  如需詳細資訊，請參閱[接收及傳送限制內 Exchange online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

7. 指定當使用者超過指定的限制時要採取的**動作**。  可行動作如下所示：
    * **禁止使用者傳送郵件到下一天為止**。  一旦已經超過任何傳送限制 （內部、 外部或每日） 將會產生警示的系統管理員和使用者將無法傳送任何進一步的電子郵件，直到下的一天，根據 UTC 時間。 沒有管理員可覆寫此區塊方法。

    * **禁止使用者傳送郵件**。  一旦已經超過任何傳送限制 （內部、 外部或每日） 將會產生警示的系統管理員和使用者將無法傳送任何進一步的電子郵件直到系統管理員移除限制。  在這些情況下使用者將會列在[受限的使用者] 頁面](removing-user-from-restricted-users-portal-after-spam.md)上。  一旦從清單中移除使用者不會限制一次的那一天。

    * **任何巨集指令/警示僅**。 一旦已經超過任何傳送限制 （內部、 外部或每日） 將會產生警示的系統管理員，但會限制使用者採取任何動作。

6. 展開 [**適用於**] 區段，然後再建立 [條件式規則，以指定使用者、 群組及要套用此原則的網域。 如果它們都是唯一，則可以建立多個條件。  附註： 使用者在指定多個條件時，必須符合所有條件。  

      * 若要選取使用者，請選取 [**寄件者**。 在後續的對話方塊中，從使用者選擇器清單中選取您公司的一或多位寄件者，然後按一下 [新增]。 若要新增不在清單上的寄件者，請輸入其電子郵件地址並按一下 [檢查名稱]。 當您選取完畢時，按一下 [確定] 回到主畫面。

      * 若要選取群組]，選取 [**寄件者是的成員**。 接著，在後續的對話方塊中，選取或指定群組。 按一下 [確定] 回到主畫面。

      * 若要選取網域，請選取 [**寄件者網域是**。 接著，在後續的對話方塊中，新增網域。 按一下 [確定] 回到主畫面。

        您可以建立規則內的例外狀況。 例如您可以篩選來自某個網域以外之所有網域的郵件。 按一下 [新增例外狀況]，再像建立其他種條件一樣建立例外狀況條件。

        將輸出垃圾郵件原則套用至群組支援僅適用於郵件啟用安全性群組。

7. 按一下 **[儲存]**。

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>若要建立一組特定使用者的自訂原則
1. 在 SCC 中，瀏覽至**威脅管理，** \> **原則** \> **反垃圾郵件**

2. 按一下 [**建立輸出原則**] 按鈕。

3. 展開 [**通知**] 區段中選取下列核取方塊相關外寄郵件，然後選取 [**新增人員**至在隨附的對話方塊中新增相關聯的電子郵件地址或地址。

4. 展開 [**收件者限制**] 區段中指定的使用者可以傳送至每小時內部和外部收件者和每日的數目上限的收件者數目上限。

7. 指定當使用者超過指定的限制時要採取的**動作**。

6. 展開 [**適用於**] 區段中，並建立條件式規則，以指定使用者、 群組及要套用此原則的網域。 如果它們都是唯一，則可以建立多個條件。  

8. 按一下 [**儲存**]

## <a name="for-more-information"></a>如需詳細資訊

[傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[輸出郵件的高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)

[反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)
