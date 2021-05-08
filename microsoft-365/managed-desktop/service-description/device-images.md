---
title: 裝置影像
description: 排序新裝置或重複使用現有裝置時的映射需求
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
ms.openlocfilehash: 00943eb85abbfd2d237ae5544eb69d3ec4d9f875
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245501"
---
# <a name="device-images"></a>裝置影像


不論是定購 [新裝置](#new-devices) 還是重複使用 [現有](#existing-devices) 的裝置，您有數個選項可確保裝置上的影像符合我們的 [裝置需求](device-requirements.md#check-hardware-requirements)。

## <a name="new-devices"></a>新裝置
當您從[認可的製造商](device-requirements.md#minimum-requirements)定購新的裝置時，請遵循下列步驟，以確定他們使用適當的 Microsoft 受管理的電腦影像和軟體設定來運送裝置。

### <a name="dell"></a>戴爾
直接與戴爾銷售代表合作，以確保將 Microsoft 受管理的電腦核准的影像套用至您的訂單裝置。 如需 Dell 裝置、影像及訂購程式的相關問題，請與 MMD_at_dell@dell.com 聯繫。

### <a name="hp"></a>惠普 
當您從 HP 定購新的裝置時，請務必在 [[車間 Windows 10 專業版商務裝置](https://www.microsoft.com/windowsforbusiness/view-all-devices)] 網站中找到的每個模型，針對 [其他需求] 區段所列的特定 SKU， (篩選該視圖，以顯示 Microsoft 受管理的電腦裝置) 。

如果您是從 HP 已核准為 [例外](customizing.md) 狀況，但目前並未列在裝置清單頁面上，請務必要求您的模型使用 SKU。 我們會使用 HP，透過您的例外要求取得此資訊。 您也可以使用下列位址，直接與 HP 聯繫以取得有關裝置和裝置順序指示的任何問題：
 
- 美洲： mmd-americas@hp.com
- 歐洲/中東、中東/非洲： mmd-emea@hp.com
- 亞太地區/日本： mmd-apj@hp.com
- Global： mmd@hp.com

### <a name="lenovo"></a>聯想
當您從聯想裝置排序裝置以用於 Microsoft 受管理的電腦時，您必須指出包含在訂單中的特定部分號碼。 請聯繫您的聯想銷售代表或聯想通道合作夥伴，並要求他們使用符合我們 [裝置需求](device-requirements.md#minimum-requirements)的系統來建立「*特殊出價模型*」。 若要包含與 Microsoft 受管理的電腦搭配使用的預先載入映射，請要求「銷售代表」參考「*system 組建區塊部分編號 SBB0Q94938 – MMD 啟用*」。

下列產品目前已啟用 Microsoft 受管理的電腦支援：

- L13 Gen 1
- L13 Yoga Gen 1
- L14 Gen 1 (Intel) 
- L14 Gen 1 (AMD) 
- L15 Gen 1 (Intel) 
- L15 Gen 1 (AMD) 
- X1 碳 Gen 8
- X1 Yoga Gen 5
- T14 Gen 1 (Intel) 
- T14 Gen 1 (AMD) 
- T15 Gen 1
- X13 Gen 1 (Intel) 


### <a name="microsoft"></a>Microsoft
所有符合裝置需求的 Microsoft 裝置都會隨附與 Microsoft 受管理的電腦搭配使用的影像。 不需要其他步驟。

若要在 Microsoft 裝置的工廠中取得最新的影像，請與您的 Surface 專業人員合作，以使用表面「限定 PO」處理常式。

## <a name="existing-devices"></a>現有裝置

您可以重複使用現有的裝置，只要這些裝置符合  [裝置需求](device-requirements.md#minimum-requirements) 和 [軟體需求](device-requirements.md#installed-software)。 遵循與製造商相關的步驟。

您可以使用製造商的影像或使用 Microsoft 受管理的電腦 "通用影像" 重新鏡像裝置。 若要取得適當的製造商影像，您可以定購至少一個 [新](#new-devices) 的模型，您正在重複使用此裝置。 然後您可以從該裝置取得影像，並將其套用至完全相同模型的其他裝置。

> [!NOTE]
> You're 建立、測試及部署映射的責任。 我們也建議您盡可能使用製造商提供的適當影像，而不使用自訂影像-----------------

### <a name="hp"></a>惠普

使用 HP 公司就緒映射隨附的 HP 商用電腦包括。恢復的 WIM 檔案。 您可以使用這個影像，將出廠還原影像套用至相同模型的其他裝置。

這些步驟將會移除裝置上的所有資料，因此開始之前，您應該先備份您要保留的任何資料。

1. 使用 WinPE[建立可啟動的 USB 磁片磁碟機](https://docs.microsoft.com/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive)。
2. 將這些檔案從 C： \\ 來源複製到 USB 磁片磁碟機：
    - Factory 復原 WIM 檔案 (例如，HP \_ EliteBook \_ 840 \_ G7 \_ 筆記本 \_ PC \_ CR \_) 
    - 部署。Cmd
    - ReCreatePartitions.txt
3. [將裝置引導至 WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB 磁片磁碟機。
4. 在命令提示字元中，執行 [Diskpart.exe](https://docs.microsoft.com/windows-server/administration/windows-commands/diskpart#additional-references)。
5. 在 Diskpart 中執行 `list disk` ，然後記下主要儲存磁片編號 (通常是磁片 0) 。
6. 輸入會結束 Diskpart `exit` 。
7. 在命令提示字元中執行 `deploy.cmd <sys_disk> <recovery_wim>` ，其中 *sys_disk* 是剛才確定的主要儲存磁片的磁片號碼，而 *recovery_wim* 是的檔案名。先前複製的 WIM 檔案。
8. 移除 USB 磁片磁碟機，然後重新開機裝置。

### <a name="microsoft"></a>Microsoft 

Microsoft 表面裝置包含每個模型特有的「裸機復原」 [影像](https://support.microsoft.com/en-us/surfacerecoveryimage) 。 您可以使用這些影像重新鏡像裝置。

這些影像使用 Windows 復原環境 (WinRE) ，而這是手動程式， (不會自動) 。 遵循為 [Surface 建立及使用 USB 復原磁片磁碟機](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)中的步驟進行。


### <a name="universal-image"></a>通用影像
Microsoft 受管理的電腦已建立包含 Windows 10 專業版和 Microsoft 365 Apps 的影像，以供 Enterprise 使用 Microsoft 受管理的電腦。 不過，如果可能的話，最好使用適用于廠商 Microsoft 受管理的電腦的影像，即使這表示舊的 Windows 版本需要在使用者登入之後更新。 使用 Microsoft 受管理的電腦通用影像應該是最後一個選項。

- 我們每月品質更新 Windows 每月品質更新每30-60 天，而 Microsoft 365 Apps Enterprise 更新至少一年兩次。
- 此映射包含復原布建套件，以確保 Windows 復原案例之後還原 Enterprise Microsoft 365 Apps。
- 您可以使用 USB 磁片磁碟機部署映射。 它包含可編寫腳本的程式，用以插入包含在 image) 中的檔 (所述的驅動程式。
- 您可以修改包含的腳本和資料夾，以用於其他自訂，例如新增特定累計更新、檔案複製程式碼，或執行其他檢查。
- 從 USB 磁片磁碟機進行部署時，會將驅動程式和品質更新加入 Windows。

> [!NOTE]
> 您有責任新增所有必要的驅動程式、執行所有測試，並確保最後部署的映射沒有任何問題。 我們提供通用映射，但會提供技術指導方針和解答問題。 請與 MMDImage@microsoft.com 聯繫。

在 [管理入口網站](../get-started/access-admin-portal.md)上建立變更要求，以送出通用影像內容及檔的要求。


