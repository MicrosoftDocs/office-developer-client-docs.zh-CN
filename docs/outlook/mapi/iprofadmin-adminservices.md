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
ms.openlocfilehash: 2c504f98655e35af62810dd428e8e04878a36dec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422080"
---
# <a name="iprofadminadminservices"></a><span data-ttu-id="35129-103">IProfAdmin::AdminServices</span><span class="sxs-lookup"><span data-stu-id="35129-103">IProfAdmin::AdminServices</span></span>

  
  
<span data-ttu-id="35129-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="35129-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="35129-105">提供对邮件服务管理对象的访问权限，以对配置文件中的邮件服务进行更改。</span><span class="sxs-lookup"><span data-stu-id="35129-105">Provides access to a message service administration object for making changes to the message services in a profile.</span></span>
  
```cpp
HRESULT AdminServices(
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSERVICEADMIN FAR * lppServiceAdmin
);
```

## <a name="parameters"></a><span data-ttu-id="35129-106">参数</span><span class="sxs-lookup"><span data-stu-id="35129-106">Parameters</span></span>

 <span data-ttu-id="35129-107">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="35129-107">_lpszProfileName_</span></span>
  
> <span data-ttu-id="35129-108">[in]指向要修改的配置文件的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="35129-108">[in] A pointer to the name of the profile to be modified.</span></span> <span data-ttu-id="35129-109">_lpszProfileName_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="35129-109">The  _lpszProfileName_ parameter must not be NULL.</span></span> 
    
 <span data-ttu-id="35129-110">_lpszPassword_</span><span class="sxs-lookup"><span data-stu-id="35129-110">_lpszPassword_</span></span>
  
> <span data-ttu-id="35129-111">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="35129-111">[in] Always NULL.</span></span> 
    
 <span data-ttu-id="35129-112">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="35129-112">_ulUIParam_</span></span>
  
> <span data-ttu-id="35129-113">[in]此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="35129-113">[in] A handle of the parent window for any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="35129-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="35129-114">_ulFlags_</span></span>
  
> <span data-ttu-id="35129-115">[in]控制邮件服务管理对象检索的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="35129-115">[in] A bitmask of flags that controls the retrieval of the message service administration object.</span></span> <span data-ttu-id="35129-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="35129-116">The following flags can be set:</span></span>
    
<span data-ttu-id="35129-117">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="35129-117">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="35129-118">启用用户界面的显示。</span><span class="sxs-lookup"><span data-stu-id="35129-118">Enables the display of a user interface.</span></span> 
    
<span data-ttu-id="35129-119">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="35129-119">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="35129-120">配置文件名称采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="35129-120">The profile name is in Unicode format.</span></span> <span data-ttu-id="35129-121">如果未MAPI_UNICODE，则名称采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="35129-121">If the MAPI_UNICODE flag is not set, the name is in ANSI format.</span></span>
    
 <span data-ttu-id="35129-122">_lppServiceAdmin_</span><span class="sxs-lookup"><span data-stu-id="35129-122">_lppServiceAdmin_</span></span>
  
> <span data-ttu-id="35129-123">[out]指向指向邮件服务管理对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="35129-123">[out] A pointer to a pointer to a message service administration object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="35129-124">返回值</span><span class="sxs-lookup"><span data-stu-id="35129-124">Return value</span></span>

<span data-ttu-id="35129-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="35129-125">S_OK</span></span> 
  
> <span data-ttu-id="35129-126">已成功返回邮件服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="35129-126">The message service administration object was successfully returned.</span></span>
    
<span data-ttu-id="35129-127">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="35129-127">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="35129-128">指定的配置文件不存在，或者密码错误，并且无法向用户显示对话框来请求正确的密码，因为 MAPI_DIALOG  _ulFlags_ 中未设置。</span><span class="sxs-lookup"><span data-stu-id="35129-128">The specified profile does not exist, or the password was wrong and a dialog box could not be displayed to the user to request the correct password because MAPI_DIALOG was not set in  _ulFlags_.</span></span>
    
<span data-ttu-id="35129-129">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="35129-129">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="35129-130">用户通常通过单击对话框中的"取消" **按钮来取消** 操作。</span><span class="sxs-lookup"><span data-stu-id="35129-130">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="35129-131">备注</span><span class="sxs-lookup"><span data-stu-id="35129-131">Remarks</span></span>

