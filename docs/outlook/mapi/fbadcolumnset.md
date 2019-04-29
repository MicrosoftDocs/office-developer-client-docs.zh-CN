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
ms.openlocfilehash: b0260ffe5dc4806cb627fd71c78866bf96796455
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434716"
---
# <a name="fbadcolumnset"></a><span data-ttu-id="902a7-103">FBadColumnSet</span><span class="sxs-lookup"><span data-stu-id="902a7-103">FBadColumnSet</span></span>

  
  
<span data-ttu-id="902a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="902a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="902a7-105">测试在对[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法的后续调用中, 服务提供商是否要使用的表格列集的有效性。</span><span class="sxs-lookup"><span data-stu-id="902a7-105">Tests the validity of a table column set for use by a service provider in a subsequent call to the [IMAPITable::SetColumns](imapitable-setcolumns.md) method.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="902a7-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="902a7-106">Header file:</span></span>  <br/> |<span data-ttu-id="902a7-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="902a7-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="902a7-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="902a7-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="902a7-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="902a7-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="902a7-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="902a7-110">Called by:</span></span>  <br/> |<span data-ttu-id="902a7-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="902a7-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadColumnSet(
  LPSPropTagArray lpptaCols
);
```

## <a name="parameters"></a><span data-ttu-id="902a7-112">参数</span><span class="sxs-lookup"><span data-stu-id="902a7-112">Parameters</span></span>

 <span data-ttu-id="902a7-113">_lpptaCols_</span><span class="sxs-lookup"><span data-stu-id="902a7-113">_lpptaCols_</span></span>
  
> <span data-ttu-id="902a7-114">实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含定义要验证的表列的属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="902a7-114">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags defining the table columns to validate.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="902a7-115">返回值</span><span class="sxs-lookup"><span data-stu-id="902a7-115">Return value</span></span>

<span data-ttu-id="902a7-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="902a7-116">TRUE</span></span> 
  
> <span data-ttu-id="902a7-117">指定的列集无效。</span><span class="sxs-lookup"><span data-stu-id="902a7-117">The specified column set is invalid.</span></span> 
    
<span data-ttu-id="902a7-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="902a7-118">FALSE</span></span> 
  
> <span data-ttu-id="902a7-119">指定的列集有效。</span><span class="sxs-lookup"><span data-stu-id="902a7-119">The specified column set is valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="902a7-120">说明</span><span class="sxs-lookup"><span data-stu-id="902a7-120">Remarks</span></span>

<span data-ttu-id="902a7-121">**FBadColumnSet**函数将类型为 PT_ERROR 的列视为无效, 并将类型为 PT_NULL 的列视为有效。</span><span class="sxs-lookup"><span data-stu-id="902a7-121">The **FBadColumnSet** function treats columns of type PT_ERROR as invalid and columns of type PT_NULL as valid.</span></span> 
  

