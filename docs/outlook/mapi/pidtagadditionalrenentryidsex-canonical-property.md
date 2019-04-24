---
title: PidTagAdditionalRenEntryIdsEx 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAdditionalRenEntryIdsEx
api_type:
- HeaderDef
ms.assetid: b5e896e7-c0c6-4ad1-bf91-9daba3a1e4d4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 57ab68d4c53693c769a4aadf8737f57ef5e73fcd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335201"
---
# <a name="pidtagadditionalrenentryidsex-canonical-property"></a>PidTagAdditionalRenEntryIdsEx 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 store 对象的特殊文件夹条目 id。 此多值属性中的每个条目都可以映射到一个或多个条目 id, 也就是说, 条目与其关联的条目 id 之间存在一对多关系。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ADDITIONAL_REN_ENTRYIDS_EX  <br/> |
|标识符:  <br/> |0x36D9  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Outlook 应用程序  <br/> |
   
## <a name="remarks"></a>注解

如果使用此属性, 则它包含指定文件夹的条目 id 的一组块。 这些块遵循以下四个表指定的格式。
  
**PersistData 块**

|**Name**|**Type**|**Size**|**Description**|
|:-----|:-----|:-----|:-----|
|**PersistID** <br/> |WORD  <br/> |双面  <br/> |此**PersistData**条目的类型标识符值。 有关有效值的列表, 请参阅 "PersistBlockType Values" 表。  <br/> |
|**DataElementsSize** <br/> |WORD  <br/> |双面  <br/> |**DataElements**字段的大小 (以字节为单位)。  <br/> |
|**DataElements** <br/> |**PersistElement**块的数组  <br/> |变量  <br/> |指示存储区中存在的**PersistElement**条目的数量。 有关此结构的格式, 请参阅 "PersistElement Block" 表。  <br/> |
   
**PersistBlockType 值**

|**名称**|**Value**|**说明**|
|:-----|:-----|:-----|
|PERSIST_SENTINEL  <br/> |0x0000  <br/> |指示将不会处理更多的**PersistData**块。  <br/> |
|RSF_PID_RSS_SUBSCRIPTION  <br/> |0x8001  <br/> |指示此块包含 "RSS 订阅" 文件夹的数据。  <br/> |
|RSF_PID_SEND_AND_TRACK  <br/> |0x8002  <br/> |指示此块包含所跟踪的邮件处理文件夹的数据。  <br/> |
|RSF_PID_TODO_SEARCH  <br/> |0x8004  <br/> |指示此块包含待办搜索文件夹的数据。  <br/> |
|RSF_PID_CONV_ACTIONS  <br/> |0x8006  <br/> |指示此块包含对话动作设置文件夹的数据。  <br/> |
|RSF_PID_COMBINED_ACTIONS  <br/> |0x8007  <br/> |此值为保留值。  <br/> |
|RSF_PID_SUGGESTED_CONTACTS  <br/> |0x8008  <br/> |指示此块包含建议的 "联系人" 文件夹的数据。  <br/> |
|RSF_PID_CONTACT_SEARCH  <br/> |0x8009  <br/> |指示此块包含联系人搜索文件夹的数据。  <br/> 仅供 Outlook 使用。  <br/> |
|RSF_PID_BUDDYLIST_PDLS  <br/> |0x800A  <br/> |指示此块包含 "即时消息 (IM) 联系人列表" 文件夹的数据。 引用的文件夹包含表示 IM 联系人列表中的每个组的个人通讯组列表 (PDLs)。  <br/> 由 Outlook 和 Exchange 使用。  <br/> |
|RSF_PID_BUDDYLIST_CONTACTS  <br/> |0x800B  <br/> |指示此块包含 IM 联系人文件夹的数据。 引用的文件夹包含 IM 联系人列表组所引用的各个联系人。  <br/> 由 Outlook 和 Exchange 使用。  <br/> |
   
如果**PersistBlockType**值不是在此处定义的值之一, 则将忽略**PersistData**块, 并继续处理, 直到处理 PERSIST_SENTINEL **PersistID**或到达流的末尾。 
  
**PersistElementBlock**

|**Name**|**Type**|**Size**|**Description**|
|:-----|:-----|:-----|:-----|
|**ElementID** <br/> |WORD  <br/> |双面  <br/> |指定此**PersistElement**块的类型标识符值。 有关有效值的列表, 请参阅 "PersistElementType Values" 表。  <br/> |
|**ElementDataSize** <br/> |WORD  <br/> |双面  <br/> |指定**ElementData**字段的大小 (以字节为单位)。  <br/> |
|**ElementData** <br/> |二进制数据数组  <br/> |变量  <br/> |包含此**PersistID** + **ElementID**对的数据。  <br/> |
   
**PersistElementType 值**

|**名称**|**值**|**ElementDataSize 的值**|**Description**|
|:-----|:-----|:-----|:-----|
|RSF_ELID_HEADER  <br/> |0x0002  <br/> |0x0004  <br/> |指示此块的**ElementData**字段包含 DWORD 标头值。 此值的解释方式取决于块的**PersistID**类型。  <br/> 对于[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb.aspx)中指定的所有**PersistID**类型, 此值为零。  <br/> |
|RSF_ELID_ENTRYID  <br/> |0x0001  <br/> |变量  <br/> |指示此块包含**PersistID**指定的文件夹的**EntryID** 。  <br/> |
|ELEMENT_SENTINEL  <br/> |0x0000  <br/> |0x0000  <br/> |指示将不会处理更多的**PersistElement**块。  <br/> |
   
如果**PersistElementType**值不是在此处定义的值之一, 则将忽略**PersistElement**块, 并继续处理, 直到处理 ELEMENT_SENTINEL **ElementID**或到达流的末尾。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 启用对允许/阻止列表的处理以及确定垃圾邮件。
    
[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定用于创建和定位邮箱中的特殊文件夹的属性和操作。
    
[[毫秒-OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)
  
> 标识和标记旨在欺骗收件人的电子邮件, 以将敏感信息 (如密码和其他个人信息) 泄漏到非信任源。
    
### <a name="header-files"></a>头文件

Mapitags
  
> 包含列为关联属性的属性的定义。
    
mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

