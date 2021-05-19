---
title: 状态对象实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 48fd3e28-c2d2-474d-9487-5e2f08ca7319
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e97efb70716ffbd7fa98f980ce8520cfcb988532
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336335"
---
# <a name="status-object-implementation"></a><span data-ttu-id="2af0e-103">状态对象实现</span><span class="sxs-lookup"><span data-stu-id="2af0e-103">Status object implementation</span></span>

<span data-ttu-id="2af0e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2af0e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2af0e-105">所有服务提供程序都必须实现状态对象，并且将该对象中的属性提供至会话状态表。</span><span class="sxs-lookup"><span data-stu-id="2af0e-105">All service providers must implement a status object and furnish properties from it to the session status table.</span></span> <span data-ttu-id="2af0e-106">您可以在状态表中包括一行或多行，具体取决于您控制的资源数。</span><span class="sxs-lookup"><span data-stu-id="2af0e-106">You can include one or more rows in the status table, depending on the number of resources that you control.</span></span> <span data-ttu-id="2af0e-107">例如，传输提供程序应在状态表中为它管理的每个邮件队列创建一行。</span><span class="sxs-lookup"><span data-stu-id="2af0e-107">A transport provider, for example, should create a row in the status table for each message queue it manages.</span></span> <span data-ttu-id="2af0e-108">发生更改时，必须更新相应的状态表行。</span><span class="sxs-lookup"><span data-stu-id="2af0e-108">When changes occur, the appropriate status table row must be updated.</span></span> <span data-ttu-id="2af0e-109">实现 Status 对象可提供对状态表中包含的信息和表中未包含的其他信息的访问。</span><span class="sxs-lookup"><span data-stu-id="2af0e-109">Status objects are implemented to provide access both to the information included in the status table and to additional information not included in the table.</span></span>
  
### <a name="to-implement-a-status-object"></a><span data-ttu-id="2af0e-110">实现状态对象</span><span class="sxs-lookup"><span data-stu-id="2af0e-110">To implement a status object</span></span>

