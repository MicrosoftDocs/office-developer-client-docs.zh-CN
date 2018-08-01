---
title: 实现通讯簿提供程序登录和注销
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c4a1fb5d-ae23-445b-a6f0-ef430b03fc9a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1ffde0814fe5024a3f89a93462c48136712f1013
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775798"
---
# <a name="implementing-address-book-provider-logon-and-logoff"></a><span data-ttu-id="426f1-103">实现通讯簿提供程序登录和注销</span><span class="sxs-lookup"><span data-stu-id="426f1-103">Implementing Address Book Provider Logon and Logoff</span></span>

<span data-ttu-id="426f1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="426f1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="426f1-105">通讯簿提供程序实现的方法通过支持会话登录和注销[IABProvider: IUnknown](iabprovideriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="426f1-105">Address book providers support session logon and logoff by implementing the methods of the [IABProvider : IUnknown](iabprovideriunknown.md) interface.</span></span> <span data-ttu-id="426f1-106">* * IABProvider * * 界面直接从**IUnknown**继承并添加其他只有两个方法：**登录**和**关机**。</span><span class="sxs-lookup"><span data-stu-id="426f1-106">The ** IABProvider ** interface inherits directly from **IUnknown** and adds only two other methods: **Logon** and **Shutdown**.</span></span> 
  
## <a name="logoff"></a><span data-ttu-id="426f1-107">注销</span><span class="sxs-lookup"><span data-stu-id="426f1-107">Logoff</span></span>

<span data-ttu-id="426f1-108">MAPI 将调用您的提供商[IABProvider::Logon](iabprovider-logon.md)方法的开头的每个会话，只要您提供程序添加到当前配置文件和客户端支持动态重新配置。</span><span class="sxs-lookup"><span data-stu-id="426f1-108">MAPI will call your provider's [IABProvider::Logon](iabprovider-logon.md) method at the beginning of every session and whenever your provider is added to the current profile and the client supports dynamic reconfiguration.</span></span> <span data-ttu-id="426f1-109">MAPI 调用**IABProvider::Logon**方法时，通讯簿提供程序开始其登录过程。</span><span class="sxs-lookup"><span data-stu-id="426f1-109">When MAPI calls the **IABProvider::Logon** method, your address book provider begins its logon process.</span></span> 
  
<span data-ttu-id="426f1-110">**若要实现 IABProvider::Log**</span><span class="sxs-lookup"><span data-stu-id="426f1-110">**To implement IABProvider::Log**</span></span>
  
1. <span data-ttu-id="426f1-111">初始化所有通过 MAPI 传入的输出参数指针。</span><span class="sxs-lookup"><span data-stu-id="426f1-111">Initialize all of the output parameter pointers passed in by MAPI.</span></span> 
    
2. <span data-ttu-id="426f1-112">调用支持对象的**IUnknown::AddRef**方法，以增加引用计数。</span><span class="sxs-lookup"><span data-stu-id="426f1-112">Call the support object's **IUnknown::AddRef** method to increment its reference count.</span></span> 
    
3. <span data-ttu-id="426f1-113">调用支持对象的[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法以打开配置文件包含有关您的提供商的配置信息部分。</span><span class="sxs-lookup"><span data-stu-id="426f1-113">Call the support object's [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method to open the section of the profile that contains configuration information about your provider.</span></span> <span data-ttu-id="426f1-114">如果想要进行更改，请传递 NULL _lpUID_参数和 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="426f1-114">Pass NULL for the  _lpUID_ parameter and the MAPI_MODIFY flag if you intend to make changes.</span></span> 
    
4. <span data-ttu-id="426f1-115">调用配置文件部分的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索提供程序所需要的登录名，例如数据文件或数据库表的名称的属性。</span><span class="sxs-lookup"><span data-stu-id="426f1-115">Call the profile section's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the properties that your provider needs for logon, such as the name of the data file or database table.</span></span> 
    
5. <span data-ttu-id="426f1-116">检查属性所有可用且有效。</span><span class="sxs-lookup"><span data-stu-id="426f1-116">Check that the properties are all available and valid.</span></span> <span data-ttu-id="426f1-117">如果需要，并且允许，显示一个对话框，提示用户对无效或丢失信息进行更正或添加并调用配置文件部分的[IMAPIProp::SetProps](imapiprop-setprops.md)方法保存任何更改。</span><span class="sxs-lookup"><span data-stu-id="426f1-117">If necessary and allowed, display a dialog box to prompt the user to make corrections or additions to invalid or missing information and call the profile section's [IMAPIProp::SetProps](imapiprop-setprops.md) method to save any changes.</span></span> <span data-ttu-id="426f1-118">一些应该可用的通用属性包括：</span><span class="sxs-lookup"><span data-stu-id="426f1-118">Some of the common properties that should be available include:</span></span> 
    
   <span data-ttu-id="426f1-119">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="426f1-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
   <span data-ttu-id="426f1-120">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="426f1-120">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    
   <span data-ttu-id="426f1-121">**PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="426f1-121">**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span></span>
    
   <span data-ttu-id="426f1-122">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="426f1-122">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="426f1-123">未设置**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 或**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="426f1-123">Do not set **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) or **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)).</span></span> <span data-ttu-id="426f1-124">在登录时，这些属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="426f1-124">At logon time, these properties are read-only.</span></span> 
  
