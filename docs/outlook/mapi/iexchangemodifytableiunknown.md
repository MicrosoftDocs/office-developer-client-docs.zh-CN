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
ms.openlocfilehash: 51a83e1e28534cc237419d9c4ae475c1d719c5de
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565072"
---
# <a name="iexchangemodifytable--iunknown"></a>IExchangeModifyTable : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
支持对 Microsoft Exchange Server table 对象的访问，特别是系统访问控制列表 (SACL) table 对象和规则对 Microsoft Exchange Server 文件夹的 table 对象。 此接口类似于[IMAPITable: IUnknown](imapitableiunknown.md)界面，但它添加支持用于控制 Sacl 和规则的特定于 Microsoft Exchange 服务器的结构。 
  
|||
|:-----|:-----|
|由公开：  <br/> |无  <br/> |
|通过实现：  <br/> |服务器 table 对象  <br/> |
|调用：  <br/> |MAPI 和客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IExchangeModifyTable  <br/> |
|指针类型：  <br/> |LPEXCHANGEMODIFYTABLE  <br/> |
|事务模型：  <br/> |事务处理  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](iexchangemodifytable-getlasterror.md) <br/> |返回一个 table 对象中上次发生的错误有关的信息。  <br/> |
|[GetTable](iexchangemodifytable-gettable.md) <br/> |返回一个 MAPI table 对象的接口的指针。  <br/> |
|[ModifyTable](iexchangemodifytable-modifytable.md) <br/> |更新 MAPI table 对象。  <br/> |
   
|**用于修改规则表属性**|**Access**|
|:-----|:-----|
|**PR_RULE_ACTIONS**([PidTagRuleActions](pidtagruleactions-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RULE_CONDITION**([PidTagRuleCondition](pidtagrulecondition-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RULE_ID**([PidTagRuleId](pidtagruleid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RULE_LEVEL**([PidTagRuleLevel](pidtagrulelevel-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RULE_NAME**([PidTagRuleName](pidtagrulename-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RULE_PROVIDER**([PidTagRuleProvider](pidtagruleprovider-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RULE_PROVIDER_DATA**([PidTagRuleProviderData](pidtagruleproviderdata-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RULE_SEQUENCE**([PidTagRuleSequence](pidtagrulesequence-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RULE_STATE**([PidTagRuleState](pidtagrulestate-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RULE_USER_FLAGS**([PidTagRuleUserFlags](pidtagruleuserflags-canonical-property.md))  <br/> |只读  <br/> |
   
|**用于修改 SACL 表属性**|**Access**|
|:-----|:-----|
|**PR_MEMBER_ENTRYID**([PidTagMemberEntryId](pidtagmemberentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MEMBER_ID**([PidTagMemberId](pidtagmemberid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MEMBER_NAME**([PidTagMemberName](pidtagmembername-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MEMBER_RIGHTS**([PidTagMemberRights](pidtagmemberrights-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="remarks"></a>注解

若要获得**IExchangeModifyTable**接口，调用类型 PT_OBJECT 上一个 folder 对象的属性上的 MAPI [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。 当调用**OpenProperty**方法时，将传递_lpiid_参数中的值**IID_IExchangeModifyTable** 。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

