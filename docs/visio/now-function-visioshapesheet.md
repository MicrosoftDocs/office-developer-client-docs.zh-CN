---
title: NOW Function (VisioShapeSheet)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251470
localization_priority: Normal
ms.assetid: 96cac1f6-cc17-466f-23d8-a9006e7de05f
description: 返回当前的日期和时间值。
ms.openlocfilehash: 387425369b1f1d6313502b3679a72cfd23038834
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780823"
---
# <a name="now-function-visioshapesheet"></a><span data-ttu-id="a48b2-103">NOW Function (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="a48b2-103">NOW Function (VisioShapeSheet)</span></span>

<span data-ttu-id="a48b2-104">返回当前的日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="a48b2-104">Returns the current date and time value.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="a48b2-105">语法</span><span class="sxs-lookup"><span data-stu-id="a48b2-105">Syntax</span></span>

<span data-ttu-id="a48b2-106">NOW ( )</span><span class="sxs-lookup"><span data-stu-id="a48b2-106">NOW ( )</span></span>
  
### <a name="return-value"></a><span data-ttu-id="a48b2-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a48b2-107">Return value</span></span>

<span data-ttu-id="a48b2-108">Datetime</span><span class="sxs-lookup"><span data-stu-id="a48b2-108">Datetime</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a48b2-109">注解</span><span class="sxs-lookup"><span data-stu-id="a48b2-109">Remarks</span></span>

<span data-ttu-id="a48b2-110">NOW 每分钟自动重新计算。</span><span class="sxs-lookup"><span data-stu-id="a48b2-110">NOW is automatically recalculated every minute.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="a48b2-111">示例 1</span><span class="sxs-lookup"><span data-stu-id="a48b2-111">Example 1</span></span>

<span data-ttu-id="a48b2-112">NOW( )</span><span class="sxs-lookup"><span data-stu-id="a48b2-112">NOW( )</span></span>
  
<span data-ttu-id="a48b2-113">返回当前的日期和时间，如 9/27/2010 12:03:30 PM。</span><span class="sxs-lookup"><span data-stu-id="a48b2-113">Returns the current date and time, such as 9/27/2010 12:03:30 PM.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="a48b2-114">示例 2</span><span class="sxs-lookup"><span data-stu-id="a48b2-114">Example 2</span></span>

<span data-ttu-id="a48b2-115">FORMAT(NOW(),"dd MMM., yyyy hh:mm")</span><span class="sxs-lookup"><span data-stu-id="a48b2-115">FORMAT(NOW(),"dd MMM., yyyy hh:mm")</span></span>
  
<span data-ttu-id="a48b2-116">以“27 Sep., 2010 12:03”格式返回当前的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a48b2-116">Returns the current date and time formatted as 27 Sep., 2010 12:03.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="a48b2-117">示例 3</span><span class="sxs-lookup"><span data-stu-id="a48b2-117">Example 3</span></span>

<span data-ttu-id="a48b2-118">NOW()+2EW.</span><span class="sxs-lookup"><span data-stu-id="a48b2-118">NOW()+2EW.</span></span>
  
<span data-ttu-id="a48b2-119">返回当前的日期和时间加上两周时间后的结果，如 10/11/10 12:03:30 PM。</span><span class="sxs-lookup"><span data-stu-id="a48b2-119">Returns the current date and time plus two elapsed weeks, such as 10/11/10 12:03:30 PM.</span></span>
  

