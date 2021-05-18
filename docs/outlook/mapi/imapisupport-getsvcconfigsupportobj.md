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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6de0fed4df9d23e67c3520ffb019a961b890f988
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411307"
---
# <a name="imapisupportgetsvcconfigsupportobj"></a><span data-ttu-id="ae0d3-103">IMAPISupport::GetSvcConfigSupportObj</span><span class="sxs-lookup"><span data-stu-id="ae0d3-103">IMAPISupport::GetSvcConfigSupportObj</span></span>

  
  
<span data-ttu-id="ae0d3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ae0d3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ae0d3-105">创建邮件服务支持对象。</span><span class="sxs-lookup"><span data-stu-id="ae0d3-105">Creates a message service support object.</span></span>
  
```cpp
HRESULT GetSvcConfigSupportObj(
  ULONG ulFlags,
  LPMAPISUP FAR * lppSvcSupport
);
```

## <a name="parameters"></a><span data-ttu-id="ae0d3-106">参数</span><span class="sxs-lookup"><span data-stu-id="ae0d3-106">Parameters</span></span>

 <span data-ttu-id="ae0d3-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ae0d3-107">_ulFlags_</span></span>
  
> <span data-ttu-id="ae0d3-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="ae0d3-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="ae0d3-109">_lppSvcSupport_</span><span class="sxs-lookup"><span data-stu-id="ae0d3-109">_lppSvcSupport_</span></span>
  
> <span data-ttu-id="ae0d3-110">[out]指向指向新邮件服务支持对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ae0d3-110">[out] A pointer to a pointer to the new message service support object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ae0d3-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ae0d3-111">Return value</span></span>

<span data-ttu-id="ae0d3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae0d3-112">S_OK</span></span> 
  
> <span data-ttu-id="ae0d3-113">已成功创建配置支持对象。</span><span class="sxs-lookup"><span data-stu-id="ae0d3-113">The configuration support object was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ae0d3-114">备注</span><span class="sxs-lookup"><span data-stu-id="ae0d3-114">Remarks</span></span>

<span data-ttu-id="ae0d3-115">**IMAPISupport：：GetSvcConfigSupportObj** 方法针对所有支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="ae0d3-115">The **IMAPISupport::GetSvcConfigSupportObj** method is implemented for all support objects.</span></span> <span data-ttu-id="ae0d3-116">服务提供程序调用 **GetSvcConfigSupportObj** 以创建要传递给邮件服务入口点函数的配置支持对象。</span><span class="sxs-lookup"><span data-stu-id="ae0d3-116">Service providers call **GetSvcConfigSupportObj** to create a configuration support object to pass to a message service entry point function.</span></span> 
  
<span data-ttu-id="ae0d3-117">邮件服务入口点函数基于 [MSGSERVICEENTRY](msgserviceentry.md) 原型，由 [IMsgServiceAdmin](imsgserviceadminiunknown.md) 接口的方法调用。</span><span class="sxs-lookup"><span data-stu-id="ae0d3-117">A message service entry point function is based on the [MSGSERVICEENTRY](msgserviceentry.md) prototype and is called by methods of the [IMsgServiceAdmin](imsgserviceadminiunknown.md) interface.</span></span> <span data-ttu-id="ae0d3-118">邮件服务入口点函数允许邮件服务在配置文件更改时配置自身或执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="ae0d3-118">A message service entry point function allows message services to configure themselves or perform other actions when the profile is changed.</span></span> <span data-ttu-id="ae0d3-119">邮件服务入口点函数可以支持配置更改，方法是显示属性表或传递给 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) 方法的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="ae0d3-119">Message service entry point functions can support configuration changes by displaying a property sheet or through a property value array passed to the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ae0d3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae0d3-120">See also</span></span>



[<span data-ttu-id="ae0d3-121">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ae0d3-121">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)
  
[<span data-ttu-id="ae0d3-122">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="ae0d3-122">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="ae0d3-123">IMsgServiceAdmin::CreateMsgService</span><span class="sxs-lookup"><span data-stu-id="ae0d3-123">IMsgServiceAdmin::CreateMsgService</span></span>](imsgserviceadmin-createmsgservice.md)
  
[<span data-ttu-id="ae0d3-124">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ae0d3-124">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)
  
[<span data-ttu-id="ae0d3-125">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="ae0d3-125">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="ae0d3-126">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ae0d3-126">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

