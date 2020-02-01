---
title: 設定 Exchange Online 中的虛擬憑證集合以驗證 S/MIME
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
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 系統管理員可了解如何設定 Exchange Online 中用來驗證 S/MIME 憑證的虛擬憑證集合。
ms.openlocfilehash: 232f45b63a38ce4591c83e4ec7a9c09a03c339d4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598320"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="e579d-103">設定 Exchange Online 中的虛擬憑證集合以驗證 S/MIME</span><span class="sxs-lookup"><span data-stu-id="e579d-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="e579d-104">如果您是系統管理員，您將必須設定 Exchange Online 中用來驗證 S/MIME 憑證的虛擬憑證集合。</span><span class="sxs-lookup"><span data-stu-id="e579d-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="e579d-105">此虛擬憑證集合會設定為具有 SST 副檔名的憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="e579d-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="e579d-106">此 SST 檔案中包含所有在驗證 S/MIME 憑證時所將使用的根憑證和中繼憑證。</span><span class="sxs-lookup"><span data-stu-id="e579d-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="e579d-107">建立及儲存 SST</span><span class="sxs-lookup"><span data-stu-id="e579d-107">Create and save an SST</span></span>

<span data-ttu-id="e579d-108">您可以使用 Windows PowerShell 中的 **Export-Certificate** 指令程式並將 _[類型]_ 值指定為 SST，從信任的機器匯出憑證，以建立此 SST 憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="e579d-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="e579d-109">如需相關指示，請參閱 [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate) (英文版)。</span><span class="sxs-lookup"><span data-stu-id="e579d-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="e579d-110">一旦您擁有 SST 憑證存放區檔案之後，請在 Exchange Online PowerShell 中使用以下語法，將 SST 檔案內容儲存在 Exchange Online 虛擬憑證存放區中。</span><span class="sxs-lookup"><span data-stu-id="e579d-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="e579d-111">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e579d-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="e579d-112">此範例匯入 SST 檔案 C:\My Documents\Exported Certificate Store.sst。</span><span class="sxs-lookup"><span data-stu-id="e579d-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="e579d-113">如需詳細的語法及參數資訊，請參閱 [Set-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)。</span><span class="sxs-lookup"><span data-stu-id="e579d-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="e579d-114">確保憑證的有效性</span><span class="sxs-lookup"><span data-stu-id="e579d-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="e579d-115">在 Exchange Online 中，憑證驗證時將只會使用 SST。</span><span class="sxs-lookup"><span data-stu-id="e579d-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="e579d-116">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e579d-116">More Information</span></span>

[<span data-ttu-id="e579d-117">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="e579d-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="e579d-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="e579d-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig)
