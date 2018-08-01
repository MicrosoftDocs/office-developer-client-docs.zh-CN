---
title: IMsgServiceAdminCopyMsgService
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.CopyMsgService
api_type:
- COM
ms.assetid: a13c6757-358f-421a-9a76-de7483501613
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d9a15abc05bf0f0a6fef35dd489f12925b88014a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775860"
---
# <a name="imsgserviceadmincopymsgservice"></a><span data-ttu-id="689f6-103">IMsgServiceAdmin::CopyMsgService</span><span class="sxs-lookup"><span data-stu-id="689f6-103">IMsgServiceAdmin::CopyMsgService</span></span>

  
  
<span data-ttu-id="689f6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="689f6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="689f6-105">将邮件服务复制到一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="689f6-105">Copies a message service into a profile.</span></span> 
  
```cpp
HRESULT CopyMsgService(
  LPMAPIUID lpUID,
  LPSTR lpszDisplayName,
  LPCIID lpInterfaceToCopy,
  LPCIID lpInterfaceDst,
  LPVOID lpObjectDst,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="689f6-106">参数</span><span class="sxs-lookup"><span data-stu-id="689f6-106">Parameters</span></span>

 <span data-ttu-id="689f6-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="689f6-107">_lpUID_</span></span>
  
> <span data-ttu-id="689f6-108">[in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要复制的消息服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="689f6-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier of the message service to copy.</span></span> 
    
 <span data-ttu-id="689f6-109">_lpszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="689f6-109">_lpszDisplayName_</span></span>
  
> <span data-ttu-id="689f6-110">[in]此参数已被弃用。</span><span class="sxs-lookup"><span data-stu-id="689f6-110">[in] This parameter has been deprecated.</span></span> 
    
 <span data-ttu-id="689f6-111">_lpInterfaceToCopy_</span><span class="sxs-lookup"><span data-stu-id="689f6-111">_lpInterfaceToCopy_</span></span>
  
> <span data-ttu-id="689f6-112">[in]指向接口标识 (IID) 值，该值代表要用于访问要复制的消息服务的配置文件部分的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="689f6-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section of the message service to copy.</span></span> <span data-ttu-id="689f6-113">在正在使用的标准配置文件部分接口[IProfSect](iprofsectimapiprop.md)，结果传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="689f6-113">Passing NULL results in the standard profile section interface, [IProfSect](iprofsectimapiprop.md), being used.</span></span>
    
 <span data-ttu-id="689f6-114">_lpInterfaceDst_</span><span class="sxs-lookup"><span data-stu-id="689f6-114">_lpInterfaceDst_</span></span>
  
> <span data-ttu-id="689f6-115">[in]指向 IID 值，该值代表要用于访问_lpObjectDst_参数指向的对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="689f6-115">[in] A pointer to the IID that represents the interface to be used to access the object pointed to by the  _lpObjectDst_ parameter.</span></span> <span data-ttu-id="689f6-116">在正在使用的会话接口[IMAPISession](imapisessioniunknown.md)，结果传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="689f6-116">Passing NULL results in the session interface, [IMAPISession](imapisessioniunknown.md), being used.</span></span> <span data-ttu-id="689f6-117">_LpInterfaceDst_参数还可以设置为 IID_IMsgServiceAdmin。</span><span class="sxs-lookup"><span data-stu-id="689f6-117">The  _lpInterfaceDst_ parameter can also be set to IID_IMsgServiceAdmin.</span></span> 
    
 <span data-ttu-id="689f6-118">_lpObjectDst_</span><span class="sxs-lookup"><span data-stu-id="689f6-118">_lpObjectDst_</span></span>
  
> <span data-ttu-id="689f6-119">[in]指向与会话或消息服务管理对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="689f6-119">[in] A pointer to a pointer to a session or message service administration object.</span></span> <span data-ttu-id="689f6-120">对象的类型应对应于_lpInterfaceDst_中传递的界面标识符。</span><span class="sxs-lookup"><span data-stu-id="689f6-120">The type of object should correspond to the interface identifier passed in  _lpInterfaceDst_.</span></span> <span data-ttu-id="689f6-121">有效对象的指针是 LPMAPISESSION 和 LPSERVICEADMIN。</span><span class="sxs-lookup"><span data-stu-id="689f6-121">Valid object pointers are LPMAPISESSION and LPSERVICEADMIN.</span></span>
    
 <span data-ttu-id="689f6-122">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="689f6-122">_ulUIParam_</span></span>
  
> <span data-ttu-id="689f6-123">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="689f6-123">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span>
    
 <span data-ttu-id="689f6-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="689f6-124">_ulFlags_</span></span>
  
> <span data-ttu-id="689f6-125">[in]位掩码的标志，控制如何复制邮件服务。</span><span class="sxs-lookup"><span data-stu-id="689f6-125">[in] A bitmask of flags that controls how the message service is copied.</span></span> <span data-ttu-id="689f6-126">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="689f6-126">The following flags can be set:</span></span>
    
<span data-ttu-id="689f6-127">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="689f6-127">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="689f6-128">请求邮件服务始终显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="689f6-128">Requests that the message service always display a configuration property sheet.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="689f6-129">返回值</span><span class="sxs-lookup"><span data-stu-id="689f6-129">Return value</span></span>

<span data-ttu-id="689f6-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="689f6-130">S_OK</span></span> 
  
> <span data-ttu-id="689f6-131">成功复制邮件服务。</span><span class="sxs-lookup"><span data-stu-id="689f6-131">The message service was successfully copied.</span></span>
    
<span data-ttu-id="689f6-132">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="689f6-132">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="689f6-133">邮件服务已配置文件中，并且不允许多个实例本身。</span><span class="sxs-lookup"><span data-stu-id="689f6-133">The message service is already in the profile and does not allow multiple instances of itself.</span></span>
    
<span data-ttu-id="689f6-134">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="689f6-134">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="689f6-135">指向_lpUID_ **MAPIUID**不引用现有消息服务。</span><span class="sxs-lookup"><span data-stu-id="689f6-135">The **MAPIUID** pointed to by  _lpUID_ does not refer to an existing message service.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="689f6-136">说明</span><span class="sxs-lookup"><span data-stu-id="689f6-136">Remarks</span></span>

<span data-ttu-id="689f6-137">**IMsgServiceAdmin::CopyMsgService**方法将消息服务复制到配置文件、 活动配置文件或另一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="689f6-137">The **IMsgServiceAdmin::CopyMsgService** method copies a message service into a profile, either the active profile or another profile.</span></span> <span data-ttu-id="689f6-138">包含要复制的消息服务的配置文件和目标不具有的相同的配置文件，但也可以是。</span><span class="sxs-lookup"><span data-stu-id="689f6-138">The profile that contains the message service to be copied and the destination do not have to be the same profile, but they can be.</span></span> 
  
<span data-ttu-id="689f6-139">不用于复制操作调用消息服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="689f6-139">The message service's entry point function is not called for a copy operation.</span></span> <span data-ttu-id="689f6-140">复制的消息服务都有为其原始相同的配置设置。</span><span class="sxs-lookup"><span data-stu-id="689f6-140">The copied message service has the same configuration settings as its original.</span></span> <span data-ttu-id="689f6-141">若要更改这些设置，客户端应调用[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法。</span><span class="sxs-lookup"><span data-stu-id="689f6-141">To change these settings, a client should call the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="689f6-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="689f6-142">See also</span></span>



[<span data-ttu-id="689f6-143">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="689f6-143">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="689f6-144">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="689f6-144">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="689f6-145">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="689f6-145">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