6. <span data-ttu-id="426f1-125">如果一个或多个配置属性不可用，失败并返回 MAPI_E_UNCONFIGURED 的值。</span><span class="sxs-lookup"><span data-stu-id="426f1-125">If one or more configuration properties are unavailable, fail and return the value MAPI_E_UNCONFIGURED.</span></span>
    
7. <span data-ttu-id="426f1-126">调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)注册[MAPIUID](mapiuid.md)。</span><span class="sxs-lookup"><span data-stu-id="426f1-126">Call [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) to register a [MAPIUID](mapiuid.md).</span></span> <span data-ttu-id="426f1-127">您的提供商可以创建由**MAPIUID** :</span><span class="sxs-lookup"><span data-stu-id="426f1-127">Your provider can create a **MAPIUID** by:</span></span> 
    
   - <span data-ttu-id="426f1-128">调用[IMAPISupport::NewUID](imapisupport-newuid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="426f1-128">Calling the [IMAPISupport::NewUID](imapisupport-newuid.md) method.</span></span> 
    
   - <span data-ttu-id="426f1-129">调用 UUIDGEN。EXE 工具定义您的提供商使用其标头文件中包含的 GUID。</span><span class="sxs-lookup"><span data-stu-id="426f1-129">Calling the UUIDGEN.EXE tool to define a GUID that your provider uses to include in one of its header files.</span></span>
    
8. <span data-ttu-id="426f1-130">如果需要，保存新创建的**MAPIUID**当前配置文件中通过调用配置文件部分的 * * IMAPIProp::SetProps * * 方法。</span><span class="sxs-lookup"><span data-stu-id="426f1-130">If desired, save a newly created **MAPIUID** in the current profile by calling the profile section's ** IMAPIProp::SetProps ** method.</span></span> 
    
9. <span data-ttu-id="426f1-131">通过调用其**IUnknown::Release**方法发布配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="426f1-131">Release the profile section by calling its **IUnknown::Release** method.</span></span> 
    
10. <span data-ttu-id="426f1-132">实例化一个新的登录对象并将_lppABLogon_参数的内容设置为此新对象的地址。</span><span class="sxs-lookup"><span data-stu-id="426f1-132">Instantiate a new logon object and set the contents of the  _lppABLogon_ parameter to the address of this new object.</span></span> 
    
<span data-ttu-id="426f1-133">因为它是可能的 MAPI 调用您 * * 登录 * * 在会话期间几次方法，则最好通过能够创建多个登录对象并跟踪创建每个对象在实现中支持这种可能性。</span><span class="sxs-lookup"><span data-stu-id="426f1-133">Because it is possible for MAPI to call your ** Logon ** method several times during a session, it is wise to support this possibility in your implementation by being able to create multiple logon objects and keep track of each object that is created.</span></span> <span data-ttu-id="426f1-134">支持多个**登录**呼叫允许用户客户端应用程序，例如，登录到不同的身份或使用不同的传送目标的会话。</span><span class="sxs-lookup"><span data-stu-id="426f1-134">Supporting multiple **Logon** calls enables a user of a client application, for example, to log on to a session with different identities or use different delivery destinations.</span></span> 
  
<span data-ttu-id="426f1-135">**关闭**时结束会话调用。</span><span class="sxs-lookup"><span data-stu-id="426f1-135">**Shutdown** is called when the session is ending.</span></span> <span data-ttu-id="426f1-136">MAPI 调用的最后一个任务之一[IABProvider::Shutdown](iabprovider-shutdown.md)方法关闭会话所涉及。</span><span class="sxs-lookup"><span data-stu-id="426f1-136">MAPI calls your [IABProvider::Shutdown](iabprovider-shutdown.md) method as one of the last tasks involved in shutting down a session.</span></span> <span data-ttu-id="426f1-137">MAPI 已发布的所有提供商的登录对象和，当您的提供商收到此呼叫时，它可以假设这是它将接收的最后一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="426f1-137">MAPI has released all of your provider's logon objects and, when your provider receives this call, it can assume that this is the last call it will receive.</span></span> <span data-ttu-id="426f1-138">**IABProvider::Shutdown**的实现中, 执行任何必要的最终清理。</span><span class="sxs-lookup"><span data-stu-id="426f1-138">In your implementation of **IABProvider::Shutdown**, perform any final cleanup that you feel is necessary.</span></span> <span data-ttu-id="426f1-139">例如，您的提供商可能会调用**MAPIDeinitIdle** ，如果它具有调用**MAPIInitIdle**会话或任何对象，具有尚未必须释放的**IUnknown::Release**方法期间使用的空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="426f1-139">For example, your provider might call **MAPIDeinitIdle** if it has called **MAPIInitIdle** to use the idle engine during the session or the **IUnknown::Release** method of any objects that have yet to be released.</span></span> 
  
<span data-ttu-id="426f1-140">如果您的提供不商任何最终清理，其实现的一行代码表进行：</span><span class="sxs-lookup"><span data-stu-id="426f1-140">If your provider has no final cleanup, its implementation can be made up of a single line of code:</span></span> 
  
```cpp
return S_OK;

```


