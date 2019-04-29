---
title: IXPLogonOpenStatusEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.OpenStatusEntry
api_type:
- COM
ms.assetid: 261d5f7c-bb61-4e1d-aa41-cca224c63f8e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d9e09de1064a0ae034bb3618f0e5b3719a82c163
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435899"
---
# <a name="ixplogonopenstatusentry"></a><span data-ttu-id="7bfce-103">IXPLogon::OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="7bfce-103">IXPLogon::OpenStatusEntry</span></span>

  
  
<span data-ttu-id="7bfce-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7bfce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7bfce-105">打开传输提供程序的 status 对象。</span><span class="sxs-lookup"><span data-stu-id="7bfce-105">Opens the transport provider's status object.</span></span>
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPMAPISTATUS FAR * lppEntry
);
```

## <a name="parameters"></a><span data-ttu-id="7bfce-106">参数</span><span class="sxs-lookup"><span data-stu-id="7bfce-106">Parameters</span></span>

 <span data-ttu-id="7bfce-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="7bfce-107">_lpInterface_</span></span>
  
> <span data-ttu-id="7bfce-108">实时指向传输登录对象的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="7bfce-108">[in] A pointer to an interface identifier (IID) for the transport logon object.</span></span> <span data-ttu-id="7bfce-109">传递 NULL 将返回[IMAPIStatus](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="7bfce-109">Passing NULL returns the [IMAPIStatus](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="7bfce-110">也可以将_lpInterface_参数设置为对象接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="7bfce-110">The  _lpInterface_ parameter can also be set to an identifier for an interface for the object.</span></span> 
    
 <span data-ttu-id="7bfce-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7bfce-111">_ulFlags_</span></span>
  
> <span data-ttu-id="7bfce-112">实时标志的位掩码, 用于控制状态对象的打开方式。</span><span class="sxs-lookup"><span data-stu-id="7bfce-112">[in] A bitmask of flags that controls how the status object is opened.</span></span> <span data-ttu-id="7bfce-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="7bfce-113">The following flag can be set:</span></span>
    
<span data-ttu-id="7bfce-114">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="7bfce-114">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="7bfce-115">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="7bfce-115">Requests read/write permission.</span></span> <span data-ttu-id="7bfce-116">默认接口是只读的。</span><span class="sxs-lookup"><span data-stu-id="7bfce-116">The default interface is read-only.</span></span> 
    
 <span data-ttu-id="7bfce-117">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="7bfce-117">_lpulObjType_</span></span>
  
> <span data-ttu-id="7bfce-118">排除一个指针, 指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="7bfce-118">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="7bfce-119">_lppEntry_</span><span class="sxs-lookup"><span data-stu-id="7bfce-119">_lppEntry_</span></span>
  
> <span data-ttu-id="7bfce-120">排除指向打开的状态对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7bfce-120">[out] A pointer to the pointer to the opened status object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7bfce-121">返回值</span><span class="sxs-lookup"><span data-stu-id="7bfce-121">Return value</span></span>

<span data-ttu-id="7bfce-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="7bfce-122">S_OK</span></span> 
  
> <span data-ttu-id="7bfce-123">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="7bfce-123">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7bfce-124">说明</span><span class="sxs-lookup"><span data-stu-id="7bfce-124">Remarks</span></span>

<span data-ttu-id="7bfce-125">当客户端应用程序在传输提供程序的状态表行中为条目标识符调用**OpenEntry**方法时, MAPI 后台处理程序将调用**IXPLogon:: OpenStatusEntry**方法。</span><span class="sxs-lookup"><span data-stu-id="7bfce-125">The MAPI spooler calls the **IXPLogon::OpenStatusEntry** method when a client application calls an **OpenEntry** method for the entry identifier in the transport provider's status table row.</span></span> <span data-ttu-id="7bfce-126">**OpenStatusEntry**将打开一个对象, 其中包含与此特定传输提供程序登录相关联的**IMAPIStatus**接口。</span><span class="sxs-lookup"><span data-stu-id="7bfce-126">**OpenStatusEntry** opens an object with the **IMAPIStatus** interface associated with this particular transport provider logon.</span></span> <span data-ttu-id="7bfce-127">然后, 使用此对象来启用客户端应用程序, 以调用**IMAPIStatus**方法 (例如, 使用[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法重新配置登录会话, 或使用[验证登录会话的状态。IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法)。</span><span class="sxs-lookup"><span data-stu-id="7bfce-127">This object is then used to enable client applications to call **IMAPIStatus** methods (for example, to reconfigure the logon session by using the [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method, or to validate the state of the logon session by using the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7bfce-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bfce-128">See also</span></span>



[<span data-ttu-id="7bfce-129">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="7bfce-129">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)
  
[<span data-ttu-id="7bfce-130">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7bfce-130">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

