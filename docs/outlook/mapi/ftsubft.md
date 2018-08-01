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
ms.openlocfilehash: 954630b0b92772d961dc61084c28a9ab419e4c2f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775015"
---
# <a name="ftsubft"></a><span data-ttu-id="a6b42-103">FtSubFt</span><span class="sxs-lookup"><span data-stu-id="a6b42-103">FtSubFt</span></span>

  
  
<span data-ttu-id="a6b42-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a6b42-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a6b42-105">剪除与从另一个无符号的 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="a6b42-105">Subtracts one unsigned 64-bit integer from another.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a6b42-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="a6b42-106">Header file:</span></span>  <br/> |<span data-ttu-id="a6b42-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="a6b42-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a6b42-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="a6b42-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a6b42-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a6b42-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a6b42-110">调用：</span><span class="sxs-lookup"><span data-stu-id="a6b42-110">Called by:</span></span>  <br/> |<span data-ttu-id="a6b42-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="a6b42-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtSubFt(
  FILETIME Minuend,
  FILETIME Subtrahend
);
```

## <a name="parameters"></a><span data-ttu-id="a6b42-112">参数</span><span class="sxs-lookup"><span data-stu-id="a6b42-112">Parameters</span></span>

 <span data-ttu-id="a6b42-113">_被减数_</span><span class="sxs-lookup"><span data-stu-id="a6b42-113">_Minuend_</span></span>
  
> <span data-ttu-id="a6b42-114">[in][FILETIME](filetime.md)结构，包含从中_减数_参数中的值是中减去的 64 位无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="a6b42-114">[in] A [FILETIME](filetime.md) structure that contains the unsigned 64-bit integer from which the value in the  _Subtrahend_ parameter is to be subtracted.</span></span> 
    
 <span data-ttu-id="a6b42-115">_减数_</span><span class="sxs-lookup"><span data-stu-id="a6b42-115">_Subtrahend_</span></span>
  
> <span data-ttu-id="a6b42-116">[in]**FILETIME**结构，其中包含从指示_被减数_参数的值减去的无符号的 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="a6b42-116">[in] A **FILETIME** structure that contains the unsigned 64-bit integer that is subtracted from the value indicated by the  _Minuend_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a6b42-117">返回值</span><span class="sxs-lookup"><span data-stu-id="a6b42-117">Return value</span></span>

<span data-ttu-id="a6b42-118">**FtSubFt**函数将返回包含结果的减法**FILETIME**结构。</span><span class="sxs-lookup"><span data-stu-id="a6b42-118">The **FtSubFt** function returns a **FILETIME** structure that contains the result of the subtraction.</span></span> <span data-ttu-id="a6b42-119">两个输入的参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="a6b42-119">The two input parameters remain unchanged.</span></span> 
  

