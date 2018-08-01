---
title: 实现服务提供程序登录
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3d3c309f-fe60-43a9-beda-16b09ec769db
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eb64f2780530fd30784bf9a9b197bcde205b4a5a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775818"
---
# <a name="implementing-service-provider-logon"></a><span data-ttu-id="308ee-103">实现服务提供程序登录</span><span class="sxs-lookup"><span data-stu-id="308ee-103">Implementing Service Provider Logon</span></span>

<span data-ttu-id="308ee-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="308ee-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="308ee-105">MAPI 提供程序对象以开始使用您从您的入口点函数返回的指针的登录过程中调用的方法。</span><span class="sxs-lookup"><span data-stu-id="308ee-105">MAPI calls a method in your provider object to begin the logon process by using the pointer that you return from your entry point function.</span></span> <span data-ttu-id="308ee-106">该方法，如下所示，取决于您的服务提供程序的类型：</span><span class="sxs-lookup"><span data-stu-id="308ee-106">The method varies as follows, depending on the type of your service provider:</span></span>
  
- <span data-ttu-id="308ee-107">[IABProvider::Logon](iabprovider-logon.md)地址簿提供程序</span><span class="sxs-lookup"><span data-stu-id="308ee-107">[IABProvider::Logon](iabprovider-logon.md) for address book providers</span></span> 
    
- <span data-ttu-id="308ee-108">[IMSProvider::Logon](imsprovider-logon.md)消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="308ee-108">[IMSProvider::Logon](imsprovider-logon.md) for message store providers</span></span> 
    
- <span data-ttu-id="308ee-109">[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)传输提供程序</span><span class="sxs-lookup"><span data-stu-id="308ee-109">[IXPProvider::TransportLogon](ixpprovider-transportlogon.md) for transport providers</span></span> 
    
<span data-ttu-id="308ee-110">在实现任何登录方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="308ee-110">Perform the following tasks in whatever logon method you implement:</span></span>
  
1. <span data-ttu-id="308ee-111">递增上通过调用其[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)方法传递作为输入参数的支持对象的引用计数。</span><span class="sxs-lookup"><span data-stu-id="308ee-111">Increment the reference count on the support object that is passed as an input parameter by calling its [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx) method.</span></span> 
    
