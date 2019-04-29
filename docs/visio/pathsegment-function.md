---
title: PATHSEGMENT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 08accf3b-93ac-9dd3-85ce-34ad42e79a4f
description: 返回一个从1开始的段落编号, 位于指定的百分比标记处沿指定的路径。
ms.openlocfilehash: c4dfc4d33de1a9c1a03ef14d76103b4de0f28bc7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432483"
---
# <a name="pathsegment-function"></a><span data-ttu-id="01549-103">PATHSEGMENT 函数</span><span class="sxs-lookup"><span data-stu-id="01549-103">PATHSEGMENT Function</span></span>

<span data-ttu-id="01549-104">返回一个从1开始的段落编号, 位于指定的百分比标记处沿指定的路径。</span><span class="sxs-lookup"><span data-stu-id="01549-104">Returns the 1-based segment number at the specified percentage mark along the specified path.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="01549-105">语法</span><span class="sxs-lookup"><span data-stu-id="01549-105">Syntax</span></span>

<span data-ttu-id="01549-106">PATHSEGMENT (\* \* *section* \* *、* **差旅** \*)</span><span class="sxs-lookup"><span data-stu-id="01549-106">PATHSEGMENT(\*\* *section* \*\*, \*\* *travel* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="01549-107">参数</span><span class="sxs-lookup"><span data-stu-id="01549-107">Parameters</span></span>

|<span data-ttu-id="01549-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="01549-108">**Name**</span></span>|<span data-ttu-id="01549-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="01549-109">**Required/Optional**</span></span>|<span data-ttu-id="01549-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="01549-110">**Data Type**</span></span>|<span data-ttu-id="01549-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="01549-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="01549-112">_section_</span><span class="sxs-lookup"><span data-stu-id="01549-112">_section_</span></span> <br/> |<span data-ttu-id="01549-113">必需</span><span class="sxs-lookup"><span data-stu-id="01549-113">Required</span></span>  <br/> |<span data-ttu-id="01549-114">**String**</span><span class="sxs-lookup"><span data-stu-id="01549-114">**String**</span></span> <br/> |<span data-ttu-id="01549-115">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="01549-115">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="01549-116">_传输_</span><span class="sxs-lookup"><span data-stu-id="01549-116">_travel_</span></span> <br/> |<span data-ttu-id="01549-117">必需</span><span class="sxs-lookup"><span data-stu-id="01549-117">Required</span></span>  <br/> |<span data-ttu-id="01549-118">**Double**</span><span class="sxs-lookup"><span data-stu-id="01549-118">**Double**</span></span> <br/> |<span data-ttu-id="01549-119">从起点到终点经过的路径的百分比。</span><span class="sxs-lookup"><span data-stu-id="01549-119">The percentage of the path traversed, from the begin point to the end point.</span></span> <span data-ttu-id="01549-120">必须为介于 0 和 1 之间的值。</span><span class="sxs-lookup"><span data-stu-id="01549-120">Must be between 0 and 1.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="01549-121">返回值</span><span class="sxs-lookup"><span data-stu-id="01549-121">Return value</span></span>

<span data-ttu-id="01549-122">Integer</span><span class="sxs-lookup"><span data-stu-id="01549-122">Integer</span></span>
  

