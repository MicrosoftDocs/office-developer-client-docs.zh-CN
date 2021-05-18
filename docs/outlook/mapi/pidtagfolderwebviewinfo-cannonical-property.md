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
  
包含 Microsoft 文件夹中文件夹主页的 URL Outlook。 此属性包含名为 **WebViewPersistenceObject 的二进制流**。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FOLDER_WEBVIEWINFO  <br/> |
|标识符:  <br/> |0x36DF  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 文件夹  <br/> |
   
## <a name="remarks"></a>备注

可指定任何文件夹的主页 URL Outlook URL。 可以从文件夹的"Outlook"对话框的"主页"选项卡访问此信息。 
  
如果包含此文件夹的 MAPI 存储未在其[IMSCapabilities：：GetCapabilities](pidtagfolderwebviewinfo-cannonical-property.md)实现中报告 MSCAP_SECURE_FOLDER_HOMEPAGES，则 Outlook 可能会忽略主页，具体取决于某些策略设置。 
  
The **Outlook Today** folder and a public folder can have home page URLs. 但是 **，Outlook Today** 文件夹使用不同的机制来管理其主页 URL;本主题中未介绍该机制。 公用文件夹可能还有一个特定于用户的主页 URL 定义。 但是，本主题中未介绍该功能。 
  
此属性的值是一个称为 **WebViewPersistenceObject 的二进制流**。
  
### <a name="webviewpersistenceobject-stream-structure"></a>WebViewPersistenceObject 流结构

**WebViewPersistenceObject** 流结构包含有关文件夹的主页 URL 的信息。 
  
此结构中的数据元素按小尾字节顺序存储，按照以下指定顺序彼此紧接。 
  
> [!NOTE]
> 以下说明可能未列出所有受此参数支持的Outlook;因此，当代码读取现有流时，也可能找到此处未列出的某些标志。 但是，您可以使用此说明以编程方式为 **PidTagFolderWebViewInfo** 属性创建值，Outlook理解。 
  
 _dwVersion_
  
> DWORD (4 字节) 。 结构格式的版本。 自 2007 Microsoft Office Outlook起，此字段的唯一受支持值如下所示。
    
|**值名称**|**值**|
|:-----|:-----|
|WEBVIEW_PERSISTENCE_VERSION  <br/> |0x00000002  <br/> |
   
 _dwType_
  
> DWORD (4 字节) 。 主页信息的类型。 自 2007 Microsoft Office Outlook起，此字段的唯一受支持值如下所示。
    
|**值名称**|**值**|
|:-----|:-----|
|WEBVIEWURL  <br/> |0x00000001  <br/> |
   
 _dwFlags_
  
> DWORD (4 字节) 。 下表列出了其值和含义的零个或多个标志的组合。
    
|标志名称****|****值****|****说明****|
|:-----|:-----|:-----|
|WEBVIEW_FLAGS_SHOWBYDEFAULT  <br/> |0x00000001  <br/> |在 **文件夹的"属性**"对话框的"主页"选项卡中选中了"默认情况下显示此文件夹的主页"复选框。  <br/> |
   
 _dwUnused[7]_
  
> 一个包含 7 个 DWORD 元素 (28 个字节) 。 未使用。
    
cbData
  
> ULONG (4 字节) 。 _wzURL_ 数据元素的大小（以字节为单位）。 
    
 _wzURL_
  
> WCHAR 元素的数组。 以零结尾的主页 URL 字符串的 UTF-16 表示形式。
    
### <a name="webviewpersistenceobject-stream-sample"></a>WebViewPersistenceObject 流示例

本节介绍 **WebViewPersistenceObject 流** 的示例。 流指定主页 URL " https://www.microsoft.com "。 
  
 **数据转储**
  
下面是流的数据转储，就像在二进制编辑器中显示一样。
  
|**流偏移**|**数据字节数**|**ASCII 数据**|
|:-----|:-----|:-----|
|0000000000  <br/> | `02 00 00 00 01 00 00 00 01 00 00 00 00 00 00 00` <br/> | `?...?...?.......` <br/> |
|0000000010  <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
|0000000020  <br/> | `00 00 00 00 00 00 00 00 32 00 00 00 68 00 74 00` <br/> | `........2...h.t.` <br/> |
|0000000030  <br/> | `74 00 70 00 3A 00 2F 00 2F 00 77 00 77 00 77 00` <br/> | `t.p.:././.w.w.w.` <br/> |
|0000000040  <br/> | `2E 00 6D 00 69 00 63 00 72 00 6F 00 73 00 6F 00` <br/> | `..m.i.c.r.o.s.o.` <br/> |
|0000000050  <br/> | `66 00 74 00 2E 00 63 00 6F 00 6D 00 00 00` <br/> | `f.t...c.o.m...` <br/> |
   
下面是 **WebViewPersistenceObject 流的示例数据的分析** 。 
  
 _dwVersion_
  
> 偏移0x0，4 字节：0x00000002 (WEBVIEW_PERSISTENCE_VERSION) 。
    
 _dwType_
  
> 偏移0x4，4 个字节：0x00000001 (WEBVIEWURL) 。
    
 _dwFlags_
  
> 偏移0x8，4 字节：0x00000001 (WEBVIEW_FLAGS_SHOWBYDEFAULT) 。
    
 _dwUnused[7]_
  
> 偏移0xC，28 个字节：全部为零。
    
 _cbData_
  
> 偏移0x28，4 字节：0x00000032。
    
 _wzURL_
  
> 偏移0x2C，0x32字节：25 个 WCHAR 的数组。 Unicode 以零结尾的字符串值 https://www.microsoft.com ：""。
    

