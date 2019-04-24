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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327998"
---
# <a name="ftmuldw"></a><span data-ttu-id="24509-103">FtMulDw</span><span class="sxs-lookup"><span data-stu-id="24509-103">FtMulDw</span></span>

  
  
<span data-ttu-id="24509-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24509-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24509-105">将未签名的64位整数乘以无符号的32位整数。</span><span class="sxs-lookup"><span data-stu-id="24509-105">Multiplies an unsigned 64-bit integer by an unsigned 32-bit integer.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="24509-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="24509-106">Header file:</span></span>  <br/> |<span data-ttu-id="24509-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="24509-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="24509-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="24509-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="24509-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="24509-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="24509-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="24509-110">Called by:</span></span>  <br/> |<span data-ttu-id="24509-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="24509-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtMulDw(
  DWORD Multiplier,
  FILETIME Multiplicand
);
```

## <a name="parameters"></a><span data-ttu-id="24509-112">参数</span><span class="sxs-lookup"><span data-stu-id="24509-112">Parameters</span></span>

 <span data-ttu-id="24509-113">_乘以_</span><span class="sxs-lookup"><span data-stu-id="24509-113">_Multiplier_</span></span>
  
> <span data-ttu-id="24509-114">实时包含未签名的32位整数乘数的双字。</span><span class="sxs-lookup"><span data-stu-id="24509-114">[in] A double word that contains the unsigned 32-bit integer multiplier.</span></span> 
    
 <span data-ttu-id="24509-115">_Multiplicand_</span><span class="sxs-lookup"><span data-stu-id="24509-115">_Multiplicand_</span></span>
  
> <span data-ttu-id="24509-116">实时一个[FILETIME](filetime.md)结构, 其中包含_乘_号参数中的值要乘以的无符号64位整数。</span><span class="sxs-lookup"><span data-stu-id="24509-116">[in] A [FILETIME](filetime.md) structure that contains the unsigned 64-bit integer to be multiplied by the value in the  _Multiplier_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="24509-117">返回值</span><span class="sxs-lookup"><span data-stu-id="24509-117">Return value</span></span>

<span data-ttu-id="24509-118">**FtMulDw**函数返回一个**FILETIME**结构, 其中包含两个整数的乘积。</span><span class="sxs-lookup"><span data-stu-id="24509-118">The **FtMulDw** function returns a **FILETIME** structure that contains the product of the two integers.</span></span> <span data-ttu-id="24509-119">这两个输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="24509-119">The two input parameters remain unchanged.</span></span> 
  

