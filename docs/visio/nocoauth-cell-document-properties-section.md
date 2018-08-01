---
title: NoCoauth 单元格（“Document Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f2095c9-ce09-48f7-b160-c9822d96a96c
description: 设置是否文档存储在 Microsoft SharePoint 2013 服务器或 Microsoft OneDrive 可以编辑多个作者同时共同创作的会话中。
ms.openlocfilehash: a20c3a5aa1392e0e6c3bef124f536b91b9642f47
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780794"
---
# <a name="nocoauth-cell-document-properties-section"></a><span data-ttu-id="2d2dc-103">NoCoauth 单元格（“Document Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="2d2dc-103">NoCoauth Cell (Document Properties Section)</span></span>

<span data-ttu-id="2d2dc-104">设置是否文档存储在 Microsoft SharePoint 2013 服务器或 Microsoft OneDrive 可以编辑多个作者同时共同创作的会话中。</span><span class="sxs-lookup"><span data-stu-id="2d2dc-104">Sets whether a document stored on a Microsoft SharePoint 2013 server or Microsoft OneDrive can be edited by multiple authors simultaneously in a coauthoring session.</span></span>
  
|<span data-ttu-id="2d2dc-105">**值**</span><span class="sxs-lookup"><span data-stu-id="2d2dc-105">**Value**</span></span>|<span data-ttu-id="2d2dc-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="2d2dc-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2d2dc-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="2d2dc-107">TRUE</span></span>  <br/> |<span data-ttu-id="2d2dc-108">文档无法合著，并且锁定以进行编辑时打开。</span><span class="sxs-lookup"><span data-stu-id="2d2dc-108">The document cannot be coauthored and is locked for editing when open.</span></span>  <br/> |
|<span data-ttu-id="2d2dc-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="2d2dc-109">FALSE</span></span>  <br/> |<span data-ttu-id="2d2dc-110">可以合著文档。</span><span class="sxs-lookup"><span data-stu-id="2d2dc-110">The document can be coauthored.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2d2dc-111">说明</span><span class="sxs-lookup"><span data-stu-id="2d2dc-111">Remarks</span></span>

<span data-ttu-id="2d2dc-112">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**NoCoauth**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2d2dc-112">To get a reference to the **NoCoauth** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2d2dc-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2d2dc-113">Cell name:</span></span>  <br/> | <span data-ttu-id="2d2dc-114">NoCoauth</span><span class="sxs-lookup"><span data-stu-id="2d2dc-114">NoCoauth</span></span>  <br/> |
   
<span data-ttu-id="2d2dc-115">若要从某个程序按索引获取对**NoCoauth**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="2d2dc-115">To get a reference to the **NoCoauth** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2d2dc-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2d2dc-116">Section index:</span></span>  <br/> |<span data-ttu-id="2d2dc-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2d2dc-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="2d2dc-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="2d2dc-118">Row index:</span></span>  <br/> |<span data-ttu-id="2d2dc-119">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="2d2dc-119">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="2d2dc-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2d2dc-120">Cell index:</span></span>  <br/> |<span data-ttu-id="2d2dc-121">**visDocNoCoauth**</span><span class="sxs-lookup"><span data-stu-id="2d2dc-121">**visDocNoCoauth**</span></span> <br/> |
   

