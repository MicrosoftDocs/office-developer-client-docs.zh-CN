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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 72b4ab1fec10b2e91c7609af6644a54d29ed5e02
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432119"
---
# <a name="imsgserviceadmincopymsgservice"></a><span data-ttu-id="3e23f-103">IMsgServiceAdmin::CopyMsgService</span><span class="sxs-lookup"><span data-stu-id="3e23f-103">IMsgServiceAdmin::CopyMsgService</span></span>

  
  
<span data-ttu-id="3e23f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e23f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e23f-105">将邮件服务复制到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="3e23f-105">Copies a message service into a profile.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="3e23f-106">参数</span><span class="sxs-lookup"><span data-stu-id="3e23f-106">Parameters</span></span>

 <span data-ttu-id="3e23f-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="3e23f-107">_lpUID_</span></span>
  
> <span data-ttu-id="3e23f-108">实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含要复制的邮件服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3e23f-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier of the message service to copy.</span></span> 
    
 <span data-ttu-id="3e23f-109">_lpszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="3e23f-109">_lpszDisplayName_</span></span>
  
> <span data-ttu-id="3e23f-110">实时此参数已被弃用。</span><span class="sxs-lookup"><span data-stu-id="3e23f-110">[in] This parameter has been deprecated.</span></span> 
    
 <span data-ttu-id="3e23f-111">_lpInterfaceToCopy_</span><span class="sxs-lookup"><span data-stu-id="3e23f-111">_lpInterfaceToCopy_</span></span>
  
> <span data-ttu-id="3e23f-112">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问要复制的邮件服务的配置文件部分的接口。</span><span class="sxs-lookup"><span data-stu-id="3e23f-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section of the message service to copy.</span></span> <span data-ttu-id="3e23f-113">在要使用的标准配置文件部分接口[IProfSect](iprofsectimapiprop.md)中传递 NULL 结果。</span><span class="sxs-lookup"><span data-stu-id="3e23f-113">Passing NULL results in the standard profile section interface, [IProfSect](iprofsectimapiprop.md), being used.</span></span>
    
 <span data-ttu-id="3e23f-114">_lpInterfaceDst_</span><span class="sxs-lookup"><span data-stu-id="3e23f-114">_lpInterfaceDst_</span></span>
  
> <span data-ttu-id="3e23f-115">实时指向 IID 的指针, 该指针表示用于访问_lpObjectDst_参数所指向的对象的接口。</span><span class="sxs-lookup"><span data-stu-id="3e23f-115">[in] A pointer to the IID that represents the interface to be used to access the object pointed to by the  _lpObjectDst_ parameter.</span></span> <span data-ttu-id="3e23f-116">在正在使用的会话接口中传递 NULL 结果 ( [IMAPISession](imapisessioniunknown.md))。</span><span class="sxs-lookup"><span data-stu-id="3e23f-116">Passing NULL results in the session interface, [IMAPISession](imapisessioniunknown.md), being used.</span></span> <span data-ttu-id="3e23f-117">也可以将_lpInterfaceDst_参数设置为 IID_IMsgServiceAdmin。</span><span class="sxs-lookup"><span data-stu-id="3e23f-117">The  _lpInterfaceDst_ parameter can also be set to IID_IMsgServiceAdmin.</span></span> 
    
 <span data-ttu-id="3e23f-118">_lpObjectDst_</span><span class="sxs-lookup"><span data-stu-id="3e23f-118">_lpObjectDst_</span></span>
  
> <span data-ttu-id="3e23f-119">实时指向指向会话或邮件服务管理对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3e23f-119">[in] A pointer to a pointer to a session or message service administration object.</span></span> <span data-ttu-id="3e23f-120">对象的类型应对应于在_lpInterfaceDst_中传递的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3e23f-120">The type of object should correspond to the interface identifier passed in  _lpInterfaceDst_.</span></span> <span data-ttu-id="3e23f-121">有效的对象指针为 LPMAPISESSION 和 LPSERVICEADMIN。</span><span class="sxs-lookup"><span data-stu-id="3e23f-121">Valid object pointers are LPMAPISESSION and LPSERVICEADMIN.</span></span>
    
 <span data-ttu-id="3e23f-122">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="3e23f-122">_ulUIParam_</span></span>
  
> <span data-ttu-id="3e23f-123">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="3e23f-123">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span>
    
 <span data-ttu-id="3e23f-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3e23f-124">_ulFlags_</span></span>
  
> <span data-ttu-id="3e23f-125">实时用于控制如何复制邮件服务的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="3e23f-125">[in] A bitmask of flags that controls how the message service is copied.</span></span> <span data-ttu-id="3e23f-126">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="3e23f-126">The following flags can be set:</span></span>
    
<span data-ttu-id="3e23f-127">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="3e23f-127">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="3e23f-128">请求邮件服务始终显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="3e23f-128">Requests that the message service always display a configuration property sheet.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3e23f-129">返回值</span><span class="sxs-lookup"><span data-stu-id="3e23f-129">Return value</span></span>

<span data-ttu-id="3e23f-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e23f-130">S_OK</span></span> 
  
> <span data-ttu-id="3e23f-131">已成功复制邮件服务。</span><span class="sxs-lookup"><span data-stu-id="3e23f-131">The message service was successfully copied.</span></span>
    
<span data-ttu-id="3e23f-132">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="3e23f-132">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="3e23f-133">邮件服务已在配置文件中, 不允许自身的多个实例。</span><span class="sxs-lookup"><span data-stu-id="3e23f-133">The message service is already in the profile and does not allow multiple instances of itself.</span></span>
    
<span data-ttu-id="3e23f-134">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="3e23f-134">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="3e23f-135">_lpUID_指向的**MAPIUID**不引用现有的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="3e23f-135">The **MAPIUID** pointed to by  _lpUID_ does not refer to an existing message service.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="3e23f-136">说明</span><span class="sxs-lookup"><span data-stu-id="3e23f-136">Remarks</span></span>

<span data-ttu-id="3e23f-137">**IMsgServiceAdmin:: CopyMsgService**方法将邮件服务复制到配置文件, 即活动配置文件或另一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="3e23f-137">The **IMsgServiceAdmin::CopyMsgService** method copies a message service into a profile, either the active profile or another profile.</span></span> <span data-ttu-id="3e23f-138">包含要复制的邮件服务的配置文件和目标不一定是相同的配置文件, 但可以是。</span><span class="sxs-lookup"><span data-stu-id="3e23f-138">The profile that contains the message service to be copied and the destination do not have to be the same profile, but they can be.</span></span> 
  
<span data-ttu-id="3e23f-139">不会为复制操作调用邮件服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="3e23f-139">The message service's entry point function is not called for a copy operation.</span></span> <span data-ttu-id="3e23f-140">复制的邮件服务的配置设置与原始的相同。</span><span class="sxs-lookup"><span data-stu-id="3e23f-140">The copied message service has the same configuration settings as its original.</span></span> <span data-ttu-id="3e23f-141">若要更改这些设置, 客户端应调用[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3e23f-141">To change these settings, a client should call the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3e23f-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e23f-142">See also</span></span>



[<span data-ttu-id="3e23f-143">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="3e23f-143">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="3e23f-144">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="3e23f-144">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="3e23f-145">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3e23f-145">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

