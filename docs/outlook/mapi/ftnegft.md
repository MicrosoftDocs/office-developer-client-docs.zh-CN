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
ms.openlocfilehash: 37dc92a40043657cb791359d543ef52c77dbd8ce
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589236"
---
# <a name="ftnegft"></a><span data-ttu-id="61fa1-103">FtNegFt</span><span class="sxs-lookup"><span data-stu-id="61fa1-103">FtNegFt</span></span>

  
  
<span data-ttu-id="61fa1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="61fa1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="61fa1-105">计算 2 的补充的无符号的 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="61fa1-105">Computes the two's complement of an unsigned 64-bit integer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="61fa1-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="61fa1-106">Header file:</span></span>  <br/> |<span data-ttu-id="61fa1-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="61fa1-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="61fa1-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="61fa1-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="61fa1-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="61fa1-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="61fa1-110">调用：</span><span class="sxs-lookup"><span data-stu-id="61fa1-110">Called by:</span></span>  <br/> |<span data-ttu-id="61fa1-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="61fa1-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtNegFt(
  FILETIME ft
);
```

## <a name="parameters"></a><span data-ttu-id="61fa1-112">参数</span><span class="sxs-lookup"><span data-stu-id="61fa1-112">Parameters</span></span>

 <span data-ttu-id="61fa1-113">_ft_</span><span class="sxs-lookup"><span data-stu-id="61fa1-113">_ft_</span></span>
  
> <span data-ttu-id="61fa1-114">[in][FILETIME](filetime.md)结构，其中包含要计算的 2 的补充无符号的 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="61fa1-114">[in] A [FILETIME](filetime.md) structure that contains the unsigned 64-bit integer for which to compute the two's complement.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="61fa1-115">返回值</span><span class="sxs-lookup"><span data-stu-id="61fa1-115">Return value</span></span>

<span data-ttu-id="61fa1-116">**FtNegFt**函数将返回一个**FILETIME**结构，其中包含 2 的补充的整数。</span><span class="sxs-lookup"><span data-stu-id="61fa1-116">The **FtNegFt** function returns a **FILETIME** structure that contains the two's complement of the integer.</span></span> <span data-ttu-id="61fa1-117">输入的参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="61fa1-117">The input parameter remains unchanged.</span></span> 
  

