---
title: attMessageStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8f55470a-65b3-4210-a7d2-9031cb17ca80
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d4dc72309ff090317b2353cab0b4fc2c5be41181
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430313"
---
# <a name="attmessagestatus"></a>attMessageStatus

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 消息标志映射到 TNEF 标志以保持向后兼容性。 所有标志都组合在一起，并采用单个字节进行编码。 映射如下所示：
  
|**MAPI 邮件标志**|**TNEF 标志**|
|:-----|:-----|
|MSGFLAG_READ  <br/> |fmsRead  <br/> |
|MSGFLAG_UNMODIFED  <br/> |~fmsModified  <br/> |
|MSGFLAG_SUBMIT  <br/> |fmsSubmitted  <br/> |
|MSGFLAG_HASATTACH  <br/> |fmsHasAttach  <br/> |
|MSGFLAG_UNSENT  <br/> |fmsLocal  <br/> |
   
这些标志在 TNEF 中定义。H 头文件。
  

