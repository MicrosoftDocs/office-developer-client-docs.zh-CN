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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316555"
---
# <a name="imapisupportgetsvcconfigsupportobj"></a><span data-ttu-id="6b89b-103">IMAPISupport::GetSvcConfigSupportObj</span><span class="sxs-lookup"><span data-stu-id="6b89b-103">IMAPISupport::GetSvcConfigSupportObj</span></span>

  
  
<span data-ttu-id="6b89b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6b89b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6b89b-105">创建邮件服务支持对象。</span><span class="sxs-lookup"><span data-stu-id="6b89b-105">Creates a message service support object.</span></span>
  
```cpp
HRESULT GetSvcConfigSupportObj(
  ULONG ulFlags,
  LPMAPISUP FAR * lppSvcSupport
);
```

## <a name="parameters"></a><span data-ttu-id="6b89b-106">参数</span><span class="sxs-lookup"><span data-stu-id="6b89b-106">Parameters</span></span>

 <span data-ttu-id="6b89b-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6b89b-107">_ulFlags_</span></span>
  
> <span data-ttu-id="6b89b-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="6b89b-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="6b89b-109">_lppSvcSupport_</span><span class="sxs-lookup"><span data-stu-id="6b89b-109">_lppSvcSupport_</span></span>
  
> <span data-ttu-id="6b89b-110">排除指向新邮件服务支持对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6b89b-110">[out] A pointer to a pointer to the new message service support object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6b89b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6b89b-111">Return value</span></span>

<span data-ttu-id="6b89b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b89b-112">S_OK</span></span> 
  
> <span data-ttu-id="6b89b-113">成功创建了配置支持对象。</span><span class="sxs-lookup"><span data-stu-id="6b89b-113">The configuration support object was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6b89b-114">注解</span><span class="sxs-lookup"><span data-stu-id="6b89b-114">Remarks</span></span>

<span data-ttu-id="6b89b-115">**IMAPISupport:: GetSvcConfigSupportObj**方法是为所有支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="6b89b-115">The **IMAPISupport::GetSvcConfigSupportObj** method is implemented for all support objects.</span></span> <span data-ttu-id="6b89b-116">服务提供程序调用**GetSvcConfigSupportObj**以创建要传递给邮件服务入口点函数的配置支持对象。</span><span class="sxs-lookup"><span data-stu-id="6b89b-116">Service providers call **GetSvcConfigSupportObj** to create a configuration support object to pass to a message service entry point function.</span></span> 
  
<span data-ttu-id="6b89b-117">邮件服务入口点函数基于[MSGSERVICEENTRY](msgserviceentry.md)原型, 并由[IMsgServiceAdmin](imsgserviceadminiunknown.md)接口的方法调用。</span><span class="sxs-lookup"><span data-stu-id="6b89b-117">A message service entry point function is based on the [MSGSERVICEENTRY](msgserviceentry.md) prototype and is called by methods of the [IMsgServiceAdmin](imsgserviceadminiunknown.md) interface.</span></span> <span data-ttu-id="6b89b-118">邮件服务入口点函数允许邮件服务在配置文件发生更改时配置自身或执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="6b89b-118">A message service entry point function allows message services to configure themselves or perform other actions when the profile is changed.</span></span> <span data-ttu-id="6b89b-119">邮件服务入口点函数可通过显示属性表或通过传递给[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法的属性值数组来支持配置更改。</span><span class="sxs-lookup"><span data-stu-id="6b89b-119">Message service entry point functions can support configuration changes by displaying a property sheet or through a property value array passed to the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6b89b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b89b-120">See also</span></span>



[<span data-ttu-id="6b89b-121">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6b89b-121">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)
  
[<span data-ttu-id="6b89b-122">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="6b89b-122">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="6b89b-123">IMsgServiceAdmin::CreateMsgService</span><span class="sxs-lookup"><span data-stu-id="6b89b-123">IMsgServiceAdmin::CreateMsgService</span></span>](imsgserviceadmin-createmsgservice.md)
  
[<span data-ttu-id="6b89b-124">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6b89b-124">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)
  
[<span data-ttu-id="6b89b-125">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="6b89b-125">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="6b89b-126">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6b89b-126">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

