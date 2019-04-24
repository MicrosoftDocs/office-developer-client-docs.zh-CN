---
title: PidTagServiceSupportFiles 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceSupportFiles
api_type:
- COM
ms.assetid: df4be986-62a8-49d6-8eca-25b55c74f830
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3753177552d45e32e53ae192a9dfae15b601afcc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359470"
---
# <a name="pidtagservicesupportfiles-canonical-property"></a>PidTagServiceSupportFiles 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含属于邮件服务的文件的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_SUPPORT_FILES、PR_SERVICE_SUPPORT_FILES_A、PR_SERVICE_SUPPORT_FILES_W  <br/> |
|标识符:  <br/> |0x3D0F  <br/> |
|数据类型：  <br/> |PT_MV_STRING8、PT_MV_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>注解

通过在控制面板小程序中使用对话框, 用户可以获取属于邮件服务的文件的列表。 例如, 用户可以获取属于该服务的所有动态链接库 (dll) 的名称。 然后, 用户可以查找有关指定文件的其他详细信息, 如所有 dll 的名称和版本号。 MAPI 使用这些属性在用于邮件用户选择的对话框中创建支持文件列表。
  
MAPI 仅适用于在 Active Directory 服务接口 (ANSI) 字符集中的文件名和传递给它的其他字符串。 使用原始设备制造商 (OEM) 字符集中的文件名的客户端应用程序必须先将其转换为 ANSI, 然后再调用 MAPI。
  
## <a name="related-resources"></a>相关资源

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

