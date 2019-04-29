---
title: EVALTEXT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251422
localization_priority: Normal
ms.assetid: c9b5b96c-d8c8-6119-e3f1-a2ce9d7c043e
description: 评估 shapename 中的文本, 就好像它是一个公式并返回结果。
ms.openlocfilehash: 6600d9d6ddaf630a93fdb5c37639ce50a21a4307
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438356"
---
# <a name="evaltext-function"></a><span data-ttu-id="774d2-103">EVALTEXT 函数</span><span class="sxs-lookup"><span data-stu-id="774d2-103">EVALTEXT Function</span></span>

<span data-ttu-id="774d2-104">评估_shapename_中的文本, 就好像它是一个公式并返回结果。</span><span class="sxs-lookup"><span data-stu-id="774d2-104">Evaluates the text in  _shapename_ as if it were a formula and returns the result.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="774d2-105">语法</span><span class="sxs-lookup"><span data-stu-id="774d2-105">Syntax</span></span>

<span data-ttu-id="774d2-106">EVALTEXT (\* \* *shapename! theText* \* \*)</span><span class="sxs-lookup"><span data-stu-id="774d2-106">EVALTEXT(\*\* *shapename!theText* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="774d2-107">参数</span><span class="sxs-lookup"><span data-stu-id="774d2-107">Parameters</span></span>

|<span data-ttu-id="774d2-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="774d2-108">**Name**</span></span>|<span data-ttu-id="774d2-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="774d2-109">**Required/Optional**</span></span>|<span data-ttu-id="774d2-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="774d2-110">**Data Type**</span></span>|<span data-ttu-id="774d2-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="774d2-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="774d2-112">_shapename! theText_</span><span class="sxs-lookup"><span data-stu-id="774d2-112">_shapename!theText_</span></span> <br/> |<span data-ttu-id="774d2-113">必需</span><span class="sxs-lookup"><span data-stu-id="774d2-113">Required</span></span>  <br/> |<span data-ttu-id="774d2-114">**String**</span><span class="sxs-lookup"><span data-stu-id="774d2-114">**String**</span></span> <br/> |<span data-ttu-id="774d2-115">当关联形状的文本构成改变时触发的单元格。</span><span class="sxs-lookup"><span data-stu-id="774d2-115">A cell that is triggered when the associated shape's text composition changes.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="774d2-116">返回值</span><span class="sxs-lookup"><span data-stu-id="774d2-116">Return value</span></span>

<span data-ttu-id="774d2-117">String</span><span class="sxs-lookup"><span data-stu-id="774d2-117">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="774d2-118">说明</span><span class="sxs-lookup"><span data-stu-id="774d2-118">Remarks</span></span>

 <span data-ttu-id="774d2-119">_shapename_ 可用来指代某形状（不是当前形状）的文本。</span><span class="sxs-lookup"><span data-stu-id="774d2-119">_shapename_ can be used to refer to the text of a shape other than the current shape.</span></span> 
  
<span data-ttu-id="774d2-120">如果没有文本，则结果为零。</span><span class="sxs-lookup"><span data-stu-id="774d2-120">If there is no text, the result is zero.</span></span> <span data-ttu-id="774d2-121">如果无法对文本求值，则该函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="774d2-121">If the text cannot be evaluated, the function returns an error.</span></span>
  
## <a name="example"></a><span data-ttu-id="774d2-122">示例</span><span class="sxs-lookup"><span data-stu-id="774d2-122">Example</span></span>

<span data-ttu-id="774d2-123">EVALTEXT (第2行! theText)</span><span class="sxs-lookup"><span data-stu-id="774d2-123">EVALTEXT(Line.2!theText)</span></span> 
  
<span data-ttu-id="774d2-p102">对形状 Line.2 中包含的文本求值。例如，如果 Line.2 包含“4 ft + 0.5 ft”，则返回的值为 4.5 ft。</span><span class="sxs-lookup"><span data-stu-id="774d2-p102">Evaluates the text contained in the shape Line.2. For example, if Line.2 contains "4 ft + 0.5 ft", returns the value 4.5 ft.</span></span> 
  

