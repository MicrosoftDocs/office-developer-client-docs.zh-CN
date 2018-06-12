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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 06cad6e80a2def1c1c3d692a80efeebe0e654a92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776004"
---
# <a name="ipropdatahrsetobjaccess"></a><span data-ttu-id="e7659-103">IPropData::HrSetObjAccess</span><span class="sxs-lookup"><span data-stu-id="e7659-103">IPropData::HrSetObjAccess</span></span>

  
  
<span data-ttu-id="e7659-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e7659-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e7659-105">设置该对象的访问级别。</span><span class="sxs-lookup"><span data-stu-id="e7659-105">Sets the access level for the object.</span></span>
  
```cpp
HRESULT HrSetObjAccess(
  ULONG ulAccess
);
```

## <a name="parameters"></a><span data-ttu-id="e7659-106">参数</span><span class="sxs-lookup"><span data-stu-id="e7659-106">Parameters</span></span>

 <span data-ttu-id="e7659-107">_ulAccess_</span><span class="sxs-lookup"><span data-stu-id="e7659-107">_ulAccess_</span></span>
  
> <span data-ttu-id="e7659-108">[in]位掩码的标志，指定对象的访问级别。</span><span class="sxs-lookup"><span data-stu-id="e7659-108">[in] A bitmask of flags that specifies the object's access level.</span></span> <span data-ttu-id="e7659-109">可以设置以下标志之一：</span><span class="sxs-lookup"><span data-stu-id="e7659-109">One of the following flags can be set:</span></span>
    
<span data-ttu-id="e7659-110">IPROP_READONLY</span><span class="sxs-lookup"><span data-stu-id="e7659-110">IPROP_READONLY</span></span> 
  
> <span data-ttu-id="e7659-111">将对象的访问级别设置为只读的。</span><span class="sxs-lookup"><span data-stu-id="e7659-111">Sets the object's access level to read-only.</span></span> 
    
<span data-ttu-id="e7659-112">IPROP_READWRITE</span><span class="sxs-lookup"><span data-stu-id="e7659-112">IPROP_READWRITE</span></span> 
  
> <span data-ttu-id="e7659-113">设置对象的访问级别，以读/写。</span><span class="sxs-lookup"><span data-stu-id="e7659-113">Sets the object's access level to read/write.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e7659-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e7659-114">Return value</span></span>

<span data-ttu-id="e7659-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7659-115">S_OK</span></span> 
  
> <span data-ttu-id="e7659-116">成功将对象的访问级别设置。</span><span class="sxs-lookup"><span data-stu-id="e7659-116">The object's access level was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e7659-117">备注</span><span class="sxs-lookup"><span data-stu-id="e7659-117">Remarks</span></span>

<span data-ttu-id="e7659-118">**IPropData::HrSetObjAccess**方法将设置为整个对象，而不是为各个属性的访问级别。</span><span class="sxs-lookup"><span data-stu-id="e7659-118">The **IPropData::HrSetObjAccess** method sets the access level for an entire object, rather than for individual properties.</span></span> <span data-ttu-id="e7659-119">**HrSetObjAccess**可用于更改时创建的对象已建立的访问级别。</span><span class="sxs-lookup"><span data-stu-id="e7659-119">**HrSetObjAccess** can be used to change the access level established when the object was created.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e7659-120">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e7659-120">Notes to callers</span></span>

<span data-ttu-id="e7659-121">若要设置属性的某个访问级别，请首先调用_ulAccess_参数中的设置以使该对象可修改了 IPROP_READWRITE 标记**HrSetObjAccess** 。</span><span class="sxs-lookup"><span data-stu-id="e7659-121">To set an access level on a property, first call **HrSetObjAccess** with the IPROP_READWRITE flag set in the  _ulAccess_ parameter to make the object modifiable.</span></span> <span data-ttu-id="e7659-122">然后调用[IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md)方法， _lpPropTagArray_参数指向该数组中指定的目标属性。</span><span class="sxs-lookup"><span data-stu-id="e7659-122">Then call the [IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md) method, specifying the target property in the array pointed to by the  _lpPropTagArray_ parameter.</span></span> 
  
<span data-ttu-id="e7659-123">只读向客户端将与创建对象，创建读/写对象和添加必需属性，然后调用**HrSetObjAccess**更改为只读的对象的访问。</span><span class="sxs-lookup"><span data-stu-id="e7659-123">To create an object with properties that will be read-only to clients, create a read/write object, add the necessary properties, and then call **HrSetObjAccess** to change the object's access to read-only.</span></span> 
  
<span data-ttu-id="e7659-124">您可以使用**HrSetObjAccess**以防止客户端创建新的属性。</span><span class="sxs-lookup"><span data-stu-id="e7659-124">You can also use **HrSetObjAccess** to prevent clients from creating new properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e7659-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7659-125">See also</span></span>



[<span data-ttu-id="e7659-126">IPropData::HrGetPropAccess</span><span class="sxs-lookup"><span data-stu-id="e7659-126">IPropData::HrGetPropAccess</span></span>](ipropdata-hrgetpropaccess.md)
  
[<span data-ttu-id="e7659-127">IPropData::HrSetPropAccess</span><span class="sxs-lookup"><span data-stu-id="e7659-127">IPropData::HrSetPropAccess</span></span>](ipropdata-hrsetpropaccess.md)
  
[<span data-ttu-id="e7659-128">IPropData: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="e7659-128">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)

