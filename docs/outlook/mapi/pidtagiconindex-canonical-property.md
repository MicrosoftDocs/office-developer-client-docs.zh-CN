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
ms.openlocfilehash: 83ab01363d478d197286bfa8f7b5b092a7ffd5a6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777703"
---
# <a name="pidtagiconindex-canonical-property"></a>PidTagIconIndex 规范属性

  
  
**适用于**： Outlook 
  
包含一个数字，指示显示一组电子邮件对象时要使用的图标。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ICON_INDEX  <br/> |
|标识符：  <br/> |0x1080  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

此属性，如果存在，为对客户端的提示。 客户端可能会忽略此属性的值。 
  
|**邮件项目状态**|**图标索引**|
|:-----|:-----|
|新邮件  <br/> |0xFFFFFFFF  <br/> |
|帖子  <br/> |0x00000001  <br/> |
|其他  <br/> |0x00000003  <br/> |
|阅读邮件  <br/> |0x00000100  <br/> |
|未读的邮件  <br/> |0x00000101  <br/> |
|提交的邮件  <br/> |0x00000102  <br/> |
|未发送的邮件  <br/> |0x00000103  <br/> |
|接收邮件  <br/> |0x00000104  <br/> |
|答复的邮件  <br/> |0x00000105  <br/> |
|转发的邮件  <br/> |0x00000106  <br/> |
|远程邮件  <br/> |0x00000107  <br/> |
|传递邮件  <br/> |0x00000108  <br/> |
|阅读邮件  <br/> |0x00000109  <br/> |
|原件邮件  <br/> |0x0000010A  <br/> |
|Nonread 的邮件  <br/> |0x0000010B  <br/> |
|Recall_S 邮件  <br/> |0x0000010C  <br/> |
|Recall_F 邮件  <br/> |0x0000010D  <br/> |
|跟踪邮件  <br/> |0x0000010E  <br/> |
|利用 office 邮件  <br/> |0x0000011B  <br/> |
|邮件撤回  <br/> |0x0000011C  <br/> |
|跟踪的邮件  <br/> |0x00000130  <br/> |
|联系人  <br/> |0x00000200  <br/> |
|通讯组列表  <br/> |0x00000202  <br/> |
|粘滞便笺蓝色  <br/> |0x00000300  <br/> |
|粘滞便笺绿色  <br/> |0x00000301  <br/> |
|粘滞便笺粉色  <br/> |0x00000302  <br/> |
|粘滞便笺黄色  <br/> |0x00000303  <br/> |
|粘滞便笺白皮书  <br/> |0x00000304  <br/> |
|单实例约会  <br/> |0x00000400  <br/> |
|定期约会  <br/> |0x00000401  <br/> |
|单实例会议  <br/> |0x00000402  <br/> |
|定期会议  <br/> |0x00000403  <br/> |
|会议请求  <br/> |0x00000404  <br/> |
|Accept  <br/> |0x00000405  <br/> |
|拒绝  <br/> |0x00000406  <br/> |
|Tentativly  <br/> |0x00000407  <br/> |
|取消  <br/> |0x00000408  <br/> |
|信息性更新  <br/> |0x00000409  <br/> |
|任务/任务  <br/> |0x00000500  <br/> |
|未分配的定期任务  <br/> |0x00000501  <br/> |
|代理人的任务  <br/> |0x00000502  <br/> |
|分配人的任务  <br/> |0x00000503  <br/> |
|任务要求  <br/> |0x00000504  <br/> |
|接受任务  <br/> |0x00000505  <br/> |
|任务拒绝  <br/> |0x00000506  <br/> |
|日记对话  <br/> |0x00000601  <br/> |
|日记电子邮件  <br/> |0x00000602  <br/> |
|日记会议请求  <br/> |0x00000603  <br/> |
|日记会议响应  <br/> |0x00000604  <br/> |
|日志任务要求  <br/> |0x00000606  <br/> |
|日志任务响应  <br/> |0x00000607  <br/> |
|日记注释  <br/> |0x00000608  <br/> |
|日记传真  <br/> |0x00000609  <br/> |
|日记电话呼叫  <br/> |0x0000060A  <br/> |
|日记字母  <br/> |0x0000060C  <br/> |
|日记 Microsoft Office Word  <br/> |0x0000060D  <br/> |
|日记 Microsoft Office Excel  <br/> |0x0000060E  <br/> |
|日记 Microsoft Office PowerPoint  <br/> |0x0000060F  <br/> |
|日记 Microsoft Office Access  <br/> |0x00000610  <br/> |
|日记文档  <br/> |0x00000612  <br/> |
|日记会议  <br/> |0x00000613  <br/> |
|日记会议取消  <br/> |0x00000614  <br/> |
|日记远程会话  <br/> |0x00000615  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象在允许的操作。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
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

