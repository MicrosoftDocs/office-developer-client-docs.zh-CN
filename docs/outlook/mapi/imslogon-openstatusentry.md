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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f50c0eb9e3af68e206eaa5bcc51cefa923c30f72
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413176"
---
# <a name="imslogonopenstatusentry"></a><span data-ttu-id="ca0a1-103">IMSLogon::OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="ca0a1-103">IMSLogon::OpenStatusEntry</span></span>

  
  
<span data-ttu-id="ca0a1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca0a1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca0a1-105">打开一个 status 对象。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-105">Opens a status object.</span></span>
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPVOID FAR * lppEntry
);
```

## <a name="parameters"></a><span data-ttu-id="ca0a1-106">参数</span><span class="sxs-lookup"><span data-stu-id="ca0a1-106">Parameters</span></span>

 <span data-ttu-id="ca0a1-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="ca0a1-107">_lpInterface_</span></span>
  
> <span data-ttu-id="ca0a1-108">实时指向要打开的 status 对象的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-108">[in] A pointer to the interface identifier (IID) for the status object to open.</span></span> <span data-ttu-id="ca0a1-109">传递 NULL 表示返回对象的标准接口 (在此示例中为[IMAPIStatus](imapistatusimapiprop.md)接口)。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-109">Passing NULL indicates the standard interface for the object is returned (in this case, the [IMAPIStatus](imapistatusimapiprop.md) interface).</span></span> <span data-ttu-id="ca0a1-110">也可以将_lpInterface_参数设置为对象的相应接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-110">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the object.</span></span> 
    
 <span data-ttu-id="ca0a1-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ca0a1-111">_ulFlags_</span></span>
  
> <span data-ttu-id="ca0a1-112">实时标志的位掩码, 用于控制状态对象的打开方式。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-112">[in] A bitmask of flags that controls how the status object is opened.</span></span> <span data-ttu-id="ca0a1-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ca0a1-113">The following flag can be set:</span></span>
    
<span data-ttu-id="ca0a1-114">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="ca0a1-114">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="ca0a1-115">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-115">Requests read/write permission.</span></span> <span data-ttu-id="ca0a1-116">默认情况下, 创建具有只读权限的对象, 并且客户端应用程序不应在假定已授予读/写权限时才起作用。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-116">By default, objects are created with read-only permission, and client applications should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="ca0a1-117">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="ca0a1-117">_lpulObjType_</span></span>
  
> <span data-ttu-id="ca0a1-118">排除一个指针, 指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-118">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="ca0a1-119">_lppEntry_</span><span class="sxs-lookup"><span data-stu-id="ca0a1-119">_lppEntry_</span></span>
  
> <span data-ttu-id="ca0a1-120">排除指向指向已打开对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-120">[out] A pointer to the pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ca0a1-121">返回值</span><span class="sxs-lookup"><span data-stu-id="ca0a1-121">Return value</span></span>

<span data-ttu-id="ca0a1-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca0a1-122">S_OK</span></span> 
  
> <span data-ttu-id="ca0a1-123">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-123">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ca0a1-124">说明</span><span class="sxs-lookup"><span data-stu-id="ca0a1-124">Remarks</span></span>

<span data-ttu-id="ca0a1-125">邮件存储提供程序实现**IMSLogon:: OpenStatusEntry**方法以打开 status 对象。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-125">Message store providers implement the **IMSLogon::OpenStatusEntry** method to open a status object.</span></span> <span data-ttu-id="ca0a1-126">此状态对象随后用于使客户端可以调用[IMAPIStatus](imapistatusimapiprop.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-126">This status object is then used to enable clients to call [IMAPIStatus](imapistatusimapiprop.md) methods.</span></span> <span data-ttu-id="ca0a1-127">例如, 客户端可以使用[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法重新配置邮件存储登录会话或[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法以验证邮件存储登录会话的状态。</span><span class="sxs-lookup"><span data-stu-id="ca0a1-127">For example, clients can use the [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method to reconfigure the message store logon session or the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method to validate the state of the message store logon session.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ca0a1-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca0a1-128">See also</span></span>



[<span data-ttu-id="ca0a1-129">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ca0a1-129">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)
  
[<span data-ttu-id="ca0a1-130">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="ca0a1-130">IMAPIStatus::SettingsDialog</span></span>](imapistatus-settingsdialog.md)
  
[<span data-ttu-id="ca0a1-131">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="ca0a1-131">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
  
[<span data-ttu-id="ca0a1-132">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ca0a1-132">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

