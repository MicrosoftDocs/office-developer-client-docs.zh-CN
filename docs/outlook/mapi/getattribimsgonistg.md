---
title: GetAttribIMsgOnIStg
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.GetAttribIMsgOnIStg
api_type:
- COM
ms.assetid: bb27b28a-b2bd-4d4a-b0bb-0692f3de8e16
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e17e8ef7df33ffa248eec4195c00c77d0c49f94
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587766"
---
# <a name="getattribimsgonistg"></a><span data-ttu-id="1f8f2-103">GetAttribIMsgOnIStg</span><span class="sxs-lookup"><span data-stu-id="1f8f2-103">GetAttribIMsgOnIStg</span></span>

  
  
<span data-ttu-id="1f8f2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f8f2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f8f2-105">检索上提供[OpenIMsgOnIStg](openimsgonistg.md)函数的[IMessage](imessageimapiprop.md)对象的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-105">Retrieves attributes of properties on an [IMessage](imessageimapiprop.md) object supplied by the [OpenIMsgOnIStg](openimsgonistg.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1f8f2-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="1f8f2-106">Header file:</span></span>  <br/> |<span data-ttu-id="1f8f2-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="1f8f2-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="1f8f2-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="1f8f2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1f8f2-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="1f8f2-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="1f8f2-110">调用：</span><span class="sxs-lookup"><span data-stu-id="1f8f2-110">Called by:</span></span>  <br/> |<span data-ttu-id="1f8f2-111">客户端应用程序和消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="1f8f2-111">Client applications and message store providers</span></span>  <br/> |
   
```cpp
HRESULT GetAttribIMsgOnIStg(
  LPVOID lpObject,
  LPSPropTagArray lpPropTagArray,
  LPSPropAttrArray FAR * lppPropAttrArray
);
```

## <a name="parameters"></a><span data-ttu-id="1f8f2-112">参数</span><span class="sxs-lookup"><span data-stu-id="1f8f2-112">Parameters</span></span>

 <span data-ttu-id="1f8f2-113">_lpObject_</span><span class="sxs-lookup"><span data-stu-id="1f8f2-113">_lpObject_</span></span>
  
> <span data-ttu-id="1f8f2-114">[in]对从[OpenIMsgOnIStg](openimsgonistg.md)函数获取**IMessage**对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-114">[in] Pointer to an **IMessage** object obtained from the [OpenIMsgOnIStg](openimsgonistg.md) function.</span></span> 
    
 <span data-ttu-id="1f8f2-115">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="1f8f2-115">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="1f8f2-116">[in]指向[SPropTagArray](sproptagarray.md)结构，其中包含数组属性标记，指示要为其检索属性的属性。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-116">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags indicating the properties for which attributes are to be retrieved.</span></span> 
    
 <span data-ttu-id="1f8f2-117">_lppPropAttrArray_</span><span class="sxs-lookup"><span data-stu-id="1f8f2-117">_lppPropAttrArray_</span></span>
  
> <span data-ttu-id="1f8f2-118">[输出]为包含检索的 property 属性的返回[SPropAttrArray](spropattrarray.md)结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-118">[out] Pointer to a pointer to the returned [SPropAttrArray](spropattrarray.md) structure that contains the retrieved property attributes.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1f8f2-119">返回值</span><span class="sxs-lookup"><span data-stu-id="1f8f2-119">Return value</span></span>

<span data-ttu-id="1f8f2-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f8f2-120">S_OK</span></span> 
  
> <span data-ttu-id="1f8f2-121">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-121">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="1f8f2-122">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="1f8f2-122">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="1f8f2-123">调用成功总体上讲，但无法访问并已返回与 PT_ERROR 属性类型的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-123">The call succeeded overall, but one or more properties could not be accessed and were returned with a property type of PT_ERROR.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1f8f2-124">注解</span><span class="sxs-lookup"><span data-stu-id="1f8f2-124">Remarks</span></span>

<span data-ttu-id="1f8f2-125">Property 属性只能在 property 对象，即，实现的对象上访问[IMAPIProp: IUnknown](imapipropiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-125">Property attributes can only be accessed on property objects, that is, objects implementing the [IMAPIProp : IUnknown](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="1f8f2-126">使 MAPI 属性 OLE 结构化的存储对象上可用， [OpenIMsgOnIStg](openimsgonistg.md)生成[IMessage: IMAPIProp](imessageimapiprop.md) OLE **IStorage**对象上的对象。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-126">To make MAPI properties available on an OLE structured storage object, [OpenIMsgOnIStg](openimsgonistg.md) builds an [IMessage : IMAPIProp](imessageimapiprop.md) object on top of the OLE **IStorage** object.</span></span> <span data-ttu-id="1f8f2-127">此类对象上的属性属性可以设置或更改与[SetAttribIMsgOnIStg](setattribimsgonistg.md)和检索与**GetAttribIMsgOnIStg**。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-127">The property attributes on such objects can be set or altered with [SetAttribIMsgOnIStg](setattribimsgonistg.md) and retrieved with **GetAttribIMsgOnIStg**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1f8f2-128">**GetAttribIMsgOnIStg**和**SetAttribIMsgOnIStg**请勿对所有**IMessage**对象。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-128">**GetAttribIMsgOnIStg** and **SetAttribIMsgOnIStg** do not operate on all **IMessage** objects.</span></span> <span data-ttu-id="1f8f2-129">它们只是有效的**IMessage**上返回**OpenIMsgOnIStg** **IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-129">They are only valid for **IMessage**-on- **IStorage** objects returned by **OpenIMsgOnIStg**.</span></span> 
  
<span data-ttu-id="1f8f2-130">数目和_lppPropAttrArray_参数中的位置的属性对应于的数量和_lpPropTagArray_参数中的属性标记的位置。</span><span class="sxs-lookup"><span data-stu-id="1f8f2-130">The number and positions of the attributes in the  _lppPropAttrArray_ parameter correspond to the number and positions of the property tags in the  _lpPropTagArray_ parameter.</span></span> 
  

