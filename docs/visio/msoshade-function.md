---
title: MSOSHADE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 905cd1cc-14d3-5d37-89c4-f8461a03dda2
description: 通过将颜色的发光度降低指定的百分比来修改颜色。
ms.openlocfilehash: 207893552c7378589d4a648bf29ed88fcfd15224
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414492"
---
# <a name="msoshade-function"></a><span data-ttu-id="23ffb-103">MSOSHADE 函数</span><span class="sxs-lookup"><span data-stu-id="23ffb-103">MSOSHADE Function</span></span>

<span data-ttu-id="23ffb-104">通过将颜色的发光度降低指定的百分比来修改颜色。</span><span class="sxs-lookup"><span data-stu-id="23ffb-104">Modifies the color by decreasing its luminosity by the specified percentage.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="23ffb-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="23ffb-105">Version Information</span></span>

<span data-ttu-id="23ffb-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="23ffb-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="23ffb-107">语法</span><span class="sxs-lookup"><span data-stu-id="23ffb-107">Syntax</span></span>

<span data-ttu-id="23ffb-108">MSOSHADE (\* \* *color* \* \*, \* \* *-deltaLum* \* \*)</span><span class="sxs-lookup"><span data-stu-id="23ffb-108">MSOSHADE(\*\* *color* \*\*, \*\* *-deltaLum* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="23ffb-109">参数</span><span class="sxs-lookup"><span data-stu-id="23ffb-109">Parameters</span></span>

|<span data-ttu-id="23ffb-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="23ffb-110">**Name**</span></span>|<span data-ttu-id="23ffb-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="23ffb-111">**Required/Optional**</span></span>|<span data-ttu-id="23ffb-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="23ffb-112">**Data Type**</span></span>|<span data-ttu-id="23ffb-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="23ffb-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="23ffb-114">_color_</span><span class="sxs-lookup"><span data-stu-id="23ffb-114">_color_</span></span> <br/> |<span data-ttu-id="23ffb-115">必需</span><span class="sxs-lookup"><span data-stu-id="23ffb-115">Required</span></span>  <br/> |<span data-ttu-id="23ffb-116">**RGB**</span><span class="sxs-lookup"><span data-stu-id="23ffb-116">**RGB**</span></span> <br/> |<span data-ttu-id="23ffb-117">标准 RGB（红、绿、蓝）颜色值或对颜色的引用。</span><span class="sxs-lookup"><span data-stu-id="23ffb-117">The standard RGB (red, green, blue) color value or reference to a color.</span></span>  <br/> |
| <span data-ttu-id="23ffb-118">_-deltaLum_</span><span class="sxs-lookup"><span data-stu-id="23ffb-118">_-deltaLum_</span></span> <br/> |<span data-ttu-id="23ffb-119">必需</span><span class="sxs-lookup"><span data-stu-id="23ffb-119">Required</span></span>  <br/> |<span data-ttu-id="23ffb-120">**Integer**</span><span class="sxs-lookup"><span data-stu-id="23ffb-120">**Integer**</span></span> <br/> |<span data-ttu-id="23ffb-121">白色的百分比变化 (-100%)或黑色 (100%)从_颜色_值。</span><span class="sxs-lookup"><span data-stu-id="23ffb-121">The percentage change toward white (-100%) or black (100%) from the  _color_ value.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="23ffb-122">说明</span><span class="sxs-lookup"><span data-stu-id="23ffb-122">Remarks</span></span>

<span data-ttu-id="23ffb-123">_颜色_值越接近白色或黑色, 对由特定_deltaLum_值生成的底纹的更改越小。</span><span class="sxs-lookup"><span data-stu-id="23ffb-123">The closer the  _color_ value is to white or black, the smaller the change to the shade that is produced by a specific  _-deltaLum_ value.</span></span> 
  

