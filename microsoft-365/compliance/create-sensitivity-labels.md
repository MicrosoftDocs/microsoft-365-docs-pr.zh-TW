---
title: 建立及發佈敏感度標籤
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 建立、設定及發佈敏感度標籤的指示，以便分類及保護貴組織的文件和電子郵件。
ms.openlocfilehash: 964fd20d6ada935d2a76ca0bffccc5bf46161c58
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247456"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>建立及設定敏感度標籤及其原則

若要建立及發佈 [[敏感度標籤]](sensitivity-labels.md)，請前往標籤系統管理中心，例如 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)。 您也可以使用 Microsoft 365 安全性中心，或 Office 365 安全性與合規性中心。

首先，建立並設定您要在 Office 應用程式和服務中提供使用的敏感度標籤。 然後，建立一或多個包含您所設定的標籤和原則設定的標籤原則。 這是為您所選的使用者和位置發佈標籤和設定的標籤原則。

## <a name="create-and-configure-sensitivity-labels"></a>建立及設定敏感度標籤

1. 在標籤系統管理中心中，導覽至敏感度標籤：
    
    - Microsoft 365 合規性中心： 
        - **** 解決方案 > **資訊保護 (預覽)**
        
        如果您沒有立即看到這個選項，請先選取 [全部顯示]****。 
    
    - Microsoft 365 安全性中心： 
        - **分類** > **敏感度標籤**
    
    - Office 365 安全性與合規性中心：
        - **分類** > **敏感度標籤**

2. 選取 [標籤]**** 索引標籤上的 [+ 建立標籤]****，以啟動 [新增敏感度標籤]**** 精靈。

3. 按照標籤設定的提示進行。
    
    如需有關標籤設定的詳細資訊，請參閱概觀資訊中的[敏感度標籤的功能](sensitivity-labels.md#what-sensitivity-labels-can-do)。

4. 重複這些步驟以建立更多標籤。 不過，如果您想要建立子標籤，請先選取父標籤，並選取 **[...]** 以取得 **[其他動作]**，然後選取 **[新增子標籤]**。

5. 建立好所有需要的標籤後，請檢查其順序，並視需要將它們上下移動。 若要變更標籤的順序，請選取 **...** 以取得 [其他動作]****，然後選取 [上移]**** 或 [下移]****。 如需詳細資訊，請參閱概覽資訊中的[標籤優先順序 (順序很重要)](sensitivity-labels.md#label-priority-order-matters) (英文)。

若要編輯現有的標籤，請將其選取，然後選取 [編輯標籤]****。 這會啟動 [編輯敏感度標籤]**** 精靈，它可讓您變更步驟 3 中的所有標籤設定。 

> [!NOTE]
> 如果您編輯已使用標籤原則發佈的標籤，當完成精靈後便不需要額外的步驟。 例如，您不需要將它新增到新的標籤原則。 不過，請允許最多 24 小時的時間讓變更複寫到使用者和服務。

在您發佈標籤之前，無法在應用程式中或為服務選取標籤。 若要發佈標籤，必須先將標籤新增至標籤原則。

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 安全性與合規性中心 PowerShell 的其他標籤設定

您可以從 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 使用 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤設定。

例如，使用 *LocaleSettings* 參數為您的標籤名稱和工具提示指定不同的語言。 

使用此 Cmdlet，您同時可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。 這些進階設定包括設定標籤色彩，以及在套用標籤時套用自訂屬性。 如需完整清單，請參閱[標籤原則可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)。 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>建立標籤原則來發佈敏感度標籤

1. 在標籤系統管理中心中，導覽至敏感度標籤：
    
    - Microsoft 365 合規性中心： 
        - **** 解決方案 > **資訊保護 (預覽)**
        
        如果您沒有立即看到這個選項，請先選取 [全部顯示]****。 
    
    - Microsoft 365 安全性中心： 
        - **分類** > **敏感度標籤**
    
    - Office 365 安全性與合規性中心：
        - **分類** > **敏感度標籤**

2. 選取 **[標籤原則]** 索引標籤。

3. 選取 **[發佈標籤]** 以啟動 **[建立原則精靈]**。

4. 選取 **[選擇要發佈的敏感度標籤]**。 選取您要在應用程式和服務中提供使用的標籤，然後選取 **[新增]**。

5. 檢閱選取的標籤，若要進行任何變更，請選取 **[編輯]**。 否則請選取 **[下一步]**。

6. 遵循提示來設定原則設定。
    
    如需有關設定的詳細資訊，請參閱概觀資訊中的[標籤原則的功能](sensitivity-labels.md#what-label-policies-can-do) (英文)。

7. 如果不同的使用者或位置需要不同的原則設定，請重複這些步驟。 例如，您需要一組使用者有其他標籤，或使用者的子集有不同的預設標籤。

8. 如果您建立可能會導致使用者或位置發生衝突的多個標籤原則，請檢閱原則順序，並視需要將它們上下移動。 若要變更標籤原則的順序，請選取 **...** 以取得 **[其他動作]**，然後選取 **[上移]** 或 **[下移]**。 如需詳細資訊，請參閱概觀資訊中的 [標籤原則優先順序 (順序很重要)](sensitivity-labels.md#label-policy-priority-order-matters) (英文)。

完成精靈即會自動發佈標籤原則。 若要對已發佈的原則進行變更，只要編輯即可。 沒有特定的發佈或重新發佈動作可供您選取。

若要編輯現有的標籤原則，請將其選取，然後選取 **[編輯原則]**。 這會啟動 **[建立原則]** 精靈，讓您編輯要包含的標籤和標籤設定。 完成精靈時，任何變更都會自動複寫到選取的使用者和服務。

通常，使用者會在幾小時內在其 Office App 中看到標籤。 不過，請允許最多 24 小時的時間讓您的標籤原則及任何其他所做變更複寫到所有使用者和服務。

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 安全性與何規性中心 PowerShell 的其他標籤原則設定

您可以使用來自 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 的 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤原則設定。

使用此 Cmdlet，您可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。 這些進階設定包括為 Outlook 設定不同的預設標籤，以及在 Outlook 中實作可警告、證明或封鎖要傳送的電子郵件的快顯訊息。 如需完整清單，請參閱[標籤可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)。 

您也可以使用此 Cmdlet 往返標籤原則來新增和移除標籤。


## <a name="next-steps"></a>後續步驟

若要針對特定案例設定和使用敏感度標籤，請使用下列文章：

- [使用敏感度標籤中的加密來限制內容的存取](encryption-sensitivity-labels.md)

- [自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)

- [對團隊、群組和網站使用敏感度標籤](sensitivity-labels-teams-groups-sites.md)

- [對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)

若要監視標籤的使用方式，請參閱[利用標籤分析檢視標籤使用量](label-analytics.md) (英文)。