---
title: IProfAdminAdminServices
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.AdminServices
api_type:
- COM
ms.assetid: 87235fd2-6527-41a1-98ba-b951632a1c81
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7566bb075c2ef9903b5a376fd90f209c8683c31e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776003"
---
# <a name="iprofadminadminservices"></a><span data-ttu-id="c9979-103">IProfAdmin::AdminServices</span><span class="sxs-lookup"><span data-stu-id="c9979-103">IProfAdmin::AdminServices</span></span>

  
  
<span data-ttu-id="c9979-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c9979-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c9979-105">提供对邮件服务管理对象的更改配置文件中的消息服务的访问。</span><span class="sxs-lookup"><span data-stu-id="c9979-105">Provides access to a message service administration object for making changes to the message services in a profile.</span></span>
  
```cpp
HRESULT AdminServices(
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSERVICEADMIN FAR * lppServiceAdmin
);
```

## <a name="parameters"></a><span data-ttu-id="c9979-106">参数</span><span class="sxs-lookup"><span data-stu-id="c9979-106">Parameters</span></span>

 <span data-ttu-id="c9979-107">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="c9979-107">_lpszProfileName_</span></span>
  
> <span data-ttu-id="c9979-108">[in]一个指向要修改配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c9979-108">[in] A pointer to the name of the profile to be modified.</span></span> <span data-ttu-id="c9979-109">_LpszProfileName_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c9979-109">The  _lpszProfileName_ parameter must not be NULL.</span></span> 
    
 <span data-ttu-id="c9979-110">_lpszPassword_</span><span class="sxs-lookup"><span data-stu-id="c9979-110">_lpszPassword_</span></span>
  
> <span data-ttu-id="c9979-111">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c9979-111">[in] Always NULL.</span></span> 
    
 <span data-ttu-id="c9979-112">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="c9979-112">_ulUIParam_</span></span>
  
> <span data-ttu-id="c9979-113">[in]任何对话框的父窗口或该方法显示的窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="c9979-113">[in] A handle of the parent window for any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="c9979-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c9979-114">_ulFlags_</span></span>
  
> <span data-ttu-id="c9979-115">[in]位掩码的标志控制消息服务管理对象检索的。</span><span class="sxs-lookup"><span data-stu-id="c9979-115">[in] A bitmask of flags that controls the retrieval of the message service administration object.</span></span> <span data-ttu-id="c9979-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="c9979-116">The following flags can be set:</span></span>
    
<span data-ttu-id="c9979-117">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="c9979-117">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="c9979-118">启用的用户界面的显示。</span><span class="sxs-lookup"><span data-stu-id="c9979-118">Enables the display of a user interface.</span></span> 
    
<span data-ttu-id="c9979-119">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="c9979-119">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="c9979-120">配置文件名称为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="c9979-120">The profile name is in Unicode format.</span></span> <span data-ttu-id="c9979-121">如果未设置 MAPI_UNICODE 标志，名称为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="c9979-121">If the MAPI_UNICODE flag is not set, the name is in ANSI format.</span></span>
    
 <span data-ttu-id="c9979-122">_lppServiceAdmin_</span><span class="sxs-lookup"><span data-stu-id="c9979-122">_lppServiceAdmin_</span></span>
  
> <span data-ttu-id="c9979-123">[输出]指向与邮件服务管理对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c9979-123">[out] A pointer to a pointer to a message service administration object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c9979-124">返回值</span><span class="sxs-lookup"><span data-stu-id="c9979-124">Return value</span></span>

<span data-ttu-id="c9979-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9979-125">S_OK</span></span> 
  
> <span data-ttu-id="c9979-126">已成功返回消息服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="c9979-126">The message service administration object was successfully returned.</span></span>
    
<span data-ttu-id="c9979-127">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="c9979-127">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="c9979-128">指定的配置文件不存在，或密码不正确，无法向用户请求正确的密码，因为 MAPI_DIALOG 未设置_ulFlags_中显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="c9979-128">The specified profile does not exist, or the password was wrong and a dialog box could not be displayed to the user to request the correct password because MAPI_DIALOG was not set in  _ulFlags_.</span></span>
    
