---
title: GETVAL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251885
localization_priority: Normal
ms.assetid: 1da42991-5791-ebab-84cc-286cfe984a61
description: 获取单元格的值, 并且在单元格的值发生更改时不重新计算公式。
ms.openlocfilehash: 9449ccd8f849b23faf08ee25826301a1b6efe6d0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327312"
---
# <a name="getval-function"></a><span data-ttu-id="37d0c-103">GETVAL 函数</span><span class="sxs-lookup"><span data-stu-id="37d0c-103">GETVAL Function</span></span>

<span data-ttu-id="37d0c-104">获取单元格的值, 并且在单元格的值发生更改时不重新计算公式。</span><span class="sxs-lookup"><span data-stu-id="37d0c-104">Gets the value of a cell and doesn't recalculate the formula when the cell's value changes.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="37d0c-105">语法</span><span class="sxs-lookup"><span data-stu-id="37d0c-105">Syntax</span></span>

<span data-ttu-id="37d0c-106">GETVAL (\* \* *cellname* \* \*)</span><span class="sxs-lookup"><span data-stu-id="37d0c-106">GETVAL(\*\* *cellname* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="37d0c-107">参数</span><span class="sxs-lookup"><span data-stu-id="37d0c-107">Parameters</span></span>

|<span data-ttu-id="37d0c-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="37d0c-108">**Name**</span></span>|<span data-ttu-id="37d0c-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="37d0c-109">**Required/Optional**</span></span>|<span data-ttu-id="37d0c-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="37d0c-110">**Data Type**</span></span>|<span data-ttu-id="37d0c-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="37d0c-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="37d0c-112">_cellname_</span><span class="sxs-lookup"><span data-stu-id="37d0c-112">_cellname_</span></span> <br/> |<span data-ttu-id="37d0c-113">必需</span><span class="sxs-lookup"><span data-stu-id="37d0c-113">Required</span></span>  <br/> |<span data-ttu-id="37d0c-114">**String**</span><span class="sxs-lookup"><span data-stu-id="37d0c-114">**String**</span></span> <br/> |<span data-ttu-id="37d0c-115">要获取其值的单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="37d0c-115">The name of the cell to get the value of.</span></span>  <br/> |
   
## <a name="example"></a><span data-ttu-id="37d0c-116">示例</span><span class="sxs-lookup"><span data-stu-id="37d0c-116">Example</span></span>

<span data-ttu-id="37d0c-117">GETVAL(PinX) + GETVAL(PinY) + Width</span><span class="sxs-lookup"><span data-stu-id="37d0c-117">GETVAL(PinX) + GETVAL(PinY) + Width</span></span> 
  
<span data-ttu-id="37d0c-118">返回 PinX、PinY 和 Width 单元格的值的总和。</span><span class="sxs-lookup"><span data-stu-id="37d0c-118">Returns the sum of the value of the PinX, PinY, and Width cells.</span></span> 
  

