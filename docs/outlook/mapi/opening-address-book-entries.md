---
title: 打开通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 017a62c0-49c6-47fb-acce-db58e6bb9cc5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6ebd6009700742e9b1159bc95ff0496c423e512c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422157"
---
# <a name="opening-address-book-entries"></a>打开通讯簿条目

**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端或提供程序请求打开某个对象时, MAPI 会调用您的提供程序的[IABLogon:: OpenEntry](iablogon-openentry.md)方法。 MAPI 通过检查条目标识符的[MAPIUID](mapiuid.md)部分并将其与您的提供程序在调用**** **中注册的 MAPIUID 相匹配, 来确定表示目标对象是否属于您的提供程序的条目标识符。IMAPISupport:: SetProviderUID**。 然后, MAPI 将调用您的**OpenEntry**方法。 提供程序必须通过检索对应的对象 (容器、通讯组列表或邮件用户) 来做出响应。 
  
空条目标识符指示打开通讯簿提供程序的根容器的请求。 客户端打开根容器以访问其层次结构表及其收件人。 仅提供用于创建一次性收件人的模板的通讯簿提供程序不支持根容器的**OpenEntry**调用。 
  
### <a name="to-implement-iablogonopenentry"></a>实现 IABLogon:: OpenEntry
  
1. 检查条目标识符是否为您的提供程序支持的有效标识符。 如果它不是有效的条目标识符, 则返回 MAPI_E_INVALID_ENTRYID。 
    
2. 检查使用_ulFlags_参数传入的标志。 如果 MAPI 已在 MAPI_MODIFY 中传递, 并且您的提供程序不允许对其对象进行修改, 则会失败并返回 MAPI_E_ACCESS_DENIED 错误值。 
    
3. 检查_lpInterface_参数中请求的接口是否对您的提供程序要求打开的对象的类型有效。 如果传入的参数无效, 则失败并返回 MAPI_E_INTERFACE_NOT_SUPPORTED 错误值。 
    
4. 如果_cbEntryID_参数为零, 则这是打开提供程序的根容器的请求。 创建根容器, 并将指针返回到其**IABContainer**接口实现。 
    
5. 如果提供程序实现了多个登录对象, 每个都有其自己的注册**MAPIUID**, 请使用相应的登录对象映射包含在条目标识符中的**MAPIUID** 。 
    
6. 确定条目标识符表示的对象的类型: 邮件用户、通讯组列表或属于提供程序的容器或一个一次性邮件用户或通讯组列表, 以便可以为_lpulObjectType_设置适当的值。参数. 
    
7. 创建适当类型的对象, 并设置以下基本属性:
    
    - **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    - **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    - **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))
    - **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
8. 从条目标识符中的信息计算**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 和**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。
    
9. 返回指向对象的接口实现的指针。 
    

