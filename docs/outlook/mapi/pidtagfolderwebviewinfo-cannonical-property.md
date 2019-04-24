---
title: PidTagFolderWebViewInfo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFolderWebViewInfo
api_type:
- HeaderDef
ms.assetid: 96ea23df-aa4f-4b3e-9663-e7db39f668c1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 70932e703511235e9f5e32efd95b18d1b66494e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316308"
---
# <a name="pidtagfolderwebviewinfo-cannonical-property"></a>PidTagFolderWebViewInfo 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 Microsoft Outlook 中文件夹主页的 URL。 此属性包含一个名为**WebViewPersistenceObject**的二进制流。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FOLDER_WEBVIEWINFO  <br/> |
|标识符:  <br/> |0x36DF  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 文件夹  <br/> |
   
## <a name="remarks"></a>注解

可以为任何 Outlook 文件夹指定主页 URL。 可从文件夹的 "属性" 对话框的 "**主页**" 选项卡中访问 Outlook 中的此信息。 
  
根据某些策略设置, 如果包含此文件夹的 MAPI 存储不会在其[IMSCapabilities:: GetCapabilities](pidtagfolderwebviewinfo-cannonical-property.md)实现中报告 MSCAP_SECURE_FOLDER_HOMEPAGES, 则 Outlook 可能会忽略主页。 
  
" **Outlook 今日**" 文件夹和公用文件夹都可以包含主页 url。 但是, " **Outlook 今日**" 文件夹使用不同的机制来管理其主页 URL;本主题不包含该机制。 公用文件夹也可能有一个特定于某个用户的主页 URL 定义在该文件夹中。 但是, 本主题未对此功能进行介绍。 
  
此属性的值是名为**WebViewPersistenceObject**的二进制流。
  
### <a name="webviewpersistenceobject-stream-structure"></a>WebViewPersistenceObject 流结构

**WebViewPersistenceObject**流结构包含有关文件夹的主页 URL 的信息。 
  
此结构中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面指定的顺序中的一个。 
  
> [!NOTE]
> 以下说明可能不会列出 Outlook 支持的所有字段值;因此, 当您的代码读取现有流时, 还可能会发现此处未列出的一些标志。 但是, 可以使用此说明以编程方式为 Outlook 将理解的**PidTagFolderWebViewInfo**属性创建值。 
  
 _dwVersion_
  
> DWORD (4 个字节)。 结构格式的版本。 从 Microsoft Office Outlook 2007, 该字段唯一受支持的值如下所示。
    
|**值名称**|**值**|
|:-----|:-----|
|WEBVIEW_PERSISTENCE_VERSION  <br/> |0x00000002  <br/> |
   
 _dwType_
  
> DWORD (4 个字节)。 主页信息的类型。 从 Microsoft Office Outlook 2007, 该字段唯一受支持的值如下所示。
    
|**值名称**|**值**|
|:-----|:-----|
|WEBVIEWURL  <br/> |0x00000001  <br/> |
   
 _dwFlags_
  
> DWORD (4 个字节)。 下表中列出了零个或多个标志的组合, 这些标志的值和含义如下所示。
    
|标记名称 * * * *|****值****|****说明****|
|:-----|:-----|:-----|
|WEBVIEW_FLAGS_SHOWBYDEFAULT  <br/> |0x00000001  <br/> |在文件夹的 "属性" 对话框的 "**主页**" 选项卡中选中了 "**显示该文件夹的主页默认值**" 复选框。  <br/> |
   
 _dwUnused [7]_
  
> 一个由7个 DWORD 元素组成的数组 (总共28个字节)。 未经.
    
cbData
  
> ULONG (4 个字节)。 _wzURL_数据元素的大小 (以字节为单位)。 
    
 _wzURL_
  
> WCHAR 元素的数组。 以零结尾的主页 URL 字符串的 UTF-16 表示形式。
    
### <a name="webviewpersistenceobject-stream-sample"></a>WebViewPersistenceObject 流示例

本节介绍**WebViewPersistenceObject**流的示例。 stream 指定主页 URL "https://www.microsoft.com"。 
  
 **数据转储**
  
以下是流的数据转储, 因为它将显示在二进制编辑器中。
  
|**流偏移量**|**数据字节**|**ASCII 数据**|
|:-----|:-----|:-----|
|0000000000  <br/> | `02 00 00 00 01 00 00 00 01 00 00 00 00 00 00 00` <br/> | `?...?...?.......` <br/> |
|0000000010  <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
|0000000020  <br/> | `00 00 00 00 00 00 00 00 32 00 00 00 68 00 74 00` <br/> | `........2...h.t.` <br/> |
|0000000030  <br/> | `74 00 70 00 3A 00 2F 00 2F 00 77 00 77 00 77 00` <br/> | `t.p.:././.w.w.w.` <br/> |
|0000000040  <br/> | `2E 00 6D 00 69 00 63 00 72 00 6F 00 73 00 6F 00` <br/> | `..m.i.c.r.o.s.o.` <br/> |
|0000000050  <br/> | `66 00 74 00 2E 00 63 00 6F 00 6D 00 00 00` <br/> | `f.t...c.o.m...` <br/> |
   
下面是对**WebViewPersistenceObject**流的示例数据的分析。 
  
 _dwVersion_
  
> 偏移 0x0, 4 个字节: 0x00000002 (WEBVIEW_PERSISTENCE_VERSION)。
    
 _dwType_
  
> 偏移 0x4, 4 个字节: 0x00000001 (WEBVIEWURL)。
    
 _dwFlags_
  
> 偏移为 0x8, 4 个字节: 0x00000001 (WEBVIEW_FLAGS_SHOWBYDEFAULT)。
    
 _dwUnused [7]_
  
> 偏移量 0xC, 28 个字节: 全零。
    
 _cbData_
  
> 偏移量 0x28, 4 个字节: 0x00000032。
    
 _wzURL_
  
> 偏移量 0x2C, 0x32 字节:25 WCHARs 的数组。 Unicode 以零结尾的字符串值: "https://www.microsoft.com"。
    