<span data-ttu-id="35129-132">**IProfAdmin：：AdminServices** 方法提供对邮件服务管理对象的访问权限，以对配置文件中的邮件服务进行配置更改。</span><span class="sxs-lookup"><span data-stu-id="35129-132">The **IProfAdmin::AdminServices** method provides access to a message service administration object for making configuration changes to the message services in a profile.</span></span> 
  
 <span data-ttu-id="35129-133">_lpszPassword_ 参数必须为 NULL 或指向零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="35129-133">The  _lpszPassword_ parameter must be NULL or a pointer to a zero-length string.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="35129-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="35129-134">Notes to callers</span></span>

<span data-ttu-id="35129-135">尽管可以通过调用此方法或 [IMAPISession：：AdminServices](imapisession-adminservices.md)来检索 [IMsgServiceAdmin](imsgserviceadminiunknown.md)指针，但如果严格具有配置客户端并且未提供消息功能，请调用 **IProfAdmin：：AdminServices。**</span><span class="sxs-lookup"><span data-stu-id="35129-135">Although you can retrieve an [IMsgServiceAdmin](imsgserviceadminiunknown.md) pointer by calling either this method or [IMAPISession::AdminServices](imapisession-adminservices.md), call **IProfAdmin::AdminServices** if you have strictly a configuration client and offer no messaging features.</span></span> <span data-ttu-id="35129-136">**IProfAdmin：：AdminServices** 不会创建会话对象，也不加载任何服务提供程序，这将提高性能。</span><span class="sxs-lookup"><span data-stu-id="35129-136">**IProfAdmin::AdminServices** does not create a session object and does not load any service providers, which enhances performance.</span></span> 
  
<span data-ttu-id="35129-137">不能使用 **IProfAdmin：：AdminServices** 创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="35129-137">You cannot use **IProfAdmin::AdminServices** to create a profile.</span></span> <span data-ttu-id="35129-138">因此，您必须在  _lpszProfileName_ 中指定现有的有效配置文件。</span><span class="sxs-lookup"><span data-stu-id="35129-138">Therefore, you must specify an existing valid profile in  _lpszProfileName_.</span></span> <span data-ttu-id="35129-139">如果指定的配置文件不存在， **则 IProfAdmin：：AdminServices** 将返回MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="35129-139">If the specified profile does not exist, **IProfAdmin::AdminServices** returns MAPI_E_LOGON_FAILED.</span></span> 
  
<span data-ttu-id="35129-140">配置文件的名称长度最多为 64 个字符，可以包含下列字符：</span><span class="sxs-lookup"><span data-stu-id="35129-140">The name of the profile can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="35129-141">所有字母数字字符，包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="35129-141">All alphanumeric characters, including accent characters and the underscore character.</span></span> 
    
- <span data-ttu-id="35129-142">嵌入空格，但不包括前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="35129-142">Embedded spaces, but not leading or trailing spaces.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="35129-143">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="35129-143">MFCMAPI reference</span></span>

<span data-ttu-id="35129-144">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="35129-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="35129-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="35129-145">**File**</span></span>|<span data-ttu-id="35129-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="35129-146">**Function**</span></span>|<span data-ttu-id="35129-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="35129-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="35129-148">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="35129-148">MAPIProfileFunctions.cpp</span></span>  <br/> | <span data-ttu-id="35129-149">HrAddServiceToProfile</span><span class="sxs-lookup"><span data-stu-id="35129-149">HrAddServiceToProfile</span></span>  <br/> |<span data-ttu-id="35129-150">MFCMAPI 使用 **IProfAdmin：：AdminServices** 方法打开所选配置文件的邮件服务管理对象以添加服务。</span><span class="sxs-lookup"><span data-stu-id="35129-150">MFCMAPI uses the **IProfAdmin::AdminServices** method to open a message service administration object for the selected profile to add services.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="35129-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35129-151">See also</span></span>



[<span data-ttu-id="35129-152">IMAPISession::AdminServices</span><span class="sxs-lookup"><span data-stu-id="35129-152">IMAPISession::AdminServices</span></span>](imapisession-adminservices.md)
  
[<span data-ttu-id="35129-153">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="35129-153">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)


[<span data-ttu-id="35129-154">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="35129-154">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

