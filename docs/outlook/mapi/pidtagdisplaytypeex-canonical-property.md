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
ms.openlocfilehash: 30482f7d6acef7377a1b63bc3de4e43be48d8608
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583356"
---
# <a name="pidtagdisplaytypeex-canonical-property"></a>PidTagDisplayTypeEx 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一个条目，相对于如何条目应显示在表中的行的全局地址列表的类型。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DISPLAY_TYPE_EX  <br/> |
|标识符：  <br/> |0x3905  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 通讯簿  <br/> |
   
## <a name="remarks"></a>注解

此属性指定的一个条目，相对于它的全局地址列表中显示的方式的类型。 它提供不能用**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 表示的其他信息。
  
> [!NOTE]
> **PR_DISPLAY_TYPE**和此属性的值以"DT_"开头，并且在 Mapitags.h 中定义。 MAPI 的保留未进行归档的所有值。 客户端应用程序无需定义的任何新值，必须在准备好处理一个未记录的值。 
  
有一些可帮助确定如它是本地、 远程或安全控制对象的属性的宏。 这些宏包括： 
  
|**宏**|**值**|
|:-----|:-----|
|DTE_FLAG_REMOTE_VALID  <br/> |0x80000000)  <br/> |
|DTE_FLAG_ACL_CAPABLE  <br/> |0x40000000  <br/> |
|DTE_MASK_REMOTE  <br/> |0x0000ff00  <br/> |
|DTE_MASK_LOCAL  <br/> |0x000000ff  <br/> |
|DTE_IS_REMOTE_VALID(v)  <br/> |(!!(（v) &amp; DTE_FLAG_REMOTE_VALID)  <br/> |
|DTE_IS_ACL_CAPABLE(v)  <br/> |(!!(（v) &amp; DTE_FLAG_ACL_CAPABLE))  <br/> |
|DTE_REMOTE(v)  <br/> |((（v) &amp; DTE_MASK_REMOTE) \> \> 8)  <br/> |
|DTE_LOCAL(v)  <br/> |(（v) &amp; DTE_MASK_LOCAL)  <br/> |
|DT_ROOM  <br/> |（满足） 0X00000007）  <br/> |
|DT_EQUIPMENT  <br/> |（满足） 0X00000008）  <br/> |
|DT_SEC_DISTLIST  <br/> |（满足） 0X00000009）  <br/> |
   
以下是几个说明有关如何使用这些宏。 
  
- 若要检查是否条目是另一个林中远程条目，应用于此属性以检查是否在条目中设置 DTE_FLAG_REMOTE_VALID 标志的值 DTE_IS_REMOTE_VALID 宏。 如果是远程的条目，然后，您可以找到出远程条目的类型使用 DTE_REMOTE 宏。 
    
- 在单林和跨林配置中，当**PR_DISPLAY_TYPE**具有 DT_DISTLIST 和 DTE_IS_REMOTE_VALID 的值为 false，将宏 DTE_LOCAL 应用于此属性的值可以让您进一步标识为对象的类型DT_DISTLIST （通讯组列表） 或 DT_SEC_DISTLIST （安全通讯组列表）。 
    
- 如果宏 DTE_LOCAL 于**PR_DISPLAY_TYPE_EX**的值，它返回类型 DT_REMOTE_MAILUSER 项将是远程项。 
    
- 在单个林或跨林配置的复制控制的访问控制列表 (ACL) 中，您可以使用 DTE_IS_ACL_CAPABLE 宏来确定一个条目的安全主体。
    
在跨林配置中， **PR_DISPLAY_TYPE**有 DT_REMOTE_MAILUSER 值。 将宏 DTE_REMOTE 应用于此属性的值可以让您获取的远程条目类型。 可能的远程条目类型如下所示： 
  
|**远程条目的类型**|**值**|**说明**|
|:-----|:-----|:-----|
|DT_AGENT  <br/> |（满足） 0X00000003）  <br/> |动态通讯组列表。  <br/> |
|DT_DISTLIST  <br/> |（满足） 0X00000001）  <br/> |通讯组列表。  <br/> |
|DT_EQUIPMENT  <br/> |（满足） 0X00000008）  <br/> |设备，例如，打印机或投影仪。  <br/> |
|DT_MAILUSER  <br/> |（满足） 0X00000000）  <br/> |具有邮箱的用户。  <br/> |
|DT_REMOTE_MAILUSER  <br/> |（满足） 0X00000000）  <br/> |全局地址列表中的地址列表条目。  <br/> |
|DT_ROOM  <br/> |（满足） 0X00000007）  <br/> |会议室。  <br/> |
|DT_SEC_DISTLIST  <br/> |（满足） 0X00000009）  <br/> |安全通讯组列表。  <br/> |
   
在这两个单林和跨林配置，当**PR_DISPLAY_TYPE**具有 DT_DISTLIST 和 DTE_IS_REMOTE_VALID 的值为 false，将 DTE_LOCAL 宏应用于此属性的值可以让您获取的通讯组列表类型. 可能的通讯组列表类型如下所示： 
  
|**通讯组列表的类型**|**值**|**说明**|
|:-----|:-----|:-----|
|DT_DISTLIST  <br/> |（满足） 0X00000001）  <br/> |通讯组列表。  <br/> |
|DT_SEC_DISTLIST  <br/> |（满足） 0X00000009）  <br/> |安全通讯组列表。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

