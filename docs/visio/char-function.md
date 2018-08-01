---
title: CHAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251406
localization_priority: Normal
ms.assetid: 0803d5d3-d804-5ffe-604d-661b35d1fc01
description: 返回数字的 ANSI 字符。
ms.openlocfilehash: 209614d20dd663ed2f7ca030c25500d43f925c95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779856"
---
# <a name="char-function"></a><span data-ttu-id="55e60-103">CHAR 函数</span><span class="sxs-lookup"><span data-stu-id="55e60-103">CHAR Function</span></span>

<span data-ttu-id="55e60-104">返回数字的 ANSI 字符。</span><span class="sxs-lookup"><span data-stu-id="55e60-104">Returns the ANSI character for a number.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="55e60-105">语法</span><span class="sxs-lookup"><span data-stu-id="55e60-105">Syntax</span></span>

<span data-ttu-id="55e60-106">CHAR (* **数量** *)</span><span class="sxs-lookup"><span data-stu-id="55e60-106">CHAR(** *number* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="55e60-107">参数</span><span class="sxs-lookup"><span data-stu-id="55e60-107">Parameters</span></span>

|<span data-ttu-id="55e60-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="55e60-108">**Name**</span></span>|<span data-ttu-id="55e60-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="55e60-109">**Required/Optional**</span></span>|<span data-ttu-id="55e60-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="55e60-110">**Data Type**</span></span>|<span data-ttu-id="55e60-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="55e60-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="55e60-112">_number_</span><span class="sxs-lookup"><span data-stu-id="55e60-112">_number_</span></span> <br/> |<span data-ttu-id="55e60-113">必需</span><span class="sxs-lookup"><span data-stu-id="55e60-113">Required</span></span>  <br/> |<span data-ttu-id="55e60-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="55e60-114">**Number**</span></span> <br/> |<span data-ttu-id="55e60-115">要获取其 ANSI 字符数。</span><span class="sxs-lookup"><span data-stu-id="55e60-115">The number whose ANSI character you want to get.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="55e60-116">说明</span><span class="sxs-lookup"><span data-stu-id="55e60-116">Remarks</span></span>

<span data-ttu-id="55e60-117">结果字符串是一个字符的长度。</span><span class="sxs-lookup"><span data-stu-id="55e60-117">The resulting string is one character in length.</span></span> <span data-ttu-id="55e60-118">_号码_参数必须是介于 1 和 255 之间 （含） 的整数或函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="55e60-118">The  _number_ parameter must be an integer between 1 and 255 (inclusive), or the function returns an error.</span></span> 
  
## <a name="example"></a><span data-ttu-id="55e60-119">示例</span><span class="sxs-lookup"><span data-stu-id="55e60-119">Example</span></span>

<span data-ttu-id="55e60-120">CHAR(9)</span><span class="sxs-lookup"><span data-stu-id="55e60-120">CHAR(9)</span></span> 
  
<span data-ttu-id="55e60-121">返回制表符。</span><span class="sxs-lookup"><span data-stu-id="55e60-121">Returns the tab character.</span></span> 
  

