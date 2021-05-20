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
# <a name="ixplogonopenstatusentry"></a><span data-ttu-id="c3207-103">IXPLogon::OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="c3207-103">IXPLogon::OpenStatusEntry</span></span>

  
  
<span data-ttu-id="c3207-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c3207-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c3207-105">打开传输提供程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="c3207-105">Opens the transport provider's status object.</span></span>
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPMAPISTATUS FAR * lppEntry
);
```

## <a name="parameters"></a><span data-ttu-id="c3207-106">参数</span><span class="sxs-lookup"><span data-stu-id="c3207-106">Parameters</span></span>

 <span data-ttu-id="c3207-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="c3207-107">_lpInterface_</span></span>
  
> <span data-ttu-id="c3207-108">[in]指向用于传输登录 (IID) 接口标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="c3207-108">[in] A pointer to an interface identifier (IID) for the transport logon object.</span></span> <span data-ttu-id="c3207-109">传递 NULL 将返回 [IMAPIStatus](imapistatusimapiprop.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="c3207-109">Passing NULL returns the [IMAPIStatus](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="c3207-110">_lpInterface_ 参数还可以设置为对象的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="c3207-110">The  _lpInterface_ parameter can also be set to an identifier for an interface for the object.</span></span> 
    
 <span data-ttu-id="c3207-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c3207-111">_ulFlags_</span></span>
  
> <span data-ttu-id="c3207-112">[in]控制状态对象的打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c3207-112">[in] A bitmask of flags that controls how the status object is opened.</span></span> <span data-ttu-id="c3207-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="c3207-113">The following flag can be set:</span></span>
    
<span data-ttu-id="c3207-114">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="c3207-114">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="c3207-115">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="c3207-115">Requests read/write permission.</span></span> <span data-ttu-id="c3207-116">默认接口是只读的。</span><span class="sxs-lookup"><span data-stu-id="c3207-116">The default interface is read-only.</span></span> 
    
 <span data-ttu-id="c3207-117">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="c3207-117">_lpulObjType_</span></span>
  
> <span data-ttu-id="c3207-118">[out]指向已打开对象的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="c3207-118">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="c3207-119">_lppEntry_</span><span class="sxs-lookup"><span data-stu-id="c3207-119">_lppEntry_</span></span>
  
> <span data-ttu-id="c3207-120">[out]指向已打开状态对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c3207-120">[out] A pointer to the pointer to the opened status object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c3207-121">返回值</span><span class="sxs-lookup"><span data-stu-id="c3207-121">Return value</span></span>

<span data-ttu-id="c3207-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3207-122">S_OK</span></span> 
  
> <span data-ttu-id="c3207-123">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="c3207-123">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c3207-124">备注</span><span class="sxs-lookup"><span data-stu-id="c3207-124">Remarks</span></span>

<span data-ttu-id="c3207-125">当客户端应用程序调用传输提供程序状态表行中的条目标识符的 **OpenEntry** 方法时，MAPI 后台处理程序将调用 **IXPLogon：：OpenStatusEntry** 方法。</span><span class="sxs-lookup"><span data-stu-id="c3207-125">The MAPI spooler calls the **IXPLogon::OpenStatusEntry** method when a client application calls an **OpenEntry** method for the entry identifier in the transport provider's status table row.</span></span> <span data-ttu-id="c3207-126">**OpenStatusEntry** 打开一个对象，该对象具有与此特定传输提供程序登录相关联的 **IMAPIStatus** 接口。</span><span class="sxs-lookup"><span data-stu-id="c3207-126">**OpenStatusEntry** opens an object with the **IMAPIStatus** interface associated with this particular transport provider logon.</span></span> <span data-ttu-id="c3207-127">然后，使用此对象使客户端应用程序能够调用 **IMAPIStatus** 方法 (例如，使用 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 方法重新配置登录会话，或者使用 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法) 验证登录会话的状态。</span><span class="sxs-lookup"><span data-stu-id="c3207-127">This object is then used to enable client applications to call **IMAPIStatus** methods (for example, to reconfigure the logon session by using the [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method, or to validate the state of the logon session by using the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c3207-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3207-128">See also</span></span>



[<span data-ttu-id="c3207-129">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c3207-129">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)
  
[<span data-ttu-id="c3207-130">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c3207-130">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

