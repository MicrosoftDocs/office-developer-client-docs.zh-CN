---
title: ArchiveSourceSupportMask
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ArchiveSourceSupportMask
api_type:
- COM
ms.assetid: e35216e0-c23f-70f2-0d5f-1ac5dc00fd8c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1e0c099783b4d44b1aaf746b07c77981c135ca9a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19774556"
---
# <a name="archivesourcesupportmask"></a>ArchiveSourceSupportMask

  
  
**适用于**： Outlook 
  
指定 Microsoft Office Outlook 是否应扫描存储区中的文件夹并将它们自动存档。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|公开上：  <br/> |[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象  <br/> |
|通过创建：  <br/> |存储提供程序  <br/> |
|通过来访问：  <br/> |Outlook 和其他客户端  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|访问类型：  <br/> |只读或读/写，具体取决于存储提供程序  <br/> |
   
## <a name="remarks"></a>说明

若要提供的任何存储功能，存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。 当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。 [HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。 
  
若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。 调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PSETID_Common  <br/> |
|ulKind:  <br/> |MNID_STRING  <br/> |
|Kind.lpwstrName:  <br/> |L"ArchiveSourceSupportMask"  <br/> |
   
此属性允许存储提供程序，以指定 Outlook 是否应扫描存储区中的文件夹并将它们自动存档。
  
默认情况下，对存储，这意味着 Outlook 可以扫描存储区上的文件夹不公开此属性。 如果公开此属性，以下是可能的值：
  
```cpp
enum { 
 ASM_DEFAULT              = 0, 
 ASM_DO_NOT_ARCHIVE         = 1 << 0x0, 
 ASM_CLIENT_DO_NOT_CHANGE = 1 << 0xF 
};
```

ASM_DEFAULT
  
- Outlook 可以扫描存储区上的文件夹。
    
ASM_DO_NOT_ARCHIVE
  
- Outlook 不应扫描存储区上的文件夹。
    
ASM_CLIENT_DO_NOT_CHANGE
  
- 不允许客户端来更改此属性存储。 请注意，常量**ASM_CLIENT_DO_NOT_CHANGE**以供将来参考是当前未实现。 现在，存储可以阻止客户端硬存储此属性返回的值更改此标志。 
    

