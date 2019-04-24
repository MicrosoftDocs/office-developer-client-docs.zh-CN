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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309595"
---
# <a name="iprofadminadminservices"></a><span data-ttu-id="accd2-103">IProfAdmin::AdminServices</span><span class="sxs-lookup"><span data-stu-id="accd2-103">IProfAdmin::AdminServices</span></span>

  
  
<span data-ttu-id="accd2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="accd2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="accd2-105">提供对邮件服务管理对象的访问权限, 以对配置文件中的邮件服务进行更改。</span><span class="sxs-lookup"><span data-stu-id="accd2-105">Provides access to a message service administration object for making changes to the message services in a profile.</span></span>
  
```cpp
HRESULT AdminServices(
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSERVICEADMIN FAR * lppServiceAdmin
);
```

## <a name="parameters"></a><span data-ttu-id="accd2-106">参数</span><span class="sxs-lookup"><span data-stu-id="accd2-106">Parameters</span></span>

 <span data-ttu-id="accd2-107">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="accd2-107">_lpszProfileName_</span></span>
  
> <span data-ttu-id="accd2-108">实时指向要修改的配置文件的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="accd2-108">[in] A pointer to the name of the profile to be modified.</span></span> <span data-ttu-id="accd2-109">_lpszProfileName_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="accd2-109">The  _lpszProfileName_ parameter must not be NULL.</span></span> 
    
 <span data-ttu-id="accd2-110">_lpszPassword_</span><span class="sxs-lookup"><span data-stu-id="accd2-110">_lpszPassword_</span></span>
  
> <span data-ttu-id="accd2-111">实时始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="accd2-111">[in] Always NULL.</span></span> 
    
 <span data-ttu-id="accd2-112">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="accd2-112">_ulUIParam_</span></span>
  
> <span data-ttu-id="accd2-113">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="accd2-113">[in] A handle of the parent window for any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="accd2-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="accd2-114">_ulFlags_</span></span>
  
> <span data-ttu-id="accd2-115">实时用于控制邮件服务管理对象检索的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="accd2-115">[in] A bitmask of flags that controls the retrieval of the message service administration object.</span></span> <span data-ttu-id="accd2-116">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="accd2-116">The following flags can be set:</span></span>
    
<span data-ttu-id="accd2-117">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="accd2-117">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="accd2-118">启用用户界面的显示。</span><span class="sxs-lookup"><span data-stu-id="accd2-118">Enables the display of a user interface.</span></span> 
    
<span data-ttu-id="accd2-119">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="accd2-119">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="accd2-120">配置文件名称为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="accd2-120">The profile name is in Unicode format.</span></span> <span data-ttu-id="accd2-121">如果未设置 MAPI_UNICODE 标志, 则该名称为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="accd2-121">If the MAPI_UNICODE flag is not set, the name is in ANSI format.</span></span>
    
 <span data-ttu-id="accd2-122">_lppServiceAdmin_</span><span class="sxs-lookup"><span data-stu-id="accd2-122">_lppServiceAdmin_</span></span>
  
> <span data-ttu-id="accd2-123">排除指向邮件服务管理对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="accd2-123">[out] A pointer to a pointer to a message service administration object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="accd2-124">返回值</span><span class="sxs-lookup"><span data-stu-id="accd2-124">Return value</span></span>

<span data-ttu-id="accd2-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="accd2-125">S_OK</span></span> 
  
> <span data-ttu-id="accd2-126">成功返回邮件服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="accd2-126">The message service administration object was successfully returned.</span></span>
    
<span data-ttu-id="accd2-127">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="accd2-127">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="accd2-128">指定的配置文件不存在, 或者密码错误, 无法向用户显示一个对话框来请求正确的密码, 因为 MAPI_DIALOG 不是在_ulFlags_中设置的。</span><span class="sxs-lookup"><span data-stu-id="accd2-128">The specified profile does not exist, or the password was wrong and a dialog box could not be displayed to the user to request the correct password because MAPI_DIALOG was not set in  _ulFlags_.</span></span>
    
<span data-ttu-id="accd2-129">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="accd2-129">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="accd2-130">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="accd2-130">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="accd2-131">注解</span><span class="sxs-lookup"><span data-stu-id="accd2-131">Remarks</span></span>

