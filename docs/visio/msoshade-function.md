---
title: MSOSHADE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 905cd1cc-14d3-5d37-89c4-f8461a03dda2
description: 通过将颜色的发光度降低指定的百分比来修改颜色。
ms.openlocfilehash: f5f6eb0b6009473dcec017e951cca2f90b6c4d55
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780780"
---
# <a name="msoshade-function"></a><span data-ttu-id="d943a-103">MSOSHADE 函数</span><span class="sxs-lookup"><span data-stu-id="d943a-103">MSOSHADE Function</span></span>

<span data-ttu-id="d943a-104">通过将颜色的发光度降低指定的百分比来修改颜色。</span><span class="sxs-lookup"><span data-stu-id="d943a-104">Modifies the color by decreasing its luminosity by the specified percentage.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="d943a-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="d943a-105">Version Information</span></span>

<span data-ttu-id="d943a-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="d943a-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d943a-107">语法</span><span class="sxs-lookup"><span data-stu-id="d943a-107">Syntax</span></span>

<span data-ttu-id="d943a-108">MSOSHADE (* **颜色** *，* * *-deltaLum* * *)</span><span class="sxs-lookup"><span data-stu-id="d943a-108">MSOSHADE(** *color* **, ** *-deltaLum* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d943a-109">参数</span><span class="sxs-lookup"><span data-stu-id="d943a-109">Parameters</span></span>

|<span data-ttu-id="d943a-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="d943a-110">**Name**</span></span>|<span data-ttu-id="d943a-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d943a-111">**Required/Optional**</span></span>|<span data-ttu-id="d943a-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d943a-112">**Data Type**</span></span>|<span data-ttu-id="d943a-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="d943a-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d943a-114">_color_</span><span class="sxs-lookup"><span data-stu-id="d943a-114">_color_</span></span> <br/> |<span data-ttu-id="d943a-115">必需</span><span class="sxs-lookup"><span data-stu-id="d943a-115">Required</span></span>  <br/> |<span data-ttu-id="d943a-116">**RGB**</span><span class="sxs-lookup"><span data-stu-id="d943a-116">**RGB**</span></span> <br/> |<span data-ttu-id="d943a-117">标准 RGB（红、绿、蓝）颜色值或对颜色的引用。</span><span class="sxs-lookup"><span data-stu-id="d943a-117">The standard RGB (red, green, blue) color value or reference to a color.</span></span>  <br/> |
| <span data-ttu-id="d943a-118">_-deltaLum_</span><span class="sxs-lookup"><span data-stu-id="d943a-118">_-deltaLum_</span></span> <br/> |<span data-ttu-id="d943a-119">必需</span><span class="sxs-lookup"><span data-stu-id="d943a-119">Required</span></span>  <br/> |<span data-ttu-id="d943a-120">**Integer**</span><span class="sxs-lookup"><span data-stu-id="d943a-120">**Integer**</span></span> <br/> |<span data-ttu-id="d943a-121">更改百分比白色 (-100%) 或黑色 （100%)_颜色_值。</span><span class="sxs-lookup"><span data-stu-id="d943a-121">The percentage change toward white (-100%) or black (100%) from the  _color_ value.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d943a-122">说明</span><span class="sxs-lookup"><span data-stu-id="d943a-122">Remarks</span></span>

<span data-ttu-id="d943a-123">越接近_color_值越接近白色或黑色，对底纹由特定 _-deltaLum_值所产生的较小的更改。</span><span class="sxs-lookup"><span data-stu-id="d943a-123">The closer the  _color_ value is to white or black, the smaller the change to the shade that is produced by a specific  _-deltaLum_ value.</span></span> 
  

