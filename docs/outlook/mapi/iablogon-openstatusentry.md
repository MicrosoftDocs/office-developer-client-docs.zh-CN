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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 22f98e52444b17c383737bffd1685df0fb7ba8bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410782"
---
# <a name="iablogonopenstatusentry"></a><span data-ttu-id="f4ae3-103">IABLogon::OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="f4ae3-103">IABLogon::OpenStatusEntry</span></span>

  
  
<span data-ttu-id="f4ae3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f4ae3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f4ae3-105">打开提供程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-105">Opens the provider's status object.</span></span>
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPMAPISTATUS FAR * lppEntry
);
```

## <a name="parameters"></a><span data-ttu-id="f4ae3-106">参数</span><span class="sxs-lookup"><span data-stu-id="f4ae3-106">Parameters</span></span>

 <span data-ttu-id="f4ae3-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="f4ae3-107">_lpInterface_</span></span>
  
> <span data-ttu-id="f4ae3-108">[in]指向接口标识符的指针 (IID) 表示必须用于访问状态对象的接口。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-108">[in] A pointer to the interface identifier (IID) that represents the interface that must be used to access the status object.</span></span> <span data-ttu-id="f4ae3-109">传递 NULL 将返回对象的标准接口 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-109">Passing NULL returns the object's standard interface, [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md).</span></span>
    
 <span data-ttu-id="f4ae3-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f4ae3-110">_ulFlags_</span></span>
  
> <span data-ttu-id="f4ae3-111">[in]控制状态对象的打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-111">[in] A bitmask of flags that controls how the status object is opened.</span></span> <span data-ttu-id="f4ae3-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="f4ae3-112">The following flag can be set:</span></span>
    
<span data-ttu-id="f4ae3-113">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="f4ae3-113">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="f4ae3-114">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-114">Requests read/write permission.</span></span> <span data-ttu-id="f4ae3-115">默认情况下，使用只读访问权限打开对象，调用方不应假定已授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-115">By default, objects are opened with read-only access, and callers should not assume that read/write permission has been granted.</span></span>
    
 <span data-ttu-id="f4ae3-116">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="f4ae3-116">_lpulObjType_</span></span>
  
> <span data-ttu-id="f4ae3-117">[out]指向已打开对象的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-117">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="f4ae3-118">_lppEntry_</span><span class="sxs-lookup"><span data-stu-id="f4ae3-118">_lppEntry_</span></span>
  
> <span data-ttu-id="f4ae3-119">[out]指向已打开对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-119">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f4ae3-120">返回值</span><span class="sxs-lookup"><span data-stu-id="f4ae3-120">Return value</span></span>

<span data-ttu-id="f4ae3-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4ae3-121">S_OK</span></span> 
  
> <span data-ttu-id="f4ae3-122">调用成功，并且状态对象已打开。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-122">The call succeeded and the status object has been opened.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f4ae3-123">备注</span><span class="sxs-lookup"><span data-stu-id="f4ae3-123">Remarks</span></span>

<span data-ttu-id="f4ae3-124">通讯簿提供程序实现 **OpenStatusEntry** 方法以授予访问其状态对象的权限。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-124">Address book providers implement the **OpenStatusEntry** method to grant access to their status object.</span></span> <span data-ttu-id="f4ae3-125">所有通讯簿提供程序都需要实现至少支持 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法的状态对象。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-125">All address book providers are required to implement a status object that supports, at a minimum, the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="f4ae3-126">有关详细信息，请参阅 [状态对象实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae3-126">For more information, see [Status Object Implementation](status-object-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f4ae3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4ae3-127">See also</span></span>



[<span data-ttu-id="f4ae3-128">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="f4ae3-128">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)
  
[<span data-ttu-id="f4ae3-129">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="f4ae3-129">IMAPIStatus::SettingsDialog</span></span>](imapistatus-settingsdialog.md)
  
[<span data-ttu-id="f4ae3-130">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="f4ae3-130">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
  
[<span data-ttu-id="f4ae3-131">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f4ae3-131">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

