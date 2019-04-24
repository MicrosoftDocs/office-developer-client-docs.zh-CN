---
title: PidTagDisplayTypeEx 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayTypeEx
api_type:
- HeaderDef
ms.assetid: 23074402-6ac1-47f1-8a49-b8909f98a26e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6eea30188543cb06545a9efad705f5593d4227a7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360772"
---
# <a name="pidtagdisplaytypeex-canonical-property"></a>PidTagDisplayTypeEx 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含条目的类型, 这与在全局地址列表的表格行中的条目的显示方式有关。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DISPLAY_TYPE_EX  <br/> |
|标识符:  <br/> |0x3905  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 通讯簿  <br/> |
   
## <a name="remarks"></a>注解

此属性指定与在全局地址列表中的显示方式相对应的条目的类型。 它提供了在**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 中无法表示的其他信息。
  
> [!NOTE]
> **PR_DISPLAY_TYPE**和此属性的值以 "DT_" 开头, 并在 Mapitags 中定义。 未记录的所有值都是为 MAPI 保留的。 客户端应用程序不得定义任何新值, 并且必须准备处理未记录的值。 
  
有一些宏可帮助确定对象的属性, 例如, 它是本地、远程还是受安全性控制的对象。 这些宏包括: 
  
|**宏**|**值**|
|:-----|:-----|
|DTE_FLAG_REMOTE_VALID  <br/> |0x80000000  <br/> |
|DTE_FLAG_ACL_CAPABLE  <br/> |0x40000000  <br/> |
|DTE_MASK_REMOTE  <br/> |0x0000ff00  <br/> |
|DTE_MASK_LOCAL  <br/> |0x000000ff  <br/> |
|DTE_IS_REMOTE_VALID (v)  <br/> |(!!((v) &amp; DTE_FLAG_REMOTE_VALID)  <br/> |
|DTE_IS_ACL_CAPABLE (v)  <br/> |(!!((v) &amp; DTE_FLAG_ACL_CAPABLE))  <br/> |
|DTE_REMOTE (v)  <br/> |((v) &amp; DTE_MASK_REMOTE) \> \> 8)  <br/> |
|DTE_LOCAL (v)  <br/> |((v) &amp; DTE_MASK_LOCAL)  <br/> |
|DT_ROOM  <br/> |((ULONG) 0x00000007)  <br/> |
|DT_EQUIPMENT  <br/> |((ULONG) 0x00000008)  <br/> |
|DT_SEC_DISTLIST  <br/> |((ULONG) 0x00000009)  <br/> |
   
以下是有关如何使用这些宏的一些说明。 
  
- 若要检查某个条目是否为另一个林中的远程条目, 请将 DTE_IS_REMOTE_VALID 宏应用于此属性的值, 以检查该条目中是否设置了 DTE_FLAG_REMOTE_VALID 标志。 如果是远程条目, 则可以使用 DTE_REMOTE 宏查找远程条目的类型。 
    
- 在单林和跨林配置中, 如果**PR_DISPLAY_TYPE**的值为 DT_DISTLIST, 并且 DTE_IS_REMOTE_VALID 为 false, 则将宏 DTE_LOCAL 应用于此属性的值可以让您进一步将该对象的类型标识为可以是 DT_DISTLIST (一个通讯组列表) 或 DT_SEC_DISTLIST (安全通讯组列表)。 
    
- 如果将宏 DTE_LOCAL 应用于**PR_DISPLAY_TYPE_EX**的值, 并返回 DT_REMOTE_MAILUSER 类型, 则该条目为远程条目。 
    
- 在单个林或跨林配置 (其中复制由访问控制列表 (ACL) 控制) 中, 可以使用 DTE_IS_ACL_CAPABLE 宏来确定某个条目是否为安全主体。
    
在跨林配置中, **PR_DISPLAY_TYPE**具有 DT_REMOTE_MAILUSER 的值。 将宏 DTE_REMOTE 应用于此属性的值可允许您获取远程条目的类型。 可能的远程条目类型如下所示: 
  
|**远程条目的类型**|**Value**|**说明**|
|:-----|:-----|:-----|
|DT_AGENT  <br/> |((ULONG) 0x00000003)  <br/> |动态通讯组列表。  <br/> |
|DT_DISTLIST  <br/> |((ULONG) 0x00000001)  <br/> |通讯组列表。  <br/> |
|DT_EQUIPMENT  <br/> |((ULONG) 0x00000008)  <br/> |设备, 例如打印机或投影仪。  <br/> |
|DT_MAILUSER  <br/> |((ULONG) 0x00000000)  <br/> |拥有邮箱的用户。  <br/> |
|DT_REMOTE_MAILUSER  <br/> |((ULONG) 0x00000000)  <br/> |全局地址列表中的地址列表条目。  <br/> |
|DT_ROOM  <br/> |((ULONG) 0x00000007)  <br/> |会议室。  <br/> |
|DT_SEC_DISTLIST  <br/> |((ULONG) 0x00000009)  <br/> |安全通讯组列表。  <br/> |
   
在单个林和跨林配置中, 如果**PR_DISPLAY_TYPE**的值为 DT_DISTLIST, 并且 DTE_IS_REMOTE_VALID 为 false, 则将 DTE_LOCAL 宏应用于此属性的值可以允许您获取通讯组列表的类型. 通讯组列表的可能类型如下所示: 
  
|**通讯组列表的类型**|**Value**|**说明**|
|:-----|:-----|:-----|
|DT_DISTLIST  <br/> |((ULONG) 0x00000001)  <br/> |通讯组列表。  <br/> |
|DT_SEC_DISTLIST  <br/> |((ULONG) 0x00000009)  <br/> |安全通讯组列表。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源列表的属性和操作。
    
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

