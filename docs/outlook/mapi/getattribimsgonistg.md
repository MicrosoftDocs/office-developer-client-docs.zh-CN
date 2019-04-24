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
ms.openlocfilehash: 16e85eabc067bd82f5fb89c917afaf2831c75673
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300467"
---
# <a name="getattribimsgonistg"></a><span data-ttu-id="f1aea-103">GetAttribIMsgOnIStg</span><span class="sxs-lookup"><span data-stu-id="f1aea-103">GetAttribIMsgOnIStg</span></span>

  
  
<span data-ttu-id="f1aea-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1aea-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1aea-105">检索[OpenIMsgOnIStg](openimsgonistg.md)函数提供的[IMessage](imessageimapiprop.md)对象上属性的属性。</span><span class="sxs-lookup"><span data-stu-id="f1aea-105">Retrieves attributes of properties on an [IMessage](imessageimapiprop.md) object supplied by the [OpenIMsgOnIStg](openimsgonistg.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f1aea-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f1aea-106">Header file:</span></span>  <br/> |<span data-ttu-id="f1aea-107">Imessage</span><span class="sxs-lookup"><span data-stu-id="f1aea-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="f1aea-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="f1aea-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f1aea-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f1aea-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f1aea-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="f1aea-110">Called by:</span></span>  <br/> |<span data-ttu-id="f1aea-111">客户端应用程序和邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="f1aea-111">Client applications and message store providers</span></span>  <br/> |
   
```cpp
HRESULT GetAttribIMsgOnIStg(
  LPVOID lpObject,
  LPSPropTagArray lpPropTagArray,
  LPSPropAttrArray FAR * lppPropAttrArray
);
```

## <a name="parameters"></a><span data-ttu-id="f1aea-112">参数</span><span class="sxs-lookup"><span data-stu-id="f1aea-112">Parameters</span></span>

 <span data-ttu-id="f1aea-113">_lpObject_</span><span class="sxs-lookup"><span data-stu-id="f1aea-113">_lpObject_</span></span>
  
> <span data-ttu-id="f1aea-114">实时指向从[OpenIMsgOnIStg](openimsgonistg.md)函数获取的**IMessage**对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f1aea-114">[in] Pointer to an **IMessage** object obtained from the [OpenIMsgOnIStg](openimsgonistg.md) function.</span></span> 
    
 <span data-ttu-id="f1aea-115">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="f1aea-115">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="f1aea-116">实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含一个指明要检索其属性的属性的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="f1aea-116">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags indicating the properties for which attributes are to be retrieved.</span></span> 
    
 <span data-ttu-id="f1aea-117">_lppPropAttrArray_</span><span class="sxs-lookup"><span data-stu-id="f1aea-117">_lppPropAttrArray_</span></span>
  
> <span data-ttu-id="f1aea-118">排除指向指向包含检索到的属性属性的返回[SPropAttrArray](spropattrarray.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f1aea-118">[out] Pointer to a pointer to the returned [SPropAttrArray](spropattrarray.md) structure that contains the retrieved property attributes.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f1aea-119">返回值</span><span class="sxs-lookup"><span data-stu-id="f1aea-119">Return value</span></span>

<span data-ttu-id="f1aea-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1aea-120">S_OK</span></span> 
  
> <span data-ttu-id="f1aea-121">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="f1aea-121">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="f1aea-122">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="f1aea-122">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="f1aea-123">调用全部成功, 但无法访问一个或多个属性, 并使用 PT_ERROR 的属性类型返回。</span><span class="sxs-lookup"><span data-stu-id="f1aea-123">The call succeeded overall, but one or more properties could not be accessed and were returned with a property type of PT_ERROR.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f1aea-124">注解</span><span class="sxs-lookup"><span data-stu-id="f1aea-124">Remarks</span></span>

<span data-ttu-id="f1aea-125">只能在属性对象 (即实现[IMAPIProp: IUnknown](imapipropiunknown.md)接口的对象) 上访问属性属性。</span><span class="sxs-lookup"><span data-stu-id="f1aea-125">Property attributes can only be accessed on property objects, that is, objects implementing the [IMAPIProp : IUnknown](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="f1aea-126">若要使 MAPI 属性在 ole 结构化存储对象上可用, [OpenIMsgOnIStg](openimsgonistg.md)在 ole **IStorage**对象的顶部生成[IMessage: IMAPIProp](imessageimapiprop.md)对象。</span><span class="sxs-lookup"><span data-stu-id="f1aea-126">To make MAPI properties available on an OLE structured storage object, [OpenIMsgOnIStg](openimsgonistg.md) builds an [IMessage : IMAPIProp](imessageimapiprop.md) object on top of the OLE **IStorage** object.</span></span> <span data-ttu-id="f1aea-127">此类对象上的属性属性可以使用[SetAttribIMsgOnIStg](setattribimsgonistg.md)进行设置或更改, 并可使用**GetAttribIMsgOnIStg**进行检索。</span><span class="sxs-lookup"><span data-stu-id="f1aea-127">The property attributes on such objects can be set or altered with [SetAttribIMsgOnIStg](setattribimsgonistg.md) and retrieved with **GetAttribIMsgOnIStg**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f1aea-128">**GetAttribIMsgOnIStg**和**SetAttribIMsgOnIStg**不对所有**IMessage**对象进行操作。</span><span class="sxs-lookup"><span data-stu-id="f1aea-128">**GetAttribIMsgOnIStg** and **SetAttribIMsgOnIStg** do not operate on all **IMessage** objects.</span></span> <span data-ttu-id="f1aea-129">它们仅对**OpenIMsgOnIStg**返回的**IMessage** **IStorage**对象有效。</span><span class="sxs-lookup"><span data-stu-id="f1aea-129">They are only valid for **IMessage**-on- **IStorage** objects returned by **OpenIMsgOnIStg**.</span></span> 
  
<span data-ttu-id="f1aea-130">_lppPropAttrArray_参数中属性的数目和位置对应于_lpPropTagArray_参数中的属性标记的编号和位置。</span><span class="sxs-lookup"><span data-stu-id="f1aea-130">The number and positions of the attributes in the  _lppPropAttrArray_ parameter correspond to the number and positions of the property tags in the  _lpPropTagArray_ parameter.</span></span> 
  

