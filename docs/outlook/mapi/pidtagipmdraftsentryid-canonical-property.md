---
title: PidTagIpmDraftsEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmDraftsEntryId
api_type:
- HeaderDef
ms.assetid: 17d64211-6265-41f4-b016-3677d75af966
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e259c86803147d782469c8d86b23694d8b54e69d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327886"
---
# <a name="pidtagipmdraftsentryid-canonical-property"></a>PidTagIpmDraftsEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含"草稿Outlook的 **EntryID。** 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IPM_DRAFTS_ENTRYID  <br/> |
|标识符:  <br/> |0x36D7  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |文件夹  <br/> |
   
## <a name="remarks"></a>备注

此属性存储在收件箱文件夹以及邮件存储的根文件夹中。 若要访问特定邮件存储上的 属性，请执行下列操作： 
  
1. 首先，在"收件箱"文件夹中查找 属性。 使用 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 获取对 **"收件箱"文件夹的 EntryID** 的引用。 
    
2. 如果 **IMsgStore：：GetReceiveFolder** 成功，则使用对收件箱和 [IMsgStore：：OpenEntry](imsgstore-openentry.md) **的 EntryID** 的引用打开收件箱并获取对 **IMAPIFolder** 对象的引用。 
    
3. 如果 **IMsgStore：：OpenEntry** 成功，则使用对 **IMAPIFolder** 对象和 [IMAPIProp：：GetProps](imapiprop-getprops.md) 的返回引用获取所需属性。 
    
4. 如果步骤 1、2 或 3 失败，则查找根文件夹中的属性。 为此，请使用 **IMsgStore：：OpenEntry（** 为 **lpEntryID** 指定 NULL）打开邮件存储的根文件夹并获取对 **IMAPIFolder** 对象的引用。 
    
5. 如果打开根文件夹成功，则使用返回的 **对 IMAPIFolder** 对象和 **IMAPIProp：：GetProps** 的引用获取所需属性。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定用于创建和定位邮箱中特殊文件夹的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

