---
title: 使应用商店类型成为专用属性
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
ms.openlocfilehash: da55afcabb1354959a71d6f10472c05540427b19
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428541"
---
# <a name="make-store-type-private-property"></a>使应用商店类型成为专用属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将辅助存储视为专用存储。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|在：  <br/> |[IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 对象  <br/> |
|创建者：  <br/> |存储提供程序  <br/> |
|访问者：  <br/> |Outlook客户端和其他客户端  <br/> |
|属性类型  <br/> |PT_BOOLEAN  <br/> |
|访问类型：  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

若要提供任何存储功能，存储提供程序必须实现 [IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 并返回传递给 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 调用的任何属性的有效属性标记。 当其中任何属性的属性标记传递到 [IMAPIProp：：GetProps](imapiprop-getprops.md)时，存储提供程序还必须返回正确的属性值。 存储提供程序可以调用 [HrGetOneProp](hrgetoneprop.md) 和 [HrSetOneProp](hrsetoneprop.md) 获取或设置这些属性。 
  
若要检索此属性的值，客户端应首先使用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 获取属性标记，然后在 [IMAPIProp：：GetProps](imapiprop-getprops.md) 中指定此属性标记以获取值。 调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)时，为输入参数 _lppPropNames_ 指向的 [MAPINAMEID](mapinameid.md)结构指定以下值：
  
|||
|:-----|:-----|
|lpGuid：  <br/> |PS_PUBLIC_STRINGS  <br/> |
|ulKind：  <br/> |MNID_STRING  <br/> |
|Kind.lpwstrName：  <br/> |L"urn：schemas-microsoft-com：office：outlook#storetypeprivate"  <br/> |
   
当存储提供程序是用户的辅助Outlook时，可以使用此属性将此属性视为专用存储。 
  
默认情况下，Outlook存储处理辅助存储的方式与代理存储相同，并且辅助存储中的项目仅在用户专门将其标记为专用时是私有的。 当此属性为 **true** 时，从辅助存储中删除的项目将移动到主存储中的"已删除 **邮件** "文件夹。 标记为私有的项目不显示。 草稿存储在主存储的"草稿"文件夹中。 
  
如果服务包的版本早于 Outlook 2003 Service Pack 1 Microsoft Office Outlook或其值为 **false，** 则忽略此属性。
  

