---
title: 将存储类型视为专用的属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- Make Store Type Private Property
api_type:
- COM
ms.assetid: 7f489f55-46d4-8a88-6ebe-9db6446e69a5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7f60d9524af18bb7f2e876386c45b84f207d42bc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776183"
---
# <a name="make-store-type-private-property"></a>将存储类型视为专用的属性

  
  
**适用于**： Outlook 
  
辅助存储视为私有。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|公开上：  <br/> |[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象  <br/> |
|通过创建：  <br/> |存储提供程序  <br/> |
|通过来访问：  <br/> |Outlook 和其他客户端  <br/> |
|属性类型  <br/> |PT_BOOLEAN  <br/> |
|访问类型：  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

若要提供的任何存储功能，存储提供程序必须实现[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。 当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。 [HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。 
  
若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。 调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PS_PUBLIC_STRINGS  <br/> |
|ulKind:  <br/> |MNID_STRING  <br/> |
|Kind.lpwstrName:  <br/> |L"urn： 架构-microsoft-com:office:outlook #storetypeprivate"  <br/> |
   
存储提供程序可以使用此属性使 Outlook 辅助用户存储时，将其视为私有。 
  
默认情况下，Outlook 将辅助存储相同的方式视为代理存储区，并辅助存储中的项目是专用仅当用户标记这些专门为私有。 当此属性为**true**时，从第二存储区删除的项目被移动到主存储区中的**已删除邮件**文件夹。 不显示标记为私密的项。 草稿存储在主存储区中草稿文件夹中。 
  
如果 Outlook 版本早于 Microsoft Office Outlook 2003 Service Pack 1，或如果其值为**false**，则忽略此属性。
  

