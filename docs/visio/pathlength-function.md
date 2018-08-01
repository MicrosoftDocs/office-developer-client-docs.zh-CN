---
title: PATHLENGTH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f47ea08-fb5e-7d48-e84a-2a6570564924
description: 返回在指定 Geometry 节中定义的路径的长度。
ms.openlocfilehash: 37cabbde9fc0782bc1fde46f3065d0c945c9dada
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780850"
---
# <a name="pathlength-function"></a><span data-ttu-id="db524-103">PATHLENGTH 函数</span><span class="sxs-lookup"><span data-stu-id="db524-103">PATHLENGTH Function</span></span>

<span data-ttu-id="db524-104">返回在指定 Geometry 节中定义的路径的长度。</span><span class="sxs-lookup"><span data-stu-id="db524-104">Returns the length of the path that is defined in the specified Geometry section.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="db524-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="db524-105">Version Information</span></span>

<span data-ttu-id="db524-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="db524-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="db524-107">语法</span><span class="sxs-lookup"><span data-stu-id="db524-107">Syntax</span></span>

<span data-ttu-id="db524-108">PATHLENGTH (* **部分** * * * *[、 段]* * *)</span><span class="sxs-lookup"><span data-stu-id="db524-108">PATHLENGTH(** *section* ** ** *[,segment]* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="db524-109">参数</span><span class="sxs-lookup"><span data-stu-id="db524-109">Parameters</span></span>

|<span data-ttu-id="db524-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="db524-110">**Name**</span></span>|<span data-ttu-id="db524-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="db524-111">**Required/Optional**</span></span>|<span data-ttu-id="db524-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="db524-112">**Data Type**</span></span>|<span data-ttu-id="db524-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="db524-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="db524-114">_section_</span><span class="sxs-lookup"><span data-stu-id="db524-114">_section_</span></span> <br/> |<span data-ttu-id="db524-115">必需</span><span class="sxs-lookup"><span data-stu-id="db524-115">Required</span></span>  <br/> |<span data-ttu-id="db524-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="db524-116">**String**</span></span> <br/> |<span data-ttu-id="db524-117">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="db524-117">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="db524-118">_段_</span><span class="sxs-lookup"><span data-stu-id="db524-118">_segment_</span></span> <br/> |<span data-ttu-id="db524-119">可选</span><span class="sxs-lookup"><span data-stu-id="db524-119">Optional</span></span>  <br/> |<span data-ttu-id="db524-120">**Integer**</span><span class="sxs-lookup"><span data-stu-id="db524-120">**Integer**</span></span> <br/> |<span data-ttu-id="db524-121">要度量的路径段（从 1 开始）。</span><span class="sxs-lookup"><span data-stu-id="db524-121">The 1-based segment of the path to measure.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="db524-122">返回值</span><span class="sxs-lookup"><span data-stu-id="db524-122">Return value</span></span>

 <span data-ttu-id="db524-123">**Double**</span><span class="sxs-lookup"><span data-stu-id="db524-123">**Double**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="db524-124">注解</span><span class="sxs-lookup"><span data-stu-id="db524-124">Remarks</span></span>

<span data-ttu-id="db524-125">如果_section_或_segment_不存在，Microsoft Visio 将返回 #REF ！。</span><span class="sxs-lookup"><span data-stu-id="db524-125">If  _section_ or  _segment_ does not exist, Microsoft Visio returns #REF!.</span></span> 
  
<span data-ttu-id="db524-126">如果包含_segment_值，则 PATHLENGTH 返回仅段的长度。</span><span class="sxs-lookup"><span data-stu-id="db524-126">If you include a  _segment_ value, PATHLENGTH returns the length of that segment only.</span></span> 
  

