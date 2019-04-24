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
ms.openlocfilehash: 031e5483539ce17c8b9b994690985c2349573e27
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319507"
---
# <a name="pidlidcontactitemdata-canonical-property"></a>PidLidContactItemData 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
用于显示联系人信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidContactItemData  <br/> |
|属性集:  <br/> |PSETID_Address  <br/> |
|长 ID (盖子):  <br/> |0x00008007  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |Contact  <br/> |
   
## <a name="remarks"></a>注解

如果存在, 则该属性必须有六个条目, 每个条目对应于应用程序用户界面中的可见字段。
  
|**多值属性中的从1开始的索引**|**值必须是下列值之一**|**说明**|
|:-----|:-----|:-----|
|1  <br/> |0x00000001  <br/> |应用程序应显示联系人的住宅地址。  <br/> |
|1  <br/> |0x00000002 或0x00000000  <br/> |应用程序应显示联系人的工作。  <br/> |
|1  <br/> |0x00000003  <br/> |应用程序应显示联系人的其他地址。  <br/> |
|双面  <br/> |0x00008080  <br/> |应用程序应显示 Email1。  <br/> |
|双面  <br/> |0x00008090  <br/> |应用程序应显示 Email2。  <br/> |
|双面  <br/> |0x000080A0  <br/> |应用程序应显示 Email3。  <br/> |
|3、4、5、6  <br/> |PropertyID [[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中指定的任何电话属性或任何传真号码。  <br/> |应用程序应显示相应的属性。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

