---
title: 設定預設連線篩選原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何在 Office 365 中設定連線篩選，以允許或封鎖電子郵件伺服器中的電子郵件。
ms.openlocfilehash: 0848e9a59df8c312891add29d14eec2dfed420df
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035079"
---
# <a name="configure-connection-filtering"></a>設定連線篩選

如果您是使用 Exchange Online 中的信箱或獨立 Exchange Online Protection （EOP）客戶但沒有 Exchange Online 信箱的 Microsoft 365 客戶，您可以在 EOP （特別是預設連線篩選原則）中使用連線篩選，以根據其 IP 位址來識別正確或不良的來源電子郵件伺服器。 預設連線篩選原則的主要元件包括：

- **IP 允許清單**：針對來自您透過 ip 位址或 ip 位址範圍所指定之來源電子郵件伺服器的所有傳入郵件，略過垃圾郵件篩選。 針對來自這些來源之郵件的垃圾郵件篩選可能仍會發生的情況，請參閱本主題稍後的[篩選來自 IP 允許清單來源的郵件](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered)。 如需 IP 允許清單應如何符合整體安全寄件者策略的詳細資訊，請參閱[在 Office 365 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。

- **IP 封鎖清單**：從您透過 ip 位址或 ip 位址範圍所指定之來源電子郵件伺服器封鎖所有傳入的郵件。 內送郵件會遭到拒絕，不會標示為垃圾郵件，也不會發生其他篩選。如需 IP 封鎖清單應如何符合整體封鎖的寄件者策略的詳細資訊，請參閱[在 Office 365 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。

- **安全清單**：*安全清單*是 Microsoft datacenter 中的動態允許清單，不需要客戶設定。 Microsoft 會識別這些信任的電子郵件來源，以訂閱各種協力廠商清單。 啟用或停用 [安全清單] 的使用。您無法在 [安全清單] 上設定來源電子郵件伺服器。 在 [安全清單] 上的電子郵件伺服器上，會略過傳入郵件的垃圾郵件篩選。

本主題說明如何在安全性 & 規範中心或 PowerShell （Microsoft 365 客戶的 Exchange Online PowerShell 中）設定預設連線篩選原則。Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。 如需 EOP 如何使用連線篩選的詳細資訊，請參閱您組織的整體反垃圾郵件設定的一部分，請參閱[反垃圾郵件保護](anti-spam-protection.md)。

> [!NOTE]
> IP 允許清單、安全清單和 IP 封鎖清單是整體策略的一部分，可允許或封鎖您組織中的電子郵件。 如需詳細資訊，請參閱[建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)及[建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [反垃圾郵件設定]**** 頁面，請使用 <https://protection.office.com/antispam>。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 若要修改預設連線篩選原則，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。 若要對預設連線篩選原則進行唯讀存取，您必須是**Security Reader**角色群組的成員。 如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。

- 若要尋找您要允許或封鎖之電子郵件伺服器（寄件者）的來源 IP 位址，您可以檢查郵件頭中的 [連接 IP （**CIP**）標頭] 欄位。 若要在不同的電子郵件客戶程式中查看郵件頭，請參閱在[Outlook 中查看網際網路郵件頭](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)。

- IP 允許清單優先于 IP 封鎖清單（這兩個清單上的位址未遭到封鎖）。

- IP 允許清單和 IP 封鎖清單都支援最多1273個專案，其中一個專案是單一 IP 位址、IP 位址範圍或無類別網域間路由選擇（CIDR） IP。

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>使用安全性 & 規範中心來修改預設連線篩選原則

1. 在安全性 & 合規性中心，然後移至**威脅管理** \> **原則** \> **Anti-Spam**。

2. 在 [**反垃圾郵件設定**] 頁面上， ![按一下 [展開圖示](../../media/scc-expand-icon.png)]，然後按一下 [**編輯原則**]，展開 [連線**篩選原則**]。

3. 在出現的**預設**浮出視窗中，設定下列任一設定：

   - **描述**：輸入選用的描述文字。

   - **IP 允許清單**：按一下 [**編輯**]。 在出現的 [ **IP 允許] 清單**快顯視窗中，使用下列語法，在 [**位址] 或 [位址範圍**] 方塊中輸入 IPV4 位址：

     - 單一 IP：例如，192.168.1.1。

     - IP 範圍：例如，192.168.0.1-192.168.0.254。

     - CIDR IP：例如 192.168.0.1/25。 有效的網路遮罩值為/24 到/32。 若要略過 CIDR IP 遮罩值的垃圾郵件篩選，/1 到/23，請參閱本主題稍後的 [[略過垃圾郵件篩選] （適用于可用範圍區段之外的 CIDR ip](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) ）。

     若要新增 IP 位址或位址範圍，請**Add** ![按一下 [新增](../../media/ITPro-EAC-AddIcon.png)加入圖示]。 若要移除專案，請選取 [**允許的 IP 位址**] 中的專案，](../../media/scc-remove-icon.png)然後按一下 [**移除** ![]。 完成後，按一下 [儲存]****。

   - **IP 封鎖清單**：按一下 [**編輯**]。 在出現的 [ **Ip 封鎖**] 快顯視窗中，在 [ **ip 允許清單**] 設定中先前所述的 [**位址] 或 [位址範圍**] 方塊中輸入單一 IP、ip 範圍或 CIDR IP。

     若要新增 IP 位址或位址範圍，請**Add** ![按一下 [新增](../../media/ITPro-EAC-AddIcon.png)加入圖示]。 若要移除專案，請選取 [**封鎖的 IP 位址**] 中的專案，](../../media/scc-remove-icon.png)然後按一下 [**移除** ![]。 完成後，按一下 [儲存]****。

   - **開啟安全清單**：啟用或停用安全清單的使用，以找出將會略過垃圾郵件篩選的已知的良好寄件者。

4. 完成後，按一下 [儲存]****。

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>使用安全性 & 規範中心來查看預設連線篩選原則

1. 在安全性 & 合規性中心，然後移至**威脅管理** \> **原則** \> **Anti-Spam**。

2. 在 [**反垃圾郵件設定**] 頁面上，按一下名為**Connection filter policy**之預設原則旁的下拉式清單。

3. 原則設定會顯示在開啟的下拉式功能表中。

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-modify-the-default-connection-filter-policy"></a>使用 Exchange Online PowerShell 或獨立 Exchange Online Protection PowerShell 修改預設連線篩選原則

請使用下列語法：

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**附註**：

- 有效的 IP 位址或位址範圍值包括：

  - 單一 IP：例如，192.168.1.1。

  - IP 範圍：例如，192.168.0.1-192.168.0.254。

  - CIDR IP：例如 192.168.0.1/25。 有效的網路遮罩值為/24 到/32。

- 若要使用您指定的值*覆寫*任何現有的專案，請使用`IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`下列語法：。

- 若要*新增或移除*IP 位址或位址範圍，而不影響其他現有的專案，請`@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`使用下列語法：。

- 若要清空 IP 允許清單或 IP 封鎖清單，請使用值`$null`。

這個範例會設定 IP 允許清單和 IP 封鎖清單，其中包含指定的 IP 位址和位址範圍。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

本範例會從 IP 允許清單中新增及移除指定的 IP 位址和位址範圍。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

如需詳細的語法及參數資訊，請參閱[Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy)。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您是否已成功修改預設連線篩選原則，請執行下列任一步驟：

- 在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> **原則** \> ] **Anti-Spam** \>按一下 [連線**篩選原則（永不開啟**）] 旁的下拉式清單，然後驗證設定。

- 在 Exchange Online PowerShell 或獨立 Exchange Online Protection PowerShell 中，執行下列命令並確認設定：

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- 從 IP 允許清單中的專案傳送測試郵件。

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 允許清單的其他考慮

下列各節會指出當您設定 IP 允許清單時，需要瞭解的其他專案。

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>略過可用範圍外的 CIDR IP 的垃圾郵件篩選

如本主題稍早所述，您只能在 IP 允許清單中使用具有 network mask/24 to/32 的 CIDR IP。 若要在/1 到/23 範圍內略過來自來源電子郵件伺服器的郵件篩選，您必須使用 Exchange 郵件流程規則（也稱為傳輸規則）。 不過，如果可能的話，建議您不要這麼做，因為在任何 Microsoft 的專屬或協力廠商封鎖清單中，如果有/1 to/23 CIDR IP 範圍的 IP 位址會出現，則郵件會遭到封鎖。

現在，您完全知道潛在的問題，您可以使用下列設定建立郵件流程規則（至少），以確保來自這些 IP 位址的郵件會略過垃圾郵件篩選：

- 規則條件：**如果** \> **寄件者** \>的**IP 位址在任何這些範圍中，或完全符合** \> ，請套用此規則。請輸入含 a/1 to/23 網路遮罩的 CIDR IP。

- 規則動作：**修改郵件屬性** \> **設定垃圾郵件信賴等級 (SCL)** \> **略過垃圾郵件篩選**。

您可以審核規則、測試規則、在特定時間期間啟動規則，以及進行其他選擇。 施行規則之前，建議先測試規則一段時間。 如需詳細資訊，請參閱[在 Exchange Online 中管理郵件流程規則](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>略過來自相同來源之選擇性電子郵件網域的垃圾郵件篩選

一般來說，將 IP 位址或位址範圍新增至 IP 允許清單表示您信任來自該電子郵件來源的所有傳入郵件。 不過，如果該來源從多個網域傳送電子郵件，而您想要略過某些網域的垃圾郵件篩選功能，則該怎麼辦？ 您無法只使用 IP 允許清單來執行這項作業，但是您可以搭配郵件流程規則使用 [IP 允許] 清單。

例如，來源電子郵件伺服器192.168.1.25 會從網域 contoso.com、fabrikam.com 和 tailspintoys.com 傳送電子郵件，但您只想要對來自 fabrikam.com 中寄件者的郵件略過垃圾郵件篩選。 若要這麼做，請使用下列步驟：

1. 將192.168.1.25 新增至 IP 允許清單。

2. 設定具有下列設定的郵件流程規則（至少）：

   - 規則條件：**如果** \> **寄件者** \>的**IP 位址在任何這些範圍中，或完全符合** \> 192.168.1.25 （您在上一個步驟中新增至 ip 允許清單的相同 IP 位址或位址範圍），請套用此規則。

   - 規則動作：**修改郵件屬性** \> **設定垃圾郵件信賴等級（SCL）** \> **0**。

   - 規則例外：**寄件者** \> **網域為** \> fabrikam.com （只是您想要略過垃圾郵件篩選的網域）。

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>仍然篩選來自 IP 允許清單來源之郵件的案例

來自 IP 允許清單中的電子郵件伺服器的郵件，在下列情況下仍會受到垃圾郵件篩選：

- 您的 IP 允許清單中的 IP 位址也會設定在 Microsoft 365 （我們呼叫此租使用者 A）的*任何*租使用者中的內部部署、以 IP 為基礎的輸入連接器中，**並且**第一次遇到郵件的承租人 a 和 EOP Server 都會發生在 Microsoft 資料中心*的相同*Active Directory 樹系中。 在此案例中， **IPV： CAL** *會*新增至郵件的[反垃圾郵件郵件頭](anti-spam-message-headers.md)（指出郵件略過垃圾郵件篩選），但郵件仍受垃圾郵件篩選。

- 您的租使用者包含 IP 允許清單和 EOP server，第一次遇到郵件時，就會發生在 Microsoft 資料中心的*不同*Active Directory 樹系中。 在此案例中， **IPV： CAL** *不*會新增至郵件頭，所以郵件仍會受到垃圾郵件篩選。

如果您遇到這兩種情況，您可以使用下列設定建立郵件流程規則（至少），以確保來自有問題之 IP 位址的郵件會略過垃圾郵件篩選：

- 規則條件：**若為以下情況，套用這個規則** \> **寄件者** \> **IP 位址在任何這些範圍中或完全符合** \> (您的 IP 位址)。

- 規則動作：**修改郵件屬性** \> **設定垃圾郵件信賴等級 (SCL)** \> **略過垃圾郵件篩選**。

## <a name="new-to-office-365"></a>初次使用 Office 365 嗎？

||
|:-----|
|![LinkedIn 學習](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **新增至 Microsoft 365**的簡短圖示？ 探索免費的影片課程，以供**系統管理員和 IT 專業人員**使用，LinkedIn 的知識。|
