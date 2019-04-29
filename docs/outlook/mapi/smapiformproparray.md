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
# <a name="smapiformproparray"></a><span data-ttu-id="53e73-103">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="53e73-103">SMAPIFormPropArray</span></span>

  
  
<span data-ttu-id="53e73-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53e73-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53e73-105">包含[SMAPIFormProp](smapiformprop.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="53e73-105">Contains an array of [SMAPIFormProp](smapiformprop.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="53e73-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="53e73-106">Header file:</span></span>  <br/> |<span data-ttu-id="53e73-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="53e73-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="53e73-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="53e73-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="53e73-109">CbMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="53e73-109">CbMAPIFormPropArray</span></span>](cbmapiformproparray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cProps;
  ULONG ulPad;
  SMAPIFormProp aFormProp[MAPI_DIM];
} SMAPIFormPropArray, FAR * LPMAPIFORMPROPARRAY;

```

## <a name="members"></a><span data-ttu-id="53e73-110">Members</span><span class="sxs-lookup"><span data-stu-id="53e73-110">Members</span></span>

 <span data-ttu-id="53e73-111">**cProps**</span><span class="sxs-lookup"><span data-stu-id="53e73-111">**cProps**</span></span>
  
> <span data-ttu-id="53e73-112">**aFormProp**成员中的数组中的命名属性的计数。</span><span class="sxs-lookup"><span data-stu-id="53e73-112">Count of named properties in the array in the **aFormProp** member.</span></span> 
    
 <span data-ttu-id="53e73-113">**ulPad**</span><span class="sxs-lookup"><span data-stu-id="53e73-113">**ulPad**</span></span>
  
>  <span data-ttu-id="53e73-114">用来保证正确对齐的填充量为8个字节。</span><span class="sxs-lookup"><span data-stu-id="53e73-114">Eight bytes of padding used to guarantee correct alignment.</span></span> 
    
 <span data-ttu-id="53e73-115">**aFormProp**</span><span class="sxs-lookup"><span data-stu-id="53e73-115">**aFormProp**</span></span>
  
> <span data-ttu-id="53e73-116">表单属性的数组。</span><span class="sxs-lookup"><span data-stu-id="53e73-116">Array of form properties.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="53e73-117">说明</span><span class="sxs-lookup"><span data-stu-id="53e73-117">Remarks</span></span>

<span data-ttu-id="53e73-118">**SMAPIFormPropArray**结构作为参数传递给以下方法:</span><span class="sxs-lookup"><span data-stu-id="53e73-118">The **SMAPIFormPropArray** structure is passed as a parameter to the following methods:</span></span> 
  
- [<span data-ttu-id="53e73-119">IMAPIFormInfo::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="53e73-119">IMAPIFormInfo::CalcFormPropSet</span></span>](imapiforminfo-calcformpropset.md)
    
- [<span data-ttu-id="53e73-120">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="53e73-120">IMAPIFormMgr::CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md)
    
- [<span data-ttu-id="53e73-121">IMAPIFormContainer::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="53e73-121">IMAPIFormContainer::CalcFormPropSet</span></span>](imapiformcontainer-calcformpropset.md)
    
## <a name="see-also"></a><span data-ttu-id="53e73-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53e73-122">See also</span></span>



[<span data-ttu-id="53e73-123">CbMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="53e73-123">CbMAPIFormPropArray</span></span>](cbmapiformproparray.md)
  
[<span data-ttu-id="53e73-124">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="53e73-124">SMAPIFormProp</span></span>](smapiformprop.md)


[<span data-ttu-id="53e73-125">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="53e73-125">MAPI Structures</span></span>](mapi-structures.md)

