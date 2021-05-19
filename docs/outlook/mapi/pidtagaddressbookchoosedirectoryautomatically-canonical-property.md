---
title: PidTagAddressBookChooseDirectoryAutomatically 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cecd0679-4bc2-4399-8f89-a4e17bb909a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 41fdaf333084b7d567f4e67ae9fd2638a1731349
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409662"
---
# <a name="pidtagaddressbookchoosedirectoryautomatically-canonical-property"></a>PidTagAddressBookChooseDirectoryAutomatically 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使Microsoft Outlook 2010和Microsoft Outlook 2013为当前邮箱选择 (GAL) 联系人文件夹中最合适的全局地址列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY  <br/> |
|标识符:  <br/> |0x3D1C000B  <br/> |
|属性类型  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>备注

此属性对应于"通讯簿 **选项"对话框中** 的"自动选择"设置。 当 IID_CAPONE_PROF 配置文件部分中存在此属性并设置为 **true** 时，通讯簿对话框不再默认为 [SetDefaultDir](iaddrbook-setdefaultdir.md)方法指定的容器，而是选择 Outlook 2010 或 Outlook 2013 认为适合显示对话框的上下文的通讯簿。 请注意，这可能会导致第三方通讯簿提供商体验不佳。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[MAPI 常量](mapi-constants.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

