---
title: IMAPISupportGetSvcConfigSupportObj
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetSvcConfigSupportObj
api_type:
- COM
ms.assetid: 56c3bdae-a3a8-4334-b6d2-a89c6820d72e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1c48ceefa84658b236b8dfa4e10df18c175d920e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595158"
---
# <a name="imapisupportgetsvcconfigsupportobj"></a><span data-ttu-id="15d4c-103">IMAPISupport::GetSvcConfigSupportObj</span><span class="sxs-lookup"><span data-stu-id="15d4c-103">IMAPISupport::GetSvcConfigSupportObj</span></span>

  
  
<span data-ttu-id="15d4c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="15d4c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="15d4c-105">创建一个邮件服务支持对象。</span><span class="sxs-lookup"><span data-stu-id="15d4c-105">Creates a message service support object.</span></span>
  
```cpp
HRESULT GetSvcConfigSupportObj(
  ULONG ulFlags,
  LPMAPISUP FAR * lppSvcSupport
);
```

## <a name="parameters"></a><span data-ttu-id="15d4c-106">参数</span><span class="sxs-lookup"><span data-stu-id="15d4c-106">Parameters</span></span>

 <span data-ttu-id="15d4c-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="15d4c-107">_ulFlags_</span></span>
  
> <span data-ttu-id="15d4c-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="15d4c-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="15d4c-109">_lppSvcSupport_</span><span class="sxs-lookup"><span data-stu-id="15d4c-109">_lppSvcSupport_</span></span>
  
> <span data-ttu-id="15d4c-110">[输出]为指向新消息服务支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="15d4c-110">[out] A pointer to a pointer to the new message service support object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="15d4c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="15d4c-111">Return value</span></span>

<span data-ttu-id="15d4c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="15d4c-112">S_OK</span></span> 
  
> <span data-ttu-id="15d4c-113">已成功创建配置支持对象。</span><span class="sxs-lookup"><span data-stu-id="15d4c-113">The configuration support object was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="15d4c-114">注解</span><span class="sxs-lookup"><span data-stu-id="15d4c-114">Remarks</span></span>

<span data-ttu-id="15d4c-115">对于所有支持对象实现**IMAPISupport::GetSvcConfigSupportObj**方法。</span><span class="sxs-lookup"><span data-stu-id="15d4c-115">The **IMAPISupport::GetSvcConfigSupportObj** method is implemented for all support objects.</span></span> <span data-ttu-id="15d4c-116">服务提供商调用**GetSvcConfigSupportObj**创建配置支持对象以传递给消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="15d4c-116">Service providers call **GetSvcConfigSupportObj** to create a configuration support object to pass to a message service entry point function.</span></span> 
  
<span data-ttu-id="15d4c-117">消息服务入口点函数基于[MSGSERVICEENTRY](msgserviceentry.md)原型和[IMsgServiceAdmin](imsgserviceadminiunknown.md)接口方法调用。</span><span class="sxs-lookup"><span data-stu-id="15d4c-117">A message service entry point function is based on the [MSGSERVICEENTRY](msgserviceentry.md) prototype and is called by methods of the [IMsgServiceAdmin](imsgserviceadminiunknown.md) interface.</span></span> <span data-ttu-id="15d4c-118">消息服务入口点函数允许消息服务配置自己或更改配置文件时执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="15d4c-118">A message service entry point function allows message services to configure themselves or perform other actions when the profile is changed.</span></span> <span data-ttu-id="15d4c-119">消息服务的入口点函数可支持配置更改，通过显示属性表或属性值数组传递给[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法。</span><span class="sxs-lookup"><span data-stu-id="15d4c-119">Message service entry point functions can support configuration changes by displaying a property sheet or through a property value array passed to the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="15d4c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15d4c-120">See also</span></span>



[<span data-ttu-id="15d4c-121">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="15d4c-121">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)
  
[<span data-ttu-id="15d4c-122">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="15d4c-122">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="15d4c-123">IMsgServiceAdmin::CreateMsgService</span><span class="sxs-lookup"><span data-stu-id="15d4c-123">IMsgServiceAdmin::CreateMsgService</span></span>](imsgserviceadmin-createmsgservice.md)
  
[<span data-ttu-id="15d4c-124">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="15d4c-124">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)
  
[<span data-ttu-id="15d4c-125">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="15d4c-125">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="15d4c-126">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="15d4c-126">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

