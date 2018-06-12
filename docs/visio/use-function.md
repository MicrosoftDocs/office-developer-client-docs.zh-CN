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
description: 适用的线型、 填充图案或线端调用到形状时处于 LinePattern、 FillPattern、 BeginArrow 或 EndArrow 单元格的名称。
ms.openlocfilehash: 0b6668e57a8f997a69fece51cbc5bd1b1574a576
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781601"
---
# <a name="use-function"></a><span data-ttu-id="4022d-103">USE 函数</span><span class="sxs-lookup"><span data-stu-id="4022d-103">USE Function</span></span>

<span data-ttu-id="4022d-104">适用的线型、 填充图案或线端调用到形状时处于 LinePattern、 FillPattern、 BeginArrow 或 EndArrow 单元格的_名称_。</span><span class="sxs-lookup"><span data-stu-id="4022d-104">Applies the line pattern, fill pattern, or line end called  _name_ to the shape when placed in the LinePattern, FillPattern, BeginArrow, or EndArrow cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="4022d-105">语法</span><span class="sxs-lookup"><span data-stu-id="4022d-105">Syntax</span></span>

<span data-ttu-id="4022d-106">使用 ("* **名称** *")</span><span class="sxs-lookup"><span data-stu-id="4022d-106">USE(" ** *name* ** ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="4022d-107">参数</span><span class="sxs-lookup"><span data-stu-id="4022d-107">Parameters</span></span>

|<span data-ttu-id="4022d-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="4022d-108">**Name**</span></span>|<span data-ttu-id="4022d-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4022d-109">**Required/Optional**</span></span>|<span data-ttu-id="4022d-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4022d-110">**Data Type**</span></span>|<span data-ttu-id="4022d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="4022d-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4022d-112">_name_</span><span class="sxs-lookup"><span data-stu-id="4022d-112">_name_</span></span> <br/> |<span data-ttu-id="4022d-113">必需</span><span class="sxs-lookup"><span data-stu-id="4022d-113">Required</span></span>  <br/> |<span data-ttu-id="4022d-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="4022d-114">**String**</span></span> <br/> |<span data-ttu-id="4022d-115">是有效主控形状名称的任何字符串。</span><span class="sxs-lookup"><span data-stu-id="4022d-115">Any string that is a valid master name.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="4022d-116">返回值</span><span class="sxs-lookup"><span data-stu-id="4022d-116">Return value</span></span>

<span data-ttu-id="4022d-117">Number</span><span class="sxs-lookup"><span data-stu-id="4022d-117">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4022d-118">注解</span><span class="sxs-lookup"><span data-stu-id="4022d-118">Remarks</span></span>

<span data-ttu-id="4022d-119">如果文档的文档模具上存在名为_name_的主控形状，如线型、 填充图案、 开始箭头或结束箭头应用模式。</span><span class="sxs-lookup"><span data-stu-id="4022d-119">If a master named  _name_ is present on the document stencil of the document, the pattern is applied as a line pattern, fill pattern, begin arrow, or end arrow.</span></span> 
  
<span data-ttu-id="4022d-120">此函数始终返回 254。</span><span class="sxs-lookup"><span data-stu-id="4022d-120">This function always returns 254.</span></span>
  
## <a name="example"></a><span data-ttu-id="4022d-121">示例</span><span class="sxs-lookup"><span data-stu-id="4022d-121">Example</span></span>

<span data-ttu-id="4022d-122">USE("Railroad Tracks")</span><span class="sxs-lookup"><span data-stu-id="4022d-122">USE("Railroad Tracks")</span></span> 
  
<span data-ttu-id="4022d-123">通过对包含该公式的形状应用名为 Railroad Tracks 的主控形状图案，设置该形状的格式。</span><span class="sxs-lookup"><span data-stu-id="4022d-123">Formats the shape by applying the master pattern named Railroad Tracks to the shape containing the formula.</span></span> 
  

