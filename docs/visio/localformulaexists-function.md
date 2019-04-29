---
title: LOCALFORMULAEXISTS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60105
localization_priority: Normal
ms.assetid: 2b757c8d-7732-0f9b-c836-ef755dd1c673
description: 指示引用的单元格是否包含局部公式。
ms.openlocfilehash: bd0a5dafecf1bd8dca1567392d880ecaaa3e0374
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433288"
---
# <a name="localformulaexists-function"></a><span data-ttu-id="4c56a-103">LOCALFORMULAEXISTS 函数</span><span class="sxs-lookup"><span data-stu-id="4c56a-103">LOCALFORMULAEXISTS Function</span></span>

<span data-ttu-id="4c56a-104">指示引用的单元格是否包含局部公式。</span><span class="sxs-lookup"><span data-stu-id="4c56a-104">Indicates whether the referenced cell contains a local formula.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="4c56a-105">语法</span><span class="sxs-lookup"><span data-stu-id="4c56a-105">Syntax</span></span>

<span data-ttu-id="4c56a-106">LOCALFORMULAEXISTS (\* \* *cellref* \* \*)</span><span class="sxs-lookup"><span data-stu-id="4c56a-106">LOCALFORMULAEXISTS (\*\* *cellref* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="4c56a-107">参数</span><span class="sxs-lookup"><span data-stu-id="4c56a-107">Parameters</span></span>

|<span data-ttu-id="4c56a-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="4c56a-108">**Name**</span></span>|<span data-ttu-id="4c56a-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4c56a-109">**Required/Optional**</span></span>|<span data-ttu-id="4c56a-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4c56a-110">**Data Type**</span></span>|<span data-ttu-id="4c56a-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="4c56a-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4c56a-112">_cellref_</span><span class="sxs-lookup"><span data-stu-id="4c56a-112">_cellref_</span></span> <br/> |<span data-ttu-id="4c56a-113">必需</span><span class="sxs-lookup"><span data-stu-id="4c56a-113">Required</span></span>  <br/> |<span data-ttu-id="4c56a-114">**String**</span><span class="sxs-lookup"><span data-stu-id="4c56a-114">**String**</span></span> <br/> | <span data-ttu-id="4c56a-115">要检查其中是否存在公式的单元格。</span><span class="sxs-lookup"><span data-stu-id="4c56a-115">The cell that you want to check for the presence of a formula.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="4c56a-116">返回值</span><span class="sxs-lookup"><span data-stu-id="4c56a-116">Return value</span></span>

<span data-ttu-id="4c56a-117">布尔值</span><span class="sxs-lookup"><span data-stu-id="4c56a-117">Boolean</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4c56a-118">备注</span><span class="sxs-lookup"><span data-stu-id="4c56a-118">Remarks</span></span>

<span data-ttu-id="4c56a-119">如果单元格中包含本地公式，则 LOCALFORMULAEXISTS 函数返回 1；如果没有公式或公式是继承而来的，则返回 0（零）。</span><span class="sxs-lookup"><span data-stu-id="4c56a-119">The LOCALFORMULAEXISTS function returns 1 if the cell contains a local formula; if there is no formula, or if the formula is inherited, it returns 0 (zero).</span></span> 
  

