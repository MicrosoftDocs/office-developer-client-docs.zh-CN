---
title: PidTagIpmNoteEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmNoteEntryId
api_type:
- HeaderDef
ms.assetid: c003f7b9-b0cd-4656-98fa-3466fda6832c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3d465bfeb30d4f2964254b1d1f524f964fde7239
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327869"
---
# <a name="pidtagipmnoteentryid-canonical-property"></a>PidTagIpmNoteEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 Outlook "便笺" 文件夹的**EntryID** 。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IPM_NOTE_ENTRYID  <br/> |
|标识符:  <br/> |0x36D3  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Folder  <br/> |
   
## <a name="remarks"></a>注解

此属性存储在 "收件箱" 文件夹以及邮件存储区的根文件夹中。 若要访问特定邮件存储区上的属性, 请执行以下操作: 
  
1. 首先, 在 "收件箱" 文件夹中查找属性。 使用[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)获取对 "收件箱" 文件夹的**EntryID**的引用。 
    
2. 如果 * * IMsgStore:: GetReceiveFolder * * 成功, 则使用对收件箱和[IMsgStore:: OpenEntry](imsgstore-openentry.md)的**EntryID**的引用打开收件箱, 并获取对**IMAPIFolder**对象的引用。 
    
3. 如果**IMsgStore:: OpenEntry**成功, 则使用返回的**IMAPIFolder**对象引用和[IMAPIProp:: GetProps](imapiprop-getprops.md)获取所需的属性。 
    
4. 如果步骤1、2或3出现故障, 请查找根文件夹中的属性。 若要执行此操作, 请使用**IMsgStore:: OpenEntry**, 为**lpEntryID**指定 NULL, 以打开邮件存储区的根文件夹, 并获取对**IMAPIFolder**对象的引用。 
    
5. 如果打开根文件夹成功, 则使用返回的**IMAPIFolder**对象引用和**IMAPIProp:: GetProps**获取所需的属性。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定用于创建和定位邮箱中的特殊文件夹的属性和操作。
    
[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

