---
title: PidLidContactItemData 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactItemData
api_type:
- COM
ms.assetid: 411e8f81-c2b9-440a-9e9a-d6add5e4be63
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 510920af290fa1cfe13fc1a85ba72f902532c539
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776728"
---
# <a name="pidlidcontactitemdata-canonical-property"></a>PidLidContactItemData 规范属性

  
  
**适用于**： Outlook 
  
用于显示的联系人信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidContactItemData  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008007  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>说明

如果存在此参数，则该属性必须具有六个条目，每个对应于应用程序的用户界面中可见字段。
  
|**基于一个索引的多值属性**|**值必须是下列选项之一**|**说明**|
|:-----|:-----|:-----|
|1  <br/> |0x00000001  <br/> |应用程序应显示联系人的住宅地址。  <br/> |
|1  <br/> |0x00000002:uc 或 0x00000000  <br/> |应用程序应显示联系人的工作。  <br/> |
|1  <br/> |0x00000003  <br/> |应用程序应显示联系人的其他地址。  <br/> |
|2  <br/> |0x00008080  <br/> |应用程序应显示电子邮件 1。  <br/> |
|2  <br/> |0x00008090  <br/> |应用程序应显示电子邮件 2。  <br/> |
|2  <br/> |0x000080A0  <br/> |应用程序应显示电子邮件 3。  <br/> |
|3,4,5,6  <br/> |PropertyID 的任一电话属性或任何[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中指定的传真号码。  <br/> |应用程序应显示的相应属性。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

