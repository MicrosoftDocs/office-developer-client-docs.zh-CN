---
title: FtNegFt
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtNegFt
api_type:
- COM
ms.assetid: 639a408c-aed1-456b-9f75-9d6fb8dcb33b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: db208dad8697060e394b3ee037ea658cefbab669
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327970"
---
# <a name="ftnegft"></a><span data-ttu-id="79d07-103">FtNegFt</span><span class="sxs-lookup"><span data-stu-id="79d07-103">FtNegFt</span></span>

  
  
<span data-ttu-id="79d07-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79d07-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79d07-105">计算两个不带符号的64位整数的补码。</span><span class="sxs-lookup"><span data-stu-id="79d07-105">Computes the two's complement of an unsigned 64-bit integer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="79d07-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="79d07-106">Header file:</span></span>  <br/> |<span data-ttu-id="79d07-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="79d07-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="79d07-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="79d07-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="79d07-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="79d07-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="79d07-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="79d07-110">Called by:</span></span>  <br/> |<span data-ttu-id="79d07-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="79d07-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtNegFt(
  FILETIME ft
);
```

## <a name="parameters"></a><span data-ttu-id="79d07-112">参数</span><span class="sxs-lookup"><span data-stu-id="79d07-112">Parameters</span></span>

 <span data-ttu-id="79d07-113">_ft_</span><span class="sxs-lookup"><span data-stu-id="79d07-113">_ft_</span></span>
  
> <span data-ttu-id="79d07-114">实时一个[FILETIME](filetime.md)结构, 其中包含为其计算两个补码的无符号64位整数。</span><span class="sxs-lookup"><span data-stu-id="79d07-114">[in] A [FILETIME](filetime.md) structure that contains the unsigned 64-bit integer for which to compute the two's complement.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="79d07-115">返回值</span><span class="sxs-lookup"><span data-stu-id="79d07-115">Return value</span></span>

<span data-ttu-id="79d07-116">**FtNegFt**函数返回一个**FILETIME**结构, 其中包含整数的两个补码。</span><span class="sxs-lookup"><span data-stu-id="79d07-116">The **FtNegFt** function returns a **FILETIME** structure that contains the two's complement of the integer.</span></span> <span data-ttu-id="79d07-117">输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="79d07-117">The input parameter remains unchanged.</span></span> 
  

