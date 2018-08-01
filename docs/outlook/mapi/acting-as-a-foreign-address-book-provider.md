---
title: 充当外的地址簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6d532ed4-7dc5-46a9-995a-72bc97d16f6e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 16c3518ab4efddbd68765d9de94db64b4fdc0b64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774490"
---
# <a name="acting-as-a-foreign-address-book-provider"></a><span data-ttu-id="897a0-103">充当外的地址簿提供程序</span><span class="sxs-lookup"><span data-stu-id="897a0-103">Acting as a foreign address book provider</span></span>

<span data-ttu-id="897a0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="897a0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="897a0-105">外的提供程序是通讯簿提供程序的：</span><span class="sxs-lookup"><span data-stu-id="897a0-105">A foreign provider is an address book provider that:</span></span> 
  
- <span data-ttu-id="897a0-106">其收件人分配模板标识符。</span><span class="sxs-lookup"><span data-stu-id="897a0-106">Assigns template identifiers for its recipients.</span></span>
    
- <span data-ttu-id="897a0-107">支持[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="897a0-107">Supports the [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> 
    
- <span data-ttu-id="897a0-108">提供用于维护称为主机提供其他通讯簿提供程序的容器中存在的收件人的代码。</span><span class="sxs-lookup"><span data-stu-id="897a0-108">Supplies code for maintaining recipients that exist in the containers of other address book providers known as host providers.</span></span> <span data-ttu-id="897a0-109">此代码涉及 property 对象，通常**IMAPIProp**接口实现，其中宿主提供程序中的属性对象的换行。</span><span class="sxs-lookup"><span data-stu-id="897a0-109">This code involves a property object, typically an **IMAPIProp** interface implementation, which wraps a property object from the host provider.</span></span> 
    
<span data-ttu-id="897a0-110">充当外的提供程序是一个可选角色;并非所有提供程序需要支持模板标识符和其相关的代码。</span><span class="sxs-lookup"><span data-stu-id="897a0-110">Acting as a foreign provider is an optional role; not all providers need to support template identifiers and their related code.</span></span> <span data-ttu-id="897a0-111">如果您想要维护控制宿主提供程序创建使用模板提供商所提供的收件人，则实现外的提供程序为您提供程序。</span><span class="sxs-lookup"><span data-stu-id="897a0-111">Implement your provider as a foreign provider if you want to maintain control over recipients that host providers create using templates supplied by your provider.</span></span> 
  
<span data-ttu-id="897a0-112">您的提供商使用其条目标识符格式还可用于其模板标识符。</span><span class="sxs-lookup"><span data-stu-id="897a0-112">The format that your provider uses for its entry identifiers can also be used for its template identifiers.</span></span> <span data-ttu-id="897a0-113">模板标识符必须包含您的提供商注册的**MAPIUID**启用 MAPI 成功将收件人绑定到的适当的提供程序。</span><span class="sxs-lookup"><span data-stu-id="897a0-113">Template identifiers must include your provider's registered **MAPIUID** to enable MAPI to successfully bind recipients to the appropriate providers.</span></span> 
  
<span data-ttu-id="897a0-114">MAPI 调用您的提供商**IABLogon::OpenTemplateID**方法时宿主提供程序调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)。</span><span class="sxs-lookup"><span data-stu-id="897a0-114">MAPI calls your provider's **IABLogon::OpenTemplateID** method when a host provider calls [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md).</span></span> <span data-ttu-id="897a0-115">宿主提供程序将其调用**IMAPISupport::OpenTemplateID** _lpTemplateID_参数中传递模板标识符的收件人。</span><span class="sxs-lookup"><span data-stu-id="897a0-115">The host provider passes the template identifier of the recipient in the  _lpTemplateID_ parameter in its call to **IMAPISupport::OpenTemplateID**.</span></span> <span data-ttu-id="897a0-116">MAPI 的模板标识符通过确定属于您的提供商匹配[MAPIUID](mapiuid.md)模板标识符中与在登录时提供程序注册**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="897a0-116">MAPI determines that the template identifier belongs to your provider by matching the [MAPIUID](mapiuid.md) in the template identifier with the **MAPIUID** that your provider registered at logon time.</span></span> <span data-ttu-id="897a0-117">MAPI 然后通过**IABLogon::OpenTemplateID**方法转发到您的提供程序的宿主提供商的呼叫。</span><span class="sxs-lookup"><span data-stu-id="897a0-117">MAPI then forwards the host provider's call to your provider through the **IABLogon::OpenTemplateID** method.</span></span> 
  
<span data-ttu-id="897a0-118">宿主提供程序还将指针传递给其属性对象实现_lpMAPIPropData_参数中的收件人、 _lpInterface_参数对应的接口实现类型中的接口标识符传递_lpMAPIPropData_和一个可选的标志，FILL_ENTRY 中。</span><span class="sxs-lookup"><span data-stu-id="897a0-118">The host provider also passes a pointer to its property object implementation for the recipient in the  _lpMAPIPropData_ parameter, an interface identifier in the  _lpInterface_ parameter that corresponds to the type of interface implementation passed in  _lpMAPIPropData_, and an optional flag, FILL_ENTRY.</span></span> <span data-ttu-id="897a0-119">您的提供商有望_lppMAPIPropNew_参数中返回_lpInterface_中指定的类型的属性对象实现的指针。</span><span class="sxs-lookup"><span data-stu-id="897a0-119">Your provider is expected to return in the  _lppMAPIPropNew_ parameter a pointer to a property object implementation of the type specified in  _lpInterface_.</span></span> <span data-ttu-id="897a0-120">到您的提供程序实现的换行的属性对象或_lpMAPIPropData_中主机提供商所提供的对象，也可以是返回的指针。</span><span class="sxs-lookup"><span data-stu-id="897a0-120">The returned pointer can either be to the wrapped property object implemented by your provider or to the object supplied by the host provider in  _lpMAPIPropData_.</span></span> <span data-ttu-id="897a0-121">提供程序应返回换行的属性对象指针时：</span><span class="sxs-lookup"><span data-stu-id="897a0-121">Your provider should return a wrapped property object pointer when:</span></span>
  
- <span data-ttu-id="897a0-122">收件人的显示表包含列表框控件。</span><span class="sxs-lookup"><span data-stu-id="897a0-122">The recipient's display table contains list box controls.</span></span>
    
- <span data-ttu-id="897a0-123">从多个显示表控件中的数据，必须组合收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="897a0-123">The email address for the recipient must be assembled from data in multiple display table controls.</span></span>
    
- <span data-ttu-id="897a0-124">提供程序问题显示表通知。</span><span class="sxs-lookup"><span data-stu-id="897a0-124">Your provider issues display table notifications.</span></span>
    
<span data-ttu-id="897a0-125">FILL_ENTRY 标志指示您的提供商宿主提供程序需要更新中的收件人的所有属性。</span><span class="sxs-lookup"><span data-stu-id="897a0-125">The FILL_ENTRY flag indicates to your provider that the host provider requires all the properties of the recipient to be updated.</span></span> <span data-ttu-id="897a0-126">您的提供商需要满足此请求。</span><span class="sxs-lookup"><span data-stu-id="897a0-126">Your provider is required to fulfill this request.</span></span>
  
<span data-ttu-id="897a0-127">宿主提供程序调用您的提供商**OpenTemplateID**方法时，您的提供商可能：</span><span class="sxs-lookup"><span data-stu-id="897a0-127">When a host provider calls your provider's **OpenTemplateID** method, your provider might:</span></span> 
  
- <span data-ttu-id="897a0-128">定期更新复制项的数据。</span><span class="sxs-lookup"><span data-stu-id="897a0-128">Periodically update the data for a copied entry.</span></span>
    
- <span data-ttu-id="897a0-129">将与其原始，如时的通讯簿条目复制到个人通讯簿同步复制的条目。</span><span class="sxs-lookup"><span data-stu-id="897a0-129">Keep a copied entry synchronized with its original, such as when an address book entry is copied to the personal address book.</span></span>
    
- <span data-ttu-id="897a0-130">实现功能不能实现的宿主提供程序，如动态填充列表框中的服务器上的数据复制的条目的详细信息表。</span><span class="sxs-lookup"><span data-stu-id="897a0-130">Implement functionality that cannot be implemented by the host provider, such as dynamically populating list boxes in the copied entry's details table from data on a server.</span></span>
    
- <span data-ttu-id="897a0-131">控件中的复制的条目或实例化的模板的属性之间的交互。</span><span class="sxs-lookup"><span data-stu-id="897a0-131">Control the interaction among properties in a copied entry or instantiated template.</span></span> <span data-ttu-id="897a0-132">例如，计算**PR_EMAIL_ADDRESS** ，从明细表中显示的其他属性。</span><span class="sxs-lookup"><span data-stu-id="897a0-132">For example, computing **PR_EMAIL_ADDRESS** from other properties displayed in the details table.</span></span> 
    
<span data-ttu-id="897a0-133">前两项都不需要您的提供商提供的换行的属性对象的任务的示例 — **IMAPIProp**基于主机提供程序实现的实现。</span><span class="sxs-lookup"><span data-stu-id="897a0-133">The first two items are examples of tasks that do not require your provider to supply a wrapped property object — an implementation of **IMAPIProp** that is based on the host provider's implementation.</span></span> <span data-ttu-id="897a0-134">您的提供商可以只需更新为必需和返回，以指向传入_lpMAPIPropData_参数中主机提供商的指针_lppMAPIPropNew_参数设置属性。</span><span class="sxs-lookup"><span data-stu-id="897a0-134">Your provider can simply update the properties as necessary and return, setting the  _lppMAPIPropNew_ parameter to point to the pointer passed in by the host provider in the  _lpMAPIPropData_ parameter.</span></span> 
  
<span data-ttu-id="897a0-135">两个任务需要的提供程序返回到宿主提供程序与其他功能，例如，能够显示属性表条目的换行宿主提供程序的对象的属性对象。</span><span class="sxs-lookup"><span data-stu-id="897a0-135">The second two tasks require that your provider return to the host provider a property object that wraps the host provider's object with additional functionality, such as the ability to display a property sheet for the entry.</span></span> <span data-ttu-id="897a0-136">此属性对象将具有的消息的用户或通讯组列表，具体取决于对象中传递的_lpMAPIPropData_参数中的宿主提供程序和由_lpInterface_参数中的接口标识符的类型。</span><span class="sxs-lookup"><span data-stu-id="897a0-136">This property object will either be a messaging user or distribution list, depending on the type of object passed in by the host provider in the  _lpMAPIPropData_ parameter and indicated by the interface identifier in the  _lpInterface_ parameter.</span></span> <span data-ttu-id="897a0-137">如果_lpMAPIPropData_参数指向的消息的用户，则必须**IMailUser**实现提供程序的换行的属性对象。</span><span class="sxs-lookup"><span data-stu-id="897a0-137">If the  _lpMAPIPropData_ parameter points to a messaging user, your provider's wrapped property object must be an **IMailUser** implementation.</span></span> <span data-ttu-id="897a0-138">如果_lpMAPIPropData_指向通讯组列表，它必须是**IDistList**实现。</span><span class="sxs-lookup"><span data-stu-id="897a0-138">If  _lpMAPIPropData_ points to a distribution list, it must be an **IDistList** implementation.</span></span> 
  
<span data-ttu-id="897a0-139">提供程序的换行的 property 对象截获**IMAPIProp**方法调用来执行特定于上下文的操作的宿主提供程序的收件人 — 它环绕的对象。</span><span class="sxs-lookup"><span data-stu-id="897a0-139">Your provider's wrapped property object intercepts **IMAPIProp** method calls to perform context-specific manipulation of the host provider's recipient—the object it is wrapping.</span></span> <span data-ttu-id="897a0-140">MAPI 只有一个要求换行的 property 对象： [IMAPIProp::OpenProperty](imapiprop-openproperty.md)请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性的所有呼叫应都传递给宿主提供程序。</span><span class="sxs-lookup"><span data-stu-id="897a0-140">MAPI only has one requirement for wrapped property objects: all calls to [IMAPIProp::OpenProperty](imapiprop-openproperty.md) requesting the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property should be passed to the host provider.</span></span> <span data-ttu-id="897a0-141">Intercept 显示表通知或添加其自己的如有必要，提供程序的实现可以使用返回的 table。</span><span class="sxs-lookup"><span data-stu-id="897a0-141">Your provider's implementation can use the returned table to intercept display table notifications or to add its own if necessary.</span></span> 
  
<span data-ttu-id="897a0-142">下面的列表包括通常会实现外的提供程序实现包装的属性对象中的任务：</span><span class="sxs-lookup"><span data-stu-id="897a0-142">The following list includes tasks that are typically implemented in the wrapped property object implemented by foreign providers:</span></span>
  
- <span data-ttu-id="897a0-143">预处理和后处理主机收件人[IMAPIProp::GetProps](imapiprop-getprops.md)中的属性值。</span><span class="sxs-lookup"><span data-stu-id="897a0-143">Preprocessing and postprocessing property values for the host recipient in [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span>
    
- <span data-ttu-id="897a0-144">处理详细信息显示在**IMAPIProp::OpenProperty**表控件，如按钮和列表框。</span><span class="sxs-lookup"><span data-stu-id="897a0-144">Handling details display table controls, such as buttons and list boxes, in **IMAPIProp::OpenProperty**.</span></span>
    
- <span data-ttu-id="897a0-145">验证或主机收件人[IMAPIProp::SetProps](imapiprop-setprops.md)中处理属性值。</span><span class="sxs-lookup"><span data-stu-id="897a0-145">Validating or manipulating property values for the host recipient in [IMAPIProp::SetProps](imapiprop-setprops.md).</span></span>
    
- <span data-ttu-id="897a0-146">计算所需的属性，如**PR_EMAIL_ADDRESS**和验证的所有必要的属性已设置保存在[IMAPIProp::SaveChanges](imapiprop-savechanges.md)主机收件人之前。</span><span class="sxs-lookup"><span data-stu-id="897a0-146">Computing required properties such as **PR_EMAIL_ADDRESS** and verifying that all of the necessary properties have been set before saving the host recipient in [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span>
    
### <a name="to-implement-iablogonopentemplateid"></a><span data-ttu-id="897a0-147">若要实现 IABLogon::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="897a0-147">To implement IABLogon::OpenTemplateID</span></span>
  
1. <span data-ttu-id="897a0-148">检查是否使用传递的模板标识符_lpTemplateID_参数有效并提供程序可识别的格式。</span><span class="sxs-lookup"><span data-stu-id="897a0-148">Check if the template identifier passed in with the  _lpTemplateID_ parameter is valid and is in a format that your provider recognizes.</span></span> <span data-ttu-id="897a0-149">如果不存在，则失败并返回 MAPI_E_INVALID_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="897a0-149">If it is not, fail and return MAPI_E_INVALID_ENTRYID.</span></span> 
    
2. <span data-ttu-id="897a0-150">创建一个模板标识符，指示的类型的对象消息的用户、 通讯组列表或一次性收件人。</span><span class="sxs-lookup"><span data-stu-id="897a0-150">Create an object of the type indicated by the template identifier, either a messaging user, distribution list, or one-off recipient.</span></span> 
    
3. <span data-ttu-id="897a0-151">在宿主提供程序的 property 对象，它是由_lpMAPIPropData_参数指向的对象调用**IUnknown::AddRef**方法。</span><span class="sxs-lookup"><span data-stu-id="897a0-151">Call the **IUnknown::AddRef** method in the host provider's property object, which is the object pointed to by the  _lpMAPIPropData_ parameter.</span></span> 
    
4. <span data-ttu-id="897a0-152">如果_ulTemplateFlags_参数设置为 FILL_ENTRY:</span><span class="sxs-lookup"><span data-stu-id="897a0-152">If the  _ulTemplateFlags_ parameter is set to FILL_ENTRY:</span></span> 
    
   1. <span data-ttu-id="897a0-153">如果新对象的消息的用户或通讯组列表：</span><span class="sxs-lookup"><span data-stu-id="897a0-153">If the new object is a messaging user or distribution list:</span></span>
      
      1. <span data-ttu-id="897a0-154">检索所有新对象的属性的可能是通过调用其**IMAPIProp::GetProps**方法。</span><span class="sxs-lookup"><span data-stu-id="897a0-154">Retrieve all of the properties of the new object, possibly by calling its **IMAPIProp::GetProps** method.</span></span> 
          
      2. <span data-ttu-id="897a0-155">调用宿主提供程序的**IMAPIProp::SetProps**方法，将所有检索属性复制到宿主提供程序的属性对象。</span><span class="sxs-lookup"><span data-stu-id="897a0-155">Call the host provider's **IMAPIProp::SetProps** method to copy all of the retrieved properties to the host provider's property object.</span></span> 
      
   2. <span data-ttu-id="897a0-156">如果新对象是一次性的收件人，呼叫宿主提供程序的**IMAPIProp::SetProps**方法，以便设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="897a0-156">If the new object is a one-off recipient, call the host provider's **IMAPIProp::SetProps** method to set the following properties:</span></span> 
      
      - <span data-ttu-id="897a0-157">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 到的地址类型处理由您的提供商。</span><span class="sxs-lookup"><span data-stu-id="897a0-157">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) to the address type handled by your provider.</span></span>
        
      - <span data-ttu-id="897a0-158">**PR\_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 到的_lpTemplateID_和_cbTemplateID_参数中的模板标识符。</span><span class="sxs-lookup"><span data-stu-id="897a0-158">**PR\_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) to the template identifier from the  _lpTemplateID_ and  _cbTemplateID_ parameters.</span></span> 
        
      - <span data-ttu-id="897a0-159">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 到 DT_MAILUSER 或 DT_DISTLIST，根据需要。</span><span class="sxs-lookup"><span data-stu-id="897a0-159">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) to DT_MAILUSER or DT_DISTLIST, as appropriate.</span></span>
    
5. <span data-ttu-id="897a0-160">设置_lppMAPIPropNew_参数，以指向传入_lpMAPIPropData_参数，具体取决于您的提供商是否确定被环绕的对象是必需的属性对象或提供程序的新对象的内容。</span><span class="sxs-lookup"><span data-stu-id="897a0-160">Set the contents of the  _lppMAPIPropNew_ parameter to point to either your provider's new object or the property object passed in with the  _lpMAPIPropData_ parameter, depending on whether your provider determines a wrapped object is necessary.</span></span> 
    
6. <span data-ttu-id="897a0-161">如果出现严重错误，如网络故障或内存不足的情况，则返回相应的错误值。</span><span class="sxs-lookup"><span data-stu-id="897a0-161">If a critical error occurs, such as a network failure or an out of memory condition, return the appropriate error value.</span></span> <span data-ttu-id="897a0-162">此值应获取传播到客户端与相应的[MAPIERROR](mapierror.md)结构，由宿主提供程序执行的任务。</span><span class="sxs-lookup"><span data-stu-id="897a0-162">This value should get propagated to the client with the appropriate [MAPIERROR](mapierror.md) structure, a task performed by the host provider.</span></span> 
    

