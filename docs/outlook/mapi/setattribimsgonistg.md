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
ms.openlocfilehash: 852ce31ba5ab02ff8f05dee25c9b32acb73130ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428828"
---
# <a name="setattribimsgonistg"></a><span data-ttu-id="26c31-103">SetAttribIMsgOnIStg</span><span class="sxs-lookup"><span data-stu-id="26c31-103">SetAttribIMsgOnIStg</span></span>

  
  
<span data-ttu-id="26c31-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="26c31-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="26c31-105">设置或更改[OpenIMsgOnIStg](openimsgonistg.md)函数提供的[IMessage](imessageimapiprop.md)对象的属性属性。</span><span class="sxs-lookup"><span data-stu-id="26c31-105">Sets or alters attributes of properties on an [IMessage](imessageimapiprop.md) object supplied by the [OpenIMsgOnIStg](openimsgonistg.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="26c31-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="26c31-106">Header file:</span></span>  <br/> |<span data-ttu-id="26c31-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="26c31-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="26c31-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="26c31-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="26c31-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="26c31-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="26c31-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="26c31-110">Called by:</span></span>  <br/> |<span data-ttu-id="26c31-111">客户端应用程序和邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="26c31-111">Client applications and message store providers</span></span>  <br/> |
   
```cpp
HRESULT SetAttribIMsgOnIStg(
  LPVOID lpObject,
  LPSPropTagArray lpPropTags,
  LPSPropAttrArray lpPropAttrs,
  LPSPropProblemArray FAR * lppPropProblems
);
```

## <a name="parameters"></a><span data-ttu-id="26c31-112">参数</span><span class="sxs-lookup"><span data-stu-id="26c31-112">Parameters</span></span>

 <span data-ttu-id="26c31-113">_lpObject_</span><span class="sxs-lookup"><span data-stu-id="26c31-113">_lpObject_</span></span>
  
> <span data-ttu-id="26c31-114">[in]指向要设置其属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="26c31-114">[in] Pointer to the object for which property attributes are being set.</span></span> 
    
 <span data-ttu-id="26c31-115">_lpPropTags_</span><span class="sxs-lookup"><span data-stu-id="26c31-115">_lpPropTags_</span></span>
  
> <span data-ttu-id="26c31-116">[in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，该结构包含一组指示要设置的属性属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="26c31-116">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure containing an array of property tags indicating the properties for which property attributes are being set.</span></span> 
    
 <span data-ttu-id="26c31-117">_lpPropAttrs_</span><span class="sxs-lookup"><span data-stu-id="26c31-117">_lpPropAttrs_</span></span>
  
> <span data-ttu-id="26c31-118">[in]指向列出要设置的属性属性的 [SPropAttrArray](spropattrarray.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="26c31-118">[in] Pointer to an [SPropAttrArray](spropattrarray.md) structure listing the property attributes to set.</span></span> 
    
 <span data-ttu-id="26c31-119">_lppPropProblems_</span><span class="sxs-lookup"><span data-stu-id="26c31-119">_lppPropProblems_</span></span>
  
> <span data-ttu-id="26c31-120">[out]指向返回的包含一组属性问题的 [SPropProblemArray](spropproblemarray.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="26c31-120">[out] Pointer to the returned [SPropProblemArray](spropproblemarray.md) structure containing a set of property problems.</span></span> <span data-ttu-id="26c31-121">此结构标识 **SetAttribIMsgOnIStg** 能够设置某些属性（而不是所有属性）时遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="26c31-121">This structure identifies problems encountered if **SetAttribIMsgOnIStg** has been able to set some properties, but not all.</span></span> <span data-ttu-id="26c31-122">如果在  _lppPropProblems_ 参数中传递指向 NULL 的指针，则即使未设置某些属性，也将不会返回任何属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="26c31-122">If a pointer to NULL is passed in the  _lppPropProblems_ parameter, no property problem array is returned even if some properties were not set.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="26c31-123">返回值</span><span class="sxs-lookup"><span data-stu-id="26c31-123">Return value</span></span>

<span data-ttu-id="26c31-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="26c31-124">S_OK</span></span> 
  
> <span data-ttu-id="26c31-125">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="26c31-125">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="26c31-126">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="26c31-126">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="26c31-127">调用整体成功，但无法访问一个或多个属性，并且返回的属性类型为 PT_ERROR。</span><span class="sxs-lookup"><span data-stu-id="26c31-127">The call succeeded overall, but one or more properties could not be accessed and were returned with a property type of PT_ERROR.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="26c31-128">备注</span><span class="sxs-lookup"><span data-stu-id="26c31-128">Remarks</span></span>

<span data-ttu-id="26c31-129">只能在属性对象（即实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 接口的对象）上访问属性属性。</span><span class="sxs-lookup"><span data-stu-id="26c31-129">Property attributes can only be accessed on property objects, that is, objects implementing the [IMAPIProp : IUnknown](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="26c31-130">若要使 MAPI 属性在 OLE 结构化存储对象上可用 [，OpenIMsgOnIStg](openimsgonistg.md)在 OLE **IStorage** 对象顶部构建 [IMessage ： IMAPIProp](imessageimapiprop.md)对象。</span><span class="sxs-lookup"><span data-stu-id="26c31-130">To make MAPI properties available on an OLE structured storage object, [OpenIMsgOnIStg](openimsgonistg.md) builds an [IMessage : IMAPIProp](imessageimapiprop.md) object on top of the OLE **IStorage** object.</span></span> <span data-ttu-id="26c31-131">可以使用 **SetAttribIMsgOnIStg** 设置或更改此类对象的属性属性，然后使用 [GetAttribIMsgOnIStg 进行检索](getattribimsgonistg.md)。</span><span class="sxs-lookup"><span data-stu-id="26c31-131">The property attributes on such objects can be set or altered with **SetAttribIMsgOnIStg** and retrieved with [GetAttribIMsgOnIStg](getattribimsgonistg.md).</span></span> 
  
 <span data-ttu-id="26c31-132">**注意\*\*\*\*GetAttribIMsgOnIStg** 和 **SetAttribIMsgOnIStg** 不在所有 **IMessage** 对象上操作。</span><span class="sxs-lookup"><span data-stu-id="26c31-132">**Note** **GetAttribIMsgOnIStg** and **SetAttribIMsgOnIStg** do not operate on all **IMessage** objects.</span></span> <span data-ttu-id="26c31-133">它们仅对 **OpenIMsgOnIStg** 返回的 **IMessage**-on- **IStorage** 对象有效。</span><span class="sxs-lookup"><span data-stu-id="26c31-133">They are only valid for **IMessage**-on- **IStorage** objects returned by **OpenIMsgOnIStg**.</span></span> 
  
<span data-ttu-id="26c31-134">在  _lpPropAttrs_ 参数中，属性的数量和位置必须与在  _lpPropTags_ 参数中传递的属性标记的数量和位置相匹配。</span><span class="sxs-lookup"><span data-stu-id="26c31-134">In the  _lpPropAttrs_ parameter, the number and position of the attributes must match the number and position of the property tags passed in the  _lpPropTags_ parameter.</span></span> 
  
<span data-ttu-id="26c31-135">**SetAttribIMsgOnIStg** 函数用于使邮件属性在 **IMessage** 架构需要时为只读。</span><span class="sxs-lookup"><span data-stu-id="26c31-135">The **SetAttribIMsgOnIStg** function is used to make message properties read-only when required by the **IMessage** schema.</span></span> <span data-ttu-id="26c31-136">示例邮件存储提供程序会使用它来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="26c31-136">The sample message store provider uses it for this purpose.</span></span> <span data-ttu-id="26c31-137">有关详细信息， [请参阅邮件](mapi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="26c31-137">For more information, see [Messages](mapi-messages.md).</span></span> 
  

