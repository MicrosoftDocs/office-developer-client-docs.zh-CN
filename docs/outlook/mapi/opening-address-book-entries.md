---
title: 打开通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 017a62c0-49c6-47fb-acce-db58e6bb9cc5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cd86b9cc86f30aac75b732b97208933de4d336e9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566427"
---
# <a name="opening-address-book-entries"></a>打开通讯簿条目

**适用于**： Outlook 2013 |Outlook 2016 
  
在客户端或提供程序已请求您对象之一打开的 MAPI 调用您的提供商[IABLogon::OpenEntry](iablogon-openentry.md)方法。 MAPI，表示目标对象的项标识符通过确定属于您的提供商检查的项标识符的[MAPIUID](mapiuid.md)部分并将它与提供程序注册**调用**MAPIUID**匹配IMAPISupport::SetProviderUID**。 MAPI 然后调用**OpenEntry**方法。 您的提供商必须响应通过检索相应对象 — 容器、 通讯组列表或消息用户。 
  
NULL 条目标识符指示打开通讯簿提供程序的根容器的请求。 客户端打开根容器来访问其层次结构表和它的收件人。 仅提供模板，用于创建一次性收件人的地址簿提供程序的根容器不支持**OpenEntry**呼叫。 
  
### <a name="to-implement-iablogonopenentry"></a>若要实现 IABLogon::OpenEntry
  
1. 检查条目标识符为您提供商支持的有效标识符。 如果它不是有效的项标识符，返回 MAPI_E_INVALID_ENTRYID。 
    
2. 检查使用_ulFlags_参数传递的标志。 如果在 MAPI_MODIFY 已通过 MAPI 提供程序不允许要修改其对象，失败并返回 MAPI_E_ACCESS_DENIED 错误值。 
    
3. 检查请求_lpInterface_参数中的接口有效的已要求您提供程序打开的对象的类型。 如果传递中的参数无效，失败并返回 MAPI_E_INTERFACE_NOT_SUPPORTED 错误值。 
    
4. 如果_cbEntryID_参数为零，这是打开您的提供商根容器的请求。 创建根容器，并返回到其**IABContainer**接口实现的指针。 
    
5. 如果您的提供程序实现多个登录对象，每个都有自己注册**MAPIUID**， **MAPIUID**包含在与相应登录对象的项标识符的映射。 
    
6. 确定哪种类型的对象的项标识符代表： 邮件用户、 通讯组列表或容器属于您的提供商或一次性的邮件用户或通讯组列表，以便可以为_lpulObjectType_设置适当的值参数。 
    
7. 创建适当类型的对象，并设置以下基本属性：
    
    - **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    - **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    - **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))
    - **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
8. 计算**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 和**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 中的项标识符的信息。
    
9. 返回到该接口实现对象的指针。 
    

