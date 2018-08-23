---
title: IProfAdminCreateProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.CreateProfile
api_type:
- COM
ms.assetid: 10cda14a-8f93-41e0-b1fb-500098bdc392
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 92d5dcdf3e5e3fbdb7490d777a24976c9ae4af1a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582789"
---
# <a name="iprofadmincreateprofile"></a><span data-ttu-id="35c5d-103">IProfAdmin::CreateProfile</span><span class="sxs-lookup"><span data-stu-id="35c5d-103">IProfAdmin::CreateProfile</span></span>

  
  
<span data-ttu-id="35c5d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="35c5d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="35c5d-105">创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="35c5d-105">Creates a new profile.</span></span>
  
```cpp
HRESULT CreateProfile(
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="35c5d-106">参数</span><span class="sxs-lookup"><span data-stu-id="35c5d-106">Parameters</span></span>

 <span data-ttu-id="35c5d-107">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="35c5d-107">_lpszProfileName_</span></span>
  
> <span data-ttu-id="35c5d-108">[in]一个指向新的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="35c5d-108">[in] A pointer to the name of the new profile.</span></span>
    
 <span data-ttu-id="35c5d-109">_lpszPassword_</span><span class="sxs-lookup"><span data-stu-id="35c5d-109">_lpszPassword_</span></span>
  
> <span data-ttu-id="35c5d-110">[in]一个指向新的配置文件的密码。</span><span class="sxs-lookup"><span data-stu-id="35c5d-110">[in] A pointer to the password of the new profile.</span></span> 
    
 <span data-ttu-id="35c5d-111">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="35c5d-111">_ulUIParam_</span></span>
  
> <span data-ttu-id="35c5d-112">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="35c5d-112">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="35c5d-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="35c5d-113">_ulFlags_</span></span>
  
> <span data-ttu-id="35c5d-114">[in]位掩码的标志，控制如何创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="35c5d-114">[in] A bitmask of flags that controls how the profile is created.</span></span> <span data-ttu-id="35c5d-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="35c5d-115">The following flags can be set:</span></span>
    
<span data-ttu-id="35c5d-116">MAPI_DEFAULT_SERVICES</span><span class="sxs-lookup"><span data-stu-id="35c5d-116">MAPI_DEFAULT_SERVICES</span></span> 
  
> <span data-ttu-id="35c5d-117">MAPI 应该填充 Mapisvc.inf 文件的 [默认服务] 节中包含了消息服务的新配置文件。</span><span class="sxs-lookup"><span data-stu-id="35c5d-117">MAPI should populate the new profile with the message services that are included in the [Default Services] section of the Mapisvc.inf file.</span></span>
    
<span data-ttu-id="35c5d-118">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="35c5d-118">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="35c5d-119">可显示每个中消息服务提供程序，要添加的配置属性工作表。</span><span class="sxs-lookup"><span data-stu-id="35c5d-119">The configuration property sheets of each of the providers in the message services to be added can be displayed.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="35c5d-120">返回值</span><span class="sxs-lookup"><span data-stu-id="35c5d-120">Return value</span></span>

<span data-ttu-id="35c5d-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="35c5d-121">S_OK</span></span> 
  
> <span data-ttu-id="35c5d-122">创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="35c5d-122">The new profile was created.</span></span>
    
<span data-ttu-id="35c5d-123">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="35c5d-123">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="35c5d-124">指定新的配置文件已存在。</span><span class="sxs-lookup"><span data-stu-id="35c5d-124">The specified new profile already exists.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="35c5d-125">注解</span><span class="sxs-lookup"><span data-stu-id="35c5d-125">Remarks</span></span>

<span data-ttu-id="35c5d-126">**IProfAdmin::CreateProfile**方法创建一个新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="35c5d-126">The **IProfAdmin::CreateProfile** method creates a new profile.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="35c5d-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="35c5d-127">Notes to callers</span></span>

<span data-ttu-id="35c5d-128">在应用程序安装时或在会话过程中的任何时候，您可以调用**CreateProfile** 。</span><span class="sxs-lookup"><span data-stu-id="35c5d-128">You can call **CreateProfile** at application installation time or at any time during a session.</span></span> <span data-ttu-id="35c5d-129">在安装时调用此方法，许多的配置设置将来自 Mapisvc.inf 配置文件。</span><span class="sxs-lookup"><span data-stu-id="35c5d-129">When this method is called at installation time, many of the configuration settings come from the Mapisvc.inf configuration file.</span></span> <span data-ttu-id="35c5d-130">当活动会话过程中调用此方法时，设置来自提示通过一系列的属性表的用户。</span><span class="sxs-lookup"><span data-stu-id="35c5d-130">When this method is called during an active session, the settings come from the user who is prompted through a series of property sheets.</span></span> 
  
<span data-ttu-id="35c5d-131">如果_ulFlags_参数中设置 MAPI_DEFAULT_SERVICES 标志， **CreateProfile** Mapisvc.inf 文件中的 [默认服务] 一节中每个邮件服务调用消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="35c5d-131">If the MAPI_DEFAULT_SERVICES flag is set in the  _ulFlags_ parameter, **CreateProfile** calls the message service entry point function for each message service in the [Default Services] section in the Mapisvc.inf file.</span></span> <span data-ttu-id="35c5d-132">使用_ulContext_参数设置为 MSG_SERVICE_CREATE 调用每个邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="35c5d-132">Each message service entry point function is called with the  _ulContext_ parameter set to MSG_SERVICE_CREATE.</span></span> 
  
<span data-ttu-id="35c5d-133">如果设置 MAPI_DIALOG 和 MAPI_DEFAULT_SERVICES 标志中的_ulUIParam_和_ulFlags_参数值还传递给消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="35c5d-133">If both the MAPI_DIALOG and MAPI_DEFAULT_SERVICES flags are set, the values in the  _ulUIParam_ and  _ulFlags_ parameters are also passed to the message service entry point function.</span></span> <span data-ttu-id="35c5d-134">仅 Mapisvc.inf 文件中的所有可用信息添加到配置文件之后，也称为消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="35c5d-134">The message service entry point functions are called only after all available information from the Mapisvc.inf file has been added to the profile.</span></span> 
  
<span data-ttu-id="35c5d-135">新的配置文件和其密码的名称的长度最多为 64 个字符，并可以包含下列字符：</span><span class="sxs-lookup"><span data-stu-id="35c5d-135">The name of the new profile and its password can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="35c5d-136">所有字母数字字符，包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="35c5d-136">All alphanumeric characters, including accent characters and the underscore character.</span></span>
    
- <span data-ttu-id="35c5d-137">嵌入的空格，但不是前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="35c5d-137">Embedded spaces, but not leading or trailing spaces.</span></span>
    
<span data-ttu-id="35c5d-138">_LpszPassword_参数必须为空或为零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="35c5d-138">The  _lpszPassword_ parameter must be NULL or a pointer to a zero-length string.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="35c5d-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35c5d-139">See also</span></span>



[<span data-ttu-id="35c5d-140">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="35c5d-140">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="35c5d-141">IMsgServiceAdmin::CreateMsgService</span><span class="sxs-lookup"><span data-stu-id="35c5d-141">IMsgServiceAdmin::CreateMsgService</span></span>](imsgserviceadmin-createmsgservice.md)
  
[<span data-ttu-id="35c5d-142">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="35c5d-142">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="35c5d-143">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="35c5d-143">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

