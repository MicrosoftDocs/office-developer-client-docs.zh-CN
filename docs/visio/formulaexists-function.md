---
title: FORMULAEXISTS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033806
localization_priority: Normal
ms.assetid: 3d4f82d3-fcd0-536a-c4e1-94c362cde7c4
description: 指示引用的单元格是否包含公式。
ms.openlocfilehash: 1f28d429516d4f8b2357f1c2ab589700e38ff40a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420274"
---
# <a name="formulaexists-function"></a><span data-ttu-id="a2468-103">FORMULAEXISTS 函数</span><span class="sxs-lookup"><span data-stu-id="a2468-103">FORMULAEXISTS Function</span></span>

<span data-ttu-id="a2468-104">指示引用的单元格是否包含公式。</span><span class="sxs-lookup"><span data-stu-id="a2468-104">Indicates whether the referenced cell contains a formula.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a2468-105">语法</span><span class="sxs-lookup"><span data-stu-id="a2468-105">Syntax</span></span>

<span data-ttu-id="a2468-106">FORMULAEXISTS (\*\* *cellref* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="a2468-106">FORMULAEXISTS (\*\* *cellref* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="a2468-107">参数</span><span class="sxs-lookup"><span data-stu-id="a2468-107">Parameters</span></span>

|<span data-ttu-id="a2468-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="a2468-108">**Name**</span></span>|<span data-ttu-id="a2468-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="a2468-109">**Required/Optional**</span></span>|<span data-ttu-id="a2468-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a2468-110">**Data Type**</span></span>|<span data-ttu-id="a2468-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="a2468-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a2468-112">_cellref_</span><span class="sxs-lookup"><span data-stu-id="a2468-112">_cellref_</span></span> <br/> |<span data-ttu-id="a2468-113">必需</span><span class="sxs-lookup"><span data-stu-id="a2468-113">Required</span></span>  <br/> |<span data-ttu-id="a2468-114">**String**</span><span class="sxs-lookup"><span data-stu-id="a2468-114">**String**</span></span> <br/> |<span data-ttu-id="a2468-115">要检查其中是否存在公式的单元格。</span><span class="sxs-lookup"><span data-stu-id="a2468-115">The cell that you want to check for the presence of a formula.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a2468-116">备注</span><span class="sxs-lookup"><span data-stu-id="a2468-116">Remarks</span></span>

<span data-ttu-id="a2468-117">如果单元格包含公式，FORMULAEXISTS 函数将返回 1;如果公式不包含公式，则返回零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="a2468-117">The FORMULAEXISTS function returns 1 if the cell contains a formula; if it does not contain a formula, it returns zero (0).</span></span> 
  