1. <span data-ttu-id="2af0e-111">实现登录对象的 **OpenStatusEntry** 方法。</span><span class="sxs-lookup"><span data-stu-id="2af0e-111">Implement the **OpenStatusEntry** method of your logon object.</span></span> <span data-ttu-id="2af0e-112">当客户端想要打开状态对象时，它们调用 [IMAPISession：：OpenEntry](imapisession-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="2af0e-112">When clients want to open your status object, they call [IMAPISession::OpenEntry](imapisession-openentry.md).</span></span> <span data-ttu-id="2af0e-113">MAPI 通过调用提供程序的 **OpenStatusEntry** 方法实现打开的请求，从而导致提供程序打开其状态对象，并返回到客户端一个指向 **其 IMAPIStatus** 实现的指针。</span><span class="sxs-lookup"><span data-stu-id="2af0e-113">MAPI fulfills the open request by calling your provider's **OpenStatusEntry** method, causing your provider to open its status object and return to the client a pointer to its **IMAPIStatus** implementation.</span></span> <span data-ttu-id="2af0e-114">在 **OpenStatusEntry** 实现中，完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2af0e-114">In your **OpenStatusEntry** implementation, complete the following steps:</span></span> 
    
   1. <span data-ttu-id="2af0e-115">如果登录对象尚未创建状态对象，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2af0e-115">Perform the following tasks if your logon object has not yet created a status object:</span></span>
    
      1. <span data-ttu-id="2af0e-116">调用支持对象的 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 方法以访问提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="2af0e-116">Call the support object's [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method to access your provider's profile section.</span></span> 
          
      2. <span data-ttu-id="2af0e-117">创建新的状态对象。</span><span class="sxs-lookup"><span data-stu-id="2af0e-117">Create a new status object.</span></span>
          
      3. <span data-ttu-id="2af0e-118">在提供程序的状态对象中存储对配置文件节的引用，并调用配置文件节的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) 方法来增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="2af0e-118">Store a reference to the profile section in your provider's status object and call the profile section's [IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) method to increment its reference count.</span></span> 
          
      4. <span data-ttu-id="2af0e-119">在提供程序的状态对象中存储对登录对象的引用，并调用登录对象的 **IUnknown：：AddRef** 方法来增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="2af0e-119">Store a reference to the logon object in your provider's status object and call the logon object's **IUnknown::AddRef** method to increment its reference count.</span></span> 
          
      5. <span data-ttu-id="2af0e-120">在提供程序的登录对象中存储对 status 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2af0e-120">Store a reference to the status object in your provider's logon object.</span></span>
    
   2. <span data-ttu-id="2af0e-121">调用 status 对象的 **IUnknown：：AddRef** 方法，以在登录对象中增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="2af0e-121">Call the status object's **IUnknown::AddRef** method to increment its reference count in the logon object.</span></span> 
    
   3. <span data-ttu-id="2af0e-122">将 status 对象的PR_OBJECT_TYPE ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 设置为 MAPI_STATUS。</span><span class="sxs-lookup"><span data-stu-id="2af0e-122">Set the status object's **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) property to MAPI_STATUS.</span></span>
    
   4. <span data-ttu-id="2af0e-123">将  _lppMAPIStatus_ 输出参数设置为指向 status 对象并返回。</span><span class="sxs-lookup"><span data-stu-id="2af0e-123">Set the  _lppMAPIStatus_ output parameter to point to the status object, and return.</span></span> 
    
   5. <span data-ttu-id="2af0e-124">检查  _ulFlags_ 输入参数。</span><span class="sxs-lookup"><span data-stu-id="2af0e-124">Check the  _ulFlags_ input parameter.</span></span> <span data-ttu-id="2af0e-125">如果设置为"MAPI_MODIFY提供程序支持对状态对象的读/写访问，则返回一个可写对象。</span><span class="sxs-lookup"><span data-stu-id="2af0e-125">If it is set to MAPI_MODIFY and your provider supports read/write access to its status object, return a writeable object.</span></span> <span data-ttu-id="2af0e-126">但是，如果您的提供程序不支持对 status 对象的读/写访问，请不要失败。</span><span class="sxs-lookup"><span data-stu-id="2af0e-126">However, if your provider does not support read/write access to its status object, do not fail.</span></span> <span data-ttu-id="2af0e-127">返回一个只读状态对象。</span><span class="sxs-lookup"><span data-stu-id="2af0e-127">Return a status object that is read-only.</span></span> <span data-ttu-id="2af0e-128">预期接收读/写状态对象的客户端应在尝试进行更改之前验证已授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="2af0e-128">Clients that expect to receive read/write status objects should verify that read/write permission has been granted before attempting to make any changes.</span></span> 
    
