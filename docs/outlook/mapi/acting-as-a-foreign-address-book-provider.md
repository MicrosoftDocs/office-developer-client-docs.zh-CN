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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331205"
---
# <a name="acting-as-a-foreign-address-book-provider"></a>充当外部通讯簿提供程序

**适用于**：Outlook 2013 | Outlook 2016 
  
外部提供程序是一个通讯簿提供程序, 该提供程序: 
  
- 为其收件人分配模板标识符。
    
- 支持[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)方法。 
    
- 提供用于维护在其他通讯簿提供程序 (称为主机提供程序) 的容器中存在的收件人的代码。 此代码涉及一个 property 对象 (通常为**IMAPIProp**接口实现), 该实现将属性对象包装在主机提供程序中。 
    
充当外部提供程序是一个可选角色;并非所有提供程序都需要支持模板标识符及其相关代码。 如果要保持对承载提供程序使用您的提供程序提供的模板创建的收件人的控制, 请将提供程序实现为外部提供程序。 
  
提供程序用于其条目标识符的格式也可用于其模板标识符。 模板标识符必须包含提供程序注册的**MAPIUID** , 以使 MAPI 能够成功地将收件人绑定到相应的提供程序。 
  
当主机提供程序调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)时, MAPI 会调用您的提供程序的**IABLogon:: OpenTemplateID**方法。 主机提供程序在其对**IMAPISupport:: OpenTemplateID**的调用中传递_lpTemplateID_参数中收件人的模板标识符。 MAPI 通过将模板标识符中的[MAPIUID](mapiuid.md)与提供程序在登录时注册的**MAPIUID**相匹配, 来确定模板标识符属于您的提供程序。 然后, MAPI 通过**IABLogon:: OpenTemplateID**方法将主机提供程序的调用转发给您的提供程序。 
  
主机提供程序还向_lpMAPIPropData_参数中的收件人传递指向其 property 对象实现的指针, _lpInterface_参数中的接口标识符与接口实现的类型相对应传入_lpMAPIPropData_和可选标志 FILL_ENTRY。 您的提供程序应在_lppMAPIPropNew_参数中返回一个指向_lpInterface_中指定的类型的属性对象实现的指针。 返回的指针可指向由提供程序实现的包装属性对象, 或由_lpMAPIPropData_中主机提供程序所提供的对象。 当出现以下情况时, 提供程序应返回回绕的 property 对象指针:
  
- 收件人的显示表格包含列表框控件。
    
- 收件人的电子邮件地址必须从多个显示表控件中的数据进行组合。
    
- 提供程序问题显示表通知。
    
FILL_ENTRY 标志向提供程序指明主机提供程序需要更新收件人的所有属性。 需要提供程序才能完成此请求。
  
当主机提供程序调用您的提供程序的**OpenTemplateID**方法时, 您的提供程序可能会: 
  
- 定期更新复制的条目的数据。
    
- 保留已复制的条目与原始条目的同步, 例如将通讯簿条目复制到个人通讯簿中的时间。
    
- 实现无法由主机提供程序实现的功能, 例如, 从服务器上的数据动态填充复制项的详细信息表中的列表框。
    
- 控制复制的项或实例化模板中的属性之间的交互。 例如, 从详细信息表中显示的其他属性计算**PR_EMAIL_ADDRESS** 。 
    
前两项是不要求提供程序提供包装属性对象 (基于主机提供程序的实现的**IMAPIProp**实现) 的任务示例。 提供程序可以简单地根据需要更新属性并返回, 并将_lppMAPIPropNew_参数设置为指向由主机提供程序在_lpMAPIPropData_参数中传递的指针。 
  
第二个任务要求提供程序向主机提供程序返回一个属性对象, 该对象使用其他功能 (如显示项的属性表的功能) 包装主机提供程序的对象。 此属性对象可以是邮件用户或通讯组列表, 具体取决于由_lpMAPIPropData_参数中的主机提供程序传入的对象的类型, 并由_lpInterface_参数中的接口标识符指示。 如果_lpMAPIPropData_参数指向邮件用户, 则提供程序的包装属性对象必须是**IMailUser**实现。 如果_lpMAPIPropData_指向通讯组列表, 则它必须是**IDistList**实现。 
  
提供程序的包装属性对象会截取**IMAPIProp**方法调用, 以执行主机提供程序的收件人的特定于上下文的操作 (它所包装的对象)。 MAPI 仅对回绕的 property 对象有一个要求: 对[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性的所有调用都应传递给主机提供程序。 提供程序的实现可以使用返回的表截获显示表通知, 或在必要时添加自己的实现。 
  
下面的列表包含通常在由外来提供程序实现的包装属性对象中实现的任务:
  
- [IMAPIProp:: GetProps](imapiprop-getprops.md)中主机收件人的预处理和后处理属性值。
    
- 处理详细信息显示表控件, 如**IMAPIProp:: OpenProperty**中的按钮和列表框。
    
- 在[IMAPIProp:: SetProps](imapiprop-setprops.md)中验证或操作主机收件人的属性值。
    
- 在[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)中保存主机收件人之前, 请计算必需的属性, 如**PR_EMAIL_ADDRESS**和验证是否已设置所有必需的属性。
    
### <a name="to-implement-iablogonopentemplateid"></a>实现 IABLogon:: OpenTemplateID
  
1. 检查使用_lpTemplateID_参数传入的模板标识符是否有效, 以及提供程序识别的格式。 如果不是, 则失败并返回 MAPI_E_INVALID_ENTRYID。 
    
2. 创建由模板标识符指示的类型的对象, 可以是邮件用户、通讯组列表或一次性收件人。 
    
3. 调用主机提供程序的 property 对象中的**IUnknown:: AddRef**方法, 该方法是_lpMAPIPropData_参数指向的对象。 
    
4. 如果将_ulTemplateFlags_参数设置为 FILL_ENTRY: 
    
   1. 如果新对象是邮件用户或通讯组列表:
      
      1. 检索新对象的所有属性, 可能是通过调用其**IMAPIProp:: GetProps**方法。 
          
      2. 调用主机提供程序的**IMAPIProp:: SetProps**方法将所有检索到的属性复制到主机提供程序的 property 对象。 
      
   2. 如果新对象是一次性收件人, 请调用主机提供程序的**IMAPIProp:: SetProps**方法来设置以下属性: 
      
      - **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 到由提供程序处理的地址类型。
        
      - **从\_** _lpTemplateID_和_cbTemplateID_参数到模板标识符的 PR TEMPLATEID ([PidTagTemplateid](pidtagtemplateid-canonical-property.md))。 
        
      - **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 到 DT_MAILUSER 或 DT_DISTLIST (如果适用)。
    
5. 将_lppMAPIPropNew_参数的内容设置为指向提供程序的新对象或使用_lpMAPIPropData_参数传入的属性对象, 具体取决于您的提供程序是否必须确定包装对象。 
    
6. 如果发生严重错误 (如网络故障或内存不足的情况), 则返回相应的错误值。 此值应通过相应的[MAPIERROR](mapierror.md)结构传播到客户端, 由主机提供程序执行的任务。 
    

