---
title: SetAttribIMsgOnIStg
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SetAttribIMsgOnIStg
api_type:
- COM
ms.assetid: 683d0d00-1b93-445d-86ff-180a3e6d2323
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 076fb4946af9a80e53fb8452d720c22b351f5ef6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572520"
---
# <a name="setattribimsgonistg"></a><span data-ttu-id="663d6-103">SetAttribIMsgOnIStg</span><span class="sxs-lookup"><span data-stu-id="663d6-103">SetAttribIMsgOnIStg</span></span>

  
  
<span data-ttu-id="663d6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="663d6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="663d6-105">设置或更改的属性由[OpenIMsgOnIStg](openimsgonistg.md)函数提供[IMessage](imessageimapiprop.md)对象的属性。</span><span class="sxs-lookup"><span data-stu-id="663d6-105">Sets or alters attributes of properties on an [IMessage](imessageimapiprop.md) object supplied by the [OpenIMsgOnIStg](openimsgonistg.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="663d6-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="663d6-106">Header file:</span></span>  <br/> |<span data-ttu-id="663d6-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="663d6-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="663d6-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="663d6-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="663d6-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="663d6-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="663d6-110">调用：</span><span class="sxs-lookup"><span data-stu-id="663d6-110">Called by:</span></span>  <br/> |<span data-ttu-id="663d6-111">客户端应用程序和消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="663d6-111">Client applications and message store providers</span></span>  <br/> |
   
```cpp
HRESULT SetAttribIMsgOnIStg(
  LPVOID lpObject,
  LPSPropTagArray lpPropTags,
  LPSPropAttrArray lpPropAttrs,
  LPSPropProblemArray FAR * lppPropProblems
);
```

## <a name="parameters"></a><span data-ttu-id="663d6-112">参数</span><span class="sxs-lookup"><span data-stu-id="663d6-112">Parameters</span></span>

 <span data-ttu-id="663d6-113">_lpObject_</span><span class="sxs-lookup"><span data-stu-id="663d6-113">_lpObject_</span></span>
  
> <span data-ttu-id="663d6-114">[in]指向属性设置的属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="663d6-114">[in] Pointer to the object for which property attributes are being set.</span></span> 
    
 <span data-ttu-id="663d6-115">_lpPropTags_</span><span class="sxs-lookup"><span data-stu-id="663d6-115">_lpPropTags_</span></span>
  
> <span data-ttu-id="663d6-116">[in]指向包含属性标记，指示属性设置的属性的属性的数组[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="663d6-116">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure containing an array of property tags indicating the properties for which property attributes are being set.</span></span> 
    
 <span data-ttu-id="663d6-117">_lpPropAttrs_</span><span class="sxs-lookup"><span data-stu-id="663d6-117">_lpPropAttrs_</span></span>
  
> <span data-ttu-id="663d6-118">[in]指向列出属性属性设置[SPropAttrArray](spropattrarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="663d6-118">[in] Pointer to an [SPropAttrArray](spropattrarray.md) structure listing the property attributes to set.</span></span> 
    
 <span data-ttu-id="663d6-119">_lppPropProblems_</span><span class="sxs-lookup"><span data-stu-id="663d6-119">_lppPropProblems_</span></span>
  
> <span data-ttu-id="663d6-120">[输出]返回[SPropProblemArray](spropproblemarray.md)结构包含一组属性问题的指针。</span><span class="sxs-lookup"><span data-stu-id="663d6-120">[out] Pointer to the returned [SPropProblemArray](spropproblemarray.md) structure containing a set of property problems.</span></span> <span data-ttu-id="663d6-121">此结构标识**SetAttribIMsgOnIStg**已能够设置某些属性，而不是全部如果遇到问题。</span><span class="sxs-lookup"><span data-stu-id="663d6-121">This structure identifies problems encountered if **SetAttribIMsgOnIStg** has been able to set some properties, but not all.</span></span> <span data-ttu-id="663d6-122">如果_lppPropProblems_参数中传递为 NULL 的指针，即使未设置某些属性，则返回没有属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="663d6-122">If a pointer to NULL is passed in the  _lppPropProblems_ parameter, no property problem array is returned even if some properties were not set.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="663d6-123">返回值</span><span class="sxs-lookup"><span data-stu-id="663d6-123">Return value</span></span>

<span data-ttu-id="663d6-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="663d6-124">S_OK</span></span> 
  
> <span data-ttu-id="663d6-125">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="663d6-125">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="663d6-126">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="663d6-126">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="663d6-127">调用成功总体上讲，但无法访问并已返回与 PT_ERROR 属性类型的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="663d6-127">The call succeeded overall, but one or more properties could not be accessed and were returned with a property type of PT_ERROR.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="663d6-128">注解</span><span class="sxs-lookup"><span data-stu-id="663d6-128">Remarks</span></span>

<span data-ttu-id="663d6-129">Property 属性只能在 property 对象，即，实现的对象上访问[IMAPIProp: IUnknown](imapipropiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="663d6-129">Property attributes can only be accessed on property objects, that is, objects implementing the [IMAPIProp : IUnknown](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="663d6-130">使 MAPI 属性 OLE 结构化的存储对象上可用， [OpenIMsgOnIStg](openimsgonistg.md)生成[IMessage: IMAPIProp](imessageimapiprop.md) OLE **IStorage**对象上的对象。</span><span class="sxs-lookup"><span data-stu-id="663d6-130">To make MAPI properties available on an OLE structured storage object, [OpenIMsgOnIStg](openimsgonistg.md) builds an [IMessage : IMAPIProp](imessageimapiprop.md) object on top of the OLE **IStorage** object.</span></span> <span data-ttu-id="663d6-131">此类对象上的属性属性可以设置或更改与**SetAttribIMsgOnIStg**和检索与[GetAttribIMsgOnIStg](getattribimsgonistg.md)。</span><span class="sxs-lookup"><span data-stu-id="663d6-131">The property attributes on such objects can be set or altered with **SetAttribIMsgOnIStg** and retrieved with [GetAttribIMsgOnIStg](getattribimsgonistg.md).</span></span> 
  
 <span data-ttu-id="663d6-132">**注释****GetAttribIMsgOnIStg**和**SetAttribIMsgOnIStg**请勿对所有**IMessage**对象。</span><span class="sxs-lookup"><span data-stu-id="663d6-132">**Note** **GetAttribIMsgOnIStg** and **SetAttribIMsgOnIStg** do not operate on all **IMessage** objects.</span></span> <span data-ttu-id="663d6-133">它们只是有效的**IMessage**上返回**OpenIMsgOnIStg** **IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="663d6-133">They are only valid for **IMessage**-on- **IStorage** objects returned by **OpenIMsgOnIStg**.</span></span> 
  
<span data-ttu-id="663d6-134">在_lpPropAttrs_参数的数量和位置的属性必须匹配的数量和_lpPropTags_参数中传递的属性标记的位置。</span><span class="sxs-lookup"><span data-stu-id="663d6-134">In the  _lpPropAttrs_ parameter, the number and position of the attributes must match the number and position of the property tags passed in the  _lpPropTags_ parameter.</span></span> 
  
<span data-ttu-id="663d6-135">**SetAttribIMsgOnIStg**函数用于只读时所需的**IMessage**架构进行邮件属性。</span><span class="sxs-lookup"><span data-stu-id="663d6-135">The **SetAttribIMsgOnIStg** function is used to make message properties read-only when required by the **IMessage** schema.</span></span> <span data-ttu-id="663d6-136">示例邮件存储提供程序将使用它实现此目的。</span><span class="sxs-lookup"><span data-stu-id="663d6-136">The sample message store provider uses it for this purpose.</span></span> <span data-ttu-id="663d6-137">有关详细信息，请参阅[消息](mapi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="663d6-137">For more information, see [Messages](mapi-messages.md).</span></span> 
  

