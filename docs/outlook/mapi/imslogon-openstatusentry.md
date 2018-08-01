---
title: IMSLogonOpenStatusEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.OpenStatusEntry
api_type:
- COM
ms.assetid: 850e256b-6b50-428c-aede-287edaf7b005
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 55cf41d251db4c84dad9f12d8f83d0b0dda63ff3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775912"
---
# <a name="imslogonopenstatusentry"></a><span data-ttu-id="8073f-103">IMSLogon::OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="8073f-103">IMSLogon::OpenStatusEntry</span></span>

  
  
<span data-ttu-id="8073f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8073f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8073f-105">打开状态对象。</span><span class="sxs-lookup"><span data-stu-id="8073f-105">Opens a status object.</span></span>
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPVOID FAR * lppEntry
);
```

## <a name="parameters"></a><span data-ttu-id="8073f-106">参数</span><span class="sxs-lookup"><span data-stu-id="8073f-106">Parameters</span></span>

 <span data-ttu-id="8073f-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="8073f-107">_lpInterface_</span></span>
  
> <span data-ttu-id="8073f-108">[in]指向要打开的状态对象的界面标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="8073f-108">[in] A pointer to the interface identifier (IID) for the status object to open.</span></span> <span data-ttu-id="8073f-109">传递 NULL 指示对象的标准接口返回 （在本例中为[IMAPIStatus](imapistatusimapiprop.md)接口）。</span><span class="sxs-lookup"><span data-stu-id="8073f-109">Passing NULL indicates the standard interface for the object is returned (in this case, the [IMAPIStatus](imapistatusimapiprop.md) interface).</span></span> <span data-ttu-id="8073f-110">_LpInterface_参数还可以设置为适当的接口的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="8073f-110">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the object.</span></span> 
    
 <span data-ttu-id="8073f-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8073f-111">_ulFlags_</span></span>
  
> <span data-ttu-id="8073f-112">[in]位掩码的标志，控制如何打开状态对象。</span><span class="sxs-lookup"><span data-stu-id="8073f-112">[in] A bitmask of flags that controls how the status object is opened.</span></span> <span data-ttu-id="8073f-113">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="8073f-113">The following flag can be set:</span></span>
    
<span data-ttu-id="8073f-114">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="8073f-114">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="8073f-115">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="8073f-115">Requests read/write permission.</span></span> <span data-ttu-id="8073f-116">默认情况下，对象在创建具有只读权限，并以为，读/写权限授予客户端应用程序不起作用。</span><span class="sxs-lookup"><span data-stu-id="8073f-116">By default, objects are created with read-only permission, and client applications should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="8073f-117">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="8073f-117">_lpulObjType_</span></span>
  
> <span data-ttu-id="8073f-118">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="8073f-118">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="8073f-119">_lppEntry_</span><span class="sxs-lookup"><span data-stu-id="8073f-119">_lppEntry_</span></span>
  
> <span data-ttu-id="8073f-120">[输出]指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8073f-120">[out] A pointer to the pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8073f-121">返回值</span><span class="sxs-lookup"><span data-stu-id="8073f-121">Return value</span></span>

<span data-ttu-id="8073f-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="8073f-122">S_OK</span></span> 
  
> <span data-ttu-id="8073f-123">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="8073f-123">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8073f-124">说明</span><span class="sxs-lookup"><span data-stu-id="8073f-124">Remarks</span></span>

<span data-ttu-id="8073f-125">消息存储提供程序实现**IMSLogon::OpenStatusEntry**方法打开状态对象。</span><span class="sxs-lookup"><span data-stu-id="8073f-125">Message store providers implement the **IMSLogon::OpenStatusEntry** method to open a status object.</span></span> <span data-ttu-id="8073f-126">此状态对象然后用于启用客户端调用[IMAPIStatus](imapistatusimapiprop.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8073f-126">This status object is then used to enable clients to call [IMAPIStatus](imapistatusimapiprop.md) methods.</span></span> <span data-ttu-id="8073f-127">例如，客户端可以使用[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法重新配置消息存储登录会话或[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法以验证邮件存储登录会话的状态。</span><span class="sxs-lookup"><span data-stu-id="8073f-127">For example, clients can use the [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method to reconfigure the message store logon session or the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method to validate the state of the message store logon session.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8073f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8073f-128">See also</span></span>



[<span data-ttu-id="8073f-129">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="8073f-129">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)
  
[<span data-ttu-id="8073f-130">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="8073f-130">IMAPIStatus::SettingsDialog</span></span>](imapistatus-settingsdialog.md)
  
[<span data-ttu-id="8073f-131">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="8073f-131">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
  
[<span data-ttu-id="8073f-132">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8073f-132">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

