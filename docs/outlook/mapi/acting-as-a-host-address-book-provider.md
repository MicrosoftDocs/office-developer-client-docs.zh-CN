---
title: 充当主机通讯簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f06a1034-ee49-4a09-831e-9752713228a8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: de0acb88eee6addc0347f5281e5fbe5070bad0a4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595404"
---
# <a name="acting-as-a-host-address-book-provider"></a>充当主机通讯簿提供程序

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
宿主提供程序是通讯簿提供程序，包括其容器中的其他提供程序的收件人，并依赖于由其他提供程序部分控制其维护的收件人的实现。 宿主提供程序使用这些外的收件人的模板的标识符将这些收件人数据绑定到外的提供程序中的代码。 您的提供商检索收件人的**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性，并将其传递[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)将调用时启动此绑定进程。 
  
当您提供程序调用**IMAPISupport::OpenTemplateID**，MAPI 匹配**MAPIUID**内时与**MAPIUID**模板标识符由提供程序注册，并调用提供程序的[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)方法。 外的提供程序可能会返回一个指针到提供程序的属性对象，它自己属性的对象实现，或实现的换行提供程序的对象。 返回的指针放在_lppMAPIPropNew_参数的内容。 
  
您的提供商可以选择设置了 FILL_ENTRY 标志呼叫**IMAPISupport::OpenTemplateID** 。 正在创建收件人或您的提供商已刷新收件人的属性以来已通过很长时间时，请设置此标志。 常用 FILL_ENTRY 标志是保留与原始同步您提供程序中的收件人。 实现此类型的同步计划增强了性能。 
  
 **若要保留外的收件人同步**
  
1. 确定适当的时间间隔定期更新。 
    
2. 时间戳每个呼叫[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)。 
    
3. 评估需要执行完全更新基于上次调用已过期的时间量。 如果需要完全更新，则呼叫**IMAPISupport::OpenTemplateID** FILL_ENTRY 标志。 如果不是必需的则不要在调用设置标志。 
    
当客户端请求复制的收件人的属性之一，您的提供商可以选择是否处理请求本身或使用外的提供商所提供的代码。 您的提供商可以预期外的提供程序以截获最，如果不是所有，呼叫到**IMAPIProp** [IMAPIProp::OpenProperty](imapiprop-openproperty.md)除外。 调用**OpenProperty**请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性始终被转接到您的提供商。
  
 **若要访问模板标识符代码**
  
1. 打开收件人，并调用其[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 如果**GetProps**失败，因为**PR_TEMPLATEID**不可用外的提供程序不支持的模板标识符和相关的代码的此收件人。 您的提供商需要收件人其实现用于所有维护。 
    
2. 如果从**GetProps**返回模板标识符，将其和指针传递给**IMAPISupport::OpenTemplateID**方法调用中的收件人的**IMAPIProp**实现。 如果需要最或所有收件人的属性设置 FILL_ENTRY 标志更新，例如，在创建时间或如果其尚未更新一段。 
    
3. 如果**OpenTemplateID**返回外的提供程序**IMAPIProp**实现，返回到客户端指向此实现的指针。 
    
4. 如果**OpenTemplateID**不会返回实现，通常因为外的提供程序不在配置文件中，返回到客户端提供商的**IMAPIProp**实现的指针。 客户端应该能够处理使用任一接口的对象的属性。 
    

