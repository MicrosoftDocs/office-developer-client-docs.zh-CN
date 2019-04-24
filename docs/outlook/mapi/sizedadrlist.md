---
title: SizedADRLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedADRLIST
api_type:
- COM
ms.assetid: 5c64d74a-83a7-4122-b1d1-fcca0f4a6cdb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c35a1eb54b29c04bc8eed453272b59aae0ea737e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282773"
---
# <a name="sizedadrlist"></a><span data-ttu-id="cbe01-103">SizedADRLIST</span><span class="sxs-lookup"><span data-stu-id="cbe01-103">SizedADRLIST</span></span>

<span data-ttu-id="cbe01-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cbe01-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cbe01-105">定义具有指定名称的[ADRLIST](adrlist.md)结构, 其中包含指定数量的[ADRENTRY](adrentry.md)结构。</span><span class="sxs-lookup"><span data-stu-id="cbe01-105">Defines an [ADRLIST](adrlist.md) structure with the specified name that contains a specified number of [ADRENTRY](adrentry.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cbe01-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="cbe01-106">Header file:</span></span>  <br/> |<span data-ttu-id="cbe01-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="cbe01-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="cbe01-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="cbe01-108">Related structure:</span></span>  <br/> |<span data-ttu-id="cbe01-109">**ADRLIST**</span><span class="sxs-lookup"><span data-stu-id="cbe01-109">**ADRLIST**</span></span> <br/> |
   
```cpp
SizedADRLIST (_centries,_name)
```

## <a name="parameters"></a><span data-ttu-id="cbe01-110">参数</span><span class="sxs-lookup"><span data-stu-id="cbe01-110">Parameters</span></span>

<span data-ttu-id="cbe01-111">__centries_</span><span class="sxs-lookup"><span data-stu-id="cbe01-111">__centries_</span></span>
  
> <span data-ttu-id="cbe01-112">要包含在新**ADRLIST**结构中的**ADRENTRY**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="cbe01-112">Count of **ADRENTRY** structures to be included in the new **ADRLIST** structure.</span></span> 
    
<span data-ttu-id="cbe01-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="cbe01-113">__name_</span></span>
  
> <span data-ttu-id="cbe01-114">新**ADRLIST**结构的名称。</span><span class="sxs-lookup"><span data-stu-id="cbe01-114">Name for the new **ADRLIST** structure.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="cbe01-115">注解</span><span class="sxs-lookup"><span data-stu-id="cbe01-115">Remarks</span></span>

<span data-ttu-id="cbe01-116">**SizedADRLIST**宏允许您在已知数组长度要求时定义具有显式边界的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="cbe01-116">The **SizedADRLIST** macro lets you define a recipient list that has explicit bounds when array length requirements are known.</span></span> <span data-ttu-id="cbe01-117">下面的代码演示如何将**SizedADRLIST**宏的结果转换为**ADRLIST**结构指针:</span><span class="sxs-lookup"><span data-stu-id="cbe01-117">The following code shows how to cast the result of the **SizedADRLIST** macro to an **ADRLIST** structure pointer:</span></span> 
  
```cpp
lpADRList = (LPADRLIST) &SizedADRList;
```

## <a name="see-also"></a><span data-ttu-id="cbe01-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbe01-118">See also</span></span>

- [<span data-ttu-id="cbe01-119">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="cbe01-119">ADRLIST</span></span>](adrlist.md)
- [<span data-ttu-id="cbe01-120">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="cbe01-120">ADRENTRY</span></span>](adrentry.md)
- [<span data-ttu-id="cbe01-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="cbe01-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

