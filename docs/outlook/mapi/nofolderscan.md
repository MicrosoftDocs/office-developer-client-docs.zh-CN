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
ms.openlocfilehash: 3416bc50e4628df2be09f9fe1a22d19530bcdff8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578050"
---
# <a name="nofolderscan"></a>NoFolderScan

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定 Microsoft Office Outlook 是否应扫描存储区上的联系人文件夹。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|公开上：  <br/> |[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象  <br/> |
|通过创建：  <br/> |存储提供程序  <br/> |
|通过来访问：  <br/> |Outlook 和其他客户端  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|访问类型：  <br/> |只读或读/写，具体取决于存储提供程序  <br/> |
   
## <a name="remarks"></a>注解

若要提供的任何存储功能，存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。 当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。 [HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。 
  
若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。 调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PSETID_Common  <br/> |
|ulKind:  <br/> |MNID_STRING  <br/> |
|Kind.lpwstrName:  <br/> |L"NoFolderScan"  <br/> |
   
此属性提供了一种方法向 Outlook 中指定的存储提供程序不扫描以避免性能下降存储区中的联系人文件夹。 使用 Outlook 检查在此期间的邮件合并操作中的状态和此属性的值在启动扫描之前。
  
默认情况下，对存储，这意味着 Outlook 可以扫描存储区上的联系人文件夹不公开此属性。 如果公开此属性，以下是可能的值：
  
- 零 (0): Outlook 可以执行扫描。
    
- 非零值： Outlook 不应扫描存储区上的联系人文件夹。
    

