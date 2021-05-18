---
title: PidTagLastVerbExecuted 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLastVerbExecuted
api_type:
- HeaderDef
ms.assetid: 502f0261-697f-41bf-8530-75e1d0f503e5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9abd4eb955428595ebe41ab9b2c661303ee2779a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279613"
---
# <a name="pidtaglastverbexecuted-canonical-property"></a>PidTagLastVerbExecuted 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含执行的最后一个动作。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_LAST_VERB_EXECUTED  <br/> |
|标识符:  <br/> |0x1081  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |历史记录  <br/> |
   
## <a name="remarks"></a>备注

此属性可以具有以下值之一：
  
|**Verb**|**属性值**|
|:-----|:-----|
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
|送达回执  <br/> |0x00000108  <br/> |
|已读回执  <br/> |0x00000109  <br/> |
|未送达回执  <br/> |0x0000010A  <br/> |
|未读回执  <br/> |0x0000010B  <br/> |
|Recall_S邮件  <br/> |0x0000010C  <br/> |
|Recall_F邮件  <br/> |0x0000010D  <br/> |
|跟踪邮件  <br/> |0x0000010E  <br/> |
|外出Office邮件  <br/> |0x0000011B  <br/> |
|撤回邮件  <br/> |0x0000011C  <br/> |
|跟踪的邮件  <br/> |0x00000139  <br/> |
|联系人  <br/> |0x00000200  <br/> |
|通讯组列表  <br/> |0x00000201  <br/> |
|粘滞便笺，蓝色  <br/> |0x00000300  <br/> |
|粘滞便笺，绿色  <br/> |0x00000301  <br/> |
|粘滞便笺，粉色  <br/> |0x00000302  <br/> |
|粘滞便笺，黄色  <br/> |0x00000303  <br/> |
|粘滞便笺，白色  <br/> |0x00000304  <br/> |
|单实例约会  <br/> |0x00000400  <br/> |
|定期约会  <br/> |0x00000401  <br/> |
|单实例会议  <br/> |0x00000402  <br/> |
|定期会议  <br/> |0x00000403  <br/> |
|会议请求/完整更新  <br/> |0x00000404  <br/> |
|接受  <br/> |0x00000405  <br/> |
|拒绝  <br/> |0x00000406  <br/> |
|暂时接受  <br/> |0x00000407  <br/> |
|Cancelation  <br/> |0x00000408  <br/> |
|信息更新  <br/> |0x00000409  <br/> |
|任务/任务更新  <br/> |0x00000500  <br/> |
|未分配定期任务  <br/> |0x00000501  <br/> |
|被分派人的任务  <br/> |0x00000502  <br/> |
|分配者的任务  <br/> |0x00000503  <br/> |
|任务要求  <br/> |0x00000504  <br/> |
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
|日记任务  <br/> |0x0000060B  <br/> |
|日记信函  <br/> |0x0000060C  <br/> |
|Journal Microsoft Office Word  <br/> |0x0000060D  <br/> |
|日记Microsoft Office Excel  <br/> |0x0000060E  <br/> |
|日记Microsoft Office PowerPoint  <br/> |0x0000060F  <br/> |
|Journal Microsoft Office Access  <br/> |0x00000610  <br/> |
|日记文档  <br/> |0x00000612  <br/> |
|日记会议  <br/> |0x00000613  <br/> |
|日记会议取消  <br/> |0x00000614  <br/> |
|日记远程会话  <br/> |0x00000615  <br/> |
|新邮件  <br/> |0xFFFFFFFF  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> 
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

