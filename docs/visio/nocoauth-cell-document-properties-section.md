---
title: 'NoCoauth Cell (Document Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f2095c9-ce09-48f7-b160-c9822d96a96c
description: 设置存储在 Microsoft SharePoint 2013 服务器或 Microsoft OneDrive上的文档是否可以由多个作者在共同创作会话中同时编辑。
ms.openlocfilehash: a76e2d3b2c3cf6e99e37596b016f448b0be56fd3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420512"
---
# <a name="nocoauth-cell-document-properties-section"></a><span data-ttu-id="52dfd-103">NoCoauth Cell (Document Properties Section) </span><span class="sxs-lookup"><span data-stu-id="52dfd-103">NoCoauth Cell (Document Properties Section)</span></span>

<span data-ttu-id="52dfd-104">设置存储在 Microsoft SharePoint 2013 服务器或 Microsoft OneDrive上的文档是否可以由多个作者在共同创作会话中同时编辑。</span><span class="sxs-lookup"><span data-stu-id="52dfd-104">Sets whether a document stored on a Microsoft SharePoint 2013 server or Microsoft OneDrive can be edited by multiple authors simultaneously in a coauthoring session.</span></span>
  
|<span data-ttu-id="52dfd-105">**值**</span><span class="sxs-lookup"><span data-stu-id="52dfd-105">**Value**</span></span>|<span data-ttu-id="52dfd-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="52dfd-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52dfd-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="52dfd-107">TRUE</span></span>  <br/> |<span data-ttu-id="52dfd-108">该文档无法共同授权，并且将在打开时锁定进行编辑。</span><span class="sxs-lookup"><span data-stu-id="52dfd-108">The document cannot be coauthored and is locked for editing when open.</span></span>  <br/> |
|<span data-ttu-id="52dfd-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="52dfd-109">FALSE</span></span>  <br/> |<span data-ttu-id="52dfd-110">文档可以共同授权。</span><span class="sxs-lookup"><span data-stu-id="52dfd-110">The document can be coauthored.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="52dfd-111">备注</span><span class="sxs-lookup"><span data-stu-id="52dfd-111">Remarks</span></span>

<span data-ttu-id="52dfd-112">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **NoCoauth** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="52dfd-112">To get a reference to the **NoCoauth** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="52dfd-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="52dfd-113">Cell name:</span></span>  <br/> | <span data-ttu-id="52dfd-114">NoCoauth</span><span class="sxs-lookup"><span data-stu-id="52dfd-114">NoCoauth</span></span>  <br/> |
   
<span data-ttu-id="52dfd-115">若要从程序按索引获取对 **NoCoauth** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="52dfd-115">To get a reference to the **NoCoauth** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="52dfd-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="52dfd-116">Section index:</span></span>  <br/> |<span data-ttu-id="52dfd-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="52dfd-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="52dfd-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="52dfd-118">Row index:</span></span>  <br/> |<span data-ttu-id="52dfd-119">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="52dfd-119">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="52dfd-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="52dfd-120">Cell index:</span></span>  <br/> |<span data-ttu-id="52dfd-121">**visDocNoCoauth**</span><span class="sxs-lookup"><span data-stu-id="52dfd-121">**visDocNoCoauth**</span></span> <br/> |
   

