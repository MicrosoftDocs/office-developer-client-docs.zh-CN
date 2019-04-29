---
title: 充当外部通讯簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6d532ed4-7dc5-46a9-995a-72bc97d16f6e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 300681bd585e9d534113404a82f43565f4e79bb4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435738"
---
# <a name="acting-as-a-foreign-address-book-provider"></a><span data-ttu-id="40f0a-103">充当外部通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="40f0a-103">Acting as a foreign address book provider</span></span>

<span data-ttu-id="40f0a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="40f0a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="40f0a-105">外部提供程序是一个通讯簿提供程序, 该提供程序:</span><span class="sxs-lookup"><span data-stu-id="40f0a-105">A foreign provider is an address book provider that:</span></span> 
  
- <span data-ttu-id="40f0a-106">为其收件人分配模板标识符。</span><span class="sxs-lookup"><span data-stu-id="40f0a-106">Assigns template identifiers for its recipients.</span></span>
    
- <span data-ttu-id="40f0a-107">支持[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="40f0a-107">Supports the [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> 
    
- <span data-ttu-id="40f0a-108">提供用于维护在其他通讯簿提供程序 (称为主机提供程序) 的容器中存在的收件人的代码。</span><span class="sxs-lookup"><span data-stu-id="40f0a-108">Supplies code for maintaining recipients that exist in the containers of other address book providers known as host providers.</span></span> <span data-ttu-id="40f0a-109">此代码涉及一个 property 对象 (通常为**IMAPIProp**接口实现), 该实现将属性对象包装在主机提供程序中。</span><span class="sxs-lookup"><span data-stu-id="40f0a-109">This code involves a property object, typically an **IMAPIProp** interface implementation, which wraps a property object from the host provider.</span></span> 
    
<span data-ttu-id="40f0a-110">充当外部提供程序是一个可选角色;并非所有提供程序都需要支持模板标识符及其相关代码。</span><span class="sxs-lookup"><span data-stu-id="40f0a-110">Acting as a foreign provider is an optional role; not all providers need to support template identifiers and their related code.</span></span> <span data-ttu-id="40f0a-111">如果要保持对承载提供程序使用您的提供程序提供的模板创建的收件人的控制, 请将提供程序实现为外部提供程序。</span><span class="sxs-lookup"><span data-stu-id="40f0a-111">Implement your provider as a foreign provider if you want to maintain control over recipients that host providers create using templates supplied by your provider.</span></span> 
  
<span data-ttu-id="40f0a-112">提供程序用于其条目标识符的格式也可用于其模板标识符。</span><span class="sxs-lookup"><span data-stu-id="40f0a-112">The format that your provider uses for its entry identifiers can also be used for its template identifiers.</span></span> <span data-ttu-id="40f0a-113">模板标识符必须包含提供程序注册的**MAPIUID** , 以使 MAPI 能够成功地将收件人绑定到相应的提供程序。</span><span class="sxs-lookup"><span data-stu-id="40f0a-113">Template identifiers must include your provider's registered **MAPIUID** to enable MAPI to successfully bind recipients to the appropriate providers.</span></span> 
  
<span data-ttu-id="40f0a-114">当主机提供程序调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)时, MAPI 会调用您的提供程序的**IABLogon:: OpenTemplateID**方法。</span><span class="sxs-lookup"><span data-stu-id="40f0a-114">MAPI calls your provider's **IABLogon::OpenTemplateID** method when a host provider calls [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md).</span></span> <span data-ttu-id="40f0a-115">主机提供程序在其对**IMAPISupport:: OpenTemplateID**的调用中传递_lpTemplateID_参数中收件人的模板标识符。</span><span class="sxs-lookup"><span data-stu-id="40f0a-115">The host provider passes the template identifier of the recipient in the  _lpTemplateID_ parameter in its call to **IMAPISupport::OpenTemplateID**.</span></span> <span data-ttu-id="40f0a-116">MAPI 通过将模板标识符中的[MAPIUID](mapiuid.md)与提供程序在登录时注册的**MAPIUID**相匹配, 来确定模板标识符属于您的提供程序。</span><span class="sxs-lookup"><span data-stu-id="40f0a-116">MAPI determines that the template identifier belongs to your provider by matching the [MAPIUID](mapiuid.md) in the template identifier with the **MAPIUID** that your provider registered at logon time.</span></span> <span data-ttu-id="40f0a-117">然后, MAPI 通过**IABLogon:: OpenTemplateID**方法将主机提供程序的调用转发给您的提供程序。</span><span class="sxs-lookup"><span data-stu-id="40f0a-117">MAPI then forwards the host provider's call to your provider through the **IABLogon::OpenTemplateID** method.</span></span> 
  
<span data-ttu-id="40f0a-118">主机提供程序还向_lpMAPIPropData_参数中的收件人传递指向其 property 对象实现的指针, _lpInterface_参数中的接口标识符与接口实现的类型相对应传入_lpMAPIPropData_和可选标志 FILL_ENTRY。</span><span class="sxs-lookup"><span data-stu-id="40f0a-118">The host provider also passes a pointer to its property object implementation for the recipient in the  _lpMAPIPropData_ parameter, an interface identifier in the  _lpInterface_ parameter that corresponds to the type of interface implementation passed in  _lpMAPIPropData_, and an optional flag, FILL_ENTRY.</span></span> <span data-ttu-id="40f0a-119">您的提供程序应在_lppMAPIPropNew_参数中返回一个指向_lpInterface_中指定的类型的属性对象实现的指针。</span><span class="sxs-lookup"><span data-stu-id="40f0a-119">Your provider is expected to return in the  _lppMAPIPropNew_ parameter a pointer to a property object implementation of the type specified in  _lpInterface_.</span></span> <span data-ttu-id="40f0a-120">返回的指针可指向由提供程序实现的包装属性对象, 或由_lpMAPIPropData_中主机提供程序所提供的对象。</span><span class="sxs-lookup"><span data-stu-id="40f0a-120">The returned pointer can either be to the wrapped property object implemented by your provider or to the object supplied by the host provider in  _lpMAPIPropData_.</span></span> <span data-ttu-id="40f0a-121">当出现以下情况时, 提供程序应返回回绕的 property 对象指针:</span><span class="sxs-lookup"><span data-stu-id="40f0a-121">Your provider should return a wrapped property object pointer when:</span></span>
  
- <span data-ttu-id="40f0a-122">收件人的显示表格包含列表框控件。</span><span class="sxs-lookup"><span data-stu-id="40f0a-122">The recipient's display table contains list box controls.</span></span>
    
- <span data-ttu-id="40f0a-123">收件人的电子邮件地址必须从多个显示表控件中的数据进行组合。</span><span class="sxs-lookup"><span data-stu-id="40f0a-123">The email address for the recipient must be assembled from data in multiple display table controls.</span></span>
    
- <span data-ttu-id="40f0a-124">提供程序问题显示表通知。</span><span class="sxs-lookup"><span data-stu-id="40f0a-124">Your provider issues display table notifications.</span></span>
    
<span data-ttu-id="40f0a-125">FILL_ENTRY 标志向提供程序指明主机提供程序需要更新收件人的所有属性。</span><span class="sxs-lookup"><span data-stu-id="40f0a-125">The FILL_ENTRY flag indicates to your provider that the host provider requires all the properties of the recipient to be updated.</span></span> <span data-ttu-id="40f0a-126">需要提供程序才能完成此请求。</span><span class="sxs-lookup"><span data-stu-id="40f0a-126">Your provider is required to fulfill this request.</span></span>
  
<span data-ttu-id="40f0a-127">当主机提供程序调用您的提供程序的**OpenTemplateID**方法时, 您的提供程序可能会:</span><span class="sxs-lookup"><span data-stu-id="40f0a-127">When a host provider calls your provider's **OpenTemplateID** method, your provider might:</span></span> 
  
- <span data-ttu-id="40f0a-128">定期更新复制的条目的数据。</span><span class="sxs-lookup"><span data-stu-id="40f0a-128">Periodically update the data for a copied entry.</span></span>
    
- <span data-ttu-id="40f0a-129">保留已复制的条目与原始条目的同步, 例如将通讯簿条目复制到个人通讯簿中的时间。</span><span class="sxs-lookup"><span data-stu-id="40f0a-129">Keep a copied entry synchronized with its original, such as when an address book entry is copied to the personal address book.</span></span>
    
- <span data-ttu-id="40f0a-130">实现无法由主机提供程序实现的功能, 例如, 从服务器上的数据动态填充复制项的详细信息表中的列表框。</span><span class="sxs-lookup"><span data-stu-id="40f0a-130">Implement functionality that cannot be implemented by the host provider, such as dynamically populating list boxes in the copied entry's details table from data on a server.</span></span>
    
- <span data-ttu-id="40f0a-131">控制复制的项或实例化模板中的属性之间的交互。</span><span class="sxs-lookup"><span data-stu-id="40f0a-131">Control the interaction among properties in a copied entry or instantiated template.</span></span> <span data-ttu-id="40f0a-132">例如, 从详细信息表中显示的其他属性计算**PR_EMAIL_ADDRESS** 。</span><span class="sxs-lookup"><span data-stu-id="40f0a-132">For example, computing **PR_EMAIL_ADDRESS** from other properties displayed in the details table.</span></span> 
    
<span data-ttu-id="40f0a-133">前两项是不要求提供程序提供包装属性对象 (基于主机提供程序的实现的**IMAPIProp**实现) 的任务示例。</span><span class="sxs-lookup"><span data-stu-id="40f0a-133">The first two items are examples of tasks that do not require your provider to supply a wrapped property object — an implementation of **IMAPIProp** that is based on the host provider's implementation.</span></span> <span data-ttu-id="40f0a-134">提供程序可以简单地根据需要更新属性并返回, 并将_lppMAPIPropNew_参数设置为指向由主机提供程序在_lpMAPIPropData_参数中传递的指针。</span><span class="sxs-lookup"><span data-stu-id="40f0a-134">Your provider can simply update the properties as necessary and return, setting the  _lppMAPIPropNew_ parameter to point to the pointer passed in by the host provider in the  _lpMAPIPropData_ parameter.</span></span> 
  
<span data-ttu-id="40f0a-135">第二个任务要求提供程序向主机提供程序返回一个属性对象, 该对象使用其他功能 (如显示项的属性表的功能) 包装主机提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="40f0a-135">The second two tasks require that your provider return to the host provider a property object that wraps the host provider's object with additional functionality, such as the ability to display a property sheet for the entry.</span></span> <span data-ttu-id="40f0a-136">此属性对象可以是邮件用户或通讯组列表, 具体取决于由_lpMAPIPropData_参数中的主机提供程序传入的对象的类型, 并由_lpInterface_参数中的接口标识符指示。</span><span class="sxs-lookup"><span data-stu-id="40f0a-136">This property object will either be a messaging user or distribution list, depending on the type of object passed in by the host provider in the  _lpMAPIPropData_ parameter and indicated by the interface identifier in the  _lpInterface_ parameter.</span></span> <span data-ttu-id="40f0a-137">如果_lpMAPIPropData_参数指向邮件用户, 则提供程序的包装属性对象必须是**IMailUser**实现。</span><span class="sxs-lookup"><span data-stu-id="40f0a-137">If the  _lpMAPIPropData_ parameter points to a messaging user, your provider's wrapped property object must be an **IMailUser** implementation.</span></span> <span data-ttu-id="40f0a-138">如果_lpMAPIPropData_指向通讯组列表, 则它必须是**IDistList**实现。</span><span class="sxs-lookup"><span data-stu-id="40f0a-138">If  _lpMAPIPropData_ points to a distribution list, it must be an **IDistList** implementation.</span></span> 
  
<span data-ttu-id="40f0a-139">提供程序的包装属性对象会截取**IMAPIProp**方法调用, 以执行主机提供程序的收件人的特定于上下文的操作 (它所包装的对象)。</span><span class="sxs-lookup"><span data-stu-id="40f0a-139">Your provider's wrapped property object intercepts **IMAPIProp** method calls to perform context-specific manipulation of the host provider's recipient—the object it is wrapping.</span></span> <span data-ttu-id="40f0a-140">MAPI 仅对回绕的 property 对象有一个要求: 对[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性的所有调用都应传递给主机提供程序。</span><span class="sxs-lookup"><span data-stu-id="40f0a-140">MAPI only has one requirement for wrapped property objects: all calls to [IMAPIProp::OpenProperty](imapiprop-openproperty.md) requesting the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property should be passed to the host provider.</span></span> <span data-ttu-id="40f0a-141">提供程序的实现可以使用返回的表截获显示表通知, 或在必要时添加自己的实现。</span><span class="sxs-lookup"><span data-stu-id="40f0a-141">Your provider's implementation can use the returned table to intercept display table notifications or to add its own if necessary.</span></span> 
  
<span data-ttu-id="40f0a-142">下面的列表包含通常在由外来提供程序实现的包装属性对象中实现的任务:</span><span class="sxs-lookup"><span data-stu-id="40f0a-142">The following list includes tasks that are typically implemented in the wrapped property object implemented by foreign providers:</span></span>
  
- <span data-ttu-id="40f0a-143">[IMAPIProp:: GetProps](imapiprop-getprops.md)中主机收件人的预处理和后处理属性值。</span><span class="sxs-lookup"><span data-stu-id="40f0a-143">Preprocessing and postprocessing property values for the host recipient in [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span>
    
- <span data-ttu-id="40f0a-144">处理详细信息显示表控件, 如**IMAPIProp:: OpenProperty**中的按钮和列表框。</span><span class="sxs-lookup"><span data-stu-id="40f0a-144">Handling details display table controls, such as buttons and list boxes, in **IMAPIProp::OpenProperty**.</span></span>
    
- <span data-ttu-id="40f0a-145">在[IMAPIProp:: SetProps](imapiprop-setprops.md)中验证或操作主机收件人的属性值。</span><span class="sxs-lookup"><span data-stu-id="40f0a-145">Validating or manipulating property values for the host recipient in [IMAPIProp::SetProps](imapiprop-setprops.md).</span></span>
    
- <span data-ttu-id="40f0a-146">在[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)中保存主机收件人之前, 请计算必需的属性, 如**PR_EMAIL_ADDRESS**和验证是否已设置所有必需的属性。</span><span class="sxs-lookup"><span data-stu-id="40f0a-146">Computing required properties such as **PR_EMAIL_ADDRESS** and verifying that all of the necessary properties have been set before saving the host recipient in [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span>
    
### <a name="to-implement-iablogonopentemplateid"></a><span data-ttu-id="40f0a-147">实现 IABLogon:: OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="40f0a-147">To implement IABLogon::OpenTemplateID</span></span>
  
1. <span data-ttu-id="40f0a-148">检查使用_lpTemplateID_参数传入的模板标识符是否有效, 以及提供程序识别的格式。</span><span class="sxs-lookup"><span data-stu-id="40f0a-148">Check if the template identifier passed in with the  _lpTemplateID_ parameter is valid and is in a format that your provider recognizes.</span></span> <span data-ttu-id="40f0a-149">如果不是, 则失败并返回 MAPI_E_INVALID_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="40f0a-149">If it is not, fail and return MAPI_E_INVALID_ENTRYID.</span></span> 
    
2. <span data-ttu-id="40f0a-150">创建由模板标识符指示的类型的对象, 可以是邮件用户、通讯组列表或一次性收件人。</span><span class="sxs-lookup"><span data-stu-id="40f0a-150">Create an object of the type indicated by the template identifier, either a messaging user, distribution list, or one-off recipient.</span></span> 
    
3. <span data-ttu-id="40f0a-151">调用主机提供程序的 property 对象中的**IUnknown:: AddRef**方法, 该方法是_lpMAPIPropData_参数指向的对象。</span><span class="sxs-lookup"><span data-stu-id="40f0a-151">Call the **IUnknown::AddRef** method in the host provider's property object, which is the object pointed to by the  _lpMAPIPropData_ parameter.</span></span> 
    
4. <span data-ttu-id="40f0a-152">如果将_ulTemplateFlags_参数设置为 FILL_ENTRY:</span><span class="sxs-lookup"><span data-stu-id="40f0a-152">If the  _ulTemplateFlags_ parameter is set to FILL_ENTRY:</span></span> 
    
   1. <span data-ttu-id="40f0a-153">如果新对象是邮件用户或通讯组列表:</span><span class="sxs-lookup"><span data-stu-id="40f0a-153">If the new object is a messaging user or distribution list:</span></span>
      
      1. <span data-ttu-id="40f0a-154">检索新对象的所有属性, 可能是通过调用其**IMAPIProp:: GetProps**方法。</span><span class="sxs-lookup"><span data-stu-id="40f0a-154">Retrieve all of the properties of the new object, possibly by calling its **IMAPIProp::GetProps** method.</span></span> 
          
      2. <span data-ttu-id="40f0a-155">调用主机提供程序的**IMAPIProp:: SetProps**方法将所有检索到的属性复制到主机提供程序的 property 对象。</span><span class="sxs-lookup"><span data-stu-id="40f0a-155">Call the host provider's **IMAPIProp::SetProps** method to copy all of the retrieved properties to the host provider's property object.</span></span> 
      
   2. <span data-ttu-id="40f0a-156">如果新对象是一次性收件人, 请调用主机提供程序的**IMAPIProp:: SetProps**方法来设置以下属性:</span><span class="sxs-lookup"><span data-stu-id="40f0a-156">If the new object is a one-off recipient, call the host provider's **IMAPIProp::SetProps** method to set the following properties:</span></span> 
      
      - <span data-ttu-id="40f0a-157">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 到由提供程序处理的地址类型。</span><span class="sxs-lookup"><span data-stu-id="40f0a-157">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) to the address type handled by your provider.</span></span>
        
      - <span data-ttu-id="40f0a-158">**从\_** _lpTemplateID_和_cbTemplateID_参数到模板标识符的 PR TEMPLATEID ([PidTagTemplateid](pidtagtemplateid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="40f0a-158">**PR\_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) to the template identifier from the  _lpTemplateID_ and  _cbTemplateID_ parameters.</span></span> 
        
      - <span data-ttu-id="40f0a-159">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 到 DT_MAILUSER 或 DT_DISTLIST (如果适用)。</span><span class="sxs-lookup"><span data-stu-id="40f0a-159">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) to DT_MAILUSER or DT_DISTLIST, as appropriate.</span></span>
    
5. <span data-ttu-id="40f0a-160">将_lppMAPIPropNew_参数的内容设置为指向提供程序的新对象或使用_lpMAPIPropData_参数传入的属性对象, 具体取决于您的提供程序是否必须确定包装对象。</span><span class="sxs-lookup"><span data-stu-id="40f0a-160">Set the contents of the  _lppMAPIPropNew_ parameter to point to either your provider's new object or the property object passed in with the  _lpMAPIPropData_ parameter, depending on whether your provider determines a wrapped object is necessary.</span></span> 
    
6. <span data-ttu-id="40f0a-161">如果发生严重错误 (如网络故障或内存不足的情况), 则返回相应的错误值。</span><span class="sxs-lookup"><span data-stu-id="40f0a-161">If a critical error occurs, such as a network failure or an out of memory condition, return the appropriate error value.</span></span> <span data-ttu-id="40f0a-162">此值应通过相应的[MAPIERROR](mapierror.md)结构传播到客户端, 由主机提供程序执行的任务。</span><span class="sxs-lookup"><span data-stu-id="40f0a-162">This value should get propagated to the client with the appropriate [MAPIERROR](mapierror.md) structure, a task performed by the host provider.</span></span> 
    

