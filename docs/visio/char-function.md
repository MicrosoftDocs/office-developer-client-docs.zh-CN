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
ms.openlocfilehash: 6f1c459892331ec30ad93bbc860fcd038e8f4732
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418188"
---
# <a name="char-function"></a><span data-ttu-id="37888-103">CHAR 函数</span><span class="sxs-lookup"><span data-stu-id="37888-103">CHAR Function</span></span>

<span data-ttu-id="37888-104">返回数字的 ANSI 字符。</span><span class="sxs-lookup"><span data-stu-id="37888-104">Returns the ANSI character for a number.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="37888-105">语法</span><span class="sxs-lookup"><span data-stu-id="37888-105">Syntax</span></span>

<span data-ttu-id="37888-106">CHAR (\*\* *number* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="37888-106">CHAR(\*\* *number* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="37888-107">参数</span><span class="sxs-lookup"><span data-stu-id="37888-107">Parameters</span></span>

|<span data-ttu-id="37888-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="37888-108">**Name**</span></span>|<span data-ttu-id="37888-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="37888-109">**Required/Optional**</span></span>|<span data-ttu-id="37888-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="37888-110">**Data Type**</span></span>|<span data-ttu-id="37888-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="37888-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="37888-112">_number_</span><span class="sxs-lookup"><span data-stu-id="37888-112">_number_</span></span> <br/> |<span data-ttu-id="37888-113">必需</span><span class="sxs-lookup"><span data-stu-id="37888-113">Required</span></span>  <br/> |<span data-ttu-id="37888-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="37888-114">**Number**</span></span> <br/> |<span data-ttu-id="37888-115">要获取其 ANSI 字符的编号。</span><span class="sxs-lookup"><span data-stu-id="37888-115">The number whose ANSI character you want to get.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="37888-116">备注</span><span class="sxs-lookup"><span data-stu-id="37888-116">Remarks</span></span>

<span data-ttu-id="37888-117">结果字符串的长度为一个字符。</span><span class="sxs-lookup"><span data-stu-id="37888-117">The resulting string is one character in length.</span></span> <span data-ttu-id="37888-118">_number 参数_ 必须是介于 1 和 255 之间的整数 (包含) ，否则函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="37888-118">The  _number_ parameter must be an integer between 1 and 255 (inclusive), or the function returns an error.</span></span> 
  
## <a name="example"></a><span data-ttu-id="37888-119">示例</span><span class="sxs-lookup"><span data-stu-id="37888-119">Example</span></span>

<span data-ttu-id="37888-120">CHAR (9) </span><span class="sxs-lookup"><span data-stu-id="37888-120">CHAR(9)</span></span> 
  
<span data-ttu-id="37888-121">返回制表符。</span><span class="sxs-lookup"><span data-stu-id="37888-121">Returns the tab character.</span></span> 
  

