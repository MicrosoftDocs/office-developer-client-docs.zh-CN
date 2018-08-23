---
title: PidTagIpmAppointmentEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmAppointmentEntryId
api_type:
- HeaderDef
ms.assetid: a6e8c8fb-b76a-4a73-b112-6399e4d94233
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 64945d678051d2e3ae486395fb8ec6630de6a59e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571155"
---
# <a name="pidtagipmappointmententryid-canonical-property"></a>PidTagIpmAppointmentEntryId 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含 Outlook 日历文件夹的**EntryID** 。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IPM_APPOINTMENT_ENTRYID  <br/> |
|标识符：  <br/> |0x36D0  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Folder  <br/> |
   
## <a name="remarks"></a>注解

此属性存储和消息存储库的根文件夹中收件箱文件夹。 若要访问特定的邮件存储区上的属性，请执行以下过程。 
  
1. 首先，查找收件箱文件夹中的属性。 使用[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)获取收件箱文件夹的**EntryID**的引用。 
    
2. 如果**IMsgStore::GetReceiveFolder**操作成功，则使用**EntryID**的收件箱和[IMsgStore::OpenEntry](imsgstore-openentry.md)引用打开收件箱并获取**IMAPIFolder**对象的引用。 
    
3. 如果**IMsgStore::OpenEntry**成功，然后使用**IMAPIFolder**对象和[IMAPIProp::GetProps](imapiprop-getprops.md)返回的参考获取所需的属性。 
    
4. 如果步骤 1、 2 或 3 失败，查找的根文件夹中的属性。 若要执行的操作，使用**IMsgStore::OpenEntry**，指定 NULL 的**lpEntryID**，打开的邮件存储区的根文件夹，并获取**IMAPIFolder**对象的引用。 
    
5. 如果成功打开根文件夹，然后使用**IMAPIFolder**对象和**IMAPIProp::GetProps**返回的参考获取所需的属性。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。
    
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

