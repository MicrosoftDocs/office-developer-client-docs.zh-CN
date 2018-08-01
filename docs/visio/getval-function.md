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
description: 获取单元格的值和单元格的值更改时不重新计算公式。
ms.openlocfilehash: b4c8ea14b7184101a360c9f5ee4af03fd178aa6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780341"
---
# <a name="getval-function"></a><span data-ttu-id="67312-103">GETVAL 函数</span><span class="sxs-lookup"><span data-stu-id="67312-103">GETVAL Function</span></span>

<span data-ttu-id="67312-104">获取单元格的值和单元格的值更改时不重新计算公式。</span><span class="sxs-lookup"><span data-stu-id="67312-104">Gets the value of a cell and doesn't recalculate the formula when the cell's value changes.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="67312-105">语法</span><span class="sxs-lookup"><span data-stu-id="67312-105">Syntax</span></span>

<span data-ttu-id="67312-106">GETVAL (* * *cellname* * *)</span><span class="sxs-lookup"><span data-stu-id="67312-106">GETVAL(** *cellname* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="67312-107">参数</span><span class="sxs-lookup"><span data-stu-id="67312-107">Parameters</span></span>

|<span data-ttu-id="67312-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="67312-108">**Name**</span></span>|<span data-ttu-id="67312-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="67312-109">**Required/Optional**</span></span>|<span data-ttu-id="67312-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="67312-110">**Data Type**</span></span>|<span data-ttu-id="67312-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="67312-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="67312-112">_cellname_</span><span class="sxs-lookup"><span data-stu-id="67312-112">_cellname_</span></span> <br/> |<span data-ttu-id="67312-113">必需</span><span class="sxs-lookup"><span data-stu-id="67312-113">Required</span></span>  <br/> |<span data-ttu-id="67312-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="67312-114">**String**</span></span> <br/> |<span data-ttu-id="67312-115">要获取其值的单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="67312-115">The name of the cell to get the value of.</span></span>  <br/> |
   
## <a name="example"></a><span data-ttu-id="67312-116">示例</span><span class="sxs-lookup"><span data-stu-id="67312-116">Example</span></span>

<span data-ttu-id="67312-117">GETVAL(PinX) + GETVAL(PinY) + Width</span><span class="sxs-lookup"><span data-stu-id="67312-117">GETVAL(PinX) + GETVAL(PinY) + Width</span></span> 
  
<span data-ttu-id="67312-118">返回 PinX、PinY 和 Width 单元格的值的总和。</span><span class="sxs-lookup"><span data-stu-id="67312-118">Returns the sum of the value of the PinX, PinY, and Width cells.</span></span> 
  

