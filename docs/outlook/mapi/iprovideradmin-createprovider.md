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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 72dddca5a8079374600e05b96a24cbbc25e7f7f9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279554"
---
# <a name="iprovideradmincreateprovider"></a><span data-ttu-id="74c51-103">IProviderAdmin::CreateProvider</span><span class="sxs-lookup"><span data-stu-id="74c51-103">IProviderAdmin::CreateProvider</span></span>

<span data-ttu-id="74c51-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="74c51-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="74c51-105">向邮件服务中添加服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="74c51-105">Adds a service provider to the message service.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="74c51-106">参数</span><span class="sxs-lookup"><span data-stu-id="74c51-106">Parameters</span></span>

 <span data-ttu-id="74c51-107">_lpszProvider_</span><span class="sxs-lookup"><span data-stu-id="74c51-107">_lpszProvider_</span></span>
  
> <span data-ttu-id="74c51-108">实时指向要添加的提供程序的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="74c51-108">[in] A pointer to the name of the provider to add.</span></span>
    
 <span data-ttu-id="74c51-109">_cValues_</span><span class="sxs-lookup"><span data-stu-id="74c51-109">_cValues_</span></span>
  
> <span data-ttu-id="74c51-110">实时由_lpProps_参数指向的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="74c51-110">[in] The count of property values pointed to by the  _lpProps_ parameter.</span></span> 
    
 <span data-ttu-id="74c51-111">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="74c51-111">_lpProps_</span></span>
  
> <span data-ttu-id="74c51-112">实时指向描述要添加的提供程序的属性的属性值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="74c51-112">[in] A pointer to a property value array that describes the properties of the provider to add.</span></span>
    
 <span data-ttu-id="74c51-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="74c51-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="74c51-114">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="74c51-114">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="74c51-115">如果在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 则使用_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="74c51-115">The  _ulUIParam_ parameter is used if the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="74c51-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="74c51-116">_ulFlags_</span></span>
  
> <span data-ttu-id="74c51-117">实时用于控制提供程序添加的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="74c51-117">[in] A bitmask of flags that controls the provider addition.</span></span> <span data-ttu-id="74c51-118">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="74c51-118">The following flags can be set:</span></span>
    
  - <span data-ttu-id="74c51-119">MAPI_DIALOG: 显示一个对话框, 提示输入配置信息。</span><span class="sxs-lookup"><span data-stu-id="74c51-119">MAPI_DIALOG: Displays a dialog box to prompt for configuration information.</span></span>
      
  - <span data-ttu-id="74c51-120">MAPI_UNICODE: 提供程序名称和字符串属性采用 UNICODE 格式。</span><span class="sxs-lookup"><span data-stu-id="74c51-120">MAPI_UNICODE: The provider name and string properties are in Unicode format.</span></span> <span data-ttu-id="74c51-121">如果未设置 MAPI_UNICODE 标志, 则这些字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="74c51-121">If the MAPI_UNICODE flag is not set, these strings are in ANSI format.</span></span>
    
 <span data-ttu-id="74c51-122">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="74c51-122">_lpUID_</span></span>
  
> <span data-ttu-id="74c51-123">排除指向[MAPIUID](mapiuid.md)结构的指针, 该对象包含表示要添加的提供程序的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="74c51-123">[out] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier that represents the provider to add.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="74c51-124">返回值</span><span class="sxs-lookup"><span data-stu-id="74c51-124">Return value</span></span>

<span data-ttu-id="74c51-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="74c51-125">S_OK</span></span> 
  
> <span data-ttu-id="74c51-126">已成功将该提供程序添加到邮件服务中。</span><span class="sxs-lookup"><span data-stu-id="74c51-126">The provider was successfully added to the message service.</span></span>
    
<span data-ttu-id="74c51-127">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="74c51-127">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="74c51-128">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="74c51-128">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="74c51-129">注解</span><span class="sxs-lookup"><span data-stu-id="74c51-129">Remarks</span></span>

<span data-ttu-id="74c51-130">**IProviderAdmin:: CreateProvider**方法将服务提供程序添加到邮件服务中。</span><span class="sxs-lookup"><span data-stu-id="74c51-130">The **IProviderAdmin::CreateProvider** method adds a service provider to the message service.</span></span> <span data-ttu-id="74c51-131">_lpszProvider_参数必须指向属于邮件服务的提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="74c51-131">The  _lpszProvider_ parameter must point to the name of a provider that belongs to the message service.</span></span> <span data-ttu-id="74c51-132">**CreateProvider**不验证该名称是否与服务中的提供程序的名称匹配;如果传递的名称与服务名称不匹配, 则调用会成功, 但结果是不可预知的。</span><span class="sxs-lookup"><span data-stu-id="74c51-132">**CreateProvider** does not verify whether the name matches the name of a provider in the service; if the passed name does not match a service name, the call succeeds, but the results are unpredictable.</span></span> <span data-ttu-id="74c51-133">大多数邮件服务在使用配置文件时不允许添加或删除提供程序。</span><span class="sxs-lookup"><span data-stu-id="74c51-133">Most message services do not allow providers to be added or deleted while the profile is in use.</span></span> 
  
<span data-ttu-id="74c51-134">从 mapisvc.inf 文件中将有关服务提供程序的所有可用信息添加到配置文件后, **CreateProvider**将调用邮件服务的入口点函数, 并将_ulContext_参数设置为 MSG_SERVICE_PROVIDER_CREATE。</span><span class="sxs-lookup"><span data-stu-id="74c51-134">After all of the available information about the service provider has been added to the profile from the Mapisvc.inf file, **CreateProvider** calls the message service's entry point function with the  _ulContext_ parameter set to MSG_SERVICE_PROVIDER_CREATE.</span></span> <span data-ttu-id="74c51-135">如果在**CreateProvider**方法的_ulFlags_参数中设置了 MAPI_DIALOG, 则_ulUIParam_和_ulFlags_参数中的值也会传递到入口点函数。</span><span class="sxs-lookup"><span data-stu-id="74c51-135">If MAPI_DIALOG is set in the **CreateProvider** method's  _ulFlags_ parameter, the values in the  _ulUIParam_ and  _ulFlags_ parameters are also passed to the entry point function.</span></span> <span data-ttu-id="74c51-136">这些附加参数使服务提供程序能够显示其属性表, 以便用户可以输入配置设置。</span><span class="sxs-lookup"><span data-stu-id="74c51-136">These additional parameters enable the service provider to display its property sheet so the user can enter configuration settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="74c51-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74c51-137">See also</span></span>

- [<span data-ttu-id="74c51-138">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="74c51-138">MAPIUID</span></span>](mapiuid.md)  
- [<span data-ttu-id="74c51-139">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="74c51-139">MSGSERVICEENTRY</span></span>](msgserviceentry.md)  
- [<span data-ttu-id="74c51-140">SPropValue</span><span class="sxs-lookup"><span data-stu-id="74c51-140">SPropValue</span></span>](spropvalue.md)  
- [<span data-ttu-id="74c51-141">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="74c51-141">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)

