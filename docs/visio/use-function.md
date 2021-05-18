---
title: USE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251510
localization_priority: Normal
ms.assetid: 410c4187-21f3-d959-750e-9dc6095fba9a
description: 当置于 LinePattern、FillPattern、BeginArrow 或 EndArrow 单元格中时，将线条图案、填充图案或行尾名称应用于形状。
ms.openlocfilehash: ddd15c1c127fafa1a230545d544c74956f5c0262
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422822"
---
# <a name="use-function"></a><span data-ttu-id="7bb20-103">USE 函数</span><span class="sxs-lookup"><span data-stu-id="7bb20-103">USE Function</span></span>

<span data-ttu-id="7bb20-104">当置于 LinePattern、FillPattern、BeginArrow 或 EndArrow 单元格中时，将线条图案、填充图案或行尾名称应用于形状。 </span><span class="sxs-lookup"><span data-stu-id="7bb20-104">Applies the line pattern, fill pattern, or line end called  _name_ to the shape when placed in the LinePattern, FillPattern, BeginArrow, or EndArrow cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="7bb20-105">语法</span><span class="sxs-lookup"><span data-stu-id="7bb20-105">Syntax</span></span>

<span data-ttu-id="7bb20-106">USE (" \*\* *name* \*\* ") </span><span class="sxs-lookup"><span data-stu-id="7bb20-106">USE(" \*\* *name* \*\* ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7bb20-107">参数</span><span class="sxs-lookup"><span data-stu-id="7bb20-107">Parameters</span></span>

|<span data-ttu-id="7bb20-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="7bb20-108">**Name**</span></span>|<span data-ttu-id="7bb20-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7bb20-109">**Required/Optional**</span></span>|<span data-ttu-id="7bb20-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7bb20-110">**Data Type**</span></span>|<span data-ttu-id="7bb20-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="7bb20-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7bb20-112">_name_</span><span class="sxs-lookup"><span data-stu-id="7bb20-112">_name_</span></span> <br/> |<span data-ttu-id="7bb20-113">必需</span><span class="sxs-lookup"><span data-stu-id="7bb20-113">Required</span></span>  <br/> |<span data-ttu-id="7bb20-114">**String**</span><span class="sxs-lookup"><span data-stu-id="7bb20-114">**String**</span></span> <br/> |<span data-ttu-id="7bb20-115">是有效主控形状名称的任何字符串。</span><span class="sxs-lookup"><span data-stu-id="7bb20-115">Any string that is a valid master name.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="7bb20-116">返回值</span><span class="sxs-lookup"><span data-stu-id="7bb20-116">Return value</span></span>

<span data-ttu-id="7bb20-117">帐号</span><span class="sxs-lookup"><span data-stu-id="7bb20-117">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7bb20-118">备注</span><span class="sxs-lookup"><span data-stu-id="7bb20-118">Remarks</span></span>

<span data-ttu-id="7bb20-119">如果  _文档的文档模具_ 上存在名为"名称"的主控形状，则应用该图案作为线型、填充图案、开始箭头或结束箭头。</span><span class="sxs-lookup"><span data-stu-id="7bb20-119">If a master named  _name_ is present on the document stencil of the document, the pattern is applied as a line pattern, fill pattern, begin arrow, or end arrow.</span></span> 
  
<span data-ttu-id="7bb20-120">此函数始终返回 254。</span><span class="sxs-lookup"><span data-stu-id="7bb20-120">This function always returns 254.</span></span>
  
## <a name="example"></a><span data-ttu-id="7bb20-121">示例</span><span class="sxs-lookup"><span data-stu-id="7bb20-121">Example</span></span>

<span data-ttu-id="7bb20-122">USE("Railroad Tracks")</span><span class="sxs-lookup"><span data-stu-id="7bb20-122">USE("Railroad Tracks")</span></span> 
  
<span data-ttu-id="7bb20-123">通过对包含该公式的形状应用名为 Railroad Tracks 的主控形状图案，设置该形状的格式。</span><span class="sxs-lookup"><span data-stu-id="7bb20-123">Formats the shape by applying the master pattern named Railroad Tracks to the shape containing the formula.</span></span> 
  

