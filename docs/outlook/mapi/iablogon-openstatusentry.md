---
title: IABLogonOpenStatusEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.OpenStatusEntry
api_type:
- COM
ms.assetid: 66f1e246-a67a-4f8a-ae3a-6a8ec8c2b367
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e693e1c3d6cb975a3a329e15c0b1a6d08817461a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775216"
---
# <a name="iablogonopenstatusentry"></a><span data-ttu-id="d241e-103">IABLogon::OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="d241e-103">IABLogon::OpenStatusEntry</span></span>

  
  
<span data-ttu-id="d241e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d241e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d241e-105">打开提供程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="d241e-105">Opens the provider's status object.</span></span>
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPMAPISTATUS FAR * lppEntry
);
```

## <a name="parameters"></a><span data-ttu-id="d241e-106">参数</span><span class="sxs-lookup"><span data-stu-id="d241e-106">Parameters</span></span>

 <span data-ttu-id="d241e-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="d241e-107">_lpInterface_</span></span>
  
> <span data-ttu-id="d241e-108">[in]指向接口标识 (IID) 表示必须用于访问状态对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="d241e-108">[in] A pointer to the interface identifier (IID) that represents the interface that must be used to access the status object.</span></span> <span data-ttu-id="d241e-109">如果传递 NULL 返回对象的标准接口， [IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="d241e-109">Passing NULL returns the object's standard interface, [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md).</span></span>
    
 <span data-ttu-id="d241e-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d241e-110">_ulFlags_</span></span>
  
> <span data-ttu-id="d241e-111">[in]位掩码的标志，控制如何打开状态对象。</span><span class="sxs-lookup"><span data-stu-id="d241e-111">[in] A bitmask of flags that controls how the status object is opened.</span></span> <span data-ttu-id="d241e-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="d241e-112">The following flag can be set:</span></span>
    
<span data-ttu-id="d241e-113">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="d241e-113">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="d241e-114">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="d241e-114">Requests read/write permission.</span></span> <span data-ttu-id="d241e-115">默认情况下，对象打开具有只读访问权限和呼叫者不应假定已被授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="d241e-115">By default, objects are opened with read-only access, and callers should not assume that read/write permission has been granted.</span></span>
    
 <span data-ttu-id="d241e-116">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="d241e-116">_lpulObjType_</span></span>
  
> <span data-ttu-id="d241e-117">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="d241e-117">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="d241e-118">_lppEntry_</span><span class="sxs-lookup"><span data-stu-id="d241e-118">_lppEntry_</span></span>
  
> <span data-ttu-id="d241e-119">[输出]指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d241e-119">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d241e-120">返回值</span><span class="sxs-lookup"><span data-stu-id="d241e-120">Return value</span></span>

<span data-ttu-id="d241e-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="d241e-121">S_OK</span></span> 
  
> <span data-ttu-id="d241e-122">调用成功，并已打开状态对象。</span><span class="sxs-lookup"><span data-stu-id="d241e-122">The call succeeded and the status object has been opened.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d241e-123">说明</span><span class="sxs-lookup"><span data-stu-id="d241e-123">Remarks</span></span>

<span data-ttu-id="d241e-124">通讯簿提供程序实现**OpenStatusEntry**方法向其状态对象授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="d241e-124">Address book providers implement the **OpenStatusEntry** method to grant access to their status object.</span></span> <span data-ttu-id="d241e-125">所有通讯簿提供程序所都需实现支持，最少， [IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法状态对象。</span><span class="sxs-lookup"><span data-stu-id="d241e-125">All address book providers are required to implement a status object that supports, at a minimum, the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="d241e-126">有关详细信息，请参阅[状态对象实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="d241e-126">For more information, see [Status Object Implementation](status-object-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d241e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d241e-127">See also</span></span>



[<span data-ttu-id="d241e-128">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d241e-128">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)
  
[<span data-ttu-id="d241e-129">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="d241e-129">IMAPIStatus::SettingsDialog</span></span>](imapistatus-settingsdialog.md)
  
[<span data-ttu-id="d241e-130">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="d241e-130">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
  
[<span data-ttu-id="d241e-131">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d241e-131">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

