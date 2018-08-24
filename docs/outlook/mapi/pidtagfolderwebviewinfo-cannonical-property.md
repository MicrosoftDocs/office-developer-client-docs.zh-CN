---
title: PidTagFolderWebViewInfo Cannonical Property
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
ms.openlocfilehash: eec8ea4b4ddee8b6c399bbb4871c286fea4fae3d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588403"
---
# <a name="pidtagfolderwebviewinfo-cannonical-property"></a>PidTagFolderWebViewInfo Cannonical Property

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含在 Microsoft Outlook 中的文件夹主页的 URL。 此属性包含调用**WebViewPersistenceObject**二进制流。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FOLDER_WEBVIEWINFO  <br/> |
|标识符：  <br/> |0x36DF  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 文件夹  <br/> |
   
## <a name="remarks"></a>注解

可为指定的任何 Outlook 文件夹主页 URL。 从属性对话框的文件夹的**主页**选项卡，可以在 Outlook 中访问此信息。 
  
根据特定的策略设置，主页可能被忽略 outlook 的 MAPI 存储区包含此文件夹不在其[IMSCapabilities::GetCapabilities](pidtagfolderwebviewinfo-cannonical-property.md)实现报告 MSCAP_SECURE_FOLDER_HOMEPAGES。 
  
**Outlook 今日**文件夹和公用文件夹可以具有主页的 Url。 **Outlook 今日**文件夹但是使用另一种机制来管理其主页 URL;本主题中未涵盖的机制。 公用文件夹可能还需要在其中定义特定于用户的主页 URL。 但是，该功能不在本主题中所述。 
  
此属性的值是调用**WebViewPersistenceObject**二进制流。
  
### <a name="webviewpersistenceobject-stream-structure"></a>WebViewPersistenceObject 流结构

**WebViewPersistenceObject**流结构包含有关某个文件夹主页 URL 的信息。 
  
此结构中的数据元素存储在-little-endian 字节的顺序，紧跟相互按照下面指定的顺序。 
  
> [!NOTE]
> 以下说明可能不会列出所有 Outlook; 支持的字段值因此，当您的代码读取现有流时，可能还发现此处未列出一些标志。 但是，该说明可用于以编程方式创建 Outlook 将了解**PidTagFolderWebViewInfo**属性的值。 
  
 _dwVersion_
  
> DWORD （4 个字节）。 结构的格式的版本。 从 Microsoft Office Outlook 2007 中，该字段仅受支持的值如下所示。
    
|**值名称**|**值**|
|:-----|:-----|
|WEBVIEW_PERSISTENCE_VERSION  <br/> |0x00000002  <br/> |
   
 _dwType_
  
> DWORD （4 个字节）。 主页信息的类型。 从 Microsoft Office Outlook 2007 中，该字段仅受支持的值如下所示。
    
|**值名称**|**值**|
|:-----|:-----|
|WEBVIEWURL  <br/> |0x00000001  <br/> |
   
 _dwFlags_
  
> DWORD （4 个字节）。 零个或更多的组合标记其值并在下表中列出的含义。
    
|标志名称 ***|****值****|****说明****|
|:-----|:-----|:-----|
|WEBVIEW_FLAGS_SHOWBYDEFAULT  <br/> |0x00000001  <br/> |**显示默认情况下，此文件夹主页**复选框已签入的文件夹的属性对话框的**主页**选项卡。  <br/> |
   
 _dwUnused [7]_
  
> 7 DWORD 元素 （28 字节） 的数组。 未使用。
    
cbData
  
> ULONG （4 个字节）。 以字节为单位的_wzURL_数据元素的大小。 
    
 _wzURL_
  
> WCHAR 元素的数组。 Utf-16 字符串表示形式零结尾主页的 URL。
    
### <a name="webviewpersistenceobject-stream-sample"></a>WebViewPersistenceObject 流示例

本节介绍**WebViewPersistenceObject**流的示例。 Stream 指定的主页上 URL"http://www.microsoft.com"。 
  
 **数据转储**
  
下面是流的它将二进制编辑器中显示数据转储。
  
|**流偏移**|**数据字节**|**ASCII 数据**|
|:-----|:-----|:-----|
|0000000000  <br/> | `02 00 00 00 01 00 00 00 01 00 00 00 00 00 00 00` <br/> | `?...?...?.......` <br/> |
|0000000010  <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
|0000000020  <br/> | `00 00 00 00 00 00 00 00 32 00 00 00 68 00 74 00` <br/> | `........2...h.t.` <br/> |
|0000000030  <br/> | `74 00 70 00 3A 00 2F 00 2F 00 77 00 77 00 77 00` <br/> | `t.p.:././.w.w.w.` <br/> |
|0000000040  <br/> | `2E 00 6D 00 69 00 63 00 72 00 6F 00 73 00 6F 00` <br/> | `..m.i.c.r.o.s.o.` <br/> |
|0000000050  <br/> | `66 00 74 00 2E 00 63 00 6F 00 6D 00 00 00` <br/> | `f.t...c.o.m...` <br/> |
   
下面是**WebViewPersistenceObject**流的示例数据的分析。 
  
 _dwVersion_
  
> 偏移 0x0，4 个字节： 0x00000002:uc (WEBVIEW_PERSISTENCE_VERSION)。
    
 _dwType_
  
> 偏移 0x4，4 个字节： 0x00000001 (WEBVIEWURL)。
    
 _dwFlags_
  
> 偏移 0x8，4 个字节： 0x00000001 (WEBVIEW_FLAGS_SHOWBYDEFAULT)。
    
 _dwUnused [7]_
  
> 偏移 0xC，28 字节： 所有零。
    
 _cbData_
  
> 偏移 0x28，4 个字节： 0x00000032。
    
 _wzURL_
  
> 偏移量 0x2C，0x32 字节： 25 WCHARs 的数组。 一个 Unicode 零结尾字符串值:"http://www.microsoft.com"。
    

