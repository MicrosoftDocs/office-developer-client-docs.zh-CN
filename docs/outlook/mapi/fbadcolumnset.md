---
title: FBadColumnSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadColumnSet
api_type:
- HeaderDef
ms.assetid: 15be5a8c-4299-4434-b521-c901215b9dda
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5d1654908c50c348a27e1281168756100b7a88a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774912"
---
# <a name="fbadcolumnset"></a><span data-ttu-id="279c3-103">FBadColumnSet</span><span class="sxs-lookup"><span data-stu-id="279c3-103">FBadColumnSet</span></span>

  
  
<span data-ttu-id="279c3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="279c3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="279c3-105">设置表格列的有效性测试使用后续调用[IMAPITable::SetColumns](imapitable-setcolumns.md)方法中的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="279c3-105">Tests the validity of a table column set for use by a service provider in a subsequent call to the [IMAPITable::SetColumns](imapitable-setcolumns.md) method.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="279c3-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="279c3-106">Header file:</span></span>  <br/> |<span data-ttu-id="279c3-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="279c3-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="279c3-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="279c3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="279c3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="279c3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="279c3-110">调用：</span><span class="sxs-lookup"><span data-stu-id="279c3-110">Called by:</span></span>  <br/> |<span data-ttu-id="279c3-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="279c3-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadColumnSet(
  LPSPropTagArray lpptaCols
);
```

## <a name="parameters"></a><span data-ttu-id="279c3-112">参数</span><span class="sxs-lookup"><span data-stu-id="279c3-112">Parameters</span></span>

 <span data-ttu-id="279c3-113">_lpptaCols_</span><span class="sxs-lookup"><span data-stu-id="279c3-113">_lpptaCols_</span></span>
  
> <span data-ttu-id="279c3-114">[in]指向包含属性标记定义要验证的表格列的数组[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="279c3-114">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags defining the table columns to validate.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="279c3-115">返回值</span><span class="sxs-lookup"><span data-stu-id="279c3-115">Return value</span></span>

<span data-ttu-id="279c3-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="279c3-116">TRUE</span></span> 
  
> <span data-ttu-id="279c3-117">指定的列集无效。</span><span class="sxs-lookup"><span data-stu-id="279c3-117">The specified column set is invalid.</span></span> 
    
<span data-ttu-id="279c3-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="279c3-118">FALSE</span></span> 
  
> <span data-ttu-id="279c3-119">指定的列集才有效。</span><span class="sxs-lookup"><span data-stu-id="279c3-119">The specified column set is valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="279c3-120">说明</span><span class="sxs-lookup"><span data-stu-id="279c3-120">Remarks</span></span>

<span data-ttu-id="279c3-121">**FBadColumnSet**函数处理无效 PT_ERROR 类型的列和有效 PT_NULL 类型的列。</span><span class="sxs-lookup"><span data-stu-id="279c3-121">The **FBadColumnSet** function treats columns of type PT_ERROR as invalid and columns of type PT_NULL as valid.</span></span> 
  

