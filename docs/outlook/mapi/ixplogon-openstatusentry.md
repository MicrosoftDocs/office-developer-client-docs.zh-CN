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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7cb77308ebc7229adcab290fc8e1f9e11ce45065
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587017"
---
# <a name="ixplogonopenstatusentry"></a><span data-ttu-id="910fa-103">IXPLogon::OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="910fa-103">IXPLogon::OpenStatusEntry</span></span>

  
  
<span data-ttu-id="910fa-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="910fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="910fa-105">打开传输提供程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="910fa-105">Opens the transport provider's status object.</span></span>
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPMAPISTATUS FAR * lppEntry
);
```

## <a name="parameters"></a><span data-ttu-id="910fa-106">参数</span><span class="sxs-lookup"><span data-stu-id="910fa-106">Parameters</span></span>

 <span data-ttu-id="910fa-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="910fa-107">_lpInterface_</span></span>
  
> <span data-ttu-id="910fa-108">[in]指向传输登录对象的界面标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="910fa-108">[in] A pointer to an interface identifier (IID) for the transport logon object.</span></span> <span data-ttu-id="910fa-109">如果传递 NULL 返回[IMAPIStatus](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="910fa-109">Passing NULL returns the [IMAPIStatus](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="910fa-110">_LpInterface_参数还可以设置为对象的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="910fa-110">The  _lpInterface_ parameter can also be set to an identifier for an interface for the object.</span></span> 
    
 <span data-ttu-id="910fa-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="910fa-111">_ulFlags_</span></span>
  
> <span data-ttu-id="910fa-112">[in]位掩码的标志，控制如何打开状态对象。</span><span class="sxs-lookup"><span data-stu-id="910fa-112">[in] A bitmask of flags that controls how the status object is opened.</span></span> <span data-ttu-id="910fa-113">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="910fa-113">The following flag can be set:</span></span>
    
<span data-ttu-id="910fa-114">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="910fa-114">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="910fa-115">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="910fa-115">Requests read/write permission.</span></span> <span data-ttu-id="910fa-116">默认接口是只读的。</span><span class="sxs-lookup"><span data-stu-id="910fa-116">The default interface is read-only.</span></span> 
    
 <span data-ttu-id="910fa-117">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="910fa-117">_lpulObjType_</span></span>
  
> <span data-ttu-id="910fa-118">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="910fa-118">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="910fa-119">_lppEntry_</span><span class="sxs-lookup"><span data-stu-id="910fa-119">_lppEntry_</span></span>
  
> <span data-ttu-id="910fa-120">[输出]指向打开的状态对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="910fa-120">[out] A pointer to the pointer to the opened status object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="910fa-121">返回值</span><span class="sxs-lookup"><span data-stu-id="910fa-121">Return value</span></span>

<span data-ttu-id="910fa-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="910fa-122">S_OK</span></span> 
  
> <span data-ttu-id="910fa-123">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="910fa-123">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="910fa-124">注解</span><span class="sxs-lookup"><span data-stu-id="910fa-124">Remarks</span></span>

<span data-ttu-id="910fa-125">客户端应用程序的传输提供程序的状态表格行中的项标识符调用**OpenEntry**方法时，MAPI 后台处理程序调用**IXPLogon::OpenStatusEntry**方法。</span><span class="sxs-lookup"><span data-stu-id="910fa-125">The MAPI spooler calls the **IXPLogon::OpenStatusEntry** method when a client application calls an **OpenEntry** method for the entry identifier in the transport provider's status table row.</span></span> <span data-ttu-id="910fa-126">**OpenStatusEntry**打开与此特定传输提供程序的登录关联的**IMAPIStatus**接口的对象。</span><span class="sxs-lookup"><span data-stu-id="910fa-126">**OpenStatusEntry** opens an object with the **IMAPIStatus** interface associated with this particular transport provider logon.</span></span> <span data-ttu-id="910fa-127">此对象然后用于启用客户端应用程序调用**IMAPIStatus**方法 （例如，若要重新登录会话配置使用[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法，或使用[验证登录会话的状态IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法)。</span><span class="sxs-lookup"><span data-stu-id="910fa-127">This object is then used to enable client applications to call **IMAPIStatus** methods (for example, to reconfigure the logon session by using the [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method, or to validate the state of the logon session by using the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="910fa-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="910fa-128">See also</span></span>



[<span data-ttu-id="910fa-129">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="910fa-129">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)
  
[<span data-ttu-id="910fa-130">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="910fa-130">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

