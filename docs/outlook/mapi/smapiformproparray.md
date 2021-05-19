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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420064"
---
# <a name="smapiformproparray"></a><span data-ttu-id="951c1-103">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="951c1-103">SMAPIFormPropArray</span></span>

  
  
<span data-ttu-id="951c1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="951c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="951c1-105">包含 [SMAPIFormProp 结构](smapiformprop.md) 数组。</span><span class="sxs-lookup"><span data-stu-id="951c1-105">Contains an array of [SMAPIFormProp](smapiformprop.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="951c1-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="951c1-106">Header file:</span></span>  <br/> |<span data-ttu-id="951c1-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="951c1-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="951c1-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="951c1-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="951c1-109">CbMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="951c1-109">CbMAPIFormPropArray</span></span>](cbmapiformproparray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cProps;
  ULONG ulPad;
  SMAPIFormProp aFormProp[MAPI_DIM];
} SMAPIFormPropArray, FAR * LPMAPIFORMPROPARRAY;

```

## <a name="members"></a><span data-ttu-id="951c1-110">Members</span><span class="sxs-lookup"><span data-stu-id="951c1-110">Members</span></span>

 <span data-ttu-id="951c1-111">**cProps**</span><span class="sxs-lookup"><span data-stu-id="951c1-111">**cProps**</span></span>
  
> <span data-ttu-id="951c1-112">**aFormProp** 成员数组中命名属性的计数。</span><span class="sxs-lookup"><span data-stu-id="951c1-112">Count of named properties in the array in the **aFormProp** member.</span></span> 
    
 <span data-ttu-id="951c1-113">**ulPad**</span><span class="sxs-lookup"><span data-stu-id="951c1-113">**ulPad**</span></span>
  
>  <span data-ttu-id="951c1-114">用于保证正确对齐的八字节填充。</span><span class="sxs-lookup"><span data-stu-id="951c1-114">Eight bytes of padding used to guarantee correct alignment.</span></span> 
    
 <span data-ttu-id="951c1-115">**aFormProp**</span><span class="sxs-lookup"><span data-stu-id="951c1-115">**aFormProp**</span></span>
  
> <span data-ttu-id="951c1-116">表单属性数组。</span><span class="sxs-lookup"><span data-stu-id="951c1-116">Array of form properties.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="951c1-117">备注</span><span class="sxs-lookup"><span data-stu-id="951c1-117">Remarks</span></span>

<span data-ttu-id="951c1-118">**SMAPIFormPropArray** 结构作为参数传递给以下方法：</span><span class="sxs-lookup"><span data-stu-id="951c1-118">The **SMAPIFormPropArray** structure is passed as a parameter to the following methods:</span></span> 
  
- [<span data-ttu-id="951c1-119">IMAPIFormInfo::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="951c1-119">IMAPIFormInfo::CalcFormPropSet</span></span>](imapiforminfo-calcformpropset.md)
    
- [<span data-ttu-id="951c1-120">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="951c1-120">IMAPIFormMgr::CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md)
    
- [<span data-ttu-id="951c1-121">IMAPIFormContainer::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="951c1-121">IMAPIFormContainer::CalcFormPropSet</span></span>](imapiformcontainer-calcformpropset.md)
    
## <a name="see-also"></a><span data-ttu-id="951c1-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="951c1-122">See also</span></span>



[<span data-ttu-id="951c1-123">CbMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="951c1-123">CbMAPIFormPropArray</span></span>](cbmapiformproparray.md)
  
[<span data-ttu-id="951c1-124">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="951c1-124">SMAPIFormProp</span></span>](smapiformprop.md)


[<span data-ttu-id="951c1-125">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="951c1-125">MAPI Structures</span></span>](mapi-structures.md)

