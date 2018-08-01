---
title: NEARESTPOINTONPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 539bf79a-df09-2048-2aba-8c863dd26fc2
description: 返回距指定坐标最近的点沿路径的距离百分比，返回的值介于 0 到 1 之间。
ms.openlocfilehash: d9e9b890033526fec99f04cee30ae93578487652
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780781"
---
# <a name="nearestpointonpath-function"></a><span data-ttu-id="d2a52-103">NEARESTPOINTONPATH 函数</span><span class="sxs-lookup"><span data-stu-id="d2a52-103">NEARESTPOINTONPATH Function</span></span>

<span data-ttu-id="d2a52-104">返回距指定坐标最近的点沿路径的距离百分比，返回的值介于 0 到 1 之间。</span><span class="sxs-lookup"><span data-stu-id="d2a52-104">Returns the percentage of the distance along the path of the point that is nearest to the specified coordinates, as a value between 0 and 1.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="d2a52-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="d2a52-105">Version Information</span></span>

<span data-ttu-id="d2a52-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="d2a52-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d2a52-107">语法</span><span class="sxs-lookup"><span data-stu-id="d2a52-107">Syntax</span></span>

<span data-ttu-id="d2a52-108">NEARESTPOINTONPATH (* **部分** *，* * *x* * *，* * *y* * *)</span><span class="sxs-lookup"><span data-stu-id="d2a52-108">NEARESTPOINTONPATH(** *section* **, ** *x* **, ** *y* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d2a52-109">参数</span><span class="sxs-lookup"><span data-stu-id="d2a52-109">Parameters</span></span>

|<span data-ttu-id="d2a52-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="d2a52-110">**Name**</span></span>|<span data-ttu-id="d2a52-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d2a52-111">**Required/Optional**</span></span>|<span data-ttu-id="d2a52-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d2a52-112">**Data Type**</span></span>|<span data-ttu-id="d2a52-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="d2a52-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d2a52-114">_section_</span><span class="sxs-lookup"><span data-stu-id="d2a52-114">_section_</span></span> <br/> |<span data-ttu-id="d2a52-115">必需</span><span class="sxs-lookup"><span data-stu-id="d2a52-115">Required</span></span>  <br/> |<span data-ttu-id="d2a52-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="d2a52-116">**String**</span></span> <br/> |<span data-ttu-id="d2a52-117">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="d2a52-117">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="d2a52-118">_x_</span><span class="sxs-lookup"><span data-stu-id="d2a52-118">_x_</span></span> <br/> |<span data-ttu-id="d2a52-119">必需</span><span class="sxs-lookup"><span data-stu-id="d2a52-119">Required</span></span>  <br/> |<span data-ttu-id="d2a52-120">**Double**</span><span class="sxs-lookup"><span data-stu-id="d2a52-120">**Double**</span></span> <br/> |<span data-ttu-id="d2a52-121">_X_-指定点的坐标。</span><span class="sxs-lookup"><span data-stu-id="d2a52-121">The  _x_-coordinate of the specified point.</span></span>  <br/> |
| <span data-ttu-id="d2a52-122">_y_</span><span class="sxs-lookup"><span data-stu-id="d2a52-122">_y_</span></span> <br/> |<span data-ttu-id="d2a52-123">必需</span><span class="sxs-lookup"><span data-stu-id="d2a52-123">Required</span></span>  <br/> |<span data-ttu-id="d2a52-124">**Double**</span><span class="sxs-lookup"><span data-stu-id="d2a52-124">**Double**</span></span> <br/> |<span data-ttu-id="d2a52-125">_Y_-指定点的坐标。</span><span class="sxs-lookup"><span data-stu-id="d2a52-125">The  _y_-coordinate of the specified point.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="d2a52-126">返回值</span><span class="sxs-lookup"><span data-stu-id="d2a52-126">Return value</span></span>

 <span data-ttu-id="d2a52-127">**Double**</span><span class="sxs-lookup"><span data-stu-id="d2a52-127">**Double**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d2a52-128">注解</span><span class="sxs-lookup"><span data-stu-id="d2a52-128">Remarks</span></span>

<span data-ttu-id="d2a52-129">如果_section_不存在，Microsoft Visio 将返回 #REF ！。</span><span class="sxs-lookup"><span data-stu-id="d2a52-129">If  _section_ does not exist, Microsoft Visio returns #REF!.</span></span> 
  

