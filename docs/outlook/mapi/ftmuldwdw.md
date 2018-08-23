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
ms.openlocfilehash: 8002698b1644fb63292b4242d4fb3d784a99a03f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592022"
---
# <a name="ftmuldwdw"></a><span data-ttu-id="5e8f9-103">FtMulDwDw</span><span class="sxs-lookup"><span data-stu-id="5e8f9-103">FtMulDwDw</span></span>

  
  
<span data-ttu-id="5e8f9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e8f9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5e8f9-105">另一个乘以一个无符号的 32 位整数。</span><span class="sxs-lookup"><span data-stu-id="5e8f9-105">Multiplies one unsigned 32-bit integer by another.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5e8f9-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="5e8f9-106">Header file:</span></span>  <br/> |<span data-ttu-id="5e8f9-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="5e8f9-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="5e8f9-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="5e8f9-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="5e8f9-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="5e8f9-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="5e8f9-110">调用：</span><span class="sxs-lookup"><span data-stu-id="5e8f9-110">Called by:</span></span>  <br/> |<span data-ttu-id="5e8f9-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="5e8f9-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtMulDwDw(
  DWORD Multiplicand,
  DWORD Multiplier
);
```

## <a name="parameters"></a><span data-ttu-id="5e8f9-112">参数</span><span class="sxs-lookup"><span data-stu-id="5e8f9-112">Parameters</span></span>

 <span data-ttu-id="5e8f9-113">_被乘数_</span><span class="sxs-lookup"><span data-stu-id="5e8f9-113">_Multiplicand_</span></span>
  
> <span data-ttu-id="5e8f9-114">[in]双字包含 32 位无符号的整数相乘的_乘数_参数中的值。</span><span class="sxs-lookup"><span data-stu-id="5e8f9-114">[in] A double word that contains the unsigned 32-bit integer to be multiplied by the value in the  _Multiplier_ parameter.</span></span> 
    
 <span data-ttu-id="5e8f9-115">_乘子_</span><span class="sxs-lookup"><span data-stu-id="5e8f9-115">_Multiplier_</span></span>
  
> <span data-ttu-id="5e8f9-116">[in]双字包含 32 位无符号的整数乘数。</span><span class="sxs-lookup"><span data-stu-id="5e8f9-116">[in] A double word that contains the unsigned 32-bit integer multiplier.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5e8f9-117">返回值</span><span class="sxs-lookup"><span data-stu-id="5e8f9-117">Return value</span></span>

<span data-ttu-id="5e8f9-118">**FtMulDwDw**函数将返回一个[FILETIME](filetime.md)结构，其中包含两个包含整数的产品。</span><span class="sxs-lookup"><span data-stu-id="5e8f9-118">The **FtMulDwDw** function returns a [FILETIME](filetime.md) structure that contains the product of the two integers.</span></span> <span data-ttu-id="5e8f9-119">两个输入的参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="5e8f9-119">The two input parameters remain unchanged.</span></span> 
  

