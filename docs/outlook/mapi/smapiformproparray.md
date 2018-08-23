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
ms.openlocfilehash: 389984f9d98ece6b2040edd741e3028fd7d766ed
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579310"
---
# <a name="smapiformproparray"></a><span data-ttu-id="94a9a-103">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="94a9a-103">SMAPIFormPropArray</span></span>

  
  
<span data-ttu-id="94a9a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="94a9a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="94a9a-105">包含一个[SMAPIFormProp](smapiformprop.md)结构数组。</span><span class="sxs-lookup"><span data-stu-id="94a9a-105">Contains an array of [SMAPIFormProp](smapiformprop.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="94a9a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="94a9a-106">Header file:</span></span>  <br/> |<span data-ttu-id="94a9a-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="94a9a-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="94a9a-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="94a9a-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="94a9a-109">CbMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="94a9a-109">CbMAPIFormPropArray</span></span>](cbmapiformproparray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cProps;
  ULONG ulPad;
  SMAPIFormProp aFormProp[MAPI_DIM];
} SMAPIFormPropArray, FAR * LPMAPIFORMPROPARRAY;

```

## <a name="members"></a><span data-ttu-id="94a9a-110">Members</span><span class="sxs-lookup"><span data-stu-id="94a9a-110">Members</span></span>

 <span data-ttu-id="94a9a-111">**cProps**</span><span class="sxs-lookup"><span data-stu-id="94a9a-111">**cProps**</span></span>
  
> <span data-ttu-id="94a9a-112">在**aFormProp**成员数组中的命名属性的计数。</span><span class="sxs-lookup"><span data-stu-id="94a9a-112">Count of named properties in the array in the **aFormProp** member.</span></span> 
    
 <span data-ttu-id="94a9a-113">**ulPad**</span><span class="sxs-lookup"><span data-stu-id="94a9a-113">**ulPad**</span></span>
  
>  <span data-ttu-id="94a9a-114">8 个字节用于保证正确的对齐方式的边距。</span><span class="sxs-lookup"><span data-stu-id="94a9a-114">Eight bytes of padding used to guarantee correct alignment.</span></span> 
    
 <span data-ttu-id="94a9a-115">**aFormProp**</span><span class="sxs-lookup"><span data-stu-id="94a9a-115">**aFormProp**</span></span>
  
> <span data-ttu-id="94a9a-116">窗体属性的数组。</span><span class="sxs-lookup"><span data-stu-id="94a9a-116">Array of form properties.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="94a9a-117">注解</span><span class="sxs-lookup"><span data-stu-id="94a9a-117">Remarks</span></span>

<span data-ttu-id="94a9a-118">**SMAPIFormPropArray**结构作为参数传递给以下方法：</span><span class="sxs-lookup"><span data-stu-id="94a9a-118">The **SMAPIFormPropArray** structure is passed as a parameter to the following methods:</span></span> 
  
- [<span data-ttu-id="94a9a-119">IMAPIFormInfo::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="94a9a-119">IMAPIFormInfo::CalcFormPropSet</span></span>](imapiforminfo-calcformpropset.md)
    
- [<span data-ttu-id="94a9a-120">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="94a9a-120">IMAPIFormMgr::CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md)
    
- [<span data-ttu-id="94a9a-121">IMAPIFormContainer::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="94a9a-121">IMAPIFormContainer::CalcFormPropSet</span></span>](imapiformcontainer-calcformpropset.md)
    
## <a name="see-also"></a><span data-ttu-id="94a9a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94a9a-122">See also</span></span>



[<span data-ttu-id="94a9a-123">CbMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="94a9a-123">CbMAPIFormPropArray</span></span>](cbmapiformproparray.md)
  
[<span data-ttu-id="94a9a-124">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="94a9a-124">SMAPIFormProp</span></span>](smapiformprop.md)


[<span data-ttu-id="94a9a-125">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="94a9a-125">MAPI Structures</span></span>](mapi-structures.md)