<span data-ttu-id="accd2-132">**IProfAdmin:: AdminServices**方法提供对邮件服务管理对象的访问权限, 以便对配置文件中的邮件服务进行配置更改。</span><span class="sxs-lookup"><span data-stu-id="accd2-132">The **IProfAdmin::AdminServices** method provides access to a message service administration object for making configuration changes to the message services in a profile.</span></span> 
  
 <span data-ttu-id="accd2-133">_lpszPassword_参数必须为 NULL 或指向零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="accd2-133">The  _lpszPassword_ parameter must be NULL or a pointer to a zero-length string.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="accd2-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="accd2-134">Notes to callers</span></span>

<span data-ttu-id="accd2-135">尽管您可以通过调用此方法或[IMAPISession:: AdminServices](imapisession-adminservices.md), 调用**IProfAdmin:: AdminServices**来检索[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针, 前提是您严格拥有配置客户端且不提供邮件功能。</span><span class="sxs-lookup"><span data-stu-id="accd2-135">Although you can retrieve an [IMsgServiceAdmin](imsgserviceadminiunknown.md) pointer by calling either this method or [IMAPISession::AdminServices](imapisession-adminservices.md), call **IProfAdmin::AdminServices** if you have strictly a configuration client and offer no messaging features.</span></span> <span data-ttu-id="accd2-136">**IProfAdmin:: AdminServices**不会创建 session 对象, 也不会加载任何服务提供程序, 从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="accd2-136">**IProfAdmin::AdminServices** does not create a session object and does not load any service providers, which enhances performance.</span></span> 
  
<span data-ttu-id="accd2-137">您不能使用**IProfAdmin:: AdminServices**创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="accd2-137">You cannot use **IProfAdmin::AdminServices** to create a profile.</span></span> <span data-ttu-id="accd2-138">因此, 您必须在_lpszProfileName_中指定现有的有效配置文件。</span><span class="sxs-lookup"><span data-stu-id="accd2-138">Therefore, you must specify an existing valid profile in  _lpszProfileName_.</span></span> <span data-ttu-id="accd2-139">如果指定的配置文件不存在, 则**IProfAdmin:: AdminServices**将返回 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="accd2-139">If the specified profile does not exist, **IProfAdmin::AdminServices** returns MAPI_E_LOGON_FAILED.</span></span> 
  
<span data-ttu-id="accd2-140">配置文件的名称的长度最长为64个字符, 并且可以包含以下字符:</span><span class="sxs-lookup"><span data-stu-id="accd2-140">The name of the profile can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="accd2-141">所有字母数字字符, 包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="accd2-141">All alphanumeric characters, including accent characters and the underscore character.</span></span> 
    
- <span data-ttu-id="accd2-142">嵌入空格, 但不能是前导空格或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="accd2-142">Embedded spaces, but not leading or trailing spaces.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="accd2-143">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="accd2-143">MFCMAPI reference</span></span>

<span data-ttu-id="accd2-144">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="accd2-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="accd2-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="accd2-145">**File**</span></span>|<span data-ttu-id="accd2-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="accd2-146">**Function**</span></span>|<span data-ttu-id="accd2-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="accd2-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="accd2-148">MAPIProfileFunctions</span><span class="sxs-lookup"><span data-stu-id="accd2-148">MAPIProfileFunctions.cpp</span></span>  <br/> | <span data-ttu-id="accd2-149">HrAddServiceToProfile</span><span class="sxs-lookup"><span data-stu-id="accd2-149">HrAddServiceToProfile</span></span>  <br/> |<span data-ttu-id="accd2-150">MFCMAPI 使用**IProfAdmin:: AdminServices**方法打开所选配置文件的邮件服务管理对象以添加服务。</span><span class="sxs-lookup"><span data-stu-id="accd2-150">MFCMAPI uses the **IProfAdmin::AdminServices** method to open a message service administration object for the selected profile to add services.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="accd2-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="accd2-151">See also</span></span>



[<span data-ttu-id="accd2-152">IMAPISession::AdminServices</span><span class="sxs-lookup"><span data-stu-id="accd2-152">IMAPISession::AdminServices</span></span>](imapisession-adminservices.md)
  
[<span data-ttu-id="accd2-153">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="accd2-153">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)


[<span data-ttu-id="accd2-154">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="accd2-154">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

