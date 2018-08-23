---
title: 实现提供程序一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b0dcbfe-6bed-4fb8-a906-009f1d009055
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f484174bd0a83c9bb874bec4896fe3dd925405c7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568236"
---
# <a name="implementing-a-provider-one-off-table"></a>实现提供程序一次性表

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 客户端应用程序的用户将收件人添加到的传出邮件时调用提供商的[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)方法。 通常情况下，请求的地址的类型是唯一的邮件系统。 如果您的提供商支持收件人的创建，它必须提供一个一次性表，用于公开每种类型的受支持的收件人地址的模板。 如果您的提供程序不支持收件人的创建，返回 MAPI_E_NO_SUPPORT 从**GetOneOffTable**呼叫。 
  
MAPI 通常将您的提供商一次性表保持打开状态的生存期内会话，仅当在客户端调用子系统的时释放其或通讯簿的[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。 MAPI 注册此表中的通知，以便如果添加或删除模板时，可以向用户反映这些更改。 
  
 **若要实现 IABLogon::GetOneOffTable**
  
1. 检查的 flags 参数， _ulFlags_值。 如果设置了 MAPI_UNICODE 标志，并且您的提供程序不支持 Unicode，失败并返回 MAPI_E_BAD_CHARWIDTH。 
    
2. 检查是否已创建提供商的一次性表。 一次性表是通常静态的因为您的提供商从来多次通过创建过程。 如果表格已存在，向其返回一个指针。 
    
3. 如果尚不存在一次性表，调用**CreateTable**创建一个。 
    
4. 设置表格行中的列的以下属性：
    
  - **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 模板可以创建的收件人的类型的名称。 
    
  - **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md)) 到一次性模板的项标识符。
    
  - **PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md)) 指示显示一次性表中的层次结构级别。
    
  - **PR_SELECTABLE**([PidTagSelectable](pidtagselectable-canonical-property.md)) 为 TRUE 以指示是否该行表示模板和 FALSE 否则。
    
  - **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 到由模板创建的地址的类型。
    
  - **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 到 DT_MAILUSER 或另一个值，该值指示显示模板的类型。
    
  - **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 为唯一的二进制值。 
    
5. 调用[ITableData::HrModifyRow](itabledata-hrmodifyrow.md)直接修改表格。 
    
6. 调用[ITableData::HrGetView](itabledata-hrgetview.md)创建**IMAPITable**接口实现，以返回到呼叫者。 
    

