---
title: PidTagAccessControlListTable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAccess
api_type:
- HeaderDef
ms.assetid: 48667fda-ddc4-42ac-9231-761db0a4c1a9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9c71a2b806b810906c13ea4750e5491b1544f640
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424502"
---
# <a name="pidtagaccesscontrollisttable-canonical-property"></a>PidTagAccessControlListTable 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个表, 该表由应用于文件夹的所有系统访问控制列表 (SACL) 组成。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ACL_TABLE  <br/> |
|标识符:  <br/> |0x3FE0  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |访问控制  <br/> |
   
## <a name="remarks"></a>说明

此属性在 Exchange 服务器上的所有 folder 对象上都存在。 此属性中包含的值用于读取和修改文件夹的访问控制列表 (acl)。 您可以将[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法与**IID_IExchangeModifyTable**接口标识符一起使用, 以获取文件夹上的 ACL 表的[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)接口。 您可以使用此接口读取和修改这些 acl。 
  
## <a name="related-resources"></a>相关资源

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

