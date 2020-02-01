---
title: 設定連線篩選原則、允許清單、封鎖清單
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: 若要確定您信任的人所傳送的電子郵件並未遭到封鎖，可以使用連線篩選原則，對於您信任的 IP 位址建立允許清單 (也稱為安全寄件者清單)。 您也可以建立封鎖寄件者清單。
ms.openlocfilehash: 06915527af68df6a858ca8ed97612ab40178be84
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599590"
---
# <a name="configure-the-connection-filter-policy"></a>設定連線篩選原則

大多數的人都有信任的朋友和企業夥伴。 發現這些人寄送的電子郵件出現在垃圾郵件資料夾或甚至遭到垃圾郵件篩選器整個封鎖，會令人感覺不便。 如果您想要確定您信任的人所傳送的電子郵件並未遭到封鎖，可以使用連線篩選原則，對於您信任的 IP 位址建立允許清單 (也稱為安全寄件者清單)。 您也可以建立不想收到電子郵件的封鎖寄件者清單，其中列出一般來自已知濫發垃圾郵件者的 IP 位址。

- 當考慮[允許清單](create-safe-sender-lists-in-office-365.md)** 時，請牢記連線篩選原則本身與篩選「允許的信任帳戶」** 有關。 這項功能可讓您更準確地篩選較不信任或不信任的郵件程式，並同時保留您所需的資訊。 連線篩選原則允許清單是關於從更大的帳戶和 IP 集區，篩選到少數信任的 IP，並確保您信任的郵件程式能更輕鬆地存取。

- 可將建立封鎖清單的連線篩選原則視為在篩選器中捕捉較少或不信任的帳戶。

 如需適用於整個組織的垃圾郵件設定，請參閱[如何在 Office 365 中防止好的電子郵件被標示為垃圾郵件](prevent-email-from-being-marked-as-spam.md)或[如何減少 Office 365 中的垃圾郵件](reduce-spam-email.md)。 如果您有系統管理員層級的控制權，且您想要避免誤判或漏報，這些內容很有幫助。

> [!TIP]
> 您可能想要暫停並了解如何建立[允許 (或安全寄件者) 清單](create-safe-sender-lists-in-office-365.md)和[封鎖清單](create-block-sender-lists-in-office-365.md)。

下列影片顯示連線篩選原則的組態步驟：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 預估完成時間：15 分鐘

- 您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱 [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) (部分機器翻譯) 主題中的「反垃圾郵件」項目。

- 若要取得寄件者的 IP 位址以允許或封鎖其郵件，您可以檢查郵件的 Internet 標頭。 如＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞所述尋找 CIP 標頭。 如需如何在各種電子郵件用戶端中檢視郵件標頭的詳細資訊，請參閱[在 Outlook 中查看網際網路郵件標題](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)。

- 從 IP 封鎖清單上的 IP 位址傳送的電子郵件訊息會遭到拒絕，不會標示為垃圾郵件，也不會發生額外的篩選。

- 下列連線篩選程序也可以透過遠端 PowerShell 執行。 使用 [Get-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedconnectionfilterpolicy) Cmdlet 來檢閱您的設定，以及使用 [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy) 來編輯您的連線篩選原則設定。 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (部分機器翻譯)。 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>使用 EAC 編輯預設連線篩選原則

您可以在 Exchange 系統管理中心 (EAC) 編輯連線篩選原則，以建立 IP 允許清單或 IP 封鎖清單。連線篩選原則設定僅適用於輸入郵件。

1. 在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[連線篩選器]**，然後連按兩下預設原則。

