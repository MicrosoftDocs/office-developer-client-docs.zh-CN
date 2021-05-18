---
title: FtMulDwDw
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtMulDwDw
api_type:
- COM
ms.assetid: 8c1a342c-d7ae-4e26-b327-a63cdd3c3ee6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 54561450e7d91d8a30695dacf508758623547e39
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412910"
---
# <a name="ftmuldwdw"></a><span data-ttu-id="7c723-103">FtMulDwDw</span><span class="sxs-lookup"><span data-stu-id="7c723-103">FtMulDwDw</span></span>

  
  
<span data-ttu-id="7c723-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7c723-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7c723-105">将一个无符号 32 位整数乘以另一个。</span><span class="sxs-lookup"><span data-stu-id="7c723-105">Multiplies one unsigned 32-bit integer by another.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7c723-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7c723-106">Header file:</span></span>  <br/> |<span data-ttu-id="7c723-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="7c723-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="7c723-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7c723-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7c723-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7c723-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7c723-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7c723-110">Called by:</span></span>  <br/> |<span data-ttu-id="7c723-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="7c723-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtMulDwDw(
  DWORD Multiplicand,
  DWORD Multiplier
);
```

## <a name="parameters"></a><span data-ttu-id="7c723-112">参数</span><span class="sxs-lookup"><span data-stu-id="7c723-112">Parameters</span></span>

 <span data-ttu-id="7c723-113">_Multiplicand_</span><span class="sxs-lookup"><span data-stu-id="7c723-113">_Multiplicand_</span></span>
  
> <span data-ttu-id="7c723-114">[in]包含要乘以  _乘_ 数参数中的值的无符号 32 位整数的双词。</span><span class="sxs-lookup"><span data-stu-id="7c723-114">[in] A double word that contains the unsigned 32-bit integer to be multiplied by the value in the  _Multiplier_ parameter.</span></span> 
    
 <span data-ttu-id="7c723-115">_乘数_</span><span class="sxs-lookup"><span data-stu-id="7c723-115">_Multiplier_</span></span>
  
> <span data-ttu-id="7c723-116">[in]包含无符号 32 位整数乘数的双词。</span><span class="sxs-lookup"><span data-stu-id="7c723-116">[in] A double word that contains the unsigned 32-bit integer multiplier.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7c723-117">返回值</span><span class="sxs-lookup"><span data-stu-id="7c723-117">Return value</span></span>

<span data-ttu-id="7c723-118">**FtMulDwDw** 函数返回 [FILETIME](filetime.md)结构，其中包含两个整数的乘数。</span><span class="sxs-lookup"><span data-stu-id="7c723-118">The **FtMulDwDw** function returns a [FILETIME](filetime.md) structure that contains the product of the two integers.</span></span> <span data-ttu-id="7c723-119">两个输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="7c723-119">The two input parameters remain unchanged.</span></span> 
  

