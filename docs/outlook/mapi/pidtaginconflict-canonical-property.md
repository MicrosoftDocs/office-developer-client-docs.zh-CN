---
title: PidTagInConflict 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInConflict
api_type:
- HeaderDef
ms.assetid: e83c05c6-a7c0-486c-a112-58a39255767a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fc2774efed1a15fe79e167149f2cb162bae7642c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358532"
---
# <a name="pidtaginconflict-canonical-property"></a>PidTagInConflict 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果附件代表备用副本，则包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IN_CONFLICT  <br/> |
|标识符:  <br/> |0x666C  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |冲突注释  <br/> |
   
## <a name="remarks"></a>备注

在同步期间，当检测到副本中邮件的当前版本存在冲突时，电子邮件客户端和服务器必须生成冲突解决邮件。 必须了解的是，本地副本中的邮件的当前版本是在当前同步操作期间传输的。 在将任何冲突消息下载到本地副本之前，服务器上已存在冲突时，将发生此情况。 冲突解决消息必须同步为具有冲突 PCLs 的独立副本。 冲突解决邮件本身不得在客户端和服务器之间同步;应仅交换独立副本。 然后，同步伙伴必须生成与冲突消息的结构相匹配的新消息。 因此，客户端和服务器使用相同的算法检测"获胜方"项目非常重要。 必须应用以下规则来检测"获胜方"：
  
1. 上次修改时间。
    
2. 更高的 CN GUID (使用内存比较) 中断关系。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理在服务器和客户端之间同步邮件对象数据。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