2. Click the **Connection filtering** menu item and then create the lists you want: an IP Allow list, an IP Block list, or both.

   若要建立這些清單，請按一下![加入圖示](../media/ITPro-EAC-AddIcon.gif)。在後續對話方塊中，指定 IP 位址或位址範圍，然後按一下 **[確定]**。重複此程序來新增其他位址。(新增 IP 位址後，您也可以編輯或移除 IP 位址。)

   以 nnn.nnn.nnn.nnn 格式 (其中 nnn 是從 0 到 255 的數字) 來指定 IPV4 IP 位址。 您也可以用 nnn.nnn.nnn.nnn/rr 格式來指定無類別網域間路由選擇 (CIDR) 範圍，其中 rr 是 24 到 32 的數字。 若要指定 24 到 32 以外的範圍，請參閱下一節：[設定 IP 允許清單時的其他考量](#additional-considerations-when-configuring-ip-allow-lists)。

   > [!NOTE]
   > 如果將 IP 位址新增到兩個清單中，則允許從該 IP 位址傳送的電子郵件。<br/><br/> 您最多可以指定 1273 個項目，一個項目就是單一 IP 位址，或 IP 位址從 /24 至 /32 的 CIDR 範圍。 <br/><br/> 如果您正在傳送 TLS 加密訊息，則 IPv6 位址與位址範圍不受支援。

3. 或者，選取 **[啟用安全清單]** 核取方塊避免某些已知寄件者的電子郵件遺失。 怎麼做？ Microsoft 會訂閱協力廠商來源的信任寄件者。 使用這份安全清單表示不會將信任的寄件者錯誤標記為垃圾郵件。 我們建議您選取這個選項，因為它應該會減少您收到的誤判 (好的郵件被分類為垃圾郵件)。

4. 按一下 **[儲存]**。預設原則設定的摘要隨即出現在右側窗格中。

## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>設定 IP 允許清單時的其他考量

以下是設定 IP 允許清單時需要考慮或應該注意的其他事項。

### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>指定超出建議範圍的 CIDR 範圍

若要指定 /1 到 /23 的 CIDR IP 位址範圍，您必須建立在該 IP 位置範圍上運作的傳輸規則，並使該規則將垃圾郵件信賴等級 (SCL) 設為 [略過垃圾郵件篩選]**** (表示將接收自此 IP 位址範圍的所有郵件都設為「不是垃圾郵件」，且服務不會執行其他篩選)。 However, if any of these IP addresses appear on any of Microsoft's proprietary block lists or on any of our third-party block lists, these messages will still be blocked. 因此，強烈建議您使用 /24 到 /32 IP 位址範圍。

若要建立此郵件流程規則，請執行下列步驟。

1. 在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。

2. 按一下 ![加入圖示](../media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。

3. 命名規則，然後按一下 **[更多選項]**。

4. 在 **[套用此規則情況]** 下，選取 **[寄件者]**，然後選擇 **[IP 位址在任何這些範圍中或完全符合]**。

5. 在 [指定 IP 位址]**** 方塊中，指定 IP 位址範圍，按一下 [新增]**** ![新增圖示](../media/ITPro-EAC-AddIcon.gif)，然後按一下 [確定]****。

6. 在 **[執行下列動作]** 方塊下，選擇 **[修改訊息屬性]**，再選擇 **[設定垃圾郵件信賴等級 (SCL)]** 來設定動作。在 **[指定 SCL]** 方塊中，選取 **[略過垃圾郵件篩選]**，然後按一下 **[確定]**。

7. 您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。 施行規則之前，建議先測試規則一段時間。 [Exchange Server 中的郵件流程規則](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) (部分機器翻譯) 包含這些選項的詳細資訊。

8. 按一下 [儲存]**** 儲存規則。 規則會顯示在您的規則清單中。

當您建立並強制執行規則之後，服務會針對您指定的 IP 位址範圍略過垃圾郵件篩選。

### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>針對特定網域設定 IP 允許清單例外狀況

一般而言，建議將您認為安全的所有網域的 IP 位址 (或 IP 位址範圍) 新增至 IP 允許清單。 不過，如果不要將 IP 允許清單項目套用至所有網域，您可以建立排除特定網域的郵件流程規則 (也稱為傳輸規則)。

例如，假設您有三個網域：ContosoA.com、ContosoB.com 和 ContosoC.com，而您想要新增 IP 位址 (為了簡單起見，我們用 1.2.3.4)，並僅針對網域 ContosoB.com 來略過篩選。 您可以建立 1.2.3.4 的 IP 允許清單，以針對所有網域將垃圾郵件信賴等級 (SCL) 設定為 -1 (表示歸類為非垃圾郵件)。 接著，您可以建立一個郵件流程規則，以針對 ContosoB.com 以外的所有網域將 SCL 設定為 0。 這會導致針對與此 IP 位址相關聯的所有網域 (在規則中列為例外的 ContosoB.com 除外) 來重新掃描郵件。 ContosoB.com 的 SCL 仍為 -1 (表示略過篩選)，然而 ContosoA.com 和 ContosoC.com 的 SCL 為 0 (表示將由內容篩選器進行重複掃描)。

若要執行此動作，請執行下列步驟：

1. 在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。

2. 按一下 ![加入圖示](../media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。

3. 命名規則，然後按一下 **[更多選項]**。

4. 在 **[套用此規則情況]** 下，選取 **[寄件者]**，然後選擇 **[IP 位址在任何這些範圍中或完全符合]**。

5. 在 [指定 IP 位址]**** 方塊中，指定您在 IP 允許清單中輸入的 IP 位址或 IP 位址範圍，按一下 [新增]**** ![新增圖示](../media/ITPro-EAC-AddIcon.gif)，然後按一下 [確定]****。

6. 在 [執行下列動作]**** 下，選擇 [修改訊息屬性]****，再選擇 [設定垃圾郵件信賴等級 (SCL)]**** 來設定動作。 在 [指定 SCL]**** 方塊中，選取 [0]****，然後按一下 [確定]****。

7. 按一下 [新增例外狀況]****，在 [除非]**** 下，選取 [寄件者]****，然後選擇 [網域是]****。

8. 在 [指定網域]**** 方塊中，輸入您要略過垃圾郵件篩選的網域，例如 **contosob.com**。 按一下 [新增]**** ![新增圖示](../media/ITPro-EAC-AddIcon.gif)，將它移至片語清單。 如果要新增其他網域當作例外狀況，請重複此步驟，完成時按一下 **[確定]**。

9. 您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。 施行規則之前，建議先測試規則一段時間。 [Exchange Server 中的郵件流程規則](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) (部分機器翻譯) 包含這些選項的詳細資訊。

10. 按一下 [儲存]**** 儲存規則。 規則會顯示在您的規則清單中。

建立並強制執行規則後，系統就只會針對您輸入的例外網域，對您指定的 IP 位址或 IP 位址範圍略過垃圾郵件篩選。

### <a name="scenarios-where-allowed-ip-addresses-are-still-filtered"></a>仍然篩選允許 IP 位址的案例

在下列案例中，來自您在連線篩選原則中所設定允許 IP 位址的郵件，仍然受限於垃圾郵件篩選：

- 連線篩選原則中的來源 IP 位址也是在內部部署、以 IP 為主的輸入連接器、「任何」** 租用戶 (讓我們將其稱為租用戶 A) 中設定，**而且**租用戶 A 和第一次在 Office 365 中遇到郵件的 Exchange Online Protection 伺服器都是在 Microsoft 資料中心的相同 Active Directory 樹系。 在這種情況下，**IPV:CAL** 會新增至郵件的[反垃圾郵件標頭](anti-spam-message-headers.md) (表示郵件略過垃圾郵件篩選)，但是郵件仍受限於垃圾郵件篩選。

- 您的租用戶 (您已設定連線篩選原則) 和 Exchange Online Protection 伺服器 (在 Office 365 中第一次遇到郵件)，出現在 Microsoft 資料中心的不同 Active Directory 樹系中。 在這個案例中，**IPV:CAL** 不會新增至郵件標頭，因此郵件仍受限於垃圾郵件篩選。

如果您遇到下列其中一種情況，您可以在 EAC 中建立郵件流程規則，並 (至少) 使用下列設定，以確保來自 IP 位址的郵件略過垃圾郵件篩選：

- 規則條件：**若為以下情況，套用這個規則** \> **寄件者** \> **IP 位址在任何這些範圍中或完全符合** \> (您的 IP 位址)。

- 規則動作：**修改郵件屬性** \> **設定垃圾郵件信賴等級 (SCL)** \> **略過垃圾郵件篩選**。

基本上是與上一個[針對特定網域設定 IP 允許清單例外狀況](#scoping-an-ip-allow-list-exception-for-a-specific-domain)區段的規則建立程序相同。

## <a name="new-to-office-365"></a>初次使用 Office 365 嗎？

||
|:-----|
|![LinkedIn Learning 的短圖示](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？** 探索 LinkedIn Learning 提供的 **Office 365 admins and IT pros** 免費影片課程。|

## <a name="for-more-information"></a>如需詳細資訊

[Exchange Online 中的安全寄件者和封鎖寄件者清單](safe-sender-and-blocked-sender-lists-faq.md)

[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)

[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)

[如何在 Office 365 中防止好的電子郵件被標示為垃圾郵件](prevent-email-from-being-marked-as-spam.md)

[如何減少 Office 365 中的垃圾郵件](reduce-spam-email.md)