2. <span data-ttu-id="308ee-112">调用支持对象的[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法，以访问您的配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="308ee-112">Call the support object's [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method to access your profile section.</span></span> 
    
3. <span data-ttu-id="308ee-113">调用配置文件部分的[IMAPIProp::SetProps](imapiprop-setprops.md)方法来设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="308ee-113">Call the profile section's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set the following properties:</span></span> 
    
  - <span data-ttu-id="308ee-114">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="308ee-114">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
  - <span data-ttu-id="308ee-115">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="308ee-115">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    
  - <span data-ttu-id="308ee-116">**PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="308ee-116">**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span></span>
    
  - <span data-ttu-id="308ee-117">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="308ee-117">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="308ee-118">请务尝试设置配置文件节的**PR_RESOURCE_FLAGS**或**PR_PROVIDER_DLL_NAME**属性。</span><span class="sxs-lookup"><span data-stu-id="308ee-118">Do not attempt to set the profile section's **PR_RESOURCE_FLAGS** or **PR_PROVIDER_DLL_NAME** properties.</span></span> <span data-ttu-id="308ee-119">在登录时，这些属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="308ee-119">At logon time, these properties are read-only.</span></span> 
  
4. <span data-ttu-id="308ee-120">检查可以存储在配置文件或可从用户所需的配置属性。</span><span class="sxs-lookup"><span data-stu-id="308ee-120">Check that the properties you need for configuration are either stored in the profile or are available from the user.</span></span> <span data-ttu-id="308ee-121">有关检查您的配置的详细信息，请参阅[验证服务提供程序配置](verifying-service-provider-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="308ee-121">For more information about checking your configuration, see [Verifying Service Provider Configuration](verifying-service-provider-configuration.md).</span></span>
    
5. <span data-ttu-id="308ee-122">如果您的提供商的地址簿或消息存储提供程序，请调用注册的唯一标识符或[MAPIUID](mapiuid.md)，支持对象的[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="308ee-122">Call the support object's [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method to register a unique identifier, or [MAPIUID](mapiuid.md), if your provider is an address book or message store provider.</span></span> <span data-ttu-id="308ee-123">传输提供程序注册**MAPIUID**结构时 MAPI 调用其[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法。</span><span class="sxs-lookup"><span data-stu-id="308ee-123">Transport providers register **MAPIUID** structures when MAPI calls their [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> <span data-ttu-id="308ee-124">有关注册**MAPIUID**的详细信息，请参阅[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="308ee-124">For more information about registering a **MAPIUID**, see [Registering Service Provider Unique Identifiers](registering-service-provider-unique-identifiers.md).</span></span>
    
6. <span data-ttu-id="308ee-125">实例化一个登录对象并返回具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="308ee-125">Instantiate a logon object and return with one of the following values:</span></span>
    
  - <span data-ttu-id="308ee-126">以指示成功登录的 S_OK。</span><span class="sxs-lookup"><span data-stu-id="308ee-126">S_OK to indicate a successful logon.</span></span>
    
  - <span data-ttu-id="308ee-127">MAPI_E_UNCONFIGURED 以指示的一个或多个配置属性不可用。</span><span class="sxs-lookup"><span data-stu-id="308ee-127">MAPI_E_UNCONFIGURED to indicate that one or more of the configuration properties were unavailable.</span></span>
    
  - <span data-ttu-id="308ee-128">MAPI_E_USER_CANCEL 可以指示用户取消配置对话框中，导致无法配置属性。</span><span class="sxs-lookup"><span data-stu-id="308ee-128">MAPI_E_USER_CANCEL to indicate that the user canceled the configuration dialog box, causing configuration properties to be unavailable.</span></span>
    
  - <span data-ttu-id="308ee-129">MAPI_E_FAILONEPROVIDER 表明，无法配置您的提供商，但 MAPI 应允许其无论使用。</span><span class="sxs-lookup"><span data-stu-id="308ee-129">MAPI_E_FAILONEPROVIDER to indicate that your provider could not be configured, but that MAPI should allow it to be used regardless.</span></span> <span data-ttu-id="308ee-130">登录方法应返回此值以报告非致命错误，例如提供程序时需要密码和无法提示用户为其因为禁用用户界面。</span><span class="sxs-lookup"><span data-stu-id="308ee-130">Logon methods should return this value to report a nonfatal error, such as when the provider requires a password and cannot prompt the user for it because the user interface is disabled.</span></span> 
    
<span data-ttu-id="308ee-131">上述列表中的任务描述服务提供程序 logon 方法的最小实现。</span><span class="sxs-lookup"><span data-stu-id="308ee-131">The preceding list of tasks describes a minimum implementation for a service provider logon method.</span></span> <span data-ttu-id="308ee-132">如有必要，可以包含其他功能。</span><span class="sxs-lookup"><span data-stu-id="308ee-132">You can include additional functionality, if necessary.</span></span> <span data-ttu-id="308ee-133">例如，某些提供程序调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)要更新其登录方法中的状态表。</span><span class="sxs-lookup"><span data-stu-id="308ee-133">For example, some providers call [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) to update the status table in their logon method.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="308ee-134">若要获得最佳性能在登录时，避免调用[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md)或[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)。</span><span class="sxs-lookup"><span data-stu-id="308ee-134">To achieve the best performance at logon time, avoid calling either [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md) or [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md).</span></span> <span data-ttu-id="308ee-135">这些呼叫可以完成和控制权归还给您的登录方法之前，必须启动 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="308ee-135">Before these calls can complete and return control to your logon method, the MAPI spooler must be started.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="308ee-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="308ee-136">See also</span></span>

- [<span data-ttu-id="308ee-137">启动服务提供程序</span><span class="sxs-lookup"><span data-stu-id="308ee-137">Starting a Service Provider</span></span>](starting-a-service-provider.md)

