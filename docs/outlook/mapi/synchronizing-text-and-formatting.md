---
title: 同步文本和格式
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d7e166f0-1214-4571-b9a8-366960772a7a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 852ef988566ade8fca6551bea0d618199319d1d4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435101"
---
# <a name="synchronizing-text-and-formatting"></a>同步文本和格式

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在 RTF 邮件中发送 RTF 格式 (的主要) 是使文本与格式保持同步。 为了确保在邮件到达其目标位置时，它们作为预期的来源，并且文本和格式已同步，MAPI 提供了 [RTFSync](rtfsync.md) 函数。 **RTFSync** 通常由 RTF 感知客户端在显示传入邮件之前调用，而 MAPI 后台程序在将邮件下载到传输提供程序时调用。 调用方通过向 **RTFSync** 传递一个或两个标志来指定可能存在差异的区域：
  
- RTF_SYNC_BODY_CHANGED指示邮件文本中的修改。
    
- RTF_SYNC_RTF_CHANGED用于指示邮件格式的修改。
    
**RTFSync** 中发生的同步过程是邮件文本的复杂的循环冗余检查 (CRC) 忽略某些字符并转换其他字符。 最有可能由传输提供程序添加的字符将被忽略。 MAPI 定义用于 RTF 的几个属性，如下表所述。 
  
|**RTF 属性**|**说明**|
|:-----|:-----|
|**PR_RTF_SYNC_BODY_TAG (** [PidTagRtfSyncBodyTag](pidtagrtfsyncbodytag-canonical-property.md))   <br/> |指示真实邮件文本的开头。  <br/> |
|**PR_RTF_SYNC_BODY_CRC (** [PidTagRtfSyncBodyCrc](pidtagrtfsyncbodycrc-canonical-property.md))   <br/> |包含邮件文本的循环冗余检查的结果。  <br/> |
|**PR_RTF_SYNC_BODY_COUNT (** [PidTagRtfSyncBodyCount](pidtagrtfsyncbodycount-canonical-property.md))   <br/> |包含文件 中的字符 **PR_RTF_SYNC_BODY_CRC。**  <br/> |
|**PR_RTF_IN_SYNC (** [PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))   <br/> |如果邮件文本和格式已同步，则设置为 TRUE。  <br/> |
|**PR_RTF_SYNC_PREFIX_COUNT (** [PidTagRtfSyncPrefixCount](pidtagrtfsyncprefixcount-canonical-property.md))   <br/> |包含邮件文本之前的非空字符数。  <br/> |
|**PR_RTF_SYNC_TRAILING_COUNT (** [PidTagRtfSyncTrailingCount)](pidtagrtfsynctrailingcount-canonical-property.md)  <br/> |包含邮件文本结尾的非空字符数。  <br/> |
   

