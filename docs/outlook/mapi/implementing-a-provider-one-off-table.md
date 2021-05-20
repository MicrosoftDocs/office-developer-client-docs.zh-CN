---
title: 实现提供程序One-Off表
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
# <a name="implementing-a-provider-one-off-table"></a>实现提供程序One-Off表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端应用程序的用户向传出邮件添加收件人时，MAPI 将调用提供程序的 [IABLogon：：GetOneOffTable](iablogon-getoneofftable.md) 方法。 通常，请求的地址类型对邮件系统是唯一的。 如果您的提供程序支持收件人创建，则它必须提供一个一次表，用于公开每种类型的受支持收件人地址的模板。 如果您的提供程序不支持创建收件人，请从 **GetOneOffTable** MAPI_E_NO_SUPPORT返回一个收件人。 
  
MAPI 通常会在会话的生存期内保持提供程序的一对一表为打开状态，仅在客户端调用子系统或通讯簿的 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法时释放它。 MAPI 在此表上注册通知，以便添加或删除模板时，这些更改可以反映给用户。 
  
 **实现 IABLogon：：GetOneOffTable**
  
1. 检查 flags 参数  _ulFlags 的值_。 如果已MAPI_UNICODE，并且您的提供程序不支持 Unicode，则失败并返回MAPI_E_BAD_CHARWIDTH。 
    
2. 检查是否已创建提供程序的一对一表。 由于一键式表通常是静态的，因此提供程序绝不会多次完成创建过程。 如果表已存在，则返回指向它的指针。 
    
3. 如果一对一表尚不存在，请调用 **CreateTable** 创建一个。 
    
4. 为表行中的列设置以下属性：
    
  - **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 模板可以创建的收件人类型的名称。 
    
  - **PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 一次模板的条目标识符。
    
  - **PR_DEPTH (** [PidTagDepth](pidtagdepth-canonical-property.md)) 来指示一次表显示中的层次结构级别。
    
  - **PR_SELECTABLE (** [PidTagSelectable](pidtagselectable-canonical-property.md)) 为 TRUE，以指示该行是否表示模板，否则为 FALSE。
    
  - **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 模板创建的地址类型。
    
  - **PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) DT_MAILUSER或指示模板的显示类型的其他值。
    
  - **PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 一个唯一的二进制值。 
    
5. 调用 [ITableData：：HrModifyRow](itabledata-hrmodifyrow.md) 以直接修改表。 
    
6. 调用 [ITableData：：HrGetView](itabledata-hrgetview.md) 以创建 **IMAPITable** 接口实现以返回到调用方。 
    

