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
description: 指示是否引用的单元格包含公式。
ms.openlocfilehash: 9f006cdfed9830734ed2226673ba7566995a58b8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780312"
---
# <a name="formulaexists-function"></a><span data-ttu-id="c8944-103">FORMULAEXISTS 函数</span><span class="sxs-lookup"><span data-stu-id="c8944-103">FORMULAEXISTS Function</span></span>

<span data-ttu-id="c8944-104">指示是否引用的单元格包含公式。</span><span class="sxs-lookup"><span data-stu-id="c8944-104">Indicates whether the referenced cell contains a formula.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="c8944-105">语法</span><span class="sxs-lookup"><span data-stu-id="c8944-105">Syntax</span></span>

<span data-ttu-id="c8944-106">FORMULAEXISTS (* * *cellref* * *)</span><span class="sxs-lookup"><span data-stu-id="c8944-106">FORMULAEXISTS (** *cellref* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c8944-107">参数</span><span class="sxs-lookup"><span data-stu-id="c8944-107">Parameters</span></span>

|<span data-ttu-id="c8944-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="c8944-108">**Name**</span></span>|<span data-ttu-id="c8944-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c8944-109">**Required/Optional**</span></span>|<span data-ttu-id="c8944-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c8944-110">**Data Type**</span></span>|<span data-ttu-id="c8944-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="c8944-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c8944-112">_cellref_</span><span class="sxs-lookup"><span data-stu-id="c8944-112">_cellref_</span></span> <br/> |<span data-ttu-id="c8944-113">必需</span><span class="sxs-lookup"><span data-stu-id="c8944-113">Required</span></span>  <br/> |<span data-ttu-id="c8944-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="c8944-114">**String**</span></span> <br/> |<span data-ttu-id="c8944-115">要检查其中是否存在公式的单元格。</span><span class="sxs-lookup"><span data-stu-id="c8944-115">The cell that you want to check for the presence of a formula.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c8944-116">注解</span><span class="sxs-lookup"><span data-stu-id="c8944-116">Remarks</span></span>

<span data-ttu-id="c8944-117">FORMULAEXISTS 函数返回 1; 如果该单元格包含公式;如果它不包含公式，它将返回零 (0)。</span><span class="sxs-lookup"><span data-stu-id="c8944-117">The FORMULAEXISTS function returns 1 if the cell contains a formula; if it does not contain a formula, it returns zero (0).</span></span> 
  

