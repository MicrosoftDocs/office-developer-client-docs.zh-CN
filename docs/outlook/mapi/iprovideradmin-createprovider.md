---
title: IProviderAdminCreateProvider
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.CreateProvider
api_type:
- COM
ms.assetid: 80c1449a-6cd9-4b93-a300-395979894b71
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 01cc8a8a54137b72091abab3671c08b526ef9e31
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776041"
---
# <a name="iprovideradmincreateprovider"></a><span data-ttu-id="11ecf-103">IProviderAdmin::CreateProvider</span><span class="sxs-lookup"><span data-stu-id="11ecf-103">IProviderAdmin::CreateProvider</span></span>

<span data-ttu-id="11ecf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="11ecf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="11ecf-105">向消息服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="11ecf-105">Adds a service provider to the message service.</span></span> 
  
```cpp
HRESULT CreateProvider(
  LPSTR lpszProvider,
  ULONG cValues,
  LPSPropValue lpProps,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  MAPIUID FAR * lpUID
);
```

## <a name="parameters"></a><span data-ttu-id="11ecf-106">参数</span><span class="sxs-lookup"><span data-stu-id="11ecf-106">Parameters</span></span>

 <span data-ttu-id="11ecf-107">_lpszProvider_</span><span class="sxs-lookup"><span data-stu-id="11ecf-107">_lpszProvider_</span></span>
  
> <span data-ttu-id="11ecf-108">[in]一个指向要添加的提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="11ecf-108">[in] A pointer to the name of the provider to add.</span></span>
    
 <span data-ttu-id="11ecf-109">_cValues_</span><span class="sxs-lookup"><span data-stu-id="11ecf-109">_cValues_</span></span>
  
> <span data-ttu-id="11ecf-110">[in]_LpProps_参数指向的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="11ecf-110">[in] The count of property values pointed to by the  _lpProps_ parameter.</span></span> 
    
 <span data-ttu-id="11ecf-111">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="11ecf-111">_lpProps_</span></span>
  
> <span data-ttu-id="11ecf-112">[in]一个指向介绍要添加的提供程序的属性的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="11ecf-112">[in] A pointer to a property value array that describes the properties of the provider to add.</span></span>
    
 <span data-ttu-id="11ecf-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="11ecf-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="11ecf-114">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="11ecf-114">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="11ecf-115">如果 MAPI_DIALOG 标志设置_ulFlags_参数中，使用_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="11ecf-115">The  _ulUIParam_ parameter is used if the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="11ecf-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="11ecf-116">_ulFlags_</span></span>
  
> <span data-ttu-id="11ecf-117">[in]位掩码的标志控制提供程序添加的。</span><span class="sxs-lookup"><span data-stu-id="11ecf-117">[in] A bitmask of flags that controls the provider addition.</span></span> <span data-ttu-id="11ecf-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="11ecf-118">The following flags can be set:</span></span>
    
  - <span data-ttu-id="11ecf-119">MAPI_DIALOG： 显示一个对话框，提示配置信息。</span><span class="sxs-lookup"><span data-stu-id="11ecf-119">MAPI_DIALOG: Displays a dialog box to prompt for configuration information.</span></span>
      
  - <span data-ttu-id="11ecf-120">MAPI_UNICODE： 提供程序名称和字符串属性采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="11ecf-120">MAPI_UNICODE: The provider name and string properties are in Unicode format.</span></span> <span data-ttu-id="11ecf-121">如果未设置 MAPI_UNICODE 标志，这些字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="11ecf-121">If the MAPI_UNICODE flag is not set, these strings are in ANSI format.</span></span>
    
 <span data-ttu-id="11ecf-122">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="11ecf-122">_lpUID_</span></span>
  
> <span data-ttu-id="11ecf-123">[输出]一个指向[MAPIUID](mapiuid.md)结构，其中包含代表要添加的提供程序的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="11ecf-123">[out] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier that represents the provider to add.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="11ecf-124">返回值</span><span class="sxs-lookup"><span data-stu-id="11ecf-124">Return value</span></span>

<span data-ttu-id="11ecf-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="11ecf-125">S_OK</span></span> 
  
> <span data-ttu-id="11ecf-126">提供程序已成功添加到邮件服务。</span><span class="sxs-lookup"><span data-stu-id="11ecf-126">The provider was successfully added to the message service.</span></span>
    
<span data-ttu-id="11ecf-127">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="11ecf-127">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="11ecf-128">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="11ecf-128">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="11ecf-129">说明</span><span class="sxs-lookup"><span data-stu-id="11ecf-129">Remarks</span></span>

<span data-ttu-id="11ecf-130">**IProviderAdmin::CreateProvider**方法向邮件服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="11ecf-130">The **IProviderAdmin::CreateProvider** method adds a service provider to the message service.</span></span> <span data-ttu-id="11ecf-131">_LpszProvider_参数必须指向属于邮件服务提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="11ecf-131">The  _lpszProvider_ parameter must point to the name of a provider that belongs to the message service.</span></span> <span data-ttu-id="11ecf-132">**CreateProvider**不验证该名称是否与服务; 中提供的名称匹配如果传递的名称不匹配的服务名称，调用成功，但结果将无法预料。</span><span class="sxs-lookup"><span data-stu-id="11ecf-132">**CreateProvider** does not verify whether the name matches the name of a provider in the service; if the passed name does not match a service name, the call succeeds, but the results are unpredictable.</span></span> <span data-ttu-id="11ecf-133">大多数消息服务不允许提供程序添加或删除配置文件时使用。</span><span class="sxs-lookup"><span data-stu-id="11ecf-133">Most message services do not allow providers to be added or deleted while the profile is in use.</span></span> 
  
<span data-ttu-id="11ecf-134">毕竟可用信息有关服务提供程序已添加到配置文件从 Mapisvc.inf 文件， **CreateProvider** _ulContext_参数设置为 MSG_SERVICE_ 呼叫消息服务的入口点函数PROVIDER_CREATE。</span><span class="sxs-lookup"><span data-stu-id="11ecf-134">After all of the available information about the service provider has been added to the profile from the Mapisvc.inf file, **CreateProvider** calls the message service's entry point function with the  _ulContext_ parameter set to MSG_SERVICE_PROVIDER_CREATE.</span></span> <span data-ttu-id="11ecf-135">如果 MAPI_DIALOG 设置**CreateProvider**方法的_ulFlags_参数中，在_ulUIParam_和_ulFlags_参数中的值还传递到入口点函数。</span><span class="sxs-lookup"><span data-stu-id="11ecf-135">If MAPI_DIALOG is set in the **CreateProvider** method's  _ulFlags_ parameter, the values in the  _ulUIParam_ and  _ulFlags_ parameters are also passed to the entry point function.</span></span> <span data-ttu-id="11ecf-136">这些其他参数启用要显示其属性表，以便用户可以输入配置设置的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="11ecf-136">These additional parameters enable the service provider to display its property sheet so the user can enter configuration settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="11ecf-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11ecf-137">See also</span></span>

- [<span data-ttu-id="11ecf-138">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="11ecf-138">MAPIUID</span></span>](mapiuid.md)  
- [<span data-ttu-id="11ecf-139">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="11ecf-139">MSGSERVICEENTRY</span></span>](msgserviceentry.md)  
- [<span data-ttu-id="11ecf-140">SPropValue</span><span class="sxs-lookup"><span data-stu-id="11ecf-140">SPropValue</span></span>](spropvalue.md)  
- [<span data-ttu-id="11ecf-141">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="11ecf-141">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)

