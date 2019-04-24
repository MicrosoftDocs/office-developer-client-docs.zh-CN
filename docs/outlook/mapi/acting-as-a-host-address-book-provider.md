---
title: 充当主机通讯簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f06a1034-ee49-4a09-831e-9752713228a8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 202d4b4391de7553e39e50dc527df5502ebcefb3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331267"
---
# <a name="acting-as-a-host-address-book-provider"></a>充当主机通讯簿提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
主机提供程序是一个通讯簿提供程序, 其中包含来自其容器中的其他提供程序的收件人, 并依赖其他提供程序的收件人实现以部分控制其维护。 主机提供程序使用这些外部收件人的模板标识符将这些收件人的数据绑定到外部提供程序中的代码。 当提供程序检索收件人的**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性并将其传递到[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)的调用中时, 将启动此绑定过程。 
  
当提供程序调用**IMAPISupport:: OpenTemplateID**时, MAPI 会将模板标识符中的**MAPIUID**与提供程序注册的**MAPIUID**进行匹配, 并调用提供程序的[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)方法。 外部提供程序可能返回指向提供程序的 property 对象的指针、其自己的 property 对象实现或包装提供程序对象的实现。 返回的指针放置在_lppMAPIPropNew_参数的内容中。 
  
提供程序可以选择是否调用**IMAPISupport:: OpenTemplateID**和 FILL_ENTRY 标志集。 在创建收件人时或在你的提供程序刷新收件人的属性后经过较长时间时, 请设置此标志。 FILL_ENTRY 标志的常见用途是使提供程序中的收件人与原始的同步。 实现此类型的同步计划可提高性能。 
  
 **保持外部收件人同步**
  
1. 确定定期更新的适当时间间隔。 
    
2. 对[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)的每个调用的时间戳。 
    
3. 评估是否有必要根据自上次呼叫后过期的时间量来执行完全更新。 如果需要进行完全更新, 请使用 FILL_ENTRY 标志调用**IMAPISupport:: OpenTemplateID** 。 如果不需要, 请不要在呼叫中设置标志。 
    
当客户端发出请求复制的收件人的属性之一时, 提供程序可以选择是处理请求本身还是使用外部提供程序提供的代码。 提供程序可以预期外部提供程序截获对**IMAPIProp**的大部分 (如果不是) 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)除外。 对**OpenProperty**请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性的调用将始终转发给提供程序。
  
 **访问模板标识符代码**
  
1. 打开收件人并调用其[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 如果**GetProps**因**PR_TEMPLATEID**不可用而失败, 则外部提供程序不支持此收件人的模板标识符和相关代码。 提供程序将需要对所有维护使用其收件人实现。 
    
2. 如果从**GetProps**返回模板标识符, 则将其传递, 并在调用**IMAPISupport:: OpenTemplateID**方法时, 将指针传递给收件人的**IMAPIProp**实现。 如果大多数或所有收件人的属性需要更新, 如创建时或尚未更新一段时间, 则设置 FILL_ENTRY 标志。 
    
3. 如果**OpenTemplateID**返回外部提供程序的**IMAPIProp**实现, 则向客户端返回指向此实现的指针。 
    
4. 如果**OpenTemplateID**不返回实现, 通常是因为外部提供程序不在配置文件中, 请将指向提供程序的**IMAPIProp**实现的指针返回到客户端。 客户端应能够使用任意一个接口处理对象的属性。 
    

