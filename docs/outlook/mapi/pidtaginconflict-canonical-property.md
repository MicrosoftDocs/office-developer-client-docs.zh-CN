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
  
当附件代表备用副本时, 该参数包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IN_CONFLICT  <br/> |
|标识符:  <br/> |0x666C  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |冲突注释  <br/> |
   
## <a name="remarks"></a>注解

同步期间, 电子邮件客户端和服务器必须生成冲突解决消息, 以检测副本中的当前版本的邮件的冲突。 请务必了解, 在当前同步操作过程中, 本地副本中的邮件的当前版本可能已传输。 当服务器上已存在冲突时, 将发生这种情况, 在将任何冲突的邮件下载到本地副本之前。 冲突解决邮件必须作为相互冲突的 PCLs 的独立副本进行同步。 冲突解决邮件本身不得在客户端和服务器之间同步;只应交换独立的副本。 然后, 同步伙伴必须生成与冲突邮件的结构相匹配的新邮件。 因此, 客户端和服务器应使用相同的算法来检测 "入选方" 项, 这一点非常重要。 必须应用以下规则来检测 "入选方":
  
1. 上次修改时间。
    
2. 较高的 CN GUID (使用内存比较) 中断关联。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理服务器和客户端之间的同步邮件对象数据。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

