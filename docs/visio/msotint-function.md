---
title: MSOTINT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1bae0af9-229d-e114-4feb-bf6d7a7d8b08
description: 通过将颜色的发光度增加指定的百分比来修改颜色。
ms.openlocfilehash: d63b90d0cd6fcb35e23a8efa4ca9e13e2838bc21
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406421"
---
# <a name="msotint-function"></a><span data-ttu-id="6dcb4-103">MSOTINT 函数</span><span class="sxs-lookup"><span data-stu-id="6dcb4-103">MSOTINT Function</span></span>

<span data-ttu-id="6dcb4-104">通过将颜色的发光度增加指定的百分比来修改颜色。</span><span class="sxs-lookup"><span data-stu-id="6dcb4-104">Modifies the color by increasing its luminosity by the specified percentage.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="6dcb4-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="6dcb4-105">Version Information</span></span>

<span data-ttu-id="6dcb4-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="6dcb4-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="6dcb4-107">语法</span><span class="sxs-lookup"><span data-stu-id="6dcb4-107">Syntax</span></span>

<span data-ttu-id="6dcb4-108">MSOTINT (\*\* *color* \*\*， \*\* *deltaLum* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="6dcb4-108">MSOTINT(\*\* *color* \*\*, \*\* *deltaLum* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="6dcb4-109">参数</span><span class="sxs-lookup"><span data-stu-id="6dcb4-109">Parameters</span></span>

|<span data-ttu-id="6dcb4-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="6dcb4-110">**Name**</span></span>|<span data-ttu-id="6dcb4-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="6dcb4-111">**Required/Optional**</span></span>|<span data-ttu-id="6dcb4-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="6dcb4-112">**Data Type**</span></span>|<span data-ttu-id="6dcb4-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="6dcb4-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6dcb4-114">_color_</span><span class="sxs-lookup"><span data-stu-id="6dcb4-114">_color_</span></span> <br/> |<span data-ttu-id="6dcb4-115">必需</span><span class="sxs-lookup"><span data-stu-id="6dcb4-115">Required</span></span>  <br/> |<span data-ttu-id="6dcb4-116">**RGB**</span><span class="sxs-lookup"><span data-stu-id="6dcb4-116">**RGB**</span></span> <br/> |<span data-ttu-id="6dcb4-117">标准 RGB（红、绿、蓝）颜色值或对颜色的引用。</span><span class="sxs-lookup"><span data-stu-id="6dcb4-117">The standard RGB (red, green, blue) color value or reference to a color.</span></span>  <br/> |
| <span data-ttu-id="6dcb4-118">_deltaLum_</span><span class="sxs-lookup"><span data-stu-id="6dcb4-118">_deltaLum_</span></span> <br/> |<span data-ttu-id="6dcb4-119">必需</span><span class="sxs-lookup"><span data-stu-id="6dcb4-119">Required</span></span>  <br/> |<span data-ttu-id="6dcb4-120">**Integer**</span><span class="sxs-lookup"><span data-stu-id="6dcb4-120">**Integer**</span></span> <br/> |<span data-ttu-id="6dcb4-121">从颜色值 (到 100%) 或黑色 (100%) 的百  _分比_ 变化。</span><span class="sxs-lookup"><span data-stu-id="6dcb4-121">The percentage change toward white (-100%) or black (100%) from the  _color_ value.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6dcb4-122">备注</span><span class="sxs-lookup"><span data-stu-id="6dcb4-122">Remarks</span></span>

<span data-ttu-id="6dcb4-123">颜色值  _越_ 接近白色或黑色，由特定  _deltaLum_ 值产生的淡色变化越小。</span><span class="sxs-lookup"><span data-stu-id="6dcb4-123">The closer the  _color_ value is to white or black, the smaller the change to the tint that is produced by a specific  _deltaLum_ value.</span></span> 
  

