---
title: DEPENDSON 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251420
localization_priority: Normal
ms.assetid: 8fcfcfdd-69e2-b061-fdb6-d29389d14403
description: 创建单元格引用依赖关系。
ms.openlocfilehash: 26e7f5fb0620a5f1812d878f02d5bedd43afe524
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360228"
---
# <a name="dependson-function"></a><span data-ttu-id="ec918-103">DEPENDSON 函数</span><span class="sxs-lookup"><span data-stu-id="ec918-103">DEPENDSON Function</span></span>

<span data-ttu-id="ec918-104">创建单元格引用依赖关系。</span><span class="sxs-lookup"><span data-stu-id="ec918-104">Creates a cell reference dependency.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="ec918-105">语法</span><span class="sxs-lookup"><span data-stu-id="ec918-105">Syntax</span></span>

<span data-ttu-id="ec918-106">DEPENDSON (\* \* *cellref* \* \* [, \* \* *cellref2* \* \*,...])</span><span class="sxs-lookup"><span data-stu-id="ec918-106">DEPENDSON(\*\* *cellref* \*\* [, \*\* *cellref2* \*\*,...])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ec918-107">参数</span><span class="sxs-lookup"><span data-stu-id="ec918-107">Parameters</span></span>

|<span data-ttu-id="ec918-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="ec918-108">**Name**</span></span>|<span data-ttu-id="ec918-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ec918-109">**Required/Optional**</span></span>|<span data-ttu-id="ec918-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ec918-110">**Data Type**</span></span>|<span data-ttu-id="ec918-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="ec918-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ec918-112">_cellref_</span><span class="sxs-lookup"><span data-stu-id="ec918-112">_cellref_</span></span> <br/> |<span data-ttu-id="ec918-113">必需</span><span class="sxs-lookup"><span data-stu-id="ec918-113">Required</span></span>  <br/> |<span data-ttu-id="ec918-114">**String**</span><span class="sxs-lookup"><span data-stu-id="ec918-114">**String**</span></span> <br/> |<span data-ttu-id="ec918-115">第一个单元格引用。</span><span class="sxs-lookup"><span data-stu-id="ec918-115">The first cell reference.</span></span>  <br/> |
| <span data-ttu-id="ec918-116">_cellref2_</span><span class="sxs-lookup"><span data-stu-id="ec918-116">_cellref2_</span></span> <br/> |<span data-ttu-id="ec918-117">可选</span><span class="sxs-lookup"><span data-stu-id="ec918-117">Optional</span></span>  <br/> |<span data-ttu-id="ec918-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="ec918-118">**String**</span></span> <br/> |<span data-ttu-id="ec918-119">第二个单元格引用。</span><span class="sxs-lookup"><span data-stu-id="ec918-119">The second cell reference.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ec918-120">注解</span><span class="sxs-lookup"><span data-stu-id="ec918-120">Remarks</span></span>

<span data-ttu-id="ec918-p101">此函数总是返回 FALSE。在 Event 行或 Action 单元格中使用时不起任何作用。</span><span class="sxs-lookup"><span data-stu-id="ec918-p101">This function always returns FALSE. It has no effect when used in an Event row or an Action cell.</span></span> 
  
## <a name="example"></a><span data-ttu-id="ec918-123">示例</span><span class="sxs-lookup"><span data-stu-id="ec918-123">Example</span></span>

<span data-ttu-id="ec918-124">OPENTEXTWIN() + DEPENDSON(PinX,PinY)</span><span class="sxs-lookup"><span data-stu-id="ec918-124">OPENTEXTWIN() + DEPENDSON(PinX,PinY)</span></span> 
  
<span data-ttu-id="ec918-125">只要形状的 PinX 或 PinY 单元格改变，就打开该形状的文本块。</span><span class="sxs-lookup"><span data-stu-id="ec918-125">Opens the text block for a shape whenever the shape's PinX or PinY cells change.</span></span> 
  

