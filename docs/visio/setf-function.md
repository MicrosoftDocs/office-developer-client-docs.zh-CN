---
title: SETF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251496
localization_priority: Normal
ms.assetid: fcf415c1-171f-b75f-6e40-2bbdbe8b1cfb
description: 设置单元格的公式。
ms.openlocfilehash: 63050de92394ebbdce6cfe053e15347ca3ce5c7f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425972"
---
# <a name="setf-function"></a><span data-ttu-id="b738d-103">SETF 函数</span><span class="sxs-lookup"><span data-stu-id="b738d-103">SETF Function</span></span>

<span data-ttu-id="b738d-104">设置单元格的公式。</span><span class="sxs-lookup"><span data-stu-id="b738d-104">Sets a cell's formula.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b738d-105">语法</span><span class="sxs-lookup"><span data-stu-id="b738d-105">Syntax</span></span>

<span data-ttu-id="b738d-106">SETF ( GETREF (\*\* *cell* \*\* ) ， \*\* *formula* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="b738d-106">SETF( GETREF(\*\* *cell* \*\* ), \*\* *formula* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="b738d-107">参数</span><span class="sxs-lookup"><span data-stu-id="b738d-107">Parameters</span></span>

|<span data-ttu-id="b738d-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="b738d-108">**Name**</span></span>|<span data-ttu-id="b738d-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="b738d-109">**Required/Optional**</span></span>|<span data-ttu-id="b738d-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b738d-110">**Data Type**</span></span>|<span data-ttu-id="b738d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="b738d-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b738d-112">_cell_</span><span class="sxs-lookup"><span data-stu-id="b738d-112">_cell_</span></span> <br/> |<span data-ttu-id="b738d-113">必需</span><span class="sxs-lookup"><span data-stu-id="b738d-113">Required</span></span>  <br/> |<span data-ttu-id="b738d-114">**String**</span><span class="sxs-lookup"><span data-stu-id="b738d-114">**String**</span></span> <br/> |<span data-ttu-id="b738d-115">要设置其公式的单元格。</span><span class="sxs-lookup"><span data-stu-id="b738d-115">The cell whose formula to set.</span></span>  <br/> |
| <span data-ttu-id="b738d-116">_formula_</span><span class="sxs-lookup"><span data-stu-id="b738d-116">_formula_</span></span> <br/> |<span data-ttu-id="b738d-117">必需</span><span class="sxs-lookup"><span data-stu-id="b738d-117">Required</span></span>  <br/> |<span data-ttu-id="b738d-118">**String**</span><span class="sxs-lookup"><span data-stu-id="b738d-118">**String**</span></span> <br/> |<span data-ttu-id="b738d-119">要使用的公式。</span><span class="sxs-lookup"><span data-stu-id="b738d-119">The formula to use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b738d-120">备注</span><span class="sxs-lookup"><span data-stu-id="b738d-120">Remarks</span></span>

<span data-ttu-id="b738d-121">计算时，formula 中的表达式  _结果将成为单元格_ 中的新  _公式_。</span><span class="sxs-lookup"><span data-stu-id="b738d-121">When evaluated, the result of the expression in  _formula_ becomes the new formula in  _cell_.</span></span> <span data-ttu-id="b738d-122">如果  _formula_ 括在引号中，则引用的表达式将写入  _单元格_。</span><span class="sxs-lookup"><span data-stu-id="b738d-122">If  _formula_ is enclosed in quotation marks, the quoted expression is written to  _cell_.</span></span> <span data-ttu-id="b738d-123">若要将  _单元格_ 设置为字符串，请用三组引号将  _公式_ 括起来。</span><span class="sxs-lookup"><span data-stu-id="b738d-123">To set  _cell_ to a string, enclose  _formula_ in three sets of quotation marks.</span></span> 
  
<span data-ttu-id="b738d-p102">目标单元格必须使用 GETREF() 引用来指定或必须指定为一个字符串，以避免循环。最好使用 GETREF，因为 Microsoft Visio 能够在形状移到不同的文档时调整引用。</span><span class="sxs-lookup"><span data-stu-id="b738d-p102">The target cell must be specified using a GETREF() reference or as a string to avoid circularity. Using GETREF is preferred, because Microsoft Visio can adjust references when the shape is moved to a different document.</span></span>
  
<span data-ttu-id="b738d-126">如果没有  _使用_ GETREF 或字符串指定单元格，函数将返回错误，并且单元格的公式不变。</span><span class="sxs-lookup"><span data-stu-id="b738d-126">If  _cell_ is not specified using GETREF or as a string, the function returns an error, and no cell's formula is changed.</span></span> <span data-ttu-id="b738d-127">如果  _formula_ 包含语法错误，函数将返回错误，并且  _单元格中的公式_ 不会更改。</span><span class="sxs-lookup"><span data-stu-id="b738d-127">If  _formula_ contains a syntax error, the function returns an error, and the formula in  _cell_ is not changed.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="b738d-128">示例 1</span><span class="sxs-lookup"><span data-stu-id="b738d-128">Example 1</span></span>

<span data-ttu-id="b738d-129">SETF ( GETREF (Scratch.A1) ， 1.5 in \* 6 + 1 ft) </span><span class="sxs-lookup"><span data-stu-id="b738d-129">SETF( GETREF(Scratch.A1), 1.5 in \* 6 + 1 ft)</span></span>
  
<span data-ttu-id="b738d-130">将 Scratch.A1 的公式设置为 21 英寸。</span><span class="sxs-lookup"><span data-stu-id="b738d-130">Sets the formula of Scratch.A1 to 21 inches.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="b738d-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="b738d-131">Example 2</span></span>

<span data-ttu-id="b738d-132">SETF ( GETREF (Scratch.A1) ，"1.5 in \* 6 + 1 ft") </span><span class="sxs-lookup"><span data-stu-id="b738d-132">SETF( GETREF(Scratch.A1), "1.5 in \* 6 + 1 ft")</span></span>
  
<span data-ttu-id="b738d-133">将 Scratch.</span><span class="sxs-lookup"><span data-stu-id="b738d-133">Sets the formula of Scratch.</span></span> <span data-ttu-id="b738d-134">A1 到表达式 1.5 in \* 6+1 ft。</span><span class="sxs-lookup"><span data-stu-id="b738d-134">A1 to the expression 1.5 in\*6+1 ft.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="b738d-135">示例 3</span><span class="sxs-lookup"><span data-stu-id="b738d-135">Example 3</span></span>

<span data-ttu-id="b738d-136">SETF( GETREF(Scratch.A1), """Say """"ahh""""""")</span><span class="sxs-lookup"><span data-stu-id="b738d-136">SETF( GETREF(Scratch.A1), """Say """"ahh""""""")</span></span>
  
<span data-ttu-id="b738d-137">将 Scratch.A1 的公式设置为字符串“Say ""ahh""”，该字符串相当于“Say "ahh"”。</span><span class="sxs-lookup"><span data-stu-id="b738d-137">Sets the formula of Scratch.A1 to the string "Say ""ahh""" which evaluates to Say "ahh".</span></span>
  