2. <span data-ttu-id="2af0e-129">设置所有必需的状态对象和状态表属性。</span><span class="sxs-lookup"><span data-stu-id="2af0e-129">Set all of the required status object and status table properties.</span></span> <span data-ttu-id="2af0e-130">状态表行中包括的属性应该可以通过状态对象使用，MAPI 计算的属性除外。</span><span class="sxs-lookup"><span data-stu-id="2af0e-130">The properties that you include in your status table row should be available through your status object, except for the properties calculated by MAPI.</span></span> <span data-ttu-id="2af0e-131">所需属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="2af0e-131">The required properties are as follows:</span></span>
    
   - <span data-ttu-id="2af0e-132">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2af0e-132">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
   - <span data-ttu-id="2af0e-133">**PR_PROVIDER_DLL_NAME (** [PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2af0e-133">**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))</span></span>
    
   - <span data-ttu-id="2af0e-134">**PR_PROVIDER_DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2af0e-134">**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span></span>
    
   - <span data-ttu-id="2af0e-135">**PR_RESOURCE_TYPE (** [PidTagResourceType](pidtagresourcetype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2af0e-135">**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span></span>
    
   - <span data-ttu-id="2af0e-136">**PR_RESOURCE_METHODS (** [PidTagResourceMethods)](pidtagresourcemethods-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2af0e-136">**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))</span></span>
    
   - <span data-ttu-id="2af0e-137">**PR_RESOURCE_FLAGS (** [PidTagResourceFlags)](pidtagresourceflags-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2af0e-137">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span></span>
    
   - <span data-ttu-id="2af0e-138">**PR_STATUS_CODE (** [PidTagStatusCode](pidtagstatuscode-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2af0e-138">**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md))</span></span>
    
3. <span data-ttu-id="2af0e-139">实现适用于你的提供程序的 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="2af0e-139">Implement the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) methods that are appropriate for your provider.</span></span> <span data-ttu-id="2af0e-140">根据你的提供程序，你无需在 **IMAPIStatus** 中实现所有四种方法。</span><span class="sxs-lookup"><span data-stu-id="2af0e-140">Depending on your provider, you do not need to implement all of the four methods in **IMAPIStatus**.</span></span> <span data-ttu-id="2af0e-141">每个提供程序都应实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 接口和 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法方法的只读版本。</span><span class="sxs-lookup"><span data-stu-id="2af0e-141">Every provider should implement a read-only version of the methods of the [IMAPIProp : IUnknown](imapipropiunknown.md) interface and the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> 

   <span data-ttu-id="2af0e-142">传输提供程序还应实现 [IMAPIStatus：：FlushQueues](imapistatus-flushqueues.md)，并且所有提供程序都应支持 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md)。</span><span class="sxs-lookup"><span data-stu-id="2af0e-142">Transport providers should also implement [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md), and all providers should support [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md).</span></span> <span data-ttu-id="2af0e-143">但是，对 [IMAPIStatus：：ChangePassword](imapistatus-changepassword.md) 的支持是可选的。</span><span class="sxs-lookup"><span data-stu-id="2af0e-143">However, support for [IMAPIStatus::ChangePassword](imapistatus-changepassword.md) is optional.</span></span> <span data-ttu-id="2af0e-144">只有需要密码并且希望允许用户以编程方式更改密码的服务提供商才需要实现此方法。</span><span class="sxs-lookup"><span data-stu-id="2af0e-144">Only service providers that require passwords and want to allow users to change them programmatically need to implement this method.</span></span> <span data-ttu-id="2af0e-145">对于您支持的每种方法，在 PR_RESOURCE_METHODS 属性 **中** 设置相应的位。</span><span class="sxs-lookup"><span data-stu-id="2af0e-145">For every method that you support, set the corresponding bit in the **PR_RESOURCE_METHODS** property.</span></span> <span data-ttu-id="2af0e-146">例如，如果仅支持 **ValidateState** 和 **SettingsDialog，PR_RESOURCE_METHODS\*\*\*\*设置为：**</span><span class="sxs-lookup"><span data-stu-id="2af0e-146">For example, if you support **ValidateState** and **SettingsDialog** only, set **PR_RESOURCE_METHODS** to the following:</span></span> 
    
   `STATUS_VALIDATE_STATE | STATUS_SETTINGS_DIALOG`
    
   <span data-ttu-id="2af0e-147">客户端应先检查PR_RESOURCE_METHODS，然后再尝试调用状态对象。</span><span class="sxs-lookup"><span data-stu-id="2af0e-147">Clients should check the value of **PR_RESOURCE_METHODS** before attempting to call your status object.</span></span> <span data-ttu-id="2af0e-148">通过返回任何不受支持的方法来处理MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="2af0e-148">Handle calls to any of your unsupported methods by returning MAPI_E_NO_SUPPORT.</span></span> 
    
4. <span data-ttu-id="2af0e-149">在 [登录期间调用 IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md) 以将一行或多行添加到状态表中。</span><span class="sxs-lookup"><span data-stu-id="2af0e-149">Call [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) during logon to add your row or rows to the status table.</span></span> <span data-ttu-id="2af0e-150">传递一个属性值数组，其中包含行的列信息  _，ulFlags_ 参数的列信息为 0。</span><span class="sxs-lookup"><span data-stu-id="2af0e-150">Pass a property value array that contains the column information for the row and 0 for the  _ulFlags_ parameter.</span></span> <span data-ttu-id="2af0e-151">如果稍后在会话中提供程序的状态发生更改，并且有必要更新列信息，请再次调用 **ModifyStatusRow，** 并设置 STATUSROW_UPDATE标记。</span><span class="sxs-lookup"><span data-stu-id="2af0e-151">If at some point later in the session your provider's status changes and it becomes necessary to update the column information, call **ModifyStatusRow** again with the STATUSROW_UPDATE flag set.</span></span> 
    
<span data-ttu-id="2af0e-152">有关状态对象的信息，请参阅 [MAPI Status Objects](mapi-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="2af0e-152">For more information about status objects, see [MAPI Status Objects](mapi-status-objects.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2af0e-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2af0e-153">See also</span></span>

- [<span data-ttu-id="2af0e-154">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="2af0e-154">MAPI Service Providers</span></span>](mapi-service-providers.md)

