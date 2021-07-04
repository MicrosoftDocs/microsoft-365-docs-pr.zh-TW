---
title: 使用 SKOS 格式匯入字詞組
description: 瞭解如何使用 SKOS 格式匯入字詞組
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288512"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="d0c6f-103">使用 SKOS 格式匯入字詞組</span><span class="sxs-lookup"><span data-stu-id="d0c6f-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="d0c6f-104">您可以使用 SKOS 格式匯入字詞組。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="d0c6f-105">如需有關格式的詳細資訊，請參閱[「SharePoint 分類法的SKOS 格式參考」](skos-format-reference.md) (英文) 。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span> <span data-ttu-id="d0c6f-106">此功能需要 [SharePoint Syntex](index.md) 授權。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="d0c6f-107">我們建議您將匯入檔案維持在少於 20,000 個字詞。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-107">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="d0c6f-108">較大的檔案可能會增加驗證和匯入所需的時間。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-108">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="d0c6f-109">在 SharePoint 系統管理中心展開 **[內容服務]**，然後按一下 **[字詞庫]**。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-109">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="d0c6f-110">選取您要匯入字詞組的字詞群組。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-110">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="d0c6f-111">在命令列中，按一下 **[ 匯入字詞組]**。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-111">In the command bar, click **Import term set**.</span></span>

4. <span data-ttu-id="d0c6f-112">如果您想要下載用作範本的範例檔案，請按一下 **[sample-metadata. ttl]** ，取得使用 SKOS 格式的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-112">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>

5. <span data-ttu-id="d0c6f-113">建立重要檔案以涵蓋您要匯入的字詞組和字詞。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-113">Create the import file that contains the term sets & terms you wish to import.</span></span>

6. <span data-ttu-id="d0c6f-114">在 **[檔案格式]** 底下，選取 **[SKOS (\*.ttl)]**。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-114">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7. <span data-ttu-id="d0c6f-115">按一下 **[瀏覽]** 並瀏覽至新增匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-115">Click **Browse** and navigate to and add your import file.</span></span>

8. <span data-ttu-id="d0c6f-116">按一下 **[匯入]**。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-116">Click **Import**.</span></span> <span data-ttu-id="d0c6f-117">直到匯入完成之後，才能關閉面板。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-117">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="d0c6f-118">成功匯入檔案時，系統會顯示一則成功訊息，而字詞儲存區將會重新整理，您可以瀏覽至新建立的字詞組。</span><span class="sxs-lookup"><span data-stu-id="d0c6f-118">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0c6f-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="d0c6f-119">See also</span></span>

[<span data-ttu-id="d0c6f-120">受管理的中繼資料簡介</span><span class="sxs-lookup"><span data-stu-id="d0c6f-120">Introduction to managed metadata</span></span>](/sharepoint/managed-metadata)

[<span data-ttu-id="d0c6f-121">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="d0c6f-121">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="d0c6f-122">匯入字詞組 (網站層級)</span><span class="sxs-lookup"><span data-stu-id="d0c6f-122">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
