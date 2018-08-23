---
title: 同步文本和格式设置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d7e166f0-1214-4571-b9a8-366960772a7a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d797932a9fd22944f1cfd78e7fb67cd3ddbf8632
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588816"
---
# <a name="synchronizing-text-and-formatting"></a>同步文本和格式设置

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
发送富文本格式 (RTF) 邮件的主要难题保持同步带格式的文本。 若要确保时邮件到达其目标它们以适合其原始发件人和文本和格式的同步、 MAPI 提供了[RTFSync](rtfsync.md)函数。 **RTFSync**通常调用之前显示传入消息的 RTF 感知客户端和 MAPI 后台处理程序时其下载到传输提供程序的消息。 呼叫者通过将一个或两个标志传递给**RTFSync**指定可能的区别的区域：
  
- 指示消息文本中的修改的 RTF_SYNC_BODY_CHANGED。
    
- RTF_SYNC_RTF_CHANGED 以指示邮件格式中的修改。
    
**RTFSync**中发生的同步过程是消息文本，将忽略某些字符并将其他人转换的复杂循环冗余检查 (CRC)。 很可能由传输提供程序添加的字符将被忽略。 MAPI 定义用于处理 RTF 下, 表中所述的几个属性。 
  
|**RTF 属性**|**说明**|
|:-----|:-----|
|**PR_RTF_SYNC_BODY_TAG**([PidTagRtfSyncBodyTag](pidtagrtfsyncbodytag-canonical-property.md))  <br/> |指示实际消息文本的开头。  <br/> |
|**PR_RTF_SYNC_BODY_CRC**([PidTagRtfSyncBodyCrc](pidtagrtfsyncbodycrc-canonical-property.md))  <br/> |包含消息文本的循环冗余检查的结果。  <br/> |
|**PR_RTF_SYNC_BODY_COUNT**([PidTagRtfSyncBodyCount](pidtagrtfsyncbodycount-canonical-property.md))  <br/> |包含**PR_RTF_SYNC_BODY_CRC**中的字符数。  <br/> |
|**PR_RTF_IN_SYNC**([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))  <br/> |设置为 true 时，邮件已同步文本和格式。  <br/> |
|**PR_RTF_SYNC_PREFIX_COUNT**([PidTagRtfSyncPrefixCount](pidtagrtfsyncprefixcount-canonical-property.md))  <br/> |包含 nonwhitespace 字符数的低于消息文本。  <br/> |
|**PR_RTF_SYNC_TRAILING_COUNT**([PidTagRtfSyncTrailingCount](pidtagrtfsynctrailingcount-canonical-property.md))  <br/> |包含跟踪消息文本的 nonwhitespace 字符的数。  <br/> |
   

