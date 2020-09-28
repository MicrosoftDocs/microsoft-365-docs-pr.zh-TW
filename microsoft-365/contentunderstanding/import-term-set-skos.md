---
title: 使用以 SKOS 為基礎的格式匯入字詞集
description: 瞭解如何使用以 SKOS 為基礎的格式匯入字詞集
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295794"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="79de3-103">使用以 SKOS 為基礎的格式匯入字詞集</span><span class="sxs-lookup"><span data-stu-id="79de3-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="79de3-104">您可以使用以 SKOS 為基礎的格式匯入字詞集合。</span><span class="sxs-lookup"><span data-stu-id="79de3-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="79de3-105">如需格式的詳細資訊，請參閱 [SharePoint 分類法 SKOS format reference](skos-format-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="79de3-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="79de3-106">建議您將匯入檔案保持在20000個以下的字詞。</span><span class="sxs-lookup"><span data-stu-id="79de3-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="79de3-107">較大的檔案可增加驗證和匯入所需的時間。</span><span class="sxs-lookup"><span data-stu-id="79de3-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="79de3-108">在 SharePoint 系統管理中心，展開 [ **內容服務**]，然後按一下 [ **字詞存放區**]。</span><span class="sxs-lookup"><span data-stu-id="79de3-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="79de3-109">選取您要匯入字詞集的字詞群組。</span><span class="sxs-lookup"><span data-stu-id="79de3-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="79de3-110">在命令列中，按一下 [匯 **入字詞集**]。</span><span class="sxs-lookup"><span data-stu-id="79de3-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="79de3-111">如果您想要下載用作範本的範例檔案，請按一下 **sample-metadata** 以取得使用以 SKOS 為基礎之格式的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="79de3-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="79de3-112">建立包含字詞集的匯入檔案 & 您想要匯入的字詞。</span><span class="sxs-lookup"><span data-stu-id="79de3-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="79de3-113">在 [ **檔案格式**] 底下，選取 [ \*\*SKOS ( \*) \*\*。</span><span class="sxs-lookup"><span data-stu-id="79de3-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="79de3-114">按一下 **[流覽]** ，然後流覽並新增您的匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="79de3-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="79de3-115">按一下 [匯入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="79de3-115">Click **Import**.</span></span> <span data-ttu-id="79de3-116">在匯入完成之前，請勿關閉面板。</span><span class="sxs-lookup"><span data-stu-id="79de3-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="79de3-117">順利匯入檔案時，會顯示成功訊息，而且會重新整理字詞存放區，您可以流覽至新建立的字詞集。</span><span class="sxs-lookup"><span data-stu-id="79de3-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="79de3-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="79de3-118">See also</span></span>

[<span data-ttu-id="79de3-119">受管理的中繼資料簡介</span><span class="sxs-lookup"><span data-stu-id="79de3-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="79de3-120">檔理解概述</span><span class="sxs-lookup"><span data-stu-id="79de3-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="79de3-121"> (網站層級) 匯入字詞集 </span><span class="sxs-lookup"><span data-stu-id="79de3-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)