---
title: PidTagIconIndex 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIconIndex
api_type:
- HeaderDef
ms.assetid: 35bb0d6d-41d4-47d6-b161-be3721894201
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 35d9d0a50539f8aab2d26730dd4e4544c2535e60
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346618"
---
# <a name="pidtagiconindex-canonical-property"></a>PidTagIconIndex 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个数字，指示在显示一组电子邮件对象时要使用哪个图标。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ICON_INDEX  <br/> |
|标识符:  <br/> |0x1080  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性（如果存在）是客户端的提示。 客户端可能会忽略此属性的值。 
  
|**邮件项目状态**|**图标索引**|
|:-----|:-----|
|新邮件  <br/> |0xFFFFFFFF  <br/> |
|文章  <br/> |0x00000001  <br/> |
|其他  <br/> |0x00000003  <br/> |
|阅读邮件  <br/> |0x00000100  <br/> |
|未读邮件  <br/> |0x00000101  <br/> |
|提交的邮件  <br/> |0x00000102  <br/> |
|未发送的邮件  <br/> |0x00000103  <br/> |
|回执邮件  <br/> |0x00000104  <br/> |
|答复的邮件  <br/> |0x00000105  <br/> |
|转发的邮件  <br/> |0x00000106  <br/> |
|远程邮件  <br/> |0x00000107  <br/> |
|传递邮件  <br/> |0x00000108  <br/> |
|阅读邮件  <br/> |0x00000109  <br/> |
|未送达邮件  <br/> |0x0000010A  <br/> |
|非读邮件  <br/> |0x0000010B  <br/> |
|Recall_S邮件  <br/> |0x0000010C  <br/> |
|Recall_F邮件  <br/> |0x0000010D  <br/> |
|跟踪邮件  <br/> |0x0000010E  <br/> |
|外出邮件  <br/> |0x0000011B  <br/> |
|撤回邮件  <br/> |0x0000011C  <br/> |
|跟踪的邮件  <br/> |0x00000130  <br/> |
|联系人  <br/> |0x00000200  <br/> |
|通讯组列表  <br/> |0x00000202  <br/> |
|粘滞便笺蓝色  <br/> |0x00000300  <br/> |
|粘滞便笺绿色  <br/> |0x00000301  <br/> |
|粘滞便笺粉色  <br/> |0x00000302  <br/> |
|粘滞便笺黄色  <br/> |0x00000303  <br/> |
|粘滞便笺白色  <br/> |0x00000304  <br/> |
|单实例约会  <br/> |0x00000400  <br/> |
|定期约会  <br/> |0x00000401  <br/> |
|单实例会议  <br/> |0x00000402  <br/> |
|定期会议  <br/> |0x00000403  <br/> |
|会议请求  <br/> |0x00000404  <br/> |
|接受  <br/> |0x00000405  <br/> |
|拒绝  <br/> |0x00000406  <br/> |
|一个百年  <br/> |0x00000407  <br/> |
|取消  <br/> |0x00000408  <br/> |
|信息更新  <br/> |0x00000409  <br/> |
|任务/任务  <br/> |0x00000500  <br/> |
|未分配定期任务  <br/> |0x00000501  <br/> |
|被分派人的任务  <br/> |0x00000502  <br/> |
|分配者的任务  <br/> |0x00000503  <br/> |
|任务请求  <br/> |0x00000504  <br/> |
|任务接受  <br/> |0x00000505  <br/> |
|任务拒绝  <br/> |0x00000506  <br/> |
|日记对话  <br/> |0x00000601  <br/> |
|日记电子邮件  <br/> |0x00000602  <br/> |
|日记会议请求  <br/> |0x00000603  <br/> |
|日记会议响应  <br/> |0x00000604  <br/> |
|日记任务请求  <br/> |0x00000606  <br/> |
|日记任务响应  <br/> |0x00000607  <br/> |
|日记注释  <br/> |0x00000608  <br/> |
|日记传真  <br/> |0x00000609  <br/> |
|日记电话呼叫  <br/> |0x0000060A  <br/> |
|日记字母  <br/> |0x0000060C  <br/> |
|Journal Microsoft Office Word  <br/> |0x0000060D  <br/> |
|Journal Microsoft Office Excel  <br/> |0x0000060E  <br/> |
|Journal Microsoft Office PowerPoint  <br/> |0x0000060F  <br/> |
|Journal Microsoft Office Access  <br/> |0x00000610  <br/> |
|日记文档  <br/> |0x00000612  <br/> |
|日记会议  <br/> |0x00000613  <br/> |
|日记会议取消  <br/> |0x00000614  <br/> |
|日记远程会话  <br/> |0x00000615  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许对电子邮件对象执行的属性和操作。
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 指定对联系人和个人通讯组列表允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

