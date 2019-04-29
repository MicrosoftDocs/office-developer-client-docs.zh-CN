---
title: 实现提供程序一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b0dcbfe-6bed-4fb8-a906-009f1d009055
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 023686702b76b5b29acf4304fcfdb3377e8cfcff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436291"
---
# <a name="implementing-a-provider-one-off-table"></a>实现提供程序一次性表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端应用程序的用户向传出的邮件中添加收件人时, MAPI 将调用提供程序的[IABLogon:: GetOneOffTable](iablogon-getoneofftable.md)方法。 通常情况下, 请求的地址类型对您的邮件系统是唯一的。 如果您的提供商支持收件人创建, 则必须提供一个一次性表格, 以显示每种类型的受支持收件人地址的模板。 如果您的提供商不支持收件人创建, 请从**GetOneOffTable**调用返回 MAPI_E_NO_SUPPORT。 
  
MAPI 通常会使提供程序的一次性表在会话生存期间处于打开状态, 仅当客户端调用子系统或通讯簿的[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法时, 才会释放此表。 此表上的通知的 MAPI 寄存器, 以便在添加或删除模板时, 可以向用户反映这些更改。 
  
 **实现 IABLogon:: GetOneOffTable**
  
1. 检查 flags 参数的值_ulFlags_。 如果设置了 MAPI_UNICODE 标志, 并且您的提供程序不支持 UNICODE, 则失败并返回 MAPI_E_BAD_CHARWIDTH。 
    
2. 检查是否已创建提供商的一次性表。 由于一次性表通常是静态的, 因此提供程序永远不需要经过一次创建过程。 如果表已存在, 则返回指向它的指针。 
    
3. 如果尚不存在一个一次性表, 请调用**CreateTable**以创建一个。 
    
4. 为表格行中的列设置以下属性:
    
  - **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 到模板可以创建的收件人类型的名称。 
    
  - **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md)) 到一次性模板的条目标识符。
    
  - **PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md)), 用于指示一次性表格显示中的层次结构级别。
    
  - **PR_SELECTABLE**([PidTagSelectable](pidtagselectable-canonical-property.md)) 设置为 TRUE, 以指示该行是否表示模板, 否则为 FALSE。
    
  - **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 到模板创建的地址的类型。
    
  - **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 到 DT_MAILUSER 或另一个指示模板的显示类型的值。
    
  - **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 到一个唯一的二进制值。 
    
5. 调用[ITableData:: HrModifyRow](itabledata-hrmodifyrow.md)以直接修改表。 
    
6. 调用[ITableData:: HrGetView](itabledata-hrgetview.md)以创建**IMAPITable**接口实现以返回到调用方。 
    

