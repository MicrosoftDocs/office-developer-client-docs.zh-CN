---
title: 实现通讯簿提供程序登录和注销
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c4a1fb5d-ae23-445b-a6f0-ef430b03fc9a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8d33bccdd01075d692e5a887082ba51ee23bb083
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438734"
---
# <a name="implementing-address-book-provider-logon-and-logoff"></a><span data-ttu-id="fceb5-103">实现通讯簿提供程序登录和注销</span><span class="sxs-lookup"><span data-stu-id="fceb5-103">Implementing Address Book Provider Logon and Logoff</span></span>

<span data-ttu-id="fceb5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fceb5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fceb5-105">通讯簿提供程序通过实现 [IABProvider ： IUnknown](iabprovideriunknown.md) 接口的方法支持会话登录和注销。</span><span class="sxs-lookup"><span data-stu-id="fceb5-105">Address book providers support session logon and logoff by implementing the methods of the [IABProvider : IUnknown](iabprovideriunknown.md) interface.</span></span> <span data-ttu-id="fceb5-106">\*\* IABProvider \*\* 接口直接继承自 **IUnknown** 并仅添加其他两种方法：**登录和\*\*\*\*关机**。</span><span class="sxs-lookup"><span data-stu-id="fceb5-106">The \*\* IABProvider \*\* interface inherits directly from **IUnknown** and adds only two other methods: **Logon** and **Shutdown**.</span></span> 
  
## <a name="logoff"></a><span data-ttu-id="fceb5-107">注销</span><span class="sxs-lookup"><span data-stu-id="fceb5-107">Logoff</span></span>

<span data-ttu-id="fceb5-108">MAPI 将在每个会话的开头以及将提供程序添加到当前配置文件且客户端支持动态重新配置时调用提供程序的 [IABProvider：：Logon](iabprovider-logon.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="fceb5-108">MAPI will call your provider's [IABProvider::Logon](iabprovider-logon.md) method at the beginning of every session and whenever your provider is added to the current profile and the client supports dynamic reconfiguration.</span></span> <span data-ttu-id="fceb5-109">当 MAPI 调用 **IABProvider：：Logon** 方法时，通讯簿提供程序将开始其登录过程。</span><span class="sxs-lookup"><span data-stu-id="fceb5-109">When MAPI calls the **IABProvider::Logon** method, your address book provider begins its logon process.</span></span> 
  
<span data-ttu-id="fceb5-110">**实现 IABProvider：：Log**</span><span class="sxs-lookup"><span data-stu-id="fceb5-110">**To implement IABProvider::Log**</span></span>
  
1. <span data-ttu-id="fceb5-111">初始化 MAPI 传入的所有输出参数指针。</span><span class="sxs-lookup"><span data-stu-id="fceb5-111">Initialize all of the output parameter pointers passed in by MAPI.</span></span> 
    
2. <span data-ttu-id="fceb5-112">调用支持对象的 **IUnknown：：AddRef** 方法来增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="fceb5-112">Call the support object's **IUnknown::AddRef** method to increment its reference count.</span></span> 
    
3. <span data-ttu-id="fceb5-113">调用支持对象的 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 方法以打开包含有关提供程序的配置信息的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="fceb5-113">Call the support object's [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method to open the section of the profile that contains configuration information about your provider.</span></span> <span data-ttu-id="fceb5-114">如果打算进行更改，请为  _lpUID_ 参数和 MAPI_MODIFY 标志传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="fceb5-114">Pass NULL for the  _lpUID_ parameter and the MAPI_MODIFY flag if you intend to make changes.</span></span> 
    
4. <span data-ttu-id="fceb5-115">调用配置文件节的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索提供程序登录所需的属性，例如数据文件或数据库表的名称。</span><span class="sxs-lookup"><span data-stu-id="fceb5-115">Call the profile section's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the properties that your provider needs for logon, such as the name of the data file or database table.</span></span> 
    
5. <span data-ttu-id="fceb5-116">检查属性是否全部可用且有效。</span><span class="sxs-lookup"><span data-stu-id="fceb5-116">Check that the properties are all available and valid.</span></span> <span data-ttu-id="fceb5-117">如有必要且允许，显示一个对话框，提示用户对无效或缺失的信息进行更正或添加，并调用配置文件节的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来保存任何更改。</span><span class="sxs-lookup"><span data-stu-id="fceb5-117">If necessary and allowed, display a dialog box to prompt the user to make corrections or additions to invalid or missing information and call the profile section's [IMAPIProp::SetProps](imapiprop-setprops.md) method to save any changes.</span></span> <span data-ttu-id="fceb5-118">一些应该可用的常见属性包括：</span><span class="sxs-lookup"><span data-stu-id="fceb5-118">Some of the common properties that should be available include:</span></span> 
    
   <span data-ttu-id="fceb5-119">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fceb5-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
   <span data-ttu-id="fceb5-120">**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fceb5-120">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    
   <span data-ttu-id="fceb5-121">**PR_PROVIDER_DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="fceb5-121">**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span></span>
    
   <span data-ttu-id="fceb5-122">**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="fceb5-122">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="fceb5-123">不要将 **PR_RESOURCE_FLAGS (** [PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 或 **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="fceb5-123">Do not set **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) or **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)).</span></span> <span data-ttu-id="fceb5-124">登录时，这些属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="fceb5-124">At logon time, these properties are read-only.</span></span> 
  
