---
title: FtSubFt
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtSubFt
api_type:
- COM
ms.assetid: 6619fc41-5518-44ce-85c1-6b0077ed5cb9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: edd789a586adc71289ff821aa7cf7a33f79fb738
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408416"
---
# <a name="ftsubft"></a><span data-ttu-id="206ae-103">FtSubFt</span><span class="sxs-lookup"><span data-stu-id="206ae-103">FtSubFt</span></span>

  
  
<span data-ttu-id="206ae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="206ae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="206ae-105">从一个不带符号的64位整数中减去另一个。</span><span class="sxs-lookup"><span data-stu-id="206ae-105">Subtracts one unsigned 64-bit integer from another.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="206ae-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="206ae-106">Header file:</span></span>  <br/> |<span data-ttu-id="206ae-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="206ae-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="206ae-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="206ae-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="206ae-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="206ae-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="206ae-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="206ae-110">Called by:</span></span>  <br/> |<span data-ttu-id="206ae-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="206ae-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtSubFt(
  FILETIME Minuend,
  FILETIME Subtrahend
);
```

## <a name="parameters"></a><span data-ttu-id="206ae-112">参数</span><span class="sxs-lookup"><span data-stu-id="206ae-112">Parameters</span></span>

 <span data-ttu-id="206ae-113">_Minuend_</span><span class="sxs-lookup"><span data-stu-id="206ae-113">_Minuend_</span></span>
  
> <span data-ttu-id="206ae-114">实时一个[FILETIME](filetime.md)结构, 其中包含要从中减去_Subtrahend_参数中的值的无符号64位整数。</span><span class="sxs-lookup"><span data-stu-id="206ae-114">[in] A [FILETIME](filetime.md) structure that contains the unsigned 64-bit integer from which the value in the  _Subtrahend_ parameter is to be subtracted.</span></span> 
    
 <span data-ttu-id="206ae-115">_Subtrahend_</span><span class="sxs-lookup"><span data-stu-id="206ae-115">_Subtrahend_</span></span>
  
> <span data-ttu-id="206ae-116">实时一个**FILETIME**结构, 其中包含从_Minuend_参数指示的值中减去的无符号64位整数。</span><span class="sxs-lookup"><span data-stu-id="206ae-116">[in] A **FILETIME** structure that contains the unsigned 64-bit integer that is subtracted from the value indicated by the  _Minuend_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="206ae-117">返回值</span><span class="sxs-lookup"><span data-stu-id="206ae-117">Return value</span></span>

<span data-ttu-id="206ae-118">**FtSubFt**函数返回一个**FILETIME**结构, 其中包含减法的结果。</span><span class="sxs-lookup"><span data-stu-id="206ae-118">The **FtSubFt** function returns a **FILETIME** structure that contains the result of the subtraction.</span></span> <span data-ttu-id="206ae-119">这两个输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="206ae-119">The two input parameters remain unchanged.</span></span> 
  

