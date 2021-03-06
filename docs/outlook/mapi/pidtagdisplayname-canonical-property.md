---
title: PidTagDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayName
api_type:
- HeaderDef
ms.assetid: bd094e00-5c60-4bb3-9a45-b943fab52876
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 834141fe3e57fde5e6404776e0ad5ce3b438450e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360800"
---
# <a name="pidtagdisplayname-canonical-property"></a>PidTagDisplayName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含显示名称 MAPI 对象的属性。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DISPLAY_NAME、PR_DISPLAY_NAME_A、PR_DISPLAY_NAME_W  <br/> |
|标识符:  <br/> |0x3001  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI common  <br/> |
   
## <a name="remarks"></a>备注

文件夹要求同级子文件夹具有唯一的显示名称。 例如，如果文件夹包含两个子文件夹，这两个子文件夹不能对此属性使用相同的值。 此限制不适用于其他容器，如通讯簿和通讯组列表。 
  
服务提供商应设置此属性的值，以便它包含提供程序类型和配置信息。 其他信息有助于区分相同类型的提供程序的实例。 未配置的提供程序应该使用命名提供程序的字符串。 配置的提供程序应该使用相同的字符串，后跟括号中的区分字符串。 例如，未配置的邮件存储提供程序可能会将这些属性设置为： 
  
个人信息存储
  
然后，配置的版本可以设置以下属性： 
  
个人信息存储 (1998 年 2 月 6 日) 
  
对于 status 对象，这些属性包含用户界面可以显示的组件的名称。 
  
> [!NOTE]
> 在 MAPI 邮件的收件人姓名中不能使用分号。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹操作。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表允许的属性和操作。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
[[MS-XWDVSEC]](https://msdn.microsoft.com/library/dc043d09-6b76-4392-aea3-68f8e81c64d8%28Office.15%29.aspx)
  
> 扩展 WebDAV 协议，该协议指定如何通过 WebDAV Exchange请求和设置安全描述符。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagTransmittableDisplayName 规范属性](pidtagtransmittabledisplayname-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

