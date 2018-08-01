---
title: PATHSEGMENT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 08accf3b-93ac-9dd3-85ce-34ad42e79a4f
description: 返回在指定路径指定的百分比标记处 1 开始的线段数。
ms.openlocfilehash: b25f43ffa3c719cfc5ffbd1e417f2da9640e483b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780855"
---
# <a name="pathsegment-function"></a><span data-ttu-id="43852-103">PATHSEGMENT 函数</span><span class="sxs-lookup"><span data-stu-id="43852-103">PATHSEGMENT Function</span></span>

<span data-ttu-id="43852-104">返回在指定路径指定的百分比标记处 1 开始的线段数。</span><span class="sxs-lookup"><span data-stu-id="43852-104">Returns the 1-based segment number at the specified percentage mark along the specified path.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="43852-105">语法</span><span class="sxs-lookup"><span data-stu-id="43852-105">Syntax</span></span>

<span data-ttu-id="43852-106">PATHSEGMENT (* **部分** *，* **差旅** *)</span><span class="sxs-lookup"><span data-stu-id="43852-106">PATHSEGMENT(** *section* **, ** *travel* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="43852-107">参数</span><span class="sxs-lookup"><span data-stu-id="43852-107">Parameters</span></span>

|<span data-ttu-id="43852-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="43852-108">**Name**</span></span>|<span data-ttu-id="43852-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="43852-109">**Required/Optional**</span></span>|<span data-ttu-id="43852-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="43852-110">**Data Type**</span></span>|<span data-ttu-id="43852-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="43852-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="43852-112">_section_</span><span class="sxs-lookup"><span data-stu-id="43852-112">_section_</span></span> <br/> |<span data-ttu-id="43852-113">必需</span><span class="sxs-lookup"><span data-stu-id="43852-113">Required</span></span>  <br/> |<span data-ttu-id="43852-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="43852-114">**String**</span></span> <br/> |<span data-ttu-id="43852-115">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="43852-115">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="43852-116">_出差_</span><span class="sxs-lookup"><span data-stu-id="43852-116">_travel_</span></span> <br/> |<span data-ttu-id="43852-117">必需</span><span class="sxs-lookup"><span data-stu-id="43852-117">Required</span></span>  <br/> |<span data-ttu-id="43852-118">**Double**</span><span class="sxs-lookup"><span data-stu-id="43852-118">**Double**</span></span> <br/> |<span data-ttu-id="43852-p101">从起点到终点经过的路径的百分比。必须为介于 0 和 1 之间的值。</span><span class="sxs-lookup"><span data-stu-id="43852-p101">The percentage of the path traversed, from the begin point to the end point. Must be between 0 and 1.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="43852-121">返回值</span><span class="sxs-lookup"><span data-stu-id="43852-121">Return value</span></span>

<span data-ttu-id="43852-122">Integer</span><span class="sxs-lookup"><span data-stu-id="43852-122">Integer</span></span>
  

