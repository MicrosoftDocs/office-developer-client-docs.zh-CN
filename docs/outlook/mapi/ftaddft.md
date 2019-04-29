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
ms.openlocfilehash: cb20469adec938817fedf1b00789304625b388c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404762"
---
# <a name="ftaddft"></a><span data-ttu-id="82aa8-103">FtAddFt</span><span class="sxs-lookup"><span data-stu-id="82aa8-103">FtAddFt</span></span>

  
  
<span data-ttu-id="82aa8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82aa8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82aa8-105">将一个无符号64位整数添加到另一个。</span><span class="sxs-lookup"><span data-stu-id="82aa8-105">Adds one unsigned 64-bit integer to another.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="82aa8-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="82aa8-106">Header file:</span></span>  <br/> |<span data-ttu-id="82aa8-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="82aa8-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="82aa8-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="82aa8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="82aa8-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="82aa8-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="82aa8-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="82aa8-110">Called by:</span></span>  <br/> |<span data-ttu-id="82aa8-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="82aa8-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtAddFt(
  FILETIME Addend1,
  FILETIME Addend2
);
```

## <a name="parameters"></a><span data-ttu-id="82aa8-112">参数</span><span class="sxs-lookup"><span data-stu-id="82aa8-112">Parameters</span></span>

 <span data-ttu-id="82aa8-113">_Addend1_</span><span class="sxs-lookup"><span data-stu-id="82aa8-113">_Addend1_</span></span>
  
> <span data-ttu-id="82aa8-114">实时一个[FILETIME](filetime.md)结构, 其中包含要添加的第一个不带符号的64位整数。</span><span class="sxs-lookup"><span data-stu-id="82aa8-114">[in] A [FILETIME](filetime.md) structure that contains the first unsigned 64-bit integer to be added.</span></span> 
    
 <span data-ttu-id="82aa8-115">_Addend2_</span><span class="sxs-lookup"><span data-stu-id="82aa8-115">_Addend2_</span></span>
  
> <span data-ttu-id="82aa8-116">实时一个**FILETIME**结构, 其中包含要添加的第二个带符号的64位整数。</span><span class="sxs-lookup"><span data-stu-id="82aa8-116">[in] A **FILETIME** structure that contains the second unsigned 64-bit integer to be added.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="82aa8-117">返回值</span><span class="sxs-lookup"><span data-stu-id="82aa8-117">Return value</span></span>

<span data-ttu-id="82aa8-118">**FtAddFt**函数返回一个**FILETIME**结构, 其中包含两个整数的和。</span><span class="sxs-lookup"><span data-stu-id="82aa8-118">The **FtAddFt** function returns a **FILETIME** structure that contains the sum of the two integers.</span></span> <span data-ttu-id="82aa8-119">这两个输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="82aa8-119">The two input parameters remain unchanged.</span></span> 
  

