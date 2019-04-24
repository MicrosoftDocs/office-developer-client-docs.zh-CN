---
title: 实现服务提供程序登录
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3d3c309f-fe60-43a9-beda-16b09ec769db
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 533c00a0c994e7dfc5adc476899553bc39a2a9ab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310085"
---
# <a name="implementing-service-provider-logon"></a><span data-ttu-id="21eae-103">实现服务提供程序登录</span><span class="sxs-lookup"><span data-stu-id="21eae-103">Implementing Service Provider Logon</span></span>

<span data-ttu-id="21eae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="21eae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="21eae-105">MAPI 使用从入口点函数返回的指针调用提供程序对象中的方法, 以开始登录过程。</span><span class="sxs-lookup"><span data-stu-id="21eae-105">MAPI calls a method in your provider object to begin the logon process by using the pointer that you return from your entry point function.</span></span> <span data-ttu-id="21eae-106">根据您的服务提供程序的类型, 此方法的不同之处如下:</span><span class="sxs-lookup"><span data-stu-id="21eae-106">The method varies as follows, depending on the type of your service provider:</span></span>
  
- <span data-ttu-id="21eae-107">[IABProvider::](iabprovider-logon.md)通讯簿提供程序的登录名</span><span class="sxs-lookup"><span data-stu-id="21eae-107">[IABProvider::Logon](iabprovider-logon.md) for address book providers</span></span> 
    
- <span data-ttu-id="21eae-108">[IMSProvider::](imsprovider-logon.md)针对邮件存储提供程序的登录</span><span class="sxs-lookup"><span data-stu-id="21eae-108">[IMSProvider::Logon](imsprovider-logon.md) for message store providers</span></span> 
    
- <span data-ttu-id="21eae-109">[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)的传输提供程序</span><span class="sxs-lookup"><span data-stu-id="21eae-109">[IXPProvider::TransportLogon](ixpprovider-transportlogon.md) for transport providers</span></span> 
    
<span data-ttu-id="21eae-110">在您实施的任何登录方法中执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="21eae-110">Perform the following tasks in whatever logon method you implement:</span></span>
  
