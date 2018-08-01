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
ms.openlocfilehash: d3a8dc45bb131f5d2e7ff370617a10e3096a99f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777300"
---
# <a name="pidtagadditionalrenentryidsex-canonical-property"></a>PidTagAdditionalRenEntryIdsEx 规范属性

  
  
**适用于**： Outlook 
  
包含一个 store 对象的特殊文件夹条目 Id。 此多值属性中的每个条目可以映射到一个或多个条目 Id，即，没有条目和其相关联的条目 Id-一对多关系。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ADDITIONAL_REN_ENTRYIDS_EX  <br/> |
|标识符：  <br/> |0x36D9  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Outlook 应用程序  <br/> |
   
## <a name="remarks"></a>说明

如果使用此属性，则它包含指定条目 Id 的文件夹的块的数组。 块按照指定以下四个表的格式。
  
**PersistData 块**

|**名称**|**类型**|**Size**|**说明**|
|:-----|:-----|:-----|:-----|
|**PersistID** <br/> |WORD  <br/> |2  <br/> |键入此**PersistData**条目标识符值。 请参阅有效的值列表中的"PersistBlockType 值"表。  <br/> |
|**DataElementsSize** <br/> |WORD  <br/> |2  <br/> |大小 （以字节为单位， **DataElements**字段）。  <br/> |
|**DataElements** <br/> |**PersistElement**块的数组  <br/> |变量  <br/> |指示存储存在多少**PersistElement**条目。 请参阅此结构的格式的"PersistElement 块"表。  <br/> |
   
**PersistBlockType 值**

|**名称**|**值**|**说明**|
|:-----|:-----|:-----|
|PERSIST_SENTINEL  <br/> |0x0000  <br/> |指示将处理没有更多的**PersistData**块。  <br/> |
|RSF_PID_RSS_SUBSCRIPTION  <br/> |0x8001  <br/> |指示此块包含数据的 RSS 订阅文件夹。  <br/> |
|RSF_PID_SEND_AND_TRACK  <br/> |0x8002  <br/> |指示此块包含跟踪邮件处理文件夹的数据。  <br/> |
|RSF_PID_TODO_SEARCH  <br/> |0x8004  <br/> |指示此块包含待办事项搜索文件夹的数据。  <br/> |
|RSF_PID_CONV_ACTIONS  <br/> |0x8006  <br/> |指示此块包含数据的对话操作设置文件夹。  <br/> |
|RSF_PID_COMBINED_ACTIONS  <br/> |0x8007  <br/> |保留此值。  <br/> |
|RSF_PID_SUGGESTED_CONTACTS  <br/> |0x8008  <br/> |指示此块包含建议的联系人文件夹的数据。  <br/> |
|RSF_PID_CONTACT_SEARCH  <br/> |0x8009  <br/> |指示此块包含联系人搜索文件夹的数据。  <br/> 仅由 Outlook。  <br/> |
|RSF_PID_BUDDYLIST_PDLS  <br/> |0x800A  <br/> |指示此块包含数据的即时消息 (IM) 联系人列表的文件夹。 引用文件夹包含个人通讯组列表 (PDLs) 表示 IM 联系人列表中的每个组。  <br/> Outlook 和 Exchange 使用。  <br/> |
|RSF_PID_BUDDYLIST_CONTACTS  <br/> |0x800B  <br/> |指示此块包含数据的 IM 联系人文件夹。 引用文件夹包含单个联系人的 IM 联系人列表组引用。  <br/> Outlook 和 Exchange 使用。  <br/> |
   
如果**PersistBlockType**值不是所定义此处， **PersistData**块被忽略，直到处理 PERSIST_SENTINEL **PersistID**或达到流末尾继续处理。 
  
**PersistElementBlock**

|**名称**|**类型**|**Size**|**说明**|
|:-----|:-----|:-----|:-----|
|**ElementID** <br/> |WORD  <br/> |2  <br/> |指定此**PersistElement**块的类型标识符值。 请参阅有效的值的列表的"PersistElementType 值"表。  <br/> |
|**ElementDataSize** <br/> |WORD  <br/> |2  <br/> |指定的大小，以字节为单位， **ElementData**字段。  <br/> |
|**ElementData** <br/> |二进制数据的数组  <br/> |变量  <br/> |包含数据的此**PersistID** + **ElementID**对。  <br/> |
   
**PersistElementType 值**

|**名称**|**值**|**ElementDataSize 的值**|**说明**|
|:-----|:-----|:-----|:-----|
|RSF_ELID_HEADER  <br/> |0x0002  <br/> |0x0004  <br/> |指示此块**ElementData**字段包含 DWORD 标头值。 如何解释此值取决于的块**PersistID**类型。  <br/> 对于[[MS OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb.aspx)中指定的所有**PersistID**类型，此值为零。  <br/> |
|RSF_ELID_ENTRYID  <br/> |0x0001  <br/> |变量  <br/> |指示此块包含**PersistID**指定的文件夹的**EntryID** 。  <br/> |
|ELEMENT_SENTINEL  <br/> |0x0000  <br/> |0x0000  <br/> |指示将处理没有更多的**PersistElement**块。  <br/> |
   
如果**PersistElementType**值不是所定义此处， **PersistElement**块被忽略，直到处理 ELEMENT_SENTINEL **ElementID**或达到流末尾继续处理。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许处理的允许/阻止列表，并确定的垃圾邮件。
    
[[MS OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。
    
[[MS OXPHISH]](http://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)
  
> 标识，并将标记旨在到非可靠来源欺骗透露敏感信息 （如密码和其他个人信息） 的收件人的电子邮件。
    
### <a name="header-files"></a>头文件

Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

