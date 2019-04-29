---
title: IPropDataHrSetObjAccess
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData.HrSetObjAccess
api_type:
- COM
ms.assetid: 01bd3235-22cc-4ff3-b2b6-341ce622128b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4e478c9e8978125a37691ee5bd97fa9f1cbce077
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425153"
---
# <a name="ipropdatahrsetobjaccess"></a><span data-ttu-id="57255-103">IPropData::HrSetObjAccess</span><span class="sxs-lookup"><span data-stu-id="57255-103">IPropData::HrSetObjAccess</span></span>

  
  
<span data-ttu-id="57255-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="57255-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="57255-105">设置对象的访问级别。</span><span class="sxs-lookup"><span data-stu-id="57255-105">Sets the access level for the object.</span></span>
  
```cpp
HRESULT HrSetObjAccess(
  ULONG ulAccess
);
```

## <a name="parameters"></a><span data-ttu-id="57255-106">参数</span><span class="sxs-lookup"><span data-stu-id="57255-106">Parameters</span></span>

 <span data-ttu-id="57255-107">_ulAccess_</span><span class="sxs-lookup"><span data-stu-id="57255-107">_ulAccess_</span></span>
  
> <span data-ttu-id="57255-108">实时指定对象的访问级别的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="57255-108">[in] A bitmask of flags that specifies the object's access level.</span></span> <span data-ttu-id="57255-109">可以设置下列标志之一:</span><span class="sxs-lookup"><span data-stu-id="57255-109">One of the following flags can be set:</span></span>
    
<span data-ttu-id="57255-110">IPROP_READONLY</span><span class="sxs-lookup"><span data-stu-id="57255-110">IPROP_READONLY</span></span> 
  
> <span data-ttu-id="57255-111">将对象的访问级别设置为只读。</span><span class="sxs-lookup"><span data-stu-id="57255-111">Sets the object's access level to read-only.</span></span> 
    
<span data-ttu-id="57255-112">IPROP_READWRITE</span><span class="sxs-lookup"><span data-stu-id="57255-112">IPROP_READWRITE</span></span> 
  
> <span data-ttu-id="57255-113">将对象的访问级别设置为 "读/写"。</span><span class="sxs-lookup"><span data-stu-id="57255-113">Sets the object's access level to read/write.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="57255-114">返回值</span><span class="sxs-lookup"><span data-stu-id="57255-114">Return value</span></span>

<span data-ttu-id="57255-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="57255-115">S_OK</span></span> 
  
> <span data-ttu-id="57255-116">已成功设置对象的访问级别。</span><span class="sxs-lookup"><span data-stu-id="57255-116">The object's access level was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="57255-117">说明</span><span class="sxs-lookup"><span data-stu-id="57255-117">Remarks</span></span>

<span data-ttu-id="57255-118">**IPropData:: HrSetObjAccess**方法设置整个对象的访问级别, 而不是设置各个属性的访问级别。</span><span class="sxs-lookup"><span data-stu-id="57255-118">The **IPropData::HrSetObjAccess** method sets the access level for an entire object, rather than for individual properties.</span></span> <span data-ttu-id="57255-119">**HrSetObjAccess**可用于更改创建对象时建立的访问级别。</span><span class="sxs-lookup"><span data-stu-id="57255-119">**HrSetObjAccess** can be used to change the access level established when the object was created.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="57255-120">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="57255-120">Notes to callers</span></span>

<span data-ttu-id="57255-121">若要设置属性的访问级别, 请先使用_ulAccess_参数中设置的 IPROP_READWRITE 标志调用**HrSetObjAccess** , 使该对象可修改。</span><span class="sxs-lookup"><span data-stu-id="57255-121">To set an access level on a property, first call **HrSetObjAccess** with the IPROP_READWRITE flag set in the  _ulAccess_ parameter to make the object modifiable.</span></span> <span data-ttu-id="57255-122">然后, 调用[IPropData:: HrSetPropAccess](ipropdata-hrsetpropaccess.md)方法, 在由_lpPropTagArray_参数指向的数组中指定目标属性。</span><span class="sxs-lookup"><span data-stu-id="57255-122">Then call the [IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md) method, specifying the target property in the array pointed to by the  _lpPropTagArray_ parameter.</span></span> 
  
<span data-ttu-id="57255-123">若要创建具有对客户端只读属性的对象, 请创建一个读/写对象, 添加所需的属性, 然后调用**HrSetObjAccess**将该对象的访问权限更改为只读。</span><span class="sxs-lookup"><span data-stu-id="57255-123">To create an object with properties that will be read-only to clients, create a read/write object, add the necessary properties, and then call **HrSetObjAccess** to change the object's access to read-only.</span></span> 
  
<span data-ttu-id="57255-124">您还可以使用**HrSetObjAccess**来阻止客户端创建新属性。</span><span class="sxs-lookup"><span data-stu-id="57255-124">You can also use **HrSetObjAccess** to prevent clients from creating new properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="57255-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57255-125">See also</span></span>



[<span data-ttu-id="57255-126">IPropData::HrGetPropAccess</span><span class="sxs-lookup"><span data-stu-id="57255-126">IPropData::HrGetPropAccess</span></span>](ipropdata-hrgetpropaccess.md)
  
[<span data-ttu-id="57255-127">IPropData::HrSetPropAccess</span><span class="sxs-lookup"><span data-stu-id="57255-127">IPropData::HrSetPropAccess</span></span>](ipropdata-hrsetpropaccess.md)
  
[<span data-ttu-id="57255-128">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="57255-128">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)

