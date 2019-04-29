---
title: 将存储类型设为私有属性
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
# <a name="make-store-type-private-property"></a>将存储类型设为私有属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将辅助存储视为专用。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|公开于:  <br/> |[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象  <br/> |
|创建者:  <br/> |存储提供程序  <br/> |
|访问者:  <br/> |Outlook 和其他客户端  <br/> |
|属性类型  <br/> |PT_BOOLEAN  <br/> |
|访问类型:  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>说明

若要提供任何存储功能, 存储提供程序必须实现[IMsgStore: IMAPIProp](imsgstoreimapiprop.md) , 并返回传递给[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)调用的任何这些属性的有效属性标记。 当这些属性中任一属性的属性标记传递给[IMAPIProp:: GetProps](imapiprop-getprops.md)时, 存储提供程序还必须返回正确的属性值。 存储提供程序可以调用[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)以获取或设置这些属性。 
  
若要检索此属性的值, 客户端应首先使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取属性标记, 然后在[IMAPIProp:: GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。 调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)时, 请为输入参数_lppPropNames_所指向的[MAPINAMEID](mapinameid.md)结构指定以下值:
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PS_PUBLIC_STRINGS  <br/> |
|ulKind:  <br/> |MNID_STRING  <br/> |
|类型 lpwstrName:  <br/> |L "urn: 架构-microsoft-com: office: outlook # storetypeprivate"  <br/> |
   
当应用程序是用户的辅助存储时, 存储提供程序可以使用此属性让 Outlook 将其视为私有。 
  
默认情况下, Outlook 按与委派存储相同的方式处理辅助存储, 辅助存储中的项目仅当用户特别将其标记为专用时才是专用的。 当此属性为**true**时, 从辅助存储中删除的项目将移至主存储中的 "**已删除邮件**" 文件夹中。 标记为 "私人性质" 的项目不会显示。 草稿存储在主存储区的 "草稿" 文件夹中。 
  
如果 Outlook 的版本早于 Microsoft Office Outlook 2003 Service Pack 1, 或者其值为**false**, 则忽略此属性。
  

