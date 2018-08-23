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
ms.openlocfilehash: cafc6e3b6d863a7c2acec5811bf161ad0cd64458
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570028"
---
# <a name="acting-as-a-foreign-address-book-provider"></a>充当外的地址簿提供程序

**适用于**： Outlook 2013 |Outlook 2016 
  
外的提供程序是通讯簿提供程序的： 
  
- 其收件人分配模板标识符。
    
- 支持[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)方法。 
    
- 提供用于维护称为主机提供其他通讯簿提供程序的容器中存在的收件人的代码。 此代码涉及 property 对象，通常**IMAPIProp**接口实现，其中宿主提供程序中的属性对象的换行。 
    
充当外的提供程序是一个可选角色;并非所有提供程序需要支持模板标识符和其相关的代码。 如果您想要维护控制宿主提供程序创建使用模板提供商所提供的收件人，则实现外的提供程序为您提供程序。 
  
您的提供商使用其条目标识符格式还可用于其模板标识符。 模板标识符必须包含您的提供商注册的**MAPIUID**启用 MAPI 成功将收件人绑定到的适当的提供程序。 
  
MAPI 调用您的提供商**IABLogon::OpenTemplateID**方法时宿主提供程序调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)。 宿主提供程序将其调用**IMAPISupport::OpenTemplateID** _lpTemplateID_参数中传递模板标识符的收件人。 MAPI 的模板标识符通过确定属于您的提供商匹配[MAPIUID](mapiuid.md)模板标识符中与在登录时提供程序注册**MAPIUID** 。 MAPI 然后通过**IABLogon::OpenTemplateID**方法转发到您的提供程序的宿主提供商的呼叫。 
  
宿主提供程序还将指针传递给其属性对象实现_lpMAPIPropData_参数中的收件人、 _lpInterface_参数对应的接口实现类型中的接口标识符传递_lpMAPIPropData_和一个可选的标志，FILL_ENTRY 中。 您的提供商有望_lppMAPIPropNew_参数中返回_lpInterface_中指定的类型的属性对象实现的指针。 到您的提供程序实现的换行的属性对象或_lpMAPIPropData_中主机提供商所提供的对象，也可以是返回的指针。 提供程序应返回换行的属性对象指针时：
  
- 收件人的显示表包含列表框控件。
    
- 从多个显示表控件中的数据，必须组合收件人的电子邮件地址。
    
- 提供程序问题显示表通知。
    
FILL_ENTRY 标志指示您的提供商宿主提供程序需要更新中的收件人的所有属性。 您的提供商需要满足此请求。
  
宿主提供程序调用您的提供商**OpenTemplateID**方法时，您的提供商可能： 
  
- 定期更新复制项的数据。
    
- 将与其原始，如时的通讯簿条目复制到个人通讯簿同步复制的条目。
    
- 实现功能不能实现的宿主提供程序，如动态填充列表框中的服务器上的数据复制的条目的详细信息表。
    
- 控件中的复制的条目或实例化的模板的属性之间的交互。 例如，计算**PR_EMAIL_ADDRESS** ，从明细表中显示的其他属性。 
    
前两项都不需要您的提供商提供的换行的属性对象的任务的示例 — **IMAPIProp**基于主机提供程序实现的实现。 您的提供商可以只需更新为必需和返回，以指向传入_lpMAPIPropData_参数中主机提供商的指针_lppMAPIPropNew_参数设置属性。 
  
两个任务需要的提供程序返回到宿主提供程序与其他功能，例如，能够显示属性表条目的换行宿主提供程序的对象的属性对象。 此属性对象将具有的消息的用户或通讯组列表，具体取决于对象中传递的_lpMAPIPropData_参数中的宿主提供程序和由_lpInterface_参数中的接口标识符的类型。 如果_lpMAPIPropData_参数指向的消息的用户，则必须**IMailUser**实现提供程序的换行的属性对象。 如果_lpMAPIPropData_指向通讯组列表，它必须是**IDistList**实现。 
  
提供程序的换行的 property 对象截获**IMAPIProp**方法调用来执行特定于上下文的操作的宿主提供程序的收件人 — 它环绕的对象。 MAPI 只有一个要求换行的 property 对象： [IMAPIProp::OpenProperty](imapiprop-openproperty.md)请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性的所有呼叫应都传递给宿主提供程序。 Intercept 显示表通知或添加其自己的如有必要，提供程序的实现可以使用返回的 table。 
  
下面的列表包括通常会实现外的提供程序实现包装的属性对象中的任务：
  
- 预处理和后处理主机收件人[IMAPIProp::GetProps](imapiprop-getprops.md)中的属性值。
    
- 处理详细信息显示在**IMAPIProp::OpenProperty**表控件，如按钮和列表框。
    
- 验证或主机收件人[IMAPIProp::SetProps](imapiprop-setprops.md)中处理属性值。
    
- 计算所需的属性，如**PR_EMAIL_ADDRESS**和验证的所有必要的属性已设置保存在[IMAPIProp::SaveChanges](imapiprop-savechanges.md)主机收件人之前。
    
### <a name="to-implement-iablogonopentemplateid"></a>若要实现 IABLogon::OpenTemplateID
  
1. 检查是否使用传递的模板标识符_lpTemplateID_参数有效并提供程序可识别的格式。 如果不存在，则失败并返回 MAPI_E_INVALID_ENTRYID。 
    
2. 创建一个模板标识符，指示的类型的对象消息的用户、 通讯组列表或一次性收件人。 
    
3. 在宿主提供程序的 property 对象，它是由_lpMAPIPropData_参数指向的对象调用**IUnknown::AddRef**方法。 
    
4. 如果_ulTemplateFlags_参数设置为 FILL_ENTRY: 
    
   1. 如果新对象的消息的用户或通讯组列表：
      
      1. 检索所有新对象的属性的可能是通过调用其**IMAPIProp::GetProps**方法。 
          
      2. 调用宿主提供程序的**IMAPIProp::SetProps**方法，将所有检索属性复制到宿主提供程序的属性对象。 
      
   2. 如果新对象是一次性的收件人，呼叫宿主提供程序的**IMAPIProp::SetProps**方法，以便设置以下属性： 
      
      - **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 到的地址类型处理由您的提供商。
        
      - **PR\_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 到的_lpTemplateID_和_cbTemplateID_参数中的模板标识符。 
        
      - **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 到 DT_MAILUSER 或 DT_DISTLIST，根据需要。
    
5. 设置_lppMAPIPropNew_参数，以指向传入_lpMAPIPropData_参数，具体取决于您的提供商是否确定被环绕的对象是必需的属性对象或提供程序的新对象的内容。 
    
6. 如果出现严重错误，如网络故障或内存不足的情况，则返回相应的错误值。 此值应获取传播到客户端与相应的[MAPIERROR](mapierror.md)结构，由宿主提供程序执行的任务。 
    

