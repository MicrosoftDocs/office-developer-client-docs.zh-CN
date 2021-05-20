---
title: NoFolderScan
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4949aef9-4c96-82cc-cd13-57981e07cc40
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fc5f5a42e2b1e57374ff80a9333b927cc8dba120
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436805"
---
# <a name="nofolderscan"></a>NoFolderScan

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定用户Microsoft Office Outlook应扫描存储区上的联系人文件夹。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|在：  <br/> |[IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 对象  <br/> |
|创建者：  <br/> |存储提供程序  <br/> |
|访问者：  <br/> |Outlook客户端和其他客户端  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|访问类型：  <br/> |只读或可读/写，具体取决于存储提供程序  <br/> |
   
## <a name="remarks"></a>备注

若要提供任何存储功能，存储提供程序必须实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 并返回传递给 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 调用的任何属性的有效属性标记。 当其中任何属性的属性标记传递到 [IMAPIProp：：GetProps](imapiprop-getprops.md)时，存储提供程序还必须返回正确的属性值。 存储提供程序可以调用 [HrGetOneProp](hrgetoneprop.md) 和 [HrSetOneProp](hrsetoneprop.md) 获取或设置这些属性。 
  
若要检索此属性的值，客户端应首先使用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 获取属性标记，然后在 [IMAPIProp：：GetProps](imapiprop-getprops.md) 中指定此属性标记以获取值。 调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)时，为输入参数 _lppPropNames_ 指向的 [MAPINAMEID](mapinameid.md)结构指定以下值：
  
|||
|:-----|:-----|
|lpGuid：  <br/> |PSETID_Common  <br/> |
|ulKind：  <br/> |MNID_STRING  <br/> |
|Kind.lpwstrName：  <br/> |L"NoFolderScan"  <br/> |
   
此属性为存储提供程序提供了一种指定Outlook扫描存储中的联系人文件夹以避免性能下降的方法。 在邮件合并操作中，它Outlook启动扫描之前检查此属性是否存在和值。
  
默认情况下，此属性不会在存储区上公开，这意味着Outlook可以扫描存储区上的"联系人"文件夹。 如果公开该属性，则可能的值如下：
  
- 零 (0) ：Outlook执行扫描。
    
- 非零值：Outlook不扫描存储上的联系人文件夹。
    

