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
# <a name="acting-as-a-foreign-address-book-provider"></a>充当外部通讯簿提供程序

**适用于**：Outlook 2013 | Outlook 2016 
  
外提供商是通讯簿提供程序，用于： 
  
- 为其收件人分配模板标识符。
    
- 支持 [IABLogon：：OpenTemplateID](iablogon-opentemplateid.md) 方法。 
    
- 提供用于维护存在于其他通讯簿提供程序（称为宿主提供程序）的容器中的收件人的代码。 此代码涉及一个属性对象，通常为 **IMAPIProp** 接口实现，它包装主机提供程序中的属性对象。 
    
充当外提供商是可选角色;并非所有提供程序都需要支持模板标识符及其相关代码。 如果要保持对宿主提供商使用提供程序提供的模板创建的收件人的控制，请实现作为外提供商的提供程序。 
  
提供程序用于其条目标识符的格式还可用于其模板标识符。 模板标识符必须包含提供程序的注册 **MAPIUID，MAPI** 才能将收件人成功绑定到相应的提供程序。 
  
当主机提供程序调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md)时，MAPI 将调用提供程序的 **IABLogon：：OpenTemplateID** 方法。 主机提供程序在其对 **IMAPISupport：：OpenTemplateID** 的调用中传递 _lpTemplateID_ 参数中收件人的模板标识符。 MAPI 将模板标识符中的 [MAPIUID](mapiuid.md) 与提供程序在登录时注册的 **MAPIUID** 相匹配，确定模板标识符属于你的提供程序。 然后，MAPI 通过 **IABLogon：：OpenTemplateID** 方法将宿主提供商的调用转发到您的提供商。 
  
主机提供程序还将指针传递给  _lpMAPIPropData_ 参数中收件人的属性对象实现  _、lpInterface_ 参数中的接口标识符（对应于在  _lpMAPIPropData_ 中传递的接口实现的类型）和可选标志 FILL_ENTRY。 您的提供程序预期在  _lppMAPIPropNew_ 参数中返回一个指针，指向  _在 lpInterface_ 中指定的类型的属性对象实现。 返回的指针可以是提供程序实现的封装属性对象，也可以是  _lpMAPIPropData_ 中的宿主提供程序提供的对象。 当发生此等操作时，提供程序应返回包装的属性对象指针：
  
- 收件人的显示表包含列表框控件。
    
- 收件人的电子邮件地址必须从多个显示表控件的数据进行组合。
    
- 提供程序问题显示表通知。
    
the FILL_ENTRY flag indicates to your provider that the host provider requires all the properties of the recipient to be updated. 提供商需要满足此请求。
  
当宿主提供商调用提供程序的 **OpenTemplateID** 方法时，您的提供程序可能： 
  
- 定期更新复制的条目的数据。
    
- 使复制的条目与其原始条目保持同步，例如将通讯簿条目复制到个人通讯簿时。
    
- 实现宿主提供程序无法实现的功能，例如从服务器上数据动态填充复制条目的详细信息表中的列表框。
    
- 控制复制的条目或实例化模板中的属性之间的交互。 例如，计算 **PR_EMAIL_ADDRESS** 表中显示的其他属性的计算结果。 
    
前两项是不需要提供程序提供包装属性对象（基于宿主提供程序的实现 **实现 IMAPIProp）** 的任务示例。 提供程序只需在必要时更新属性并返回，将  _lppMAPIPropNew_ 参数设置为指向宿主提供程序在  _lpMAPIPropData_ 参数中传递的指针。 
  
后两个任务要求提供程序向宿主提供程序返回一个属性对象，该对象使用附加功能包装主机提供程序的对象，例如显示条目属性表项的功能。 此属性对象将为消息用户或通讯组列表，具体取决于宿主提供程序在  _lpMAPIPropData_ 参数中传入的对象类型，由  _lpInterface_ 参数中的接口标识符指示。 如果  _lpMAPIPropData_ 参数指向消息用户，则提供程序的封装属性对象必须是 **IMailUser** 实现。 如果  _lpMAPIPropData_ 指向通讯组列表，则它必须是 **IDistList** 实现。 
  
提供程序的包装属性对象截获 **IMAPIProp** 方法调用，以对宿主提供程序的收件人（它正在包装的对象）执行特定于上下文的操作。 MAPI 仅对封装属性对象有一个要求：对请求 PR_DETAILS_TABLE ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md) **)** 属性的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)的所有调用都应传递给主机提供程序。 提供程序的实现可以使用返回的表截获显示表通知，或者根据需要添加自己的通知。 
  
以下列表包括通常在由外提供程序实现的封装属性对象中实现的任务：
  
- [IMAPIProp：：GetProps](imapiprop-getprops.md)中主机收件人的预处理和后处理属性值。
    
- 处理详细信息显示表控件，如 **IMAPIProp：：OpenProperty 中的按钮和列表框**。
    
- 验证或操作 [IMAPIProp：：SetProps](imapiprop-setprops.md)中主机收件人的属性值。
    
- 在将主机 **收件人保存在** [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)中之前，计算所需的属性（如 PR_EMAIL_ADDRESS 并验证是否已设置所有必要的属性）。
    
### <a name="to-implement-iablogonopentemplateid"></a>实现 IABLogon：：OpenTemplateID
  
1. 检查与  _lpTemplateID_ 参数一起传入的模板标识符是否有效，并且其格式是否为提供程序可识别的格式。 如果不是，则失败并返回MAPI_E_INVALID_ENTRYID。 
    
2. 创建由模板标识符指示的类型的对象，可以是邮件用户、通讯组列表或一次发送收件人。 
    
3. 在宿主提供程序的属性对象 _（lpMAPIPropData_ 参数指向的对象）中调用 **IUnknown：：AddRef** 方法。 
    
4. 如果  _ulTemplateFlags_ 参数设置为 FILL_ENTRY： 
    
   1. 如果新对象是邮件用户或通讯组列表：
      
      1. 通过调用其 **IMAPIProp：：GetProps** 方法检索新对象的所有属性。 
          
      2. 调用宿主提供程序的 **IMAPIProp：：SetProps** 方法，将检索到的所有属性复制到宿主提供程序的属性对象。 
      
   2. 如果新对象是一对一收件人，请调用宿主提供程序的 **IMAPIProp：：SetProps** 方法来设置以下属性： 
      
      - **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 提供程序处理的地址类型。
        
      - **PR \_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md))  _lpTemplateID_ 和  _cbTemplateID_ 参数中的模板标识符。 
        
      - **PR_DISPLAY_TYPE (** PidTagDisplayType) DT_MAILUSER或DT_DISTLIST [PidTagDisplayType。](pidtagdisplaytype-canonical-property.md)
    
5. 设置  _lppMAPIPropNew_ 参数的内容，以指向提供程序的新对象或用  _lpMAPIPropData_ 参数传入的属性对象，具体取决于提供程序是否确定封装对象是必需的。 
    
6. 如果发生严重错误（如网络故障或内存不足情况），则返回相应的错误值。 此值应该通过相应的 [MAPIERROR](mapierror.md) 结构（由宿主提供程序执行的任务）传播到客户端。 
    

