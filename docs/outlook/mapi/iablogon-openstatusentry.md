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
ms.openlocfilehash: cb9a2ba72ee9fd9c45aefe9d0797930a4871404a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579282"
---
# <a name="iablogonopenstatusentry"></a><span data-ttu-id="68e7a-103">IABLogon::OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="68e7a-103">IABLogon::OpenStatusEntry</span></span>

  
  
<span data-ttu-id="68e7a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="68e7a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="68e7a-105">打开提供程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="68e7a-105">Opens the provider's status object.</span></span>
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPMAPISTATUS FAR * lppEntry
);
```

## <a name="parameters"></a><span data-ttu-id="68e7a-106">参数</span><span class="sxs-lookup"><span data-stu-id="68e7a-106">Parameters</span></span>

 <span data-ttu-id="68e7a-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="68e7a-107">_lpInterface_</span></span>
  
> <span data-ttu-id="68e7a-108">[in]指向接口标识 (IID) 表示必须用于访问状态对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="68e7a-108">[in] A pointer to the interface identifier (IID) that represents the interface that must be used to access the status object.</span></span> <span data-ttu-id="68e7a-109">如果传递 NULL 返回对象的标准接口， [IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="68e7a-109">Passing NULL returns the object's standard interface, [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md).</span></span>
    
 <span data-ttu-id="68e7a-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="68e7a-110">_ulFlags_</span></span>
  
> <span data-ttu-id="68e7a-111">[in]位掩码的标志，控制如何打开状态对象。</span><span class="sxs-lookup"><span data-stu-id="68e7a-111">[in] A bitmask of flags that controls how the status object is opened.</span></span> <span data-ttu-id="68e7a-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="68e7a-112">The following flag can be set:</span></span>
    
<span data-ttu-id="68e7a-113">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="68e7a-113">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="68e7a-114">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="68e7a-114">Requests read/write permission.</span></span> <span data-ttu-id="68e7a-115">默认情况下，对象打开具有只读访问权限和呼叫者不应假定已被授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="68e7a-115">By default, objects are opened with read-only access, and callers should not assume that read/write permission has been granted.</span></span>
    
 <span data-ttu-id="68e7a-116">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="68e7a-116">_lpulObjType_</span></span>
  
> <span data-ttu-id="68e7a-117">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="68e7a-117">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="68e7a-118">_lppEntry_</span><span class="sxs-lookup"><span data-stu-id="68e7a-118">_lppEntry_</span></span>
  
> <span data-ttu-id="68e7a-119">[输出]指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="68e7a-119">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="68e7a-120">返回值</span><span class="sxs-lookup"><span data-stu-id="68e7a-120">Return value</span></span>

<span data-ttu-id="68e7a-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="68e7a-121">S_OK</span></span> 
  
> <span data-ttu-id="68e7a-122">调用成功，并已打开状态对象。</span><span class="sxs-lookup"><span data-stu-id="68e7a-122">The call succeeded and the status object has been opened.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="68e7a-123">注解</span><span class="sxs-lookup"><span data-stu-id="68e7a-123">Remarks</span></span>

<span data-ttu-id="68e7a-124">通讯簿提供程序实现**OpenStatusEntry**方法向其状态对象授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="68e7a-124">Address book providers implement the **OpenStatusEntry** method to grant access to their status object.</span></span> <span data-ttu-id="68e7a-125">所有通讯簿提供程序所都需实现支持，最少， [IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法状态对象。</span><span class="sxs-lookup"><span data-stu-id="68e7a-125">All address book providers are required to implement a status object that supports, at a minimum, the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="68e7a-126">有关详细信息，请参阅[状态对象实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="68e7a-126">For more information, see [Status Object Implementation](status-object-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="68e7a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68e7a-127">See also</span></span>



[<span data-ttu-id="68e7a-128">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="68e7a-128">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)
  
[<span data-ttu-id="68e7a-129">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="68e7a-129">IMAPIStatus::SettingsDialog</span></span>](imapistatus-settingsdialog.md)
  
[<span data-ttu-id="68e7a-130">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="68e7a-130">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
  
[<span data-ttu-id="68e7a-131">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="68e7a-131">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

