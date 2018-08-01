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
ms.openlocfilehash: 48dfced07a8fd78a1af22679759effbd3c6da343
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777302"
---
# <a name="pidtagaddressbookchoosedirectoryautomatically-canonical-property"></a>PidTagAddressBookChooseDirectoryAutomatically 规范属性

  
  
**适用于**： Outlook 
  
启用 Microsoft Outlook 2010 和 Microsoft Outlook 2013，选择最合适的全局地址列表 (GAL) 或联系人的当前邮箱文件夹。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY  <br/> |
|标识符：  <br/> |0x3D1C000B  <br/> |
|属性类型  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>说明

此属性对应于通讯簿选项对话框中的**自动选择**设置。 当此属性存在 IID_CAPONE_PROF 配置文件一节，并设置为**true**，通讯簿对话框不再默认为[SetDefaultDir](iaddrbook-setdefaultdir.md)方法中，指定的容器，但选择通讯簿的 Outlook 2010 或 Outlook 2013考虑适用于在其中显示对话框中的上下文。 请注意，这可能会导致不好的体验的第三方通讯簿提供程序。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[MAPI 常量](mapi-constants.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

