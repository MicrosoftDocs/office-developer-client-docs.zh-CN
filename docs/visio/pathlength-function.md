---
title: PATHLENGTH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f47ea08-fb5e-7d48-e84a-2a6570564924
description: 返回在指定 Geometry 节中定义的路径的长度。
ms.openlocfilehash: e4f90c2bb886f54164bedab5f8d78fc528758414
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405847"
---
# <a name="pathlength-function"></a><span data-ttu-id="d2188-103">PATHLENGTH 函数</span><span class="sxs-lookup"><span data-stu-id="d2188-103">PATHLENGTH Function</span></span>

<span data-ttu-id="d2188-104">返回在指定 Geometry 节中定义的路径的长度。</span><span class="sxs-lookup"><span data-stu-id="d2188-104">Returns the length of the path that is defined in the specified Geometry section.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="d2188-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="d2188-105">Version Information</span></span>

<span data-ttu-id="d2188-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="d2188-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d2188-107">语法</span><span class="sxs-lookup"><span data-stu-id="d2188-107">Syntax</span></span>

<span data-ttu-id="d2188-108">PATHLENGTH (\*\* *section* \*\* \*\* *[，segment]* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="d2188-108">PATHLENGTH(\*\* *section* \*\* \*\* *[,segment]* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d2188-109">参数</span><span class="sxs-lookup"><span data-stu-id="d2188-109">Parameters</span></span>

|<span data-ttu-id="d2188-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="d2188-110">**Name**</span></span>|<span data-ttu-id="d2188-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d2188-111">**Required/Optional**</span></span>|<span data-ttu-id="d2188-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d2188-112">**Data Type**</span></span>|<span data-ttu-id="d2188-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="d2188-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d2188-114">_section_</span><span class="sxs-lookup"><span data-stu-id="d2188-114">_section_</span></span> <br/> |<span data-ttu-id="d2188-115">必需</span><span class="sxs-lookup"><span data-stu-id="d2188-115">Required</span></span>  <br/> |<span data-ttu-id="d2188-116">**String**</span><span class="sxs-lookup"><span data-stu-id="d2188-116">**String**</span></span> <br/> |<span data-ttu-id="d2188-117">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="d2188-117">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="d2188-118">_segment_</span><span class="sxs-lookup"><span data-stu-id="d2188-118">_segment_</span></span> <br/> |<span data-ttu-id="d2188-119">可选</span><span class="sxs-lookup"><span data-stu-id="d2188-119">Optional</span></span>  <br/> |<span data-ttu-id="d2188-120">**Integer**</span><span class="sxs-lookup"><span data-stu-id="d2188-120">**Integer**</span></span> <br/> |<span data-ttu-id="d2188-121">要度量的路径段（从 1 开始）。</span><span class="sxs-lookup"><span data-stu-id="d2188-121">The 1-based segment of the path to measure.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="d2188-122">返回值</span><span class="sxs-lookup"><span data-stu-id="d2188-122">Return value</span></span>

 <span data-ttu-id="d2188-123">**Double**</span><span class="sxs-lookup"><span data-stu-id="d2188-123">**Double**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d2188-124">备注</span><span class="sxs-lookup"><span data-stu-id="d2188-124">Remarks</span></span>

<span data-ttu-id="d2188-125">如果  _section_ 或  _segment_ 不存在，Microsoft Visio 将返回 #REF！。</span><span class="sxs-lookup"><span data-stu-id="d2188-125">If  _section_ or  _segment_ does not exist, Microsoft Visio returns #REF!.</span></span> 
  
<span data-ttu-id="d2188-126">如果  _包含段值_ ，PATHLENGTH 将仅返回该线段的长度。</span><span class="sxs-lookup"><span data-stu-id="d2188-126">If you include a  _segment_ value, PATHLENGTH returns the length of that segment only.</span></span> 
  

