---
title: IExchangeModifyTable IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IExchangeModifyTable
api_type:
- COM
ms.assetid: 45a73c7b-5855-4b70-866b-facb41cb3c32
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 333e1d5cacc069ee1faef01426a1c0a60ef07f8e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418104"
---
# <a name="iexchangemodifytable--iunknown"></a>IExchangeModifyTable : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
支持访问 Microsoft Exchange Server 表对象，特别是 SACL (SACL) 表对象和规则表Microsoft Exchange Server对象。 此接口类似于[IMAPITable ： IUnknown](imapitableiunknown.md)接口，但它添加了对Microsoft Exchange Server SACLs 和规则的特定结构的支持。 
  
|||
|:-----|:-----|
|公开者：  <br/> |无  <br/> |
|实现者：  <br/> |服务器表对象  <br/> |
|调用者：  <br/> |MAPI 和客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IExchangeModifyTable  <br/> |
|指针类型：  <br/> |LPEXCHANGEMODIFYTABLE  <br/> |
|事务模型：  <br/> |Transacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](iexchangemodifytable-getlasterror.md) <br/> |返回有关 table 对象中发生的最后一个错误的信息。  <br/> |
|[GetTable](iexchangemodifytable-gettable.md) <br/> |返回一个指向 MAPI 表对象的接口的指针。  <br/> |
|[ModifyTable](iexchangemodifytable-modifytable.md) <br/> |更新 MAPI 表对象。  <br/> |
   
|**用于修改规则表的属性**|**Access**|
|:-----|:-----|
|**PR_RULE_ACTIONS (** [PidTagRuleActions](pidtagruleactions-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RULE_CONDITION (** [PidTagRuleCondition)](pidtagrulecondition-canonical-property.md)  <br/> |只读  <br/> |
|**PR_RULE_ID (** [PidTagRuleId](pidtagruleid-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RULE_LEVEL (** [PidTagRuleLevel](pidtagrulelevel-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RULE_NAME (** [PidTagRuleName](pidtagrulename-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RULE_PROVIDER (** [PidTagRuleProvider](pidtagruleprovider-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RULE_PROVIDER_DATA (** [PidTagRuleProviderData](pidtagruleproviderdata-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RULE_SEQUENCE (** [PidTagRuleSequence)](pidtagrulesequence-canonical-property.md)  <br/> |只读  <br/> |
|**PR_RULE_STATE (** [PidTagRuleState](pidtagrulestate-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RULE_USER_FLAGS (** [PidTagRuleUserFlags)](pidtagruleuserflags-canonical-property.md)  <br/> |只读  <br/> |
   
|**用于修改 SACL 表的属性**|**Access**|
|:-----|:-----|
|**PR_MEMBER_ENTRYID (** [PidTagMemberEntryId)](pidtagmemberentryid-canonical-property.md)  <br/> |只读  <br/> |
|**PR_MEMBER_ID (** [PidTagMemberId)](pidtagmemberid-canonical-property.md)  <br/> |只读  <br/> |
|**PR_MEMBER_NAME (** [PidTagMemberName)](pidtagmembername-canonical-property.md)  <br/> |只读  <br/> |
|**PR_MEMBER_RIGHTS (** [PidTagMemberRights)](pidtagmemberrights-canonical-property.md)  <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

若要获取 **IExchangeModifyTable** 接口，请对文件夹对象上类型为 PT_OBJECT 的属性调用 MAPI [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法。 调用 **OpenProperty** 方法时，将值IID_IExchangeModifyTable _lpiid_**参数中**。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

