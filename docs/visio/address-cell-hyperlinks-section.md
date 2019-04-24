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
ms.openlocfilehash: 0fbb89e18a2d7a849e2369c0d41aac4a647f067b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338547"
---
# <a name="address-cell-hyperlinks-section"></a><span data-ttu-id="5f66e-103">Address 单元格（“Hyperlinks”内容）</span><span class="sxs-lookup"><span data-stu-id="5f66e-103">Address Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="5f66e-104">指定要跳转到的 URL 地址、文件名或 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="5f66e-104">Specifies a URL address, file name, or UNC path to which to jump.</span></span>
  
<span data-ttu-id="5f66e-105">您可以根据在 "**属性**" 对话框 (依次单击 "**文件**" 选项卡、"**信息**"、"属性" 和 "属性") 的 "**摘要**" 选项卡上为文档定义的基准路径, 将地址指定为相对路径。 \*\*\*\*, 然后单击 "**高级属性**")。</span><span class="sxs-lookup"><span data-stu-id="5f66e-105">You can specify Address as a relative path based on the base path defined for the document in the **Hyperlink base** box on the **Summary** tab of the **Properties** dialog box (click the **File** tab, click **Info**, click \*\* Properties \*\*, and then click **Advanced Properties**).</span></span> <span data-ttu-id="5f66e-106">如果文档没有基础路径，则应用程序会基于文档路径导航。</span><span class="sxs-lookup"><span data-stu-id="5f66e-106">If the document has no base path, the application navigates based on the document path.</span></span> <span data-ttu-id="5f66e-107">如果未保存文档，则超链接尚未定义。</span><span class="sxs-lookup"><span data-stu-id="5f66e-107">If the document has not been saved, the hyperlink is undefined.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5f66e-108">注解</span><span class="sxs-lookup"><span data-stu-id="5f66e-108">Remarks</span></span>

<span data-ttu-id="5f66e-109">您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上单击 **“超链接”**）中设置 Address 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="5f66e-109">You can also set the value of the Address cell in the **Hyperlinks** dialog box (click **Hyperlink** on the **Insert** tab).</span></span> 
  
<span data-ttu-id="5f66e-110">若要从某个程序按索引获取对 Address 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="5f66e-110">To get a reference to the Address cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5f66e-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5f66e-111">Cell name:</span></span>  <br/> |<span data-ttu-id="5f66e-112">超链接。</span><span class="sxs-lookup"><span data-stu-id="5f66e-112">Hyperlink.</span></span> <span data-ttu-id="5f66e-113">*名称*。超链接的地址。</span><span class="sxs-lookup"><span data-stu-id="5f66e-113">*name*  .Address           where Hyperlink.</span></span> <span data-ttu-id="5f66e-114">*name*是超链接行的名称</span><span class="sxs-lookup"><span data-stu-id="5f66e-114">*name*  is the name of the hyperlink row</span></span>  <br/> |
   
<span data-ttu-id="5f66e-115">若要从另一个公式或从使用**CellsU**属性的某个程序按名称获取对 Address 单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="5f66e-115">To get a reference to the Address cell by name from another formula, or from a program, by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5f66e-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5f66e-116">Section index:</span></span>  <br/> |<span data-ttu-id="5f66e-117">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="5f66e-117">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="5f66e-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="5f66e-118">Row index:</span></span>  <br/> |<span data-ttu-id="5f66e-119">**visRow1stHyperlink** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="5f66e-119">**visRow1stHyperlink** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="5f66e-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5f66e-120">Cell index:</span></span>  <br/> |<span data-ttu-id="5f66e-121">**visHLinkAddress**</span><span class="sxs-lookup"><span data-stu-id="5f66e-121">**visHLinkAddress**</span></span> <br/> |
   