<span data-ttu-id="c9979-129">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="c9979-129">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="c9979-130">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="c9979-130">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c9979-131">说明</span><span class="sxs-lookup"><span data-stu-id="c9979-131">Remarks</span></span>

<span data-ttu-id="c9979-132">**IProfAdmin::AdminServices**方法提供对邮件服务管理对象的配置更改配置文件中的消息服务的访问。</span><span class="sxs-lookup"><span data-stu-id="c9979-132">The **IProfAdmin::AdminServices** method provides access to a message service administration object for making configuration changes to the message services in a profile.</span></span> 
  
 <span data-ttu-id="c9979-133">_LpszPassword_参数必须为空或为零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="c9979-133">The  _lpszPassword_ parameter must be NULL or a pointer to a zero-length string.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c9979-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c9979-134">Notes to callers</span></span>

<span data-ttu-id="c9979-135">尽管您可以通过调用此方法或[IMAPISession::AdminServices](imapisession-adminservices.md)检索[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针，调用**IProfAdmin::AdminServices** ，如果您具有严格配置客户端，并提供任何消息功能。</span><span class="sxs-lookup"><span data-stu-id="c9979-135">Although you can retrieve an [IMsgServiceAdmin](imsgserviceadminiunknown.md) pointer by calling either this method or [IMAPISession::AdminServices](imapisession-adminservices.md), call **IProfAdmin::AdminServices** if you have strictly a configuration client and offer no messaging features.</span></span> <span data-ttu-id="c9979-136">**IProfAdmin::AdminServices**不创建会话对象，并且未加载任何服务提供商，其增强了性能。</span><span class="sxs-lookup"><span data-stu-id="c9979-136">**IProfAdmin::AdminServices** does not create a session object and does not load any service providers, which enhances performance.</span></span> 
  
<span data-ttu-id="c9979-137">不能使用**IProfAdmin::AdminServices**创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="c9979-137">You cannot use **IProfAdmin::AdminServices** to create a profile.</span></span> <span data-ttu-id="c9979-138">因此，您必须在_lpszProfileName_指定现有的有效的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c9979-138">Therefore, you must specify an existing valid profile in  _lpszProfileName_.</span></span> <span data-ttu-id="c9979-139">如果指定的配置文件不存在，则**IProfAdmin::AdminServices**返回 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="c9979-139">If the specified profile does not exist, **IProfAdmin::AdminServices** returns MAPI_E_LOGON_FAILED.</span></span> 
  
<span data-ttu-id="c9979-140">配置文件的名称的长度最多为 64 个字符，并可以包含下列字符：</span><span class="sxs-lookup"><span data-stu-id="c9979-140">The name of the profile can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="c9979-141">所有字母数字字符，包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="c9979-141">All alphanumeric characters, including accent characters and the underscore character.</span></span> 
    
- <span data-ttu-id="c9979-142">嵌入的空格，但不是前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="c9979-142">Embedded spaces, but not leading or trailing spaces.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="c9979-143">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="c9979-143">MFCMAPI reference</span></span>

<span data-ttu-id="c9979-144">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c9979-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c9979-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="c9979-145">**File**</span></span>|<span data-ttu-id="c9979-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="c9979-146">**Function**</span></span>|<span data-ttu-id="c9979-147">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c9979-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9979-148">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="c9979-148">MAPIProfileFunctions.cpp</span></span>  <br/> | <span data-ttu-id="c9979-149">HrAddServiceToProfile</span><span class="sxs-lookup"><span data-stu-id="c9979-149">HrAddServiceToProfile</span></span>  <br/> |<span data-ttu-id="c9979-150">MFCMAPI 使用**IProfAdmin::AdminServices**方法打开选定的配置文件添加服务消息服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="c9979-150">MFCMAPI uses the **IProfAdmin::AdminServices** method to open a message service administration object for the selected profile to add services.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c9979-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9979-151">See also</span></span>



[<span data-ttu-id="c9979-152">IMAPISession::AdminServices</span><span class="sxs-lookup"><span data-stu-id="c9979-152">IMAPISession::AdminServices</span></span>](imapisession-adminservices.md)
  
[<span data-ttu-id="c9979-153">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c9979-153">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)


[<span data-ttu-id="c9979-154">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c9979-154">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

