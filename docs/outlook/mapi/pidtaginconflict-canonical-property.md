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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384435"
---
# <a name="pidtaginconflict-canonical-property"></a>PidTagInConflict 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 TRUE 时附件表示备用的副本。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IN_CONFLICT  <br/> |
|标识符：  <br/> |0x666C  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |冲突注释  <br/> |
   
## <a name="remarks"></a>说明

同步过程中副本中检测针对一条消息的当前版本冲突时的电子邮件客户端和服务器必须生成冲突解决消息。 务必了解可能会在当前的同步操作过程中已传输的当前版本中的本地副本的消息。 当已存在冲突的服务器上的任何冲突消息已下载到的本地副本之前，将发生此错误。 冲突解决消息必须作为具有冲突 Pcl 的独立副本进行同步。 冲突解决消息本身不必须同步客户端和服务器; 之间应交换仅的独立副本。 同步伙伴然后必须生成新消息相匹配的结构冲突消息。 因此，很重要的客户端和服务器使用相同的算法来检测"获胜"项。 必须应用以下规则来检测"入选":
  
1. 上次修改时间。
    
2. 更高版本 （使用内存比较） 的 CN GUID 中断领结。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 同步服务器和客户端之间的消息对象数据的句柄。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

