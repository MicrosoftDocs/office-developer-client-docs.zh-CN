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
ms.openlocfilehash: 2dc431d807bd74640e5b5a9c020f668b13530197
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778437"
---
# <a name="pidtagservicesupportfiles-canonical-property"></a>PidTagServiceSupportFiles 规范属性

  
  
**适用于**： Outlook 
  
包含属于邮件服务的文件列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_SUPPORT_FILES，PR_SERVICE_SUPPORT_FILES_A，PR_SERVICE_SUPPORT_FILES_W  <br/> |
|标识符：  <br/> |0x3D0F  <br/> |
|数据类型：  <br/> |PT_MV_STRING8 PT_MV_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>说明

使用控制面板中的对话框，用户可以获得的文件属于邮件服务的列表。 例如，用户可以获得的所有动态链接库 (Dll) 属于该服务的名称。 然后，用户可以查找有关指定的文件，如名称和版本号的所有 Dll 的其他详细信息。 MAPI 使用这些属性在消息用户所选内容的对话框中创建支持文件列表。
  
MAPI 仅适用于文件名，并在其他字符串传递给它，在 Active Directory 服务接口 (ANSI) 字符集。 使用文件名的原始设备制造商 (OEM) 字符集中的客户端应用程序必须将其转换为 ANSI 调用 MAPI 之前。
  
## <a name="related-resources"></a>相关资源

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

