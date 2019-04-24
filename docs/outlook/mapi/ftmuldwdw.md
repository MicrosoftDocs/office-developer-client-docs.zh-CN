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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327977"
---
# <a name="ftmuldwdw"></a><span data-ttu-id="13ea3-103">FtMulDwDw</span><span class="sxs-lookup"><span data-stu-id="13ea3-103">FtMulDwDw</span></span>

  
  
<span data-ttu-id="13ea3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="13ea3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="13ea3-105">将一个不带符号的32位整数乘以另一个。</span><span class="sxs-lookup"><span data-stu-id="13ea3-105">Multiplies one unsigned 32-bit integer by another.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="13ea3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="13ea3-106">Header file:</span></span>  <br/> |<span data-ttu-id="13ea3-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="13ea3-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="13ea3-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="13ea3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="13ea3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="13ea3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="13ea3-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="13ea3-110">Called by:</span></span>  <br/> |<span data-ttu-id="13ea3-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="13ea3-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtMulDwDw(
  DWORD Multiplicand,
  DWORD Multiplier
);
```

## <a name="parameters"></a><span data-ttu-id="13ea3-112">参数</span><span class="sxs-lookup"><span data-stu-id="13ea3-112">Parameters</span></span>

 <span data-ttu-id="13ea3-113">_Multiplicand_</span><span class="sxs-lookup"><span data-stu-id="13ea3-113">_Multiplicand_</span></span>
  
> <span data-ttu-id="13ea3-114">实时包含与_乘数_参数中的值相乘的无符号32位整数的双字。</span><span class="sxs-lookup"><span data-stu-id="13ea3-114">[in] A double word that contains the unsigned 32-bit integer to be multiplied by the value in the  _Multiplier_ parameter.</span></span> 
    
 <span data-ttu-id="13ea3-115">_乘以_</span><span class="sxs-lookup"><span data-stu-id="13ea3-115">_Multiplier_</span></span>
  
> <span data-ttu-id="13ea3-116">实时包含未签名的32位整数乘数的双字。</span><span class="sxs-lookup"><span data-stu-id="13ea3-116">[in] A double word that contains the unsigned 32-bit integer multiplier.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="13ea3-117">返回值</span><span class="sxs-lookup"><span data-stu-id="13ea3-117">Return value</span></span>

<span data-ttu-id="13ea3-118">**FtMulDwDw**函数返回一个[FILETIME](filetime.md)结构, 其中包含两个整数的乘积。</span><span class="sxs-lookup"><span data-stu-id="13ea3-118">The **FtMulDwDw** function returns a [FILETIME](filetime.md) structure that contains the product of the two integers.</span></span> <span data-ttu-id="13ea3-119">这两个输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="13ea3-119">The two input parameters remain unchanged.</span></span> 
  

