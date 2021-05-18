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
# <a name="ftsubft"></a><span data-ttu-id="d97db-103">FtSubFt</span><span class="sxs-lookup"><span data-stu-id="d97db-103">FtSubFt</span></span>

  
  
<span data-ttu-id="d97db-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d97db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d97db-105">将一个无符号 64 位整数从另一个整数中减去。</span><span class="sxs-lookup"><span data-stu-id="d97db-105">Subtracts one unsigned 64-bit integer from another.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d97db-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d97db-106">Header file:</span></span>  <br/> |<span data-ttu-id="d97db-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="d97db-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="d97db-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="d97db-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d97db-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d97db-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d97db-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="d97db-110">Called by:</span></span>  <br/> |<span data-ttu-id="d97db-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="d97db-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtSubFt(
  FILETIME Minuend,
  FILETIME Subtrahend
);
```

## <a name="parameters"></a><span data-ttu-id="d97db-112">参数</span><span class="sxs-lookup"><span data-stu-id="d97db-112">Parameters</span></span>

 <span data-ttu-id="d97db-113">_Minuend_</span><span class="sxs-lookup"><span data-stu-id="d97db-113">_Minuend_</span></span>
  
> <span data-ttu-id="d97db-114">[in]包含无符号 64 位整数的 [FILETIME](filetime.md) 结构，将从该整数中减去  _Subtrahend_ 参数中的值。</span><span class="sxs-lookup"><span data-stu-id="d97db-114">[in] A [FILETIME](filetime.md) structure that contains the unsigned 64-bit integer from which the value in the  _Subtrahend_ parameter is to be subtracted.</span></span> 
    
 <span data-ttu-id="d97db-115">_Subtrahend_</span><span class="sxs-lookup"><span data-stu-id="d97db-115">_Subtrahend_</span></span>
  
> <span data-ttu-id="d97db-116">[in]包含无符号 64 位整数的 **FILETIME** 结构，该整数从  _Minuend_ 参数指示的值中减去。</span><span class="sxs-lookup"><span data-stu-id="d97db-116">[in] A **FILETIME** structure that contains the unsigned 64-bit integer that is subtracted from the value indicated by the  _Minuend_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d97db-117">返回值</span><span class="sxs-lookup"><span data-stu-id="d97db-117">Return value</span></span>

<span data-ttu-id="d97db-118">**FtSubFt** 函数返回包含减法结果的 **FILETIME** 结构。</span><span class="sxs-lookup"><span data-stu-id="d97db-118">The **FtSubFt** function returns a **FILETIME** structure that contains the result of the subtraction.</span></span> <span data-ttu-id="d97db-119">两个输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="d97db-119">The two input parameters remain unchanged.</span></span> 
  

