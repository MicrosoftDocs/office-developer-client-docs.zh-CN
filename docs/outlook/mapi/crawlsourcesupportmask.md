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
  
指定用户Microsoft Office Outlook在启动时是否扫描存储区中的文件夹（包括联系人、日历和任务文件夹）以填充导航窗格。
  
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
|Kind.lpwstrName：  <br/> |L"CrawlSourceSupportMask"  <br/> |
   
此属性为存储提供程序提供了一种方法，Outlook是否应该扫描存储区中的各种文件夹。 当扫描每个打开Outlook的现有文件夹以填充导航窗格时，**它将在启动时** 使用;Outlook扫描之前，检查存储区中此属性是否存在和值。 
  
默认情况下，此属性不会在存储区上公开，这意味着Outlook扫描存储区上的文件夹。 如果公开该属性，则可能的值如下：
  
```
enum { 
 CSM_DEFAULT              = 0, 
 CSM_DO_NOT_CRAWL         = 1 << 0x0, 
 CSM_CLIENT_DO_NOT_CHANGE = 1 << 0xF 
};
```

CSM_DEFAULT
  
- Outlook扫描存储区上的文件夹。
    
CSM_DO_NOT_CRAWL
  
- Outlook不应扫描存储区上的文件夹。
    
CSM_CLIENT_DO_NOT_CHANGE
  
- 不允许客户端在存储上更改此属性。 请注意，常量 **CSM_CLIENT_DO_NOT_CHANGE** 供将来参考，当前未实现。 目前，存储区可以通过硬用存储为此属性返回的值硬值来阻止客户端更改此标志。 
    

