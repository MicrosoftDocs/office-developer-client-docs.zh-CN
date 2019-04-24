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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328593"
---
# <a name="formulaexists-function"></a><span data-ttu-id="392d5-103">FORMULAEXISTS 函数</span><span class="sxs-lookup"><span data-stu-id="392d5-103">FORMULAEXISTS Function</span></span>

<span data-ttu-id="392d5-104">指示引用的单元格是否包含公式。</span><span class="sxs-lookup"><span data-stu-id="392d5-104">Indicates whether the referenced cell contains a formula.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="392d5-105">语法</span><span class="sxs-lookup"><span data-stu-id="392d5-105">Syntax</span></span>

<span data-ttu-id="392d5-106">FORMULAEXISTS (\* \* *cellref* \* \*)</span><span class="sxs-lookup"><span data-stu-id="392d5-106">FORMULAEXISTS (\*\* *cellref* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="392d5-107">参数</span><span class="sxs-lookup"><span data-stu-id="392d5-107">Parameters</span></span>

|<span data-ttu-id="392d5-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="392d5-108">**Name**</span></span>|<span data-ttu-id="392d5-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="392d5-109">**Required/Optional**</span></span>|<span data-ttu-id="392d5-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="392d5-110">**Data Type**</span></span>|<span data-ttu-id="392d5-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="392d5-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="392d5-112">_cellref_</span><span class="sxs-lookup"><span data-stu-id="392d5-112">_cellref_</span></span> <br/> |<span data-ttu-id="392d5-113">必需</span><span class="sxs-lookup"><span data-stu-id="392d5-113">Required</span></span>  <br/> |<span data-ttu-id="392d5-114">**String**</span><span class="sxs-lookup"><span data-stu-id="392d5-114">**String**</span></span> <br/> |<span data-ttu-id="392d5-115">要检查其中是否存在公式的单元格。</span><span class="sxs-lookup"><span data-stu-id="392d5-115">The cell that you want to check for the presence of a formula.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="392d5-116">注解</span><span class="sxs-lookup"><span data-stu-id="392d5-116">Remarks</span></span>

<span data-ttu-id="392d5-117">如果单元格包含公式, 则 FORMULAEXISTS 函数返回 1; 否则返回1。如果它不包含公式, 则返回零 (0)。</span><span class="sxs-lookup"><span data-stu-id="392d5-117">The FORMULAEXISTS function returns 1 if the cell contains a formula; if it does not contain a formula, it returns zero (0).</span></span> 
  

