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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b104c62eb617e6c68f85dea4ef6379c831733844
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317113"
---
# <a name="iprofadmincreateprofile"></a><span data-ttu-id="21792-103">IProfAdmin::CreateProfile</span><span class="sxs-lookup"><span data-stu-id="21792-103">IProfAdmin::CreateProfile</span></span>

  
  
<span data-ttu-id="21792-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="21792-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="21792-105">创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="21792-105">Creates a new profile.</span></span>
  
```cpp
HRESULT CreateProfile(
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="21792-106">参数</span><span class="sxs-lookup"><span data-stu-id="21792-106">Parameters</span></span>

 <span data-ttu-id="21792-107">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="21792-107">_lpszProfileName_</span></span>
  
> <span data-ttu-id="21792-108">实时指向新配置文件的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="21792-108">[in] A pointer to the name of the new profile.</span></span>
    
 <span data-ttu-id="21792-109">_lpszPassword_</span><span class="sxs-lookup"><span data-stu-id="21792-109">_lpszPassword_</span></span>
  
> <span data-ttu-id="21792-110">实时指向新配置文件的密码的指针。</span><span class="sxs-lookup"><span data-stu-id="21792-110">[in] A pointer to the password of the new profile.</span></span> 
    
 <span data-ttu-id="21792-111">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="21792-111">_ulUIParam_</span></span>
  
> <span data-ttu-id="21792-112">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="21792-112">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="21792-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="21792-113">_ulFlags_</span></span>
  
> <span data-ttu-id="21792-114">实时用于控制如何创建配置文件的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="21792-114">[in] A bitmask of flags that controls how the profile is created.</span></span> <span data-ttu-id="21792-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="21792-115">The following flags can be set:</span></span>
    
<span data-ttu-id="21792-116">MAPI_DEFAULT_SERVICES</span><span class="sxs-lookup"><span data-stu-id="21792-116">MAPI_DEFAULT_SERVICES</span></span> 
  
> <span data-ttu-id="21792-117">MAPI 应使用包含在 mapisvc.inf 文件的 [默认服务] 部分中的邮件服务来填充新配置文件。</span><span class="sxs-lookup"><span data-stu-id="21792-117">MAPI should populate the new profile with the message services that are included in the [Default Services] section of the Mapisvc.inf file.</span></span>
    
<span data-ttu-id="21792-118">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="21792-118">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="21792-119">可以显示要添加的邮件服务中每个提供程序的配置属性表。</span><span class="sxs-lookup"><span data-stu-id="21792-119">The configuration property sheets of each of the providers in the message services to be added can be displayed.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="21792-120">返回值</span><span class="sxs-lookup"><span data-stu-id="21792-120">Return value</span></span>

<span data-ttu-id="21792-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="21792-121">S_OK</span></span> 
  
> <span data-ttu-id="21792-122">已创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="21792-122">The new profile was created.</span></span>
    
<span data-ttu-id="21792-123">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="21792-123">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="21792-124">指定的新配置文件已存在。</span><span class="sxs-lookup"><span data-stu-id="21792-124">The specified new profile already exists.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="21792-125">注解</span><span class="sxs-lookup"><span data-stu-id="21792-125">Remarks</span></span>

<span data-ttu-id="21792-126">**IProfAdmin:: CreateProfile**方法创建一个新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="21792-126">The **IProfAdmin::CreateProfile** method creates a new profile.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="21792-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="21792-127">Notes to callers</span></span>

<span data-ttu-id="21792-128">您可以在应用程序安装时或在会话过程中的任何时间调用**CreateProfile** 。</span><span class="sxs-lookup"><span data-stu-id="21792-128">You can call **CreateProfile** at application installation time or at any time during a session.</span></span> <span data-ttu-id="21792-129">在安装时调用此方法时, 许多配置设置来自 mapisvc.inf 配置文件。</span><span class="sxs-lookup"><span data-stu-id="21792-129">When this method is called at installation time, many of the configuration settings come from the Mapisvc.inf configuration file.</span></span> <span data-ttu-id="21792-130">在活动会话过程中调用此方法时, 这些设置将来自通过一系列属性表提示的用户。</span><span class="sxs-lookup"><span data-stu-id="21792-130">When this method is called during an active session, the settings come from the user who is prompted through a series of property sheets.</span></span> 
  
<span data-ttu-id="21792-131">如果在_ulFlags_参数中设置了 MAPI_DEFAULT_SERVICES 标志, 则**CreateProfile**会为 mapisvc.inf 文件中的 [默认服务] 部分中的每个邮件服务调用邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="21792-131">If the MAPI_DEFAULT_SERVICES flag is set in the  _ulFlags_ parameter, **CreateProfile** calls the message service entry point function for each message service in the [Default Services] section in the Mapisvc.inf file.</span></span> <span data-ttu-id="21792-132">调用每个邮件服务入口点函数时, _ulContext_参数设置为 MSG_SERVICE_CREATE。</span><span class="sxs-lookup"><span data-stu-id="21792-132">Each message service entry point function is called with the  _ulContext_ parameter set to MSG_SERVICE_CREATE.</span></span> 
  
<span data-ttu-id="21792-133">如果同时设置了 MAPI_DIALOG 和 MAPI_DEFAULT_SERVICES 标志, 则_ulUIParam_和_ulFlags_参数中的值也会传递给邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="21792-133">If both the MAPI_DIALOG and MAPI_DEFAULT_SERVICES flags are set, the values in the  _ulUIParam_ and  _ulFlags_ parameters are also passed to the message service entry point function.</span></span> <span data-ttu-id="21792-134">仅在将 mapisvc.inf 文件中的所有可用信息添加到配置文件后, 才会调用邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="21792-134">The message service entry point functions are called only after all available information from the Mapisvc.inf file has been added to the profile.</span></span> 
  
<span data-ttu-id="21792-135">新配置文件的名称及其密码的长度最长为64个字符, 并且可以包含以下字符:</span><span class="sxs-lookup"><span data-stu-id="21792-135">The name of the new profile and its password can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="21792-136">所有字母数字字符, 包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="21792-136">All alphanumeric characters, including accent characters and the underscore character.</span></span>
    
- <span data-ttu-id="21792-137">嵌入空格, 但不能是前导空格或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="21792-137">Embedded spaces, but not leading or trailing spaces.</span></span>
    
<span data-ttu-id="21792-138">_lpszPassword_参数必须为 NULL 或指向零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="21792-138">The  _lpszPassword_ parameter must be NULL or a pointer to a zero-length string.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="21792-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21792-139">See also</span></span>



[<span data-ttu-id="21792-140">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="21792-140">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="21792-141">IMsgServiceAdmin::CreateMsgService</span><span class="sxs-lookup"><span data-stu-id="21792-141">IMsgServiceAdmin::CreateMsgService</span></span>](imsgserviceadmin-createmsgservice.md)
  
[<span data-ttu-id="21792-142">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="21792-142">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="21792-143">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="21792-143">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

