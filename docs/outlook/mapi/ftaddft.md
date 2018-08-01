---
title: FtAddFt
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtAddFt
api_type:
- COM
ms.assetid: 341ad06b-1caa-49bb-b859-cb512f6fb55d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e0e1535a770d4f1b437faf6a90c5f6415f6000ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775012"
---
# <a name="ftaddft"></a><span data-ttu-id="a350a-103">FtAddFt</span><span class="sxs-lookup"><span data-stu-id="a350a-103">FtAddFt</span></span>

  
  
<span data-ttu-id="a350a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a350a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a350a-105">添加到另一个无符号的 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="a350a-105">Adds one unsigned 64-bit integer to another.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a350a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="a350a-106">Header file:</span></span>  <br/> |<span data-ttu-id="a350a-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="a350a-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a350a-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="a350a-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a350a-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a350a-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a350a-110">调用：</span><span class="sxs-lookup"><span data-stu-id="a350a-110">Called by:</span></span>  <br/> |<span data-ttu-id="a350a-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="a350a-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtAddFt(
  FILETIME Addend1,
  FILETIME Addend2
);
```

## <a name="parameters"></a><span data-ttu-id="a350a-112">参数</span><span class="sxs-lookup"><span data-stu-id="a350a-112">Parameters</span></span>

 <span data-ttu-id="a350a-113">_Addend1_</span><span class="sxs-lookup"><span data-stu-id="a350a-113">_Addend1_</span></span>
  
> <span data-ttu-id="a350a-114">[in]包含的第一个无符号的 64 位整数，要添加的[FILETIME](filetime.md)结构。</span><span class="sxs-lookup"><span data-stu-id="a350a-114">[in] A [FILETIME](filetime.md) structure that contains the first unsigned 64-bit integer to be added.</span></span> 
    
 <span data-ttu-id="a350a-115">_Addend2_</span><span class="sxs-lookup"><span data-stu-id="a350a-115">_Addend2_</span></span>
  
> <span data-ttu-id="a350a-116">[in]包含的第二个无符号的 64 位整数，要添加的**FILETIME**结构。</span><span class="sxs-lookup"><span data-stu-id="a350a-116">[in] A **FILETIME** structure that contains the second unsigned 64-bit integer to be added.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a350a-117">返回值</span><span class="sxs-lookup"><span data-stu-id="a350a-117">Return value</span></span>

<span data-ttu-id="a350a-118">**FtAddFt**函数将返回一个**FILETIME**结构，其中包含两个包含整数的总和。</span><span class="sxs-lookup"><span data-stu-id="a350a-118">The **FtAddFt** function returns a **FILETIME** structure that contains the sum of the two integers.</span></span> <span data-ttu-id="a350a-119">两个输入的参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="a350a-119">The two input parameters remain unchanged.</span></span> 
  

