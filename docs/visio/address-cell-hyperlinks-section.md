---
title: Address 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251387
localization_priority: Normal
ms.assetid: 3864aadd-3f86-c20e-1a74-b0aaff5106f7
description: 指定要跳转到的 URL 地址、文件名或 UNC 路径。
ms.openlocfilehash: 840ce0c4ce73da378f80e5d8a185073ac3915daf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779649"
---
# <a name="address-cell-hyperlinks-section"></a><span data-ttu-id="ad8ae-103">Address 单元格（“Hyperlinks”部分）</span><span class="sxs-lookup"><span data-stu-id="ad8ae-103">Address Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="ad8ae-104">指定要跳转到的 URL 地址、文件名或 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-104">Specifies a URL address, file name, or UNC path to which to jump.</span></span>
  
<span data-ttu-id="ad8ae-105">您可以为相对路径基于**属性**对话框的**摘要**选项卡上的**超链接基础**框中为文档定义的基路径指定地址 (单击**文件**选项卡，单击**信息**，单击 * * 属性 * *，然后单击**高级属性**)。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-105">You can specify Address as a relative path based on the base path defined for the document in the **Hyperlink base** box on the **Summary** tab of the **Properties** dialog box (click the **File** tab, click **Info**, click ** Properties **, and then click **Advanced Properties**).</span></span> <span data-ttu-id="ad8ae-106">如果文档有无基路径，应用程序导航基于文档路径。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-106">If the document has no base path, the application navigates based on the document path.</span></span> <span data-ttu-id="ad8ae-107">如果文档尚未保存，未定义超链接。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-107">If the document has not been saved, the hyperlink is undefined.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ad8ae-108">说明</span><span class="sxs-lookup"><span data-stu-id="ad8ae-108">Remarks</span></span>

<span data-ttu-id="ad8ae-109">您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上单击 **“超链接”**）中设置 Address 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-109">You can also set the value of the Address cell in the **Hyperlinks** dialog box (click **Hyperlink** on the **Insert** tab).</span></span> 
  
<span data-ttu-id="ad8ae-110">若要从某个程序按索引获取对 Address 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ad8ae-110">To get a reference to the Address cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ad8ae-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ad8ae-111">Cell name:</span></span>  <br/> |<span data-ttu-id="ad8ae-112">超链接。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-112">Hyperlink.</span></span> <span data-ttu-id="ad8ae-113">*名称*。地址位置超链接。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-113">*name*  .Address           where Hyperlink.</span></span> <span data-ttu-id="ad8ae-114">*name*是超链接行的名称</span><span class="sxs-lookup"><span data-stu-id="ad8ae-114">*name*  is the name of the hyperlink row</span></span>  <br/> |
   
<span data-ttu-id="ad8ae-115">若要获取对 Address 单元格的引用按名称从另一个公式或从某个程序中，使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="ad8ae-115">To get a reference to the Address cell by name from another formula, or from a program, by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ad8ae-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ad8ae-116">Section index:</span></span>  <br/> |<span data-ttu-id="ad8ae-117">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="ad8ae-117">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="ad8ae-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="ad8ae-118">Row index:</span></span>  <br/> |<span data-ttu-id="ad8ae-119">**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="ad8ae-119">**visRow1stHyperlink** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="ad8ae-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ad8ae-120">Cell index:</span></span>  <br/> |<span data-ttu-id="ad8ae-121">**visHLinkAddress**</span><span class="sxs-lookup"><span data-stu-id="ad8ae-121">**visHLinkAddress**</span></span> <br/> |
   

