---
title: PidTagItemTemporaryflags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagItemTemporaryflags
api_type:
- HeaderDef
ms.assetid: 8066de8e-2b77-4bac-8df3-e64b03ee42b9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ec092e6cc6174e156dbfe7784143c9d74715eef7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357699"
---
# <a name="pidtagitemtemporaryflags-canonical-property"></a>PidTagItemTemporaryflags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指示邮件已阅读但未标记为 "已读" 的标志。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ITEM_TMPFLAGS  <br/> |
|标识符:  <br/> |0x1097  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性在 Outlook 的 "未读邮件" 搜索文件夹中使用, 以在不实际将邮件标记为 "已读" 的情况下跟踪已读取的邮件, 这会将其从文件夹中删除。 当视图更改时, 将删除此属性并将项目标记为已读。 此属性不会同步到 Exchange 服务器。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹操作。
    
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

