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
  
当客户端或提供程序请求打开其中一个对象时，MAPI 将调用提供程序的 [IABLogon：：OpenEntry](iablogon-openentry.md) 方法。 MAPI 通过检查条目标识符的 [MAPIUID](mapiuid.md)部分，并匹配提供程序在 **IMAPISupport：：SetProviderUID** 调用中注册的 **MAPIUID，** 确定表示目标对象的条目标识符属于你的提供程序。 然后，MAPI 调用 **OpenEntry** 方法。 提供程序必须通过检索相应的对象（容器、通讯组列表或邮件用户）进行响应。 
  
NULL 条目标识符指示打开通讯簿提供程序的根容器的请求。 客户端打开根容器以访问其层次结构表及其收件人。 仅提供用于创建一次收件人的模板的通讯簿提供程序不支持对根容器的 **OpenEntry** 调用。 
  
### <a name="to-implement-iablogonopenentry"></a>实现 IABLogon：：OpenEntry
  
1. 检查条目标识符是提供程序支持的有效标识符。 如果条目标识符无效，则返回MAPI_E_INVALID_ENTRYID。 
    
2. 检查使用  _ulFlags_ 参数传入的标志。 如果 MAPI 已传入 MAPI_MODIFY且提供程序不允许修改其对象，则失败并返回错误MAPI_E_ACCESS_DENIED值。 
    
3. 检查  _lpInterface_ 参数中请求的接口是否对要求提供程序打开的对象类型有效。 如果传入的参数无效，则失败并返回MAPI_E_INTERFACE_NOT_SUPPORTED错误值。 
    
4. 如果  _cbEntryID_ 参数为零，则请求打开提供程序的根容器。 创建根容器并返回指向 **其 IABContainer 接口实现的** 指针。 
    
5. 如果提供程序实现多个登录对象，每个对象都有其自己的注册 **MAPIUID，** 则使用相应的登录对象映射条目标识符中包含的 **MAPIUID。** 
    
6. 确定条目标识符表示的对象类型：属于提供程序的邮件用户、通讯组列表或容器，或者一次消息用户或通讯组列表，以便可以为  _lpulObjectType_ 参数设置适当的值。 
    
7. 创建相应类型的 对象并设置以下基本属性：
    
    - **PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 
    - **PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 
    - **PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) 
    - **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 
    
8. 根据 **条目PR_EMAIL_ADDRESS (** 的信息计算 [PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 和 **PR_DISPLAY_NAME** ([PidTagDisplayName) 。](pidtagdisplayname-canonical-property.md)
    
9. 返回一个指向对象的接口实现指针。 
    

