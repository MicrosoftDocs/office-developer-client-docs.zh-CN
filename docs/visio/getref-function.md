---
title: GETREF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251884
localization_priority: Normal
ms.assetid: 25c9f817-d22b-28c9-1339-dc9f27d0dd41
description: 引用单元格, 并且在引用的单元格发生更改时不重新计算公式。
ms.openlocfilehash: 38f3c8b4f34ed2b3d3711be5faed6b0d317e907a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424327"
---
# <a name="getref-function"></a><span data-ttu-id="3d6f1-103">GETREF 函数</span><span class="sxs-lookup"><span data-stu-id="3d6f1-103">GETREF Function</span></span>

<span data-ttu-id="3d6f1-104">引用单元格, 并且在引用的单元格发生更改时不重新计算公式。</span><span class="sxs-lookup"><span data-stu-id="3d6f1-104">References a cell and doesn't recalculate the formula when the referenced cell changes.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3d6f1-105">语法</span><span class="sxs-lookup"><span data-stu-id="3d6f1-105">Syntax</span></span>

<span data-ttu-id="3d6f1-106">GETREF (\* \* *cellname* \* \*)</span><span class="sxs-lookup"><span data-stu-id="3d6f1-106">GETREF(\*\* *cellname* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="3d6f1-107">参数</span><span class="sxs-lookup"><span data-stu-id="3d6f1-107">Parameters</span></span>

|<span data-ttu-id="3d6f1-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="3d6f1-108">**Name**</span></span>|<span data-ttu-id="3d6f1-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="3d6f1-109">**Required/Optional**</span></span>|<span data-ttu-id="3d6f1-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3d6f1-110">**Data Type**</span></span>|<span data-ttu-id="3d6f1-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="3d6f1-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3d6f1-112">_cellname_</span><span class="sxs-lookup"><span data-stu-id="3d6f1-112">_cellname_</span></span> <br/> |<span data-ttu-id="3d6f1-113">必需</span><span class="sxs-lookup"><span data-stu-id="3d6f1-113">Required</span></span>  <br/> |<span data-ttu-id="3d6f1-114">**String**</span><span class="sxs-lookup"><span data-stu-id="3d6f1-114">**String**</span></span> <br/> |<span data-ttu-id="3d6f1-115">要获取其引用的单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="3d6f1-115">The name of the cell to get a reference to.</span></span>  <br/> |
   
## <a name="example"></a><span data-ttu-id="3d6f1-116">示例</span><span class="sxs-lookup"><span data-stu-id="3d6f1-116">Example</span></span>

<span data-ttu-id="3d6f1-117">SETF (GETREF (PinX), 5.1)</span><span class="sxs-lookup"><span data-stu-id="3d6f1-117">SETF(GETREF(PinX),5.1)</span></span> 
  
<span data-ttu-id="3d6f1-118">将 PinX 单元格的公式设置为 5.1。</span><span class="sxs-lookup"><span data-stu-id="3d6f1-118">Sets the formula of the PinX cell to 5.1.</span></span> 
  

