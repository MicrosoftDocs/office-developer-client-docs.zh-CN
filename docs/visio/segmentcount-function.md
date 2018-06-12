---
title: SEGMENTCOUNT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 792ec0e4-4a48-136b-904c-fe269e355070
description: 返回组成路径的线段数。
ms.openlocfilehash: 93a77d9085e6900f502a75401847ad685d25effd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781245"
---
# <a name="segmentcount-function"></a><span data-ttu-id="8aed4-103">SEGMENTCOUNT 函数</span><span class="sxs-lookup"><span data-stu-id="8aed4-103">SEGMENTCOUNT Function</span></span>

<span data-ttu-id="8aed4-104">返回组成路径的线段数。</span><span class="sxs-lookup"><span data-stu-id="8aed4-104">Returns the number of line segments that make up the path.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8aed4-105">语法</span><span class="sxs-lookup"><span data-stu-id="8aed4-105">Syntax</span></span>

<span data-ttu-id="8aed4-106">SEGMENTCOUNT (* * *pathRef* * *)</span><span class="sxs-lookup"><span data-stu-id="8aed4-106">SEGMENTCOUNT(** *pathRef* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8aed4-107">参数</span><span class="sxs-lookup"><span data-stu-id="8aed4-107">Parameters</span></span>

|<span data-ttu-id="8aed4-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="8aed4-108">**Name**</span></span>|<span data-ttu-id="8aed4-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8aed4-109">**Required/Optional**</span></span>|<span data-ttu-id="8aed4-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8aed4-110">**Data Type**</span></span>|<span data-ttu-id="8aed4-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="8aed4-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8aed4-112">_pathRef_</span><span class="sxs-lookup"><span data-stu-id="8aed4-112">_pathRef_</span></span> <br/> |<span data-ttu-id="8aed4-113">必需</span><span class="sxs-lookup"><span data-stu-id="8aed4-113">Required</span></span>  <br/> |<span data-ttu-id="8aed4-114">**Integer**</span><span class="sxs-lookup"><span data-stu-id="8aed4-114">**Integer**</span></span> <br/> |<span data-ttu-id="8aed4-115">代表路径的 Geometry 节，通过对 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="8aed4-115">The Geometry section that represents the path, specified by a reference to Path cell (for example, Geometry1.Path).</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="8aed4-116">返回值</span><span class="sxs-lookup"><span data-stu-id="8aed4-116">Return value</span></span>

<span data-ttu-id="8aed4-117">Integer</span><span class="sxs-lookup"><span data-stu-id="8aed4-117">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8aed4-118">注解</span><span class="sxs-lookup"><span data-stu-id="8aed4-118">Remarks</span></span>

<span data-ttu-id="8aed4-119">返回的线段总数中不包含跨线。</span><span class="sxs-lookup"><span data-stu-id="8aed4-119">Line jumps are not included in the total number of segments returned.</span></span>
  

