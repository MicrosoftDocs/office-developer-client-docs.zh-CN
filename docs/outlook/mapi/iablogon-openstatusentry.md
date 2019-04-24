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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349019"
---
# <a name="iablogonopenstatusentry"></a><span data-ttu-id="2d8a3-103">IABLogon::OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="2d8a3-103">IABLogon::OpenStatusEntry</span></span>

  
  
<span data-ttu-id="2d8a3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2d8a3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2d8a3-105">打开提供程序的 status 对象。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-105">Opens the provider's status object.</span></span>
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPMAPISTATUS FAR * lppEntry
);
```

## <a name="parameters"></a><span data-ttu-id="2d8a3-106">参数</span><span class="sxs-lookup"><span data-stu-id="2d8a3-106">Parameters</span></span>

 <span data-ttu-id="2d8a3-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="2d8a3-107">_lpInterface_</span></span>
  
> <span data-ttu-id="2d8a3-108">实时指向接口标识符 (IID) 的指针, 该接口标识符表示必须用于访问 status 对象的接口。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-108">[in] A pointer to the interface identifier (IID) that represents the interface that must be used to access the status object.</span></span> <span data-ttu-id="2d8a3-109">传递 NULL 将返回对象的标准接口[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-109">Passing NULL returns the object's standard interface, [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md).</span></span>
    
 <span data-ttu-id="2d8a3-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2d8a3-110">_ulFlags_</span></span>
  
> <span data-ttu-id="2d8a3-111">实时标志的位掩码, 用于控制状态对象的打开方式。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-111">[in] A bitmask of flags that controls how the status object is opened.</span></span> <span data-ttu-id="2d8a3-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2d8a3-112">The following flag can be set:</span></span>
    
<span data-ttu-id="2d8a3-113">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="2d8a3-113">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="2d8a3-114">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-114">Requests read/write permission.</span></span> <span data-ttu-id="2d8a3-115">默认情况下, 将使用只读访问权限打开对象, 并且调用方不应假定已授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-115">By default, objects are opened with read-only access, and callers should not assume that read/write permission has been granted.</span></span>
    
 <span data-ttu-id="2d8a3-116">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="2d8a3-116">_lpulObjType_</span></span>
  
> <span data-ttu-id="2d8a3-117">排除一个指针, 指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-117">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="2d8a3-118">_lppEntry_</span><span class="sxs-lookup"><span data-stu-id="2d8a3-118">_lppEntry_</span></span>
  
> <span data-ttu-id="2d8a3-119">排除指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-119">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2d8a3-120">返回值</span><span class="sxs-lookup"><span data-stu-id="2d8a3-120">Return value</span></span>

<span data-ttu-id="2d8a3-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d8a3-121">S_OK</span></span> 
  
> <span data-ttu-id="2d8a3-122">调用成功, 状态对象已打开。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-122">The call succeeded and the status object has been opened.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2d8a3-123">注解</span><span class="sxs-lookup"><span data-stu-id="2d8a3-123">Remarks</span></span>

<span data-ttu-id="2d8a3-124">通讯簿提供程序实现**OpenStatusEntry**方法, 以授予对其状态对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-124">Address book providers implement the **OpenStatusEntry** method to grant access to their status object.</span></span> <span data-ttu-id="2d8a3-125">所有通讯簿提供程序都需要实现一个 status 对象, 该对象至少支持[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-125">All address book providers are required to implement a status object that supports, at a minimum, the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="2d8a3-126">有关详细信息, 请参阅[Status Object 实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="2d8a3-126">For more information, see [Status Object Implementation](status-object-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d8a3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d8a3-127">See also</span></span>



[<span data-ttu-id="2d8a3-128">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="2d8a3-128">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)
  
[<span data-ttu-id="2d8a3-129">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="2d8a3-129">IMAPIStatus::SettingsDialog</span></span>](imapistatus-settingsdialog.md)
  
[<span data-ttu-id="2d8a3-130">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="2d8a3-130">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
  
[<span data-ttu-id="2d8a3-131">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2d8a3-131">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

