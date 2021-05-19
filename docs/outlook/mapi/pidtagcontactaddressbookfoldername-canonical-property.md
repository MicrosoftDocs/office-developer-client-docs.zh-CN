---
title: PidTagContactAddressBookFolderName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContactAddressBookFolderName
api_type:
- HeaderDef
ms.assetid: 6149da2f-6e42-429c-bcdb-d517d21df720
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0068b579bb570e49c4403baa017c550814af8f9a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419245"
---
# <a name="pidtagcontactaddressbookfoldername-canonical-property"></a>PidTagContactAddressBookFolderName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于通讯簿条目的文件夹名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAB_FOLDER_NAME、PR_CONTAB_FOLDER_NAME_W  <br/> |
|标识符:  <br/> |0x6613  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |联系人通讯簿  <br/> |
   
## <a name="remarks"></a>备注

文件夹名称中不能使用下列字符：
  
[ ] / \ &amp; ~ ? \* | \<\> " ; : +
  
## <a name="related-resources"></a>相关资源

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

