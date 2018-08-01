---
title: MASTERNAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251581
localization_priority: Normal
ms.assetid: 519d79d4-9178-2231-c26d-aa7f31a43412
description: 返回工作表的主控形状名称为 string，或返回字符串任何主控形状，如果表没有主控形状。
ms.openlocfilehash: c1d5891fba0f967cde4a4e9ca58d07f87239f0b0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780702"
---
# <a name="mastername-function"></a><span data-ttu-id="f36bd-103">MASTERNAME 函数</span><span class="sxs-lookup"><span data-stu-id="f36bd-103">MASTERNAME Function</span></span>

<span data-ttu-id="f36bd-104">返回工作表的主控形状名称为 string，或将返回字符串"\<任何主控形状\>"如果表没有主控形状。</span><span class="sxs-lookup"><span data-stu-id="f36bd-104">Returns a sheet's master name as a string, or returns the string "\<no master\>" if the sheet doesn't have a master.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f36bd-105">语法</span><span class="sxs-lookup"><span data-stu-id="f36bd-105">Syntax</span></span>

<span data-ttu-id="f36bd-106">MASTERNAME ([* * *langID_opt* * *])</span><span class="sxs-lookup"><span data-stu-id="f36bd-106">MASTERNAME ([ ** *langID_opt* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f36bd-107">参数</span><span class="sxs-lookup"><span data-stu-id="f36bd-107">Parameters</span></span>

|<span data-ttu-id="f36bd-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="f36bd-108">**Name**</span></span>|<span data-ttu-id="f36bd-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f36bd-109">**Required/Optional**</span></span>|<span data-ttu-id="f36bd-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f36bd-110">**Data Type**</span></span>|<span data-ttu-id="f36bd-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f36bd-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f36bd-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="f36bd-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="f36bd-113">可选</span><span class="sxs-lookup"><span data-stu-id="f36bd-113">Optional</span></span>  <br/> |<span data-ttu-id="f36bd-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="f36bd-114">**Number**</span></span> <br/> |<span data-ttu-id="f36bd-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="f36bd-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="f36bd-118">返回值</span><span class="sxs-lookup"><span data-stu-id="f36bd-118">Return value</span></span>

<span data-ttu-id="f36bd-119">字符串</span><span class="sxs-lookup"><span data-stu-id="f36bd-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f36bd-120">注解</span><span class="sxs-lookup"><span data-stu-id="f36bd-120">Remarks</span></span>

<span data-ttu-id="f36bd-121">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="f36bd-121">If you pass an illegal language code, the local language is used.</span></span> 
  

