---
title: FtMulDw
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtMulDw
api_type:
- COM
ms.assetid: e135ba67-97be-4ce0-a72e-93c49ed7d6e2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 27ec919d720e1089d6e102f20485d936c9dc9808
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406344"
---
# <a name="ftmuldw"></a><span data-ttu-id="2f4d2-103">FtMulDw</span><span class="sxs-lookup"><span data-stu-id="2f4d2-103">FtMulDw</span></span>

  
  
<span data-ttu-id="2f4d2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f4d2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f4d2-105">无符号 64 位整数乘以无符号 32 位整数。</span><span class="sxs-lookup"><span data-stu-id="2f4d2-105">Multiplies an unsigned 64-bit integer by an unsigned 32-bit integer.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2f4d2-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2f4d2-106">Header file:</span></span>  <br/> |<span data-ttu-id="2f4d2-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="2f4d2-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="2f4d2-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="2f4d2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2f4d2-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2f4d2-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2f4d2-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="2f4d2-110">Called by:</span></span>  <br/> |<span data-ttu-id="2f4d2-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="2f4d2-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtMulDw(
  DWORD Multiplier,
  FILETIME Multiplicand
);
```

## <a name="parameters"></a><span data-ttu-id="2f4d2-112">参数</span><span class="sxs-lookup"><span data-stu-id="2f4d2-112">Parameters</span></span>

 <span data-ttu-id="2f4d2-113">_乘数_</span><span class="sxs-lookup"><span data-stu-id="2f4d2-113">_Multiplier_</span></span>
  
> <span data-ttu-id="2f4d2-114">[in]包含无符号 32 位整数乘数的双词。</span><span class="sxs-lookup"><span data-stu-id="2f4d2-114">[in] A double word that contains the unsigned 32-bit integer multiplier.</span></span> 
    
 <span data-ttu-id="2f4d2-115">_Multiplicand_</span><span class="sxs-lookup"><span data-stu-id="2f4d2-115">_Multiplicand_</span></span>
  
> <span data-ttu-id="2f4d2-116">[in] [FILETIME](filetime.md) 结构，包含要乘以  _乘_ 数参数中的值的无符号 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="2f4d2-116">[in] A [FILETIME](filetime.md) structure that contains the unsigned 64-bit integer to be multiplied by the value in the  _Multiplier_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2f4d2-117">返回值</span><span class="sxs-lookup"><span data-stu-id="2f4d2-117">Return value</span></span>

<span data-ttu-id="2f4d2-118">**FtMulDw** 函数返回 **FILETIME** 结构，其中包含两个整数的乘数。</span><span class="sxs-lookup"><span data-stu-id="2f4d2-118">The **FtMulDw** function returns a **FILETIME** structure that contains the product of the two integers.</span></span> <span data-ttu-id="2f4d2-119">两个输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="2f4d2-119">The two input parameters remain unchanged.</span></span> 
  

