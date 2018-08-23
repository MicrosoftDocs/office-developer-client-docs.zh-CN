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
ms.openlocfilehash: c823a4e3d08d9082a3b5ac5c4bd8169612caa16e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583993"
---
# <a name="ftmuldw"></a><span data-ttu-id="7fd20-103">FtMulDw</span><span class="sxs-lookup"><span data-stu-id="7fd20-103">FtMulDw</span></span>

  
  
<span data-ttu-id="7fd20-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7fd20-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7fd20-105">相乘 32 位无符号整数无符号的 64 位的整数。</span><span class="sxs-lookup"><span data-stu-id="7fd20-105">Multiplies an unsigned 64-bit integer by an unsigned 32-bit integer.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7fd20-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="7fd20-106">Header file:</span></span>  <br/> |<span data-ttu-id="7fd20-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="7fd20-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="7fd20-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="7fd20-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7fd20-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7fd20-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7fd20-110">调用：</span><span class="sxs-lookup"><span data-stu-id="7fd20-110">Called by:</span></span>  <br/> |<span data-ttu-id="7fd20-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="7fd20-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtMulDw(
  DWORD Multiplier,
  FILETIME Multiplicand
);
```

## <a name="parameters"></a><span data-ttu-id="7fd20-112">参数</span><span class="sxs-lookup"><span data-stu-id="7fd20-112">Parameters</span></span>

 <span data-ttu-id="7fd20-113">_乘子_</span><span class="sxs-lookup"><span data-stu-id="7fd20-113">_Multiplier_</span></span>
  
> <span data-ttu-id="7fd20-114">[in]双字包含 32 位无符号的整数乘数。</span><span class="sxs-lookup"><span data-stu-id="7fd20-114">[in] A double word that contains the unsigned 32-bit integer multiplier.</span></span> 
    
 <span data-ttu-id="7fd20-115">_被乘数_</span><span class="sxs-lookup"><span data-stu-id="7fd20-115">_Multiplicand_</span></span>
  
> <span data-ttu-id="7fd20-116">[in]一个[FILETIME](filetime.md)结构包含无符号的 64 位整数，若要相乘的_乘数_参数中的值。</span><span class="sxs-lookup"><span data-stu-id="7fd20-116">[in] A [FILETIME](filetime.md) structure that contains the unsigned 64-bit integer to be multiplied by the value in the  _Multiplier_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7fd20-117">返回值</span><span class="sxs-lookup"><span data-stu-id="7fd20-117">Return value</span></span>

<span data-ttu-id="7fd20-118">**FtMulDw**函数将返回一个**FILETIME**结构，其中包含两个包含整数的产品。</span><span class="sxs-lookup"><span data-stu-id="7fd20-118">The **FtMulDw** function returns a **FILETIME** structure that contains the product of the two integers.</span></span> <span data-ttu-id="7fd20-119">两个输入的参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="7fd20-119">The two input parameters remain unchanged.</span></span> 
  

