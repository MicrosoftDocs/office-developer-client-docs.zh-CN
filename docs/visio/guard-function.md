---
title: GUARD 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251435
localization_priority: Normal
ms.assetid: 6c85414c-9fb6-cdc5-f5b6-8eb13c9608af
description: 通过在绘图窗口中执行的操作 (例如移动、调整大小、组合或取消组合形状) 防止删除和更改表达式。
ms.openlocfilehash: 0bdfa023d53e739a970cab65b1dbd67bc1a44461
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408150"
---
# <a name="guard-function"></a><span data-ttu-id="e1d21-103">GUARD 函数</span><span class="sxs-lookup"><span data-stu-id="e1d21-103">GUARD Function</span></span>

<span data-ttu-id="e1d21-104">通过在绘图窗口中执行的操作 (例如移动、调整大小、组合或取消组合形状) 防止删除和更改*表达式*。</span><span class="sxs-lookup"><span data-stu-id="e1d21-104">Protects  *expression*  from deletion and change by actions performed in the drawing window, for example, moving, sizing, grouping, or ungrouping shapes.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e1d21-105">语法</span><span class="sxs-lookup"><span data-stu-id="e1d21-105">Syntax</span></span>

<span data-ttu-id="e1d21-106">GUARD (\* **表达式** \*)</span><span class="sxs-lookup"><span data-stu-id="e1d21-106">GUARD(\*\* *expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e1d21-107">参数</span><span class="sxs-lookup"><span data-stu-id="e1d21-107">Parameters</span></span>

|<span data-ttu-id="e1d21-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="e1d21-108">**Name**</span></span>|<span data-ttu-id="e1d21-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e1d21-109">**Required/Optional**</span></span>|<span data-ttu-id="e1d21-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e1d21-110">**Data Type**</span></span>|<span data-ttu-id="e1d21-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1d21-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e1d21-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="e1d21-112">_expression_</span></span> <br/> |<span data-ttu-id="e1d21-113">必需</span><span class="sxs-lookup"><span data-stu-id="e1d21-113">Required</span></span>  <br/> |<span data-ttu-id="e1d21-114">**String**</span><span class="sxs-lookup"><span data-stu-id="e1d21-114">**String**</span></span> <br/> |<span data-ttu-id="e1d21-115">常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。</span><span class="sxs-lookup"><span data-stu-id="e1d21-115">A combination of constants, operators, functions, and references to ShapeSheet cells that results in a value.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e1d21-116">说明</span><span class="sxs-lookup"><span data-stu-id="e1d21-116">Remarks</span></span>

<span data-ttu-id="e1d21-117">最容易受 GUARD 函数影响的单元格是“Height”、“Width”、“PinX”和“PinY”。</span><span class="sxs-lookup"><span data-stu-id="e1d21-117">The cells most often affected by the GUARD function are Width, Height, PinX, and PinY.</span></span> 
  
<span data-ttu-id="e1d21-p101">在任意单元格中保护一个公式可以防止该单元格的值被绘图窗口中的动作所改变。然而，绘图窗口中的一个动作可能影响几个单元格，如果您想要防止形状的外观发生意外的改变，这些单元格必须都受到保护。</span><span class="sxs-lookup"><span data-stu-id="e1d21-p101">Guarding a formula in any cell prevents that cell's value from being changed by actions in the drawing window. However, one action in the drawing window can affect several cells, and each of these cells must be guarded if you want to prevent unexpected changes to the shape's appearance.</span></span> 
  
## <a name="example"></a><span data-ttu-id="e1d21-120">示例</span><span class="sxs-lookup"><span data-stu-id="e1d21-120">Example</span></span>

<span data-ttu-id="e1d21-121">GUARD(TEXTWIDTH(TheText) + 0.5 in)</span><span class="sxs-lookup"><span data-stu-id="e1d21-121">GUARD(TEXTWIDTH(TheText) + 0.5 in)</span></span> 
  
<span data-ttu-id="e1d21-p102">形状的“Shape Transform”内容中的 Width 单元格中的此表达式可以防止当绘图窗口中形状的宽度改变时，表达式 (TEXTWIDTH(TheText) + 0.5 in) 被其他值替换。TheText 是关联形状的文本构成改变时所触发的单元格。</span><span class="sxs-lookup"><span data-stu-id="e1d21-p102">This expression in the Width cell of a shape's Shape Transform section prevents the expression (TEXTWIDTH(TheText) + 0.5 in) from being replaced with another value when the shape's width is changed in the drawing window. TheText is a cell that gets triggered when the associated shape's text composition changes.</span></span> 
  

