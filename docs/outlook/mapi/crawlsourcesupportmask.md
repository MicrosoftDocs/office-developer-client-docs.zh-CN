---
title: CrawlSourceSupportMask
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CrawlSourceSupportMask
api_type:
- COM
ms.assetid: d0a2f7ea-df6a-89e8-18c2-ac92e0a20edc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cc3fcedb73b4acbd85529615d857403b4c268f3d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420911"
---
# <a name="crawlsourcesupportmask"></a>CrawlSourceSupportMask

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定 Microsoft Office Outlook 是否应扫描存储区中的文件夹, 包括 "联系人"、"日历" 和 "任务" 文件夹, 以便在启动时填充导航窗格。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|公开于:  <br/> |[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象  <br/> |
|创建者:  <br/> |存储提供程序  <br/> |
|访问者:  <br/> |Outlook 和其他客户端  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|访问类型:  <br/> |只读或读/写, 具体取决于存储提供程序  <br/> |
   
## <a name="remarks"></a>说明

若要提供任何存储功能, 存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md) , 并返回传递给[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)调用的任何这些属性的有效属性标记。 当这些属性中任一属性的属性标记传递给[IMAPIProp:: GetProps](imapiprop-getprops.md)时, 存储提供程序还必须返回正确的属性值。 存储提供程序可以调用[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)以获取或设置这些属性。 
  
若要检索此属性的值, 客户端应首先使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取属性标记, 然后在[IMAPIProp:: GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。 调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)时, 请为输入参数_lppPropNames_所指向的[MAPINAMEID](mapinameid.md)结构指定以下值:
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PSETID_Common  <br/> |
|ulKind:  <br/> |MNID_STRING  <br/> |
|类型 lpwstrName:  <br/> |L "CrawlSourceSupportMask"  <br/> |
   
此属性提供了一种存储提供程序以指定 Outlook 是否应扫描存储中的各个文件夹的方法。 当 Outlook 扫描每个打开的存储区上的现有文件夹以填充**导航**窗格时, 在启动时使用它。Outlook 在启动扫描前检查是否存在该存储的该属性的状态和值。 
  
默认情况下, 不会在存储区上公开此属性, 这意味着 Outlook 可以扫描存储区上的文件夹。 如果公开了属性, 以下是可能的值:
  
```
enum { 
 CSM_DEFAULT              = 0, 
 CSM_DO_NOT_CRAWL         = 1 << 0x0, 
 CSM_CLIENT_DO_NOT_CHANGE = 1 << 0xF 
};
```

CSM_DEFAULT
  
- Outlook 可以扫描存储区上的文件夹。
    
CSM_DO_NOT_CRAWL
  
- Outlook 不应扫描存储区上的文件夹。
    
CSM_CLIENT_DO_NOT_CHANGE
  
- 不允许客户端更改存储区上的该属性。 请注意, 常量**CSM_CLIENT_DO_NOT_CHANGE**是为了供将来参考, 目前尚未实现。 现在, 存储可以阻止客户端更改此标志, hardcoding 存储为此属性返回的值。 
    

