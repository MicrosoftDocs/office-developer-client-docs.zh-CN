---
title: SMAPIFormPropArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIFormPropArray
api_type:
- COM
ms.assetid: bb243bc4-4974-4ad6-aa76-2426c1ebe84b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 50b6581dec8211968a49b204c6d9b1ba1c65bb62
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309511"
---
# <a name="smapiformproparray"></a><span data-ttu-id="e6bd7-103">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="e6bd7-103">SMAPIFormPropArray</span></span>

  
  
<span data-ttu-id="e6bd7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6bd7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6bd7-105">包含[SMAPIFormProp](smapiformprop.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="e6bd7-105">Contains an array of [SMAPIFormProp](smapiformprop.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6bd7-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="e6bd7-106">Header file:</span></span>  <br/> |<span data-ttu-id="e6bd7-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="e6bd7-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="e6bd7-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="e6bd7-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="e6bd7-109">CbMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="e6bd7-109">CbMAPIFormPropArray</span></span>](cbmapiformproparray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cProps;
  ULONG ulPad;
  SMAPIFormProp aFormProp[MAPI_DIM];
} SMAPIFormPropArray, FAR * LPMAPIFORMPROPARRAY;

```

## <a name="members"></a><span data-ttu-id="e6bd7-110">Members</span><span class="sxs-lookup"><span data-stu-id="e6bd7-110">Members</span></span>

 <span data-ttu-id="e6bd7-111">**cProps**</span><span class="sxs-lookup"><span data-stu-id="e6bd7-111">**cProps**</span></span>
  
> <span data-ttu-id="e6bd7-112">**aFormProp**成员中的数组中的命名属性的计数。</span><span class="sxs-lookup"><span data-stu-id="e6bd7-112">Count of named properties in the array in the **aFormProp** member.</span></span> 
    
 <span data-ttu-id="e6bd7-113">**ulPad**</span><span class="sxs-lookup"><span data-stu-id="e6bd7-113">**ulPad**</span></span>
  
>  <span data-ttu-id="e6bd7-114">用来保证正确对齐的填充量为8个字节。</span><span class="sxs-lookup"><span data-stu-id="e6bd7-114">Eight bytes of padding used to guarantee correct alignment.</span></span> 
    
 <span data-ttu-id="e6bd7-115">**aFormProp**</span><span class="sxs-lookup"><span data-stu-id="e6bd7-115">**aFormProp**</span></span>
  
> <span data-ttu-id="e6bd7-116">表单属性的数组。</span><span class="sxs-lookup"><span data-stu-id="e6bd7-116">Array of form properties.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e6bd7-117">注解</span><span class="sxs-lookup"><span data-stu-id="e6bd7-117">Remarks</span></span>

<span data-ttu-id="e6bd7-118">**SMAPIFormPropArray**结构作为参数传递给以下方法:</span><span class="sxs-lookup"><span data-stu-id="e6bd7-118">The **SMAPIFormPropArray** structure is passed as a parameter to the following methods:</span></span> 
  
- [<span data-ttu-id="e6bd7-119">IMAPIFormInfo::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="e6bd7-119">IMAPIFormInfo::CalcFormPropSet</span></span>](imapiforminfo-calcformpropset.md)
    
- [<span data-ttu-id="e6bd7-120">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="e6bd7-120">IMAPIFormMgr::CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md)
    
- [<span data-ttu-id="e6bd7-121">IMAPIFormContainer::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="e6bd7-121">IMAPIFormContainer::CalcFormPropSet</span></span>](imapiformcontainer-calcformpropset.md)
    
## <a name="see-also"></a><span data-ttu-id="e6bd7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6bd7-122">See also</span></span>



[<span data-ttu-id="e6bd7-123">CbMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="e6bd7-123">CbMAPIFormPropArray</span></span>](cbmapiformproparray.md)
  
[<span data-ttu-id="e6bd7-124">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="e6bd7-124">SMAPIFormProp</span></span>](smapiformprop.md)


[<span data-ttu-id="e6bd7-125">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="e6bd7-125">MAPI Structures</span></span>](mapi-structures.md)

