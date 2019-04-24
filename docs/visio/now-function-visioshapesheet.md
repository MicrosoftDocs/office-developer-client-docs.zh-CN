---
title: NOW 函数 (VisioShapeSheet)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251470
localization_priority: Normal
ms.assetid: 96cac1f6-cc17-466f-23d8-a9006e7de05f
description: 返回当前日期和时间值。
ms.openlocfilehash: 9e28f51b0e1d1c09a70e54e432a865968c721940
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340990"
---
# <a name="now-function-visioshapesheet"></a><span data-ttu-id="f0ed3-103">NOW 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="f0ed3-103">NOW Function (VisioShapeSheet)</span></span>

<span data-ttu-id="f0ed3-104">返回当前日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="f0ed3-104">Returns the current date and time value.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f0ed3-105">语法</span><span class="sxs-lookup"><span data-stu-id="f0ed3-105">Syntax</span></span>

<span data-ttu-id="f0ed3-106">NOW ( )</span><span class="sxs-lookup"><span data-stu-id="f0ed3-106">NOW ( )</span></span>
  
### <a name="return-value"></a><span data-ttu-id="f0ed3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f0ed3-107">Return value</span></span>

<span data-ttu-id="f0ed3-108">Datetime</span><span class="sxs-lookup"><span data-stu-id="f0ed3-108">Datetime</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f0ed3-109">注解</span><span class="sxs-lookup"><span data-stu-id="f0ed3-109">Remarks</span></span>

<span data-ttu-id="f0ed3-110">NOW 每分钟自动重新计算。</span><span class="sxs-lookup"><span data-stu-id="f0ed3-110">NOW is automatically recalculated every minute.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="f0ed3-111">示例 1</span><span class="sxs-lookup"><span data-stu-id="f0ed3-111">Example 1</span></span>

<span data-ttu-id="f0ed3-112">NOW( )</span><span class="sxs-lookup"><span data-stu-id="f0ed3-112">NOW( )</span></span>
  
<span data-ttu-id="f0ed3-113">返回当前的日期和时间，如 9/27/2010 12:03:30 PM。</span><span class="sxs-lookup"><span data-stu-id="f0ed3-113">Returns the current date and time, such as 9/27/2010 12:03:30 PM.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="f0ed3-114">示例 2</span><span class="sxs-lookup"><span data-stu-id="f0ed3-114">Example 2</span></span>

<span data-ttu-id="f0ed3-115">FORMAT(NOW(),"dd MMM., yyyy hh:mm")</span><span class="sxs-lookup"><span data-stu-id="f0ed3-115">FORMAT(NOW(),"dd MMM., yyyy hh:mm")</span></span>
  
<span data-ttu-id="f0ed3-116">以“27 Sep., 2010 12:03”格式返回当前的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="f0ed3-116">Returns the current date and time formatted as 27 Sep., 2010 12:03.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="f0ed3-117">示例 3</span><span class="sxs-lookup"><span data-stu-id="f0ed3-117">Example 3</span></span>

<span data-ttu-id="f0ed3-118">NOW () + 2EW。</span><span class="sxs-lookup"><span data-stu-id="f0ed3-118">NOW()+2EW.</span></span>
  
<span data-ttu-id="f0ed3-119">返回当前的日期和时间加上两周时间后的结果，如 10/11/10 12:03:30 PM。</span><span class="sxs-lookup"><span data-stu-id="f0ed3-119">Returns the current date and time plus two elapsed weeks, such as 10/11/10 12:03:30 PM.</span></span>
  