6. <span data-ttu-id="fceb5-125">如果一个或多个配置属性不可用，则失败并返回值 MAPI_E_UNCONFIGURED。</span><span class="sxs-lookup"><span data-stu-id="fceb5-125">If one or more configuration properties are unavailable, fail and return the value MAPI_E_UNCONFIGURED.</span></span>
    
7. <span data-ttu-id="fceb5-126">调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md) 注册 [MAPIUID](mapiuid.md)。</span><span class="sxs-lookup"><span data-stu-id="fceb5-126">Call [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) to register a [MAPIUID](mapiuid.md).</span></span> <span data-ttu-id="fceb5-127">你的提供程序可以通过：创建 **MAPIUID：**</span><span class="sxs-lookup"><span data-stu-id="fceb5-127">Your provider can create a **MAPIUID** by:</span></span> 
    
   - <span data-ttu-id="fceb5-128">调用 [IMAPISupport：：NewUID](imapisupport-newuid.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="fceb5-128">Calling the [IMAPISupport::NewUID](imapisupport-newuid.md) method.</span></span> 
    
   - <span data-ttu-id="fceb5-129">调用 UUIDGEN.EXE 工具定义提供程序用于包括在其头文件之一中的 GUID。</span><span class="sxs-lookup"><span data-stu-id="fceb5-129">Calling the UUIDGEN.EXE tool to define a GUID that your provider uses to include in one of its header files.</span></span>
    
8. <span data-ttu-id="fceb5-130">如果需要，通过调用配置文件节的 \*\* IMAPIProp：：SetProps \*\* 方法，将新创建的 **MAPIUID** 保存到当前配置文件中。</span><span class="sxs-lookup"><span data-stu-id="fceb5-130">If desired, save a newly created **MAPIUID** in the current profile by calling the profile section's \*\* IMAPIProp::SetProps \*\* method.</span></span> 
    
9. <span data-ttu-id="fceb5-131">通过调用其 **IUnknown：：Release 方法释放配置文件** 部分。</span><span class="sxs-lookup"><span data-stu-id="fceb5-131">Release the profile section by calling its **IUnknown::Release** method.</span></span> 
    
10. <span data-ttu-id="fceb5-132">实例化新的登录对象，将  _lppABLogon_ 参数的内容设置为此新对象的地址。</span><span class="sxs-lookup"><span data-stu-id="fceb5-132">Instantiate a new logon object and set the contents of the  _lppABLogon_ parameter to the address of this new object.</span></span> 
    
<span data-ttu-id="fceb5-133">由于 MAPI 可以在会话期间多次调用 \*\* Logon \*\* 方法，因此，通过能够创建多个登录对象并跟踪创建的每个对象，在实现中支持这种可能性是明智的。</span><span class="sxs-lookup"><span data-stu-id="fceb5-133">Because it is possible for MAPI to call your \*\* Logon \*\* method several times during a session, it is wise to support this possibility in your implementation by being able to create multiple logon objects and keep track of each object that is created.</span></span> <span data-ttu-id="fceb5-134">例如，支持 **多个** 登录调用使客户端应用程序的用户可以登录到具有不同标识的会话或使用不同的传递目标。</span><span class="sxs-lookup"><span data-stu-id="fceb5-134">Supporting multiple **Logon** calls enables a user of a client application, for example, to log on to a session with different identities or use different delivery destinations.</span></span> 
  
<span data-ttu-id="fceb5-135">**会话** 结束时将调用关闭。</span><span class="sxs-lookup"><span data-stu-id="fceb5-135">**Shutdown** is called when the session is ending.</span></span> <span data-ttu-id="fceb5-136">MAPI 调用 [IABProvider：：Shutdown](iabprovider-shutdown.md) 方法作为关闭会话所涉及的最后一项任务之一。</span><span class="sxs-lookup"><span data-stu-id="fceb5-136">MAPI calls your [IABProvider::Shutdown](iabprovider-shutdown.md) method as one of the last tasks involved in shutting down a session.</span></span> <span data-ttu-id="fceb5-137">MAPI 已释放提供程序的所有登录对象，当提供程序收到此调用时，它可以假定这是它将接收的最后一个调用。</span><span class="sxs-lookup"><span data-stu-id="fceb5-137">MAPI has released all of your provider's logon objects and, when your provider receives this call, it can assume that this is the last call it will receive.</span></span> <span data-ttu-id="fceb5-138">在 **IABProvider：：Shutdown** 的实现中，执行你认为必要的任何最终清理。</span><span class="sxs-lookup"><span data-stu-id="fceb5-138">In your implementation of **IABProvider::Shutdown**, perform any final cleanup that you feel is necessary.</span></span> <span data-ttu-id="fceb5-139">例如，如果提供程序调用 **MAPIInitIdle** 以在会话期间使用空闲引擎或尚未释放的任何对象的 **IUnknown：：Release** 方法，则提供程序可能会调用 **MAPIDeinitIdle。**</span><span class="sxs-lookup"><span data-stu-id="fceb5-139">For example, your provider might call **MAPIDeinitIdle** if it has called **MAPIInitIdle** to use the idle engine during the session or the **IUnknown::Release** method of any objects that have yet to be released.</span></span> 
  
<span data-ttu-id="fceb5-140">如果提供程序没有最终清理，其实现可以由一行代码决定：</span><span class="sxs-lookup"><span data-stu-id="fceb5-140">If your provider has no final cleanup, its implementation can be made up of a single line of code:</span></span> 
  
```cpp
return S_OK;

```