1. <span data-ttu-id="21eae-111">通过调用其[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来递增作为输入参数传递的 support 对象的引用计数。</span><span class="sxs-lookup"><span data-stu-id="21eae-111">Increment the reference count on the support object that is passed as an input parameter by calling its [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method.</span></span> 
    
2. <span data-ttu-id="21eae-112">调用支持对象的[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法以访问您的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="21eae-112">Call the support object's [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method to access your profile section.</span></span> 
    
3. <span data-ttu-id="21eae-113">调用配置文件节的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法以设置以下属性:</span><span class="sxs-lookup"><span data-stu-id="21eae-113">Call the profile section's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set the following properties:</span></span> 
    
  - <span data-ttu-id="21eae-114">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="21eae-114">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
  - <span data-ttu-id="21eae-115">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="21eae-115">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    
  - <span data-ttu-id="21eae-116">**PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="21eae-116">**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span></span>
    
  - <span data-ttu-id="21eae-117">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="21eae-117">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="21eae-118">请勿尝试设置 profile 节的**PR_RESOURCE_FLAGS**或**PR_PROVIDER_DLL_NAME**属性。</span><span class="sxs-lookup"><span data-stu-id="21eae-118">Do not attempt to set the profile section's **PR_RESOURCE_FLAGS** or **PR_PROVIDER_DLL_NAME** properties.</span></span> <span data-ttu-id="21eae-119">在登录时, 这些属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="21eae-119">At logon time, these properties are read-only.</span></span> 
  
4. <span data-ttu-id="21eae-120">检查配置所需的属性是否已存储在配置文件中, 或是否可从用户获取。</span><span class="sxs-lookup"><span data-stu-id="21eae-120">Check that the properties you need for configuration are either stored in the profile or are available from the user.</span></span> <span data-ttu-id="21eae-121">有关检查配置的详细信息, 请参阅[验证服务提供程序配置](verifying-service-provider-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="21eae-121">For more information about checking your configuration, see [Verifying Service Provider Configuration](verifying-service-provider-configuration.md).</span></span>
    
5. <span data-ttu-id="21eae-122">如果您的提供商是通讯簿或邮件存储提供程序, 则调用支持对象的[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)方法以注册唯一标识符或[MAPIUID](mapiuid.md)。</span><span class="sxs-lookup"><span data-stu-id="21eae-122">Call the support object's [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method to register a unique identifier, or [MAPIUID](mapiuid.md), if your provider is an address book or message store provider.</span></span> <span data-ttu-id="21eae-123">当 MAPI 调用其[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法时, 传输提供程序注册**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="21eae-123">Transport providers register **MAPIUID** structures when MAPI calls their [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> <span data-ttu-id="21eae-124">有关注册**MAPIUID**的详细信息, 请参阅[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="21eae-124">For more information about registering a **MAPIUID**, see [Registering Service Provider Unique Identifiers](registering-service-provider-unique-identifiers.md).</span></span>
    
6. <span data-ttu-id="21eae-125">实例化登录对象, 并返回以下值之一:</span><span class="sxs-lookup"><span data-stu-id="21eae-125">Instantiate a logon object and return with one of the following values:</span></span>
    
  - <span data-ttu-id="21eae-126">S_OK 表示登录成功。</span><span class="sxs-lookup"><span data-stu-id="21eae-126">S_OK to indicate a successful logon.</span></span>
    
  - <span data-ttu-id="21eae-127">MAPI_E_UNCONFIGURED, 以指示一个或多个配置属性不可用。</span><span class="sxs-lookup"><span data-stu-id="21eae-127">MAPI_E_UNCONFIGURED to indicate that one or more of the configuration properties were unavailable.</span></span>
    
  - <span data-ttu-id="21eae-128">MAPI_E_USER_CANCEL 指示用户取消了 "配置" 对话框, 从而导致配置属性不可用。</span><span class="sxs-lookup"><span data-stu-id="21eae-128">MAPI_E_USER_CANCEL to indicate that the user canceled the configuration dialog box, causing configuration properties to be unavailable.</span></span>
    
  - <span data-ttu-id="21eae-129">MAPI_E_FAILONEPROVIDER 指示无法配置您的提供程序, 但 MAPI 应允许使用它, 而不考虑。</span><span class="sxs-lookup"><span data-stu-id="21eae-129">MAPI_E_FAILONEPROVIDER to indicate that your provider could not be configured, but that MAPI should allow it to be used regardless.</span></span> <span data-ttu-id="21eae-130">登录方法应返回此值以报告非严重错误, 例如, 当提供程序需要密码时, 如果用户界面被禁用, 则不能提示用户。</span><span class="sxs-lookup"><span data-stu-id="21eae-130">Logon methods should return this value to report a nonfatal error, such as when the provider requires a password and cannot prompt the user for it because the user interface is disabled.</span></span> 
    
<span data-ttu-id="21eae-131">前面的任务列表介绍了服务提供程序登录方法的最低实现。</span><span class="sxs-lookup"><span data-stu-id="21eae-131">The preceding list of tasks describes a minimum implementation for a service provider logon method.</span></span> <span data-ttu-id="21eae-132">如有必要, 可以包括其他功能。</span><span class="sxs-lookup"><span data-stu-id="21eae-132">You can include additional functionality, if necessary.</span></span> <span data-ttu-id="21eae-133">例如, 某些提供程序调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)以在其登录方法中更新状态表。</span><span class="sxs-lookup"><span data-stu-id="21eae-133">For example, some providers call [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) to update the status table in their logon method.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="21eae-134">若要在登录时获得最佳性能, 请避免调用[IMAPISupport reparesubmit](imapisupport-preparesubmit.md)或[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)。</span><span class="sxs-lookup"><span data-stu-id="21eae-134">To achieve the best performance at logon time, avoid calling either [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md) or [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md).</span></span> <span data-ttu-id="21eae-135">必须先启动 MAPI 后台处理程序, 然后才能完成这些呼叫并将控制返回给您的登录方法。</span><span class="sxs-lookup"><span data-stu-id="21eae-135">Before these calls can complete and return control to your logon method, the MAPI spooler must be started.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="21eae-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21eae-136">See also</span></span>

- [<span data-ttu-id="21eae-137">启动服务提供程序</span><span class="sxs-lookup"><span data-stu-id="21eae-137">Starting a Service Provider</span></span>](starting-a-service-provider.md)

